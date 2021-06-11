---
title: Microsoft 365 및 사용자에 대한 조직 및 수명 주기 거버넌스 Microsoft Teams
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
recommendations: false
description: 공동 작업 도구에 대한 수명 주기 거버넌스 옵션에 대해 Microsoft 365
ms.openlocfilehash: 7d88618b75ef731bf38df029970efdc05f3eea5a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538822"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="e5dd5-103">Microsoft 365 및 사용자에 대한 조직 및 수명 주기 거버넌스 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e5dd5-103">Plan organization and lifecycle governance for Microsoft 365 groups and Microsoft Teams</span></span>

<span data-ttu-id="e5dd5-104">Microsoft 365 그룹에는 조직에 필요한 거버넌스 기능을 구현하기 위한 다양한 도구 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-104">Microsoft 365 groups has a rich set of tools to implement the governance capabilities your organization requires.</span></span> 

<span data-ttu-id="e5dd5-105">다음 섹션에서는 기능에 대해 설명하고 모범 사례를 권장하며, 거버넌스 요구 사항을 결정하기 위한 올바른 질문과 요구 사항을 충족하는 방법을 결정하는 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-105">The following section describes the capabilities, recommends best practices, and provides guidance to ask the right questions to determine the requirements for governance, and how to meet them.</span></span>

## <a name="control-who-can-create-microsoft-365-groups"></a><span data-ttu-id="e5dd5-106">그룹을 만들 수 있는 Microsoft 365 제어</span><span class="sxs-lookup"><span data-stu-id="e5dd5-106">Control who can create Microsoft 365 groups</span></span>

<span data-ttu-id="e5dd5-107">그룹은 최종 사용자가 Outlook, SharePoint, 기타 환경 등 여러 끝점에서 Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-107">Groups can be created by end-users from multiple end-points including Outlook, SharePoint, Teams, and other environments.</span></span>

![이미지 desc](../media/04.png)

<span data-ttu-id="e5dd5-109">그룹 소유자에게 권한을 부여하고 사용자가 작업을 보다 쉽게 완료할 수 있도록 셀프 서비스를 권장하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-109">We highly recommend self-service to empower group owners and help users get their work done more easily.</span></span> <span data-ttu-id="e5dd5-110">그룹 및 팀 만들기를 제한하면 많은 Microsoft 365 서비스를 사용하려면 그룹을 만들어야 하기 때문에 사용자의 생산성이 늦어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-110">Limiting group and team creation can slow users productivity because many Microsoft 365 services require that groups be created for the service to function.</span></span>

<span data-ttu-id="e5dd5-111">그룹을 만들 때 다음과 같은 거버넌스 옵션을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-111">Consider the following governance options for groups creation:</span></span>

- <span data-ttu-id="e5dd5-112">그룹 시작을 제한하려면 그룹 [](microsoft-365-groups-expiration-policy.md) 만료 정책을 사용하여 사용되지 않는 그룹을 자동으로 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-112">To limit group sprawl, use [groups expiration policies](microsoft-365-groups-expiration-policy.md) to automatically delete groups that are not being used.</span></span>
- <span data-ttu-id="e5dd5-113">그룹 만들기를 동적 [](/azure/active-directory/users-groups-roles/groups-create-rule) 구성원이 포함된 보안 그룹의 구성원(예: 모든 정규 직원)으로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-113">Limit group creation to members of a [security groups with dynamic membership](/azure/active-directory/users-groups-roles/groups-create-rule) containing, for example, all full-time employees.</span></span>
- <span data-ttu-id="e5dd5-114">그룹 만들기를 보안 그룹으로 제한하고 사용자가 보안 그룹의 구성원이 되기 위해 조직의 그룹 사용 정책에 대한 교육을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-114">Limit group creation to a security group and require users to complete training in your organization's group usage policies in order to become members of the security group.</span></span>

<span data-ttu-id="e5dd5-115">그룹을 만들 수 있는 사용자만 제한하려는 경우 그룹을 만들 수 있는 사용자 관리를 Microsoft 365 구성하는 방법에 대한 자세한 내용은 Manage who can create [Microsoft 365](manage-creation-of-groups.md) for how to configure this을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-115">If you want to limit who can create groups, see [Manage who can create Microsoft 365 groups](manage-creation-of-groups.md) for information on how to configure this.</span></span>

## <a name="group-delete-restore-and-archiving"></a><span data-ttu-id="e5dd5-116">그룹 삭제, 복원 및 보관</span><span class="sxs-lookup"><span data-stu-id="e5dd5-116">Group delete, restore, and archiving</span></span>

<span data-ttu-id="e5dd5-117">Microsoft 365 그룹이 삭제되면 기본적으로 30일 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-117">When a Microsoft 365 group is deleted, by default it's retained for 30 days.</span></span> <span data-ttu-id="e5dd5-118">이 30일의 기간을 "일시 삭제"라고 하며 이 기간 동안 그룹을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-118">This 30-day period is called "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="e5dd5-119">30일이 지나면 그룹 및 관련 콘텐츠가 영구적으로 삭제되며 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-119">After 30 days, the group and associated content is permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="e5dd5-120">채팅, 파일 또는 메일을 보존하기 위한 보존 정책이 있는 경우 그룹이 삭제된 후에 해당 항목이 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-120">If you have retention policies in place to retain chat, files, or mail, those items will be preserved after the group is deleted.</span></span> <span data-ttu-id="e5dd5-121">자세한 [내용은 보존 정책에](../compliance/retention.md) 대한 자세한 정보를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-121">See [Learn about retention policies](../compliance/retention.md) for details.</span></span>

