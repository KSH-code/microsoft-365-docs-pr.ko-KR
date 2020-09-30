---
title: 자동화 된 조사 및 응답 (AIR)-시작
keywords: AIR, autoIR, ATP, 자동화, 조사, 대응, 재구성, 위협, 고급, 위협, 보호
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 09/29/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Microsoft Defender for Office 365의 자동화 된 조사 및 응답 기능 사용을 시작 하세요.
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: b844e4817bc77d7f6f4e99df53fc4b14c7e7110c
ms.sourcegitcommit: 6b1d0bea86ced26cae51695c0077adce8bcff3c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308890"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-office-365"></a>Office 365에서 자동화 된 조사 및 응답 (AIR) 사용 시작

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft Defender For Office 365에](office-365-atp.md) 는 보안 작업 팀의 시간과 노력을 절감할 수 있는 강력한 자동화 된 조사 및 응답 (AIR) 기능이 포함 되어 있습니다. 알림이 트리거되면 해당 경고를 검토 하 고 우선 순위를 지정 하 고 응답 하는 보안 운영 팀이 진행 됩니다. 들어오는 알림의 볼륨을 유지 하는 것은 매우 어려울 수 있습니다. 이 중 일부를 자동화 하면 도움이 될 수 있습니다. AIR을 사용 하는 경우 보안 운영 팀은 트리거된 경고에 대 한 시야 없이 우선 순위가 더 높은 작업에 집중할 수 있습니다.

