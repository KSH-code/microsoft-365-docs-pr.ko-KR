---
title: Microsoft Defender for Office 365
keywords: AIR, autoIR, Endpoint용 Microsoft Defender, 자동화, 조사, 대응, 수정, 위협, 고급, 위협, 보호
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft Defender for Office 365.
ms.date: 04/30/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c994783506f1ba8bc2807b7261d98303cc72f76b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60196660"
---
# <a name="remediation-actions-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="remediation-actions"></a>수정 작업

Microsoft [Defender](defender-for-office-365.md) for Office 365 수정 작업이 포함되어 있습니다. 이러한 수정 작업은 다음을 포함할 수 있습니다.

- 전자 메일 메시지 또는 클러스터의 일시 삭제
- 차단 URL(클릭 시간)
- 외부 메일 전달 해제
- 위임 해제

Microsoft Defender for Office 365 수정 작업은 자동으로 수행되지 않습니다. 대신, 수정 작업은 조직의 보안 운영 팀의 승인이 있는 경우만 수행됩니다.

## <a name="threats-and-remediation-actions"></a>위협 및 수정 작업

Microsoft Defender for Office 365 다양한 위협을 해결하기 위한 수정 작업이 포함되어 있습니다. 자동화된 조사를 수행하면 검토 및 승인할 수정 작업이 하나 이상 수행되는 경우가 종종 있습니다. 경우에 따라 자동화된 조사가 특정 수정 작업을 수행하지 않는 경우도 있습니다. 추가로 조사하고 적절한 조치를 취하기 위해 다음 표의 지침을 사용하세요.

