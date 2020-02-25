---
title: Office 365의 자동화 된 조사 및 응답 (AIR)
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
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection 계획 2의 자동화 된 조사 및 응답 기능 사용을 시작 하세요.
ms.openlocfilehash: 3a362f7d15a9cc8e1f5784ec03c8c04d3d77886d
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42262015"
---
# <a name="automated-investigation-and-response-air-in-office-365"></a>Office 365의 자동화 된 조사 및 응답 (AIR)

[Office 365 Advanced Threat Protection](office-365-atp.md) 요금제 2에는 보안 작업 팀의 시간과 노력을 줄일 수 있는 강력한 자동 조사 및 응답 (AIR) 기능이 포함 되어 있습니다. 특정 알림이 트리거되면 하나 이상의 보안 playbook가 시작 되 고 자동화 된 조사 프로세스가 시작 됩니다. 이를 통해 보안 운영 팀은 트리거된 경고에 대 한 시야 없이 우선 순위가 높은 작업에 집중할 수 있습니다. 

## <a name="the-overall-flow-of-air"></a>전체 공기 흐름

높은 수준에서 AIR 흐름은 다음과 같은 방식으로 작동 합니다.

|단계  |진행 작업  |
|---------|---------|
|개     |Office 이벤트에 의해 알림이 트리거되고 [보안 playbook](automated-investigation-response-office.md#security-playbooks) 선택한 경고에 대 한 자동 조사를 시작 합니다. <br/><br/>또는 보안 분석가가 [위협 탐색기](threat-explorer.md)를 사용 하는 동안 [자동화 된 조사를 트리거할](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) 수 있습니다.        |
|2     |자동 조사가 실행 되는 동안 전자 메일 및 해당 전자 메일에 관련 된 엔터티에 대 한 추가 데이터 (파일, Url 및 받는 사람)를 수집 합니다.  새 관련 경고가 트리거되면 조사 범위가 증가할 수 있습니다.         |
|3(sp3)     |자동화 된 조사 도중 및 후에 [세부 정보 및 결과](air-view-investigation-results.md) 를 볼 수 있습니다. 결과에는 발견 된 모든 위협을 응답 하 고 수정 하기 위해 취할 수 있는 [권장 작업이](air-remediation-actions.md) 포함 됩니다. 또한 모든 조사 활동을 추적 하는 [playbook 로그](air-view-investigation-results.md#playbook-log) 를 사용할 수 있습니다.<br/><br/>조직에서 사용자 지정 보고 솔루션 또는 타사 솔루션을 사용 하는 경우에는 [Office 365 관리 활동 API를 사용](air-custom-reporting.md) 하 여 자동화 된 조사 및 위협에 대 한 정보를 볼 수 있습니다.         |
|1-4     |보안 운영 팀은 [조사 결과 및 권장 사항을](air-view-investigation-results.md)검토 하 고 [업데이트 관리 작업을 승인](air-remediation-actions.md#approve-or-reject-pending-actions)합니다. Office 365에서는 작업이 자동으로 수행 되지 않습니다. 관리 작업은 조직의 보안 팀이 승인 하는 경우에만 수행 됩니다.         |

자동화 된 조사 프로세스 중 및 이후에 보안 팀은 다음을 수행할 수 있습니다.

- [조사와 관련 된 경고에 대 한 세부 정보 보기](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [조사 결과 세부 정보 보기](air-view-investigation-results.md#view-details-of-an-investigation)
- [조사 결과로 작업 검토 및 승인](air-remediation-actions.md#approve-or-reject-pending-actions)

자세한 내용은 [AIR works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)를 참조 하세요.

## <a name="how-to-get-air"></a>공기를 얻는 방법

Office 365 AIR은 다음의 구독에 포함되어 있습니다.

- Microsoft 365 E5
- Office 365 E5
- Microsoft 위협 방지
- Office 365 Advanced Threat Protection Plan 2

이러한 구독을 사용 하지 않는 경우 [무료 평가판을 시작](https://go.microsoft.com/fwlink/p/?LinkID=698279&culture=en-US&country=US)합니다.

기능 가용성에 대 한 자세한 내용은 [ATP (Advanced Threat Protection) 계획에서 사용 가능한 기능](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)을 참조 하세요.

## <a name="required-permissions-to-use-air-capabilities"></a>AIR 기능을 사용 하는 데 필요한 사용 권한

사용 권한은 다음 표에 설명 된 것과 같은 특정 역할을 통해 부여 됩니다. 

|작업 |필요한 역할 |
|--|--|
|AIR 기능을 설정 하려면 |다음 역할 중 하나입니다. <br/>- **전역 관리자**<br/>- **보안 관리자** <br/>이러한 역할은 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 또는 [Office 365 보안 & 준수 센터](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)에서 할당 될 수 있습니다. |
|권장 작업을 승인 하거나 거부 하려면|[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 또는 [Office 365 보안 & 준수 센터](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center))에서 할당 된 다음 역할 중 하나입니다.<br/>- **전역 관리자** <br/>- **보안 관리자**<br/>- **보안 독자** <br/>--- 및 ---<br/>- **검색 및 제거** (이 역할은 [Office 365 보안 & 준수 센터](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)에만 할당 됩니다. 여기에 새 역할 그룹을 만들고 새 역할 그룹에 검색 및 제거 역할을 추가 해야 할 수 있습니다.

## <a name="related-articles"></a>관련 문서

- [Microsoft Threat Protection의 자동화된 조사 및 대응](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

- [Microsoft Defender Advanced Threat Protection의 자동화 된 조사 및 재구성](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)