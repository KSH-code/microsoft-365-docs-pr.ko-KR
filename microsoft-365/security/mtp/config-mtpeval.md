---
title: 평가판 랩 또는 파일럿 환경에 대해 Microsoft Threat Protection 핵심 요소로 구성
description: '평가판 랩 또는 파일럿 환경에 대해 Microsoft Threat Protection 핵심 요소로 (예: Office 365 ATP, Azure ATP, Microsoft Cloud App Security, Microsoft Defender ATP)를 구성 합니다.'
keywords: microsoft threat Protection 평가판, Microsoft Threat protection 평가판 구성, microsoft threat protection 파일럿 프로젝트 구성, microsoft threat protection 핵심 요소로, Microsoft 위협 보호 핵심 요소로를 구성 합니다.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 43facffde9c31dc33445de87997d2b91cba6a9f1
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277562"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-or-pilot-environment"></a>평가판 랩 또는 파일럿 환경에 대해 Microsoft Threat Protection 핵심 요소로 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 위협 방지


Microsoft Threat Protection 평가판 랩 또는 파일럿 환경을 만들고 배포 하는 과정은 다음 세 단계로 진행 됩니다.

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Microsoft Threat Protection 평가판 랩 또는 파일럿 환경 준비" />
      <br/>1 단계: 준비 </a><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab or pilot environment" title="Microsoft Threat Protection 평가판 랩 또는 파일럿 환경 설정" />
      <br/>2 단계: 설치 </a><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Microsoft Threat Protection 평가판 랩 또는 파일럿 환경 및 온보드 끝점에 대해 각 Microsoft Threat Protection를 구성 합니다." />
      <br/>3 단계: 온보드 & 구성 </a><br>
</td>
  </tr>
</table>

현재 구성 단계입니다.


준비는 성공적인 배포의 핵심입니다. 이 문서에서는 Microsoft Defender ATP 배포를 준비할 때 고려해 야 할 사항을 안내 합니다.


## <a name="microsoft-threat-protection-pillars"></a>Microsoft Threat Protection 핵심 요소로
Microsoft Threat Protection은 핵심 요소로 4 개로 구성 됩니다. 한 번에 네트워크 조직의 보안에 대 한 가치를 제공할 수 있지만 Microsoft Threat Protection 핵심 요소로 4 개를 사용 하도록 설정 하면 조직에 가장 많은 값이 제공 됩니다.

![사용자, Azure Advanced threat protection, 끝점에 대 한 위협 보호 솔루션, Microsoft Defender Advanced Threat Protection, 클라우드 앱, Microsoft Cloud App Security 및 data의 경우 Office 365 Advanced Threat Protection of_Microsoft  ](../../media/mtp-eval-31.png)

이 섹션에서는 다음을 구성할 수 있도록 안내 합니다.
-   Office 365 Advanced Threat Protection
-   Azure Advanced Threat Protection 
-   Microsoft Cloud App Security
-   Microsoft Defender Advanced Threat Protection


## <a name="configure-office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection 구성

>[!NOTE]
>Office 365 Advanced Threat Protection을 이미 사용 하도록 설정한 경우에는이 단계를 건너뜁니다. 

이러한 설정 중 일부를 결정 하는 데 도움이 되는 *Office 365 Advanced Threat Protection 권장 구성 분석기 (ORCA)* 라는 PowerShell 모듈이 있습니다. ORCAReport에서 관리자 권한으로 실행 하는 경우, get-스팸 방지, 피싱 및 기타 메시지 바이러스 백신 설정을 평가 하는 데 도움이 됩니다. 이 모듈은에서 다운로드할 수 있습니다 https://www.powershellgallery.com/packages/ORCA/ . 