이 문서의 내용
- [전체 공기 흐름](#the-overall-flow-of-air)
- [공기를 얻는 방법](#how-to-get-air) 한 
- AIR 기능을 구성 하거나 사용 하는 [데 필요한 사용 권한](#required-permissions-to-use-air-capabilities) 

## <a name="the-overall-flow-of-air"></a>전체 공기 흐름

높은 수준에서 경고가 트리거되고 보안 playbook에 의해 자동화 된 조사가 시작 되어 발견 및 추천이 발생 합니다. 다음은 AIR의 전체 흐름을 단계별로 설명한 것입니다.

1. 자동화 된 조사가 다음 중 한 가지 방법으로 시작 됩니다.

   - 인시던트를 만드는 Office 이벤트에 의해 [경고가](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) 트리거됩니다. 인시던트 유형에 따라 [보안 playbook](automated-investigation-response-office.md#security-playbooks) 자동 조사를 시작 합니다. 

     --- 또는 ---
   
   - 보안 분석가가 [Threat Explorer](threat-explorer.md)를 사용 하는 동안 [자동화 된 조사를 시작](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) 합니다.

2. 자동화 된 조사가 실행 되는 동안에는 해당 전자 메일에 대 한 추가 데이터와 해당 전자 메일에 관련 된 엔터티가 수집 됩니다. 이러한 엔터티는 파일, Url 및 받는 사람을 포함할 수 있습니다.  새 경고 및 관련 경고가 트리거되면 조사의 범위가 증가할 수 있습니다.

3. 자동화 된 조사 도중 및 후에 [세부 정보 및 결과](air-view-investigation-results.md) 를 볼 수 있습니다. 결과에는 발견 된 모든 위협을 응답 하 고 수정 하기 위해 취할 수 있는 [권장 작업이](air-remediation-actions.md) 포함 됩니다. 또한 모든 조사 활동을 추적 하는 [playbook 로그](air-view-investigation-results.md#playbook-log) 를 사용할 수 있습니다.

    조직에서 사용자 지정 보고 솔루션 또는 타사 솔루션을 사용 하는 경우에는 [Office 365 관리 활동 API를 사용](air-custom-reporting.md) 하 여 자동화 된 조사 및 위협에 대 한 정보를 볼 수 있습니다.

4. 보안 운영 팀은 [조사 결과 및 권장 사항을](air-view-investigation-results.md)검토 하 고 [재구성 작업을 승인 하거나 거부](air-review-approve-pending-completed-actions.md)합니다. 

    보류 중인 재구성 작업이 승인 되거나 거부 됨에 따라 자동 조사가 완료 됩니다.

> [!NOTE]
> Office 365 ATP에서는 재구성 작업이 자동으로 수행 되지 않습니다. 수정 작업은 조직의 보안 팀이 승인한 경우에만 적용될 수 있습니다. 

자동화 된 조사 프로세스 중 및 이후에 보안 팀은 다음을 수행할 수 있습니다.

- [조사와 관련 된 경고에 대 한 세부 정보 보기](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [조사 결과 세부 정보 보기](air-view-investigation-results.md#view-details-of-an-investigation)

- [조사 결과로 작업 검토 및 승인](air-review-approve-pending-completed-actions.md)

> [!TIP]
> 자세한 내용은 [AIR works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)를 참조 하세요.

## <a name="how-to-get-air"></a>공기를 얻는 방법

AIR 기능은 [Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)에 포함 되어 있습니다. 그러나 AIR이 예상 대로 작동 하려면 [정책이 구성 되어 있어야](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) 합니다. 또한 조직의 [경고 정책을](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)검토 하 고 잠재적으로 구성 해야 합니다. 

Microsoft 365에서는 Exchange 관리자 권한 남용, 맬웨어 활동, 잠재적 외부 및 내부 위협, 정보 관리 위험을 식별 하는 데 도움이 되는 다양 한 기본 제공 경고 정책을 제공 합니다. 몇 가지 [기본 경고 정책이](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) 자동 조사를 트리거할 수 있습니다. 이러한 경계 및 제한은 다음과 같습니다.

- 잠재적으로 악의적인 URL 클릭이 검색 됨

- 사용자가 전자 메일 메시지를 피싱으로 보고

- 배달이 완료 된 후 맬웨어를 포함 하는 전자 메일 메시지가 제거 됨

- 배달 후 피싱 Url이 포함 된 전자 메일 메시지가 제거 됨

- 의심 스러운 전자 메일 전송 패턴이 검색 됨

- 사용자가 전자 메일을 보낼 수 없도록 제한 됨

[알림 및 AIR에 대해 자세히 알아보세요](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="required-permissions-to-use-air-capabilities"></a>AIR 기능을 사용 하는 데 필요한 사용 권한

사용 권한은 다음 표에 설명 된 것과 같은 특정 역할을 통해 부여 됩니다. 

|작업 |필요한 역할 |
|--|--|
|AIR 기능을 설정 하려면 |다음 역할 중 하나입니다. <br/>-전역 관리자<br/>-보안 관리자 <br/>이러한 역할은 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 또는 [보안 & 준수 센터](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)에서 할당할 수 있습니다. |
|권장 작업을 승인 하거나 거부 하려면|[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 또는 [보안 & 준수 센터](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center))에서 할당 된 다음 역할 중 하나입니다.<br/>-전역 관리자 <br/>-보안 관리자<br/>-보안 독자 <br/>--- 및 ---<br/>-검색 및 제거 (이 역할은 [보안 & 준수 센터](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)에만 할당 됨) 여기에 새 역할 그룹을 만들고 새 역할 그룹에 검색 및 제거 역할을 추가 해야 할 수 있습니다.

[Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) 라이선스는 다음에 할당 되어야 합니다.
- 보안 관리자 (전역 관리자 포함)
- 조직의 보안 운영 팀 (보안 판독기 및 검색 및 제거 역할을 포함 하는 작업)
- 최종 사용자

또한 보호가 유지 되도록 하려면 [Microsoft Defender For Office 365 정책도](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) 정의 하 고 적용 해야 합니다.

## <a name="next-steps"></a>다음 단계

- [자세한 내용은 자동화 된 조사의 세부 정보 및 결과를 참조 하세요.](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [보류 중인 작업 검토 및 승인](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a>관련 문서

- [끝점에 대 한 Microsoft Defender의 자동화 된 조사 및 재구성](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsoft 365 Defender의 자동화 된 조사 및 응답](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
