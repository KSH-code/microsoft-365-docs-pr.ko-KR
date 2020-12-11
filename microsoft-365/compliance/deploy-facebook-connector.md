---
title: Facebook 비즈니스 페이지 데이터를 보관할 커넥터 배포
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 관리자는 Facebook 비즈니스 페이지를 Microsoft 365로 가져오고 보관하는 기본 커넥터를 설정할 수 있습니다. 이 데이터를 Microsoft 365로 가져온 후 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 준수 기능을 사용하여 조직의 Facebook 데이터의 거버넌스를 관리할 수 있습니다.
ms.openlocfilehash: b771c50eb5c2eb5f99269f1f399d27043ebee6bb
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619954"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a>Facebook 비즈니스 페이지 데이터를 보관할 커넥터 배포

이 문서에는 Office 365 가져오기 서비스를 사용하여 Facebook 비즈니스 페이지에서 Microsoft 365로 데이터를 가져오는 커넥터를 배포하는 단계별 프로세스가 포함되어 있습니다. 이 프로세스에 대한 개략적인 개요와 Facebook 커넥터를 배포하는 데 필요한 필수 구성 사항 목록을 확인하려면 Facebook 데이터를 보관할 커넥터 [설정을 참조하세요.](archive-facebook-data-with-sample-connector.md)

## <a name="step-1-create-an-app-in-azure-active-directory"></a>1단계: Azure Active Directory에서 앱 만들기

1. 이동하여 전역 관리자 계정의 자격 <https://portal.azure.com> 증명을 사용하여 로그인합니다.

    ![AAD에서 앱 만들기](../media/FBCimage1.png)

2. 왼쪽 탐색 창에서 **Azure Active Directory를 클릭합니다.**

    ![Azure Active Directory 클릭](../media/FBCimage2.png)

3. 왼쪽 탐색 창에서 앱 등록(미리 **보기)을** 클릭한 다음 새 **등록을 클릭합니다.**

    ![Click **App registrations (Preview)** and then click **New registration**](../media/FBCimage3.png)

4. 응용 프로그램을 등록합니다. 리디렉션 URI에서 응용 프로그램 유형 드롭다운 목록에서 웹을 선택한 다음 <https://portal.azure.com> URI의 상자에 입력합니다.

   ![응용 프로그램 등록](../media/FBCimage4.png)

5. 응용 **프로그램(클라이언트) ID** 및 **디렉터리(테넌트) ID를** 복사하여 텍스트 파일 또는 기타 안전한 위치에 저장합니다. 이후 단계에서 이러한 IDS를 사용할 수 있습니다.

   ![응용 프로그램 ID 및 디렉터리 ID 복사 및 저장](../media/FBCimage5.png)

6. 새 **앱의 & 인증서로 이동하세요.**

   ![새 앱의 & 인증서로 이동](../media/FBCimage6.png)

7. 새 **클라이언트 비밀 클릭**

   ![새 클라이언트 비밀 클릭](../media/FBCimage7.png)

8. 새 비밀을 만드시다. 설명 상자에 비밀을 입력한 다음 만료 기간을 선택합니다.

    ![비밀을 입력한 다음 만료 기간을 선택](../media/FBCimage8.png)

