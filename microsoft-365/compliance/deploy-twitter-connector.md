---
title: Twitter 데이터를 보관하는 커넥터 배포
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
ROBOTS: NOINDEX, NOFOLLOW
description: 관리자는 Twitter 데이터를 가져오고 보관할 네이티브 커넥터를 설정하여 기본 Microsoft 365. 이 데이터를 Microsoft 365 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용하여 조직의 Twitter 데이터의 거버넌스를 관리할 수 있습니다.
ms.openlocfilehash: bd0885c0b9893b79d36981d52f596d1e5d6b8396
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60757072"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a>Twitter 데이터를 보관하는 커넥터 배포

이 문서에는 가져오기 서비스를 사용하여 Office 365 Twitter 계정의 데이터를 가져오는 커넥터를 배포하는 단계별 프로세스가 포함되어 Microsoft 365. 이 프로세스에 대한 개략적인 개요와 Twitter 커넥터를 배포하는 데 필요한 필수 구성 항목 목록은 [Set up a connector to archive Twitter data을 참조하세요. ](archive-twitter-data-with-sample-connector.md)

## <a name="step-1-create-an-app-in-azure-active-directory"></a>1단계: 앱에서 앱 Azure Active Directory

1. 으로 이동한 후 전역 관리자 계정의 자격 증명을 <https://portal.azure.com> 사용하여 로그인합니다.

   ![Azure에 로그인합니다.](../media/TCimage01.png)

2. 왼쪽 탐색 창에서 **Azure Active Directory** 를 클릭합니다.

   ![다음으로 Azure Active Directory.](../media/TCimage02.png)

3. 왼쪽 탐색 창에서 앱 등록(미리 **보기)을 클릭한** 다음 새 등록 **을 클릭합니다.**

   ![새 앱 등록을 생성합니다.](../media/TCimage03.png)