1. [Office 365 보안 & 준수 센터](https://protection.office.com/homepage)  >  **위협 관리**  >  **정책**으로 이동 합니다.

   ![이미지 of_Office 365 보안 & 준수 센터 위협 관리 정책 페이지](../../media/mtp-eval-32.png)
 
2. **ATP 피싱 방지**를 클릭 하 고 정책 이름과 설명을 **작성** 하 여 채웁니다 .를 선택 합니다. **다음**을 클릭합니다.

   ![이미지 of_Office 365 보안 & 준수 센터 정책 이름을 지정할 수 있는 피싱 방지 정책 페이지](../../media/mtp-eval-33.png)

   > [!NOTE]
   > 고급 ATP 피싱 방지 정책을 편집 합니다. **Advanced 피싱 임계값** 을 **2-적극적**으로 변경 합니다.

3. **조건 추가** 드롭다운 메뉴를 클릭 하 고 도메인을 받는 사람 도메인으로 선택 합니다. **다음**을 클릭합니다.

   ![이미지 of_Office 365 보안 & 준수 센터 피싱 방지 정책 페이지로, 해당 응용 프로그램에 조건을 추가할 수 있습니다.](../../media/mtp-eval-34.png)
 
4. 설정을 검토 합니다. **이 정책 만들기** 를 클릭 하 여 확인 합니다. 

   ![이미지 of_Office 365 보안 & 준수 센터 피싱 방지 정책 페이지에서 설정을 검토 하 고이 정책 만들기 단추를 클릭할 수 있습니다.](../../media/mtp-eval-35.png)
 
5. **Atp 안전한 첨부 파일** 을 선택 하 고 **SharePoint, OneDrive 및 Microsoft 팀에 게 atp 설정** 옵션을 선택 합니다.

   ![이미지 of_Office 365 보안 & 준수 센터 페이지에서 SharePoint, OneDrive 및 Microsoft 팀에 대 한 ATP를 설정할 수 있습니다.](../../media/mtp-eval-36.png)

6. + 아이콘을 클릭 하 여 새 안전한 첨부 파일 정책을 만들려면 도메인에 받는 사람 도메인으로 적용 합니다. **저장**을 클릭합니다.

   ![이미지 of_Office 365 보안 & 준수 센터 페이지 새 안전한 첨부 파일 정책 만들기](../../media/mtp-eval-37.png)
 
7. 다음으로 **ATP 안전한 링크** 정책을 선택 하 고 연필 아이콘을 클릭 하 여 기본 정책을 편집 합니다.

8. **사용자가 안전 링크를 클릭 하면 추적 안 함** 옵션이 선택 되어 있지 않은 동안 나머지 옵션이 선택 되어 있는지 확인 합니다. 자세한 내용은 [안전한 링크 설정을](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) 참조 하십시오. **저장**을 클릭합니다. 

   ![Image of_Office 365 보안 & 준수 센터 페이지-사용자가 안전한 클릭을 선택 하지 않은 경우 옵션을 추적 하지 않습니다.](../../media/mtp-eval-38.png)

9. 다음으로, **맬웨어 방지** 정책을 선택 하 고 기본값을 선택한 다음 연필 아이콘을 선택 합니다.

10. **설정을** 클릭 하 고 **예를 선택 하 고 기본 알림 텍스트를 사용** 하 여 **맬웨어 검색 응답**을 사용 하도록 설정 합니다. **일반 첨부 파일 형식 필터** 를 설정 합니다. **저장**을 클릭합니다.

    ![Image of_Office 365 보안 & 준수 센터 페이지에서 맬웨어 검색 응답이 기본 알림과 일반 첨부 파일 유형 필터를 사용 하 여 켜져 있음을 보여 줍니다.](../../media/mtp-eval-39.png)
  
11. [Office 365 Security & 준수 센터](https://protection.office.com/homepage)  >  **검색**  >  **감사 로그 검색** 및 감사 설정으로 이동 합니다.

    ![이미지 of_Office 365 보안 & 준수 센터 페이지에서 감사 로그 검색을 설정할 수 있습니다.](../../media/mtp-eval-40.png)

12. Office 365 ATP와 Microsoft Defender ATP를 통합 합니다. [Office 365 Security & 준수 센터](https://protection.office.com/homepage)  >  **Threat management**  >  **Explorer** 로 이동 하 여 화면의 오른쪽 위 모서리에 있는 **wdatp 설정을** 선택 합니다. Microsoft Defender ATP 연결 대화 상자에서 **WINDOWS ATP에 연결**을 설정 합니다.

    ![이미지 of_Office 365 보안 & 준수 센터 페이지에서 Windows Defender ATP 연결을 설정할 수 있습니다.](../../media/mtp-eval-41.png)

## <a name="configure-azure-advanced-threat-protection"></a>Azure Advanced Threat Protection 구성

>[!NOTE]
>Azure Advanced Threat Protection을 이미 사용 하도록 설정한 경우에는이 단계를 건너뜁니다.

1. [Microsoft 365 보안 센터로](https://security.microsoft.com/info) 이동 하 > **기타 리소스**  >  **Azure Advanced Threat Protection**를 선택 합니다.

   ![이미지 of_Microsoft 365 Azure Advanced Threat Protection을 여는 옵션이 있는 보안 센터 페이지](../../media/mtp-eval-42.png)

2. **만들기** 를 클릭 하 여 Azure Advanced Threat Protection 마법사를 시작 합니다. 

   ![만들기 단추를 클릭 해야 하는 고급 위협 방지 마법사 페이지를 of_Azure 합니다.](../../media/mtp-eval-43.png)

3. **Active Directory 포리스트에 연결 하려면 사용자 이름 및 암호 입력**을 선택 합니다.  

   ![이미지 of_Azure Advanced Threat Protection 시작 페이지](../../media/mtp-eval-44.png)

4. Active Directory 온-프레미스 자격 증명을 입력 합니다. 이 계정에는 Active Directory에 대 한 읽기 액세스 권한이 있는 모든 사용자 계정이 있을 수 있습니다.

   ![자격 증명을 입력 해야 하는 Advanced Threat Protection 디렉터리 서비스 페이지 이미지 of_Azure](../../media/mtp-eval-45.png)

5. 그런 다음 **센서 설정 다운로드** 및 도메인 컨트롤러로 파일 전송을 선택 합니다.

   ![센서 설정 다운로드를 선택할 수 있는 고급 위협 방지 페이지 of_Azure](../../media/mtp-eval-46.png)

6. Azure ATP 센서 설정을 실행 하 고 마법사 팔 로우를 시작 합니다.

   ![Azure ATP 센서 마법사를 따르려면 다음을 클릭 해야 하는 Advanced Threat Protection 페이지 of_Azure 합니다.](../../media/mtp-eval-47.png)
 
7. 센서 배포 유형에서 **다음** 을 클릭 합니다.

   ![다음 페이지로 이동 하려면 고급 위협 보호 페이지 of_Azure 다음을 클릭 해야 합니다.](../../media/mtp-eval-48.png)
 
8. 마법사에서 다음에 입력 해야 하므로 액세스 키를 복사 합니다.

   ![다음 Azure ATP 센서 설정 마법사 페이지에 입력 해야 하는 액세스 키를 복사 해야 하는 이미지 of_the 센서 페이지](../../media/mtp-eval-49.png)
 
9. Access 키를 마법사에 복사 하 고 **설치**를 클릭 합니다. 

   ![이미지 of_Azure Advanced Threat Protection Azure ATP 센서 마법사 페이지에서 액세스 키를 입력 한 다음 install (설치) 단추를 클릭 합니다.](../../media/mtp-eval-50.png)

10. 축 하 합니다, 도메인 컨트롤러에서 Azure Advanced Threat Protection을 구성 했습니다.

    ![이미지 of_Azure Advanced Threat Protection Azure ATP 센서 마법사 설치 완료 (finish) 단추를 클릭 해야 하는 경우](../../media/mtp-eval-51.png)
 
11. [Azure AZURE atp](https://go.microsoft.com/fwlink/?linkid=2040449) 설정 섹션에서 **Windows Defender atp**를 선택 하 고 설정/해제를 켭니다. **저장**을 클릭합니다. 

    ![이미지 of_the Azure Azure ATP 설정 페이지 Windows Defender ATP 전환 기능을 설정 해야 합니다.](../../media/mtp-eval-52.png)

>[!NOTE]
>Windows Defender ATP가 Microsoft Defender ATP와 다시 브랜드 되었습니다. 모든 포털에서 다시 브랜딩 변경을 수행 하는 것은 일관성을 위해 롤업 되 고 있습니다.


## <a name="configure-microsoft-cloud-app-security"></a>Microsoft Cloud App Security 구성

>[!NOTE]
>Microsoft Cloud App Security를 이미 사용 하도록 설정한 경우에는이 단계를 건너뜁니다. 

1. [Microsoft 365 보안 센터로](https://security.microsoft.com/info)이동  >  **More Resources**  >  **microsoft Cloud App security**.

   ![Image of_Microsoft 365 Microsoft Cloud App card를 볼 수 있고 열기 단추를 클릭 해야 하는 보안 센터 페이지](../../media/mtp-eval-53.png)

2. Azure ATP를 통합 하는 정보 프롬프트에서 **AZURE atp 데이터 통합 사용**을 선택 합니다.
  
   ![Azure ATP 데이터 통합 링크 사용을 선택 해야 하는 Azure ATP 통합을 위한 이미지 of_the 정보 프롬프트](../../media/mtp-eval-54.png)

   > [!NOTE]
   > 이 메시지가 표시 되지 않으면 Azure ATP 데이터 통합이 이미 사용 하도록 설정 되었음을 의미할 수 있습니다. 그러나 확실히 모르는 경우 IT 관리자에 게 문의 하 여 확인 합니다. 

3. **설정**으로 이동 하 여 **Azure ATP 통합** 을 설정/해제 한 다음 **저장**을 클릭 합니다. 

   ![이미지 of_the 설정 페이지 Azure ATP 통합 기능을 설정 하 고 저장을 클릭 합니다.](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > 새 Azure ATP 인스턴스의 경우이 통합 토글이 자동으로 설정 됩니다. 다음 단계를 진행 하기 전에 Azure ATP 통합을 사용 하도록 설정 했는지 확인 합니다.
 
4. 클라우드 검색 설정 아래에서 **Microsoft DEFENDER ATP 통합**을 선택한 다음 통합을 사용 하도록 설정 합니다. **저장**을 클릭합니다.

   ![Microsoft defender ATP 통합 아래의 unsanctioned 앱 차단 확인란이 선택 된 Microsoft Defender ATP 페이지 이미지를 of_the 합니다. 저장을 클릭 합니다.](../../media/mtp-eval-56.png)

5. 클라우드 검색 설정에서 **사용자 향상**을 선택한 다음 Azure Active Directory와의 통합을 사용 하도록 설정 합니다.

   ![Azure Active Directory 사용자 이름으로 검색 된 사용자 식별자가 선택 됨 확인란을 선택한 사용자 향상 섹션 이미지](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection 구성

>[!NOTE]
>Microsoft Defender Advanced Threat Protection을 이미 사용 하도록 설정한 경우에는이 단계를 건너뜁니다.

1. [Microsoft 365 보안 센터](https://security.microsoft.com/info)  >  **More Resources**  >  **microsoft Defender 보안 센터**리소스로 이동 합니다. **열기**를 클릭합니다. 

   ![Microsoft 365 보안 센터 페이지의 이미지 of_Microsoft Defender 보안 센터 옵션](../../media/mtp-eval-58.png)
 
2. Microsoft Defender Advanced Threat Protection 마법사를 따릅니다. **다음**을 클릭합니다. 

   ![이미지 of_the Microsoft Defender 보안 센터 시작 마법사 페이지](../../media/mtp-eval-59.png)

3. 기본 설정 데이터 저장소 위치, 데이터 보존 정책, 조직 크기 및 미리 보기 기능의 옵트인에 따라를 선택 합니다.

   ![이미지 of_the 페이지에서 데이터 저장소 국가, 보존 정책 및 조직 크기를 선택 합니다. 선택이 완료 되 면 다음을 클릭 합니다.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > 나중에 데이터 저장 위치와 같은 일부 설정은 변경할 수 없습니다. 

   **다음**을 클릭합니다. 

4. **계속** 을 클릭 하 고 MICROSOFT Defender ATP 테 넌 트를 프로 비전 합니다.

   !["계속" 단추를 클릭 하 여 클라우드 인스턴스를 만들도록 하는 이미지 of_the 페이지 프롬프트](../../media/mtp-eval-61.png)

5. 그룹 정책, Microsoft Endpoint Manager 또는 Microsoft Defender ATP에 대 한 로컬 스크립트를 실행 하 여 끝점을 온보드 했습니다. 편의상이 가이드에서는 로컬 스크립트를 사용 합니다.

6. **패키지 다운로드** 를 클릭 하 고 사용자의 끝점에 온 보 딩 스크립트를 복사 합니다.

   ![사용자가 끝점 또는 끝점에 온 보 딩 스크립트를 복사할 수 있도록 패키지 다운로드 단추를 클릭 하 라는 메시지를 표시 하는 이미지 of_page](../../media/mtp-eval-62.png)

7. 끝점에서 온 보 딩 스크립트를 관리자로 실행 하 고 Y를 선택 합니다. 

   ![온 보 딩 스크립트를 실행 하는 이미지 of_the 명령줄을 선택한 다음 계속 하려면 Y를 선택 합니다.](../../media/mtp-eval-63.png)

8. 축 하 합니다, 첫 번째 끝점을 등록 했습니다.

   ![이미지 of_the 명령줄에서 첫 번째 끝점을 등록 확인 합니다. 계속 하려면 아무 키나 누르십시오.](../../media/mtp-eval-64.png)

9. Microsoft Defender ATP 마법사의 검색 테스트를 복사 하 여 붙여 넣습니다.

   ![이미지 of_the 복사를 클릭 하 여 명령 프롬프트에 붙여 넣으려는 검색 테스트 스크립트를 복사 하는 검색 테스트 단계를 실행 합니다.](../../media/mtp-eval-65.png)

10. 관리자 권한 명령 프롬프트에 PowerShell 스크립트를 복사 하 고 실행 합니다. 

    ![관리자 권한 명령 프롬프트에 PowerShell 스크립트를 복사 하 고 실행 해야 하는 이미지 of_command 프롬프트](../../media/mtp-eval-66.png)

11. 마법사에서 **Microsoft DEFENDER ATP 사용 시작** 을 선택 합니다.

    ![Microsoft Defender ATP 사용 시작을 클릭 해야 하는 마법사의 이미지 of_the 확인 메시지를 표시 합니다.](../../media/mtp-eval-67.png)
 
12. [Microsoft Defender 보안 센터](https://securitycenter.windows.com/)를 방문 합니다. **설정** 으로 이동한 후 **고급 기능**을 선택 합니다. 

    ![고급 기능을 선택 해야 하는 이미지 of_Microsoft Defender 보안 센터 설정 메뉴](../../media/mtp-eval-68.png)

13. **Azure Advanced Threat Protection**과의 통합을 사용 하도록 설정 합니다.  

    ![이미지 of_Microsoft Defender 보안 센터 고급 기능, Azure Advanced Threat Protection 옵션 설정/해제 해야 하는 경우](../../media/mtp-eval-69.png)

14. **Office 365 위협 인텔리전스**와의 통합을 설정 합니다.

    ![이미지 of_Microsoft Defender 보안 센터 고급 기능, Office 365 위협 인텔리전스 옵션 설정/해제 해야 하는 경우](../../media/mtp-eval-70.png)

15. **Microsoft Cloud App Security**와의 통합을 설정 합니다.

    ![이미지 of_Microsoft Defender 보안 센터 고급 기능, Microsoft Cloud App Security option 전환에 필요한 기능](../../media/mtp-eval-71.png)

16. 아래로 스크롤한 후 **기본 설정 저장** 을 클릭 하 여 새 통합을 확인 합니다.

    ![클릭 해야 하는 이미지 of_Save 기본 설정 단추](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-threat-protection-service"></a>Microsoft Threat Protection 서비스 시작

>[!NOTE]
>2020 년 6 월 1 일부 부터는 Microsoft에서 모든 적격 테 넌 트에 대해 Microsoft Threat Protection 기능을 자동으로 사용 하도록 설정 합니다. 자세한 내용은 [라이선스 자격에 대 한 Microsoft 기술 커뮤니티 문서를](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) 참조 하세요. 


[Microsoft 365 보안 센터로](https://security.microsoft.com/homepage)이동 합니다. **설정** 으로 이동한 후 **Microsoft Threat Protection**을 선택 합니다.

![이미지 of_Microsoft 위협 보호 옵션 스크린샷 (Microsoft 365 보안 센터 설정 페이지) ](../../media/mtp-eval-72b.png) <br>

보다 포괄적인 지침을 보려면 [Microsoft Threat Protection 설정을](mtp-enable.md)참조 하십시오. 

축하합니다! Microsoft Threat Protection 평가판 랩 또는 파일럿 환경을 만들었습니다. 이제 Microsoft Threat Protection 사용자 인터페이스를 이해 하는 데 도움이 될 수 있습니다. 다음 Microsoft Threat Protection 대화형 가이드에서 설명 하 고 일상적인 보안 작업에 각 대시보드를 사용 하는 방법을 알고 있어야 합니다.


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

다음으로, 공격을 시뮬레이트하고 상호 제품 기능 검색 방법, 알림을 만들고 끝점에 대 한 fileless 공격에 자동으로 대응 하는 방법을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계
|![공격 시뮬레이션 단계](../../media/mtp/run-sim.png) <br>[공격 시뮬레이션 단계](mtp-pilot-simulate.md) | Microsoft Threat Protection 파일럿 환경에 대 한 공격 시뮬레이션을 실행 합니다.
|:-------|:-----|
