---
title: Microsoft Defender for Office 365의 자동화 된 조사 및 응답
keywords: AIR, autoIR, ATP, 자동화, 조사, 대응, 재구성, 위협, 고급, 위협, 보호
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/05/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Microsoft Defender for Office 365의 자동화 된 조사 및 응답 기능 사용을 시작 하세요.
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 86414eaf0917a6cad7debc44e3f7aa604c55ae70
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357746"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365의 자동 조사 및 응답 (AIR)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft Defender For Office 365에](office-365-atp.md) 는 보안 작업 팀의 시간과 노력을 절감할 수 있는 강력한 자동화 된 조사 및 응답 (AIR) 기능이 포함 되어 있습니다. 알림이 트리거되면 해당 경고를 검토 하 고 우선 순위를 지정 하 고 응답 하는 보안 운영 팀이 진행 됩니다. 들어오는 알림의 볼륨을 유지 하는 것은 매우 어려울 수 있습니다. 이러한 작업 중 일부를 자동화 하는 것이 도움이 될 수 있습니다.

AIR을 사용 하면 보안 운영 팀이 보다 효율적이 고 효율적으로 작업할 수 있습니다. AIR 기능에는 현재 존재 하는 잘 알려진 위협에 대응 하 여 자동화 된 조사 프로세스가 포함 되어 있습니다. 적절 한 교정 작업을 통해 승인을 받고, 보안 운영 팀이 검색 된 위협에 효과적으로 응답할 수 있도록 합니다. AIR을 사용 하는 경우 보안 운영 팀은 트리거된 중요 경고의 시야 없이 우선 순위가 더 높은 작업에 집중할 수 있습니다.

이 문서에서는 다음에 대해 설명합니다.

