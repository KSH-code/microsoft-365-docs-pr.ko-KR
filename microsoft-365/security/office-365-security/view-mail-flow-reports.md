---
title: 보안 & 준수 센터에서 메일 흐름 보고서 보기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 조직에 대 한 메일 흐름 보안 보고서를 찾아서 사용 하는 방법에 대해 알아봅니다. 메일 흐름 보고서는 보안 & 준수 센터에서 사용할 수 있습니다.
ms.custom: ''
ms.openlocfilehash: 70c96bb4f43edb80f98fdc98aa173fed9e54e7d7
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937260"
---
# <a name="view-mail-flow-reports-in-the-security--compliance-center"></a>보안 & 준수 센터에서 메일 흐름 보고서 보기

보안 & 준수 센터에서 사용할 수 있는 [메일 흐름 정보](mail-flow-insights-v2.md) 이외에, Microsoft 365 조직을 모니터링 하는 데 도움이 되는 다양 한 메일 흐름 보고서도 사용할 수 있습니다. [필요한 권한이](#what-permissions-are-needed-to-view-these-reports)있는 경우 <https://office.protection.com> **보고서** 대시보드로 이동 하 여 보안 & 준수 센터에서 이러한 보고서를 볼 수 있습니다 \> **Dashboard**. 보고서 대시보드로 직접 이동 하려면를 엽니다 <https://office.protection.office.com/insightdashboard> .

![보안 & 준수 센터의 보고서 대시보드](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a>커넥터 보고서

**커넥터 보고서** 에는 조직에 대해 구성 된 [인바운드 및 아웃 바운드 커넥터](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 에 대 한 메일 흐름 활동이 표시 됩니다.

보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 후 **커넥터 보고서**를 선택 합니다. 보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=ConnectorReport> .

![보고서 대시보드의 커넥터 보고서 위젯](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a>커넥터 보고서에 대 한 보고서 보기

보고서 보기에서는 다음과 같은 차트를 사용할 수 있습니다.

- **데이터 보기 기준: 메일 흐름**:이 차트에서는 다음을 기준으로 구성한 인바운드 및 아웃 바운드 메시지의 수를 보여 줍니다.

  - **합계**
  - **커넥터 없이 인터넷에서**
  - **커넥터 없이 인터넷에 연결**
  - 구성한 특정 커넥터
  
  차트에서 데이터를 격리 하려면 다음 **에 대 한 데이터 표시** 컨트롤을 사용 하 여 이러한 옵션 중 하나 또는 **모든 메일 흐름**을 선택 합니다.

  ![커넥터 보고서에서 메일 흐름을 기준으로 데이터 보기](../../media/connector-report-view-data-by-mail-flow.png)

- **데이터 보기 기준: tls 사용량**:이 차트에서는 메일 흐름에 대 한 Tls (전송 계층 보안) 버전 사용 비율을 보여 줍니다.

  차트에서 데이터를 격리 하려면 다음 **에 대 한 데이터 표시** 컨트롤을 사용 하 여 다음 옵션 중 하나를 선택 합니다.

  - **모든 메일 흐름**
  - **커넥터 없이 인터넷에서**
  - **커넥터 없이 인터넷에 연결**
  - 구성한 특정 커넥터

  ![커넥터 보고서에서 TLS 사용을 기준으로 데이터 보기](../../media/connector-report-view-data-by-tls-usage.png)

보고서 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.

### <a name="details-table-view-for-the-connector-report"></a>커넥터 보고서에 대 한 세부 정보 테이블 보기

보고서 보기에서 **세부 정보 테이블 보기** 를 클릭 하면 다음과 같은 정보가 표시 됩니다.

- **날짜**
- **커넥터 방향 및 이름**
- **커넥터 유형**
- **강제 TLS?**: **True** 또는 **False**값을 지정 합니다.
- **TLS 없음** (백분율)
- **TLS 1.0** (백분율)
- **TLS 1.1** (백분율)
- **TLS 1.2** (백분율)
- **볼륨**: 메시지 수입니다.

세부 정보 표 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.

보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.

## <a name="exchange-transport-rule-report"></a>Exchange 전송 규칙 보고서

**Exchange 전송 규칙 보고서** 는 조직에서 들어오고 나가는 메시지에 대 한 메일 흐름 규칙 (전송 규칙이 라고도 함)의 영향을 보여 줍니다.

보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 다음 **Exchange 전송 규칙**을 선택 합니다. 보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=ETRRuleReport> .

![보고서 대시보드의 Exchange 전송 규칙 위젯](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a>Exchange 전송 규칙 보고서에 대 한 보고서 보기

보고서 보기에서는 다음과 같은 차트를 사용할 수 있습니다.

- **데이터 보기 기준: Exchange 전송 규칙** \> **아래로 나누기: 방향**:이 차트에서는 전송 규칙의 영향을 받는 **인바운드** 및 **아웃 바운드** 메시지의 수를 보여 줍니다.

- **데이터 보기 기준: Exchange 전송 규칙** \> **아래로 나누기: 심각도**:이 차트에는 **높은 심각도** 및 **보통 심각도**및 **심각도가 낮은** 메시지 수가 표시 됩니다. 심각도 수준을 규칙의 작업으로 설정 합니다 (심각도 수준이 나 _Setauditseverity_**으로이 규칙 감사** ). 자세한 내용은 [Mail flow rule actions In Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)을 참조 하십시오.

- **데이터 보기 기준: DLP Exchange 전송 규칙** \> **아래로 나누기: 방향**:이 차트에서는 DLP (데이터 손실 방지) 전송 규칙의 영향을 받는 **인바운드** 및 **아웃 바운드** 메시지의 수를 보여 줍니다. 다음 옵션을 선택 하 여 차트를 보다 구체화할 수 있습니다.

  - **데이터 표시: 모든 DLP 전송 규칙**
  - **데이터 표시: 손상 된 사용자**
  - **데이터 표시: 검색 된 콘텐츠가 부족 함 미국 Patriot Act**

- **데이터 보기 기준: DLP Exchange 전송 규칙** \> **아래로 나누기: 방향**:이 보기에는 DLP 전송 규칙의 영향을 받은 **높은 심각도** 및 **중간**심각도 메시지와 **낮은 심각도** 메시지가 표시 됩니다. 다음 옵션을 선택 하 여 차트를 보다 구체화할 수 있습니다.

  - **데이터 표시: 모든 DLP 전송 규칙**
  - **데이터 표시: 손상 된 사용자**
  - **데이터 표시: 검색 된 콘텐츠가 부족 함 미국 Patriot Act**

보고서 보기에서 **필터** 를 클릭 하면 다음 필터를 사용 하 여 결과를 수정할 수 있습니다.

- **시작 날짜** 및 **끝 날짜**
- 방향 값
- 심각도 값

![Exchange 전송 규칙 보고서의 보고서 보기](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a>Exchange 전송 규칙 보고서에 대 한 세부 정보 테이블 보기

**세부 정보 표 보기**를 클릭 하면 표시 되는 정보는 보고 있는 차트에 따라 달라 집니다.

- **데이터 보기 기준: Exchange 전송 규칙**:

  - **날짜**
  - **전송 규칙**
  - **제목**
  - **보낸 사람 주소**
  - **받는 사람 주소**
  - **심각도**
  - **방향**

- **데이터 보기 기준: DLP Exchange 전송 규칙**:

  - **날짜**
  - **DLP 정책**
  - **전송 규칙**
  - **제목**
  - **보낸 사람 주소**
  - **받는 사람 주소**
  - **심각도**
  - **방향**

세부 정보 표 보기에서 **필터** 를 클릭 하면 다음 필터를 사용 하 여 결과를 수정할 수 있습니다.

- **시작 날짜** 및 **끝 날짜**
- 방향 값
- 심각도 값

보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.

## <a name="forwarding-report"></a>전달 보고서

**전달 보고서** 에는 조직의 자동으로 전달 되는 메시지가 Exchange Online 사서함의 외부 도메인으로 표시 됩니다. 전달 된 메시지는 보안 또는 준수 위험을 초래할 수 있으며 계정이 손상 된 것을 나타냅니다.

보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 후 **전달 보고서**를 선택 합니다. 보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=MailFlowForwarding> .

![보고서 대시보드에서 보고서 위젯 전달](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a>전달 보고서에 대 한 보고서 보기

보고서 보기에서는 다음과 같은 차트를 사용할 수 있습니다.

- **데이터 표시: 전달 메서드**: 다음과 같은 메서드가 표시 됩니다.

  - **전송 규칙**: [메일 흐름 규칙이](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)라고도 합니다.
  - **사서함 규칙**: [받은 편지함 규칙이](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)라고도 합니다.

  ![전달 보고서의 전달 메서드 보기](../../media/forwarding-report-forwarding-methods.png)

- **다음에 대 한 데이터 표시: 전달 도메인**:이 보기에는 전달 대상이 되는 받는 사람 도메인이 표시 됩니다.

  ![전달 보고서의 전달 도메인 보기](../../media/forwarding-report-forwarding-domains.png)

- **데이터 표시: 전달자**: 다음 전달자가 표시 됩니다.

  - **전송 규칙**
  - 전달 받은 편지함 규칙을 포함 하는 사서함입니다.

  ![전달 보고서의 전달자 보기](../../media/forwarding-report-forwarders.png)

보고서 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.

### <a name="details-table-view-for-the-forwarding-report"></a>전달 보고서에 대 한 세부 정보 테이블 보기

보고서 보기에서 **세부 정보 테이블 보기** 를 클릭 하면 다음과 같은 정보가 표시 됩니다.

- **전달자**: 값 **전송 규칙** 또는 전달 받은 편지함 규칙을 포함 하는 사서함입니다.
- **전달 유형**: 값 **사서함 규칙** 또는 **전송 규칙**
- **받는 사람 이름**
- **받는 사람 도메인**
- **Details**: 메일 흐름 규칙의 GUID 값 또는 받은 편지함 규칙의 RuleIdentity 값입니다.
- **개수**
- **첫 번째 전달 날짜**

세부 정보 표 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.

보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.

## <a name="mailflow-status-report"></a>메일 흐름 상태 보고서

**메일 흐름 status 보고서** 는 edge에서 허용 되거나 차단 되는 전자 메일에 대 한 추가 정보가 포함 된 [보낸 날짜 및 받은 전자 메일 보고서](#sent-and-received-email-report)와 유사 합니다. 이 보고서는 edge 보호 정보를 포함 하며, EOP (Exchange Online Protection)에서 평가를 위해 서비스에 허용 되기 전에 차단 되는 전자 메일의 양을 보여 줍니다.

보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 다음 **메일 흐름 status report**를 선택 합니다. **메일 흐름 상태 보고서**로 바로 이동 하려면을 엽니다 <https://protection.office.com/mailflowStatusReport> .

![보고서 대시보드의 메일 흐름 상태 보고서 위젯](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a>메일 흐름 상황 보고서의 형식 보기

보고서를 열 때 **형식** 탭이 기본적으로 선택 되어 있습니다. 기본적으로이 보기에는 다음 필터를 사용 하 여 구성 된 차트 및 데이터 테이블이 포함 되어 있습니다.

- **날짜**: 지난 7 일
- **방향**:

  - **인바운드**
  - **아웃 바운드**
  - **조직 내** ( **인바운드** 및 **아웃 바운드**와 별도로 계산 됨)

- 다음을 **입력**합니다.

  - **좋은 메일**
  - **맬웨어**
  - **스팸**
  - **에 지 보호**
  - **규칙 메시지**
  - **피싱 전자 메일**

차트는 **형식** 값으로 구성 됩니다.

**필터** 를 클릭 하거나 차트 범례에서 값을 클릭 하 여 이러한 필터를 변경할 수 있습니다.

데이터 테이블에는 다음과 같은 정보가 포함 됩니다.

- **방향**
- **유형**
- **24시간**
- **3 일**
- **7일**
- **15일**
- **30일**

**자세한 내용을 보려면 범주 선택을**클릭 하면 다음 값 중에서 선택할 수 있습니다.

- **피싱 전자 메일**:이 옵션을 선택 하면 [위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report)로 이동 합니다.
- **전자 메일의 맬웨어**:이 옵션을 선택 하면 [위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report)로 이동 합니다.
- **스팸 감지**:이 옵션을 선택 하면 [스팸 감지 보고서](view-email-security-reports.md#spam-detections-report)가 사용 됩니다.
- **Edge 차단 된 스팸**:이 옵션을 선택 하면 [스팸 감지 보고서](view-email-security-reports.md#spam-detections-report)가 사용 됩니다.

**내보내기**:

자세히 보기에 대해서는 1 일 동안 데이터만 내보낼 수 있습니다. 따라서 데이터를 7 일간 내보내려는 경우에는 7 개의 서로 다른 내보내기 작업을 수행 해야 합니다.

내보낸 각 .csv 파일은 15만 행으로 제한 됩니다. 해당 날짜의 데이터에 15만 개 이상의 행이 포함 되어 있는 경우 여러 .csv 파일이 만들어집니다.

![메일 흐름 상황 보고서의 형식 보기 ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a>메일 흐름 상태 보고서에 대 한 방향 보기

**방향** 탭을 클릭 하면 **유형** 보기에서 같은 기본 필터가 사용 됩니다.

차트는 **방향** 값으로 구성 됩니다.

**필터** 를 클릭 하거나 차트 범례에서 값을 클릭 하 여 이러한 필터를 변경할 수 있습니다. **Type** 보기에서 동일한 필터가 사용 됩니다.

데이터 테이블에 **유형** 보기와 동일한 정보가 포함 되어 있습니다.

**자세한 내용에 대 한 자세한 내용은** **종류** 보기와 동일 합니다.

**내보내기**:

자세히 보기에 대해서는 1 일 동안 데이터만 내보낼 수 있습니다. 따라서 데이터를 7 일간 내보내려는 경우에는 7 개의 서로 다른 내보내기 작업을 수행 해야 합니다.

내보낸 각 .csv 파일은 15만 행으로 제한 됩니다. 해당 날짜의 데이터에 15만 개 이상의 행이 포함 되어 있는 경우 여러 .csv 파일이 만들어집니다.

![메일 흐름 상황 보고서의 방향 보기 ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a>보내고 받은 전자 메일 보고서

**Sent and received email** 보고서는 스팸 감지, 맬웨어 및 "양호"로 식별 된 전자 메일을 포함 하 여 수신 및 발신 전자 메일에 대 한 정보를 표시 하는 스마트 보고서입니다. 이 보고서와 [메일 흐름 status 보고서](#mailflow-status-report) 의 차이점은 다음과 같습니다 .이 보고서에는 edge 보호에 의해 차단 된 메시지에 대 한 데이터가 포함 되어 있지 않습니다.

보고서의 집계 보기 및 자세히 보기를 사용 하면 90 일의 필터링을 사용할 수 있습니다.

보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 다음 **보내고 받은 전자 메일**을 선택 합니다. 보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .

![보고서 대시보드의 보낸 날짜 및 받은 전자 메일 위젯](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a>보내고 받은 전자 메일 보고서에 대 한 보고서 보기

보고서 보기에서는 다음과 같은 차트를 사용할 수 있습니다.

- **아래로 나누기: Type**: 다음은 사용 가능한 모든 종류를 표시 하는 차트입니다.

  - **합계**
  - **좋은 메일**
  - **맬웨어 (맬웨어 방지)** (EOP)
  - **스팸 감지**
  - **규칙 메시지**
  - **고급 맬웨어** (OFFICE 365 ATP)

  차트에서 날짜 (데이터 요소)를 가리키면 해당 날짜에 대 한 세부 정보를 볼 수 있습니다.

  ![보낸 편지함 및 받은 전자 메일 보고서에 보기 입력](../../media/sent-and-received-email-report-type-view.png)

- **나누기: 방향**: **합계**, **인바운드**및 **아웃 바운드** 데이터를 표시 하는 차트입니다. 차트에서 날짜 (데이터 요소)를 가리키면 해당 날짜에 대 한 세부 정보를 볼 수 있습니다.

  ![보내고 받은 전자 메일 보고서의 방향 보기](../../media/sent-and-received-email-report-direction-view.png)

- **드릴 다운 기준** \> **맬웨어 (맬웨어 방지)**:이 옵션을 선택 하면 [전자 메일 보고서의 맬웨어 감지](view-email-security-reports.md#malware-detection-in-email-report)로 이동 됩니다.

- **드릴 다운 기준** \> **스팸 검색)**:이 옵션을 선택 하면 [스팸 감지 보고서](view-email-security-reports.md#spam-detections-report)가 사용 됩니다.

보고서 보기에서 **필터** 를 클릭 하면 다음 필터를 사용 하 여 결과를 수정할 수 있습니다.

- **시작 날짜** 및 **끝 날짜**
- 방향 값
- 형식 값

보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.

### <a name="details-table-view-for-the-sent-and-received-email-report"></a>보내고 받은 전자 메일 보고서에 대 한 세부 정보 테이블 보기

**아래로 나누기: 방향** 보기 또는 **아래로 나누기 기준: 방향** 보기로 **자세히 표 보기** 를 클릭 하면 다음과 같은 정보가 표시 됩니다.

- **날짜 (UTC)**
- **유형**
- **방향**
- **메시지 수**

세부 정보 표 보기에서 **필터** 를 클릭 하면 다음 필터를 사용 하 여 결과를 수정할 수 있습니다.

- **시작 날짜** 및 **끝 날짜**
- 방향 값
- 형식 값

보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.

## <a name="top-senders-and-recipients-report"></a>상위 보낸 사람 및 받는 사람 보고서

**상위 보낸 사람 및 받는 사람** 보고서는 상위 전자 메일 보낸 사람 및 받는 사람을 표시 하는 원형 차트입니다.

보고서를 보려면 [보안 & 준수 센터](https://protection.office.com)를 열고 **보고서** \> **대시보드로** 이동한 다음 **상위 보낸 사람 및 받는 사람**을 선택 합니다. 보고서로 직접 이동 하려면를 엽니다 <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .

![보고서 대시보드의 상위 보낸 사람 및 받는 사람 위젯](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a>상위 보낸 사람 및 받는 사람 보고서에 대 한 보고서 보기

보고서 보기에서는 다음과 같은 차트를 사용할 수 있습니다.

- **상위 메일 보낸 사람에 대 한 데이터 표시 \>**
- **상위 메일 받는 사람에 대 한 데이터 표시 \>**
- **주요 스팸 받는 사람에 대 한 데이터 표시 \>**
- **데이터 \> 표시 상위 맬웨어 받는 사람** (EOP)
- **데이터 \> 표시 최상위 맬웨어 받는 사람 (ATP)** (Office 365 ATP)

원형 차트의 컴포지션은 이러한 선택에 따라 변경 됩니다.

원형 차트의 쐐기형 위에 마우스를 올리면 보내거나 받은 메시지 수가 표시 됩니다.

보고서 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.

![상위 보낸 사람 및 받는 사람 보고서의 보고서 보기에 있는 원형 차트](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a>상위 보낸 사람 및 받는 사람 보고서에 대 한 세부 정보 테이블 보기

**세부 정보 표 보기**를 클릭 하면 표시 되는 정보는 보고 있는 차트에 따라 달라 집니다.

- **상위 메일 보낸 사람에 대 한 데이터 표시 \>**

  - **상위 메일 보낸 사람**
  - **개수**

- **상위 메일 받는 사람에 대 한 데이터 표시 \>**

  - **주요 메일 받는 사람**
  - **개수**

- **주요 스팸 받는 사람에 대 한 데이터 표시 \>**

  - **주요 스팸 받는 사람**
  - **개수**

- **데이터 \> 표시 상위 맬웨어 받는 사람** (EOP)

  - **주요 맬웨어 받는 사람**
  - **개수**

- **데이터 \> 표시 최상위 맬웨어 받는 사람 (ATP)** (Office 365 ATP)

  - **주요 ATP (맬웨어 수신자)**
  - **개수**

세부 정보 표 보기에서 **필터** 를 클릭 하면 **시작 날짜** 및 **종료 날짜**와 함께 날짜 범위를 지정할 수 있습니다.

보고서 보기로 돌아가려면 **보고서 보기**를 클릭 합니다.

## <a name="what-permissions-are-needed-to-view-these-reports"></a>이러한 보고서를 표시 하는 데 필요한 사용 권한은 무엇입니까?

보고서를 보고 사용 하려면 보안 & 준수 센터 **및** Exchange Online에서 지정 된 역할 그룹의 구성원 이어야 합니다.

- 보안 & 준수 센터에서 다음 역할 그룹 중 하나의 구성원 이어야 합니다.

  -조직 관리

  -보안 관리자 ( [Azure Active Directory 관리 센터](https://aad.portal.azure.com) 에서이 작업을 수행할 수도 있음)-보안 독자

  자세한 내용은 [보안 및 준수 센터의 사용 권한](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)을 참조하세요.

- Exchange Online에서 다음 역할 그룹 중 하나의 구성원 이어야 합니다.

  -조직 관리

  -보기 전용 조직 관리

  -보기 전용 받는 사람

  -준수 관리

자세한 내용은 exchange online의 [사용 권한](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) 및 [exchange online에서 역할 그룹 관리](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)를 참조 하세요.

## <a name="related-topics"></a>관련 항목

[보안 및 준수 센터의 똑똑한 보고서 및 분석](reports-and-insights-in-security-and-compliance.md)

[보안 및 준수 센터의 전자 메일 보안 보고서 보기](view-email-security-reports.md)
