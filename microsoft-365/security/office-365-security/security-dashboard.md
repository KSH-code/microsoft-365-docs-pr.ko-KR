---
title: 보안 대시보드 개요
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 새 보안 대시보드를 사용하여 위협 방지 Office 365 검토하고 보안 경고를 보고 이에 대한 행동을 할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 18cde7063e8a25426b56ee184b71408016a6116d
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59189089"
---
# <a name="security-dashboard-in-the-security--compliance-center"></a>보안 및 준수 센터의 & 대시보드

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a>기본 기능 및 보안 대시보드를 여는 방법

보안 & 준수 센터를 통해 조직에서 데이터 보호 및 규정 <https://protection.office.com> 준수를 관리할 수 있습니다. 필요한 권한이 있는 경우 보안 대시보드를 통해 위협 방지 상태를 검토하고 보안 경고를 보고 이에 대한 행동을 할 수 있습니다.

비디오를 시청하여 개요를 확인한 다음 이 문서를 읽고 자세한 내용을 확인할 수 있습니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

조직의 구독에 포함된 내용에 따라 보안 대시보드에는 다음 섹션에 설명된 위협 관리 요약, 위협 방지 상태, 전역 주간 위협 감지, 맬웨어 등의 여러 위젯이 포함됩니다.

보안 및 준수 센터에서 보안 대시보드를 & 위협 관리  대시보드로 \> **이동하세요.** 보안 대시보드로 직접 이동하기 위해 를 <https://protection.office.com/searchandinvestigation/dashboard> 사용하세요.

> [!NOTE]
> 보안 대시보드를 표시하려면 전역 관리자, 보안 관리자 또는 보안 읽기 권한자 되어야 합니다. 일부 위젯을 사용하려면 추가 사용 권한이 필요합니다. 자세한 내용은 보안 및 준수 센터의 사용 [& 참조합니다.](permissions-in-the-security-and-compliance-center.md)

## <a name="threat-management-summary"></a>위협 관리 요약

위협 관리 요약 위젯은 지난 7일 동안 조직이 위협으로부터 보호된 방법을 한눈에 알 수 있습니다.

![보안 대시보드 - 위협 관리 요약 위젯.](../../media/SecDash-ThreatMgmtSummary.png)

위협 관리 요약에 표시될 정보는 구독에 포함된 내용에 따라 다를 수 있습니다. 다음 표에서는 사용자 및 사용자에 대해 포함된 Office 365 E3 Office 365 E5.

<br>

****

|Office 365 E3|Office 365 E5|
|---|---|
|차단된 맬웨어 메시지<br>피싱 메시지 차단<br>사용자가 보고한 메시지<br><br><br><br>|차단된 맬웨어 메시지<br>피싱 메시지 차단<br>사용자가 보고한 메시지<br>제로 데이 맬웨어 차단<br>검색된 고급 피싱 메시지<br>악의적인 URL 차단|
|

위협 관리 요약 위젯을 보거나 액세스하려면 보고서에 대한 Defender를 볼 Office 365 있어야 합니다. 자세한 내용은 [보고서용 Defender를](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)보는 데 필요한 사용 권한을 Office 365 참조하세요.

## <a name="threat-protection-status"></a>위협 방지 상태

위협 방지 상태 위젯은 피싱 및 맬웨어의 추세적이고 상세한 보기로 위협 방지 효과를 보여줍니다.

![위협 방지 상태 위젯.](../../media/tpswidget.png)

세부 정보는 Microsoft 365 구독에 Microsoft Defender for [Exchange Online Protection(EOP)를](exchange-online-protection-overview.md) 포함하는지 여부에 [따라 Office 365.](defender-for-office-365.md)

<br>

****

