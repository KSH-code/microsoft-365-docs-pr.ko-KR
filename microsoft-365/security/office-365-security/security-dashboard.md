---
title: 보안 대시보드 개요
f1.keywords:
- NOCSH
ms.author: siosulli
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 새 보안 대시보드를 사용 하 여 Office 365 위협 방지 상태를 검토 하 고 보안 경고를 보고 작동 합니다.
ms.openlocfilehash: b49422621e70d597251cd342559e59ffa0e128f6
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877328"
---
# <a name="security-dashboard"></a>보안 대시보드

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a>기본 기능 및 보안 대시보드를 여는 방법

[보안 & 준수 센터](../../compliance/go-to-the-securitycompliance-center.md) 를 통해 조직에서 데이터 보호 및 규정 준수를 관리할 수 있습니다. 필요한 사용 권한이 있는 경우 보안 대시보드를 사용 하 여 위협 방지 상태를 검토 하 고 보안 경고에 대 한 작업을 수행할 수 있습니다.

비디오를 시청 하 여 개요를 확인 한 다음이 문서를 참조 하 여 자세한 내용을 확인 하세요.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

조직의 구독에 포함 된 내용에 따라 보안 대시보드에는 다음 섹션에 설명 된 것 처럼 위협 관리 요약, 위협 방지 상태, 전역 주간 위협 감지, 맬웨어 등의 여러 widget이 포함 됩니다.

보안 대시보드를 보려면 [보안 & 준수 센터](../../compliance/go-to-the-securitycompliance-center.md)에서 **위협 관리** \> **대시보드로** 이동 합니다.

> [!NOTE]
> 보안 대시보드를 보려면 전역 관리자, 보안 관리자 또는 보안 독자 여야 합니다. 일부 위젯을 보려면 추가 권한이 필요 합니다. 자세한 내용은 [Security & 준수 센터의 사용 권한을](permissions-in-the-security-and-compliance-center.md)참조 하세요.

## <a name="threat-management-summary"></a>위협 관리 요약

위협 관리 요약 위젯은 지난 7 일 동안 위협 으로부터 조직이 보호 된 방식을 한눈에 보여 줍니다.

![보안 대시보드-위협 관리 요약 위젯](../../media/SecDash-ThreatMgmtSummary.png)

위협 관리 요약에 표시 되는 정보는 구독에 포함 된 항목에 따라 달라 집니다. 다음 표에는 Office 365 E3 및 Office 365 E5에 포함 된 정보에 대 한 설명이 나와 있습니다.

|Office 365 E3|Office 365 E5|
|---|---|
|차단 된 맬웨어 메시지<br/>차단 된 피싱 메시지<br>사용자가 보고 한 메시지<br><br><br><br>|차단 된 맬웨어 메시지<br>차단 된 피싱 메시지<br>사용자가 보고 한 메시지<br>제로 일 맬웨어 차단<br>검색 된 고급 피싱 메시지<br>차단 된 악의적인 Url|

위협 관리 요약 위젯을 보거나 액세스 하려면 Defender for Office 365 reports를 볼 수 있는 권한이 있어야 합니다. 자세한 내용은 [어떤 사용 권한으로 Defender For Office 365 reports?를 확인 해야 합니까?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)를 참조 하십시오.

## <a name="threat-protection-status"></a>위협 방지 상태

위협 방지 상태 위젯은 피싱 및 맬웨어 추이에 대 한 경향 및 상세 보기로 위협 보호 효과를 표시 합니다.

![위협 방지 상태 위젯](../../media/tpswidget.png)

자세한 내용은 365 Microsoft [Defender For Office 365](office-365-atp.md)이 포함 되어 있는지 여부에 따라 사용 하는 EOP ( [Exchange Online Protection](exchange-online-protection-overview.md) )에 대해 설명 합니다.

