---
title: 사용자를 대신하여 Microsoft 365 Defender API에 액세스하는 앱 만들기
description: 사용자를 대신하여 Microsoft 365 Defender API에 액세스하는 방법을 학습합니다.
keywords: 액세스, 사용자 대신 api, 응용 프로그램, 사용자, 액세스 토큰, 토큰,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 720707ab58ff5de8ddc64ac1df717d9812227735
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220095"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a>사용자를 대신하여 Microsoft 365 Defender API에 액세스하는 앱 만들기

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다. Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.

이 페이지에서는 단일 사용자를 대신하여 응용 프로그램에 프로그래밍 Microsoft 365 Defender 응용 프로그램을 만드는 방법을 설명합니다.

정의된 사용자 없이 Microsoft 365 Defender 프로그래밍 액세스 권한이 필요한 경우(예: 백그라운드 앱 또는 데몬을 작성하는 경우) 사용자 없이 앱에 액세스하는 Microsoft 365 Defender [만들기를 참조하세요.](api-create-app-web.md) 대규모 조직 또는 고객 그룹에게 서비스를 제공하는 경우와 같은 여러 테넌트에 대한 액세스를 제공해야 하는 경우 파트너 액세스 권한이 있는 앱 만들기를 Microsoft 365 Defender [참조하세요.](api-partner-access.md) 필요한 액세스 종류가 확실하지 않은 경우 [시작을 참조합니다.](api-access.md)

