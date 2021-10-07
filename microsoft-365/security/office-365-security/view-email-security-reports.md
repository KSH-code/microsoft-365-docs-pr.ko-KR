---
title: 전자 메일 보안 보고서 보기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: 관리자는 전자 메일 포털에서 사용할 수 있는 전자 메일 보안 보고서를 찾아 Microsoft 365 Defender 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 33bc93dba189a571779f2cd36fe3b295ed3acc2a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211948"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a>전자 메일 포털에서 전자 메일 Microsoft 365 Defender 보기

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

의 Microsoft 365 Defender 포털에서 다양한 보고서를 사용하여 스팸 방지, 맬웨어 방지 및 암호화 기능과 같은 전자 메일 보안 기능이 Microsoft 365 보호하는 방법을 볼 <https://security.microsoft.com> 수 있습니다. 필요한 사용 권한이 [있는](#what-permissions-are-needed-to-view-these-reports)경우 이 문서에 설명된 바와 같이 이러한 보고서를 보고 다운로드할 수 있습니다.

> [!NOTE]
>
> Email & **공동** 작업 보고서 페이지의 일부 보고서에는 Microsoft Defender가 Office 365. 이러한 보고서에 대한 자세한 내용은 view [Defender for Office 365 reports in the Microsoft 365 Defender 참조하세요.](view-reports-for-mdo.md)
>
> 메일 흐름과 관련된 보고서는 이제 EAC(Exchange 관리 센터)에 있습니다. 이러한 보고서에 대한 자세한 내용은 새 Exchange 관리 센터의 [메일 흐름 보고서를 참조하세요.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)

## <a name="compromised-users-report"></a>손상된 사용자 보고서

