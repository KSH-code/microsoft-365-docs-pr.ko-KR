---
title: Office 365용 Microsoft Defender의 자동화된 조사에 따라 수정 작업
keywords: AIR, autoIR, ATP, 자동화된, 조사, 대응, 수정, 위협, 고급, 위협, 보호
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Office 365용 Microsoft Defender의 자동화된 조사에 따라 수정 조치에 대해 자세히 알아보습니다.
ms.date: 01/21/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 39032cb187b2654b6ae03c048e706afb665a8761
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939308"
---
# <a name="remediation-actions-following-automated-investigation-in-microsoft-defender-for-office-365"></a>Office 365용 Microsoft Defender의 자동화된 조사에 따라 수정 작업

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="remediation-actions"></a>수정 작업

[Office](office-365-air.md) [365용 Microsoft Defender의](office-365-atp.md) 자동화된 조사 및 대응 기능(AIR)에는 특정 수정 작업이 포함됩니다. 자동화 조사가 실행되고 있거나 완료된 경우, 일반적으로 보안 운영 팀이 진행해야 하는 하나 이상의 수정 조치를 보게됩니다. 이러한 수정 작업에는 다음이 포함됩니다.

- 전자 메일 메시지 또는 클러스터의 일시 삭제
- 차단 URL(클릭 시간)
- 외부 메일 전달 해제
- 위임 해제

> [!NOTE]
> Office 365용 Microsoft Defender에서 자동화된 조사는 자동으로 수행되는 수정 작업이 수행되지 않습니다. 수정 작업은 조직의 보안 운영 팀이 승인한 경우만 수행됩니다.

## <a name="threats-and-remediation-actions"></a>위협 및 수정 작업

이 섹션의 표에서는 Office 365용 Microsoft Defender의 위협 및 적절한 수정 조치를 요약하여 설명합니다. 경우에 따라 자동화된 조사가 특정 수정 작업을 수행하지 않는 경우도 있습니다. 보안 운영 팀은 아래 표에 설명된 바와 같이 추가 조사를 수행하고 적절한 조치를 취할 수 있습니다.

