---
title: Microsoft Defender for Office 365의 자동화 된 조사 후의 수정 작업
keywords: AIR, autoIR, ATP, 자동화, 조사, 대응, 재구성, 위협, 고급, 위협, 보호
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Office 365 용 Microsoft Defender의 자동화 된 조사에 따라 수정 작업에 대해 알아봅니다.
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: ffd0429d3dc85371e7b6bb1c2d1246d9820d0e2e
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446710"
---
# <a name="remediation-actions-following-automated-investigation-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365의 자동화 된 조사 후의 수정 작업

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="remediation-actions"></a>수정 작업

[Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) 의 [자동화 된 조사 및 대응 기능](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR)은 특정 수정 작업을 포함 합니다. 자동화 조사가 실행되고 있거나 완료된 경우, 일반적으로 보안 운영 팀이 진행해야 하는 하나 이상의 수정 조치를 보게됩니다. 이러한 교정 작업에는 다음이 포함 될 수 있습니다.

- 전자 메일 메시지 또는 클러스터의 일시 삭제
- 차단 URL(클릭 시간)
- 외부 메일 전달 해제
- 위임 해제

> [!NOTE]
> Microsoft Defender for Office 365에서는 자동화 된 조사로 인해 자동 수정 작업이 수행 되지 않습니다. 관리 작업은 조직의 보안 운영 팀이 승인 하는 경우에만 수행 됩니다.

## <a name="threats-and-remediation-actions"></a>위협 및 업데이트 관리 작업

다음 표에는 Microsoft Defender for Office 365의 위협과 해당 교정 작업에 대 한 설명이 요약 되어 있습니다. 일부 경우에는 자동화 된 조사로 인해 특정 업데이트 관리 작업이 수행 되지 않습니다. 보안 운영 팀은 아래 표에 설명 된 대로 적절 한 조치를 더 조사 하 고 수행할 수 있습니다.

****

