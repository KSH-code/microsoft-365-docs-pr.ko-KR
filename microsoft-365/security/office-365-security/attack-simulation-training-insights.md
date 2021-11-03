---
title: Insights 시뮬레이션 교육을 보고합니다.
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 관리자는 Microsoft 365 Defender 포털의 공격 시뮬레이션 교육이 사용자에게 미치는 영향을 알아보고 시뮬레이션 및 교육 결과를 통해 정보를 얻을 수 있습니다.
ms.technology: mdo
ms.openlocfilehash: f101abfb8d7ebd771ab2d02847f9371d35441ae6
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60702687"
---
# <a name="insights-and-reports-for-attack-simulation-training-in-defender-for-office-365"></a>Insights Defender의 공격 시뮬레이션 교육에 대한 Office 365

**Microsoft** [Defender for Office 365 요금제 2에 적용](defender-for-office-365.md)

Microsoft Defender for Office Plan 2 또는 Microsoft 365 E5 시뮬레이션 교육에서 Microsoft는 시뮬레이션 결과 및 해당 교육의 인사이트와 보고서를 제공합니다. 이 정보를 통해 사용자의 위협 준비 진행 상황을 알리고 향후 공격에 대비할 수 있도록 권장되는 다음 단계를 안내할 수 있습니다.

Insights 및 보고서는 Microsoft 365 Defender 포털의 공격 시뮬레이션 교육에서 다음 위치에서 사용할 수 있습니다.

- 개요 **탭**
- 시뮬레이션 탭의 **시뮬레이션 세부 정보입니다.**

이 문서의 나머지에서는 사용 가능한 정보에 대해 설명합니다.

공격 시뮬레이션 교육에 대한 시작 정보는 공격 시뮬레이션 교육 사용 [시작을 참조하세요.](attack-simulation-training-get-started.md)

## <a name="insights-and-reports-on-the-overview-tab-of-attack-simulation-training"></a>Insights 시뮬레이션 교육의 개요 탭에 대한 정보 및 보고서

개요 탭으로  이동하여 에서 Microsoft 365 Defender 포털을 열고 전자 메일 & 공동 작업 공격 시뮬레이션 교육으로 이동한 다음 개요 탭이 선택되어 있는지(기본값) 확인해야 <https://security.microsoft.com/>  \> 합니다.  공격 시뮬레이션 교육 **페이지의 개요** **탭으로** 직접 이동하기 위해 를 <https://security.microsoft.com/attacksimulator?viewid=overview> 사용합니다.

이 섹션의 나머지 부분에서는 공격 시뮬레이션 교육의 개요 탭에서 사용할 수 있는 정보에 대해 설명합니다. 

### <a name="recent-simulations-card"></a>최근 시뮬레이션 카드

개요 **탭의** 최근  시뮬레이션 카드에는 조직에서 만들거나 실행한 마지막 세 가지 시뮬레이션이 표시됩니다.

시뮬레이션을 선택하여 세부 정보를 볼 수 있습니다.

모든 **시뮬레이션 보기를 선택하면** 시뮬레이션 **탭으로 이동됩니다.**

시뮬레이션 **시작을 선택하면** 시뮬레이션 만들기 마법사가 시작됩니다. 자세한 내용은 에 대한 Defender의 피싱 공격 [시뮬레이션을 Office 365.](attack-simulation-training.md)

![Microsoft 365 Defender 포털의 공격 시뮬레이션 교육 개요 탭에 있는 최근 시뮬레이션 카드입니다.](../../media/attack-sim-training-overview-recent-simulations-card.png)

### <a name="behavior-impact-on-compromise-rate-card"></a>손상율 카드에 대한 동작 영향

개요 **탭의** 손상율 카드에 대한 동작 영향은 사용자가 이전 데이터와 비교하여 시뮬레이션에 응답한 Microsoft 365.  이러한 정보를 사용하여 동일한 사용자 그룹에 대해 여러 시뮬레이션을 실행하여 사용자 위협 준비의 진행 상황을 추적할 수 있습니다.

차트 데이터 자체에는 다음 정보가 표시됩니다.

- **예측된** 손상률: 다른 모든 조직에서 동일한 유형의 페이로드를 사용하는 공격 시뮬레이션 교육 시뮬레이션의 평균 손상 <sup>\*</sup> Microsoft 365.
- **실제 손상율:** 시뮬레이션에 대해 <sup>\*</sup> 내렸다는 사용자의 실제 비율입니다.

차트에서 데이터 데이터 포인트를 마우스로 마우스로 대면 실제 백분율 값이 표시됩니다.

