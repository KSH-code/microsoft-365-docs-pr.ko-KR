---
title: Facebook Business pages 데이터를 보관 하기 위한 커넥터 배포
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
description: 관리자는 Facebook Business 페이지를 가져오고 보관 하기 위한 기본 커넥터를 Microsoft 365에 설정할 수 있습니다. 이 데이터를 Microsoft 365로 가져온 후 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용 하 여 조직의 Facebook 데이터를 관리할 수 있습니다.
ms.openlocfilehash: 9ef7a2f3a24201ff4a32839671df7430a492bb44
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943041"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a>Facebook Business pages 데이터를 보관 하기 위한 커넥터 배포

이 문서에서는 Office 365 가져오기 서비스를 사용 하 여 Facebook Business 페이지의 데이터를 Microsoft 365로 가져오는 커넥터를 배포 하는 단계별 프로세스를 소개 합니다. 이 프로세스에 대 한 간략 한 개요와 Facebook 커넥터를 배포 하는 데 필요한 필수 구성 요소 목록은 [facebook 데이터를 보관할 커넥터 설정을](archive-facebook-data-with-sample-connector.md)참조 하십시오. 

## <a name="step-1-create-an-app-in-azure-active-directory"></a>1 단계: Azure Active Directory에 앱 만들기

1. 로 이동 <https://portal.azure.com> 하 고 전역 관리자 계정의 자격 증명을 사용 하 여 로그인 합니다.

    ![AAD에서 앱 만들기](../media/FBCimage1.png)

2. 왼쪽 탐색 창에서 **Azure Active Directory**를 클릭 합니다.

    ![Azure Active Directory를 클릭 합니다.](../media/FBCimage2.png)

3. 왼쪽 탐색 창에서 **앱 등록 (미리 보기)** 을 클릭 하 고 **새 등록**을 클릭 합니다.

    ![* * 앱 등록 (미리 보기) * *를 클릭 하 고 * * 새 등록을 클릭 합니다.](../media/FBCimage3.png)

4. 응용 프로그램을 등록 합니다. 리디렉션 URI의 응용 프로그램 형식 드롭다운 목록에서 웹을 선택한 다음 URI에 <https://portal.azure.com> 대 한 상자에 입력 합니다.

   ![응용 프로그램 등록](../media/FBCimage4.png)

5. **응용 프로그램 (클라이언트) id** 및 **디렉터리 (테 넌 트) id** 를 복사한 다음 텍스트 파일 또는 기타 안전한 위치에 저장 합니다. 이후 단계에서 이러한 Id를 사용 합니다.

   ![응용 프로그램 ID 및 디렉터리 ID를 복사 하 고 저장 합니다.](../media/FBCimage5.png)

6. **새 앱에 대 한 인증서 & 비밀으로 이동 합니다.**

   ![새 앱에 대 한 인증서 & 비밀으로 이동 합니다.](../media/FBCimage6.png)

7. **새 클라이언트 암호** 를 클릭 합니다.

   ![새 클라이언트 암호를 클릭 합니다.](../media/FBCimage7.png)

8. 새 암호를 만듭니다. 설명 상자에 암호를 입력 하 고 만료 기간을 선택 합니다. 

    ![암호를 입력 하 고 만료 기간을 선택 합니다.](../media/FBCimage8.png)