|범주|위협/위험|수정 작업|
|:---|:---|:---|
|전자 메일|맬웨어|전자 메일/클러스터를 소프트 삭제 <br> 클러스터의 전자 메일 메시지 수가 맬웨어를 포함하는 경우 클러스터는 악성으로 간주됩니다.|
|전자 메일|악성 URL <br> (Office [365용 Microsoft Defender의 안전한 링크에서](atp-safe-links.md)악성 URL이 검색되었습니다.)|전자 메일/클러스터를 소프트 삭제 <p> 악의적인 URL이 포함된 전자 메일은 악의적인 것으로 간주됩니다.|
|전자 메일|피싱|전자 메일/클러스터를 소프트 삭제 <br> 클러스터의 여러 전자 메일 메시지에 피싱 시도가 포함되어 있는 경우 클러스터는 피싱으로 간주됩니다.|
|전자 메일|Zapped 피싱 <br> (전자 메일 메시지가 배달 및 [zapped.)](zero-hour-auto-purge.md)|전자 메일/클러스터를 소프트 삭제 <p> 보고서는 zapped 메시지를 볼 수 있습니다. [ZAP에서 메시지와 FAQ를 이동한지 확인](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message)|
|전자 메일|사용자가 보고한 누락된 [피싱](enable-the-report-message-add-in.md) 전자 메일|[사용자 보고서에 의해 트리거된 자동화된 조사](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|전자 메일|볼륨 이상 <br> (최근 전자 메일 수량은 일치하는 조건에 대해 이전 7-10일을 초과합니다.)|자동화된 조사는 특정 보류 중인 작업을 수행하지 않습니다. <p> 볼륨 이상은 명확한 위협이 아니며, 지난 7~10일과 비교할 때 최근 며칠 동안 더 큰 전자 메일 볼륨을 나타냈기만 합니다. 볼륨 이상이 잠재적인 문제를 나타낼 수 있는 경우도 하지만 악의적인 판정이나 전자 메일 메시지/클러스터의 수동 검토와 관련해 확인이 필요합니다. 배달된 [의심스러운 전자 메일 찾기를 참조하세요.](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered)|
|전자 메일|위협을 찾을 수 없음 <br> (시스템에서 전자 메일 클러스터 결과의 파일, URL 또는 분석을 기반으로 위협을 찾지 못했습니다.)|자동화된 조사는 특정 보류 중인 작업을 수행하지 않습니다. <p> 조사가 완료된 후 [발견](zero-hour-auto-purge.md) 및 잠기는 위협은 조사의 수치적 발견에 반영되지 않지만 위협 탐색기에서 이러한 위협을 볼 [수 있습니다.](threat-explorer.md)|
|사용자|사용자가 악성 URL을 클릭한 경우 <br> 사용자가 나중에 악의적인 것으로 확인된 페이지로 이동하거나, 사용자가 안전한 [](atp-safe-links.md#warning-pages-from-safe-links) 링크 경고 페이지를 우회하여 악의적인 페이지로 이동했습니다.|자동화된 조사는 특정 보류 중인 작업을 수행하지 않습니다. <p> 위협 탐색기를 사용하여 URL에 대한 데이터를 [보고 판정을 클릭합니다.](threat-explorer.md#view-phishing-url-and-click-verdict-data) <p> 조직에서 [끝점용 Microsoft Defender를](https://docs.microsoft.com/windows/security/threat-protection/) [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) 사용하는 경우 사용자를 조사하여 계정이 손상된지 확인하는 것이 있습니다.|
|사용자|사용자가 맬웨어/피싱을 보내고 있습니다.|자동화된 조사는 특정 보류 중인 작업을 수행하지 않습니다. <p> 사용자가 맬웨어/피싱을 보고하거나 공격의 [](anti-spoofing-protection.md) 일부로 사용자를 스푸핑할 수 있습니다. 위협 [탐색기를](threat-explorer.md) 사용하여 맬웨어 또는 피싱이 포함된 [전자](threat-explorer-views.md#email--malware) 메일을 [보고 처리합니다.](threat-explorer-views.md#email--phish)|
|사용자|전자 메일 전달 <br> 사서함 전달 규칙은 데이터 유출에 사용할 수 있도록 구성됩니다.|전달 규칙 제거 <p> 자동 [전달된](mail-flow-insights-v2.md)메시지 보고서를 [](mfi-auto-forwarded-messages-report.md)비롯한 메일 흐름 정보를 사용하여 전달된 전자 메일에 대한 보다 구체적인 세부 정보를 볼 수 있습니다.|
|사용자|전자 메일 위임 규칙 <br> 사용자의 계정에 위임이 설정되어 있습니다.|위임 규칙 제거 <p> 조직에서 [끝점용 Microsoft Defender를](https://docs.microsoft.com/windows/security/threat-protection/) [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) 사용하는 경우 위임 권한을 받고 있는 사용자를 조사하는 것이 있습니다.|
|사용자|데이터 유출 <br> (사용자가 전자 메일 또는 파일 공유 DLP 정책을 [위반했습니다.)](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|자동화된 조사는 특정 보류 중인 작업을 수행하지 않습니다. <p> [DLP 보고서를 보고 조치를 취합니다.](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports)|
|사용자|전자 메일 보내기 <br> 사용자가 최근에 이전 7-10일 동안보다 더 많은 전자 메일을 보냈습니다.|자동화된 조사는 특정 보류 중인 작업을 수행하지 않습니다. <p> 대량의 전자 메일을 보내는 것 자체는 악성이 아닙니다. 사용자가 이벤트를 위해 대규모 받는 사람 그룹에 전자 메일을 보냈을 수 있습니다. 조사를 위해 [](mail-flow-insights-v2.md)메일 흐름 맵 보고서를 [](mfi-mail-flow-map-report.md) 비롯한 메일 흐름 정보를 사용하여 진행되는 작업을 파악하고 조치를 취합니다.|
|

## <a name="next-steps"></a>다음 단계

- [Microsoft Defender for Office 365의 자동화된 조사 세부 정보 및 결과 보기](air-view-investigation-results.md)

- [Microsoft Defender for Office 365에서 자동화된 조사 후 보류 중 또는 완료된 수정 작업 보기](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>관련 문서

- [끝점용 Microsoft Defender의 자동화된 조사에 대해 자세히 알아보기](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsoft 365 Defender의 기능에 대해 자세히 알아보기](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