4. 응용 프로그램을 등록합니다. URI **리디렉션(선택 사항)의** 응용 프로그램 유형 드롭다운 목록에서 웹을 선택한 다음  `https://portal.azure.com` URI의 상자에 입력합니다.

   ![리디렉션 https://portal.azure.com URI를 입력합니다.](../media/TCimage04.png)

5. 응용 **프로그램(클라이언트) ID** 및 **디렉터리(테넌트) ID를** 복사하여 텍스트 파일 또는 기타 안전한 위치에 저장합니다. 이러한 ID는 이후 단계에서 사용할 수 있습니다.

    ![응용 프로그램 ID 및 디렉터리 ID를 복사하여 저장합니다.](../media/TCimage05.png)

6. 새 **앱에 &** 대한 인증서 관리로 이동하고 **클라이언트 비밀에서** 새 클라이언트 비밀 **을 클릭합니다.**

   ![새 클라이언트 비밀을 생성합니다.](../media/TCimage06.png)

7. 새 비밀을 만드시다. 설명 상자에 비밀을 입력한 다음 만료 기간을 선택합니다.

   ![비밀을 입력하고 만료 기간을 선택 합니다.](../media/TCimage08.png)

8. 비밀 값을 복사하여 텍스트 파일이나 다른 저장 위치에 저장합니다. 이 AAD 단계에서 사용하는 응용 프로그램 비밀입니다.

   ![비밀을 복사하여 저장합니다.](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>2단계: Azure 계정으로 GitHub 커넥터 웹 서비스 배포

1. 이 [사이트로 GitHub Azure에](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) **배포를 클릭합니다.**

    ![Azure 홈 페이지로 이동합니다.](../media/FBCimage11.png)

2. Azure에 **배포를 클릭하면** 사용자 지정 템플릿 페이지가 있는 Azure Portal로 리디렉션됩니다. 기본 사항 **및** **설정** 입력한 다음 구매를 **클릭합니다.**

   ![리소스 만들기를 클릭하고 저장소 계정을 입력합니다.](../media/FBCimage12.png)

    - **구독:** Twitter 커넥터 웹 서비스를 배포할 Azure 구독을 선택합니다.

    - **리소스 그룹:** 새 리소스 그룹을 선택하거나 만들 수 있습니다. 리소스 그룹은 Azure 솔루션에 대한 관련 리소스를 보유하는 컨테이너입니다.

    - **위치:** 위치를 선택하십시오.

    - **웹앱 이름:** 커넥터 웹앱에 고유한 이름을 제공합니다. Th 이름은 3-18자 사이입니다. 이 이름은 Azure 앱 서비스 URL을 만드는 데 사용됩니다. 예를 들어 **twitterconnector의** 웹 앱 이름을 제공하는 경우 Azure 앱 서비스 URL은 에 **twitterconnector.azurewebsites.net.**

    - **tenantId:** 1단계에서 Microsoft 365 Azure Active Directory에서 Facebook 커넥터 앱을 만들고 복사한 조직의 테넌트 ID입니다.

   - **APISecretKey:** 모든 값을 비밀로 입력할 수 있습니다. 5단계에서 커넥터 웹앱에 액세스하는 데 사용됩니다.

3. 배포가 성공하면 페이지는 다음 스크린샷과 유사하게 표시됩니다.

    ![계정 Storage 클릭한 다음 계정 Storage 클릭합니다.](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a>3단계: Twitter 앱 만들기

1. 로 이동하여 조직의 개발자 계정에 대한 자격 증명을 사용하여 로그인한 다음 https://developer.twitter.com 앱을 **클릭합니다.**

   ![으로 https://developer.twitter.com 이동하여 로그인합니다.](../media/TCimage25-5.png)
2. 앱 **만들기를 클릭합니다.**

   ![앱 페이지로 이동하여 앱을 만드십시오.](../media/TCimage26.png)

3. 앱 **세부 정보에서** 응용 프로그램에 대한 정보를 추가합니다.

   ![앱에 대한 정보를 입력합니다.](../media/TCimage27.png)

4. Twitter 개발자 대시보드에서 방금 만든 앱을 선택하고 세부 **정보를 클릭합니다.**

   ![앱 ID를 복사하여 저장합니다.](../media/TCimage28.png)

5. 키 및 **토큰** 탭의 소비자 API 키 아래에서 **API** 키와 API 비밀 키를 모두 복사하여 텍스트 파일 또는 다른 저장소 위치에 저장합니다. 그런 다음 **만들기를** 클릭하여 액세스 토큰 및 액세스 토큰 비밀을 생성하고 이를 텍스트 파일 또는 다른 저장소 위치에 복사합니다.

   ![API 비밀 키를 복사하여 저장합니다.](../media/TCimage29.png)

   그런 다음 **만들기를** 클릭하여 액세스 토큰 및 액세스 토큰 비밀을 생성하고 이를 텍스트 파일 또는 다른 저장소 위치에 복사합니다.

6. 사용 권한 **탭을** 클릭하고 다음 스크린샷과 같이 사용 권한을 구성합니다.

   ![사용 권한을 구성합니다.](../media/TCimage30.png)

7. 사용 권한 설정을 저장한  후 앱 세부 정보 탭을 클릭한 다음 편집을 > **클릭합니다.**

   ![앱 세부 정보를 편집합니다.](../media/TCimage31.png)

8. 다음 작업을 수행합니다.

   - 커넥터 앱이 Twitter에 로그인할 수 있도록 허용하려면 확인란을 선택합니다.

   - **\<connectorserviceuri> /Views/TwitterOAuth** 형식을 사용하여 OAuth 리디렉션 Uri를 추가합니다. 여기서 *connectorserviceuri* 값은 조직의 Azure 앱 서비스 URL입니다(예: https://twitterconnector.azurewebsites.net/Views/TwitterOAuth ).

    ![커넥터 앱이 Twitter에 로그인하고 OAuth 리디렉션 Uri를 추가할 수 있도록 허용합니다.](../media/TCimage32.png)

이제 Twitter 개발자 앱을 사용할 준비가 완료되었습니다.

## <a name="step-4-configure-the-connector-web-app"></a>4단계: 커넥터 웹앱 구성

1. \<AzureAppResourceName>.https:// .azurewebsites.net(여기서 **AzureAppResourceName은** 4단계에서 명명한 Azure 앱 리소스의 이름)로 이동하십시오. 예를 들어 이름이 **twitterconnector이면** 로 https://twitterconnector.azurewebsites.net 이동하세요. 앱의 홈 페이지는 다음 스크린샷과 같습니다.

   ![Azure 앱 리소스 페이지로 이동합니다.](../media/FBCimage41.png)

2. **구성을** 클릭하여 로그인 페이지를 표시합니다.

   ![로그인 페이지를 표시하려면 구성을 클릭합니다.](../media/FBCimage42.png)

3. 테넌트 ID 상자에 테넌트 ID(2단계에서 획득한)를 입력하거나 붙여넣습니다. 암호 상자에 APISecretKey(2단계에서 획득)를 입력하거나 붙여넣은 다음 구성 설정 설정 클릭하여 구성 **세부 정보** 페이지를 표시합니다.

   ![테넌트 ID 및 API 비밀 키를 사용하여 로그인합니다.](../media/TCimage35.png)

4. 다음 구성 설정을 입력합니다.

   - **Twitter Api 키:** 3단계에서 만든 Twitter 응용 프로그램의 API 키입니다.

   - **Twitter Api 비밀 키:** 3단계에서 만든 Twitter 응용 프로그램의 API 비밀 키입니다.

   - **Twitter 액세스 토큰:** 3단계에서 만든 액세스 토큰입니다.

   - **Twitter 액세스 토큰 비밀:** 3단계에서 만든 액세스 토큰 비밀입니다.

   - **AAD 응용 프로그램 ID:** 1단계에서 Azure Active Directory 앱의 응용 프로그램 ID

   - **AAD 응용 프로그램 비밀:** 1단계에서 만든 APISecretKey 비밀의 값입니다.

5. **저장을** 클릭하여 커넥터 설정을 저장합니다.

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>5단계: 계정에서 Twitter 커넥터 Microsoft 365 규정 준수 센터

1. 웹 페이지로 Microsoft 365 규정 준수 센터 <a href="https://go.microsoft.com/fwlink/p/?linkid=2173865" target="_blank"> /a의 **데이터** 커넥터<선택합니다.

2. Twitter **아래의 데이터 커넥터** **페이지에서** 보기를 **클릭합니다.**

3. Twitter **페이지에서** 커넥터 **추가를 클릭합니다.**

4. 서비스 **약관 페이지에서** 동의를 **클릭합니다.**

5. 커넥터 **앱에 대한** 자격 증명 추가 페이지에서 다음 정보를 입력하고 연결 유효성 **검사를 클릭합니다.**

   ![커넥터 앱 자격 증명을 입력합니다.](../media/TCimage38.png)

    - 이름 **상자에** Twitter 도움말 핸들과 같은 **커넥터의 이름을 입력합니다.**

    - 커넥터 **URL 상자에** Azure 앱 서비스 URL을 입력하거나 붙여넣습니다. 예를 들면 `https://twitterconnector.azurewebsites.net` 입니다.

    - 암호 **상자에** 2단계에서 만든 APISecretKey 값을 입력하거나 붙여넣습니다.

    - Azure **앱 ID** 상자에 1단계에서 획득한 Azure 응용 프로그램 앱 ID(클라이언트 ID라고도함)의 값을 입력하거나 붙여넣습니다. 

6. 연결의 유효성이 검사된 후 다음 을 **클릭합니다.**

7. 데이터 **가져오기 Microsoft 365** 승인 페이지에서 APISecretKey를 다시 입력하거나 붙여넣은 다음 웹앱 **로그인을 클릭합니다.**

8. Twitter로 **로그인을 클릭합니다.**

9. Twitter 로그인 페이지에서 조직의 Twitter 계정에 대한 자격 증명을 사용하여 로그인합니다.

   ![Twitter 계정에 로그인합니다.](../media/TCimage42.png)

   로그인하면 Twitter 페이지에 "Twitter Connector Job Successfully set up"이 표시됩니다.

10. **계속을** 클릭하여 Twitter 커넥터 설정을 완료합니다.

11. 필터 **설정 페이지에서** 필터를 적용하여 특정 연령의 항목을 처음에 가져올 수 있습니다. 연령을 선택하고 다음 을 **클릭합니다.**

12. 저장소 **위치 선택 페이지에서** Twitter 항목을 가져올 Microsoft 365 사서함의 전자 메일 주소를 입력하고 다음 을 **클릭합니다.**

13. **다음을** 클릭하여 커넥터 설정을 검토한 다음 마친을 클릭하여 커넥터 설정을 완료합니다. 

14. 준수 센터에서 데이터 커넥터  페이지로 이동한 다음  커넥터 탭을 클릭하여 가져오기 프로세스의 진행률을 봐야 합니다.