9. 비밀 값을 복사하여 텍스트 파일 또는 다른 저장 위치에 저장합니다. 이후 단계에서 사용하는 AAD 응용 프로그램 비밀입니다.

   ![비밀 값 복사 및 저장](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>2단계: GitHub에서 Azure 계정으로 커넥터 웹 서비스 배포

1. 이 [GitHub 사이트로](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) 이동하여 **Azure에 배포를 클릭합니다.**

    ![Azure에 배포를 클릭합니다.](../media/FBCGithubApp.png)

2. **Azure에 배포를 클릭하면** 사용자 지정 템플릿 페이지를 사용하여 Azure Portal로 리디렉션됩니다. 기본 사항 **및**  설정 세부 정보를 입력하고 구매를 **클릭합니다.**

   - **구독:** Facebook 비즈니스 페이지 커넥터 웹 서비스를 배포할 Azure 구독을 선택합니다.

   - **리소스 그룹:** 새 리소스 그룹을 선택하거나 만들 수 있습니다. 리소스 그룹은 Azure 솔루션에 대한 관련 리소스를 보유하는 컨테이너입니다.

   - **위치:** 위치를 선택하십시오.

   - **웹앱 이름:** 커넥터 웹앱의 고유한 이름을 제공합니다. Th 이름은 3-18자 사이입니다. 이 이름은 Azure 앱 서비스 URL을 만드는 데 사용됩니다. 예를 들어 **fbconnector의** 웹 앱 이름을 제공하면 Azure 앱 서비스 URL이 **fbconnector.azurewebsites.net.**

   - **tenantId:** 1단계에서 Azure Active Directory에서 Facebook 커넥터 앱을 만들고 복사한 Microsoft 365 조직의 테넌트 ID입니다.

   - **APISecretKey:** 모든 값을 비밀로 입력할 수 있습니다. 5단계에서 커넥터 웹앱에 액세스하는 데 사용됩니다.

     ![리소스 만들기 및 저장소 계정 유형 클릭](../media/FBCimage12.png)

3. 배포가 성공하면 페이지는 다음 스크린샷과 비슷합니다.

   ![저장소를 클릭한 다음 저장소 계정을 클릭합니다.](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a>3단계: Facebook 앱 등록

1. Go to <https://developers.facebook.com> , log in using the credentials for the account for your organization's Facebook Business pages, and then click Add New **App.**

   ![Facebook 비즈니스용 새 앱 추가 페이지](../media/FBCimage25.png)

2. 새 앱 ID를 만드시다.

   ![새 앱 ID 만들기](../media/FBCimage26.png)

3. 왼쪽 탐색 창에서 제품  추가를 클릭한 다음 Facebook 로그인 타일에서 **설정을** 클릭합니다. 

   ![제품 추가를 클릭합니다.](../media/FBCimage27.png)

4. Facebook 로그인 통합 페이지에서 웹을 **클릭합니다.**

   ![Facebook 로그인 통합 페이지에서 웹 클릭](../media/FBCimage28.png)

5. Azure 앱 서비스 URL을 추가합니다. 예를 들면 `https://fbconnector.azurewebsites.net` 다음과 같습니다.

   ![Azure 앱 서비스 URL 추가](../media/FBCimage29.png)

6. Facebook 로그인 설정의 QuickStart 섹션을 완료합니다.

   ![빠른 시작 섹션 완료](../media/FBCimage30.png)

7. **Facebook** 로그인 아래의 왼쪽 탐색 창에서 설정을 클릭하고 유효한 OAuth 리디렉션 URI 상자에 **OAuth 리디렉션 URI를 추가합니다.**  connectorserviceuri의 값은 조직의 Azure 앱 서비스 URL인 **\<connectorserviceuri> /Views/FacebookOAuth** 형식을 `https://fbconnector.azurewebsites.net` 사용합니다.

   ![유효한 OAuth 리디렉션 URI 상자에 OAuth 리디렉션 URI 추가](../media/FBCimage31.png)

8. 왼쪽 탐색 창에서 제품  추가를 클릭한 다음 **Webhook을 클릭합니다.** 페이지 **풀다운** 메뉴에서 **페이지를 클릭합니다.**

   ![제품 추가를 클릭한 다음 **Webhook을 클릭합니다.](../media/FBCimage32.png)

9. Webhook 콜백 URL을 추가하고 확인 토큰을 추가합니다. 콜백 URL의 형식은 **<connectorserviceuri> /api/FbPageWebhook** 형식을 사용합니다. 여기서 connectorserviceuri의 값은 조직의 Azure 앱 서비스 URL입니다. 예를 들면 다음과 `https://fbconnector.azurewebsites.net` 같습니다.

   확인 토큰은 강력한 암호와 유사해야 합니다. 확인 토큰을 텍스트 파일 또는 다른 저장소 위치에 복사합니다.

   ![확인 토큰 추가](../media/FBCimage33.png)

10. 피드에 대한 끝점을 테스트하고 구독합니다.

    ![끝점 테스트 및 구독](../media/FBCimage34.png)

11. 개인 정보 URL, 앱 아이콘 및 비즈니스 사용을 추가합니다. 또한 앱 ID 및 앱 비밀을 텍스트 파일 또는 다른 저장소 위치에 복사합니다.

    ![개인 정보 URL, 앱 아이콘 및 비즈니스 사용 추가](../media/FBCimage35.png)

12. 앱을 공개합니다.

    ![앱을 공개로 만들기](../media/FBCimage36.png)

13. 관리자 또는 테스터 역할에 사용자를 추가합니다.

    ![관리자 또는 테스터 역할에 사용자 추가](../media/FBCimage37.png)

14. 페이지 공용 **콘텐츠 액세스 권한을 추가합니다.**

    ![페이지 공용 콘텐츠 액세스 권한 dd](../media/FBCimage38.png)

15. 페이지 관리 권한 추가

    ![페이지 관리 권한 추가](../media/FBCimage39.png)

16. Facebook에서 응용 프로그램을 검토합니다.

    ![Facebook에서 응용 프로그램을 검토합니다.](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a>4단계: 커넥터 웹앱 구성

1. (여기서 `https://<AzureAppResourceName>.azurewebsites.net` AzureAppResourceName은 4단계에서 명명한 Azure 앱 리소스의 이름)로 이동하세요. 예를 들어 이름이 **fbconnector이면**. `https://fbconnector.azurewebsites.net` 앱의 홈 페이지는 다음 스크린샷과 같습니다.

   ![커넥터 웹앱으로 이동](../media/FBCimage41.png)

2. 로그인 **페이지를** 표시하려면 구성을 클릭합니다.

   ![로그인 페이지를 표시하려면 구성을 클릭합니다.](../media/FBCimage42.png)

3. 테넌트 ID 상자에 2단계에서 획득한 테넌트 ID를 입력하거나 붙여넣습니다. 암호 상자에 APISecretKey(2단계에서 획득한 APISecretKey)를  입력하거나 붙여넣은 다음 구성 설정 설정을 클릭하여 구성 세부 정보 페이지를 표시합니다.

    ![테넌트 ID 및 암호를 사용하여 로그인하고 구성 세부 정보 페이지로 이동합니다.](../media/FBCimage43.png)

4. 다음 구성 설정을 입력합니다.

   - **Facebook 응용 프로그램 ID:** 3단계에서 획득한 Facebook 응용 프로그램의 앱 ID입니다.

   - **Facebook 응용 프로그램 비밀:** 3단계에서 획득한 Facebook 응용 프로그램의 앱 비밀입니다.

   - **Facebook webhook은 토큰을 검증합니다.** 3단계에서 만든 확인 토큰입니다.

   - **AAD 응용 프로그램 ID:** 1단계에서 만든 Azure Active Directory 앱의 응용 프로그램 ID입니다.

   - **AAD 응용 프로그램 비밀:** 1단계에서 만든 APISecretKey 비밀의 값입니다.

5. 연결선 **설정을** 저장하려면 저장을 클릭합니다.

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a>5단계: Microsoft 365 규정 준수 센터에서 Facebook 커넥터 설정

1. Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click Data **connectors** in the left nav.

2. 데이터 커넥터 **페이지에서** Facebook 비즈니스 페이지 **아래에 있는 보기를** **클릭합니다.**

3. Facebook 비즈니스 **페이지 페이지에서** 커넥터 **추가를 클릭합니다.**

4. 서비스 약관 **페이지에서** 수락을 **클릭합니다.**

5. 커넥터 **앱의** 자격 증명 추가 페이지에서 다음 정보를 입력하고 연결 유효성 검사를 **클릭합니다.**

   ![커넥터 앱 자격 증명 입력](../media/TCimage38.png)

   - 이름 **상자에** 커넥터의 이름(예: Facebook 뉴스 페이지)을 **입력합니다.**

   - 연결 **URL 상자에** Azure 앱 서비스 URL을 입력하거나 붙여넣습니다. 예를 들면 `https://fbconnector.azurewebsites.net` 다음과 같습니다.

   - 암호 **상자에** 2단계에서 추가한 APISecretKey 값을 입력하거나 붙여넣습니다.

   - Azure **앱 ID** 상자에 1단계에서 만든 AAD 응용 프로그램 ID로도 호출되는 응용 프로그램(클라이언트) ID의 값을 입력하거나 붙여넣습니다.

6. 연결의 유효성을 검사한 후 다음을 **클릭합니다.**

7. Microsoft **365** 인증 페이지에서 APISecretKey를 다시 입력하거나 붙여넣은 다음 **로그인 웹앱을 클릭합니다.**

8. Facebook 커넥터 앱 구성 페이지에서 **Facebook으로** 로그인을 클릭하고 조직의 Facebook 비즈니스 페이지에 대한 계정의 자격 증명을 사용하여 로그인합니다.  로그인한 Facebook 계정에 조직의 Facebook 비즈니스 페이지에 대한 관리자 역할이 할당되어 있는지 확인

   ![Facebook으로 로그인](../media/FBCimage50.png)

9. 로그인한 Facebook 계정으로 관리되는 비즈니스 페이지 목록이 표시됩니다. 보관할 페이지를 선택하고 다음을 **클릭합니다.**

   ![보관할 조직 비즈니스 페이지 선택](../media/FBCimage52.png)

10. **계속을** 클릭하여 커넥터 서비스 앱의 설정을 종료합니다.

11. 필터 **설정 페이지에서** 특정 연령의 항목을 처음에 가져오는 필터를 적용할 수 있습니다. 연령을 선택하고 다음을 **클릭합니다.**

12. 저장소 **위치** 선택 페이지에서 Facebook 항목을 가져올 Microsoft 365 사서함의 전자 메일 주소를 입력하고 다음을 **클릭합니다.**

13. **다음을** 클릭하여 커넥터 설정을 검토한 다음 **마친을** 클릭하여 커넥터 설정을 완료합니다.

14. 준수 센터에서 데이터 커넥터  페이지로 이동한 다음  커넥터 탭을 클릭하여 가져오기 프로세스의 진행률을 확인하십시오.