9. 비밀 값을 복사 하 여 텍스트 파일 또는 기타 저장 위치에 저장 합니다. 이는 이후 단계에서 사용 하는 AAD 응용 프로그램 비밀입니다.

   ![비밀 값을 복사 하 고 저장 합니다.](../media/FBCimage9.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>2 단계: GitHub에서 Azure 계정으로 커넥터 웹 서비스 배포

1. [이 GitHub 사이트로](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) 이동한 후 **Azure에 배포를**클릭 합니다.

    ![Azure에 배포 클릭](../media/FBCGithubApp.png)

2. **Azure에 배포**를 클릭 하면 사용자 지정 서식 파일 페이지를 사용 하 여 azure 포털로 리디렉션됩니다. **기본 사항** 및 **설정** 세부 정보를 입력 하 고 **구매**를 클릭 합니다.

    - **구독:** Facebook Business pages connector 웹 서비스를 배포 하려는 Azure 구독을 선택 합니다.
    
    - **리소스 그룹:** 새 리소스 그룹을 선택 하거나 만듭니다. 리소스 그룹은 Azure 솔루션에 대 한 관련 리소스를 포함 하는 컨테이너입니다.

    - **위치:** 위치를 선택 합니다.

    - **웹 응용 프로그램 이름:** 커넥터 웹 응용 프로그램의 고유한 이름을 지정 합니다. Th 이름의 길이는 3에서 18 자 사이 여야 합니다. 이 이름은 Azure app service URL을 만드는 데 사용 됩니다. 예를 들어 **fbconnector** 의 웹 앱 이름을 제공 하는 경우 Azure APP service URL은 **fbconnector.azurewebsites.net**가 됩니다.
    
    - **tenantId:** 1 단계에서 Azure Active Directory에 Facebook connector 앱을 만든 후 복사한 Microsoft 365 조직의 테 넌 트 ID입니다.
    
   - **APISecretKey:** 임의의 값을 비밀로 입력할 수 있습니다. 이는 5 단계에서 커넥터 웹 앱에 액세스 하는 데 사용 됩니다.
   
     ![리소스 만들기 및 저장소 계정 입력을 클릭 합니다.](../media/FBCimage12.png)

3. 배포가 성공적으로 완료 되 면 페이지는 다음 스크린샷과 유사 하 게 표시 됩니다.

     ![저장소를 클릭 한 다음 저장소 계정을 클릭 합니다.](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a>3 단계: Facebook 앱 등록

1. <https://developers.facebook.com>으로 이동 하 고 조직의 Facebook Business 페이지의 계정에 대 한 자격 증명을 사용 하 여 로그인 한 다음 **새 앱 추가**를 클릭 합니다.

   ![Facebook business에 대 한 새 앱 추가 페이지](../media/FBCimage25.png)

2. 새 앱 ID를 만듭니다.

   ![새 앱 ID 만들기](../media/FBCimage26.png)

3. 왼쪽 탐색 창에서 **제품 추가** 를 클릭 한 다음 **Facebook 로그인** 타일에서 **설정을** 클릭 합니다.

   ![제품 추가 클릭](../media/FBCimage27.png)

4. Facebook 로그온 페이지에서 **웹**을 클릭 합니다.

   ![Facebook 로그인 페이지에서 웹을 클릭 합니다.](../media/FBCimage28.png)

5. Azure 앱 서비스 URL을 추가 합니다. 예를 `https://fbconnector.azurewebsites.net`들어

   ![Azure 앱 서비스 URL 추가](../media/FBCimage29.png)

6. Facebook 로그인 설정의 퀵 스타트 섹션을 완료 합니다.

   ![퀵 스타트 섹션 완료](../media/FBCimage30.png)

7. **Facebook 로그인**아래의 왼쪽 탐색 창에서 **설정을**클릭 하 고 **유효한 OAuth 리디렉션 URI** 상자에 OAuth 리디렉션 URI를 추가 합니다. Connectorserviceuri의 값은 조직의 Azure app 서비스 URL 인 ** \<connectorserviceuri>/views/facebookoauth**형식을 사용 합니다. 예를 `https://fbconnector.azurewebsites.net`들면입니다.

   ![OAuth 리디렉션 URI를 유효한 OAuth 리디렉션 Uri 상자에 추가 합니다.](../media/FBCimage31.png)

8. 왼쪽 탐색 창에서 **제품 추가** 를 클릭 한 다음 **webhooks를 클릭 합니다.** **페이지** 풀 다운 메뉴에서 **페이지**를 클릭 합니다. 

   ![제품 추가를 클릭 한 다음 * * Webhooks를 클릭 합니다.](../media/FBCimage32.png)

9. Webhooks 콜백 URL을 추가 하 고 verify token을 추가 합니다. 콜백 URL의 형식은 ** <connectorserviceuri>/api/FbPageWebhook**형식을 사용 하며, 여기서 connectorserviceuri의 값은 조직의 Azure 앱 서비스 URL입니다. 예를 `https://fbconnector.azurewebsites.net`들어 

    Verify 토큰은 강력한 암호와 비슷해야 합니다. 텍스트 파일 또는 기타 저장소 위치에 verify 토큰을 복사 합니다.

        ![Add the verify token](../media/FBCimage33.png)

10. 테스트 하 고 피드의 끝점을 구독 합니다.

    ![테스트 및 끝점 구독](../media/FBCimage34.png)

11. 개인 정보 URL, 앱 아이콘 및 비즈니스 사용을 추가 합니다. 또한 앱 ID 및 앱 암호를 텍스트 파일 또는 기타 저장 위치에 복사 합니다.

    ![개인 정보 URL, 앱 아이콘 및 비즈니스 용도 추가](../media/FBCimage35.png)

12. 앱을 공용으로 설정 합니다.

    ![앱을 공용으로 설정](../media/FBCimage36.png)

13. 관리자 또는 테스터 역할에 사용자를 추가 합니다.

    ![관리자 또는 테스터 역할에 사용자 추가](../media/FBCimage37.png)

14. **페이지 공용 콘텐츠 액세스** 권한을 추가 합니다.

    ![dd 페이지 공용 콘텐츠 액세스 권한](../media/FBCimage38.png)

15. 페이지 관리 권한을 추가 합니다.

    ![페이지 관리 권한 추가](../media/FBCimage39.png)

16. Facebook에서 검토 한 응용 프로그램을 가져옵니다.

    ![Facebook에서 검토 한 응용 프로그램 가져오기](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a>4 단계: 커넥터 웹 응용 프로그램 구성

1. Https://\<AzureAppResourceName> (여기에서 AzureAppResourceName는 4 단계에서 명명 한 Azure 앱 리소스의 이름)으로 이동 합니다 (예: 이름이 **fbconnector**이면로 `https://fbconnector.azurewebsites.net`이동). 앱의 홈 페이지는 다음 스크린샷 처럼 표시 됩니다.

   ![커넥터 웹 앱으로 이동](../media/FBCimage41.png)

2. **구성을** 클릭 하 여 로그인 페이지를 표시 합니다.
 
   ![로그인 페이지를 표시 하려면 구성을 클릭 합니다.](../media/FBCimage42.png)

3. 테 넌 트 Id 상자에 2 단계에서 받은 테 넌 트 Id를 입력 하거나 붙여 넣습니다. 암호 상자에 2 단계에서 구한 APISecretKey를 입력 하거나 붙여 넣은 다음 **구성 설정 설정을** 클릭 하 여 구성 세부 정보 페이지를 표시 합니다.

    ![테 넌 트 Id 및 암호를 사용 하 여 로그인 하 고 구성 세부 정보 페이지로 이동](../media/FBCimage43.png)

4. 다음 구성 설정을 입력 합니다. 

   - **Facebook 응용 프로그램 ID:** 3 단계에서 구한 Facebook 응용 프로그램의 앱 ID입니다.
   
   - **Facebook 응용 프로그램 암호:** 3 단계에서 얻은 Facebook 응용 프로그램에 대 한 앱 비밀입니다.
   
   - **Facebook webhook 확인 토큰:** 3 단계에서 만든 verify 토큰입니다.
   
   - **AAD 응용 프로그램 ID:** 1 단계에서 만든 Azure Active Directory 앱의 응용 프로그램 ID입니다.
   
   - **AAD 응용 프로그램 암호:** 1 단계에서 만든 APISecretKey 암호에 대 한 값입니다.

5. **저장** 을 클릭 하 여 커넥터 설정을 저장 합니다.

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a>5 단계: Microsoft 365 준수 센터에서 Facebook 커넥터 설정

1. 로 이동한 [https://compliance.microsoft.com](https://compliance.microsoft.com) 후 왼쪽 탐색 창에서 **데이터 커넥터** 를 클릭 합니다.

2. **데이터 커넥터 (미리 보기)** 페이지의 **Facebook Business 페이지**에서 **보기**를 클릭 합니다.

3. **Facebook business pages** 페이지에서 **커넥터 추가**를 클릭 합니다.

4. **서비스 약관** 페이지에서 **수락**을 클릭 합니다.

5.  **커넥터 응용 프로그램에 대 한 자격 증명 추가** 페이지에서 다음 정보를 입력 한 다음 **연결 유효성 검사**를 클릭 합니다.

    ![커넥터 앱 자격 증명 입력](../media/TCimage38.png)

    - **이름** 상자에 **Facebook 뉴스 페이지**와 같은 커넥터의 이름을 입력 합니다.
    
    - **연결 URL** 상자에 Azure 앱 서비스 URL을 입력 하거나 붙여넣습니다. 예를 `https://fbconnector.azurewebsites.net`들어
    
    - **암호** 상자에 2 단계에서 추가한 APISecretKey의 값을 입력 하거나 붙여넣습니다.
    
    - **Azure 앱 id** 상자에 1 단계에서 만든 AAD 응용 프로그램 id로 호출 되는 응용 프로그램 (클라이언트) id의 값을 입력 하거나 붙여넣습니다.
 
6. 연결이 성공적으로 확인 되 면 **다음**을 클릭 합니다.

7. **Microsoft 365에서 데이터를 가져올 수 있는 권한을 부여** 합니다 페이지에서 APISecretKey를 다시 입력 하거나 붙여 넣은 다음 **로그인 웹 앱**을 클릭 합니다.

8. **Facebook connector 앱 구성** 페이지에서 **facebook을 사용** 하 여 로그인을 클릭 하 고 조직의 facebook 비즈니스 페이지에 대 한 계정의 자격 증명을 사용 하 여 로그온 합니다. 로그인 한 Facebook 계정에 조직의 Facebook Business 페이지에 대 한 관리자 역할이 할당 되었는지 확인 합니다.

   ![Facebook을 사용 하 여 로그인](../media/FBCimage50.png)

9. 로그인 한 Facebook 계정으로 관리 되는 비즈니스 페이지 목록이 표시 됩니다. 보관할 페이지를 선택 하 고 **다음**을 클릭 합니다.

    ![보관 하려는 조직 비즈니스 페이지를 선택 합니다.](../media/FBCimage52.png)

10. **계속** 을 클릭 하 여 커넥터 서비스 앱의 설정을 종료 합니다.

11. **필터 설정** 페이지에서 특정 기간에 해당 하는 항목을 처음 가져올 때 필터를 적용할 수 있습니다. 보존 기간을 선택 하 고 **다음**을 클릭 합니다.

12. **저장소 위치 선택** 페이지에서 Facebook 항목을 가져올 Microsoft 365 사서함의 전자 메일 주소를 입력 하 고 **다음**을 클릭 합니다.

13. **관리자 동의 제공**에서 **동의 제공** 을 클릭 한 다음 단계를 따릅니다. 조직의 데이터에 액세스 하려면 Office 365 가져오기 서비스에 대 한 동의를 제공 하는 전역 관리자 여야 합니다.

14. **다음** 을 클릭 하 여 커넥터 설정을 검토 한 다음 **마침을** 클릭 하 여 커넥터 설치를 완료 합니다.

15. 준수 센터에서 **데이터 커넥터** 페이지로 이동한 다음 **커넥터** 탭을 클릭 하 여 가져오기 프로세스의 진행 상태를 확인 합니다.
