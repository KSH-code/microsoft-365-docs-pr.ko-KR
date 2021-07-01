---
title: 시험 Microsoft 365 Defender 환경의 기본 구성 기조 구성
description: 평가판 또는 파일럿 환경에 Microsoft 365 Defender Microsoft Defender for Office 365, ID용 Microsoft Defender, Microsoft Cloud App Security 및 끝점용 Microsoft Defender와 같은 기본 기조를 구성합니다.
keywords: Microsoft 365 Defender 평가판 구성, Microsoft 365 Defender 구성, Microsoft 365 Defender 파일럿 프로젝트 구성, Microsoft 365 Defender 기조 구성, Microsoft 365 Defender 기조
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e50210f02d14be33c357517515d456318aac4bb6
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229782"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>시험 Microsoft 365 Defender 환경의 기본 구성 기조 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender


Microsoft 365 Defender 테스트 랩 또는 파일럿 환경을 만들고 배포하는 과정은 다음 3단계 프로세스입니다.

|[![1 단계: 준비](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)<br/>[1 단계: 준비](prepare-m365d-eval.md) |[![2 단계: 설정](../../media/phase-diagrams/setup.png)](setup-m365deval.md)<br/>[2 단계: 설정](setup-m365deval.md) |![3 단계: 온보딩](../../media/phase-diagrams/onboard.png)<br/>3 단계: 온보딩 | [![파일럿으로 돌아가기](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[파일럿 플레이북으로 돌아가기](m365d-pilot.md) |
|--|--|--|--|
|| |*여기 있습니다!* | |

현재 구성 단계에 있습니다.

성공적인 배포의 핵심은 준비입니다. 이 문서에서는 끝점용 Microsoft Defender 배포를 준비할 때 고려해야 할 지점을 안내합니다.

## <a name="microsoft-365-defender-pillars"></a>Microsoft 365 Defender 기조
Microsoft 365 Defender 4개의 기조로 구성됩니다. 하나의 기둥이 네트워크 조직의 보안에 이미 가치를 제공할 수 있겠지만 네 가지 Microsoft 365 Defender 기조를 설정하면 조직에 가장 큰 가치를 제공합니다.

![클라우드 of_Microsoft 앱, Microsoft Cloud App Security 및 데이터용 끝점에 대한 사용자용 Microsoft Defender 365 Defender 솔루션인 ID용 Microsoft Defender를 Office 365](../../media/mtp/m365pillars.png)

이 섹션에서는 다음을 구성하는 방법을 안내합니다.

- Office 365용 Microsoft Defender
- ID용 Microsoft Defender
- Microsoft Cloud App Security
- 엔드포인트용 Microsoft Defender

## <a name="configure-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

> [!NOTE]
> 사용자에 대해 Defender를 이미 사용하도록 설정한 경우 이 단계를 Office 365.

이러한 설정 중 일부를 확인하는 데 도움이 되는 Office 365 *ORCA(Advanced Threat Protection* 권장 구성 분석기)라는 PowerShell 모듈이 있습니다. 테넌트에서 관리자로 실행하면 get-ORCAReport는 스팸 방지, 피싱 방지 및 기타 메시지 예방조치 설정에 대한 평가를 생성하는 데 도움이 됩니다. 이 모듈은 에서 다운로드할 수 https://www.powershellgallery.com/packages/ORCA/ 있습니다.

1. 보안 [Office 365 준수 & 관리](https://protection.office.com/homepage)  >  **정책으로**  >  **이동합니다.**

   ![이미지 of_Office 365 보안 & 센터 위협 관리 정책 페이지](../../media/mtp-eval-32.png)

2. 피싱 **방지를 클릭하고** **정책** 이름 및 설명 만들기를 선택하고 입력합니다. **다음** 을 클릭합니다.

   ![정책의 이름을 of_Office 365 보안 & 준수 센터 피싱 방지 정책 페이지 이미지](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Microsoft Defender에서 고급 피싱 방지 정책을 편집하여 Office 365. 고급 **피싱 임계값을** **2 - 적극적으로 변경합니다.**

3. 조건 **추가** 드롭다운 메뉴를 클릭하고 받는 사람 도메인으로 도메인을 선택합니다. **다음** 을 클릭합니다.

   ![응용 of_Office 조건을 추가할 수 있는 & 365 보안 & 준수 센터 피싱 방지 정책 페이지 이미지](../../media/mtp-eval-34.png)

4. 설정을 검토합니다. 이 **정책 만들기를 클릭하여** 확인할 수 있습니다.

   ![of_Office 설정을 검토하고 이 정책 만들기 단추를 클릭할 수 있는 & 365 보안 & 준수 센터 피싱 방지 정책 페이지 이미지](../../media/mtp-eval-35.png)

5. 첨부 **금고** 선택하고 설정, **SharePoint,** OneDrive 및 Microsoft Teams 옵션을 선택합니다.

   ![이미지 of_Office 365 보안 & 준수 센터 페이지에서 SharePoint, OneDrive 및 데이터 센터에 대해 ATP를 켜면 Microsoft Teams](../../media/mtp-eval-36.png)

6. + 아이콘을 클릭하여 새 안전한 첨부 파일 정책을 만들고 도메인에 받는 사람 도메인으로 적용합니다. **저장** 을 클릭합니다.

   ![새 of_Office 안전한 첨부 파일 & 만들 수 있는 365 보안 및 준수 센터 페이지 이미지](../../media/mtp-eval-37.png)

7. 그런 다음  연결 금고 선택한 다음 연필 아이콘을 클릭하여 기본 정책을 편집합니다.

8. 나머지 옵션이  선택되어 있는 동안 사용자가 안전한 링크를 클릭하는 경우 추적 안 하세요. 옵션이 선택되어 있는지 확인 합니다. 자세한 [금고 링크](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) 설정을 참조하세요. **저장** 을 클릭합니다.

   ![이미지 of_Office 365 보안 & 준수 센터 페이지에서 사용자가 안전을 클릭하는 경우 추적 안 하도록 설정 옵션이 선택되어 있지 않습니다.](../../media/mtp-eval-38.png)

9. 그런 다음 **맬웨어** 방지 정책을 선택하고 기본값을 선택하고 연필 아이콘을 선택합니다.

10. **맬웨어 설정** **예를** 선택하고 기본 알림 텍스트를 사용하여 **맬웨어** 검색 응답을 사용하도록 설정할 수 있습니다. 일반 첨부 **파일 형식 필터를 켜습니다.** **저장** 을 클릭합니다.

    ![기본 of_Office 알림과 함께 맬웨어 검색 응답이 켜져 있으며 일반적인 첨부 파일 형식 필터가 켜져 있는 & 365 보안 및 준수 센터 페이지 이미지](../../media/mtp-eval-39.png)

11. 보안 [Office 365 센터](https://protection.office.com/homepage)& 감사 로그 검색으로  >    >  **이동한** 다음 감사를 켜야 합니다.

    ![감사 of_Office 365 보안 & 센터 페이지에서 감사 로그 검색을 켜면 됩니다.](../../media/mtp-eval-40.png)

12. Microsoft Defender for Office 365 Microsoft Defender for Endpoint와 통합합니다. Office 365 [보안](https://protection.office.com/homepage)& 센터 위협 관리 탐색기로 이동하고 화면 오른쪽 설정 끝점용  >    >   **Microsoft Defender를** 선택합니다. 끝점 연결용 Defender 대화 상자에서 **끝점용 Microsoft Defender에 커넥트 를 으로 전환합니다.**

    ![끝점 of_Office Microsoft Defender를 끄는 & 365 보안 및 준수 센터 페이지 이미지](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>ID에 맞게 Microsoft Defender 구성

> [!NOTE]
> Id에 대해 Microsoft Defender를 이미 사용하도록 설정한 경우 이 단계를 건너뛰기

1. 보안 [Microsoft 365 센터로](https://security.microsoft.com/info) > 추가 리소스   >  **Microsoft Defender for Identity 를 선택합니다.**

   ![Id에 대한 Microsoft Defender를 여는 옵션이 있는 of_Microsoft 365 보안 센터 페이지 이미지](../../media/mtp-eval-42.png)

2. **만들기를** 클릭하여 Id에 대한 Microsoft Defender 마법사를 시작합니다.

   ![만들기 of_Microsoft 클릭해야 하는 ID용 Defender 마법사 페이지 이미지](../../media/mtp-eval-43.png)

3. 사용자 이름 및 암호 제공을 선택하고 Active Directory 포리스트에 **연결합니다.**

   ![ID of_Microsoft Defender 이미지 페이지](../../media/mtp-eval-44.png)

4. Active Directory의 사내 자격 증명을 입력합니다. 이 계정은 Active Directory에 대한 읽기 권한이 있는 모든 사용자 계정일 수 있습니다.

   ![자격 증명을 of_Microsoft Id 디렉터리 서비스 페이지에 대한 Defender 이미지](../../media/mtp-eval-45.png)

5. 그런 다음 센서 설치 **다운로드를 선택하고** 파일을 도메인 컨트롤러로 전송합니다.

   ![센서 of_Microsoft 다운로드를 선택할 수 있는 ID용 Defender 이미지 페이지](../../media/mtp-eval-46.png)

6. Microsoft Defender for Identity Sensor Setup을 실행하고 마법사 다음을 시작하십시오.

   ![ID of_Microsoft Microsoft Defender 센서 마법사를 따라 이동하려면 다음을 클릭해야 하는 ID용 Defender 페이지 이미지](../../media/mtp-eval-47.png)

7. 센서 **배포 유형에서** 다음을 클릭합니다.

   ![다음 of_Microsoft 이동하려면 다음을 클릭해야 하는 ID용 Defender 페이지 이미지](../../media/mtp-eval-48.png)

8. 마법사에서 다음에 입력해야 하여 액세스 키를 복사합니다.

   ![이미지 of_the 다음 Microsoft Defender for Identity 센서 설정 마법사 페이지에 입력해야 하는 액세스 키를 복사해야 하는 센서 페이지](../../media/mtp-eval-49.png)

9. 마법사에 선택키를 복사하고 설치를 **클릭합니다.**

   ![선택키를 of_Microsoft 설치 단추를 클릭해야 하는 ID용 Defender 센서 마법사 페이지에 대한 이미지](../../media/mtp-eval-50.png)

10. 축하합니다. 도메인 컨트롤러에서 ID에 대한 Microsoft Defender를 성공적으로 구성했습니다.

    ![완료 of_Microsoft 클릭해야 하는 ID용 Defender 센서 마법사 설치 완료 이미지](../../media/mtp-eval-51.png)

11. Id [설정에 대한 Microsoft Defender 섹션에서](https://go.microsoft.com/fwlink/?linkid=2040449) **끝점용 Microsoft Defender **를 선택한 다음 토글을 켜십시오. **저장** 을 클릭합니다.

    ![끝점 of_the Microsoft Defender 토글을 켜야 하는 ID용 Microsoft Defender 설정 페이지의 이미지](../../media/mtp-eval-52.png)

## <a name="configure-microsoft-cloud-app-security"></a>구성 Microsoft Cloud App Security

> [!NOTE]
> 이 단계를 이미 사용하도록 설정한 경우 이 단계를 Microsoft Cloud App Security.

1. 보안 [Microsoft 365 추가 리소스](https://security.microsoft.com/info)센터로  >    >  **Microsoft Cloud App Security.**

   ![이미지 of_Microsoft Microsoft Cloud App 카드를 볼 수 있으며 열기 단추를 클릭해야 하는 365 보안 센터 페이지](../../media/mtp-eval-53.png)

2. ID에 대한 Microsoft Defender를 통합하기 위한 정보 프롬프트에서 ID 데이터 **통합에 대해 Microsoft Defender 사용 을 선택합니다.**

   ![ID에 of_the Microsoft Defender를 통합하기 위한 정보 프롬프트 이미지](../../media/mtp-eval-54.png)

   > [!NOTE]
   > 이 프롬프트가 표시되지 않는 경우 ID용 Microsoft Defender 데이터 통합이 이미 활성화되어 있는 것일 수 있습니다. 그러나 확실하지 않은 경우 IT 관리자에게 문의하여 확인을 합니다.

3. 다음으로 **설정** 로 이동하여 **Id에** 대한 Microsoft Defender 통합 토글을 켜고 저장을 **클릭합니다.**

   ![Id에 of_the Microsoft Defender 통합 토글을 켜고 저장을 클릭해야 하는 이미지 설정 페이지](../../media/mtp-eval-55.png)

   > [!NOTE]
   > 새 Microsoft Defender for Identity 인스턴스의 경우 이 통합 토글이 자동으로 켜집니다. 다음 단계를 진행하기 전에 ID에 대한 Microsoft Defender 통합이 활성화되어 있는지 확인합니다.

4. 클라우드 검색 설정에서 **끝점 통합용 Microsoft Defender를 선택한** 다음 통합을 사용하도록 설정하십시오. **저장** 을 클릭합니다.

   ![이미지 of_the Microsoft Defender for Endpoint 통합 아래에서 차단되지 않은 앱 차단 확인란이 선택된 끝점용 Microsoft Defender 페이지입니다. 저장을 클릭합니다.](../../media/mtp-eval-56.png)

5. 클라우드 검색 설정에서 사용자 강화를 선택한 다음 사용자 및 사용자 Azure Active Directory.

   ![사용자 이름 확인란을 Azure Active Directory 검색된 사용자 식별자를 보강하는 사용자 강화 섹션의 이미지](../../media/mtp-eval-57.png)

## <a name="configure-microsoft-defender-for-endpoint"></a>끝점에 맞게 Microsoft Defender 구성

> [!NOTE]
> 끝점에 대해 Microsoft Defender를 이미 사용하도록 설정한 경우 이 단계를 건너뜁.

1. 보안 [Microsoft 365 추가 리소스](https://security.microsoft.com/info)센터로  >    >  **Microsoft Defender 보안 센터.** **열기** 를 클릭합니다. 

   ![of_Microsoft 센터 페이지의 이미지 Microsoft 365 Defender 보안 센터 옵션](../../media/mtp-eval-58.png)

2. 끝점용 Microsoft Defender 마법사를 따르기. **다음** 을 클릭합니다.

   ![이미지 of_the Microsoft Defender 보안 센터 시작 마법사 페이지](../../media/mtp-eval-59.png)

3. 기본 설정 데이터 저장소 위치, 데이터 보존 정책, 조직 크기 및 미리 보기 기능에 대한 옵트인(opt in)을 기준으로 합니다.

   ![이미지 of_the 데이터 저장소 국가, 보존 정책 및 조직 크기를 선택합니다. 선택이 완료되면 다음을 클릭합니다.](../../media/mtp-eval-60.png)

   > [!NOTE]
   > 데이터 저장 위치와 같은 일부 설정은 이후에 변경할 수 없습니다.

   **다음** 을 클릭합니다.

4. **계속을** 클릭하면 끝점 테넌트에 대한 Microsoft Defender를 프로비전합니다.

   ![클라우드 of_the 만들기 위한 계속 단추를 클릭하라는 메시지 표시 페이지 이미지](../../media/mtp-eval-61.png)

5. 그룹 정책을 통해 끝점을 온보딩하거나, Microsoft Endpoint Manager 또는 끝점용 Microsoft Defender에 대한 로컬 스크립트를 실행하여 끝점을 온보딩합니다. 간편한 설명을 위해 이 가이드에서는 로컬 스크립트를 사용하세요.

6. 패키지 **다운로드를** 클릭하고 끝점에 온보딩 스크립트를 복사합니다.

   ![이미지 of_page 패키지 다운로드 단추를 클릭하여 끝점 또는 끝점에 온보딩 스크립트를 복사합니다.](../../media/mtp-eval-62.png)

7. 끝점에서 관리자 권한으로 온보딩 스크립트를 실행하고 Y를 선택 합니다.

   ![이미지 of_the 명령줄에서 온보딩 스크립트를 실행하고 Y를 선택해 계속 진행](../../media/mtp-eval-63.png)

8. 축하합니다. 첫 번째 끝점을 온보드했습니다.

   ![이미지 of_the 끝점을 온보드했다는 확인 메시지가 표시됩니다. 계속하기 위해 아무 키나 누르기](../../media/mtp-eval-64.png)

9. Microsoft Defender for Endpoint 마법사에서 검색 테스트를 복사하여 붙여 넣습니다.

   ![이미지 of_the 명령 프롬프트에 붙여넣을 검색 테스트 스크립트를 복사하려면 복사를 클릭해야 하는 검색 테스트 단계를 실행합니다.](../../media/mtp-eval-65.png)

10. PowerShell 스크립트를 상승된 명령 프롬프트에 복사하여 실행합니다.

    ![PowerShell 스크립트를 of_command 명령 프롬프트에 복사하고 실행해야 하는 이미지 프롬프트](../../media/mtp-eval-66.png)

11. **마법사에서 끝점용 Microsoft Defender 사용** 시작을 선택합니다.

    ![이미지 of_the 끝점용 Microsoft Defender 사용 시작을 클릭해야 하는 마법사의 확인 프롬프트](../../media/mtp-eval-67.png)

12. 를 [Microsoft Defender 보안 센터.](https://securitycenter.windows.com/) 다음으로 **설정** 고급 **기능을 선택합니다.**

    ![고급 of_Microsoft 선택해야 하는 설정 Defender 보안 센터 메뉴의 이미지](../../media/mtp-eval-68.png)

13. Id에 대한 **Microsoft Defender와의 통합을 켜기.**

    ![이미지 of_Microsoft Defender 보안 센터 고급 기능, ID에 대한 Microsoft Defender 옵션 토글](../../media/mtp-eval-69.png)

14. 위협 인텔리전스와의 Office 365 **를 켜야 합니다.**

    ![이미지 of_Microsoft Defender 보안 센터 고급 기능, Office 365 설정해야 하는 위협 인텔리전스 옵션 토글](../../media/mtp-eval-70.png)

15. 에서 로 **통합을 Microsoft Cloud App Security.**

    ![이미지 of_Microsoft Defender 보안 센터 고급 기능, Microsoft Cloud App Security 설정해야 하는 옵션 토글](../../media/mtp-eval-71.png)

16. 아래로 스크롤하여 기본 설정 저장을 **클릭하여** 새 통합을 확인할 수 있습니다.

    ![클릭해야 of_Save 기본 설정 단추 이미지](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>Microsoft 365 Defender 서비스 시작

> [!NOTE]
> 2020년 6월 1일부터 Microsoft는 모든 적격 테넌트에 대해 Microsoft 365 Defender 기능을 자동으로 사용할 수 있습니다. 자세한 내용은 Community Microsoft [Tech Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) 문서를 참조하세요.

보안 [Microsoft 365 로 이동](https://security.microsoft.com/homepage) 에서 **설정** 로 이동한 다음 를 **Microsoft 365 Defender.**

![of_Microsoft 보안 센터 페이지의 Microsoft 365 365 Defender 옵션 설정 스크린샷](../../media/mtp-eval-72b.png)

보다 포괄적인 지침은 을(를) [켜기 Microsoft 365 Defender.](m365d-enable.md)

축하합니다! 파일럿 랩 또는 파일럿 Microsoft 365 Defender 방금 만들었다고 합니다. 이제 사용자 인터페이스에 익숙해 Microsoft 365 Defender 있습니다. 다음 대화형 가이드에서 Microsoft 365 Defender 내용을 알아보고 각 대시보드를 사용하여 매일 수행되는 보안 작업 작업을 수행하는 방법을 알아 봐야 합니다.

[대화형 가이드 확인](https://aka.ms/MTP-Interactive-Guide)

다음으로, 공격을 시뮬레이트하고 제품 간 기능이 끝점에 대한 파일 없는 공격을 감지하고, 경고를 만들고, 자동으로 대응하는 방법을 볼 수 있습니다.

## <a name="next-step"></a>다음 단계

- [테스트 경고 생성](generate-test-alert.md) - 테스트 랩에서 공격 시뮬레이션을 Microsoft 365 Defender 실행합니다.
