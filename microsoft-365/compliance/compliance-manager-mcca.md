---
title: 준수 관리자를 위한 Microsoft 준수 구성 분석기
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 준수 구성 분석기를 사용 하 여 Microsoft 준수 관리자를 통해 신속 하 게 시작 하 고 실행 하는 방법을 이해 합니다.
ms.openlocfilehash: 1f7d987262a7d390cb9efe2162ae9be9f56c8757
ms.sourcegitcommit: d333d82fd5e4f3265e8b9372094e85875bee6fe5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49072007"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager"></a>준수 관리자를 위한 Microsoft 준수 구성 분석기

**이 문서의 내용** Microsoft 규정 준수 구성 분석기 도구를 설치 하 고 실행 하는 방법에 대해 알아봅니다.

## <a name="microsoft-compliance-configuration-analyzer-mcca-overview"></a>MCCA (Microsoft 준수 구성 분석기) 개요

Microsoft 규정 준수 구성 분석기 (MCCA)는 [Microsoft 준수 관리자](compliance-manager.md)를 시작 하는 데 도움이 되는 도구입니다. MCCA는 조직의 현재 구성을 페치하고 Microsoft 365 권장 모범 사례에 따라 유효성을 검사 하는 PowerShell 기반 유틸리티입니다. 이러한 모범 사례는 데이터 보호 및 데이터 관리를 위한 주요 규정 및 표준을 포함 하는 컨트롤 집합을 기반으로 합니다.

MCCA를 통해 준수 관리자의 현재 Microsoft 365 환경에 적용 되는 개선 조치를 빠르게 확인할 수 있습니다. MCCA로 식별 되는 각 작업은 준수 관리자에 대 한 직접 링크 및 정정 작업 수행을 시작할 수 있는 적절 한 솔루션을 포함 하 여 구현에 대 한 권장 사항을 제공 합니다.