<span data-ttu-id="e5dd5-122">그룹을 삭제하 고 하나 이상의 그룹에 연결된 서비스의 콘텐츠를 유지하려면 보관 [그룹,](end-life-cycle-groups-teams-sites-yammer.md) 팀 및 Yammer 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-122">If you want to delete a group but preserve the content from one or more of the group-connected services, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information.</span></span>

## <a name="group-naming-policy"></a><span data-ttu-id="e5dd5-123">그룹 이름 정책</span><span class="sxs-lookup"><span data-stu-id="e5dd5-123">Group naming policy</span></span>

<span data-ttu-id="e5dd5-124">그룹 이름 정책은 다음 두 가지 방법으로 그룹을 관리하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-124">A groups naming policy can help you govern groups in two ways:</span></span>

- <span data-ttu-id="e5dd5-125">접두사/접미사 명명 정책을 사용하여 그룹 이름 및 연결된 전자 메일 주소의 시작 또는 끝에 고정 문자열 또는 Azure AD 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-125">A prefix/suffix naming policy can be used to enforce fixed strings or Azure AD attributes at the beginning or end of a group name and its associated email address.</span></span> <span data-ttu-id="e5dd5-126">이렇게 하면 부서 이름이나 그룹 이름에 지역을 포함하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-126">By doing this, you can ensure the inclusion of, for example, department names or regions in group names.</span></span>
- <span data-ttu-id="e5dd5-127">차단된 단어 정책은 임원 이름과 같은 특정 단어가 그룹 이름에 사용되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-127">A blocked words policy can ensure that certain words, such as the names of executives, are not used in group names.</span></span>

<span data-ttu-id="e5dd5-128">그룹 연결 서비스에서 그룹을 만들면 이름 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-128">Naming policies are applied when groups are created from any of the group-connected services.</span></span>

<span data-ttu-id="e5dd5-129">그룹에 대해 이름 정책을 사용하기로 결정한 경우 그룹 Microsoft 365 [정책을 참조합니다.](groups-naming-policy.md)</span><span class="sxs-lookup"><span data-stu-id="e5dd5-129">If you decide to use naming policies for groups, see [Microsoft 365 Groups naming policy](groups-naming-policy.md).</span></span>

## <a name="group-expiration-policy"></a><span data-ttu-id="e5dd5-130">그룹 만료 정책</span><span class="sxs-lookup"><span data-stu-id="e5dd5-130">Group expiration policy</span></span>

<span data-ttu-id="e5dd5-131">만료 기간을 지정할 수 있으며 해당 기간이 끝나고 갱신되지 않은 그룹은 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-131">You can specify an expiration period and any group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="e5dd5-132">만료 기간은 그룹이 만들어지거나 마지막으로 갱신된 날짜부터 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-132">The expiration period begins when the group is created, or on the date it was last renewed.</span></span>

<span data-ttu-id="e5dd5-133">그룹이 만료될 수 있는 것으로 설정하면 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-133">Once you set groups to expire:</span></span>
- <span data-ttu-id="e5dd5-134">그룹의 소유자는 만료가 다가오면 그룹을 갱신할 수 있는 알림을 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-134">Owners of the group are notified to renew the group as the expiration nears.</span></span>
- <span data-ttu-id="e5dd5-135">활성 그룹은 자동으로 갱신됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-135">Active groups are renewed automatically.</span></span>
- <span data-ttu-id="e5dd5-136">갱신되지 않은 그룹은 모두 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-136">Any group that is not renewed is deleted.</span></span>
- <span data-ttu-id="e5dd5-137">삭제된 모든 그룹은 그룹 소유자 또는 관리자가 30일 이내에 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-137">Any group that is deleted can be restored within 30 days by the group owners or the admin.</span></span>

<span data-ttu-id="e5dd5-138">만료 정책은 더 이상 사용되지 않는 그룹을 삭제하도록 하여 그룹 스플로링을 제한하는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-138">Expiration policies are a good way to limit group sprawl by ensuring that groups that are no longer in use are deleted.</span></span> <span data-ttu-id="e5dd5-139">그룹 만료 정책을 만들 경우 그룹 만료 [정책 Microsoft 365 참조합니다.](microsoft-365-groups-expiration-policy.md)</span><span class="sxs-lookup"><span data-stu-id="e5dd5-139">If you want to create a group expiration policy, see [Microsoft 365 Group Expiration Policy](microsoft-365-groups-expiration-policy.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e5dd5-140">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e5dd5-140">Related topics</span></span>

[<span data-ttu-id="e5dd5-141">공동 작업 거버넌스 계획 단계별</span><span class="sxs-lookup"><span data-stu-id="e5dd5-141">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="e5dd5-142">공동 작업 거버넌스 계획 만들기</span><span class="sxs-lookup"><span data-stu-id="e5dd5-142">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="e5dd5-143">이전 직원 제거 및 보안 데이터</span><span class="sxs-lookup"><span data-stu-id="e5dd5-143">Remove a former employee and secure data</span></span>](/microsoft-365/admin/add-users/remove-former-employee)