|구독에 다음이 포함 된 경우 ...|다음 정보가 표시 됩니다.|
|---|---|
|EOP 이지만 Office 용 Microsoft Defender 365이 아님|EOP에서 검색 하 고 차단한 악성 전자 메일입니다.<br><br> [위협 방지 상태 보고서 (EOP)](view-email-security-reports.md#threat-protection-status-report)를 참조 하세요.|
|Microsoft Defender for Office 365|EOP 및 Office 365 용 Defender에서 검색 및 차단 된 악의적인 콘텐츠 및 악성 전자 메일<br><br>맬웨어 방지 엔진에 의해 차단 되는 악성 콘텐츠가 포함 된 고유 전자 메일 메시지의 집계 횟수, [영 자동 제거](zero-hour-auto-purge.md)및 office 365 기능 ( [안전 링크](atp-safe-links.md), [안전한 첨부 파일](atp-safe-attachments.md), [defender for office 365의 사전 피싱](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365))<br><br>[위협 방지 상태 보고서](view-reports-for-atp.md#threat-protection-status-report)를 참조 하세요.|

위협 방지 상태 위젯을 보거나 액세스 하려면 Defender for Office 365 보고서용 보기 권한이 있어야 합니다. 자세한 내용은 [어떤 권한이 있는지 Defender For Office 365 reports를 확인 하는 데 필요한 사용 권한을](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports) 참조 하세요.

## <a name="global-weekly-threat-detections"></a>전역 주간 위협 감지

전체 주간 위협 감지 위젯은 지난 7 일 동안 전자 메일 메시지에서 검색 된 위협의 수를 보여 줍니다.

![전역 주간 위협 감지 위젯](../../media/globalweeklythreatdetections.png)

메트릭은 다음 표에 설명 된 대로 계산 됩니다.

|메트릭|계산 방법|
|---|---|
|검색 된 메시지|검색 된 전자 메일 메시지의 수를 받는 사람 수에 곱하여 함|
|위협이 중지 됨|맬웨어를 포함 하는 것으로 식별 되는 전자 메일 메시지 수 (받는 사람 수)|
|[Defender For Office 365에 대해](office-365-atp.md) 차단 됨|Defender for Office 365에 받는 사람 수를 곱하여 차단 된 전자 메일 메시지 수|
|배달 후 제거 됨|[자동 삭제](zero-hour-auto-purge.md) 를 통해 제거 되는 메시지 수를 받는 사람 수 곱하여|

## <a name="malware"></a>맬웨어

맬웨어 위젯은 지난 7 일 동안의 맬웨어 추세 및 맬웨어 패밀리 유형에 대 한 세부 정보를 표시 합니다.

![맬웨어 추세 및 패밀리 유형](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a>인사이트

자세한 내용은 검토 해야 하는 주요 문제 뿐 아니라 권장 사항과 고려할 작업도 포함 되어 있습니다.

![고급 통찰력](../../media/smartinsights.png)

예를 들어 일부 사용자가 정크 메일 옵션을 사용 하지 않도록 설정 했으므로 피싱 전자 메일 메시지가 배달 되는 것을 볼 수 있습니다. Insights 작동 방식에 대 한 자세한 내용은 [Security & 준수 센터의 Reports and insights](reports-and-insights-in-security-and-compliance.md)를 참조 하십시오.

## <a name="threat-investigation-and-response"></a>위협 조사 및 응답

조직의 구독에  [Office 365 계획 2 용 Microsoft Defender](office-365-ti.md)가 포함 되어 있는 경우 보안 대시보드에 advanced threat 조사한 및 응답 도구가 포함 된 섹션이 있습니다. 이러한 도구에는 [자동화 된 조사 및 응답 기능이](automated-investigation-response-office.md)포함 되어 있습니다. 자동화 된 조사 및 응답은 [손상 된 사용자 계정에 빠르게 주소를 지정](address-compromised-users-quickly.md)하는 등의 시나리오에서 유용할 수 있습니다.

자세한 내용은 [Office 365에서 자동 조사 및 응답을 사용 하 여 시작](office-365-air.md)하기를 참조 하세요.

## <a name="trends"></a>추세

보안 대시보드 아래쪽에는 조직에 대 한 전자 메일 흐름 추세를 요약 하는 **추세** 섹션을 소개 합니다. 보고서는 스팸으로 분류 된 전자 메일, 맬웨어, 피싱 시도 및 좋은 전자 메일에 대 한 정보를 제공 합니다. 타일을 클릭 하 여 보고서에서 자세한 정보를 볼 수 있습니다.

![조직에 대 한 전자 메일 흐름 추세를 요약 하는 추세 섹션](../../media/trends.png)

또한 조직의 구독에 [Office 365 계획 2에 대 한 Defender](office-365-ti.md)가 포함 되어 있는 경우 보안 팀이 우선 순위가 높은 보안 경고에 대 한 작업을 확인 하 고 수행할 수 있도록 하는 **최근 위협 관리 경고** 보고서가이 섹션에 포함 됩니다.

보내고 받은 전자 메일 위젯을 보거나 액세스 하려면 Defender for Office 365 reports에 대 한 사용 권한이 있어야 합니다. 자세한 내용은 [어떤 사용 권한으로 Defender For Office 365 reports?를 확인 해야 합니까?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)를 참조 하십시오.

최신 위협 관리 알림 위젯을 보거나 액세스 하려면 알림을 볼 수 있는 권한이 있어야 합니다. 자세한 내용은 [경고를 보는 데 필요한 RBAC 사용 권한을](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)참조 하세요.

## <a name="related-topics"></a>관련 항목

[보안 및 준수 센터의 전자 메일 보안 보고서 보기](view-email-security-reports.md)

[Microsoft Defender for Office 365에 대 한 보고서 보기](view-reports-for-atp.md)

[Office 365용 Microsoft Defender](office-365-atp.md)

[Office 365 위협 조사 및 응답](office-365-ti.md)
