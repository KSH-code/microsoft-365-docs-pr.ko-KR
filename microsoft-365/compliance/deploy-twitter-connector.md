---
title: Twitter 데이터를 보관 하기 위한 커넥터 배포
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
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 관리자는 네이티브 커넥터를 설정 하 여 Twitter 데이터를 가져오고 Microsoft 365로 보관할 수 있습니다. 이 데이터를 Microsoft 365로 가져온 후 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용 하 여 조직의 Twitter 데이터에 대 한 관리를 관리할 수 있습니다.
ms.openlocfilehash: 1143239635aed64847c12a3d8c61c430a677e037
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636126"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a>Twitter 데이터를 보관 하기 위한 커넥터 배포

이 문서에는 Office 365 가져오기 서비스를 사용 하 여 조직의 Twitter 계정에서 Microsoft 365로 데이터를 가져오는 커넥터를 배포 하는 단계별 프로세스가 포함 되어 있습니다. 이 프로세스에 대 한 간략 한 개요와 Twitter 커넥터를 배포 하는 데 필요한 필수 구성 요소 목록은 [twitter 데이터를 보관할 커넥터 설정을 ](archive-twitter-data-with-sample-connector.md)참조 하십시오. 

## <a name="step-1-create-an-app-in-azure-active-directory"></a>1 단계: Azure Active Directory에 앱 만들기

1. 로 이동 <https://portal.azure.com> 하 고 전역 관리자 계정의 자격 증명을 사용 하 여 로그인 합니다.

   ![Azure에 로그인 합니다.](../media/TCimage01.png)

2. 왼쪽 탐색 창에서 **Azure Active Directory**를 클릭 합니다.

   ![Azure Active Directory로 이동](../media/TCimage02.png)

3. 왼쪽 탐색 창에서 **앱 등록 (미리 보기)** 을 클릭 하 고 **새 등록**을 클릭 합니다.

   ![새 앱 등록 만들기](../media/TCimage03.png)