카드에 다음과 같은 요약 정보도 표시됩니다.

- **사용자는 피싱에** 덜 노출될 수 있습니다. 시뮬레이션된 공격에 의해 손상된 실제 사용자 수와 예측된 손상율의 차이입니다. 이 사용자 수는 향후 유사한 공격으로 손상될 가능성이 낮습니다.
- **x% better than predicted rate:** 사용자가 예측한 손상률과 대조적으로 어떻게 전반적으로 나타났는가를 나타냅니다.

![웹 포털의 공격 시뮬레이션 교육 개요 탭에서 손상율 카드에 Microsoft 365 Defender 영향을 미치고 있습니다.](../../media/attack-sim-training-overview-behavior-impact-card.png)

더 자세한 보고서를 보려면 시뮬레이션 및 교육 관련 보고서 **보기를 클릭합니다.** 이 보고서는 이 문서 의 [나중에 설명됩니다.](#training-efficacy-tab-for-the-attack-simulation-report)

### <a name="simulation-coverage-card"></a>시뮬레이션 범위 카드

개요  탭의 시뮬레이션  범위 카드는 시뮬레이션을 받은 조직의 사용자 비율(시뮬레이트된 **사용자)** 및 시뮬레이션을 수신하지않은 사용자(시뮬레이션되지 않은 사용자)의 비율을 보여줍니다. 차트의 섹션 위에 마우스를 대면 각 범주의 실제 사용자 수를 볼 수 있습니다.

시뮬레이션되지 **않은** 사용자에 대한 시작 시뮬레이션을 선택하면 시뮬레이션을 받지 않은 사용자가 대상 사용자 페이지에서 자동으로 선택되는 시뮬레이션 만들기 **마법사가** 시작됩니다. 자세한 내용은 에 대한 Defender의 피싱 공격 [시뮬레이션을 Office 365.](attack-simulation-training.md)

시뮬레이션 범위 **보기 보고서를 선택하면** 공격 시뮬레이션 보고서의 사용자 범위 [탭으로 이동됩니다.](#user-coverage-tab-for-the-attack-simulation-report)

![웹 포털의 공격 시뮬레이션 교육 개요 탭에 있는 시뮬레이션 Microsoft 365 Defender 카드입니다.](../../media/attack-sim-training-overview-sim-coverage-card.png)

### <a name="training-completion-card"></a>교육 완료 카드

개요 **탭의** 교육  완료 카드는 시뮬레이션 결과를 기반으로 교육을 받은 사용자의 백분율을 다음 범주로 구성합니다.

- **완료**
- **진행 중**
- **불완전**

차트의 섹션 위에 마우스를 대면 각 범주의 실제 사용자 수를 볼 수 있습니다.

교육 완료 **보고서 보기를** 선택하면 공격 시뮬레이션 보고서의 교육 완료 [탭으로 이동됩니다.](#training-completion-tab-for-the-attack-simulation-report)

### <a name="repeat-offenders-card"></a>반복 오해자 카드

개요 탭의 반복 **가해자** **카드에는** 반복되는 가해자에 대한 정보가 표시됩니다. 반복 _가해자는_ 연속된 시뮬레이션에 의해 손상된 사용자입니다. 연속 시뮬레이션의 기본 수는 2개이지만 의 공격 시뮬레이션  설정 탭에서 값을 변경할 수 <https://security.microsoft.com/attacksimulator?viewid=setting> 있습니다.

이 차트는 반복되는 가해자 데이터를 시뮬레이션 유형별로 [구성합니다.](attack-simulation-training.md#select-a-social-engineering-technique)

- **모두**
- **맬웨어 첨부 파일**
- **맬웨어 링크**
- **자격 증명 수집**
- **첨부 파일 링크**
- **URL 드라이브**

반복되는 **가해자 보고서** 보기를 선택하면 공격 시뮬레이션 보고서에 대한 반복 가해자 [탭으로 이동됩니다.](#repeat-offenders-tab-for-the-attack-simulation-report)

### <a name="recommendations-card"></a>권장 사항 카드

개요 **권장 사항** **카드는** 실행할 다양한 유형의 시뮬레이션을 제안합니다.

시작을 **선택하면** 기술 선택 페이지에서 지정한 시뮬레이션 유형이 자동으로 선택되어 시뮬레이션 만들기 **마법사가 시작됩니다.** 자세한 내용은 에 대한 Defender의 피싱 공격 [시뮬레이션을 Office 365.](attack-simulation-training.md)

![권장 사항 포털의 공격 시뮬레이션 교육 개요 탭에 있는 Microsoft 365 Defender 있습니다.](../../media/attack-sim-training-overview-recommendations-card.png)

### <a name="attack-simulation-report"></a>공격 시뮬레이션 보고서

개요 탭에서  보기...를  클릭하여 공격 시뮬레이션 보고서를 열 **수 있습니다. 이** 문서에 설명된 여러 카드에서 사용할 수 있는 보고서 단추 보고서로 직접 이동하기 위해 다음을 사용 <https://security.microsoft.com/attacksimulationreport>

#### <a name="training-efficacy-tab-for-the-attack-simulation-report"></a>공격 시뮬레이션 보고서 교육 탭

공격 **시뮬레이션 보고서 페이지에서**  교육 검사 탭이 기본적으로 선택되어 있습니다. 이 탭은 손상율 카드에 대한  동작 영향에서 사용할 수 있는 동일한 정보를 시뮬레이션 자체의 추가 컨텍스트와 함께 제공합니다.

![검색 포털의 공격 시뮬레이션 보고서에 있는 Microsoft 365 Defender 탭입니다.](../../media/attack-sim-report-training-efficacy-view.png)

이 차트에는 **예측된 손상률** 및 실제 **손상률이 표시됩니다.** 차트에서 구역 위에 마우스를 대면 실제 백분율 값이 표시됩니다.

차트 아래의 세부 정보 표에는 다음 정보가 표시됩니다.

- **시뮬레이션 이름**
- **시뮬레이션 기술**
- **시뮬레이션 전술**
- **예측된 손상율**
- **실제 손상된 비율**
- **대상이 지정된 총 사용자 수**
- **클릭한 사용자 수**

사용 가능한 열 헤더를 클릭하여 결과를 정렬할 수 있습니다.

열 **사용자 지정을 클릭하여** 표시되는 열을 제거합니다. 완료되면 **적용** 을 클릭합니다.

검색 아이콘 검색 상자를 사용하여 시뮬레이션 이름 또는 시뮬레이션 기술로 ![ ](../../media/m365-cc-sc-search-icon.png)  **결과를 필터링합니다.**  와일드카드는 지원되지 않습니다.

내보내기 ![ 아이콘을 클릭하면 됩니다.](../../media/m365-cc-sc-download-icon.png) **보고서 내보내기** 단추, 보고서 생성 진행률이 완료율로 표시됩니다. 대화 상자가 열리면 파일 파일을 열고 .csv 파일을 저장하고 .csv 기억할 수 있습니다.

#### <a name="user-coverage-tab-for-the-attack-simulation-report"></a>공격 시뮬레이션 보고서의 사용자 범위 탭

![웹 사이트 포털의 공격 시뮬레이션 보고서에 있는 Microsoft 365 Defender 탭입니다.](../../media/attack-sim-report-user-coverage-view.png)

사용자 범위 **탭에서** 차트에는 **시뮬레이트된** 사용자 및 시뮬레이트되지 않은 **사용자가 표시됩니다.** 차트에서 데이터 데이터 지점을 마우스로 마우스로 대면 실제 값이 표시됩니다.

차트 아래의 세부 정보 표에는 다음 정보가 표시됩니다.

- **Username**
- **전자 메일 주소**
- **시뮬레이션에 포함**
- **마지막 시뮬레이션 날짜**
- **마지막 시뮬레이션 결과**
- **클릭한 횟수**
- **손상된 횟수**

사용 가능한 열 헤더를 클릭하여 결과를 정렬할 수 있습니다.

열 **사용자 지정을 클릭하여** 표시되는 열을 제거합니다. 완료되면 **적용** 을 클릭합니다.

검색 아이콘 검색 상자를 사용하여 사용자 이름 또는 전자 메일 주소로 ![ ](../../media/m365-cc-sc-search-icon.png)  결과를 **필터링합니다.**  와일드카드는 지원되지 않습니다.

내보내기 ![ 아이콘을 클릭하면 됩니다.](../../media/m365-cc-sc-download-icon.png) **보고서 내보내기** 단추, 보고서 생성 진행률이 완료율로 표시됩니다. 대화 상자가 열리면 파일 파일을 열고 .csv 파일을 저장하고 .csv 기억할 수 있습니다.

#### <a name="training-completion-tab-for-the-attack-simulation-report"></a>공격 시뮬레이션 보고서에 대한 교육 완료 탭

![검색 포털의 공격 시뮬레이션 보고서에 있는 교육 Microsoft 365 Defender 탭입니다.](../../media/attack-sim-report-training-completion-view.png)

교육 **완료 탭에서** 차트에는 완료, 진행 중 및 불완전한 시뮬레이션 **수가** 표시됩니다. 차트에서 구역 위에 마우스를 대면 실제 값이 표시됩니다.

차트 아래의 세부 정보 표에는 다음 정보가 표시됩니다.

- **Username**
- **전자 메일 주소**
- **시뮬레이션에 포함**
- **마지막 시뮬레이션 날짜**
- **마지막 시뮬레이션 결과**
- **최근 완료된 교육의 이름**
- **완료 날짜**
- **모든 교육**

사용 가능한 열 헤더를 클릭하여 결과를 정렬할 수 있습니다.

열 **사용자 지정을 클릭하여** 표시되는 열을 제거합니다. 완료되면 **적용** 을 클릭합니다.

필터 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-filter-icon.png) **다음** 값 중 하나 이상을 사용하여 차트 및 세부 정보 테이블을 필터링합니다.

- **완료**
- **진행 중**
- **모두**

필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**

검색 아이콘 검색 상자를 사용하여 사용자 이름 또는 전자 메일 주소로 ![ ](../../media/m365-cc-sc-search-icon.png)  결과를 **필터링합니다.**  와일드카드는 지원되지 않습니다.

내보내기 ![ 아이콘을 클릭하면 됩니다.](../../media/m365-cc-sc-download-icon.png) **보고서 내보내기** 단추, 보고서 생성 진행률이 완료율로 표시됩니다. 대화 상자가 열리면 파일 파일을 열고 .csv 파일을 저장하고 .csv 기억할 수 있습니다.

#### <a name="repeat-offenders-tab-for-the-attack-simulation-report"></a>공격 시뮬레이션 보고서에 대한 반복 가해자 탭

![포털의 공격 시뮬레이션 보고서에서 Microsoft 365 Defender 반복합니다.](../../media/attack-sim-report-repeat-offenders-view.png)

반복 _가해자는_ 연속된 시뮬레이션에 의해 손상된 사용자입니다. 연속 시뮬레이션의 기본 수는 2개이지만 의 공격 시뮬레이션  설정 탭에서 값을 변경할 수 <https://security.microsoft.com/attacksimulator?viewid=setting> 있습니다.

반복 **가해자 탭에서** 차트는 반복 가해자 데이터를 시뮬레이션 유형으로 [구성합니다.](attack-simulation-training.md#select-a-social-engineering-technique)

- **모두**
- **자격 증명 수집**
- **맬웨어 첨부 파일**
- **첨부 파일 링크**
- **맬웨어 링크**
- **URL 드라이브**

차트에서 데이터 데이터 지점을 마우스로 마우스로 대면 실제 값이 표시됩니다.

차트 아래의 세부 정보 표에는 다음 정보가 표시됩니다.

- **사용자**
- **반복 횟수**
- **시뮬레이션 형식**
- **시뮬레이션**

사용 가능한 열 헤더를 클릭하여 결과를 정렬할 수 있습니다.

열 **사용자 지정을 클릭하여** 표시되는 열을 제거합니다. 완료되면 **적용** 을 클릭합니다.

필터 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-filter-icon.png) **필터링하여** 시뮬레이션 형식 값의 일부 또는 전체를 사용하여 차트 및 세부 정보 테이블을 필터링합니다.

- **자격 증명 수집**
- **맬웨어 첨부 파일**
- **첨부 파일 링크**
- **맬웨어 링크**
- **URL 드라이브**

필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**

검색 아이콘 검색 상자를 사용하여 열 값으로 ![ ](../../media/m365-cc-sc-search-icon.png)  결과를 필터링합니다. 와일드카드는 지원되지 않습니다.

내보내기 ![ 아이콘을 클릭하면 됩니다.](../../media/m365-cc-sc-download-icon.png) **보고서 내보내기** 단추, 보고서 생성 진행률이 완료율로 표시됩니다. 대화 상자가 열리면 파일 파일을 열고 .csv 파일을 저장하고 .csv 기억할 수 있습니다.

## <a name="insights-and-reports-in-the-simulation-details-of-attack-simulation-training"></a>Insights 시뮬레이션 교육의 시뮬레이션 세부 정보 및 보고서

시뮬레이션 **탭으로** 이동하려면 에서 Microsoft 365 Defender 포털을 열고 전자 메일 & 공동 작업 공격 시뮬레이션 교육으로 이동한 다음 시뮬레이션 <https://security.microsoft.com/>  \>  **탭을** 클릭합니다. 공격 시뮬레이션 교육 페이지의 **시뮬레이션** 탭으로 직접 이동하기 **위해** 를 <https://security.microsoft.com/attacksimulator?viewid=simulations> 사용합니다.

목록에서 시뮬레이션을 선택하면 세부 정보 페이지가 열립니다. 이 페이지에는 예상한 시뮬레이션의 구성 설정(상태, 시작 날짜, 사용된 페이로드 등)이 포함되어 있습니다.

이 섹션의 나머지 부분에서는 시뮬레이션 세부 정보 페이지에서 사용할 수 있는 인사이트 및 보고서에 대해 설명합니다.

### <a name="simulation-impact-section"></a>시뮬레이션 영향 섹션

시뮬레이션 **세부 정보** 페이지의 시뮬레이션 영향 섹션에는 시뮬레이션에 의해 완전히 속인 사용자 수와 시뮬레이션의 총 사용자 수가 표시됩니다. 표시되는 정보는 시뮬레이션 유형에 따라 다릅니다. 예제:

- 링크: **자격 증명을 입력하고** **자격 증명을 입력하지 않은 경우.**

  ![링크 관련 시뮬레이션 세부 정보를 위한 시뮬레이션 영향 섹션입니다.](../../media/attack-sim-training-sim-details-sim-impact-links.png)

- 첨부 파일: **첨부 파일을 열고** **첨부 파일을 열지 않습니다.**

  ![첨부 파일 관련 시뮬레이션 세부 정보를 위한 시뮬레이션 영향 섹션입니다.](../../media/attack-sim-training-sim-details-sim-impact-attachments.png)

차트에서 구역 위에 마우스를 대면 각 범주의 실제 숫자가 표시됩니다.

### <a name="all-user-activity-section"></a>모든 사용자 활동 섹션

시뮬레이션 **세부 정보 페이지의** 모든 사용자 활동 섹션에는 시뮬레이션 결과의 가능한 숫자가 표시됩니다. 표시되는 정보는 시뮬레이션 유형에 따라 다릅니다. 예제:

- **SuccessfullyDeliveredEmail**
- **ReportedEmail:** 시뮬레이션 메시지를 의심스러운 것으로 보고한 사용자 수입니다.
- 링크:
  - **EmailLinkClicked**: 시뮬레이션 메시지에서 링크를 클릭한 사용자 수입니다.
  - **CredSupplied**: 링크를 클릭한 후 자격 증명을 제공한 사용자 수입니다.

    ![링크 관련 시뮬레이션 세부 정보를 위한 모든 사용자 활동 섹션입니다.](../../media/attack-sim-training-sim-details-all-user-activity-links.png)

- 첨부 파일:
  - **AttachmentOpened:** 시뮬레이션 메시지에서 첨부 파일을 연 사용자 수입니다.

    ![첨부 파일 관련 시뮬레이션 세부 정보의 모든 사용자 활동 섹션](../../media/attack-sim-training-sim-details-all-user-activity-attachments.png)

### <a name="training-completion-section"></a>교육 완료 섹션

시뮬레이션 **세부 정보** 페이지의 교육 완료 섹션에는 시뮬레이션에 필요한 교육과 교육을 완료한 사용자의 수가 표시됩니다.

![첨부 파일 관련 시뮬레이션 세부 정보를 위한 교육 완료 섹션](../../media/attack-sim-training-sim-details-training-completed.png)

## <a name="recommended-actions-section"></a>권장 작업 섹션

시뮬레이션 **세부 정보** 페이지의 권장 작업 섹션에는 [Microsoft 보안](../defender/microsoft-secure-score.md) 점수의 권장 작업과 작업의 보안 점수에 대한 영향이 표시됩니다. 이러한 권장 사항은 시뮬레이션에 사용된 페이로드를 기반으로 하여 사용자와 환경을 보호하는 데 도움이 됩니다. 목록에서 **개선** 작업을 선택하면 제안된 작업을 구현할 수 있는 위치로 이동됩니다.

![공격 시뮬레이션 교육에 대한 권장 작업 섹션](../../media/attack-sim-training-sim-details-recommended-actions.png)

## <a name="related-links"></a>관련 링크

[공격의 신나는 교육 사용 시작](attack-simulation-training-get-started.md)

[피싱 공격 시뮬레이션 만들기](attack-simulation-training.md)

[사용자 교육을 위한 페이로드 만들기](attack-simulation-training-payloads.md)