|범주|위협/위험|수정 작업|
|:---|:---|:---|
|전자 메일|맬웨어|전자 메일/클러스터 소프트 삭제 <p> 클러스터에 맬웨어가 포함된 전자 메일 메시지 수가 5개 이상인 경우 클러스터는 악성으로 간주됩니다.|
|전자 메일|악성 URL <br> (링크에서 악성 [URL을 금고 검색되었습니다.](safe-links.md)|전자 메일/클러스터 소프트 삭제 <br> URL 차단(클릭 시간 확인) <p> 악의적인 URL이 포함된 전자 메일은 악의적인 것으로 간주됩니다.|
|전자 메일|피싱|전자 메일/클러스터 소프트 삭제 <p> 클러스터의 여러 전자 메일 메시지에 피싱 시도가 포함된 경우 전체 클러스터는 피싱 시도로 간주됩니다.|
|전자 메일|Zapped 피싱 <br> (전자 메일 메시지가 배달된 다음 [zapped](zero-hour-auto-purge.md).)|전자 메일/클러스터 소프트 삭제 <p> 보고서는 zapped 메시지를 볼 수 있습니다. [ZAP에서 메시지 및 FAQ를 이동한지 확인](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message)|
|전자 메일|사용자가 보고한 [부재](enable-the-report-message-add-in.md) 중 피싱 전자 메일|[사용자 보고서에 의해 트리거된 자동화된 조사](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|전자 메일|볼륨 이상 <br> 최근 전자 메일 수량은 일치 조건에 대해 이전 7~10일을 초과합니다.|자동화된 조사는 특정 보류 중인 작업을 수행하지 않습니다. <p>볼륨 이상은 명확한 위협이 아니라 지난 7~10일과 비교할 때 최근일의 더 큰 전자 메일 볼륨을 나타냈기만 합니다. <p>전자 메일이 대량으로 발생할 수 있는 문제를 나타낼 수 있는 경우 악의적인 판정이나 전자 메일 메시지/클러스터의 수동 검토 측면에서 확인이 필요합니다. 배달된 의심스러운 전자 메일 [찾기를 참조하세요.](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered)|
|전자 메일|위협이 발견되지 않음 <br> 시스템에서 파일, URL 또는 전자 메일 클러스터 결과 분석에 기반한 위협을 찾지 못했습니다.|자동화된 조사는 특정 보류 중인 작업을 수행하지 않습니다. <p>조사가 완료된 후 [발견](zero-hour-auto-purge.md) 및 잠기는 위협은 조사의 수치적 발견에 반영되지 않지만 위협 탐색기에서는 이러한 위협을 볼 [수 있습니다.](threat-explorer.md)|
|사용자|사용자가 악성 URL을 클릭한 경우 <br> (사용자가 나중에 악의적인 것으로 확인된 페이지로 이동하거나 사용자가 악의적인 페이지로 이동하기 위해 금고 [링크](safe-links.md#warning-pages-from-safe-links) 경고 페이지를 무시했습니다.)|자동화된 조사는 특정 보류 중인 작업을 수행하지 않습니다. <p> 차단 URL(클릭 시간) <p> 위협 탐색기를 사용하여 URL에 대한 데이터를 [보고 판정을 클릭합니다.](threat-explorer.md#view-phishing-url-and-click-verdict-data) <p> 조직에서 [끝점용 Microsoft Defender를](/windows/security/threat-protection/) [](/microsoft-365/security/defender-endpoint/investigate-user) 사용하는 경우 사용자를 조사하여 계정이 손상된지 여부를 확인하는 것이 있습니다.|
|사용자|사용자가 맬웨어/피싱을 보내고 있습니다.|자동화된 조사는 특정 보류 중인 작업을 수행하지 않습니다. <p> 사용자가 맬웨어/피싱을 보고하거나 공격의 [](anti-spoofing-protection.md) 일부로 사용자를 스푸핑할 수 있습니다. 위협 [탐색기를](threat-explorer.md) 사용하여 맬웨어 또는 피싱이 포함된 [전자](threat-explorer-views.md#email--malware) 메일을 보고 [처리합니다.](threat-explorer-views.md#email--phish)|
|사용자|전자 메일 전달 <br> 사서함 전달 규칙이 구성되면 chch를 데이터 유출에 사용할 수 있습니다.|전달 규칙 제거 <p> 자동 [후원](mail-flow-insights-v2.md)메시지 보고서를 [](mfi-auto-forwarded-messages-report.md)비롯한 메일 흐름 정보를 사용하여 전달된 전자 메일에 대한 보다 구체적인 세부 정보를 볼 수 있습니다.|
|사용자|전자 메일 위임 규칙 <br> 사용자 계정에 위임이 설정되어 있습니다.|위임 규칙 제거 <p> 조직에서 [끝점용 Microsoft Defender를](/windows/security/threat-protection/) [](/microsoft-365/security/defender-endpoint/investigate-user) 사용하는 경우 위임 권한을 받고 있는 사용자를 조사하는 것이 있습니다.|
|사용자|데이터 유출 <br> (사용자가 전자 메일 또는 파일 공유 DLP 정책을 [위반했습니다.](../../compliance/dlp-learn-about-dlp.md) |자동화된 조사는 특정 보류 중인 작업을 수행하지 않습니다. <p> [DLP 보고서를 보고 작업을 실행합니다.](../../compliance/view-the-dlp-reports.md)|
|사용자|전자 메일 보내기 <br> (사용자가 최근에 이전 7-10일 동안보다 더 많은 전자 메일을 보냈습니다.)|자동화된 조사는 특정 보류 중인 작업을 수행하지 않습니다. <p> 대량의 전자 메일을 보내는 것은 자체적으로 악성이 아닙니다. 사용자가 이벤트를 위해 대규모 받는 사람 그룹에 전자 메일을 보냈을 수 있습니다. 조사를 위해 [](mail-flow-insights-v2.md)메일 흐름 맵 보고서를 [](mfi-mail-flow-map-report.md) 포함하여 메일 흐름 정보를 사용하여 진행되는 작업을 파악하고 조치를 취합니다.|

## <a name="next-steps"></a>다음 단계

- [Microsoft Defender for Office 365](air-view-investigation-results.md)
- [Microsoft Defender에서 자동화된 조사 후 보류 중 또는 완료된 수정 Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>관련 문서

- [끝점용 Microsoft Defender의 자동화된 조사에 대해 자세히 알아보시겠습니다.](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [2013의 기능에 대해 Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)