|범주|위협/위험|재구성 작업|
|---|---|---|
|이메일|맬웨어|전자 메일/클러스터 일시 삭제 <br/><br/>클러스터에 맬웨어를 포함 하는 소수의 전자 메일 메시지가 여러 개 있는 경우 클러스터가 악성으로 간주 됩니다.|
|이메일|악성 URL<br/>( [Office 365 ATP의 안전한 링크](atp-safe-links.md)에서 악의적인 URL이 검색 되었습니다.|전자 메일/클러스터 일시 삭제 <br/><br/>악성 URL이 포함 된 전자 메일은 악성으로 간주 됩니다.|
|이메일|피싱|전자 메일/클러스터 일시 삭제 <br/><br/>클러스터의 전자 메일 메시지 중 몇 개 이상이 피싱 시도를 포함 하는 경우 클러스터는 피싱 것으로 간주 됩니다.|
|이메일|Zapped 피싱 <br/>(전자 메일 메시지를 배달 하 고 [zapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge).)|전자 메일/클러스터 일시 삭제 <br/><br/>보고서를 사용 하 여 zapped 메시지를 볼 수 있습니다. [ZAP이 메시지 및 faq를 이동 하는지 확인](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge#how-to-see-if-zap-moved-your-message)합니다.|
|이메일|사용자가 [보고](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) 하는 누락 된 피싱 전자 메일|[사용자의 보고서에 의해 트리거되는 자동화 된 조사](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|이메일|볼륨 변칙 <br/>일치 조건으로 최근 전자 메일 수량이 이전 7-10 일을 초과 합니다.|자동 조사로 인해 보류 중인 특정 작업은 발생 하지 않습니다. <br/><br/>볼륨 변칙은 확실 한 위협이 되지 않지만, 지난 7-10 일에 비해 더 큰 전자 메일 볼륨을 최근 기간으로 표시 하는 것은 매우 큽니다. 이는 잠재적 문제를 나타낼 수 있지만 악성 verdicts 또는 전자 메일 메시지/클러스터의 수동 검토 측면에서 확인이 필요 합니다. [배달 된 의심 스러운 전자 메일 찾기 및 삭제](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered#find-and-delete-suspicious-email-that-was-delivered)를 참조 하세요.|
|이메일|발견 된 위협 없음 <br/>(시스템에서 전자 메일 클러스터 verdicts의 파일, url 또는 분석을 기반으로 위협을 찾지 못했습니다.)|자동 조사로 인해 보류 중인 특정 작업은 발생 하지 않습니다. <br/><br/>발견 된 위협 및 조사가 완료 된 후 [zapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge) 은 조사 결과에 반영 되지 않지만 [위협 탐색기](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)에서 이러한 위협을 볼 수 있습니다.|
|사용자|사용자가 악성 URL을 클릭 한 경우 <br/>(나중에 악성으로 확인 한 페이지를 탐색 하거나 사용자가 [안전한 링크 경고 페이지](atp-safe-links.md#warning-pages-from-safe-links) 를 건너뛰고 악의적인 페이지로 이동할 수 있습니다.)|자동 조사로 인해 보류 중인 특정 작업은 발생 하지 않습니다. <br/><br/>위협 탐색기를 사용 하 여 [url에 대 한 데이터를 확인 하 고 verdicts를 클릭](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer#view-data-about-phishing-urls-and-click-verdict)합니다. <br/><br/>조직에서 [끝점에 대해 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/)를 사용 하는 경우 [사용자의](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) 계정이 손상 되었는지 확인 하는 것을 조사 하는 것이 좋습니다.|
|사용자|사용자가 맬웨어/피싱를 보내는 중입니다.|자동 조사로 인해 보류 중인 특정 작업은 발생 하지 않습니다. <br/><br/>사용자가 맬웨어/피싱를 보고할 수도 있고, 다른 사용자가 공격의 일부로 [사용자를 스푸핑](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection) 했을 수 있습니다. [위협 탐색기](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) 를 사용 하 여 [맬웨어](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--malware) 또는 [피싱](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--phish)가 포함 된 전자 메일을 보고 처리 합니다.|
|사용자|전자 메일 전달 <br/>(이 경우 데이터 exfiltration에 사용할 수 있는 사서함 전달 규칙이 구성 됩니다.)|전달 규칙 제거 <br/><br/>전달 된 전자 메일에 대 한 좀 더 구체적인 세부 정보를 보려면 [자동 전달 메시지 보고서](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report)를 포함 하 여 [메일 흐름 정보](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2)를 사용 합니다.|
|사용자|전자 메일 위임 규칙 <br/>(사용자의 계정에 위임 설정 됨)|위임 규칙 제거 <br/><br/> 조직에서 [끝점에 대해 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/)를 사용 하는 경우 위임 권한을 얻는 [사용자를 조사](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) 하는 것이 좋습니다.|
|사용자|데이터 유출<br/>(사용자가 전자 메일 또는 파일 공유 [DLP 정책을](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)위반 했습니다.)|자동 조사로 인해 보류 중인 특정 작업은 발생 하지 않습니다. <br/><br/>[DLP 보고서를 보고 작업을 수행](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports)합니다.|
|사용자|비정상 전자 메일 보내기 <br/>(사용자가 최근 7-10 일 보다 더 많은 전자 메일을 보낸 경우)|자동 조사로 인해 보류 중인 특정 작업은 발생 하지 않습니다. <br/><br/>많은 전자 메일을 보내는 것 자체가 악의적이 지는 않습니다. 사용자는 여러 받는 사람에 게 이벤트에 대 한 전자 메일을 전송 했을 수 있습니다. 조사 하려면 [메일 흐름 맵 보고서](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-mail-flow-map-report) 를 비롯 한 [메일 흐름 정보](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2)를 사용 하 여 진행 중인 작업을 확인 하 고 조치를 취해야 합니다.|
|

## <a name="next-steps"></a>다음 단계

- [Microsoft Defender for Office 365에서 자동화 된 조사에 대 한 세부 정보 및 결과 보기](air-view-investigation-results.md)

- [Microsoft Defender for Office 365에서 자동화 된 조사에 따라 보류 중 또는 완료 되는 재구성 작업 보기](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>관련 문서

- [끝점에 대 한 Microsoft Defender의 자동화 된 조사에 대해 자세히 알아보기](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsoft 365 Defender의 추가 기능에 대해 자세히 알아보기](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
