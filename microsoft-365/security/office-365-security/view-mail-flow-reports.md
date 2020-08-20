---
title: 보고서 대시보드에서 메일 흐름 보고서 보기
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
description: 관리자는 준수 센터에서 보고서 대시보드에 사용할 수 있는 메일 흐름 보고서에 대해 & 있습니다.
ms.custom: ''
ms.openlocfilehash: 98b27497b758a202ccbb741f6cb10e4ec65570e9
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814513"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a>보안 규정 준수 센터의 보고서 대시보드에서 메일 & 보고서 보기

보안 & 준수 센터의 메일 흐름 대시보드에서 사용할 수 [있는 메일 흐름](mail-flow-insights-v2.md) 보고서 외에도 Microsoft 365 조직을 모니터링 하는 데 도움이 되는 보고서 대시보드에서 다양한 추가 메일 흐름 보고서를 사용할 수 있습니다.

필요한 권한이 있는 [경우 보고서 대시보드로](#what-permissions-are-needed-to-view-these-reports)이동하여 [보안 센터에서 & 이러한 보고서를](https://office.protection.com) 볼 **수** \> **있습니다.** 보고서 대시보드로 직접 이동하려면 <https://office.protection.office.com/insightdashboard> .

![Security Center의 보고서 & 대시보드](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a>커넥터 보고서

커넥터 **보고서는** 조직에 대해 구성된 [인바운드 및 아웃바운드 커넥터에서의](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 메일 흐름 활동을 보여줍니다.

보고서를 보려면 준수 센터에서 [보안 & 보고서](https://protection.office.com)대시보드로 **Reports** \> **이동하여 커넥터** **보고서를 선택합니다.** 보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=ConnectorReport> .

![보고서 대시보드의 커넥터 보고서 위리인](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a>커넥터 보고서의 보고서 보기

보고서 보기에서는 다음 차트를 사용할 수 있습니다.

- **데이터 보기: 메일 흐름:** 이 차트에는 다음과 같이 구성된 인바운드 및 아웃바운드 메시지 수가 표시됩니다.

  - **합계**
  - **커넥터 없이 인터넷에서**
  - **커넥터 없이 인터넷으로 연결**
  - 구성한 특정 커넥터
  
  차트의 데이터를 격리하려면 컨트롤에 대한 **데이터 표시 컨트롤을** 사용하여 이러한 옵션 중 하나 또는 모든 메일 **흐름을 선택할 수 있습니다.**

  ![커넥터 보고서에서 메일 흐름별 데이터 보기](../../media/connector-report-view-data-by-mail-flow.png)

- **데이터 보기:TLS 사용: 이**차트는 메일 흐름에 대한 TLS(전송 계층 보안) 버전 사용의 백분율을 보여 줍니다.

  차트의 데이터를 격리하려면 컨트롤의 **표시 데이터를 사용하여** 다음 옵션 중 하나를 선택합니다.

  - **모든 메일 흐름**
  - **커넥터 없이 인터넷에서**
  - **커넥터 없이 인터넷으로 연결**
  - 구성한 특정 커넥터

  ![커넥터 보고서에서 TLS 사용을 사용하여 데이터 보기](../../media/connector-report-view-data-by-tls-usage.png)

보고서 보기에서 **필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**

### <a name="details-table-view-for-the-connector-report"></a>커넥터 보고서의 세부 정보 표 보기

보고서 보기에서 **세부 정보 표를** 클릭하면 다음 정보가 표시됩니다.

- **날짜**
- **커넥터 방향 및 이름**
- **커넥터 유형**
- **강요된 TLS?**: **True** 또는 False **값입니다.**
- **TLS** 없음(비율)
- **TLS** 1.0(백분율)
- **TLS** 1.1(백분율)
- **TLS** 1.2(백분율)
- **볼륨**: 메시지의 수

세부 정보 **보기에서 필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**

보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**

## <a name="exchange-transport-rule-report"></a>Exchange 전송 규칙 보고서

**Exchange 전송 규칙 보고서는** 조직에서 들어오고 나가는 메시지에 대한 메일 흐름 규칙(전송 규칙이라고도 함)의 영향을 보여줍니다.

보고서를 보려면 보안 서비스 관리 [& 만들고 보고서](https://protection.office.com)대시보드로 **이동한** \> **다음 Exchange 전송** **규칙을 선택합니다.** 보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=ETRRuleReport> .

![보고서 대시보드의 Exchange 전송 규칙 위과 위산](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a>Exchange 전송 규칙 보고서의 보고서 보기

보고서 보기에서는 다음 차트를 사용할 수 있습니다.

- **다음을 사용하자 데이터 보기: Exchange 전송 규칙** \> **분석: 이 차트에는**전송 규칙의 영향을 **받은** 인바운드 및 아웃바운드 메시지 수가 표시됩니다. **Outbound**

- **다음을 사용하자 데이터 보기: Exchange 전송 규칙** \> **분석: 심각도: 이**차트는 높은 **심각도 및** **중간 심각도,** 낮은 심각도 메시지 **수를 표시합니다.** 심각도 수준을 규칙에서 작업으로**설정합니다(심각도 수준 또는** _SetAuditSeverity를 사용하여 이 규칙 감사)._ 자세한 내용은 [Exchange Online에서 메일 흐름 규칙 작업을 참조하세요.](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- **DLP Exchange 전송 규칙별 데이터 보기** \> **분석: 이**차트에는 DLP(데이터 **Inbound** 손실 방지) 전송 규칙의 영향을 받은 인바운드 및 아웃바운드 메시지 수가 표시됩니다. **Outbound** 다음 옵션 중에서 선택한 선택하더라도 차트를 더 세분화할 수 있습니다.

  - **데이터 표시: 모든 DLP 전송 규칙**
  - **데이터 표시: 보안 사용자 보안**
  - **미국(국가)에 대한 데이터 미만을 보냅니다.**

- **DLP Exchange 전송 규칙별 데이터 보기** \> **분석: 이 보기에는**DLP 전송 **규칙의 영향을** 받은 심각도 및 **Low severity** **중간**심각도 및 낮은 심각도 메시지의 수가 표시됩니다. 다음 옵션 중에서 선택한 선택하더라도 차트를 더 세분화할 수 있습니다.

  - **데이터 표시: 모든 DLP 전송 규칙**
  - **데이터 표시: 보안 사용자 보안**
  - **미국(국가)에 대한 데이터 미만을 보냅니다.**

보고서 보기에서 **필터를** 클릭한 경우 다음 필터를 사용하여 결과를 수정할 수 있습니다.

- **시작 날짜** **및 끝 날짜**
- 방향 값
- 심각도 값

![Exchange 전송 규칙 보고서의 보고서 보기](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a>Exchange 전송 규칙 보고서의 세부 정보 표 보기

세부 정보 **표를 보기를**클릭하면 표시되는 정보는 검색 하고 있는 차트에 따라 달라지게 됩니다.

- **다음을 사용한 데이터 보기: Exchange 전송 규칙:**

  - **날짜**
  - **전송 규칙**
  - **제목**
  - **보낸 사람 주소**
  - **받는 사람 주소**
  - **심각도**
  - **방향**

- **DLP Exchange 전송 규칙: 사용자별 데이터 보기:**

  - **날짜**
  - **DLP 정책**
  - **전송 규칙**
  - **제목**
  - **보낸 사람 주소**
  - **받는 사람 주소**
  - **심각도**
  - **방향**

세부 정보 표 **보기에서** 필터를 클릭한 경우 다음 필터를 사용하여 결과를 수정할 수 있습니다.

- **시작 날짜** **및 끝 날짜**
- 방향 값
- 심각도 값

보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**

## <a name="forwarding-report"></a>전달 보고서

전달 **보고서에는 Exchange** Online 사서함에서 외부 도메인으로 자동으로 전달된 조직의 메시지가 표시됩니다. 전달된 메시지는 보안 또는 규정 준수 위험을 일어받을 수 있기며 계정이 노출된 것을 나타냅니다.

보고서를 보려면 준수 센터에서 [보안 & 보고서](https://protection.office.com) **대시보드로** \> **이동한 후** 전달 **보고서를 선택합니다.** 보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=MailFlowForwarding> .

![보고서 대시보드에서 보고서 위도를 전달합니다.](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a>전달 보고서의 보고서 보기

보고서 보기에서는 다음 차트를 사용할 수 있습니다.

- **데이터 표시: 전달 메서드:** 다음 메서드가 표시됩니다.

  - **전송 규칙:** 메일 흐름 [규칙이라고도 알려진 전송 규칙.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - **사서함 규칙:** 받은 편지함 [규칙이라고도 함](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)규칙.

  ![전달 보고서의 전달 방법 보기](../../media/forwarding-report-forwarding-methods.png)

- **데이터 가져오기: 전달 도메인:** 이 보기에는 전달 대상에 해당하는 받는 사람 도메인이 표시됩니다.

  ![전달 보고서의 전달 도메인 보기](../../media/forwarding-report-forwarding-domains.png)

- **데이터 표시: 전달자:** 다음 전달자가 표시됩니다.

  - **전송 규칙**
  - 전달 받은 편지함 규칙이 들어 있는 사서함입니다.

  ![전달 보고서의 전달자 보기](../../media/forwarding-report-forwarders.png)

보고서 보기에서 **필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**

### <a name="details-table-view-for-the-forwarding-report"></a>전달 보고서의 세부 정보 표 보기

보고서 보기에서 **세부 정보 표를** 클릭하면 다음 정보가 표시됩니다.

- **전달자:** 전달 받은 **편지함** 규칙이 포함되어 있는 사서함 또는 가치 전송 규칙입니다.
- **전달 유형:** 값 사서함 **규칙 또는** **전송 규칙.**
- **받는 사람 이름**
- **받는 사람 도메인**
- **세부**정보: 메일 흐름 규칙의 GUID 값 또는 받은 편지함 규칙의 RuleIdentity 값입니다.
- **개수**
- **첫 번째 전달 날짜**

세부 정보 **보기에서 필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**

보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**

## <a name="mailflow-status-report"></a>메일 흐름 상태 보고서

메일 **흐름 상태 보고서는 보낸 후** 받은 전자 메일 [보고서와](#sent-and-received-email-report)비슷하지만, Edge에서 허용하거나 차단하는 방법에 대한 추가 정보입니다. Edge 보호 정보를 포함하는 유일한 보고서이며 EOP(Exchange Online Protection)에서 평가를 위해 서비스로 허용되기 전에 차단되는 전자 메일의 양만 표시합니다. 메시지를 받는 사람 5명에게 보낼 경우 메시지 하나가 5명인 다른 메시지로 계산된다는 점을 이해해야 합니다.  
보고서를 보려면 보안 센터에서 [& 만들고 보고서](https://protection.office.com) **대시보드로** \> **이동한 후 메일** 흐름 상태 **보고서를 선택합니다.** 메일 흐름 상태 보고서로 **직접 이동하려면 을**엽니다. <https://protection.office.com/mailflowStatusReport>

![보고서 대시보드의 메일 흐름 상태 보고서 위리인](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a>메일 흐름 상태 보고서의 유형 보기

보고서를 열면 기본적으로 **Type(종류)** 탭이 선택되어 있습니다. 기본적으로 이 보기에는 다음과 같은 필터로 구성된 차트와 데이터 테이블이 포함되어 있습니다.

- **날짜**: 지난 7일
- **Direction**:

  - **인바운드**
  - **아웃바운드**
  - **조직 내: 이**수는 테넌트 내의 메시지 수입니다. 보낸 abc@domain.com 사람 번호(인바운드 및 xyz@domain.com 아웃바운드에서 별도로 **계산)를 받는** 사람 **번호로 보내기**

- **Type**:

  - **정상 메일**
  - **맬웨어**
  - **스팸**
  - **Edge 보호**
  - **규칙 메시지**
  - **피싱 전자 메일**

차트가 Type 값을 사용하여 **구성됩니다.**

필터를 클릭하거나 차트 **범례에서** 값을 클릭하여 이러한 필터를 변경할 수 있습니다.

데이터 테이블에는 다음과 같은 정보가 포함됩니다.

- **방향**
- **Type**
- **24시간**
- **3일**
- **7일**
- **15일**
- **30일**

자세한 **정보를 보기 위해 범주를 선택할 경우**다음 값 중에서 선택할 수 있습니다.

- **피싱 전자 메일:** 이 기능을 선택하면 위협 방지 상태 [보고서로 이동됩니다.](view-email-security-reports.md#threat-protection-status-report)
- **전자 메일의 맬웨어:** 이 선택을 선택하면 위협 방지 상태 [보고서로 이동됩니다.](view-email-security-reports.md#threat-protection-status-report)
- **스팸 검색:** 이 선택 항목을 사용하면 스팸 검색 [보고서로 이동됩니다.](view-email-security-reports.md#spam-detections-report)
- **Edge 차단된 스팸:** 이 선택 항목을 선택하면 스팸 [검색 보고서로 이동합니다.](view-email-security-reports.md#spam-detections-report)

**Export**:

세부 정보 보기의 경우 한 날짜에 한 번만 데이터를 내보낼 수 있습니다. 따라서 7일 동안 데이터를 내보내려면 7가지 다른 내보내기 작업을 수행해야 합니다.

내보낸 각 .csv 파일은 150,000개의 행으로 제한됩니다. 해당 날짜의 데이터에 15만 개보다 많은 행이 포함되어 있는 경우 여러 개의 .csv 파일이 생성됩니다.

![메일 흐름 상태 보고서의 유형 보기 ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a>메일 흐름 상태 보고서의 방향 보기

방향 탭을 **클릭하면** 유형 보기의 동일한 기본 **필터가** 사용됩니다.

차트가 Direction 값으로 **구성됩니다.**

필터를 클릭하거나 차트 **범례에서** 값을 클릭하여 이러한 필터를 변경할 수 있습니다. 형식 보기의 동일한 **필터가** 사용됩니다.

데이터 테이블에는 형식 보기의 동일한 정보가 **포함됩니다.**

이 **범주에서 사용 가능한 더 자세한 선택** 항목 및 동작에 대한 범주선택은 유형 보기와 **같습니다.**

**Export**:

세부 정보 보기의 경우 한 날짜에 한 번만 데이터를 내보낼 수 있습니다. 따라서 7일 동안 데이터를 내보내려면 7가지 다른 내보내기 작업을 수행해야 합니다.

내보낸 각 .csv 파일은 150,000개의 행으로 제한됩니다. 해당 날짜의 데이터에 15만 개보다 많은 행이 포함되어 있는 경우 여러 개의 .csv 파일이 생성됩니다.

![메일 흐름 상태 보고서의 방향 보기 ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a>메일 흐름 상태 보고서의 Funnel 보기

금지 **보기에서는** Microsoft의 전자 메일 위협 방지 기능으로 조직 내 수신 및 보내는 전자 메일을 필터링하는 방법을 보여 줍니다. 이 표에서는 총 전자 메일 수와 Edge 보호, 맬웨어 방지, 피싱 방지, 스팸 방지 및 스푸핑 방지를 비롯한 구성된 위협 보호 기능이 이 개수에 미치는 영향에 대한 세부 정보를 제공합니다.

기본적으로 이 **보기에 포함된 새로운** 탭과 다음과 같은 필터로 구성된 데이터 테이블이 이 보기에 포함됩니다.

- **날짜**: 지난 7일

- **Direction**:

  - **인바운드**
  - **아웃바운드**
  - **조직 내: 테넌트**내에서 보낸 메시지에 대한 수입니다. 다시 보낸 사람 주소는 abc@domain.com 사람 주소(인바운드 및 xyz@domain.com 아웃바운드에서 별도로 계산됨)에게 보냅니다.

집계 보기 및 데이터 테이블 보기에서는 90일 동안 필터링이 허용됩니다.

**Filter를 클릭하면**차트 및 데이터 테이블을 모두 필터링할 수 있습니다.

이 차트에는 다음과 같이 구성된 전자 메일 수가 표시됩니다.

  - **총 전자 메일**
  - **Edge 보호 후 전자 메일**
  - **Email after anti-malware, file reputation, file type block**
  - **피싱 방지, URL 신뢰도, 브랜드 가장, 스푸핑 방지 후의 전자 메일**
  - **스팸 방지 후의 전자 메일, 대량 메일 필터링**
  - 사용자 및 도메인 가장 1 **이후의**<sup>전자 메일</sup>
  - **파일 및 URL 디온 1 이후의**<sup>메일</sup>
  - **배달 후 보호 후 검색된 전자 메일(URL 클릭 시간 보호)**

<sup>1</sup> Office 365 ATP만

EOP 또는 ATP를 사용하여 별도로 필터링된 전자 메일을 표시하려면 차트 범례에서 값을 클릭합니다.

데이터 테이블에는 내내의 날짜 순서대로 표시된 다음 정보가 포함됩니다.

 - **날짜**
 - **총 전자 메일**
 - **Edge 보호**
 - **맬웨어 방지, 파일 신뢰도, 파일 형식 차단**
 - **피싱 방지, URL 신뢰도, 브랜드 가장, 스푸핑 방지**
 - **스팸 방지, 대량 메일 필터링**
 - **사용자 및 도메인 가장(ATP)**
 - **파일 및 URL 디터와이션(ATP)**
 - **POST-Delivery Protection and ZAP(ATP) 또는 ZAP(ZAP)**

데이터 테이블에서 행을 선택하면 전자 메일 수에 대한 추가 분석이 플라이아웃에 표시됩니다.

**Export**:

옵션에서 **내보내기를** **클릭한 후에는**다음 값 중 하나를 선택할 수 있습니다.

- **요약(가장 최근 90일 동안의 데이터 사용)**
- **세부 정보(지난 30일 동안의 데이터 사용)**

날짜 **아래에서**범위를 선택한 다음 적용을 **클릭합니다.** 현재 필터의 데이터는 .csv 파일로 내보내집니다.

내보낸 각 .csv 파일은 150,000개의 행으로 제한됩니다. 데이터에 15만 개보다 많은 행이 포함되어 있는 경우 여러 .csv 파일이 생성됩니다.

 ![메일 흐름 상태 보고서의 Funnel 보기 ](../../media/mail-flow-status-report-funnel-view.png)

 ### <a name="tech-view-for-the-mailflow-status-report"></a>메일 흐름 상황 보고서기술 보기

기술 **보기는** 새로운 **보기와 비슷하며, 구성된** 위협 방지 기능에 대한 더 세부 세부 정보를 제공합니다. 차트에서 다양한 위협 방지 단계에서 메시지가 분류되는 방식을 확인할 수 있습니다.

기본적으로 Tech **보기 탭을** 클릭하면 이 보기에는 다음과 같은 필터를 사용하여 구성된 차트 및 데이터 테이블이 포함됩니다.

- **날짜**: 지난 7일

- **Direction**:

  - **인바운드**
  - **아웃바운드**
  - **조직 내: 이**수는 테넌트 내의 메시지 수입니다. 보낸 abc@domain.com 사람 이름(인바운드 및 xyz@domain.com 아웃바운드에서 별도로 계산)을 통해 받는 사람 데이터를 보냅니다.

집계 보기 및 데이터 테이블 보기에서는 90일 동안 필터링이 허용됩니다.

**Filter를 클릭하면**차트 및 데이터 테이블을 모두 필터링할 수 있습니다.

이 차트에는 다음 범주로 구성된 메시지가 표시됩니다.

  - **총 전자 메일**
  - **Edge 허용, 에지 필터링**
  - **맬웨어가 아오오고 ATP(안전한 첨부 파일 검색), 맬웨어 방지 엔진 검색, 규칙 차단**
  - **피싱, DMARC 실패, 가장 감지, 스푸핑 탐지, 피싱 탐지**
  - **URL 감각이 포함된 검색, URL 감지(ATP)**
  - **스팸이 아지 지 않습니다, 스팸**
  - **악성이 아닌 이메일, ATP(안전한 링크 검색), ZAP**

차트에서 범주 위에 위로 가리면 해당 범주의 메시지 수를 볼 수 있습니다.

데이터 테이블에는 내내의 날짜 순서대로 표시된 다음 정보가 포함됩니다.

  - **날짜**  
  - **총 전자 메일**
  - **Edge 필터링됨**
  - **맬웨어 방지 엔진, 안전한 첨부 파일, 규칙 필터링됨**
  - **DMARC, 가장, 스푸핑, 피싱 필터링**
  - **URL 감지**
  - **스팸 방지 필터링됨**
  - **ZAP 제거됨**
  - **안전한 링크로 검색**

데이터 테이블에서 행을 선택하면 전자 메일 수에 대한 추가 분석이 플라이아웃에 표시됩니다.

**Export**:

내보내기를 **클릭하고**옵션 **아래에서** 다음 값 중 하나를 선택할 수 있습니다.

- **요약(가장 최근 90일 동안의 데이터 사용)**
- **세부 정보(지난 30일 동안의 데이터 사용)**

날짜 **아래에서**범위를 선택한 다음 적용을 **클릭합니다.** 현재 필터의 데이터는 .csv 파일로 내보내집니다.

내보낸 각 .csv 파일은 150,000개의 행으로 제한됩니다. 데이터에 15만 개보다 많은 행이 포함되어 있는 경우 여러 .csv 파일이 생성됩니다.

 ![메일 흐름 상태 보고서의 Tech 보기 ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a>보낸 메일 및 받은 전자 메일 보고서

보낸 **및 받은 전자 메일 보고서는** 스팸 탐지, 맬웨어 및 "스팸"으로 확인된 전자 메일을 비롯한 수신 및 보내는 전자 메일에 대한 정보를 보여 주는 스마트 보고서입니다. 이 보고서와 메일 흐름 상태 보고서의 차이점은 [Edge](#mailflow-status-report) 보호에서 차단된 메시지에 대한 데이터는 이 보고서에 포함되지 않습니다.

보고서의 집계 보기 및 세부 정보 보기를 사용하면 필터링 기간을 90일 동안 사용할 수 있습니다.

보고서를 보려면 규정 준수 [센터에서 보안 & 보고서 대시보드로](https://protection.office.com) **Reports** \> **이동한 다음 보낸 전자** **메일과 받은 전자 메일을 선택합니다.** 보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .

![보고서 대시보드에서 고지되거나 받은 전자 메일 위장](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a>보낸 및 받은 전자 메일 보고서의 보고서 보기

보고서 보기에서는 다음 차트를 사용할 수 있습니다.

- **분석합니다. 유형: 차트에**사용 가능한 모든 범주가 표시됩니다.

  - **합계**
  - **정상 메일**
  - **맬웨어 방지(맬웨어 방지)(EOP)**
  - **스팸 감지**
  - **규칙 메시지**
  - **고급 맬웨어(Office** 365 ATP)

  차트에서 하루(데이터 요소)을 가리치면 해당 날짜에 대한 세부 정보를 볼 수 있습니다.

  ![보낸 전자 메일 및 받은 전자 메일 보고서의 유형 보기](../../media/sent-and-received-email-report-type-view.png)

- **분석 단위: 차트에 합계,** **인바운드** **및 아웃바운드** **데이터가 표시됩니다.** 차트에서 하루(데이터 요소)을 가리치면 해당 날짜에 대한 세부 정보를 볼 수 있습니다.

  ![보낸 메일 및 받은 전자 메일 보고서의 방향 보기](../../media/sent-and-received-email-report-direction-view.png)

- **아래쪽으로 드릴다운** \> **맬웨어(맬웨어 방지):** 이 옵션을 선택하면 전자 메일 [보고서에서 맬웨어 검색으로 이동됩니다.](view-email-security-reports.md#malware-detections-in-email-report)

- **아래쪽으로 드릴다운** \> **스팸 검색:** 이 선택 항목을 클릭하면 스팸 검색 [보고서로 이동됩니다.](view-email-security-reports.md#spam-detections-report)

보고서 보기에서 **필터를** 클릭한 경우 다음 필터를 사용하여 결과를 수정할 수 있습니다.

- **시작 날짜** **및 끝 날짜**
- 방향 값
- Type 값

보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**

### <a name="details-table-view-for-the-sent-and-received-email-report"></a>보낸 메일 및 받은 전자 메일 보고서의 세부 정보 표 보기

항목 분석: **방향 보기에서 세부** 정보 **보기를** 아래쪽으로 **나누기를 선택하면** 다음 정보가 표시됩니다. 방향 보기를 선택하면 다음과 같은 정보가 표시됩니다.

- **날짜(UTC)**
- **Type**
- **방향**
- **메시지 수**

세부 정보 표 **보기에서** 필터를 클릭한 경우 다음 필터를 사용하여 결과를 수정할 수 있습니다.

- **시작 날짜** **및 끝 날짜**
- 방향 값
- Type 값

보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**

## <a name="top-senders-and-recipients-report"></a>상위 보낸 사람 및 받는 사람 보고서

보낸 **사람 과정에서 가장 많이 사용된** 보낸 사람 및 받는 사람" 보고서는 주요 전자 메일 보낸 사람 및 받는 사람을 나타내는 원형 차트입니다.

보고서를 보려면 보안 센터에서 [& 보고서 대시보드로](https://protection.office.com) **Reports** \> **이동한 후** 상단 **발신자와 받는 사람을 선택합니다.** 보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .

![보고서 대시보드의 상위 보낸 사람 및 받는 사람 위산 위과](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a>상위 보낸 사람 및 받는 사람 보고서에 대한 보고서 보기

보고서 보기에서는 다음 차트를 사용할 수 있습니다.

- **주요 메일 \> 보낸 사람을 위한 데이터 표시**
- **상위 메일 \> 수신자에 대한 데이터 표시**
- **스팸상을 \> 많이 받는 사람에 대한 데이터 표시**
- **다음에 대한 데이터 표시 \> 상위 맬웨어 받는** 사람(EOP)
- **다음에 대한 데이터 표시 \> ATP(상위 맬웨어 받는 사람)(Office** 365 ATP)

원형 차트의 구성은 이러한 선택에 따라 변경됩니다.

원형 차트에서 WEDGE를 가리면 보내거나 받은 메시지 수를 볼 수 있습니다.

보고서 보기에서 **필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**

![상위 보낸 사람 및 받는 사람 보고서 보고서보고서 보고서의 보고서 보기에 원형 차트](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a>맨 위의 보낸 사람 및 받는 사람 보고서의 세부 정보 표 보기

세부 정보 **표를 보기를**클릭하면 표시되는 정보는 검색 하고 있는 차트에 따라 달라지게 됩니다.

- **주요 메일 \> 보낸 사람을 위한 데이터 표시**

  - **주요 메일 보낸 사람**
  - **개수**

- **상위 메일 \> 수신자에 대한 데이터 표시**

  - **최상위 메일 받는 사람**
  - **개수**

- **스팸상을 \> 많이 받는 사람에 대한 데이터 표시**

  - **상위 스팸 받는 사람**
  - **개수**

- **다음에 대한 데이터 표시 \> 상위 맬웨어 받는** 사람(EOP)

  - **상위 맬웨어 받는 사람**
  - **개수**

- **다음에 대한 데이터 표시 \> ATP(상위 맬웨어 받는 사람)(Office** 365 ATP)

  - **상위 맬웨어 받는 사람(ATP)**
  - **개수**

세부 정보 **보기에서 필터를** 클릭한 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**

보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**

## <a name="what-permissions-are-needed-to-view-these-reports"></a>이러한 보고서를 보는 데 필요한 권한은 무엇입니까?

보고서를 보고 사용하려면 준수 센터 및 Exchange Online에서 보안 그룹의 & **합니다.**

- 새 & 센터에서 다음 역할 그룹 중 하나의 구성원이어야 합니다.

  -Organization Management -Security Administrator (Azure Active Directory 관리 센터에서도 이 [작업을 수행할 수 있나요)](https://aad.portal.azure.com) - 보안 읽기 권한자

  자세한 내용은 [보안 및 준수 센터의 사용 권한](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)을 참조하세요.

- Exchange Online에서는 다음 역할 그룹 중 하나의 구성원이어야 합니다.

  -Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management

자세한 내용은 [Exchange Online의 사용 권한을 사용하고](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) [Exchange Online의 역할 그룹 관리를 참조하세요.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)

## <a name="related-topics"></a>관련 항목

[보안 및 준수 센터의 스마트 보고서 및 인사이트](reports-and-insights-in-security-and-compliance.md)

[보안 및 준수 센터의 메일 흐름 파악](mail-flow-insights-v2.md)

[보안 및 준수 센터의 전자 메일 보안 보고서 보기](view-email-security-reports.md)

[Office 365 Advanced Threat Protection 보고서 보기](view-reports-for-atp.md)