Microsoft 365 Defender API 집합을 통해 많은 데이터와 작업을 노출합니다. 이러한 API를 사용하면 워크플로를 자동화하고 워크플로의 Microsoft 365 Defender 사용할 수 있습니다. 이 API 액세스에는 OAuth2.0 인증이 필요합니다. 자세한 내용은 [OAuth 2.0 Authorization Code Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

일반적으로 이러한 API를 사용하려면 다음 단계를 수행해야 합니다.

- Azure AD(Azure Active Directory 응용 프로그램을 만들 수 있습니다.
- 이 응용 프로그램을 사용하여 액세스 토큰을 얻습니다.
- 토큰을 사용하여 API에 Microsoft 365 Defender 있습니다.

이 문서에서는 이러한 방법을 설명합니다.

- Azure AD 응용 프로그램 만들기
- 액세스 토큰을 Microsoft 365 Defender
- 토큰 유효성 검사

> [!NOTE]
> 사용자를 Microsoft 365 Defender API에 액세스할 때 올바른 응용 프로그램 사용 권한 및 사용자 권한이 필요합니다.

> [!TIP]
> 포털에서 작업을 수행할 수 있는 권한이 있는 경우 API에서 작업을 수행할 수 있는 권한이 있습니다.

## <a name="create-an-app"></a>앱 만들기

1. 전역 관리자 역할을 사용하여 [사용자로 Azure에](https://portal.azure.com) **로그인합니다.**

2. 앱 등록 **Azure Active Directory**  >  **새**  >  **등록으로 이동합니다.**

   ![응용 프로그램 Microsoft Azure 탐색하는 이미지입니다.](../../media/atp-azure-new-app2.png)

3. 양식에서 응용 프로그램의 이름을 선택하고 리디렉션 URI에 대해 다음 정보를 입력한 다음 등록을 **선택합니다.**

   ![응용 프로그램 만들기 창의 이미지입니다.](../../media/nativeapp-create2.PNG)

   - **응용 프로그램 유형:** 공용 클라이언트
   - **리디렉션 URI:**https://portal.azure.com

4. 응용 프로그램 페이지에서 **조직에서** 사용하는 API 권한 추가 권한 api를 >  >    >   Microsoft **Threat Protection을** 입력하고 **Microsoft Threat Protection을 선택합니다.** 이제 앱에서 앱에 액세스할 Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection은* 이전 이름인 Microsoft 365 Defender 목록에 나타나지 않습니다. 표시하려면 텍스트 상자에 이름을 쓰기 시작해야 합니다.

   ![API 권한 선택의 이미지입니다.](../../media/apis-in-my-org-tab.PNG)

   - 사용 **권한 위임 을 선택 합니다.** 시나리오에 대한 관련 사용 권한(예: **Incident.Read)을** 선택한 다음 사용 권한 추가 **를 선택합니다.**

   ![API 액세스 및 API 선택 이미지입니다.](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > 시나리오에 대한 관련 권한을 선택해야 합니다. *모든 인시던트 읽기는* 예시일 것입니다. 필요한 사용 권한을 확인하려면 호출할  API의 사용 권한 섹션을 참조하세요.
    >
    > 예를 들어 고급 [쿼리를 실행하려면](api-advanced-hunting.md)'고급 쿼리 실행' 권한을 선택합니다. 장치를 [격리하려면](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)'컴퓨터 격리' 권한을 선택합니다.

5. 관리자 **동의 부여를 선택합니다.** 권한을 추가할 때마다 권한을 적용하려면 **관리자** 동의 부여를 선택해야 합니다.

   ![권한 부여 이미지.](../../media/grant-consent-delegated.PNG)

6. 안전한 곳에 응용 프로그램 ID와 테넌트 ID를 기록합니다. 응용 프로그램 페이지 **개요** 아래에 나열됩니다.

   ![생성된 앱 ID의 이미지입니다.](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a>액세스 토큰을 얻게 됩니다.

토큰에 대한 Azure Active Directory [Azure AD 자습서를 참조하세요.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

### <a name="get-an-access-token-using-powershell"></a>PowerShell을 사용하여 액세스 토큰을 얻다

```PowerShell
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps } # Install the ADAL.PS package in case it's not already present

$tenantId = '' # Paste your directory (tenant) ID here.
$clientId = '' # Paste your application (client) ID here.
$redirectUri = '' # Paste your app's redirection URI

$authority = "https://login.windows.net/$tenantId"
$resourceUrl = 'https://api.security.microsoft.com'

$response = Get-ADALToken -Resource $resourceUrl -ClientId $clientId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip

$response.AccessToken
```

## <a name="validate-the-token"></a>토큰 유효성 검사

1. 토큰을 복사하여 [JWT에](https://jwt.ms) 붙여넣어 디코드합니다.
1. 디코딩된  토큰 내의 역할 클레임에 원하는 사용 권한이 포함되어 있는지 확인

다음 이미지에서는 , 및 권한을 사용하여 앱에서 획득한 디코딩된 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` 토큰을 볼 수 있습니다.

![토큰 유효성 검사의 이미지입니다.](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>토큰을 사용하여 Microsoft 365 Defender API에 액세스

1. 사용할 API(인시던트 또는 고급 헌팅)를 선택하십시오. 자세한 내용은 지원되는 [api를 Microsoft 365 Defender 참조하세요.](api-supported.md)
2. 보내고자 하는 http 요청에서 권한 부여 헤더를 로 설정하고, 권한 부여 체계인 `"Bearer" <token>` *Bearer를* 로 설정하고 유효성이 검사된 토큰이 됩니다. 
3. 토큰은 1시간 이내에 만료됩니다. 이 시간 동안 동일한 토큰을 사용하여 두 개 이상의 요청을 보낼 수 있습니다.

다음 예에서는 를 사용하여 인시던트 목록을 을(를) **요청하는 방법을 C#.**

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>관련 문서

- [Microsoft 365 Defender API 개요](api-overview.md)
- [MICROSOFT 365 DEFENDER API에 액세스](api-access.md)
- ['Hello world' 앱 만들기](api-hello-world.md)
- [사용자가 없는 앱에 액세스하는 Microsoft 365 Defender 만들기](api-create-app-web.md)
- [다중 테넌트 파트너가 액세스하여 테넌트 API에 Microsoft 365 Defender 만들기](api-partner-access.md)
- [API 제한 및 라이선싱에 대해 자세히 알아보기](api-terms.md)
- [오류 코드 이해](api-error-codes.md)
- [사용자 로그인 및 API 액세스에 대한 OAuth 2.0 권한 부여](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
