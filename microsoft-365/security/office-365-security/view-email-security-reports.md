---
title: 보안 및 준수 센터의 전자 메일 보안 보고서 보기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: 조직의 전자 메일 보안 보고서를 찾아 사용하는 방법에 대해 알아봅니다. 규정 준수 센터의 보안 센터에서 전자 & 보고서를 사용할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2b714d9dc4e3ca143d2cb2d7164f8c3c737d1928
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826508"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a>보안 및 준수 센터의 전자 메일 보안 보고서 보기

보안 & 준수 센터에서는 Microsoft 365의 [스팸](https://protection.office.com) 방지, 맬웨어 방지 및 암호화 기능과 같은 전자 메일 보안 기능이 조직을 보호하는 방식을 확인하는 데 도움이 되는 다양한 보고서가 있습니다. 필요한 권한이 있는 [경우 보고서 대시보드로](#what-permissions-are-needed-to-view-these-reports)이동하여 보안 센터에서 & **Reports** 수 \> **있습니다.** 보고서 대시보드로 직접 이동하려면 <https://protection.office.com/insightdashboard> .

![Security Center의 보고서 & 대시보드](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a>위검토된 사용자 보고서

> [!NOTE]
> Exchange Online 사서함이 있는 Microsoft 365 조직에서 이 보고서를 사용할 수 있습니다. 독립 실행형 EOP(Exchange Online Protection) 조직에서는 사용할 수 없습니다.

**위험에 당한 사용자 보고서에는** 지난 7일 동안 의심스러운 것으로 표시되거나 **Suspicious** **제한된 사용자 계정 수가** 표시됩니다. 이러한 상태 중 하나의 계정은 문제가 있거나 모두 노출됩니다. 자주 사용할 경우 보고서를 사용하여 의심스러운 스파이크나 제한된 계정에서 스파이크를 비출 수 있을지를 의심하고 추세를 일상할 수 있습니다. 손상된 사용자에 대한 자세한 내용은 [손상된 전자 메일 계정에 응답을 참조하세요.](responding-to-a-compromised-email-account.md)

![보고서 대시보드에서 위검토된 사용자 위산](../../media/compromised-users-report-widget.png)

집계 보기에는 지난 90일동안의 데이터가 표시되고 세부 정보 보기에는 지난 30일동안의 데이터가 표시될 수 있습니다.

보고서를 보려면 준수 [센터에서 & 다음](https://protection.office.com)보고서 **대시보드로** \> **이동하여** **위험한 사용자를 선택합니다.** 보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=CompromisedUsers> .

필터를 클릭하고 다음 값 중에서 하나 이상을 **선택하여** 차트 및 세부 정보 표를 모두 필터링할 수 있습니다.

- **시작 날짜** **및 끝 날짜**

- **의심스러운 경우:** 사용자 계정이 의심스러운 전자 메일을 전송하며 전자 메일을 보내지 않을 위험성이 있습니다.

- **제한됨:** 사용자 계정이 고의된 패턴으로 인해 메일을 보내지 않도록 제한되었습니다.

![위검토된 사용자 보고서의 보고서 보기](../../media/compromised-users-report-activity-view.png)

세부 정보 **표를 보기를 클릭한 경우에는**다음 세부 정보를 확인할 수 있습니다.

- **작성 시간**
- **사용자 ID**
- **작업**

보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**

## <a name="encryption-report"></a>암호화 보고서

암호화 **보고서는** EOP(Exchange Online 사서함이 있는 구독 또는 Exchange Online 사서함이 없는 독립 실행형 EOP 구독)에서 사용할 수 있습니다. 조직의 보안 팀은 이 보고서의 정보를 사용하여 중요한 전자 메일 메시지에 대한 패턴을 식별하고 정책을 적예로 적용하거나 조정할 수 있습니다. 예제:

- 사용자가 암호화하는 전자 메일 메시지가 다수 인 경우 특정 사용 사례에 대한 암호화를 자동화하는 암호화 정책을 추가할 수 있습니다. 자세한 내용은 [Microsoft 365에서 전자 메일 메시지를 암호화하기 위한 메일의 흐름 규정을 참조하세요.](../../compliance/define-mail-flow-rules-to-encrypt-email.md)

- 사용할 수 있는 암호화 템플릿이 여러 개 있지만 아무도 사용하는 사용자가 없는 경우 사용자가 기능 교육이 필요한지 여부를 알게 될 수 있습니다.

집계 보기에서는 지난 90일 동안의 필터링이 가능한 한 세부 정보 보기에서 10일 동안 필터링할 수 있습니다.

보고서를 보려면 준수 센터에서 [보안 & 보고서](https://protection.office.com)대시보드로 **이동한** \> **후 암호화** **보고서를 선택합니다.** 보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=EncryptionReport> .

암호화에 대한 자세한 내용은 [Microsoft 365에서 전자 메일 암호화를 참조하세요.](../../compliance/email-encryption.md)

### <a name="report-view-for-the-encryption-report"></a>암호화 보고서 보기

다음 필터를 차트에 사용할 수 있습니다.

- **데이터 보기: 메시지 암호화 보고서 및 분석** **방법: 다음과 같은**암호화 방법을 사용할 수 있습니다.

  - **사용자별 암호화**
  - **정책에 의한 암호화**

  필터를 **클릭하면 다음**필터를 사용하여 차트를 수정할 수 있습니다.

  - **시작 날짜** **및 끝 날짜**
  - 암호화 방법.
  - 암호화 서식 파일.

- **데이터 보기: 메시지 암호화 보고서 및 분석** **방법: 암호화 템플릿: 다음과**같은 암호화 방법을 사용할 수 있습니다.

  - **전달 안 합니다.**
  - **Encrypt only(암호화만 암호화)**
  - **OME 이전**
  - **사용자 지정**

  필터를 **클릭하면 다음**필터를 사용하여 차트를 수정할 수 있습니다.

  - **시작 날짜** **및 끝 날짜**
  - 암호화 방법
  - 암호화 템플릿

- **보기: 상위 5개의 받는 사람 도메인:** 이 보기에는 보낸 메시지 수가 상위 5명의 받는 사람 도메인에 대한 배달 보고서 수가 포함된 원형 차트가 표시됩니다.

  필터를 **클릭하면 시작**날짜와 종료 **날짜를** 선택할 **수 있습니다.**

### <a name="details-table-view-for-the-encryption-report"></a>암호화 보고서의 세부 정보 표 보기

세부 정보 **표를 보기를**클릭하면 표시되는 정보는 검색 하고 있는 차트에 따라 달라지게 됩니다.

- **분석: 암호화 방법 또는 분석** **방법: 암호화 서식 파일을**제공합니다. 암호화 서식 파일은 다음과 같은 정보를 표시합니다.

  - **날짜**
  - **보낸 사람 주소**
  - **암호화 템플릿**
  - **암호화 방법**
  - **받는 사람 주소**
  - **제목**

- **데이터 보기: 받는 사람 5개를 지정합니다.**

  - **날짜**
  - **받는 사람 도메인**
  - **메시지 수**
  
세부 정보 표 **보기에서** 필터를 클릭한 경우 다음 필터를 사용하여 결과를 수정할 수 있습니다.

- **시작 날짜** **및 끝 날짜**
- 암호화 방법
- 암호화 템플릿

보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**

## <a name="mailflow-status-report"></a>메일 흐름 상태 보고서

메일 **흐름 상태 보고서에는 맬웨어,** 스팸, 피싱 및 Edge 차단 메시지에 대한 정보가 들어 있습니다. 자세한 내용은 메일 흐름 상태 [보고서를 참조하세요.](view-mail-flow-reports.md#mailflow-status-report)

## <a name="malware-detections-in-email-report"></a>전자 메일 보고서의 맬웨어 검색

전자 **메일 보고서의 맬웨어 검색 에서는** 수신 및 보내는 전자 메일 메시지(Exchange Online Protection 또는 EOP에서 검색되는 맬웨어)에서 맬웨어 검색에 대한 정보를 보여 주는 정보가 표시됩니다. EOP의 맬웨어 보호 기능에 대한 자세한 내용은 [EOP에서 맬웨어 방지 보호 기능을 참조하세요.](anti-malware-protection.md)

 집계 보기 필터에서는 90일간을 사용할 수 있지만, 세부 정보 표시 테이블 필터는 10일 동안만 사용할 수 있습니다.

보고서를 보려면 보안 및 감사 [& 센터를 연 다음](https://protection.office.com)보고서 대시보드로 **Reports** \> **이동한** 후 전자 **메일의 맬웨어 검색을 선택합니다.** 보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=MalwareDetections> .

![보고서 대시보드에서 전자 메일 위로 스서비스의 맬웨어 감지](../../media/malware-detections-widget.png)

필터를 클릭하고 필터를 선택한 다음을 선택하여 차트 및 세부 **정보 표를 모두 필터링할** 수 있습니다.

- **시작 날짜** **및 끝 날짜**
- **인바운드**
- **아웃바운드**

![전자 메일 보고서의 맬웨어 검색에 보고서 보기](../../media/malware-detections-report-view.png)

세부 정보 **표를 보기를 클릭한 경우에는**다음 세부 정보를 확인할 수 있습니다.

- **날짜**
- **보낸 사람 주소**
- **받는 사람 주소**
- **메시지 ID**: 메시지 헤더의 **메시지 ID 헤더** 필드에서 사용할 수 있고 고유해야 합니다. 괄성에 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 주의해야 합니다(
- **제목**
- **파일 이름**
- **맬웨어 이름**

보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**

## <a name="sent-and-received-email-report"></a>보낸 메일 및 받은 전자 메일 보고서

보낸 **및 받은 전자 메일 보고서에는** 맬웨어, 스팸, 메일 흐름 규칙(전송 규칙이라고도 함) 및 전자 메일이 서비스를 받은 후의 고급 맬웨어 검색에 대한 정보가 포함되어 있습니다. 자세한 내용은 보낸 및 [받은 전자 메일 보고서를 참조하세요.](view-mail-flow-reports.md#sent-and-received-email-report)

## <a name="spam-detections-report"></a>스팸 검색 보고서

스팸 **검색 보고서에는** EOP에서 차단된 스팸 전자 메일 메시지가 표시됩니다. 메시지는 받는 사람별가 아치지 않은 개별적으로 계산됩니다. 예를 들어 동일한 스팸 메시지를 조직의 받는 사람 100명에게 전송한 경우 한 메시지로 계산됩니다.

집계 보기를 사용하면 90일 동안 필터링이 가능한 한 세부 정보 표시에는 10일 필터링이 허용됩니다.

보고서를 보려면 보안 및 [준수 센터를 & 보고서](https://protection.office.com) **대시보드로** \> **이동하여 스팸** **검색을 선택합니다.** 보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=SpamDetections> .

![보고서 대시보드의 스팸 감지 위산 위과](../../media/spam-detections-report-widget.png)

스팸 방지 보호 기능에 대한 자세한 내용은 [EOP의 스팸 방지 보호 기능을 참조하세요.](anti-spam-protection.md)

### <a name="report-view-for-the-spam-detections-report"></a>스팸 검색 보고서 보기

보고서 보기에서는 다음 차트를 사용할 수 있습니다.

- **분석: 작업:** 다음과 같은 이벤트 유형이 표시됩니다.

  - **스팸 콘텐츠 필터링됨**
  - **스팸 IP 블록**
  - **스팸 봉투 블록**
  - **스팸 DBEB 필터**: DBEB(디렉터리 기반 Edge 차단)

  차트에서 하루(데이터 요소)을 가리치하면 해당 날짜에 차단된 항목 및 분류된 항목의 수를 볼 수 있습니다.

  ![스팸 검색 보고서의 작업 보기](../../media/spam-detections-report-action-view.png)

- **아래로 나누기:** 다음지는 보여줍니다.

  - **인바운드**
  - **아웃바운드**

  ![스팸 감지 보고서 내의 방향 보기](../../media/spam-detections-report-direction-view.png)

보고서 보기에서 **필터를** 클릭한 경우 다음 필터를 사용하여 결과를 수정할 수 있습니다.

- **시작 날짜** **및 끝 날짜**
- 방향 값
- 이벤트 유형 값

### <a name="details-table-view-for-the-spam-detections-report"></a>스팸 검색 보고서의 세부 정보 표 보기

보고서 보기에서 **세부 정보 표를** 보기를 클릭하면 다음 정보가 표시됩니다.

- **날짜**
- **보낸 사람 주소**
- **받는 사람 주소**
- **이벤트 유형**
- **작업**
- **제목**

세부 정보 **표에서 필터를** 클릭한 경우 다음 필터를 사용하여 결과를 수정할 수 있습니다.

- **시작 날짜** **및 끝 날짜**
- 방향 값
- 이벤트 유형 값

보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**

## <a name="spoof-detections-report"></a>스푸핑 감지 보고서

**스푸핑 탐지 보고서에는** 검색된 스푸핑 메일 메시지의 수와 스푸핑 메일이 "좋은" 스푸핑하여 어떤 스푸핑도 가능합니다(합법적인 사업상의 이유로 스푸핑된 메일). 스푸핑에 대한 자세한 내용은 [EOP의 스푸핑 방지 보호 기능을 참조하세요.](anti-spoofing-protection.md)

보고서의 집계 보기에서는 90일 동안의 필터링이 허용되는 한편, 세부 정보 보기에는 10일 동안만 필터링이 허용됩니다.

보고서를 보려면 준수 센터에서 [&, 보고서](https://protection.office.com) **대시보드로** \> **이동하여 스푸핑** **감지를 선택합니다.** 보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=SpoofMailReport> .

![보고서 대시보드의 스푸핑 감지 위산](../../media/spoof-detections-widget.png)

차트에서 하루(데이터 요소)을 가리치면 특정 스푸핑 메일 메시지의 수를 확인할 수 있습니다.

필터를 클릭하고 다음 값 중에서 하나 이상을 **선택하여** 차트 및 세부 정보 표를 모두 필터링할 수 있습니다.

- **시작 날짜** **및 끝 날짜**

- **정상 메일**

- **스팸으로 Caught**

![스푸핑 감지 보고서의 보고서 보기](../../media/spoof-detections-report-view.png)

세부 정보 **표를 보기를 클릭한 경우에는**다음 세부 정보를 확인할 수 있습니다.

- **날짜**
- **스푸핑된 보낸 사람**
- **True - 한 사람**
- **보낸 사람 IP**
- **작업**
- **메시지 수**

보고서 보기로 돌아가려면 보고서 **보기를 클릭합니다.**

## <a name="threat-protection-status-report"></a>위협 방지 상태 보고서

위협 **방지 상태 보고서는** EOP와 Office 365 ATP에서 모두 사용할 수 있습니다. 그러나 보고서에는 서로 다른 데이터가 포함되어 있습니다. 예를 들어, EOP 고객은 전자 메일로 검색된 맬웨어에 대한 정보는 볼 수 있지만 [SharePoint Online, OneDrive 또는 Microsoft Teams에서](atp-for-spo-odb-and-teams.md)검색된 악성 파일에 대한 정보는 볼 수 없습니다.

이 보고서에서는 맬웨어 방지 엔진, [ZAP(제로](zero-hour-auto-purge.md)아우스 자동 제거) 및 ATP 안전 링크, [ATP](atp-safe-attachments.md)안전 첨부 파일 및 ATP 피싱 방지와 같은 [ATP](atp-safe-links.md)기능과 같은 악의적인 콘텐츠가 포함된 고유한 전자 메일 [메시지의 집계된 개수를 제공합니다.](set-up-anti-phishing-policies.md) 이 정보를 사용하여 추세를 확인하거나 조직 정책을 조정해야 하는지를 결정할 수 있습니다.

보고서를 보려면 보안 센터에서 [보안 & 보고서](https://protection.office.com)대시보드로 **Reports** \> **이동하여 위협 방지** **상태를 선택합니다.** 보고서로 직접 이동하려면 다음 URL 중 하나를 엽니다.

- Office 365 ATP: <https://protection.office.com/reportv2?id=ATPV2AggregateReport> .
- EOP: <https://protection.office.com/reportv2?id=ATPAggregateLightReport>

![보고서 대시보드의 위협 방지 상태 위구](../../media/threat-protection-status-report-widget.png)

기본적으로 차트는 지난 7일간의 데이터를 표시합니다. 필터를 **클릭하는 경우**90일 날짜 범위를 선택할 수 있습니다(평가판 구독은 30일로 제한될 수 있습니다). 세부 정보 표 보기에서는 30일 동안 필터링할 수 있습니다.

### <a name="report-view-for-the-threat-protection-status-report"></a>위협 방지 상태 보고서 보고서 보기

다음과 같은 보기를 사용할 수 있습니다.

- **다음 단계별로 데이터 보기:** 개요: 다음 검색 정보가 표시됩니다.

  - **전자 메일 맬웨어**
  - **전자 메일 피싱**
  - **콘텐츠 맬웨어**

  ![위협 방지 상태 보고서의 개요 보기](../../media/threat-protection-status-report-overview-view.png)

- **다음을 참조: Content(데이터 보기) \> 맬웨어**<sup>1:</sup>Office 365 ATP 조직에 대한 다음 정보가 표시됩니다.

  - **맬웨어 방지 엔진**
  - **파일 소수자**

  ![위협 방지 상태 보고서의 콘텐츠 맬웨어 보기](../../media/threat-protection-status-report-content-malware-view.png)

- **분석: 검색 기술 및 데이터 보기:** **이메일 \> 피싱: 다음**정보가 표시됩니다.

  - **ATP에서 생성된 URL 신뢰도**<sup>1</sup>
  - **고급 피싱 필터**
  - **스푸핑 방지: DMARC 실패**
  - **스푸핑 방지: 구성 내**
  - **스푸핑 방지: 외부 도메인**
  - **브랜드 가장**
  - **도메인 가장**<sup>1</sup>
  - **EOP URL 신뢰도**
  - **일반 피싱 필터**
  - **기타**
  - **피싱 ZAP**<sup>2</sup>
  - **URL 표시**<sup>1</sup>
  - **사용자 가장**<sup>1</sup>

  ![위협 방지 상태 보고서에서 피싱 전자 메일에 대한 감지 기술 보기](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- **분석: 검색 기술 및 데이터 보기:** **이메일 맬웨어: \> **다음 정보가 표시됩니다.

  - **ATP에서 생성한 파일 평명도**<sup>1</sup>
  - **맬웨어 방지 엔진**<sup>1</sup>
  - **맬웨어 방지 정책 파일 형식 차단**
  - **파일 소수**<sup>자전</sup>
  - **악성 파일 평뢰도**
  - **맬웨어 ZAP**<sup>2</sup>
  - **기타**

  ![위협 방지 상태 보고서에서 맬웨어에 대한 검색 기술 보기](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- **분석: 다음 단계에 따라 정책 유형** 및 **데이터 보기: 전자 메일 \> 피싱** 또는 **데이터 \> 보기:** 다음 정보가 표시됩니다.

  - **맬웨어 방지**
  - **안전한 첨부 파일**<sup>1</sup>
  - **피싱 방지**
  - **스팸 방지**
  - **메일 흐름 규칙(전송** 규칙이라고도 함)
  - **기타**

  ![위협 방지 상태 보고서에서 피싱 전자 메일에 대한 정책 유형 보기](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- **단계별로 분석: 전자 메일 피싱** **또는 \> ** 데이터 보기: 전자 메일 **맬웨어: \> **다음 정보가 표시됩니다.

  - **배달하지 못함**
  - **놓기**
  - **Forwarded**
  - **호스트된 사서함: 사용자 지정 폴더**
  - **Hosted mailbox: 삭제된 항목**
  - **호스트된 사서함: 받은 편지함**
  - **Hosted mailbox: Junk**
  - **온-프레미스 서버: 전달됨**
  - **격리**

  ![위협 방지 상태 보고서에서 피싱 전자 메일에 대한 배달 상태 보기](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<sup>1</sup> Office 365 ATP만

<sup>독립</sup> 실행형 EOP에서는 2시간제 자동 제거(ZAP)를 사용할 수 없습니다(Exchange Online 사서함에서만 작동).

필터를 **클릭하면 다음과**같은 필터를 사용하여 보고서를 수정할 수 있습니다.

- **시작 날짜** **및 끝 날짜**
- 검색 값
- **보호(Office** 365 ATP만 해당): **ATP 또는** **EOP** 콘텐츠 맬웨어: 데이터 보기에서는 필터링 가능한 **속성을 사용할 수 \> 없습니다.**

### <a name="details-table-view-for-the-threat-protection-status-report"></a>위협 방지 상태 보고서의 세부 정보 표 보기

세부 정보 **표를 보기를**클릭하면 표시되는 정보는 검색 하고 있는 차트에 따라 달라지게 됩니다.

- **다음을 참조: Content(데이터 보기) \> 맬웨어**:

  - **날짜**
  - **위치**
  - **지시문**
  - **맬웨어 이름**

- **View data by: Overview**: No **View details table** button is available.

- 기타 모든 차트:

  - **날짜**
  - **제목**
  - **보낸 사람**
  - **받는 사람**
  - **감지함**
  - **배달 상태**
  - **위출 출스**

필터를 **클릭하면 다음과**같은 필터를 사용하여 보고서를 수정할 수 있습니다.

- **시작 날짜** **및 끝 날짜**
- 검색 값
- **보호(Office** 365 ATP만 해당): **ATP 또는** **EOP** 콘텐츠 맬웨어: 데이터 보기에서는 필터링 가능한 **속성을 사용할 수 \> 없습니다.**

## <a name="top-malware-report"></a>상위 맬웨어 보고서

상위 **맬웨어 보고서는** EOP의 맬웨어 방지 보호에서 검색된 다양한 종류의 [맬웨어를 보여주는 기능입니다.](anti-malware-protection.md)

보고서를 보려면 규정 준수 센터에서 [보안 & 보고서](https://protection.office.com)대시보드로 **이동한** \> **후 상위** **맬웨어를 선택합니다.** 보고서로 직접 이동하려면 <https://protection.office.com/reportv2?id=TopMalware> .

![보고서 대시보드의 상위 맬웨어 위조](../../media/top-malware-report-widget.png)

원형 차트에서 WEDGE를 가리치면 맬웨어의 이름을 보고 해당 맬웨어가 포함된 경우 감지된 메시지 수를 볼 수 있습니다.

![상위 맬웨어 보고서 보기](../../media/top-malware-report-view.png)

세부 정보 **표를 보기를 클릭한 경우에는**다음 세부 정보를 확인할 수 있습니다.

- **상위 맬웨어**
- **개수**

보고서 보기 **나서 보기 보기에서** 필터를 클릭하는 경우 시작 날짜와 종료 날짜로 날짜 **범위를** 지정할 **수 있습니다.**

## <a name="url-threat-protection-report"></a>URL 위협 방지 보고서

**URL 위협 방지 보고서는** Office 365 ATP(Advanced Threat Protection)에서 사용할 수 있습니다. 자세한 내용은 URL 위협 [방지 보고서를 참조하세요.](view-reports-for-atp.md#url-threat-protection-report)

## <a name="user-reported-messages-report"></a>사용자가 보고한 메시지 보고서

사용자가 **보고한 메시지 보고서에는** 사용자가 보고서 메시지 추가 기능을 사용하여 정크 메일, 피싱 시도 또는 좋은 메일로 보고한 전자 [메일 메시지에 대한 정보가 표시됩니다.](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)

배달 상시 예정(스팸 정책 예외 또는 조직에 대해 구성된 메일 흐름 규칙과 같은 배달 이유 포함)에 대해 정보가 표시됩니다. 세부 정보를 보려면 사용자 보고서 목록에서 항목을 선택한 다음 요약 및 세부 정보 **탭에서 정보를** **확인합니다.**

![사용자 보고 메시지 보고서에는 정크 메일 또는 피싱 시도가 아님으로 지정된 메시지가 표시됩니다.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

이 보고서를 보려면 보안 [서비스 & 센터에서](https://protection.office.com)다음 중 하나를 수행합니다.

- 위협 **관리 대시보드** \> **Dashboard** \> **사용자가 보고한 메시지로 이동합니다.**

- 위협 **관리 사용자가** \> **보고한** \> **메시지로 이동합니다.**

![In the Security & Compliance Center, choose Threat management \> Review \> User reported messages](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> 사용자가 보고한 메시지 보고가 제대로 작동하려면 Office 365 **환경에 대해 감사** 로깅을 설정되어 있는 상태가 되어야 합니다. 일반적으로 감사 로그 역할이 Exchange Online에 할당된 누누가 이 작업을 수행합니다. 자세한 내용은 [Microsoft 365 감사 로그 검색 설정 또는 해제를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)

## <a name="what-permissions-are-needed-to-view-these-reports"></a>이러한 보고서를 보는 데 필요한 권한은 무엇입니까?

보고서를 보고 사용하려면 준수 센터 및 Exchange Online에서 보안 그룹의 & **합니다.**

- 새 & 센터에서 다음 역할 그룹 중 하나의 구성원이어야 합니다.

  -Organization Management -Security Administrator (Azure Active Directory 관리 센터에서도 이 [작업을 수행할 수 있나요)](https://aad.portal.azure.com) - 보안 읽기 권한자

  자세한 내용은 [보안 및 준수 센터의 사용 권한](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)을 참조하세요.

- Exchange Online에서는 다음 역할 그룹 중 하나의 구성원이어야 합니다.

  -Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management

자세한 내용은 [Exchange Online의 사용 권한을 사용하고](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) [Exchange Online의 역할 그룹 관리를 참조하세요.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)

## <a name="what-if-the-reports-arent-showing-data"></a>보고서에 데이터가 표시되지 않는 경우 어떻게 해야 할까요?

보고서에 데이터가 표시되지 않으면 정책이 올바르게 설정되었는지 다시 확인합니다. 자세한 내용은 [위협으로부터 보호를 참조하세요.](protect-against-threats.md)

## <a name="related-topics"></a>관련 항목

[EOP의 스팸 방지 및 맬웨어 방지 보호 기능](anti-spam-and-anti-malware-protection.md)

[보안 및 준수 센터의 스마트 보고서 및 인사이트](reports-and-insights-in-security-and-compliance.md)

[보안 및 준수 센터에서 & 보고서 보기](view-mail-flow-reports.md)

[Office 365 Advanced Threat Protection 보고서 보기](view-reports-for-atp.md)
