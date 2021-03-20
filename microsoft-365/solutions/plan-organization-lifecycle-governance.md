---
title: Microsoft 365 그룹 및 Microsoft Teams에 대한 조직 및 수명 주기 거버넌스 계획
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Microsoft 365의 공동 작업 도구에 대한 수명 주기 거버넌스 옵션에 대해 숙지
ms.openlocfilehash: ff3a3a60ce49c423410b51dc6fee2137ebf8952a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907931"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 그룹 및 Microsoft Teams에 대한 조직 및 수명 주기 거버넌스 계획

Microsoft 365 그룹에는 조직에 필요한 거버넌스 기능을 구현하기 위한 다양한 도구 집합이 있습니다. 

다음 섹션에서는 기능에 대해 설명하고 모범 사례를 권장하며, 거버넌스 요구 사항을 결정하기 위한 올바른 질문과 요구 사항을 충족하는 방법을 결정하는 지침을 제공합니다.

## <a name="control-who-can-create-microsoft-365-groups"></a>Microsoft 365 그룹을 만들 수 있는 사용자 제어

최종 사용자는 Outlook, SharePoint, Teams 및 기타 환경을 비롯한 여러 끝점에서 그룹을 만들 수 있습니다.

![이미지 desc](../media/04.png)

그룹 소유자에게 권한을 부여하고 사용자가 작업을 보다 쉽게 완료할 수 있도록 셀프 서비스를 권장하는 것이 좋습니다. 많은 Microsoft 365 서비스를 사용하려면 서비스가 작동하기 위해 그룹을 만들어야 하기 때문에 그룹 및 팀 만들기를 제한하면 사용자의 생산성이 느려질 수 있습니다.

그룹을 만들 때 다음과 같은 거버넌스 옵션을 고려하세요.

- 그룹 시작을 제한하려면 그룹 [](microsoft-365-groups-expiration-policy.md) 만료 정책을 사용하여 사용되지 않는 그룹을 자동으로 삭제합니다.
- 그룹 만들기를 동적 [](/azure/active-directory/users-groups-roles/groups-create-rule) 구성원이 포함된 보안 그룹의 구성원(예: 모든 정규 직원)으로 제한합니다.
- 그룹 만들기를 보안 그룹으로 제한하고 사용자가 보안 그룹의 구성원이 되기 위해 조직의 그룹 사용 정책에 대한 교육을 완료해야 합니다.

그룹을 만들 수 있는 사용자만 제한하려는 경우 이 구성 방법에 대한 자세한 내용은 [Microsoft 365](manage-creation-of-groups.md) 그룹을 만들 수 있는 사용자 관리를 참조하세요.

## <a name="group-delete-restore-and-archiving"></a>그룹 삭제, 복원 및 보관

Microsoft 365 그룹이 삭제되면 기본적으로 30일 동안 보존됩니다. 이 30일의 기간을 "일시 삭제"라고 하며 이 기간 동안 그룹을 복원할 수 있습니다. 30일이 지나면 그룹 및 관련 콘텐츠가 영구적으로 삭제되며 복원할 수 없습니다.

채팅, 파일 또는 메일을 보존하기 위한 보존 정책이 있는 경우 그룹이 삭제된 후에 해당 항목이 보존됩니다. 자세한 [내용은 보존 정책에](../compliance/retention.md) 대한 자세한 정보를 참조합니다.

그룹을 삭제하 고 하나 이상의 그룹에 연결된 서비스의 콘텐츠를 유지하려면 보관 [그룹,](end-life-cycle-groups-teams-sites-yammer.md) 팀 및 Yammer 정보를 참조하세요.

## <a name="group-naming-policy"></a>그룹 이름 정책

그룹 이름 정책은 다음 두 가지 방법으로 그룹을 관리하는 데 도움이 될 수 있습니다.

- 접두사/접미사 명명 정책을 사용하여 그룹 이름 및 연결된 전자 메일 주소의 시작 또는 끝에 고정 문자열 또는 Azure AD 특성을 적용할 수 있습니다. 이렇게 하면 부서 이름이나 그룹 이름에 지역을 포함하도록 할 수 있습니다.
- 차단된 단어 정책은 임원 이름과 같은 특정 단어가 그룹 이름에 사용되지 않도록 할 수 있습니다.

그룹 연결 서비스에서 그룹을 만들면 이름 정책이 적용됩니다.

그룹에 대해 이름 정책을 사용하기로 결정한 경우 [Microsoft 365 그룹](groups-naming-policy.md)이름 정책 을 참조합니다.

## <a name="group-expiration-policy"></a>그룹 만료 정책

만료 기간을 지정할 수 있으며 해당 기간이 끝나고 갱신되지 않은 그룹은 삭제됩니다. 만료 기간은 그룹이 만들어지거나 마지막으로 갱신된 날짜부터 시작됩니다.

그룹이 만료될 수 있는 것으로 설정하면 다음을 할 수 있습니다.
- 그룹의 소유자는 만료가 다가오면 그룹을 갱신할 수 있는 알림을 하게 됩니다.
- 활성 그룹은 자동으로 갱신됩니다.
- 갱신되지 않은 그룹은 모두 삭제됩니다.
- 삭제된 모든 그룹은 그룹 소유자 또는 관리자가 30일 이내에 복원할 수 있습니다.

만료 정책은 더 이상 사용되지 않는 그룹을 삭제하도록 하여 그룹 스플로링을 제한하는 좋은 방법입니다. 그룹 만료 정책을 만들 경우 [Microsoft 365 그룹 만료 정책을 참조합니다.](microsoft-365-groups-expiration-policy.md)

## <a name="related-topics"></a>관련 주제

[공동 작업 거버넌스 계획 단계별](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[공동 작업 거버넌스 계획 만들기](collaboration-governance-first.md)