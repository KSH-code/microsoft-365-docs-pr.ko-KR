---
title: 준수 관리자용 Microsoft 준수 구성 분석기
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 준수 구성 분석기를 사용하여 Microsoft 준수 관리자를 사용하여 빠르게 시작하고 실행하는 방법을 이해합니다.
ms.openlocfilehash: 75fb613aa1e0256c6c819336f9bcdd340acdff7d
ms.sourcegitcommit: be074f57e33c811bb3857043152825209bc8af07
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2021
ms.locfileid: "60335493"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a>준수 관리자용 Microsoft 준수 구성 분석기(미리 보기)

**이 문서의 예는** Microsoft 준수 관리자를 빠르게 시작할 수 있도록 Microsoft 준수 구성 분석기 도구를 설치하고 실행하는 방법을 학습합니다.

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a>MCCA(Microsoft 준수 구성 분석기)(미리 보기) 개요

MCCA(Microsoft 준수 구성 분석기)는 Microsoft 준수 관리자를 시작하는 데 도움이 되는 미리 보기 [도구입니다.](compliance-manager.md) MCCA는 조직의 현재 구성을 반더하고 권장 모범 사례에 대해 유효성을 Microsoft 365 PowerShell 기반 유틸리티입니다. 이러한 모범 사례는 데이터 보호 및 데이터 거버넌스에 대한 주요 규정 및 표준을 포함 하는 제어 집합을 기반으로 합니다.

MCCA를 사용하면 준수 관리자의 현재 환경과 환경에 적용되는 개선 Microsoft 365 있습니다. MCCA로 식별된 각 작업은 준수 관리자에 대한 직접 링크 및 해당 솔루션에 대한 구현에 대한 권장 사항을 제공합니다.

