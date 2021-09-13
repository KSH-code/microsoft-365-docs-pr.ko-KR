---
title: 끝점 API에 Microsoft Defender 사용
ms.reviewer: ''
description: 사용자 없이 끝점용 Microsoft Defender에 프로그래밍 Windows 프로그래밍 방식의 앱을 디자인하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, 배우, 경고, 장치, 사용자, 도메인, ip, 파일, 고급 헌팅, 쿼리
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 4c5cf3c759d0ea779e8070ad3474013a765fee95
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221911"
---
# <a name="use-microsoft-defender-for-endpoint-apis"></a>끝점 API에 Microsoft Defender 사용

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

이 페이지에서는 사용자를 대신하여 끝점용 Defender에 프로그래밍 방식 액세스 권한을 부여하는 응용 프로그램을 만드는 방법을 설명합니다.

사용자가 없는 프로그래밍식 액세스가 필요한 경우 응용 프로그램 컨텍스트를 통해 [끝점용 Microsoft Defender 액세스를 참조합니다.](exposed-apis-create-app-webapp.md)

필요한 액세스 권한이 확실하지 않은 경우 소개 페이지를 [읽어 하세요.](apis-intro.md)

끝점용 Microsoft Defender는 프로그래밍 API 집합을 통해 많은 데이터와 작업을 노출합니다. 이러한 API를 사용하면 작업 흐름을 자동화하고 끝점용 Microsoft Defender 기능을 기반으로 혁신할 수 있습니다. API 액세스에는 OAuth2.0 인증이 필요합니다. 자세한 내용은 [OAuth 2.0 Authorization Code Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

일반적으로 API를 사용하려면 다음 단계를 수행해야 합니다.

- AAD 응용 프로그램 만들기
- 이 응용 프로그램을 사용하여 액세스 토큰 얻기
- 토큰을 사용하여 Endpoint API용 Defender 액세스

이 페이지에서는 AAD 응용 프로그램을 만들고, 끝점용 Microsoft Defender에 대한 액세스 토큰을 다운로드하고, 토큰의 유효성을 검사하는 방법을 설명합니다.

> [!NOTE]
> 사용자를 대신하여 Microsoft Defender for Endpoint API에 액세스할 때 올바른 응용 프로그램 권한 및 사용자 권한이 필요합니다.
> 끝점용 Microsoft Defender에 대한 사용자 권한에 익숙하지 않은 경우 역할 기반 액세스 제어를 사용하여 포털 액세스 [관리를 참조합니다.](rbac.md)

> [!TIP]
> 포털에서 작업을 수행할 수 있는 권한이 있는 경우 API에서 작업을 수행할 수 있는 권한이 있습니다.

## <a name="create-an-app"></a>앱 만들기

1. 전역 관리자 역할이 있는 사용자 계정으로 [Azure에](https://portal.azure.com) **로그온합니다.**

2. 앱 등록 **Azure Active Directory** \> **새** \> **등록으로 이동합니다.**

   ![응용 프로그램 Microsoft Azure 탐색하는 이미지입니다.](images/atp-azure-new-app2.png)

3. 응용 **프로그램 등록 페이지가** 나타나면 응용 프로그램의 등록 정보를 입력합니다.
   - **이름** - 앱 사용자에게 표시할 의미 있는 응용 프로그램 이름을 입력합니다.
   - **지원되는 계정 유형** - 응용 프로그램에서 지원할 계정을 선택합니다.

   <br>

   ****

   |지원 계정 유형|설명|
   |---|---|
   |**이 조직 디렉터리의 계정만**|LOB(LOB) 응용 프로그램을 구축하는 경우 이 옵션을 선택합니다. 디렉터리에 응용 프로그램을 등록하지 않는 경우 이 옵션을 사용할 수 없습니다. <p> 이 옵션은 Azure AD 단일 테넌트에만 매핑됩니다. <p> 디렉터리 외부에서 앱을 등록하지 않는 한 이 옵션이 기본 옵션입니다. 앱이 디렉터리 외부에 등록되는 경우 기본값은 Azure AD 다중 테넌트 및 개인 Microsoft 계정입니다.|
   |**조직 디렉터리의 계정**|모든 비즈니스 및 교육 고객을 대상으로 지정하려면 이 옵션을 선택합니다. <p> 이 옵션은 Azure AD 전용 다중 테넌트에 매핑됩니다. <p> Azure AD 전용 단일 테넌트로 앱을 등록한 경우 Azure AD 다중 테넌트로 업데이트하고 인증 블레이드를 통해 다시 단일 테넌트로 업데이트할 **수** 있습니다.|
   |**조직 디렉터리 및 개인 Microsoft 계정의 계정**|가장 광범위한 고객을 대상으로 지정하려면 이 옵션을 선택합니다. <p> 이 옵션은 Azure AD 다중 테넌트 및 개인 Microsoft 계정에 매핑됩니다. <p> Azure AD 다중 테넌트 및 개인 Microsoft 계정으로 앱을 등록한 경우 UI에서 이 계정을 변경할 수 없습니다. 대신 응용 프로그램 매니페스트 편집기를 사용하여 지원되는 계정 유형을 변경해야 합니다.|
   |

   - **리디렉션 URI(선택 사항)** - 구축할 앱의 **유형,** 웹 또는 공용 클라이언트(모바일 & 데스크톱)를 선택한 다음 응용 프로그램에 대한 리디렉션 URI(또는 회신 **URL)를** 입력합니다.
     - 웹 응용 프로그램의 경우 앱의 기본 URL을 제공합니다. 예를 들어 로컬 컴퓨터로 실행되는 `http://localhost:31544` 웹앱의 URL일 수 있습니다. 사용자는 이 URL을 사용하여 웹 클라이언트 응용 프로그램에 로그인합니다.
     - 공용 클라이언트 응용 프로그램의 경우 Azure AD에서 토큰 응답을 반환하는 데 사용하는 URI를 제공합니다. 응용 프로그램 관련 값(예: )을 `myapp://auth` 입력합니다.

     웹 응용 프로그램 또는 네이티브 응용 프로그램에 대한 특정 예제를 확인한 다음 빠른 [시작 을 참조합니다.](/azure/active-directory/develop/#quickstarts)

     완료되면 등록을 **선택합니다.**

4. 응용 프로그램에서 끝점용 Microsoft Defender에 액세스하여 '경고 읽기' 권한을 할당하도록 허용합니다.

   - 응용 프로그램 페이지에서 **조직에서** 사용하는 API 권한 추가 API를 선택하고 \>  \>  **windowsDefenderATP를 > WindowsDefenderATP를** **선택합니다.**
   - **참고:** *WindowsDefenderATP가* 원래 목록에 나타나지 않습니다. 텍스트 상자에 이름을 입력하여 표시를 시작하십시오.

     ![사용 권한을 추가합니다.](images/add-permission.png)

   - 사용 **권한 위임 선택** \> **Alert.Read** > 사용 권한 **추가를 선택합니다.**

      ![응용 프로그램 사용 권한.](images/application-permissions-public-client.png)

   - **중요 참고** 사항: 관련 사용 권한을 선택합니다. 읽기 알림은 예시일 뿐입니다.

     예를 들어

     - 고급 [쿼리를 실행하려면](run-advanced-query-api.md)'고급 쿼리 실행' 사용 권한을 선택합니다.
     - 장치를 [격리하려면](isolate-machine.md)'컴퓨터 격리' 권한을 선택합니다.
     - 필요한 사용 권한을 확인하려면  호출할 API의 사용 권한 섹션을 참조하세요.

   - 동의 **부여를 선택합니다.**

      **참고:** 권한을 추가할 때마다 **새** 사용 권한을 적용하기 위한 동의 부여에서 선택해야 합니다.

      ![권한 부여 이미지.](images/grant-consent.png)

5. 응용 프로그램 ID 및 테넌트 ID를 기록해 써야 합니다.

   - 응용 프로그램 페이지에서 개요로 이동하여 **다음** 정보를 복사합니다.

   ![생성된 앱 ID의 이미지입니다.](images/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a>액세스 토큰을 얻게 됩니다.

AAD 토큰에 대한 자세한 내용은 [Azure AD 자습서를 참조하세요.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

### <a name="using-c"></a>C 사용\#

- 응용 프로그램에서 아래 클래스를 복사/붙여넣습니다.
- 응용 프로그램 ID, 테넌트 ID, 사용자 이름 및 암호와 함께 **AcquireUserTokenAsync** 메서드를 사용하여 토큰을 획득합니다.

    ```csharp
    namespace WindowsDefenderATP
    {
        using System.Net.Http;
        using System.Text;
        using System.Threading.Tasks;
        using Newtonsoft.Json.Linq;

        public static class WindowsDefenderATPUtils
        {
            private const string Authority = "https://login.microsoftonline.com";

            private const string WdatpResourceId = "https://api.securitycenter.microsoft.com";

            public static async Task<string> AcquireUserTokenAsync(string username, string password, string appId, string tenantId)
            {
                using (var httpClient = new HttpClient())
                {
                    var urlEncodedBody = $"resource={WdatpResourceId}&client_id={appId}&grant_type=password&username={username}&password={password}";

                    var stringContent = new StringContent(urlEncodedBody, Encoding.UTF8, "application/x-www-form-urlencoded");

                    using (var response = await httpClient.PostAsync($"{Authority}/{tenantId}/oauth2/token", stringContent).ConfigureAwait(false))
                    {
                        response.EnsureSuccessStatusCode();

                        var json = await response.Content.ReadAsStringAsync().ConfigureAwait(false);

                        var jObject = JObject.Parse(json);

                        return jObject["access_token"].Value<string>();
                    }
                }
            }
        }
    }
    ```

## <a name="validate-the-token"></a>토큰 유효성 검사

올바른 토큰이 있는지 확인합니다.

- 이전 단계에서 얻은 토큰을 디코딩하기 위해 [JWT에](https://jwt.ms) 복사/붙여넣기
- 원하는 앱 사용 권한으로 'scp' 클레임 확인
- 아래 스크린샷에서는 자습서에서 앱에서 획득한 디코딩된 토큰을 볼 수 있습니다.

![토큰 유효성 검사의 이미지입니다.](images/nativeapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>토큰을 사용하여 끝점 API용 Microsoft Defender에 액세스

- 사용하려는 API 선택 - [끝점 API에](exposed-apis-list.md) 지원되는 Microsoft Defender
- "Bearer {token}"으로 보내는 HTTP 요청에서 권한 부여 헤더 설정(Bearer는 권한 부여 체계)
- 토큰의 만료 시간은 1시간입니다(동일한 토큰을 사용하여 두 개 이상의 요청을 보낼 수 있습니다).

- 다음을 사용하여 경고 목록을 들이기 위한 요청을 **보내는 C#**

    ```csharp
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="see-also"></a>참고 항목

- [끝점 API용 Microsoft Defender](exposed-apis-list.md)
- [응용 프로그램 컨텍스트를 통해 끝점용 Microsoft Defender 액세스](exposed-apis-create-app-webapp.md)