> [!NOTE]
> 이 보고서는 사서함이 있는 Microsoft 365 조직에서 Exchange Online 있습니다. 독립 실행형 EOP(독립 실행형 Exchange Online Protection 조직에서는 사용할 수 없습니다.

손상된 **사용자 보고서에는** 지난 7일 이내에  의심 또는 제한으로  표시된 사용자 계정 수가 표시됩니다. 이러한 상태 중 하나에 있는 계정이 문제가 발생하거나 손상될 수도 있습니다. 자주 사용하는 경우 보고서를 사용하여 의심스러우거나 제한된 계정에서 스파이크 및 추세를 파악할 수 있습니다. 손상된 사용자에 대한 자세한 내용은 손상된 전자 메일 계정에 응답을 [참조하세요.](responding-to-a-compromised-email-account.md)

![전자 메일 및 공동 작업 보고서 페이지의 & 위젯](../../media/compromised-users-report-widget.png)

집계 보기는 지난 90일간의 데이터를 표시하고 세부 정보 보기에는 지난 30일간의 데이터가 표시됩니다.

Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자  메일 & 공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.** 전자 메일 & **공동** 작업 보고서 페이지에서 손상된 사용자를 **찾은** 다음 세부 정보 **보기를 클릭합니다.** 보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/reports/CompromisedUsers> 습니다.

손상된 **사용자 페이지의** 차트에는 지정된 날짜 범위에 대한 다음 정보가 표시됩니다.

- **제한:** 사용자 계정은 의심스러운 패턴으로 인해 전자 메일을 보내지 못하도록 제한되어 있습니다.
- **의심스러운**: 사용자 계정이 의심스러운 전자 메일을 보냈고 전자 메일을 보내지 못하도록 제한될 위험이 있습니다.

그래프 아래의 세부 정보 표에는 다음 정보가 표시됩니다.

- **만들기 시간**
- **사용자 ID**
- **작업**

필터를 클릭하고 플라이아웃에 나타나는 다음  값 중 하나 이상을 선택하여 차트와 세부 정보 테이블을 필터링할 수 있습니다.

- **날짜(UTC)**: **시작 날짜 및** 종료 **날짜입니다.**
- **활동:** **제한 또는** **의심스러운 활동**

필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**

주 보고서 페이지에서 일정 ![ 만들기 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **[일정 만들기](#schedule-report)**, ![ 보고서 요청 아이콘.](../../media/m365-cc-sc-download-icon.png) **[보고서 요청](#request-report)** 및 ![ 내보내기 아이콘.](../../media/m365-cc-sc-download-icon.png) **[내보내기](#export-report)** 단추를 사용할 수 있습니다.

![손상된 사용자 보고서의 보고서 보기](../../media/compromised-users-report-activity-view.png)

## <a name="exchange-transport-rule-report"></a>Exchange 전송 규칙 보고서

Exchange **전송** 규칙 보고서는 조직에서 들어오고 오는 메시지에 대한 메일 흐름 규칙(전송 규칙)의 영향을 보여줍니다.

Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자  메일 & 공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.** 전자 메일 **& 공동** 작업 보고서 페이지에서 Exchange 전송 규칙을 찾은 다음 세부 정보 **보기를** **클릭합니다.** 보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/reports/ETRRuleReport> 습니다.

![Exchange 공동 작업 보고서 페이지의 전자 메일 & 규칙 위젯을 선택합니다.](../../media/transport-rule-report-widget.png)

전송 **Exchange** 보고서 페이지에서 사용 가능한 차트 및 데이터는 다음 섹션에 설명되어 있습니다.

### <a name="chart-breakdown-by-direction"></a>방향별 차트 분석

![전송 규칙 Exchange 전송 규칙에 대한 Exchange 보기입니다.](../../media/transport-rule-report-etr-direction-view.png)

방향별 **차트 분석 을 선택하면** 다음 차트를 사용할 수 있습니다.

- **전송 규칙 Exchange** 데이터 보기: 메일  흐름 규칙의 영향을 받은 인바운드 및 아웃바운드 메시지 수입니다. 
- **DLP 전송 규칙 Exchange** 데이터 보기: DLP(데이터  손실 방지) 메일 흐름 규칙의 영향을 받은 인바운드 및 아웃바운드 메시지 수입니다. 

그래프 아래의 세부 정보 표에는 다음 정보가 나와 있습니다.

- **날짜**
- **DLP 정책(DLP** 정책으로 데이터 **Exchange 전송 규칙만** 해당)
- **전송 규칙**
- **제목**
- **보낸 사람 주소**
- **받는 사람 주소**
- **심각도**
- **방향**

필터를 클릭하고 플라이아웃에 나타나는 다음  값 중 하나 이상을 선택하여 차트와 세부 정보 테이블을 필터링할 수 있습니다.

- **날짜(UTC)** **시작 날짜 및** 종료 **날짜입니다.**
- **방향**: **아웃바운드 및** **인바운드**.
- **심각도:** **높은 심각도,** **보통 심각도** 및 **낮은 심각도**

필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**

주 보고서 페이지에서 일정 ![ 만들기 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **[일정 만들기](#schedule-report)**, ![ 보고서 요청 아이콘.](../../media/m365-cc-sc-download-icon.png) **[보고서 요청](#request-report)** 및 ![ 내보내기 아이콘.](../../media/m365-cc-sc-download-icon.png) **[내보내기](#export-report)** 단추를 사용할 수 있습니다.

### <a name="chart-breakdown-by-severity"></a>심각도별 차트 분석

![전송 규칙 보고서의 Exchange 전송 규칙에 대한 Exchange 보기입니다.](../../media/transport-rule-report-etr-severity-view.png)

심각도별 차트 분석 **을** 선택하면 다음 차트를 사용할 수 있습니다.

- **전송 규칙 Exchange** 보기: 높은 심각도, 중간 심각도 및 낮은 심각도 메시지  **수입니다.** 심각도 수준을 규칙의 작업으로 설정할 수 있습니다(**심각도** 수준 또는 _SetAuditSeverity로_ 이 규칙 감사). 자세한 내용은 에서 [메일 흐름 규칙 작업을 Exchange Online.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- **DLP** 전송 규칙 Exchange 데이터 보기: DLP 메일 흐름 규칙의 영향을  받은 높은 심각도, 보통 심각도 및 낮은 심각도 메시지의 수입니다.

그래프 아래의 세부 정보 표에는 다음 정보가 나와 있습니다.

- **날짜**
- **DLP 정책(DLP** 정책으로 데이터 **Exchange 전송 규칙만** 해당)
- **전송 규칙**
- **제목**
- **보낸 사람 주소**
- **받는 사람 주소**
- **심각도**
- **방향**

필터를 클릭하고 플라이아웃에 나타나는 다음  값 중 하나 이상을 선택하여 차트와 세부 정보 테이블을 필터링할 수 있습니다.

- **날짜(UTC)** **시작 날짜 및** 종료 **날짜**
- **방향:** **아웃바운드** 및 **인바운드**
- **심각도:** **높은 심각도,** **보통 심각도** 및 **낮은 심각도**

필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**

주 보고서 페이지에서 일정 ![ 만들기 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **[일정 만들기](#schedule-report)**, ![ 보고서 요청 아이콘.](../../media/m365-cc-sc-download-icon.png) **[보고서 요청](#request-report)** 및 ![ 내보내기 아이콘.](../../media/m365-cc-sc-download-icon.png) **[내보내기](#export-report)** 단추를 사용할 수 있습니다.

## <a name="forwarding-report"></a>전달 보고서

> [!NOTE]
> 이제 EAC에서 이 보고서를 사용할 수 있습니다. 자세한 내용은 새 EAC의 자동 전달된 메시지 [보고서를 참조하세요.](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)

## <a name="mailflow-status-report"></a>메일 흐름 상태 보고서

**메일 흐름** 상태 보고서는 수신 및 보낸 전자 메일, 스팸 검색, 맬웨어, "양호"로 식별된 전자 메일 및 에지에서 허용되거나 차단된 전자 메일에 대한 정보를 표시하는 스마트 보고서입니다. 이 보고서는 에지 보호 정보를 포함하는 유일한 보고서로, EOP(에지 보호)의 평가를 위해 서비스에 허용되기 전에 차단되는 전자 메일의 Exchange Online Protection 표시됩니다. 받는 사람 5명에게 메시지가 전송된 경우 하나의 메시지가 아니라 5개의 다른 메시지로 계산됩니다.

Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자  메일 & 공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.** 전자 메일 & **공동** 작업 보고서 페이지에서 메일 흐름 상태 요약을 **찾은** 다음 세부 정보 **보기를 클릭합니다.** 보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/reports/mailflowStatusReport> 습니다.

![메일 흐름 상태 요약 위젯의 전자 메일 & 공동 작업 보고서 페이지에서 확인할 수 있습니다.](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a>메일 흐름 상태 보고서의 형식 보기

![메일 흐름 상태 보고서에 보기를 입력합니다.](../../media/mail-flow-status-report-type-view.png)

메일 흐름 **상태 보고서** 페이지에서  유형 탭이 기본적으로 선택되어 있습니다. 이 차트에는 지정된 날짜 범위에 대한 다음 정보가 표시됩니다.

- **좋은 메일**
- **합계**
- **맬웨어**
- **피싱 전자 메일**
- **스팸**
- **에지 보호**
- **규칙 메시지**

그래프 아래의 세부 정보 표에는 다음 정보가 표시됩니다.

- **방향**
- **유형**
- **24시간**
- **3일**
- **7일**
- **15일**
- **30일**

필터를 클릭하고 플라이아웃에 나타나는 다음  값 중 하나 이상을 선택하여 차트와 세부 정보 테이블을 필터링할 수 있습니다.

- **날짜(UTC)**: **시작 날짜 및** 종료 **날짜입니다.**
- **메일 방향:** **인바운드 및** **아웃바운드**.
- **유형:**
  - **좋은 메일**
  - **맬웨어**
  - **스팸**
  - **에지 보호**
  - **규칙 메시지**
  - **피싱 전자 메일**

필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**

주 보고서 페이지로 돌아가서 자세한 내용을 보려면 범주 선택을 클릭하면 다음 값에서 선택할 수 있습니다.

- **피싱 전자 메일:** 이 선택을 통해 위협 방지 상태 [보고서로 전송됩니다.](view-email-security-reports.md#threat-protection-status-report)
- **전자 메일의** 맬웨어: 이 선택을 통해 위협 방지 상태 [보고서로 전송됩니다.](view-email-security-reports.md#threat-protection-status-report)
- **스팸 검색:** 이 선택을 통해 스팸 검색 [보고서로 전송됩니다.](view-email-security-reports.md#spam-detections-report)
- **Edge 차단 스팸:** 이 선택을 통해 스팸 검색 [보고서로 전송됩니다.](view-email-security-reports.md#spam-detections-report)

주 보고서 페이지에서 일정 ![ 만들기 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **[일정 만들기](#schedule-report)** 및 ![ 내보내기 아이콘](../../media/m365-cc-sc-download-icon.png) **[내보내기](#export-report)** 단추를 사용할 수 있습니다.

### <a name="direction-view-for-the-mailflow-status-report"></a>메일 흐름 상태 보고서의 방향 보기

![메일 흐름 상태 보고서의 방향 보기입니다.](../../media/mail-flow-status-report-direction-view.png)

방향 탭을 **클릭하면** 차트에 지정된 날짜 범위에 대한 다음 정보가 표시됩니다.

- **인바운드**
- **아웃바운드**

필터를 클릭하고 플라이아웃에 나타나는 다음  값 중 하나 이상을 선택하여 차트와 세부 정보 테이블을 필터링할 수 있습니다.

- **날짜(UTC)**: **시작 날짜 및** 종료 **날짜입니다.**
- **메일 방향:** **인바운드 및** **아웃바운드**.
- **유형:**
  - **좋은 메일**
  - **맬웨어**
  - **스팸**
  - **에지 보호**
  - **규칙 메시지**
  - **피싱 전자 메일**

필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**

주 보고서 페이지로 돌아가서 자세한 내용을 보려면 범주 선택을 클릭하면 다음 값에서 선택할 수 있습니다.

- **피싱 전자 메일:** 이 선택을 통해 위협 방지 상태 [보고서로 전송됩니다.](view-email-security-reports.md#threat-protection-status-report)
- **전자 메일의** 맬웨어: 이 선택을 통해 위협 방지 상태 [보고서로 전송됩니다.](view-email-security-reports.md#threat-protection-status-report)
- **스팸 검색:** 이 선택을 통해 스팸 검색 [보고서로 전송됩니다.](view-email-security-reports.md#spam-detections-report)
- **Edge 차단 스팸:** 이 선택을 통해 스팸 검색 [보고서로 전송됩니다.](view-email-security-reports.md#spam-detections-report)

주 보고서 페이지에서 일정 ![ 만들기 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **일정 만들기** 및 ![ 내보내기 아이콘](../../media/m365-cc-sc-download-icon.png) **내보내기** 단추를 사용할 수 있습니다.

### <a name="mailflow-view-for-the-mailflow-status-report"></a>메일 흐름 상태 보고서의 메일 흐름 보기

메일 **흐름 보기는** Microsoft의 전자 메일 위협 방지 기능이 조직에서 받는 전자 메일과 보낸 전자 메일을 필터링하는 방법을 보여줍니다. 이 보기는 가로 흐름 _다이어그램(Sankey_ 다이어그램)을 사용하여 전체 전자 메일 수에 대한 세부 정보를 제공하고 Edge 보호, 맬웨어 방지, 피싱 방지, 스팸 방지 및 스푸핑 방지를 비롯한 구성된 위협 방지 기능이 이 수에 미치는 영향을 제공합니다.

![메일 흐름 상태 보고서의 메일 흐름 보기입니다.](../../media/mail-flow-status-report-mailflow-view.png)

집계 보기 및 세부 정보 테이블 보기에서는 90일 동안 필터링할 수 있습니다.

다이어그램의 정보는 **EOP** 또는 **Defender에서** 코드한 색으로 Office 365 기술입니다.

다이어그램은 다음과 같은 가로 밴드로 구성됩니다.

- **총 전자 메일** 밴드: 이 값은 항상 먼저 표시됩니다.
- **Edge 블록** 및 **처리된 밴드:**
  - **Edge 블록:** 에지에서 필터링되어 Edge 보호로 식별되는 메시지입니다.
  - **처리된** 메시지: 필터링 스택에서 처리되는 메시지입니다.
- 결과 밴드:
  - **규칙 블록:** 메일 흐름 규칙(전송 규칙)Exchange 처리되는 메시지입니다.
  - **맬웨어** 차단: 다양한 필터로 맬웨어로 식별된 메시지입니다.<sup>\*</sup>
  - **피싱 차단:** 다양한 필터에 의해 처리되는 동안 피싱으로 식별된 메시지입니다.<sup>\*</sup>
  - **스팸 차단:** 다양한 필터에 의해 처리되는 동안 스팸으로 식별된 메시지입니다.<sup>\*</sup>
  - **가장 차단**: Defender에서 사용자 가장 또는 도메인 가장으로 검색된 메시지는 Office 365.<sup>\*</sup>
  - **검색** 차단: 파일 또는 URL을 검색하는 동안 첨부 파일 정책 또는 금고 Defender의 금고 링크 정책에 의해 검색된 Office 365.<sup>\*</sup>
  - **ZAP 제거됨**: ZAP(제로 아워 자동 삭제)에 의해 제거된 메시지입니다.<sup>\*</sup>
  - **배달된** 메시지: 허용으로 인해 사용자에게 배달된 메시지입니다.<sup>\*</sup>

다이어그램에서 가로 밴드 위에 마우스를 놓면 관련 메시지 수가 표시됩니다.

<sup>\*</sup> 이 요소를 클릭하면 다이어그램이 확장되어 세부 정보가 표시됩니다. 확장된 노드의 각 요소에 대한 설명은 [검색 기술을 참조하세요.](/office/office-365-management-api/office-365-management-activity-api-schema#detection-technologies)

![메일 흐름 상태 보고서의 메일 흐름 보기에 있는 피싱 차단 세부 정보](../../media/mail-flow-status-report-mailflow-view-details.png)

다이어그램 아래의 세부 정보 표에는 다음 정보가 표시됩니다.

- **날짜**
- **총 전자 메일**
- **Edge 필터링**
- **규칙 메시지**
- **맬웨어 방지 엔진, 금고 첨부 파일, 필터링된 규칙**
- **DMARC 가장, 스푸핑, 피싱 필터링**
- **검색**
- **스팸 방지 필터링**
- **ZAP 제거됨**
- **위협이 검색되지 않은 메시지**

세부 정보 표에서 행을 선택하면 세부 정보 플라이아웃이 표시되는 세부 정보 플라이아웃에 전자 메일 수의 세부 정보 분석이 표시됩니다.

필터를 클릭하고 플라이아웃에 나타나는 다음  값 중 하나 이상을 선택하여 차트와 세부 정보 테이블을 필터링할 수 있습니다.

- **날짜(UTC)** **시작 날짜 및** 종료 **날짜입니다.**
- **방향**: **아웃바운드 및** **인바운드**.

필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**

주 보고서 페이지에서 추세 표시를  클릭하여 나타나는 메일 흐름 추세 플라이아웃에서 추세 그래프를 **볼** 수 있습니다.

![메일 흐름 상태 보고서의 메일 흐름 보기의 메일 흐름 추세 플라이아웃](../../media/mail-flow-status-report-mailflow-view-show-trends.png)

주 보고서 페이지에서 ![ 내보내기 아이콘을 클릭합니다.](../../media/m365-cc-sc-download-icon.png) **내보내기** 단추를 사용할 수 있습니다.

## <a name="malware-detections-report"></a>맬웨어 검색 보고서

> [!NOTE]
> 이 보고서는 사용되지 않습니다. 위협 방지 상태 보고서에서 동일한 [정보를 사용할 수 있습니다.](#threat-protection-status-report)

## <a name="mail-latency-report"></a>메일 대기 시간 보고서

**Defender** for Office 365 메일 대기 시간 보고서에는 조직 내에서 경험하는 메일 배달 및 확인 대기 시간에 대한 정보가 포함되어 있습니다. 자세한 내용은 메일 대기 [시간 보고서를 참조하세요.](view-reports-for-mdo.md#mail-latency-report)

## <a name="spam-detections-report"></a>스팸 검색 보고서

> [!NOTE]
> 이 보고서는 사용되지 않습니다. 위협 방지 상태 보고서에서 동일한 [정보를 사용할 수 있습니다.](#threat-protection-status-report)

## <a name="spoof-detections-report"></a>스푸핑 검색 보고서

**스푸핑 검색 보고서에는** 스푸핑으로 인해 차단되거나 허용된 메시지에 대한 정보가 표시됩니다. 스푸핑에 대한 자세한 내용은 [EOP의 스푸핑 방지 보호를 참조하세요.](anti-spoofing-protection.md)

보고서의 집계 보기는 45일 동안 필터링할 수 있는 반면 세부 정보 보기는 <sup>\*</sup> 10일의 필터링만 허용합니다.

<sup>\*</sup> 결국 최대 90일의 필터링을 사용할 수 있습니다.

Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자  메일 & 공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.** 전자 메일 **& 공동 작업** 보고서  페이지에서 스푸핑 검색을 찾은 다음 세부 정보 **보기를 클릭합니다.** 보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/reports/SpoofMailReportV2> 습니다.

![전자 메일 공유 공동 작업 보고서 페이지에서 & 위젯을 스푸핑합니다.](../../media/spoof-detections-widget.png)

차트에는 다음 정보가 표시됩니다.

- **통과**
- **실패**
- **SoftPass**
- **없음**
- **기타**

차트에서 하루(데이터 데이터 포인트)에 마우스를 대면 검색된 스푸핑된 메시지 수와 그 이유를 볼 수 있습니다.

필터를 클릭하고 플라이아웃에 나타나는 다음  값 중 하나 이상을 선택하여 차트와 세부 정보 테이블을 필터링할 수 있습니다.

- **날짜(UTC)** **시작 날짜 및** 종료 **날짜**
- **결과**:
  - **통과**
  - **실패**
  - **SoftPass**
  - **없음**
  - **기타**
- **스푸핑 유형:** **내부 및** **외부**

![웹 사이트 포털의 메일 보고서 Microsoft 365 Defender 페이지입니다.](../../media/spoof-detections-report-page.png)

그래프 아래의 세부 정보 표에는 다음 정보가 표시됩니다.

- **날짜**
- **스푸핑된 사용자**
- **인프라 보내기**
- **스푸핑 유형**
- **결과**
- **결과 코드**
- **SPF**
- **DKIM**
- **DMARC**
- **메시지 수**

복합 인증 결과 코드에 대한 자세한 내용은 에서 스팸 방지 메시지 [헤더를 Microsoft 365.](anti-spam-message-headers.md)

주 보고서 페이지에서 일정 ![ 만들기 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **[일정 만들기](#schedule-report)**, ![ 보고서 요청 아이콘.](../../media/m365-cc-sc-download-icon.png) **[보고서 요청](#request-report)** 및 ![ 내보내기 아이콘.](../../media/m365-cc-sc-download-icon.png) **[내보내기](#export-report)** 단추를 사용할 수 있습니다.

## <a name="submissions-report"></a>제출 보고서

제출 **보고서에는** 관리자가 분석을 위해 Microsoft에 보고한 항목에 대한 정보가 표시됩니다. 자세한 내용은 관리 제출을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 Microsoft에 제출을 [참조하세요.](admin-submission.md)

Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자  메일 & 공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.** 전자 메일 & **공동** 작업 보고서 페이지에서 제출을 **찾은** 다음 세부 정보 **보기를 클릭합니다.** 보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/adminSubmissionReport> 습니다. Microsoft 365 Defender 포털에서 관리 [제출으로 이동하려면 제출로](admin-submission.md) **이동을 클릭합니다.** 관리자는 지난 30일 동안 보고서를 볼 수 있습니다.

![전자 메일 및 공동 작업 보고서 & 제출 위젯입니다.](../../media/submissions-report-widget.png)

차트에는 다음 정보가 표시됩니다.

- **보류 중**
- **완료**

필터를 클릭하고 플라이아웃에 나타나는 다음  값 중 하나 이상을 선택하여 차트와 세부 정보 테이블을 필터링할 수 있습니다.

- **보고된 날짜:** **시작 시간** 및 **종료 시간**
- **제출 유형**:
  - **전자 메일**
  - **URL**
  - **파일**
- **제출 ID**
- **네트워크 메시지 ID**
- **보낸 사람**
- **이름**
- **제출한 인원**
- **제출 이유:**
  - **정크 아님**
  - **피싱**
  - **맬웨어**
  - **스팸**
- **상태 다시 검색:**
  - **보류 중**
  - **완료**

그래프 아래의 세부 정보 표에는 동일한 정보가  표시되어  있으며 전자 메일  및 공동 작업 제출의 분석 제출 탭에서와 동일한 **그룹 또는 & 옵션이** \> **있습니다.** 자세한 내용은 Microsoft에 대한 [관리자 제출 보기를 참조하세요.](admin-submission.md#view-admin-submissions-to-microsoft)

주 보고서 페이지에서 **[내보내기](#export-report)** 단추를 사용할 수 있습니다.

![제출 포털의 Microsoft 365 Defender 페이지입니다.](../../media/submissions-report-page.png)

## <a name="threat-protection-status-report"></a>위협 방지 상태 보고서

**위협 방지 상태 보고서는** EOP 및 Defender에서 모두 사용할 수 Office 365. 그러나 보고서에는 다른 데이터가 포함되어 있습니다. 예를 들어 EOP 고객은 전자 메일에서 검색된 맬웨어에 대한 정보를 볼 수 있지만, 전자 메일, 금고 및 에 대한 첨부 파일에서 검색된 악성 파일에 대한 SharePoint [OneDrive](mdo-for-spo-odb-and-teams.md)Microsoft Teams.

이 보고서는 맬웨어 방지 엔진에 의해 차단된 파일 또는 웹 사이트 주소(URL) 및 피싱 방지 정책의 Office 365 [링크,](safe-links.md)금고 첨부 파일 및 가장 보호 기능과 같은 [](safe-attachments.md)Office 365 금고 기능에 [](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)대한 Defender와 같은 악성 콘텐츠가 있는 전자 메일 메시지 수를 제공합니다. [](zero-hour-auto-purge.md) 이 정보를 사용하여 추세를 식별하거나 조직 정책에 조정이 필요한지 여부를 확인할 수 있습니다.

**참고:** 받는 사람 5명에게 메시지가 전송된 경우 하나의 메시지가 아니라 5개의 다른 메시지로 계산됩니다.

Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자  메일 & 공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.** 전자 메일 & 공동 작업 **보고서** 페이지에서 위협 방지 상태를 **찾은** 다음 세부 정보 **보기를 클릭합니다.** 보고서로 직접 이동하기 위해 다음 URL 중 하나를 열 수 있습니다.

- Defender for Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP>
- EOP: <https://security.microsoft.com/reports/TPSAggregateReport>

![전자 메일 및 공동 작업 보고서 & 위협 방지 상태 위젯입니다.](../../media/threat-protection-status-report-widget.png)

기본적으로 차트에는 지난 7일간의 데이터가 표시됩니다. 위협 방지  상태  보고서 페이지에서 필터링을 클릭하면 90일 날짜 범위를 선택할 수 있습니다(평가판 구독은 30일로 제한될 수 있습니다). 세부 정보 표에서는 30일 동안 필터링할 수 있습니다.

다음 섹션에서는 사용 가능한 보기에 대한 설명을 제공합니다.

### <a name="view-data-by-overview"></a>개요로 데이터 보기

![위협 방지 상태 보고서의 개요 보기입니다.](../../media/threat-protection-status-report-overview-view.png)

개요로 **데이터** 보기 보기에서 차트에 다음과 같은 검색 정보가 표시됩니다.

- **전자 메일 맬웨어**
- **전자 메일 피싱**
- **전자 메일 스팸**
- **콘텐츠 맬웨어**

차트 아래에 세부 정보 표를 사용할 수 없습니다.

필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.

- **날짜(UTC)** **시작 날짜 및** 종료 **날짜입니다.**
- **검색**:
  - **전자 메일 맬웨어**
  - **전자 메일 피싱**
  - **전자 메일 스팸**
  - **콘텐츠 맬웨어**
- **보호:** **MDO(Office 365용** Defender) **및 EOP .**
- **태그:** **우선** 순위 계정을 포함하여 모든 사용자 태그 또는 지정된 사용자 태그입니다. 사용자 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)
- **방향**:
  - **모두**
  - **인바운드**
  - **아웃바운드**
- **도메인**: **전체 또는** 허용 [도메인입니다.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
- **정책 유형**:
  - **모두**
  - **맬웨어 방지**
  - **안전한 첨부 파일**
  - **피싱 방지**
  - **스팸 방지**
  - **메일 흐름 규칙(전송** 규칙)
  - **기타**

필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a>검색 기술별 전자 메일 피싱 및 차트 \> 분석으로 데이터 보기

![위협 방지 상태 보고서의 피싱 전자 메일에 대한 검색 기술 보기입니다.](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

전자 메일 **피싱으로 데이터 \> 보기** **및** 검색 기술별 차트 분석 보기에서 차트에 다음 정보가 표시됩니다.

- **URL 악의적인 신뢰도:** 다른 Office 365 고객에 대한 <sup>\*</sup> 악의적인 URL 신뢰도 Microsoft 365.
- **고급 필터:** 기계 학습을 기반으로 하는 피싱 신호입니다.
- **일반 필터:** 분석가 규칙에 기반한 피싱 신호입니다.
- **스푸핑된** 도메인: 보낸 사람이 받는 사람 도메인을 스푸핑하려고 합니다.
- **스푸핑 외부** 도메인: 보낸 사람이 다른 도메인을 스푸핑하려고 합니다.
- **스푸핑 DMARC:** 메시지에 대한 DMARC 인증 실패.
- **가장 브랜드:** 보낸 사람 기반의 잘 알려진 브랜드 가장.
- **혼합 분석 검색**
- **파일 신뢰도**
- **지문 일치**
- **URL 확인 신뢰도**<sup>\*</sup>
- **URL 확인**<sup>\*</sup>
- **가장 사용자**<sup>\*</sup>
- **가장 도메인:** 고객이 소유하거나 정의하는 도메인의 <sup>\*</sup> 가장입니다.
- **사서함 인텔리전스 가장:** 관리자가 정의하거나 사서함 인텔리전스를 통해 학습한 사용자의 <sup>\*</sup> 가장입니다.
- **파일 Detonation**<sup>\*</sup>
- **파일 데스토니아 신뢰도**<sup>\*</sup>
- **캠페인**<sup>\*</sup>

<sup>\*</sup>Defender for Office 365 전용

차트 아래의 세부 정보 표에서 다음 정보를 사용할 수 있습니다.

- **날짜**
- **제목**
- **보낸 사람**
- **받는 사람**
- **검색 기술**
- **배달 상태**
- **보낸 사람 IP**
- **태그**

필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.

- **날짜(UTC)** **시작 날짜 및** 종료 **날짜**
- **검색:** 차트와 같은 값입니다.
- **보호:** **MDO(Office 365용** Defender) 또는 **EOP**
- **방향**:
  - **모두**
  - **인바운드**
  - **아웃바운드**
- **태그:** **우선** 순위 계정을 포함하여 모든 사용자 태그 또는 지정된 사용자 태그입니다. 사용자 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)
- **도메인**: **전체 또는** 허용 [도메인입니다.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
- **정책 유형**:
  - **모두**
  - **맬웨어 방지**
  - **안전한 첨부 파일**
  - **피싱 방지**
  - **스팸 방지**
  - **메일 흐름 규칙(전송** 규칙)
  - **기타**
- **정책 이름(세부 정보 표 보기에만 해당)**: **모든** 정책 또는 지정된 정책입니다.
- **받는 사람**

필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**

주 보고서 페이지에서 일정 ![ 만들기 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **[일정 만들기](#schedule-report)**, ![ 보고서 요청 아이콘.](../../media/m365-cc-sc-download-icon.png) **[보고서 요청](#request-report)** 및 ![ 내보내기 아이콘.](../../media/m365-cc-sc-download-icon.png) **[내보내기](#export-report)** 단추를 사용할 수 있습니다.

### <a name="view-data-by-email--spam-and-chart-breakdown-by-detection-technology"></a>검색 기술별 전자 메일 스팸 및 차트 \> 분석으로 데이터 보기

![위협 방지 상태 보고서의 스팸 검색 기술 보기입니다.](../../media/threat-protection-status-report-spam-detection-tech-view.png)

전자 메일 **스팸으로 \>** 데이터 보기 **및** 검색 기술별 차트 분석 보기에서 차트에 다음 정보가 표시됩니다.

- **URL 악의적인 신뢰도**
- **고급 필터**
- **일반 필터**
- **혼합 분석 검색**
- **지문 일치**
- **도메인 신뢰도**
- **대량 전자 메일**
- **IP 신뢰도**

차트 아래의 세부 정보 표에서 다음 정보를 사용할 수 있습니다.

- **날짜**
- **제목**
- **보낸 사람**
- **받는 사람**
- **검색 기술**
- **배달 상태**
- **보낸 사람 IP**
- **태그**

필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.

- **날짜(UTC)** **시작 날짜 및** 종료 **날짜**
- **검색:** 차트와 같은 값입니다.
- **방향**:
  - **모두**
  - **인바운드**
  - **아웃바운드**
- **태그:** **우선** 순위 계정을 포함하여 모든 사용자 태그 또는 지정된 사용자 태그입니다. 사용자 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)
- **도메인**: **전체 또는** 허용 [도메인입니다.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
- **정책 유형**:
  - **모두**
  - **맬웨어 방지**
  - **안전한 첨부 파일**
  - **피싱 방지**
  - **스팸 방지**
  - **메일 흐름 규칙(전송** 규칙)
  - **기타**
- **정책 이름(세부 정보 표 보기에만 해당)**: **모든** 정책 또는 지정된 정책입니다.
- **받는 사람**

필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**

주 보고서 페이지에서 일정 ![ 만들기 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **[일정 만들기](#schedule-report)**, ![ 보고서 요청 아이콘.](../../media/m365-cc-sc-download-icon.png) **[보고서 요청](#request-report)** 및 ![ 내보내기 아이콘.](../../media/m365-cc-sc-download-icon.png) **[내보내기](#export-report)** 단추를 사용할 수 있습니다.

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a>전자 메일 맬웨어 및 검색 기술별 \> 차트 분석으로 데이터 보기

![위협 방지 상태 보고서의 맬웨어에 대한 검색 기술 보기입니다.](../../media/threat-protection-status-report-malware-detection-tech-view.png)

전자 메일 **맬웨어로 \> 데이터** 보기 및 검색 기술별 **차트** 분석 보기에서 차트에 다음 정보가 표시됩니다.

- **파일 검색:** 첨부 금고 <sup>\*</sup> 검색.
- **파일 디버터 신뢰도:** 모든 악성 파일 신뢰도에서 Office 365 <sup>\*</sup> 생성합니다.
- **파일 신뢰도**
- **맬웨어 방지 엔진:** <sup>\*</sup> 맬웨어 방지 엔진에서 검색됩니다.
- **맬웨어** 방지 정책 파일 형식 블록: 메시지에 식별된 악성 파일의 유형으로 인해 필터링된 전자 메일 메시지입니다.
- **URL 악의적인 신뢰도**<sup>\*</sup>
- **URL 확인**<sup>\*</sup>
- **URL 확인 신뢰도**<sup>\*</sup>
- **캠페인**<sup>\*</sup>

차트 아래의 세부 정보 표에서 다음 정보를 사용할 수 있습니다.

- **날짜**
- **제목**
- **보낸 사람**
- **받는 사람**
- **검색 기술**
- **배달 상태**
- **보낸 사람 IP**
- **태그**

필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.

- **날짜(UTC)** **시작 날짜 및** 종료 **날짜**
- **검색:** 차트와 같은 값입니다.
- **보호:** **MDO(Office 365용** Defender) 또는 **EOP**
- **방향**:
  - **모두**
  - **인바운드**
  - **아웃바운드**
- **태그:** **우선** 순위 계정을 포함하여 모든 사용자 태그 또는 지정된 사용자 태그입니다. 사용자 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)
- **도메인**: **전체 또는** 허용 [도메인입니다.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
- **정책 유형**:
  - **모두**
  - **맬웨어 방지**
  - **안전한 첨부 파일**
  - **피싱 방지**
  - **스팸 방지**
  - **메일 흐름 규칙(전송** 규칙)
  - **기타**
- **정책 이름(세부 정보 표 보기에만 해당)**: **모든** 정책 또는 지정된 정책입니다.
- **받는 사람**

필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**

주 보고서 페이지에서 일정 ![ 만들기 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **[일정 만들기](#schedule-report)**, ![ 보고서 요청 아이콘.](../../media/m365-cc-sc-download-icon.png) **[보고서 요청](#request-report)** 및 ![ 내보내기 아이콘.](../../media/m365-cc-sc-download-icon.png) **[내보내기](#export-report)** 단추를 사용할 수 있습니다.

### <a name="chart-breakdown-by-policy-type"></a>정책 유형별 차트 분석

![위협 방지 상태 보고서의 피싱 전자 메일, 스팸 전자 메일 또는 맬웨어 전자 메일에 대한 정책 유형 보기입니다.](../../media/threat-protection-status-report-phishing-policy-type-view.png)

전자 **메일 피싱으로 데이터 \> 보기,** 전자 메일 스팸으로 데이터 보기 **또는 \>** 전자 메일 맬웨어 보기로 데이터 **보기에서 \>** 정책 유형별 차트 분석 데이터를 선택하면 차트에 다음 정보가 표시됩니다. 

- **맬웨어 방지**
- **금고 첨부 파일**<sup>\*</sup>
- **피싱 방지**
- **스팸 방지**
- **메일 흐름 규칙(전송** 규칙으로도 알려지기)
- **기타**

차트 아래의 세부 정보 표에서 다음 정보를 사용할 수 있습니다.

- **날짜**
- **제목**
- **보낸 사람**
- **받는 사람**
- **검색 기술**
- **배달 상태**
- **보낸 사람 IP**
- **태그**

필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.

- **날짜(UTC)** **시작 날짜 및** 종료 **날짜**
- **검색**:
  - **URL 악의적인 신뢰도:** 다른 Office 365 고객에 대한 <sup>\*</sup> 악의적인 URL 신뢰도 Microsoft 365.
  - **고급 필터:** 기계 학습을 기반으로 하는 피싱 신호입니다.
  - **일반 필터:** 분석가 규칙에 기반한 피싱 신호입니다.
  - **스푸핑된** 도메인: 보낸 사람이 받는 사람 도메인을 스푸핑하려고 합니다.
  - **스푸핑 외부** 도메인: 보낸 사람이 다른 도메인을 스푸핑하려고 합니다.
  - **스푸핑 DMARC:** 메시지에 대한 DMARC 인증 실패.
  - **가장 브랜드:** 보낸 사람 기반의 잘 알려진 브랜드 가장.
  - **혼합 분석 검색**
  - **파일 신뢰도**
  - **지문 일치**
  - **URL 확인 신뢰도**<sup>\*</sup>
  - **URL 확인**<sup>\*</sup>
  - **가장 사용자**<sup>\*</sup>
  - **가장 도메인:** 고객이 소유하거나 정의하는 도메인의 <sup>\*</sup> 가장입니다.
  - **사서함 인텔리전스 가장:** 관리자가 정의하거나 사서함 인텔리전스를 통해 학습한 사용자의 <sup>\*</sup> 가장입니다.
  - **파일 Detonation**<sup>\*</sup>
  - **파일 데스토니아 신뢰도**<sup>\*</sup>
  - **캠페인**<sup>\*</sup>
- **보호:** **MDO(Office 365용** Defender) 또는 **EOP**
- **방향**:
  - **모두**
  - **인바운드**
  - **아웃바운드**
- **태그:** **우선** 순위 계정을 포함하여 모든 사용자 태그 또는 지정된 사용자 태그입니다. 사용자 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)
- **도메인**: **전체 또는** 허용 [도메인입니다.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
- **정책 유형**:
  - **모두**
  - **맬웨어 방지**
  - **안전한 첨부 파일**
  - **피싱 방지**
  - **스팸 방지**
  - **메일 흐름 규칙(전송** 규칙)
  - **기타**
- **정책 이름(세부 정보 표 보기에만 해당)**: **모든** 정책 또는 지정된 정책입니다.
- **받는 사람**

<sup>\*</sup>Defender for Office 365 전용

필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**

주 보고서 페이지에서 일정 ![ 만들기 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **[일정 만들기](#schedule-report)**, ![ 보고서 요청 아이콘.](../../media/m365-cc-sc-download-icon.png) **[보고서 요청](#request-report)** 및 ![ 내보내기 아이콘.](../../media/m365-cc-sc-download-icon.png) **[내보내기](#export-report)** 단추를 사용할 수 있습니다.

### <a name="chart-breakdown-by-delivery-status"></a>배달 상태별 차트 분석

![위협 방지 상태 보고서의 피싱 전자 메일 및 맬웨어 전자 메일에 대한 배달 상태 보기입니다.](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

전자 **메일 피싱으로 데이터 \> 보기,** 전자 메일 스팸으로 데이터 보기 **또는 \>** 전자 메일 맬웨어 보기로 데이터 **보기에서 \>** 배달별 차트 분석 표시를 선택하면 차트에 다음 정보가 표시됩니다. 

- **호스트된 사서함: 받은 편지함**
- **호스트된 사서함: 정크 메일함**
- **호스트된 사서함: 사용자 지정 폴더**
- **호스트된 사서함: 지우기 항목**
- **전달**
- **On-premises server: Delivered**
- **격리**
- **배달 실패**
- **삭제**

차트 아래의 세부 정보 표에서 다음 정보를 사용할 수 있습니다.

- **날짜**
- **제목**
- **보낸 사람**
- **받는 사람**
- **검색 기술**
- **배달 상태**
- **보낸 사람 IP**
- **태그**

필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.

- **날짜(UTC)** **시작 날짜 및** 종료 **날짜**
- **검색**:
  - **URL 악의적인 신뢰도:** 다른 Office 365 고객에 대한 <sup>\*</sup> 악의적인 URL 신뢰도 Microsoft 365.
  - **고급 필터:** 기계 학습을 기반으로 하는 피싱 신호입니다.
  - **일반 필터:** 분석가 규칙에 기반한 피싱 신호입니다.
  - **스푸핑된** 도메인: 보낸 사람이 받는 사람 도메인을 스푸핑하려고 합니다.
  - **스푸핑 외부** 도메인: 보낸 사람이 다른 도메인을 스푸핑하려고 합니다.
  - **스푸핑 DMARC:** 메시지에 대한 DMARC 인증 실패.
  - **가장 브랜드:** 보낸 사람 기반의 잘 알려진 브랜드 가장.
  - **혼합 분석 검색**
  - **파일 신뢰도**
  - **지문 일치**
  - **URL 확인 신뢰도**<sup>\*</sup>
  - **URL 확인**<sup>\*</sup>
  - **가장 사용자**<sup>\*</sup>
  - **가장 도메인:** 고객이 소유하거나 정의하는 도메인의 <sup>\*</sup> 가장입니다.
  - **사서함 인텔리전스 가장:** 관리자가 정의하거나 사서함 인텔리전스를 통해 학습한 사용자의 <sup>\*</sup> 가장입니다.
  - **파일 Detonation**<sup>\*</sup>
  - **파일 데스토니아 신뢰도**<sup>\*</sup>
  - **캠페인**<sup>\*</sup>
- **보호:** **MDO(Office 365용** Defender) 또는 **EOP**
- **방향**:
  - **모두**
  - **인바운드**
  - **아웃바운드**
- **태그:** **우선** 순위 계정을 포함하여 모든 사용자 태그 또는 지정된 사용자 태그입니다. 사용자 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)
- **도메인**: **전체 또는** 허용 [도메인입니다.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
- **정책 유형**:
  - **모두**
  - **맬웨어 방지**
  - **안전한 첨부 파일**
  - **피싱 방지**
  - **스팸 방지**
  - **메일 흐름 규칙(전송** 규칙)
  - **기타**
- **정책 이름(세부 정보 표 보기에만 해당)**: **모든** 정책 또는 지정된 정책입니다.
- **받는 사람**

<sup>\*</sup>Defender for Office 365 전용

필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**

주 보고서 페이지에서 일정 ![ 만들기 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **[일정 만들기](#schedule-report)**, ![ 보고서 요청 아이콘.](../../media/m365-cc-sc-download-icon.png) **[보고서 요청](#request-report)** 및 ![ 내보내기 아이콘.](../../media/m365-cc-sc-download-icon.png) **[내보내기](#export-report)** 단추를 사용할 수 있습니다.

### <a name="view-data-by-content--malware"></a>콘텐츠 맬웨어로 \> 데이터 보기

![위협 방지 상태 보고서의 콘텐츠 맬웨어 보기입니다.](../../media/threat-protection-status-report-content-malware-view.png)

콘텐츠 **맬웨어로 \> 데이터** 보기 보기에서 조직의 Microsoft Defender에 대한 차트에 다음 Office 365 표시됩니다.

- **맬웨어** 방지 엔진 : 에서 기본 제공 바이러스 SharePoint, OneDrive 및 Microsoft Teams 검색된 악성 [Microsoft 365.](virus-detection-in-spo.md)
- **파일 검색:** 금고, 파일 및 금고 첨부 파일에서 검색된 악성 [SharePoint,](mdo-for-spo-odb-and-teams.md)OneDrive 및 Microsoft Teams.

차트 아래의 세부 정보 표에서 다음 정보를 사용할 수 있습니다.

- **날짜(UTC)** **시작 날짜 및** 종료 **날짜**
- **위치**
- **검색 기술**
- **맬웨어 이름**

필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.

- **날짜(UTC)** **시작 날짜 및** 종료 **날짜**
- **검색:** **맬웨어 방지 엔진** 또는 **파일 검색**

필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**

주 보고서 페이지에서 일정 ![ 만들기 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **[일정 만들기](#schedule-report)**, ![ 보고서 요청 아이콘.](../../media/m365-cc-sc-download-icon.png) **[보고서 요청](#request-report)** 및 ![ 내보내기 아이콘.](../../media/m365-cc-sc-download-icon.png) **[내보내기](#export-report)** 단추를 사용할 수 있습니다.

### <a name="view-data-by-system-override-and-chart-breakdown-by-reason"></a>시스템 오버라이드 및 이유별 차트 분석별 데이터 보기

![위협 방지 상태 보고서의 메시지 은(는) 및 이유별 차트 분석 보기입니다.](../../media/threat-protection-status-report-system-override-view-breakdown-by-reason.png)

시스템  **오버라이드별** 데이터 보기 및 이유별 차트 분석 보기에서 차트에 다음과 같은 이유 정보가 표시됩니다.

- **사내 건너뛰기**
- **IP 허용**
- **Exchange 전송 규칙(메일** 흐름 규칙)
- **조직에서 허용된 보낸 사람**
- **조직 허용 도메인**
- **ZAP를 사용할 수 없습니다.**
- **사용자 금고 보낸 사람**
- **사용자 금고 도메인**
- **피싱** 시뮬레이션: 자세한 내용은 [SecOps](configure-advanced-delivery.md)사서함에 대한 사용자 및 필터되지 않은 메시지에 대한 타사 피싱 시뮬레이션 배달 구성을 참조하세요.
- **타사 필터**

차트 아래의 세부 정보 표에서 다음 정보를 사용할 수 있습니다.

- **날짜**
- **제목**
- **보낸 사람**
- **받는 사람**
- **시스템 오버라이드**
- **보낸 사람 IP**
- **태그**

필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.

- **날짜(UTC)** **시작 날짜 및** 종료 **날짜**
- **이유:** 차트와 같은 값입니다.
- **배달 위치**: **정크 메일 폴더를** 사용할 수 없는 경우 또는 **SecOps 사서함입니다.**
- **방향**:
  - **모두**
  - **인바운드**
  - **아웃바운드**
- **태그:** **우선** 순위 계정을 포함하여 모든 사용자 태그 또는 지정된 사용자 태그입니다. 사용자 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)
- **도메인**: **전체 또는** 허용 [도메인입니다.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
- **정책 유형:** **모두**
- **정책 이름(세부 정보 표 보기에만 해당)**: **모두**
- **받는 사람**

필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**

주 보고서 페이지에서 ![ 내보내기 아이콘을 클릭합니다.](../../media/m365-cc-sc-download-icon.png) **[내보내기](#export-report)** 단추를 사용할 수 있습니다.

### <a name="view-data-by-system-override-and-chart-breakdown-by-delivery-location"></a>시스템 오버라이드 및 배달 위치별 차트 분석별 데이터 보기

![위협 방지 상태 보고서의 배달 위치 보기별 메시지 오버라이드 및 차트 분석](../../media/threat-protection-status-report-system-override-view-breakdown-by-delivery-location.png)

시스템으로 데이터 보기 **및** 배달  위치 보기별 차트 분석 보기에서 차트에 다음의 은(는) 이유 정보가 표시됩니다.

- **정크 메일 폴더를 사용할 수 없습니다.**
- **SecOps 사서함:** 자세한 내용은 SecOps 사서함에 대한 사용자 및 필터되지 않은 메시지에 대한 타사 피싱 시뮬레이션 배달 [구성을 참조하세요.](configure-advanced-delivery.md)

차트 아래의 세부 정보 표에서 다음 정보를 사용할 수 있습니다.

- **날짜**
- **제목**
- **보낸 사람**
- **받는 사람**
- **시스템 오버라이드**
- **보낸 사람 IP**
- **태그**

필터를 **클릭하면** 다음과 같은 필터를 사용할 수 있습니다.

- **날짜(UTC)** **시작 날짜 및** 종료 **날짜**
- **이유**
  - **사내 건너뛰기**
  - **IP 허용**
  - **Exchange 전송 규칙(메일** 흐름 규칙)
  - **조직에서 허용된 보낸 사람**
  - **조직 허용 도메인**
  - **ZAP를 사용할 수 없습니다.**
  - **사용자 금고 보낸 사람**
  - **사용자 금고 도메인**
  - **피싱** 시뮬레이션: 자세한 내용은 [SecOps](configure-advanced-delivery.md)사서함에 대한 사용자 및 필터되지 않은 메시지에 대한 타사 피싱 시뮬레이션 배달 구성을 참조하세요.
  - **타사 필터**
- **배달 위치**: **정크 메일 폴더를** 사용할 수 없는 경우 또는 **SecOps 사서함입니다.**
- **방향**:
  - **모두**
  - **인바운드**
  - **아웃바운드**
- **태그:** **우선** 순위 계정을 포함하여 모든 사용자 태그 또는 지정된 사용자 태그입니다. 사용자 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)
- **도메인**: **전체 또는** 허용 [도메인입니다.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
- **정책 유형**:
  - **모두**
  - **맬웨어 방지**
  - **금고 첨부 파일**<sup>\*</sup>
  - **피싱 방지**
  - **스팸 방지**
  - **메일 흐름 규칙(전송** 규칙)
  - **기타**
- **정책 이름(세부 정보 표 보기에만 해당)**: **모두**
- **받는 사람**

<sup>\*</sup>Defender for Office 365 전용

필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**

주 보고서 페이지에서 ![ 내보내기 아이콘을 클릭합니다.](../../media/m365-cc-sc-download-icon.png) **[내보내기](#export-report)** 단추를 사용할 수 있습니다.

## <a name="top-malware-report"></a>상위 맬웨어 보고서

Top **malware report** shows the various kinds of malware that was detected by [anti-malware protection in EOP.](anti-malware-protection.md)

Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자  메일 & 공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.** 전자 메일 & **공동** 작업 보고서 페이지에서 상위 맬웨어를 찾은 다음 세부 정보  **보기를 클릭합니다.** 보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/reports/TopMalware> 습니다.

![전자 메일 및 공동 작업 보고서 & 맬웨어 위젯입니다.](../../media/top-malware-report-widget.png)

파이 차트에서 에지 위에 마우스를 대면 맬웨어의 종류 이름과 해당 맬웨어가 있는 것으로 감지된 메시지 수를 볼 수 있습니다.

상위 **맬웨어 보고서 페이지에는** 더 큰 버전의 파이 차트가 보고서 페이지에 표시됩니다. 차트 아래의 세부 정보 표에는 다음 정보가 표시됩니다.

- **상위 맬웨어**
- **개수**

필터를 **클릭하면** 시작 날짜 및 종료 날짜로 날짜 범위를 **지정할** **수 있습니다.**

주 보고서 페이지에서 일정 ![ 만들기 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **[일정 만들기](#schedule-report)** 및 ![ 내보내기 아이콘](../../media/m365-cc-sc-download-icon.png) **[내보내기](#export-report)** 단추를 사용할 수 있습니다.

![상위 맬웨어 보고서 보기입니다.](../../media/top-malware-report-view.png)

## <a name="url-protection-report"></a>URL 보호 보고서

**URL 보호 보고서는** Microsoft Defender for Office 365. 자세한 내용은 [URL 보호 보고서를 참조하세요.](view-reports-for-mdo.md#url-protection-report)

## <a name="user-reported-messages-report"></a>사용자가 보고한 메시지 보고서

> [!IMPORTANT]
> 사용자가 보고한  메시지 보고서가 제대로 작동하려면 사용자 환경의 감사 로깅을 설정해야 Microsoft 365 있습니다.  이 작업은 일반적으로 감사 로그 역할이 할당된 사용자가 Exchange Online. 자세한 내용은 감사 로그 Microsoft 365 설정 또는 해제를 [참조하세요.](../../compliance/turn-audit-log-search-on-or-off.md)

사용자 **보고** 메시지 보고서에는 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용하여 사용자가 [](enable-the-report-message-add-in.md) 정크 메일, 피싱 시도 또는 양호한 메일로 보고한 전자 메일 메시지에 대한 정보가 [표시됩니다.](enable-the-report-phish-add-in.md)

Microsoft 365 Defender 포털에서 보고서를 보시고 보고서 전자  메일 & 공동 작업 전자 메일 & \>  \> **보고서로 이동하세요.** 전자 메일 & **공동** 작업 보고서 페이지에서 사용자가 보고한 메시지를 **찾은** 다음 세부 정보 **보기를 클릭합니다.** 보고서로 직접 이동하기 위해 를 를 <https://security.microsoft.com/reports/userSubmissionReport> 습니다. Microsoft 365 Defender 포털에서 관리 [제출으로 이동하려면 제출로](admin-submission.md) **이동을 클릭합니다.**

![사용자가 전자 메일 및 공동 작업 보고서 페이지에서 & 위젯을 보고했습니다.](../../media/user-reported-messages-widget.png)

필터를 클릭하고 플라이아웃에 나타나는 다음  값 중 하나 이상을 선택하여 차트와 세부 정보 테이블을 필터링할 수 있습니다.

- **보고된 날짜:** **시작 시간** 및 **종료 시간**
- **보고한**
- **전자 메일 제목**
- **보고된 메시지 ID**
- **네트워크 메시지 ID**
- **보낸 사람**
- **보고된 이유**
  - **정크 아님**
  - **피싱**
  - **스팸**
- **피싱 시뮬레이션:** **예** 또는 **아니요**

필터 구성을 마치면 **적용,** 취소 또는 필터 **지우기 를 클릭합니다.**

항목을 그룹화하려면 그룹을 **클릭하고** 드롭다운 목록에서 다음 값 중 하나를 선택합니다.

- **없음**
- **이유**
- **보낸 사람**
- **보고한**
- **결과 다시 검색**
- **피싱 시뮬레이션**

![사용자가 보고한 메시지 보고서입니다.](../../media/user-reported-messages-report.png)

그래프 아래의 세부 정보 표에는 다음 정보가 표시됩니다.

- **전자 메일 제목**
- **보고한**
- **보고된 날짜**
- **보낸 사람**
- **보고된 이유**
- **결과 다시 검색**
- **태그**

분석을 위해 Microsoft에 메시지를 제출하려면 표에서 메시지 항목을 선택하고 분석을 위해 **Microsoft에** 제출을 클릭한 다음 드롭다운 목록에서 다음 값 중 하나를 선택합니다.

- **정리 보고**
- **피싱 보고**
- **맬웨어 보고**
- **스팸 보고**'
- **조사** 트리거(Office 365)

주 보고서 페이지에서 ![ 내보내기 아이콘을 클릭합니다.](../../media/m365-cc-sc-download-icon.png) **[내보내기](#export-report)** 단추를 사용할 수 있습니다.

## <a name="what-permissions-are-needed-to-view-these-reports"></a>이러한 보고서를 보는 데 필요한 사용 권한은 무엇입니까?

이 문서에 설명된 보고서를 보고 사용하려면 Microsoft 365 Defender 포털에서 다음 역할 그룹 중 하나에 Microsoft 365 Defender 합니다.

- **조직 관리**
- **보안 관리자**
- **보안 읽기 권한자**
- **전역 읽기 권한자**

자세한 내용은 [Microsoft 365 Defender 포털 권한](permissions-microsoft-365-security-center.md)을 참조하세요.

**참고:** Azure Active Directory 역할에 사용자를 추가하면 Microsoft 365 관리 센터 포털에서 필요한 사용 권한과 Microsoft 365 Defender 포털의 다른  기능에 대한 사용 권한이 Microsoft 365. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.

## <a name="what-if-the-reports-arent-showing-data"></a>보고서에 데이터가 표시되지 않는 경우 어떻게 하나요?

보고서에 데이터가 없는 경우 사용중인 필터를 확인하고 정책이 올바르게 설정되어 있는지 다시 확인합니다. 자세한 내용은 [위협으로부터 보호를 참조합니다.](protect-against-threats.md)

## <a name="schedule-report"></a>보고서 예약

1. 주 보고서 페이지에서 일정 만들기 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-create-icon.png) **일정을 만드시고 을(를**
2. 예약된 **보고서 만들기 마법사가** 열립니다. 예약된 보고서 이름 **페이지에서** 이름 값을  검토하거나 사용자 지정한 후 다음 을 **클릭합니다.**
3. 기본 **설정 설정 페이지에서** 다음 설정을 구성합니다.
   - **빈도:** 다음 값 중 하나를 선택합니다.
     - **매주(기본값)**
     - **매월**
   - **시작 날짜:** 보고서 생성이 시작되는 시간입니다. 기본값은 오늘입니다.
   - **만료 날짜:** 보고서 생성이 종료된 시간입니다. 기본값은 오늘부터 1년입니다.

   작업을 마친 후 **다음** 을 클릭합니다.

4. 받는 **사람 페이지에서** 보고서의 받는 사람을 선택합니다. 기본값은 전자 메일 주소이지만 다른 주소를 추가할 수 있습니다.

   작업을 마친 후 **다음** 을 클릭합니다.

5. 검토 **페이지에서** 선택을 검토합니다. 각 **섹션에서** 뒤로  단추 또는 편집 링크를 클릭하여 변경할 수 있습니다.

   작업을 마쳤으면 **제출** 을 클릭합니다.

### <a name="managed-existing-scheduled-reports"></a>관리되는 기존 예약된 보고서

이미 만든 예약된 보고서를 관리하기 위해 다음 단계를 수행합니다.

1. Microsoft 365 Defender 포털에서 보고서 확장  전자 메일 & \> **공동** 작업 일정 \> 관리를 **선택합니다.**

   일정 관리 페이지로 직접 **이동하기** 위해 를 사용하세요. <https://security.microsoft.com/ManageSubscription>

2. 일정 **관리 페이지에** 예약된 각 보고서에 대해 다음 정보가 표시됩니다.
   - **시작 날짜 예약**
   - **일정 이름**
   - **보고서 유형**
   - **빈도**
   - **마지막으로 보낸 메일**

   수정할 기존 예약된 보고서를 찾아 찾습니다.

3. 예약된 보고서를 선택한 후 열 수 있는 세부 정보 플라이아웃에서 다음 작업을 수행하십시오.
   - **이름 편집:** 이 단추를 클릭하고 플라이아웃이 나타나면 보고서의 이름을 변경한 다음 저장을 **클릭합니다.**
   - **일정 삭제:** 이 단추를 클릭하고 나타나는 경고를 읽은 다음(이전 보고서를 더 이상 다운로드할 수 없음) 저장을 **클릭합니다.**
   - **세부 정보 예약** 섹션: 기본 설정 편집을 **클릭하여** 다음 설정을 변경합니다.
     - **빈도**: **매주** 또는 **월별**
     - **시작 날짜**
     - **만료 날짜**

     작업을 마쳤으면 **저장** 을 클릭합니다.

   - **받는 사람 섹션:** 받는 **사람 편집을** 클릭하여 예약된 보고서의 받는 사람을 추가하거나 제거합니다. 완료되면 **저장을 클릭합니다.**

   작업을 마쳤으면 **닫기** 를 클릭합니다.

## <a name="request-report"></a>요청 보고서

1. 주 보고서 페이지에서 보고서 요청 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-download-icon.png) **보고서 요청**.
2. 필요한 **경우 보고서 만들기 마법사가** 열립니다. On the **Name on-demand report** page, review or customize the **Name** value, and then click **Next**.
3. 기본 **설정 설정 페이지에서** 다음 설정을 검토하거나 구성합니다.
   - **시작 날짜:** 보고서 생성이 시작되는 시간입니다. 기본값은 한 달 전입니다.
   - **만료 날짜:** 보고서 생성이 종료된 시간입니다. 기본값은 오늘입니다.

   작업을 마친 후 **다음** 을 클릭합니다.

4. 받는 **사람 페이지에서** 보고서의 받는 사람을 선택합니다. 기본값은 전자 메일 주소이지만 다른 주소를 추가할 수 있습니다.

   작업을 마친 후 **다음** 을 클릭합니다.

5. 검토 **페이지에서** 선택을 검토합니다. 각 **섹션에서** 뒤로  단추 또는 편집 링크를 클릭하여 변경할 수 있습니다.

   작업을 마쳤으면 **제출** 을 클릭합니다.

6. 보고서가 성공적으로 만들어진 후 다른 보고서 만들기 또는 완료 를 클릭할 수  있는 새 **on-demand 보고서** 만들기 페이지로 **이동됩니다.**

   보고서는 다음 섹션에  설명된 다운로드용 보고서 페이지에서도 사용할 수 있습니다.

### <a name="download-reports"></a>보고서 다운로드

1. Microsoft 365 Defender 포털에서 보고서 확장  전자 메일 & \> 공동 작업에서 **다운로드할** \> 보고서를 **선택합니다.**

   다운로드할 보고서 **페이지로** 직접 이동하려면 를 <https://security.microsoft.com/ReportsForDownload> 사용하세요.

2. 다운로드용 **보고서 페이지에는** 사용 가능한 각 보고서에 대해 다음 정보가 표시됩니다.
   - **시작 날짜**
   - **이름**
   - **보고서 유형**
   - **마지막으로 보낸 메일**
   - **방향**

   다운로드할 보고서를 찾아 선택합니다.

## <a name="export-report"></a>보고서 내보내기

1. 주 보고서 페이지에서 내보내기 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-download-icon.png) **내보내기(해당** 링크를 사용할 수 있는 경우).

기본 보고서 페이지를 클릭하면 다음  설정을 구성할 수 있는 내보내기 조건 플라이아웃이 나타납니다.

- **내보낼 보기 선택:** 다음 값 중 하나를 선택합니다.
  - **요약:** 지난 90일 동안 데이터를 사용할 수 있습니다.
  - **세부 정보:** 지난 30일 동안 데이터를 사용할 수 있습니다.
- **날짜(UTC)**: **시작 날짜 및** 종료 **날짜입니다.**

필터 구성을 마치면 내보내기 를 **클릭합니다.** 열 수 있는 대화 상자에서 파일을 열거나 파일을 저장하거나 선택을 기억할 수 있습니다.

내보낼 각 .csv 행은 150,000개로 제한됩니다. 데이터에 150,000개 이상의 행이 포함되어 있는 경우 여러 개의 .csv 만들어집니다.

## <a name="related-topics"></a>관련 항목

[EOP의 스팸 방지 및 맬웨어 방지 보호 기능](anti-spam-and-anti-malware-protection.md)

[검색 포털의 스마트 보고서 및 Microsoft 365 Defender 정보](reports-and-insights-in-security-and-compliance.md)

[사이트 포털에서 메일 흐름 Microsoft 365 Defender 보기](view-mail-flow-reports.md)

[Defender for Office 365](view-reports-for-mdo.md)