MCCA를 이해하기 위한 추가 리소스는 에 대한 [README](https://github.com/OfficeDev/MCCA#overview)지침을 GitHub. 이 페이지에서는 선행 구성에 대한 자세한 정보를 제공하며 전체 설치 지침을 제공합니다. 이 페이지에 액세스하려면 GitHub 계정이 필요하지 않습니다.

**가용성:** MCCA는 Office 365 및 Microsoft 365 라이선스가 있는 모든 조직과 미국 정부 Community(GCC) 보통, GCC High 및 DoD(국방부) 고객이 사용할 수 있습니다.

## <a name="install-mcca-and-run-a-report"></a>MCCA 설치 및 보고서 실행

MCCA 도구를 설치하려면 다음을 Windows PowerShell. 도구를 다운로드하여 설치한 후 보고서를 실행하기 위해 이러한 단계를 반복할 필요가 없습니다. MCCA를 열 때마다 로그인 자격 증명을 묻고 업데이트된 새 보고서를 생성합니다.

#### <a name="step-1-install-windows-powershell"></a>1단계: 설치 Windows PowerShell
먼저 PowerShell 갤러리에서 사용할 Exchange Online PowerShell 모듈(v2.0.3 이상)이 필요합니다. [설치 지침을 을(를) 얻습니다.](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)

#### <a name="step-2-install-mcca"></a>2단계: MCCA 설치

MCCA를 설치하려면 관리자 모드에서 PowerShell을 사용하여 시작하십시오. 아래 단계를 따릅니다.

1. 시작 Windows **선택합니다.**
2. **PowerShell을 입력하고** 마우스 오른쪽 단추로 Windows PowerShell **를** 클릭한 다음 관리자 권한으로 **실행을 선택합니다.**
1. 명령 프롬프트에서 다음을 입력합니다.

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a>3단계: 보고서 실행

MCCA를 설치한 후 MCCA를 실행하고 보고서를 생성할 수 있습니다. 보고서를 실행합니다.

1. PowerShell 열기
2. cmdlet을 실행합니다.

    ```powershell
    Get-MCCAReport
    ```

   높은 고객인 GCC 보고서를 실행하려면 추가 입력 매개 변수를 제공해야 합니다.

    ```powershell
    Get-MCCAReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. MCCA가 실행된 후 초기 버전 확인을 통해 자격 증명을 요청합니다. 사용자 이름 입력 프롬프트에서 Microsoft 365 계정 전자 메일 주소로 로그인합니다( 보고서를 만들 수 있는 역할[보기).](#role-based-reporting) 그런 다음 암호 프롬프트에 암호를 입력합니다.

그러면 보고서가 생성되는 데 약 2~5분 정도 걸립니다. 완료되면 브라우저 창이 열리며 HTML 보고서가 표시됩니다. 도구를 실행할 때마다 자격 증명을 요청하고 새 보고서를 생성합니다. 이 보고서는 다음 디렉터리에 로컬로 저장됩니다.

C:\Users \<username> \AppData\Local\Microsoft\MCCA. 

이 디렉터리에서 이전에 생성된 보고서에 액세스할 수 있습니다.

## <a name="understanding-your-report"></a>보고서 이해

보고서에는 보고서가 생성된 날짜와 시간을 기준으로 데이터가 반영됩니다. 맨 위 섹션에서는 생성된 경우, 조직 이름 및 테넌트 ID에 대한 세부 정보를 제공합니다.

#### <a name="geolocation-based-reporting"></a>지리적 위치 기반 보고

참고 **섹션에는** 테넌트의 지리적 위치에 따라 보고서가 사용자 지정되어 있습니다. 권장 사항 나열된 목록은 해당 국가 또는 지역에 따라 다를 수 있습니다.

지리적 위치 선택은 해당 지리적 위치와 관련된 중요한 정보 유형(SITS)을 평가하고 해당 국가 또는 지역에 맞게 보고서를 생성하는 데 사용됩니다. 테넌트에 있는 데이터에 따라 지리적 지역을 선택하십시오.

보고서의 위치 정보를 변경하려면 지리적 위치(-Geo) 입력 매개 변수를 제공해야 합니다. 테넌트에 적용할 수 있는 지리적 위치 중 하나 또는 여러 개를 선택할 수 있습니다.

다음 지침에 따라 특정 위치에 따라 보고서를 실행합니다.

1. PowerShell 열기
2. 특정 지역을 지정하기 위해 아래 표의 국가 또는 지역에 해당하는 숫자를 사용하여 cmdlet을 실행합니다. 여러 번호를 콤보로 구분하여 입력합니다. 예를 들어 아래 cmdlet은 Asia-Pacific 사용자 지정 보고서를 실행합니다.

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | 입력 |  국가 또는 지역 | 
  | :------------- | :------------: |
  | 1 | 아시아 태평양 |
  | 2 | 오스트레일리아 |
  | 3  | 캐나다 |
  | 4  | 유럽(프랑스 제외) /중동/아프리카 |
  | 5 | 프랑스 |
  | 6  | 인도 |
  | 7  | 일본 |
  | 8  | 한국 |
  | 9  | 북미(캐나다 제외) |
  | 10  | 남미 |
  | 11  | 남아프리카 공화국 |
  | 12  | 스위스 |
  | 13 | 아랍에미리트 |
  | 14  | 영국 |


 > [!NOTE]
> 보고서에는 항상 MCCA에서 지원하는 SWIFT 코드, 신용 카드 번호 등의 국제 중요한 정보 유형이 포함됩니다.

#### <a name="role-based-reporting"></a>역할 기반 보고

또한 역할에 따라 보고서가 사용자 지정됩니다.

아래 표에는 보고서의 어떤 섹션에 액세스할 수 있는 역할이 표시됩니다. 아래 표에 나열되지 않은 조직 내의 다른 역할은 도구를 실행하지 못하거나 도구를 실행하여 최종 보고서의 정보에 제한적으로 액세스할 수 있습니다.

![MCCA - 역할.](../media/compliance-manager-mcca-roles.png "MCCA 역할")

예외:
1. 사용자는 "IRM에 IRM 사용" 섹션과 별도로 IP에 대한 보고서를 Exchange Online 없습니다.
2. 사용자는 "IRM을 사용하여 IRM 사용" 섹션과 별도로 IP에 대한 Exchange Online 수 있습니다.
3. 사용자는 "O365에서 통신 규정 준수 사용" 섹션과 별도로 IP에 대한 보고서를 생성할 수 있습니다.
4. 사용자는 "감사에서 감사 사용" 섹션과 별도로 IP에 대한 보고서를 Office 365 없습니다.
5. 사용자는 "감사에서 감사 사용" 섹션과 별도로 IP에 대한 Office 365 수 있습니다.

#### <a name="solutions-summary-section"></a>솔루션 요약 섹션

보고서의 **솔루션 요약** 섹션에서는 규정 준수 관리자에서 조직이 준수 자세를 개선하는 데 도움을 줄 수 있는 개선 작업에 대해 간략하게 설명합니다.

![MCCA - 솔루션 요약.](../media/compliance-manager-mcca-solutions.png "MCCA 솔루션 요약 화면")

MCCA는 준수 관리자의 권장 개선 작업에 대해 현재 구성을 평가합니다. 주의가 필요한 것으로 MCCA 도구에서 식별된 모든 개선 작업이 이 섹션에 나열됩니다.

각 Microsoft 솔루션 옆에는 준수 관리자의 개선 작업에 해당하는 항목 수를 나타내는 색으로 코딩된 상자가 있습니다. 작업은 다음 세 가지 상태로 나됩니다.

- **확인**: 권장 조건을 충족하며 현재 주의가 필요 없는 작업
- **개선** 사항 : 주의가 필요한 작업
- **권장 사항:** 주의가 필요 없지만 모범 사례를 권장하는 작업
 
개선 사항 및 권장 사항을 확인하려면 상자를 선택합니다.

**개선 상태가 있는 항목**

개선 작업 오른쪽의  개선 레이블 옆에 있는 드롭다운을 선택합니다. 현재 설정에 대한 빠른 요약 및 세부 정보 및 권장 개선 작업이 표시됩니다. 요약에는 준수 관리자에 대한 직접 링크, 준수 관리자의 해당 솔루션 및 Microsoft 365 규정 준수 센터 문서가 포함됩니다.

준수 관리자 링크를 클릭하면 아직 구현하지 않은 해당 솔루션 내의 모든 개선 작업을 필터링된 보기로 볼 수 있습니다. 이 지점에서 준수 점수를 높이기 위해 달성할 [](compliance-score-calculation.md)수 있는 포인트 수와 해당 점수가 적용되는 평가, 적용 가능한 규정 및 인증을 볼 수 있습니다.

DLP의 경우 권장되는  정보를 기반으로 미리 생성된 PowerShell 스크립트를 제공하는 재구성 스크립트 단추가 있습니다. PowerShell 콘솔에서 직접 복사하여 붙여넣을 수 있습니다. 테스트 모드에서 DLP 정책을 생성합니다.

**추천 상태가 있는 항목**

개선 작업 오른쪽의  추천 레이블 옆에 있는 드롭다운을 선택합니다. 개선 작업과 관련된 조직의 현재 Microsoft 365 환경과 권장 모범 사례가 요약되어 있습니다.

## <a name="resources"></a>리소스

MCCA 설치, 설정 및 사용에 대한 자세한 내용은 GITHUB(계정이 필요하지 GitHub 없음)의 [README](https://github.com/OfficeDev/MCCA#overview) 지침을 참조하세요.

자세한 내용은 Windows PowerShell PowerShell 설명서를 사용하는 방법을 [참조하세요.](/powershell/scripting/how-to-use-docs) 자세한 내용은 [시작 Windows PowerShell](/powershell/scripting/windows-powershell/starting-windows-powershell)참조합니다.
