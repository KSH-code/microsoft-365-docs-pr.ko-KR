---
title: Microsoft 365 그룹 및 Microsoft 팀에 대 한 조직 및 수명 주기 거 버 넌 스 계획
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Microsoft 365의 공동 작업 도구에 대 한 수명 주기 관리 옵션에 대해 자세히 알아봅니다.
ms.openlocfilehash: 2a2f14bf439ec69e4609d22783fb14d1d5cb8e70
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662749"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 그룹 및 Microsoft 팀에 대 한 조직 및 수명 주기 거 버 넌 스 계획

Microsoft 365 그룹에는 조직에 필요한 거 버 넌 스 기능을 구현 하기 위한 다양 한 도구 집합이 포함 되어 있습니다. 

다음 섹션에서는 이러한 기능에 대해 설명 하 고 최상의 방법을 권장 하며, 거 버 넌 스에 대 한 요구 사항을 확인 하 고 문제를 충족 하는 방법을 문의할 수 있는 지침을 제공 합니다.

## <a name="control-who-can-create-microsoft-365-groups"></a>Microsoft 365 그룹을 만들 수 있는 사용자 제어

최종 사용자가 Outlook, SharePoint, 팀 및 기타 환경을 비롯 한 여러 최종 지점에서 그룹을 만들 수 있습니다.

![이미지 desc](../media/04.png)

그룹 소유자의 역량을 강화 하 고 사용자가 작업을 보다 쉽게 수행할 수 있도록 지원 하기 위해 셀프 서비스를 사용 하는 것이 좋습니다. 그룹 및 팀 만들기를 제한 하면 서비스 작동을 위해 그룹을 만들어야 하는 Microsoft 365 서비스가 많으므로 사용자 생산성이 저하 될 수 있습니다.

그룹을 만들 때는 다음과 같은 거 버 넌 스 옵션을 고려해 야 합니다.

- 그룹 sprawl을 제한 하려면 [그룹 만료 정책을](microsoft-365-groups-expiration-policy.md) 사용 하 여 사용 되지 않는 그룹을 자동으로 삭제 합니다.
- 그룹 만들기를 모든 정규 직원 등을 포함 하는 [동적 구성원 자격이 있는 보안 그룹](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) 의 구성원으로 제한 합니다.
- 그룹 만들기를 보안 그룹으로 제한 하 고 사용자가 조직의 그룹 사용 정책에서 보안 그룹의 구성원이 되기 위해 교육을 완료 하도록 요청 합니다.

그룹을 만들 수 있는 사용자를 제한 하려는 경우이를 구성 하는 방법에 대 한 정보를 보려면 [Microsoft 365 그룹을 만들 수 있는 사용자를 관리](manage-creation-of-groups.md) 합니다.

## <a name="group-delete-restore-and-archiving"></a>그룹 삭제, 복원 및 보관

Microsoft 365 그룹을 삭제 하면 기본적으로 30 일간 보존 됩니다. 이 30일의 기간을 "일시 삭제"라고 하며 이 기간 동안 그룹을 복원할 수 있습니다. 30일이 지나면 그룹 및 관련 콘텐츠가 영구적으로 삭제되며 복원할 수 없습니다.

채팅, 파일 또는 메일을 보존 하기 위한 보존 정책이 적용 된 경우 해당 항목은 그룹을 삭제 한 후에도 보존 됩니다. 자세한 내용은 [보존 정책에 대 한](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) 자세한 정보를 참조 하세요.

그룹에 연결 된 서비스 중 하나 이상에 있는 콘텐츠를 보존 하는 것은 아니지만 그룹화 하려면 [보관 그룹, 팀 및 Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information을 참조 하십시오.

## <a name="group-naming-policy"></a>그룹 명명 정책

그룹 명명 정책을 통해 다음과 같은 두 가지 방법으로 그룹을 제어할 수 있습니다.

- 접두사/접미사 명명 정책을 사용 하 여 그룹 이름 및 해당 연결 된 전자 메일 주소에 대 한 시작 또는 끝에 고정 문자열이 나 Azure AD 특성을 적용할 수 있습니다. 이렇게 하면 그룹 이름에 부서 이름이 나 지역이 포함 된 것을 확인할 수 있습니다.
- 차단 된 단어 정책은 임원 이름과 같은 특정 단어가 그룹 이름에 사용 되지 않도록 할 수 있습니다.

그룹에 연결 된 서비스에서 그룹을 만들 때 명명 정책이 적용 됩니다.

그룹에 대해 명명 정책을 사용 하기로 결정 한 경우 [Microsoft 365 groups 명명 정책을](groups-naming-policy.md)참조 하세요.

## <a name="group-expiration-policy"></a>그룹 만료 정책

만료 기간 및 해당 기간 끝에 도달 하 고 갱신 되지 않은 그룹은 삭제 되도록 지정할 수 있습니다. 만료 기간은 그룹을 만들 때 또는 마지막으로 갱신 된 날짜에 시작 됩니다.

그룹 만료로 설정 하는 경우:
- 그룹 소유자는 만료로 인해 그룹 갱신을 알리는 알림을 받습니다.
- 활성 그룹은 자동으로 갱신 됩니다.
- 갱신 되지 않은 그룹은 삭제 됩니다.
- 삭제 된 그룹은 그룹 소유자 또는 관리자가 30 일 이내에 복원할 수 있습니다.

만료 정책은 더 이상 사용 되지 않는 그룹을 삭제 하 여 sprawl 그룹을 제한 하는 좋은 방법입니다. 그룹 만료 정책을 만들려면 [Microsoft 365 그룹 만료 정책을](microsoft-365-groups-expiration-policy.md)참조 하세요.