MCCA를 이해 하는 데 사용할 수 있는 추가 리소스는 [GitHub의 추가 정보를 참조](https://github.com/OfficeDev/MCCA#overview)하세요. 이 페이지에서는 필수 구성 요소에 대 한 자세한 정보를 제공 하 고 전체 설치 방법을 설명 합니다. 이 페이지에 액세스 하려면 GitHub 계정이 필요 하지 않습니다.

## <a name="install-mcca-and-run-a-report"></a>MCCA 설치 및 보고서 실행

Windows PowerShell을 사용 하 여 MCCA 도구를 설치할 수 있습니다. 이 도구를 다운로드 하 고 설치한 후에는 이러한 단계를 반복 하 여 보고서를 실행할 필요가 없습니다. MCCA를 열 때마다 로그인 자격 증명을 묻는 메시지가 표시 되 고 업데이트 된 새 보고서가 생성 됩니다.

#### <a name="step-1-install-windows-powershell"></a>1 단계: Windows PowerShell 설치
시작 하려면 PowerShell 갤러리에서 사용할 수 있는 Exchange Online PowerShell 모듈 (v 2.0.3 이상)이 필요 합니다. [설치 지침을 가져옵니다](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).

#### <a name="step-2-install-mcca"></a>2 단계: MCCA 설치

MCCA를 설치 하려면 관리자 모드에서 PowerShell을 사용 하 여 시작 합니다. 아래 단계를 수행 합니다.

1. Windows **시작** 단추를 선택 합니다.
2. **Powershell** 을 입력 하 고 **Windows powershell** 을 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행** 을 선택 합니다.
1. 명령 프롬프트에 다음을 입력합니다.

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a>3 단계: 보고서 실행

MCCA를 설치한 후에는 MCCA를 실행 하 고 보고서를 생성할 수 있습니다. 보고서를 실행 하려면

1. PowerShell 열기
2. Cmdlet을 실행 합니다.

    ```powershell
    Get-MCCAReport
    ```
3. MCCA가 실행 되 면 초기 버전 확인을 수행 하 고 자격 증명을 요청 합니다. 사용자 이름 입력 프롬프트에서 Microsoft 365 계정 전자 메일 주소로 로그인 합니다 ([보고서를 만들 수 있는 역할 보기](#role-based-reporting)). 암호를 입력 하 라는 메시지가 표시 됩니다.

보고서를 생성 하는 데 약 2-5 분 정도 소요 됩니다. 작업이 완료 되 면 브라우저 창이 열리고 HTML 보고서가 표시 됩니다. 이 도구를 실행할 때마다 자격 증명을 묻는 메시지가 표시 되 고 새 보고서가 생성 됩니다. 이 보고서는 다음 디렉터리에 로컬로 저장 됩니다.

C:\Users \<username> \AppData\Local\Microsoft\MCCA. 

이 디렉터리에서 이전에 생성 된 보고서에 액세스할 수 있습니다.

## <a name="understanding-your-report"></a>보고서 이해

보고서가 생성 된 날짜 및 시간을 기준으로 데이터를 반영 합니다. 맨 위 섹션에는 생성 된 시기, 조직 이름 및 테 넌 트 ID에 대 한 세부 정보가 제공 됩니다.

#### <a name="geolocation-based-reporting"></a>지리적 위치 기반 보고

**메모** 섹션에는 테 넌 트의 지리적 위치에 따라 보고서가 사용자 지정 된 것으로 표시 됩니다. 이 도구에 나열 된 권장 사항은 해당 국가나 지역에 따라 다릅니다.

지리적 위치 선택은 해당 지리적 위치와 관련 된 중요 한 정보 유형 (현재 위치)을 평가 하 고 해당 국가나 지역에 맞는 보고서를 생성 하는 데 사용 됩니다. 테 넌 트에 있는 데이터를 기반으로 geolocations를 선택 합니다.

보고서의 위치 정보를 변경 하려면 location (-Geo) 입력 매개 변수를 제공 해야 합니다. 테 넌 트에 적용 가능한 geolocations를 하나 또는 여러 개 선택할 수 있습니다.

다음 지침에 따라 특정 위치에 따라 보고서를 실행 합니다.

1. PowerShell 열기
2. 특정 지역을 지정 하려면 아래 표에서 해당 국가 또는 지역에 해당 하는 번호를 사용 하 여 cmdlet을 실행 합니다. 여러 숫자를 쉼표로 구분 하 여 입력 합니다. 예를 들어 아래 cmdlet은 Asia-Pacific 및 일본에 대해 사용자 지정 된 보고서를 실행 합니다.

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | 입력 |  국가 또는 지역 | 
  | :------------- | :------------: |
  | 1  | 아시아 태평양 |
  | 2  | 오스트레일리아 |
  | 3(sp3) | 캐나다 |
  | 4  | 유럽 (프랑스 제외)/중동/아프리카 |
  | 5  | 프랑스 |
  | 6  | 인도 |
  | 7  | 일본 |
  | 8  | 한국 |
  | 9  | 북미 (캐나다 제외) |
  | 10  | 남미 |
  | 11  | 남아프리카 공화국 |
  | 12  | 스위스 |
  | 13  | 아랍에미리트 |
  | 14  | 영국 |


 > [!NOTE]
> 보고서에는 항상 SWIFT code, 신용 카드 번호 등의 MCCA에서 지 원하는 국제 중요 한 정보 유형이 포함 됩니다.

#### <a name="role-based-reporting"></a>역할 기반 보고

사용자의 역할에 따라 보고서도 사용자 지정 됩니다.

아래 표에는 보고서의 각 섹션에 대 한 액세스 권한이 있는 역할이 나와 있습니다. 조직 내의 다른 역할 (아래 표에 나열 되지 않음)은 도구를 실행 하지 못할 수도 있고, 도구를 실행 하 여 최종 보고서의 정보에 대 한 제한 된 액세스를 수행할 수도 있습니다.

![MCCA-역할](../media/compliance-manager-mcca-roles.png "MCCA 역할")

예외
1. 사용자가 "Exchange Online에 IRM 사용" 섹션에서 IP에 대 한 보고서를 생성할 수 없습니다.
2. 사용자가 "Exchange Online에 IRM 사용" 섹션에서 IP에 대 한 보고서를 생성할 수 있습니다.
3. 사용자는 "O365에서 통신 준수 기능 설정" 섹션에서 IP를 사용할 수 있는 보고서를 생성할 수도 있습니다.
4. 사용자는 "Office 365에서 감사 기능 설정" 섹션에서 IP를 사용 하지 않도록 보고서를 생성할 수 없습니다.
5. 사용자가 "Office 365의 감사 사용" 섹션에서 IP에 대 한 보고서를 생성할 수 있습니다.

#### <a name="solutions-summary-section"></a>솔루션 요약 섹션

보고서의 **솔루션 요약** 섹션에서는 조직이 준수 관리자에 게 준수 상태를 향상 시키는 데 사용할 수 있는 개선 작업에 대 한 개요를 제공 합니다.

![MCCA-솔루션 요약](../media/compliance-manager-mcca-solutions.png "MCCA 솔루션 요약 화면")

MCCA는 준수 관리자의 권장 향상 작업과 비교 하 여 현재 구성을 평가 합니다. 이 섹션에서는 MCCA 도구로 식별 되는 모든 개선 작업을 주의가 필요한 것으로 나열 합니다.

각 Microsoft 솔루션 옆에는 준수 관리자의 향상 작업에 해당 하는 항목 수를 나타내는 색으로 구분 된 입력란이 있습니다. 이 작업은 다음과 같은 세 가지 상태 상태로 나누어집니다.

- **정상** : 권장 조건을 충족 하며 지금은 주의 하지 않아도 되는 작업
- **개선** : 주의가 필요한 작업
- **권장 사항** : 주의가 필요 하지 않지만 모범 사례를 제안 하는 작업
 
향상 된 기능 및 권장 사항을 보려면 상자를 선택 합니다.

**개선 상태인 항목**

개선 작업의 오른쪽에 있는 **개선** 레이블 옆의 드롭다운을 선택 합니다. 현재 설정 및 권장 되는 개선 작업에 대 한 간략 한 요약 및 세부 정보가 표시 됩니다. 이 요약에는 준수 관리자, Microsoft 365 준수 센터의 해당 솔루션 및 관련 설명서에 대 한 직접 링크가 포함 되어 있습니다.

준수 관리자 링크를 클릭 하면 아직 구현 되지 않은 솔루션 내의 모든 개선 작업에 대 한 필터링 된 보기로 이동 합니다. 여기에서 [준수 점수](compliance-score-calculation.md)를 높이는 데 사용할 수 있는 점 수와 해당 규정 및 인증에 대 한 평가를 확인할 수 있습니다.

DLP에는 권장 사항에 따라 미리 생성 된 PowerShell 스크립트를 제공 하는 **수정 스크립트** 단추가 있습니다. PowerShell 콘솔에서 직접 복사 하 여 붙여 넣을 수 있습니다. 테스트 모드에서 DLP 정책을 만듭니다.

**추천 상태가 포함 된 항목**

개선 작업 오른쪽에 있는 **추천** 레이블 옆의 드롭다운을 선택 합니다. 개선 작업과 관련 된 조직의 현재 Microsoft 365 환경에 대 한 요약 정보와 권장 모범 사례를 확인할 수 있습니다.

## <a name="resources"></a>리소스

MCCA를 설치, 설정 및 사용 하는 방법에 대 한 자세한 내용은 GitHub (GitHub 계정 필요 없음) [의 README 지침](https://github.com/OfficeDev/MCCA#overview) 을 참조 하십시오.

Windows PowerShell에 대 한 자세한 내용을 보려면 [PowerShell 설명서 사용 방법을](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7)시작 하십시오. [Windows PowerShell 시작](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7)도 참조 하세요.
