---
title: 평가판 또는 파일럿 환경에 대한 Microsoft 365 Defender 기조 구성
description: 시험 랩 또는 파일럿 환경에 대해 Microsoft Defender for Office 365, ID용 Microsoft Defender, Microsoft Cloud App Security 및 끝점용 Microsoft Defender와 같은 Microsoft 365 Defender 기조를 구성합니다.
keywords: Microsoft Threat Protection 평가판 구성, Microsoft Threat Protection 평가판 구성, Microsoft Threat Protection 파일럿 프로젝트 구성, Microsoft Threat Protection 기조 구성, Microsoft Threat Protection 기조
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 78b37d9d435eabce47d360efd630c2e55cadacd1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932241"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>평가판 또는 파일럿 환경에 대한 Microsoft 365 Defender 기조 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender


Microsoft 365 Defender 평가판 랩 또는 파일럿 환경을 만들고 배포하는 과정은 3단계 프로세스입니다.

|[![1단계: 준비](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[1단계: 준비](prepare-mtpeval.md) |[![2단계: 설정](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[2단계: 설정](setup-mtpeval.md) |![3단계: 온보드](../../media/phase-diagrams/onboard.png)<br/>3단계: 온보드 | [![파일럿으로 돌아가기](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[파일럿 플레이북으로 돌아가기](mtp-pilot.md) |
|--|--|--|--|
|| |*You are here!* | |

현재 구성 단계에 있습니다.

성공적인 배포의 핵심은 준비입니다. 이 문서에서는 끝점용 Microsoft Defender 배포를 준비할 때 고려해야 할 점에 대해 안내합니다.


## <a name="microsoft-365-defender-pillars"></a>Microsoft 365 Defender 기조
Microsoft 365 Defender는 네 가지 기조로 구성됩니다. 하나의 기둥이 네트워크 조직의 보안에 이미 가치를 제공할 수 있도, 네 가지 Microsoft 365 Defender 기조를 사용하도록 설정하면 조직에 가장 큰 가치를 제공합니다.

![클라우드 of_Microsoft, Microsoft Cloud App Security 및 데이터용 끝점용 Microsoft Defender for Identity에 대한 사용자용 이미지 365 Defender 솔루션, ID용 Microsoft Defender](../../media/mtp/m365pillars.png)

이 섹션에서는 다음을 구성하는 방법을 안내합니다.
-   Office 365용 Microsoft Defender
-   ID용 Microsoft Defender 
-   Microsoft Cloud App Security
-   엔드포인트용 Microsoft Defender


## <a name="configure-microsoft-defender-for-office-365"></a>Office 365용 Microsoft Defender 구성

>[!NOTE]
>Office 365용 Defender를 이미 사용하도록 설정한 경우 이 단계를 건너뜁. 

이러한 설정 중 일부를 확인하는 데 도움이 *되는 Office 365 ADVANCED Threat Protection 권장 구성 분석기(ORCA)라는* PowerShell 모듈이 있습니다. 테넌트에서 관리자로 실행하면 get-ORCAReport는 스팸 방지, 피싱 방지 및 기타 메시지 예방조치 설정에 대한 평가를 생성하는 데 도움이 됩니다. .에서 이 모듈을 다운로드할 https://www.powershellgallery.com/packages/ORCA/ 수 있습니다. 

1. Office [365 보안](https://protection.office.com/homepage)및 & 센터  >  **위협 관리 정책으로**  >  **이동합니다.**

   ![이미지 of_Office 365 보안 & 센터 위협 관리 정책 페이지](../../media/mtp-eval-32.png)
 
2. 피싱 **방지를 클릭하고** 정책 **이름** 및 설명 만들기를 선택하고 입력합니다. **다음** 을 클릭합니다.

   ![정책 이름을 of_Office 365 보안 & 준수 센터 피싱 방지 정책 페이지 이미지](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Office 365용 Microsoft Defender에서 고급 피싱 방지 정책을 편집합니다. 고급 **피싱 임계값을** **2 - 적극적으로 변경합니다.**

3. 조건 **추가** 드롭다운 메뉴를 클릭하고 도메인을 받는 사람 도메인으로 선택합니다. **다음** 을 클릭합니다.

   ![응용 of_Office 조건을 추가할 수 있는 365 보안 & 준수 센터 피싱 방지 정책 페이지 이미지](../../media/mtp-eval-34.png)
 
4. 설정을 검토합니다. 확인하려면 **이 정책 만들기를** 클릭합니다. 

   ![설정 of_Office 검토하고 이 정책 만들기 단추를 클릭할 수 있는 365 보안 & 준수 센터 피싱 방지 정책 페이지 이미지](../../media/mtp-eval-35.png)
 
5. 안전한 **첨부 파일을** 선택하고 **SharePoint, OneDrive 및 Microsoft Teams에 대한 ATP 켜기 옵션을** 선택합니다.

   ![이미지 of_Office 365 보안 & 준수 센터 페이지에서 SharePoint, OneDrive 및 Microsoft Teams에 대해 ATP를 켜면 됩니다.](../../media/mtp-eval-36.png)

6. + 아이콘을 클릭하여 새 안전한 첨부 파일 정책을 만들고 도메인에 받는 사람 도메인으로 적용합니다. **저장** 을 클릭합니다.

   ![새 of_Office 안전한 첨부 파일 & 만들 수 있는 365 보안 및 준수 센터 페이지 이미지](../../media/mtp-eval-37.png)
 
7. 그런 다음 안전한 **링크** 정책을 선택한 다음 연필 아이콘을 클릭하여 기본 정책을 편집합니다.

8. 나머지 옵션이  선택되어 있는 동안 사용자가 안전한 링크 옵션을 클릭하는 경우 Do not track이 선택되어 있지 않은지 확인 자세한 [내용은 안전한 링크](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) 설정을 참조하세요. **저장** 을 클릭합니다. 

   ![이미지 of_Office 365 보안 & 준수 센터 페이지 - 사용자가 안전을 클릭한 경우 추적하지 않는 옵션이 선택되어 있지 않습니다.](../../media/mtp-eval-38.png)

9. 그런 다음 **맬웨어** 방지 정책을 선택하고 기본값을 선택하고 연필 아이콘을 선택합니다.

10. 설정을 **클릭하고** **예를** 선택하고 기본 알림 텍스트를 사용하여 맬웨어 검색 **응답을 사용하도록 설정할 수 있습니다.** 일반 첨부 **파일 형식 필터를 켜는** 경우 **저장** 을 클릭합니다.

    ![기본 of_Office 맬웨어 검색 응답이 켜져 있으며 일반적인 첨부 파일 유형 필터가 켜져 있는 맬웨어 검색 센터 페이지를 보여주는 이미지 of_Office 36 & 5 보안 및 준수 센터 페이지](../../media/mtp-eval-39.png)
  
11. Office [365 보안](https://protection.office.com/homepage)& 준수 센터 검색 감사 로그 검색으로 이동한 후  >    >   감사를 하도록 설정 합니다.

    ![감사 of_Office 검색을 & 수 있는 365 보안 및 준수 센터 페이지 이미지](../../media/mtp-eval-40.png)

12. Office 365용 Microsoft Defender와 끝점용 Microsoft Defender를 통합합니다. Office [365 보안 &](https://protection.office.com/homepage)준수 센터 위협 관리 탐색기로 이동하고 화면의 오른쪽 위 모서리에 있는 끝점 설정에 대한  >    >   **Microsoft Defender를** 선택합니다. 끝점용 Defender 연결 대화 상자에서 **끝점용 Microsoft Defender에 연결합니다.**

    ![끝점 of_Office Microsoft Defender를 & 수 있는 365 보안 및 준수 센터 페이지 이미지](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>Id에 대한 Microsoft Defender 구성

>[!NOTE]
>Id에 대해 Microsoft Defender를 이미 사용하도록 설정한 경우 이 단계를 건너뛰기

1. Microsoft [365](https://security.microsoft.com/info) 보안 센터로 이동하여 >  >  **Microsoft Defender에서** ID에 대한 추가 리소스를 선택합니다.

   ![ID of_Microsoft에 대한 Microsoft Defender를 여는 옵션이 있는 365 보안 센터 페이지 이미지](../../media/mtp-eval-42.png)

2. **Create(만들기)를** 클릭하여 ID용 Microsoft Defender 마법사를 시작합니다. 

   ![이미지 of_Microsoft Id용 Defender 마법사 페이지에서 만들기 단추를 클릭해야 합니다.](../../media/mtp-eval-43.png)

3. Choose **Provide a username and password to connect to your Active Directory forest.**  

   ![ID of_Microsoft Defender 시작 페이지 이미지](../../media/mtp-eval-44.png)

4. Active Directory의 모든 자격 증명을 입력합니다. 이 계정은 Active Directory에 대한 읽기 권한이 있는 모든 사용자 계정일 수 있습니다.

   ![자격 증명을 of_Microsoft Id 디렉터리 서비스용 Defender 페이지 이미지](../../media/mtp-eval-45.png)

5. 그런 다음 센서 설치 **다운로드를 선택하고** 파일을 도메인 컨트롤러로 전송합니다.

   ![센서 of_Microsoft 다운로드를 선택할 수 있는 ID용 Defender 페이지 이미지](../../media/mtp-eval-46.png)

6. Microsoft Defender for Identity Sensor Setup을 실행하고 마법사를 실행합니다.

   ![ID of_Microsoft Microsoft Defender 센서 마법사를 따라 이동하려면 다음을 클릭해야 하는 ID용 Defender 페이지 이미지](../../media/mtp-eval-47.png)
 
7. 센서 **배포 유형에서** 다음을 클릭합니다.

   ![이미지 of_Microsoft 다음 페이지로 이동하려면 다음을 클릭해야 하는 ID용 Defender 페이지](../../media/mtp-eval-48.png)
 
8. 마법사에서 다음에 입력해야 하기 때문에 액세스 키를 복사합니다.

   ![이미지 of_the 다음 Microsoft Defender for Identity 센서 설정 마법사 페이지에 입력해야 하는 액세스 키를 복사해야 하는 센서 페이지](../../media/mtp-eval-49.png)
 
9. 선택키를 마법사에 복사하고 설치를 **클릭합니다.** 

   ![이미지 of_Microsoft 키를 제공하고 설치 단추를 클릭해야 하는 ID용 Defender 센서 마법사 페이지](../../media/mtp-eval-50.png)

10. 축하합니다. 도메인 컨트롤러에서 ID에 대한 Microsoft Defender를 성공적으로 구성했습니다.

    ![이미지 of_Microsoft 단추를 클릭해야 하는 ID 센서 마법사 설치 완료에 대한 Defender](../../media/mtp-eval-51.png)
 
11. ID에 [대한 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2040449) 설정 섹션에서 **끝점용 Microsoft Defender **를 선택한 다음 토글을 켜십시오. **저장** 을 클릭합니다. 

    ![이미지 of_the Microsoft Defender for Identity 설정 페이지에서 끝점용 Microsoft Defender 토글을 설정해야 합니다.](../../media/mtp-eval-52.png)

>[!NOTE]
>Windows Defender ATP는 끝점용 Microsoft Defender로 다시 브랜드가 업데이트되어 있습니다. 일관성을 위해 모든 포털에서 변경 내용을 변경하는 것이 롤아웃되고 있습니다.


## <a name="configure-microsoft-cloud-app-security"></a>Microsoft Cloud App Security 구성

>[!NOTE]
>Microsoft Cloud App Security를 이미 사용하도록 설정한 경우 이 단계를 건너뜁. 

1. Microsoft [365 보안 센터](https://security.microsoft.com/info)추가  >  **리소스** Microsoft Cloud  >  **App Security로 이동합니다.**

   ![이미지 of_Microsoft Microsoft Cloud App 카드를 볼 수 있으며 열기 단추를 클릭해야 하는 365 보안 센터 페이지](../../media/mtp-eval-53.png)

2. ID에 대한 Microsoft Defender를 통합하라는 정보 프롬프트에서 ID 데이터 **통합에 대해 Microsoft Defender 사용을 선택합니다.**
  
   ![ID of_the Microsoft Defender 사용 링크를 선택해야 하는 ID에 대한 Microsoft Defender 통합 정보 프롬프트 이미지](../../media/mtp-eval-54.png)

   > [!NOTE]
   > 이 프롬프트가 표시되지 않는 경우 ID용 Microsoft Defender 데이터 통합이 이미 활성화되어 있는 것일 수 있습니다. 그러나 확실하지 않은 경우 IT 관리자에게 문의하여 확인을 하시기 바랍니다. 

3. 설정으로 **이동하여** ID 통합에 **대한 Microsoft Defender 통합** 토글을 켜고 저장을 **클릭합니다.** 

   ![ID of_the Microsoft Defender 통합 토글을 켜고 저장을 클릭해야 하는 이미지 설정 페이지](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > 새 Microsoft Defender for Identity 인스턴스의 경우 이 통합 토글이 자동으로 켜집니다. 다음 단계를 진행하기 전에 ID에 대한 Microsoft Defender 통합이 활성화되어 있는지 확인합니다.
 
4. 클라우드 검색 설정에서 **끝점 통합을 위한 Microsoft Defender를 선택한** 다음 통합을 사용하도록 설정하십시오. **저장** 을 클릭합니다.

   ![이미지 of_the Microsoft Defender for Endpoint 통합의 Microsoft Defender에서 확인란을 선택하지 않은 앱 차단이 선택된 끝점용 Microsoft Defender 페이지입니다. 저장을 클릭합니다.](../../media/mtp-eval-56.png)

5. 클라우드 검색 설정에서 사용자 강화를 선택한 다음 Azure Active Directory와의 통합을 사용하도록 설정하십시오.

   ![Azure Active Directory 사용자 이름 확인란을 사용하여 검색된 사용자 식별자를 보강하는 사용자 강화 섹션의 이미지](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender 구성

>[!NOTE]
>끝점에 대해 Microsoft Defender를 이미 사용하도록 설정한 경우 이 단계를 건너뜁습니다.

1. Microsoft [365](https://security.microsoft.com/info)보안 센터에서 Microsoft Defender 보안 센터 추가  >    >  **리소스로 이동합니다.** **열기** 를 클릭합니다. 

   ![Microsoft of_Microsoft 센터 페이지의 Defender 보안 센터 옵션에 대한 이미지](../../media/mtp-eval-58.png)
 
2. 끝점용 Microsoft Defender 마법사를 따르기 **다음** 을 클릭합니다. 

   ![이미지 of_the Microsoft Defender 보안 센터 시작 마법사 페이지](../../media/mtp-eval-59.png)

3. 기본 설정 데이터 저장소 위치, 데이터 보존 정책, 조직 크기에 따라 선택하고 미리 보기 기능을 옵트인(opt in)합니다.

   ![데이터 of_the, 보존 정책 및 조직 크기를 선택하기 위한 이미지 페이지 선택이 완료되면 다음을 클릭합니다.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > 데이터 저장 위치와 같은 일부 설정은 이후에 변경할 수 없습니다. 

   **다음** 을 클릭합니다. 

4. **계속을** 클릭하면 끝점 테넌트에 대한 Microsoft Defender가 프로비전됩니다.

   ![클라우드 of_the 만들기 위해 계속 단추를 클릭하라는 메시지 표시 페이지 이미지](../../media/mtp-eval-61.png)

5. 그룹 정책, Microsoft Endpoint Manager 또는 끝점용 Microsoft Defender에 대한 로컬 스크립트를 실행하여 끝점을 온보딩합니다. 이 가이드에서는 간편한 설명을 위해 로컬 스크립트를 사용했습니다.

6. 패키지 **다운로드를** 클릭하고 끝점에 온보딩 스크립트를 복사합니다.

   ![이미지 of_page 패키지 다운로드 단추를 클릭하여 끝점 또는 끝점에 온보딩 스크립트 복사](../../media/mtp-eval-62.png)

7. 끝점에서 관리자 권한으로 온보딩 스크립트를 실행하고 Y를 선택 합니다. 

   ![이미지 of_the 스크립트를 실행하고 계속할 Y를 선택하는 명령줄](../../media/mtp-eval-63.png)

8. 축하합니다. 첫 번째 끝점을 온보드했습니다.

   ![이미지 of_the 끝점을 온보드했다는 확인 메시지가 표시됩니다. 계속하기 위해 아무 키나 누르기](../../media/mtp-eval-64.png)

9. 끝점용 Microsoft Defender 마법사에서 검색 테스트를 복사하여 붙여 넣습니다.

   ![이미지 of_the 명령 프롬프트에 붙여넣을 검색 테스트 스크립트를 복사하려면 복사를 클릭해야 하는 검색 테스트 단계를 실행합니다.](../../media/mtp-eval-65.png)

10. PowerShell 스크립트를 상승된 명령 프롬프트에 복사하고 실행합니다. 

    ![PowerShell of_command 권한 명령 프롬프트에 복사한 후 실행해야 하는 이미지 프롬프트](../../media/mtp-eval-66.png)

11. **마법사에서 끝점용 Microsoft Defender 사용** 시작을 선택합니다.

    ![이미지 of_the 끝점용 Microsoft Defender 사용 시작을 클릭해야 하는 마법사에서 확인 메시지 표시](../../media/mtp-eval-67.png)
 
12. Microsoft [Defender 보안 센터를 방문합니다.](https://securitycenter.windows.com/) 설정으로 **이동한** 다음 **고급 기능을 선택합니다.** 

    ![고급 of_Microsoft 선택해야 하는 Defender 보안 센터 설정 메뉴에 대한 이미지](../../media/mtp-eval-68.png)

13. ID용 Microsoft **Defender와의 통합을 켜기**  

    ![이미지 of_Microsoft Defender 보안 센터 고급 기능, 켜야 하는 ID에 대한 Microsoft Defender 옵션 토글](../../media/mtp-eval-69.png)

14. **Office 365** 위협 인텔리전스와의 통합 켜기.

    ![이미지 of_Microsoft Defender 보안 센터 고급 기능, 켜야 하는 Office 365 위협 인텔리전스 옵션 토글](../../media/mtp-eval-70.png)

15. Microsoft Cloud **App Security와의 통합 켜기.**

    ![이미지 of_Microsoft Defender 보안 센터 고급 기능, 켜야 하는 Microsoft Cloud App Security 옵션 토글](../../media/mtp-eval-71.png)

16. 아래로 스크롤하여 기본 설정 저장을 **클릭하여** 새 통합을 확인할 수 있습니다.

    ![클릭해야 of_Save 이미지 기본 설정 단추](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>Microsoft 365 Defender 서비스 시작

>[!NOTE]
>2020년 6월 1일부터 Microsoft는 모든 적격 테넌트에 대해 Microsoft 365 Defender 기능을 자동으로 사용할 수 있습니다. 자세한 내용은 라이선스 자격에 [대한 Microsoft](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) 기술 커뮤니티 문서를 참조하세요. 


Microsoft [365 보안 센터로 이동](https://security.microsoft.com/homepage) 설정으로 **이동한** 다음 **Microsoft 365 Defender를 선택합니다.**

![Microsoft of_Microsoft 센터 설정 페이지의 이미지 365 Defender 옵션 스크린샷 ](../../media/mtp-eval-72b.png) <br>

보다 포괄적인 지침은 [Microsoft 365 Defender 켜기를 참조하세요.](mtp-enable.md) 

축하합니다! 방금 Microsoft 365 Defender 평가판 랩 또는 파일럿 환경을 만들게 되었습니다! 이제 Microsoft 365 Defender 사용자 인터페이스에 익숙해지세요! 다음 Microsoft 365 Defender 대화형 가이드에서 학습할 수 있는 내용을 알아보고 매일 보안 작업 작업에 각 대시보드를 사용하는 방법을 알고 있습니다.


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

다음으로, 공격을 시뮬레이트하고 제품 간 기능이 끝점에 대한 파일 없는 공격을 감지하고, 경고를 만들고, 자동으로 대응하는 방법을 볼 수 있습니다.

## <a name="next-step"></a>다음 단계
|[공격 시뮬레이션 단계](mtp-pilot-simulate.md) | Microsoft 365 Defender 파일럿 환경에 대한 공격 시뮬레이션을 실행합니다.
|:-------|:-----|