4. 응용 프로그램을 등록 합니다. **Uri 리디렉션 (선택 사항)** 아래의 응용 프로그램 형식 드롭다운 목록에서 **웹** 을 선택한 다음 URI `https://portal.azure.com` 에 대 한 상자에 입력 합니다.

   ![리디렉션 https://portal.azure.com URI의 유형입니다. ](../media/TCimage04.png)

5. **응용 프로그램 (클라이언트) id** 및 **디렉터리 (테 넌 트) id** 를 복사한 다음 텍스트 파일 또는 기타 안전한 위치에 저장 합니다. 이후 단계에서 이러한 Id를 사용 합니다.

    ![응용 프로그램 Id 및 디렉터리 Id 복사 및 저장](../media/TCimage05.png)

6. **새 앱에 대 한 인증서 & 비밀** 으로 이동 하 고 **클라이언트 암호** 에서 **새 클라이언트 암호**를 클릭 합니다.

   ![새 클라이언트 암호 만들기](../media/TCimage06.png)

7. 새 암호를 만듭니다. 설명 상자에 암호를 입력 하 고 만료 기간을 선택 합니다. 

   ![암호 입력 및 만료 기간 선택](../media/TCimage08.png)

8. 비밀 값을 복사 하 여 텍스트 파일 또는 기타 저장 위치에 저장 합니다. 이는 이후 단계에서 사용 하는 AAD 응용 프로그램 비밀입니다.

   ![암호 복사 및 저장](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>2 단계: GitHub에서 Azure 계정으로 커넥터 웹 서비스 배포

1. [이 GitHub 사이트로](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) 이동한 후 **Azure에 배포를**클릭 합니다.

    ![Azure 홈 페이지로 이동](../media/FBCimage11.png)

2. **Azure에 배포**를 클릭 하면 사용자 지정 서식 파일 페이지를 사용 하 여 azure 포털로 리디렉션됩니다. **기본 사항** 및 **설정** 세부 정보를 입력 하 고 **구매**를 클릭 합니다.

   ![리소스 만들기 및 저장소 계정 입력을 클릭 합니다.](../media/FBCimage12.png)

    - **구독:** Twitter 커넥터 웹 서비스를 배포 하려는 Azure 구독을 선택 합니다.
    
    - **리소스 그룹:** 새 리소스 그룹을 선택 하거나 만듭니다. 리소스 그룹은 Azure 솔루션에 대 한 관련 리소스를 포함 하는 컨테이너입니다.

    - **위치:** 위치를 선택 합니다.

    - **웹 응용 프로그램 이름:** 커넥터 웹 응용 프로그램의 고유한 이름을 지정 합니다. Th 이름의 길이는 3에서 18 자 사이 여야 합니다. 이 이름은 Azure app service URL을 만드는 데 사용 됩니다. 예를 들어, 웹 앱 이름을 **twitterconnector** 로 제공 하는 경우 Azure APP service URL이 **twitterconnector.azurewebsites.net**됩니다.
    
    - **tenantId:** 1 단계에서 Azure Active Directory에 Facebook connector 앱을 만든 후 복사한 Microsoft 365 조직의 테 넌 트 ID입니다.
    
   - **APISecretKey:** 임의의 값을 비밀로 입력할 수 있습니다. 이는 5 단계에서 커넥터 웹 앱에 액세스 하는 데 사용 됩니다.

3. 배포가 성공적으로 완료 되 면 페이지는 다음 스크린샷과 유사 하 게 표시 됩니다.

    ![저장소를 클릭 한 다음 저장소 계정을 클릭 합니다.](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a>3 단계: Twitter 응용 프로그램 만들기

1. https://developer.twitter.com으로 이동 하 고 조직의 개발자 계정에 대 한 자격 증명을 사용 하 여 로그인 한 다음 **앱**을 클릭 합니다.

   ![으로 이동 https://developer.twitter.com 하 여 로그인 합니다.](../media/TCimage25-5.png)
2. **앱 만들기**를 클릭 합니다.
   
   ![앱을 만들려면 앱 페이지로 이동](../media/TCimage26.png)

3. **앱 세부 정보**에서 응용 프로그램에 대 한 정보를 추가 합니다.

   ![앱에 대 한 정보 입력](../media/TCimage27.png)

4. Twitter 개발자 대시보드에서 방금 만든 앱을 선택 하 고 표시 된 앱 ID를 복사한 다음 텍스트 파일 또는 기타 저장 위치에 저장 합니다. 그런 다음 **세부 정보**를 클릭 합니다.
   
   ![앱 Id 복사 및 저장](../media/TCimage28.png)

5. **키 및 토큰** 탭의 **Consumer api 키** 아래에서 API 비밀 키를 복사 하 여 텍스트 파일 또는 기타 저장 위치에 저장 합니다. 그런 다음 **만들기** 를 클릭 하 여 액세스 토큰과 액세스 토큰 비밀을 생성 한 다음 텍스트 파일 또는 기타 저장소 위치로 복사 합니다.
   
   ![API 비밀 키에 복사 및 저장](../media/TCimage29.png)

   그런 다음 **만들기** 를 클릭 하 여 액세스 토큰과 액세스 토큰 비밀을 생성 한 다음 텍스트 파일 또는 기타 저장소 위치로 복사 합니다.

6. **사용 권한** 탭을 클릭 하 고 다음 스크린샷에 표시 된 대로 사용 권한을 구성 합니다.

   ![사용 권한 구성](../media/TCimage30.png)

7. 권한 설정을 저장 한 후에는 **앱 세부 정보** 탭을 클릭 한 다음 **세부 정보 편집 >** 편집을 클릭 합니다.

   ![앱 세부 정보 편집](../media/TCimage31.png)

8. 다음 작업을 수행 합니다.

   - 커넥터 앱이 Twitter에 로그인 하도록 허용 하는 확인란을 선택 합니다.
   
   - *Connectorserviceuri* 의 값이 조직의 Azure app 서비스 URL 인 ** \<connectorserviceuri>/views/twitteroauth**형식을 사용 하 여 OAuth 리디렉션 Uri를 추가 합니다. 예를 https://twitterconnector.azurewebsites.net/Views/TwitterOAuth들면입니다.

    ![커넥터 앱이 Twitter에 로그인 하 고 OAuth 리디렉션 Uri를 추가할 수 있도록 허용](../media/TCimage32.png)

이제 Twitter 개발자 앱을 사용할 준비가 되었습니다.

## <a name="step-4-configure-the-connector-web-app"></a>4 단계: 커넥터 웹 응용 프로그램 구성 

1. Https://\<AzureAppResourceName> azurewebsites.net (여기서 **AzureAppResourceName** 은 4 단계에서 명명 한 Azure 앱 리소스의 이름)으로 이동 합니다. 예를 들어 이름이 **twitterconnector**인 경우로 https://twitterconnector.azurewebsites.net이동 합니다. 이 앱의 홈 페이지는 다음과 같습니다.

   ![Azure 앱 리소스 페이지로 이동](../media/FBCimage41.png)

2. **구성을** 클릭 하 여 로그인 페이지를 표시 합니다.

   ![로그인 페이지를 표시 하려면 구성을 클릭 합니다.](../media/FBCimage42.png)

3. 테 넌 트 Id 상자에 2 단계에서 받은 테 넌 트 Id를 입력 하거나 붙여 넣습니다. 암호 상자에 2 단계에서 구한 APISecretKey를 입력 하거나 붙여 넣은 다음 **구성 설정 설정을** 클릭 하 여 구성 세부 정보 페이지를 표시 합니다.

   ![테 넌 트 Id 및 API 비밀 키를 사용 하 여 로그인](../media/TCimage35.png)

4. 다음 구성 설정을 입력 합니다. 

   - **Twitter Api 키:** 3 단계에서 만든 Twitter 응용 프로그램의 앱 ID입니다.
   
   - **Twitter Api 비밀 키:** 3 단계에서 만든 Twitter 응용 프로그램에 대 한 API 비밀 키입니다.
   
   - **Twitter 액세스 토큰:** 3 단계에서 만든 액세스 토큰입니다.
   
   - **Twitter 액세스 토큰 암호:** 3 단계에서 만든 액세스 토큰 비밀입니다.
   
   - **AAD 응용 프로그램 ID:** 1 단계에서 만든 Azure Active Directory 앱의 응용 프로그램 ID
   
   - **AAD 응용 프로그램 암호:** 1 단계에서 만든 APISecretKey 암호에 대 한 값입니다.

5. **저장** 을 클릭 하 여 커넥터 설정을 저장 합니다.

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>5 단계: Microsoft 365 준수 센터에서 Twitter 커넥터 설정

1. 로 이동한 [https://compliance.microsoft.com](https://compliance.microsoft.com) 후 왼쪽 탐색 창에서 **데이터 커넥터** 를 클릭 합니다.

2. **데이터 커넥터 (미리 보기)** 페이지의 **Twitter**아래에서 **보기**를 클릭 합니다.

3. **Twitter** 페이지에서 **커넥터 추가**를 클릭 합니다.

4. **서비스 약관** 페이지에서 **수락**을 클릭 합니다.

5. **커넥터 응용 프로그램에 대 한 자격 증명 추가** 페이지에서 다음 정보를 입력 한 다음 **연결 유효성 검사**를 클릭 합니다.

   ![커넥터 앱 자격 증명 입력](../media/TCimage38.png)

    - **이름** 상자에 **Twitter 도움말 핸들과**같은 커넥터의 이름을 입력 합니다.
    
    - **커넥터 URL** 상자에 Azure 앱 서비스 URL을 입력 하거나 붙여넣습니다. 예를 `https://twitterconnector.azurewebsites.net`들어
    
    - **암호** 상자에 2 단계에서 만든 APISecretKey의 값을 입력 하거나 붙여넣습니다.
    
    - **Azure 앱 id** 상자에 1 단계에서 구한 Azure 응용 프로그램 id ( *클라이언트 ID*라고도 함)의 값을 입력 하거나 붙여넣습니다.

6. 연결이 성공적으로 확인 되 면 **다음**을 클릭 합니다.

7. **Microsoft 365에서 데이터를 가져올 수 있는 권한을 부여** 합니다 페이지에서 APISecretKey를 다시 입력 하거나 붙여 넣은 다음 **로그인 웹 앱**을 클릭 합니다.

8. **Twitter를 사용 하 여 로그인을**클릭 합니다.

9. Twitter 로그인 페이지에서 조직의 Twitter 계정에 대 한 자격 증명을 사용 하 여 로그인 합니다.

   ![Twitter 계정에 로그인 합니다.](../media/TCimage42.png)

   로그인 하면 Twitter 페이지에 "Twitter 커넥터 작업을 설정 했습니다." 라는 메시지가 표시 됩니다.

10. **계속** 을 클릭 하 여 Twitter 커넥터 설정을 완료 합니다.

11. **필터 설정** 페이지에서 특정 기간에 해당 하는 항목을 처음 가져올 때 필터를 적용할 수 있습니다. 보존 기간을 선택 하 고 **다음**을 클릭 합니다.

12. **저장 위치 선택** 페이지에서 Twitter 항목을 가져올 Microsoft 365 사서함의 전자 메일 주소를 입력 하 고 **다음**을 클릭 합니다.

13. **관리자 동의 제공**에서 **동의 제공** 을 클릭 한 다음 단계를 따릅니다. 조직의 데이터에 액세스 하려면 Office 365 가져오기 서비스에 대 한 동의를 제공 하는 전역 관리자 여야 합니다.

14. **다음** 을 클릭 하 여 커넥터 설정을 검토 한 다음 **마침을** 클릭 하 여 커넥터 설치를 완료 합니다.

15. 준수 센터에서 **데이터 커넥터** 페이지로 이동한 다음 **커넥터** 탭을 클릭 하 여 가져오기 프로세스의 진행 상태를 확인 합니다.