|구독에 포함된 경우...|이러한 세부 정보가 표시|
|---|---|
|EOP는 있지만 Microsoft Defender for Office 365|EOP에서 검색 및 차단된 악성 전자 메일입니다.<p> [EOP(위협 방지 상태 보고서)를 참조합니다.](view-email-security-reports.md#threat-protection-status-report)|
|Office 365용 Microsoft Defender|EOP 및 Defender에서 악의적인 콘텐츠 및 악의적인 전자 메일을 검색하고 Office 365 <p> 맬웨어 방지 [엔진에](zero-hour-auto-purge.md)의해 차단되는 악의적인 콘텐츠가 있는 고유한 전자 메일 메시지의 집계된 수입니다(맬웨어 방지 엔진, 제로 아워 자동 제거 및 Office 365 기능에 대한 Defender(금고 [링크,](safe-links.md)금고 [첨부](safe-attachments.md)파일 및 [defender for Office 365).](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) <p> [위협 방지 상태 보고서를 참조합니다.](view-reports-for-mdo.md#threat-protection-status-report)|
|

위협 방지 상태 위젯을 보거나 액세스하려면 보고서에 대한 Defender를 볼 Office 365 있어야 합니다. 자세한 내용은 Defender for Office 365 [참조하세요.](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

## <a name="global-weekly-threat-detections"></a>Global Weekly Threat Detections

Global Weekly Threat Detections 위젯은 지난 7일 동안 전자 메일 메시지에서 감지된 위협의 수를 보여줍니다.

![전역 주간 위협 감지 위젯.](../../media/globalweeklythreatdetections.png)

메트릭은 다음 표에 설명된 바와 같이 계산됩니다.

<br>

****

|메트릭|계산 방법|
|---|---|
|검사한 메시지|검사한 전자 메일 메시지 수에 받는 사람 수를 곱한 수|
|위협 중지됨|맬웨어가 포함된 것으로 확인된 전자 메일 메시지 수에 받는 사람 수를 곱합니다.|
|2016에 [대해 Defender가 Office 365](defender-for-office-365.md)|Defender에서 차단한 전자 메일 메시지 Office 365 수에 받는 사람 수를 곱합니다.|
|배달 후 제거됨|[ZAP(제로](zero-hour-auto-purge.md) 아워 자동 제거)에 받는 사람 수를 곱하여 제거된 메시지 수|
|

## <a name="malware"></a>맬웨어

맬웨어 위젯은 지난 7일 동안의 맬웨어 추세 및 맬웨어 패밀리 유형에 대한 세부 정보를 보여 주며,

![맬웨어 추세 및 패밀리 유형](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a>인사이트

Insights 주요 문제를 표면화할 뿐만 아니라 고려할 권장 사항 및 작업도 포함됩니다.

![똑똑한 인사이트.](../../media/smartinsights.png)

예를 들어 일부 사용자가 정크 메일 옵션을 사용하지 않도록 설정하여 피싱 전자 메일 메시지가 배달되는 것을 볼 수 있습니다. 인사이트 작동 방식에 대한 자세한 내용은 Security & Compliance Center에서 보고서 [및 정보를 참조합니다.](reports-and-insights-in-security-and-compliance.md)

## <a name="threat-investigation-and-response"></a>위협 조사 및 응답

조직의 구독에 Microsoft [Defender for Office 365 계획 2가](office-365-ti.md)포함되어 있는 경우 보안 대시보드에는 고급 위협 조사 및 응답 도구가 포함된 섹션이 있습니다. 이러한 도구에는 [자동화된 조사 및 응답 기능이 포함됩니다.](automated-investigation-response-office.md) 자동화된 조사 및 대응은 손상된 사용자 계정을 신속하게 해결하는 등의 [시나리오에서 유용할 수 있습니다.](address-compromised-users-quickly.md)

자세한 내용은 에서 자동화된 조사 및 [대응(AIR)](office-365-air.md)사용 시작을 Office 365.

## <a name="trends"></a>추세

보안 대시보드 아래쪽에는 조직의  전자 메일 흐름 추세를 요약하는 추세 섹션이 있습니다. 보고서는 스팸, 맬웨어, 피싱 시도 및 양호한 전자 메일로 분류된 전자 메일에 대한 정보를 제공합니다. 보고서에서 더 자세한 정보를 보려면 타일을 클릭합니다.

![추세 섹션에는 조직의 전자 메일 흐름 추세가 요약됩니다.](../../media/trends.png)

또한 조직의 구독에 Office 365 [계획 2용 Defender가](office-365-ti.md)포함되어 있는 경우  보안 팀이 우선 순위가 높은 보안 경고를 보고 조치를 취할 수 있도록 하는 최근 위협 관리 경고 보고서도 이 섹션에 표시됩니다.

보내고 받은 전자 메일 위젯을 보거나 액세스하려면 보고서에 대한 Defender를 볼 Office 365 있어야 합니다. 자세한 내용은 [보고서용 Defender를](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)보는 데 필요한 사용 권한을 Office 365 참조하세요.

최근 위협 관리 경고 위젯을 보거나 액세스하려면 경고를 볼 수 있는 권한이 있어야 합니다. 자세한 내용은 경고를 보는 데 필요한 [RBAC 권한을 참조합니다.](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)

## <a name="related-articles"></a>관련 문서

[보안 및 준수 센터의 전자 메일 보안 보고서 보기](view-email-security-reports.md)

[Microsoft Defender for Office 365](view-reports-for-mdo.md)

[Office 365용 Defender](defender-for-office-365.md)

[Office 365 위협 조사 및 대응](office-365-ti.md)