- [전체 공기 흐름](#the-overall-flow-of-air)
- [공기를 얻는 방법](#how-to-get-air) 한
- AIR 기능을 구성 하거나 사용 하는 [데 필요한 사용 권한](#required-permissions-to-use-air-capabilities)

이 문서에는 [다음 단계](#next-steps)및 자세한 내용을 확인할 수 있는 리소스도 포함 되어 있습니다.

## <a name="the-overall-flow-of-air"></a>전체 공기 흐름

경고가 트리거된 후 보안 playbook에서 자동화 된 조사를 시작 하 여 발견 및 권장 작업을 결과로 발생 합니다. 다음은 AIR의 전체 흐름을 단계별로 설명한 것입니다.

1. 자동화 된 조사가 다음 중 한 가지 방법으로 시작 됩니다.

   - 경고는 전자 메일 (예: 메시지, 첨부 파일, URL 또는 손상 된 사용자 계정)으로 의심 되는 항목에 의해 [트리거됩니다](#which-alert-policies-trigger-automated-investigations) . 인시던트가 생성 되 고 자동 조사가 시작 됩니다.

     --- 또는 ---

   - 보안 분석가가 [Threat Explorer](threat-explorer.md)를 사용 하는 동안 [자동화 된 조사를 시작](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) 합니다.

2. 자동화 된 조사가 실행 되는 동안에는 해당 전자 메일에 대 한 추가 데이터와 해당 전자 메일에 관련 된 엔터티가 수집 됩니다. 이러한 엔터티는 파일, Url 및 받는 사람을 포함할 수 있습니다.  새 경고 및 관련 경고가 트리거되면 조사의 범위가 증가할 수 있습니다.

3. 자동화 된 조사 도중 및 후에 [세부 정보 및 결과](air-view-investigation-results.md) 를 볼 수 있습니다. 결과에는 발견 된 모든 위협에 응답 하 고 문제를 수정 하기 위해 취할 수 있는 [권장 작업이](air-remediation-actions.md) 포함 됩니다. 또한 모든 조사 활동을 추적 하는 [playbook 로그](air-view-investigation-results.md#playbook-log) 를 사용할 수 있습니다.

4. 보안 운영 팀은 [조사 결과 및 권장 사항을](air-view-investigation-results.md)검토 하 고 [재구성 작업을 승인 하거나 거부](air-review-approve-pending-completed-actions.md)합니다.

5. 보류 중인 재구성 작업이 승인 되거나 거부 됨에 따라 자동 조사가 완료 됩니다.

> [!IMPORTANT]
> Office 365 용 Microsoft Defender에는 자동으로 수정 작업이 수행 되지 않습니다. 수정 작업은 조직의 보안 팀이 승인한 경우에만 적용될 수 있습니다.
>
> AIR 기능에서는 수정 작업을 식별 하 고 의사 결정을 내리는 데 필요한 세부 정보를 제공 하 여 보안 운영 팀의 시간을 절약할 수 있습니다.

보안 운영 팀은 각 자동화 된 조사 중 및 후에 다음 작업을 수행할 수 있습니다.

- [조사와 관련 된 경고에 대 한 세부 정보 보기](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [조사 결과 세부 정보 보기](air-view-investigation-results.md#view-details-of-an-investigation)

- [조사 결과로 작업 검토 및 승인](air-review-approve-pending-completed-actions.md)

> [!TIP]
> 자세한 개요는 [AIR works](automated-investigation-response-office.md)를 참조 하세요.

## <a name="how-to-get-air"></a>공기를 얻는 방법

정책 및 경고가 구성 된 경우 [Microsoft Defender For Office 365](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)에 포함 된 AIR 기능 이에 대 한 몇 가지 도움이 필요 하면 [위협 으로부터 보호](protect-against-threats.md) 의 지침을 따라 다음 보호 설정을 설정 하거나 구성 합니다.

1. [감사 로깅](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (설정 해야 함)

2. [맬웨어 방지 정책](protect-against-threats.md#part-1---anti-malware-protection)

3. [피싱 방지 보호 기능](protect-against-threats.md#part-2---anti-phishing-protection)

4. [스팸 방지 보호](protect-against-threats.md#part-3---anti-spam-protection)

5. [안전한 링크 및 안전한 첨부 파일](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)

6. [SharePoint, OneDrive 및 Microsoft 팀에 대 한 안전한 첨부 파일](protect-against-threats.md#part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)

7. [전자 메일에 대해 제로 시간 자동 삭제](protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop)

또한 [조직의 경고 정책](https://docs.microsoft.com/microsoft-365/compliance/alert-policies), 특히 [위협 관리 범주에 있는 기본 정책을](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies)검토 해야 합니다.

## <a name="which-alert-policies-trigger-automated-investigations"></a>자동 조사를 트리거하는 경고 정책은 무엇입니까?

Microsoft 365에서는 Exchange 관리자 권한 남용, 맬웨어 활동, 잠재적 외부 및 내부 위협, 정보 관리 위험을 식별 하는 데 도움이 되는 다양 한 기본 제공 경고 정책을 제공 합니다. 몇 가지 [기본 경고 정책이](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) 자동 조사를 트리거할 수 있습니다. 다음 표에서는 자동화 된 조사를 트리거하는 경고, Microsoft 365 보안 센터에서의 심각도 및 생성 되는 방법을 설명 합니다.

|알림에서|심각도|알림을 생성 하는 방법|
|---|---|---|
|잠재적으로 악의적인 URL 클릭이 검색 되었습니다.|**High**|이 경고는 다음과 같은 경우에 발생 합니다. <ul><li>조직의 [안전한 링크로](atp-safe-links.md) 보호 된 사용자가 악의적인 링크를 클릭 합니다.</li><li>Url에 대 한 결과 변경 내용은 Microsoft Defender for Office 365를 통해 식별 됩니다.</li><li>사용자가 조직의 [안전한 링크 정책](set-up-atp-safe-links-policies.md)에 따라 안전한 링크 경고 페이지를 재정의 합니다.</li></ul> <p> 이 경고를 트리거하는 이벤트에 대 한 자세한 내용은 [안전한 링크 정책 설정을](set-up-atp-safe-links-policies.md)참조 하십시오.|
|사용자가 맬웨어 또는 피싱 하는 전자 메일 메시지를 보고 합니다.|**알림**|이 알림은 조직의 사용자가 [보고서 메시지 추가 기능](enable-the-report-message-add-in.md)을 사용 하 여 메시지를 피싱 전자 메일로 보고할 때 생성 됩니다.|
|배달이 완료 된 후 맬웨어를 포함 하는 전자 메일 메시지가 제거 됨|**알림**|이 알림은 맬웨어를 포함 하는 전자 메일 메시지가 조직의 사서함에 배달 될 때 생성 됩니다. 이 이벤트가 발생 하면 Microsoft는 [자동](zero-hour-auto-purge.md)제거를 사용 하 여 Exchange Online 사서함에서 감염 된 메시지를 제거 합니다.|
|배달 후 피싱 Url이 포함 된 전자 메일 메시지가 제거 됨|**알림**|이 경고는 피싱가 포함 된 메시지가 조직의 사서함으로 배달 될 때 생성 됩니다. 이 이벤트가 발생 하면 Microsoft는 [자동](zero-hour-auto-purge.md)제거를 사용 하 여 Exchange Online 사서함에서 감염 된 메시지를 제거 합니다.|
|의심 스러운 전자 메일 전송 패턴이 검색 됨|**Medium**|이 경고는 조직의 누군가가 의심 스러운 전자 메일을 보냈거나 전자 메일을 보낼 수 없을 위험성이 있는 경우에 생성 됩니다. 이는 계정이 손상 되었음을 나타낼 수 있지만 사용자를 제한 하기에 충분 하지 않다는 문제가 발생 하는 경우의 초기 경고입니다. <p> 드문 경우 지만이 정책에 의해 생성 된 경고는 이상 하 게 될 수 있습니다. 그러나 [사용자 계정이 손상 되었는지 여부는 확인](responding-to-a-compromised-email-account.md)하는 것이 좋습니다.|
|사용자가 전자 메일을 보낼 수 없도록 제한 됨|**High**|이 알림은 조직의 사용자가 아웃 바운드 메일을 보낼 수 없는 경우에 생성 됩니다. 일반적으로 [전자 메일 계정이 손상 되는](responding-to-a-compromised-email-account.md)경우이 결과가 발생 합니다. <p> 제한 된 사용자에 대 한 자세한 내용은 [Microsoft 365의 제한이 있는 사용자 포털에서 차단 되는 사용자 제거](removing-user-from-restricted-users-portal-after-spam.md)를 참조 하세요.|
|

> [!TIP]
> 경고 정책에 대 한 자세한 내용을 보거나 기본 설정을 편집 하려면 [Microsoft 365 준수 센터의 경고 정책을](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)참조 하세요.

## <a name="required-permissions-to-use-air-capabilities"></a>AIR 기능을 사용 하는 데 필요한 사용 권한

사용 권한은 다음 표에 설명 된 것과 같은 특정 역할을 통해 부여 됩니다.

|작업|필요한 역할|
|---|---|
|AIR 기능 설정|다음 역할 중 하나입니다. <ul><li>전역 관리자</li><li>보안 관리자</li></ul> <p> 이러한 역할은 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 또는 [보안 & 준수 센터](permissions-in-the-security-and-compliance-center.md)에서 할당할 수 있습니다.|
|자동화 된 조사 시작 <p> --- 또는 --- <p> 권장 작업 승인 또는 거부|[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 또는 [보안 & 준수 센터](permissions-in-the-security-and-compliance-center.md)에 지정 된 다음 역할 중 하나입니다. <ul><li>전역 관리자</li><li>보안 관리자</li><li>보안 읽기 권한자 <br/>--- 및 ---</li><li>검색 및 제거 (이 역할은 [보안 & 준수 센터](permissions-in-the-security-and-compliance-center.md)에만 할당 됩니다. 여기에 새 역할 그룹을 만들고이 새 역할 그룹에 검색 및 제거 역할을 추가 해야 할 수 있습니다.</li></ul>|
|

## <a name="required-licenses"></a>필수 라이선스

[Microsoft Defender For Office 365 요금제 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) 라이선스는 다음에 할당 되어야 합니다.

- 보안 관리자 (전역 관리자 포함)
- 조직의 보안 운영 팀 (보안 판독기 및 **검색 및 제거** 역할을 포함 하는 작업)
- 최종 사용자

## <a name="next-steps"></a>다음 단계

- [자세한 내용은 자동화 된 조사의 세부 정보 및 결과를 참조 하세요.](air-view-investigation-results.md#view-details-of-an-investigation)

- [보류 중인 작업 검토 및 승인](air-remediation-actions.md)

## <a name="see-also"></a>참고 항목

- [끝점에 대 한 Microsoft Defender의 자동화 된 조사 및 재구성](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsoft 365 Defender의 자동화 된 조사 및 응답](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
