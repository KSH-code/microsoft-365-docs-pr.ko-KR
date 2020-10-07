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
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Microsoft 365의 공동 작업 도구에 대 한 수명 주기 관리 옵션에 대해 자세히 알아봅니다.
ms.openlocfilehash: 706f1aaecf22c4088d4539c208fef68320c5e710
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377190"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="f209b-103">Microsoft 365 그룹 및 Microsoft 팀에 대 한 조직 및 수명 주기 거 버 넌 스 계획</span><span class="sxs-lookup"><span data-stu-id="f209b-103">Plan organization and lifecycle governance for Microsoft 365 groups and Microsoft Teams</span></span>

<span data-ttu-id="f209b-104">Microsoft 365 그룹에는 조직에 필요한 거 버 넌 스 기능을 구현 하기 위한 다양 한 도구 집합이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-104">Microsoft 365 groups has a rich set of tools to implement the governance capabilities your organization requires.</span></span> 

<span data-ttu-id="f209b-105">다음 섹션에서는 이러한 기능에 대해 설명 하 고 최상의 방법을 권장 하며, 거 버 넌 스에 대 한 요구 사항을 확인 하 고 문제를 충족 하는 방법을 문의할 수 있는 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-105">The following section describes the capabilities, recommends best practices, and provides guidance to ask the right questions to determine the requirements for governance, and how to meet them.</span></span>

## <a name="control-who-can-create-microsoft-365-groups"></a><span data-ttu-id="f209b-106">Microsoft 365 그룹을 만들 수 있는 사용자 제어</span><span class="sxs-lookup"><span data-stu-id="f209b-106">Control who can create Microsoft 365 groups</span></span>

<span data-ttu-id="f209b-107">최종 사용자가 Outlook, SharePoint, 팀 및 기타 환경을 비롯 한 여러 최종 지점에서 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-107">Groups can be created by end-users from multiple end-points including Outlook, SharePoint, Teams, and other environments.</span></span>

![이미지 desc](../media/04.png)

<span data-ttu-id="f209b-109">그룹 소유자의 역량을 강화 하 고 사용자가 작업을 보다 쉽게 수행할 수 있도록 지원 하기 위해 셀프 서비스를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-109">We highly recommend self-service to empower group owners and help users get their work done more easily.</span></span> <span data-ttu-id="f209b-110">그룹 및 팀 만들기를 제한 하면 서비스 작동을 위해 그룹을 만들어야 하는 Microsoft 365 서비스가 많으므로 사용자 생산성이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-110">Limiting group and team creation can slow users productivity because many Microsoft 365 services require that groups be created for the service to function.</span></span>

<span data-ttu-id="f209b-111">그룹을 만들 때는 다음과 같은 거 버 넌 스 옵션을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-111">Consider the following governance options for groups creation:</span></span>

- <span data-ttu-id="f209b-112">그룹 sprawl을 제한 하려면 [그룹 만료 정책을](microsoft-365-groups-expiration-policy.md) 사용 하 여 사용 되지 않는 그룹을 자동으로 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-112">To limit group sprawl, use [groups expiration policies](microsoft-365-groups-expiration-policy.md) to automatically delete groups that are not being used.</span></span>
- <span data-ttu-id="f209b-113">그룹 만들기를 모든 정규 직원 등을 포함 하는 [동적 구성원 자격이 있는 보안 그룹](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) 의 구성원으로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-113">Limit group creation to members of a [security groups with dynamic membership](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) containing, for example, all full-time employees.</span></span>
- <span data-ttu-id="f209b-114">그룹 만들기를 보안 그룹으로 제한 하 고 사용자가 조직의 그룹 사용 정책에서 보안 그룹의 구성원이 되기 위해 교육을 완료 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-114">Limit group creation to a security group and require users to complete training in your organization's group usage policies in order to become members of the security group.</span></span>

<span data-ttu-id="f209b-115">그룹을 만들 수 있는 사용자를 제한 하려는 경우이를 구성 하는 방법에 대 한 정보를 보려면 [Microsoft 365 그룹을 만들 수 있는 사용자를 관리](manage-creation-of-groups.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-115">If you want to limit who can create groups, see [Manage who can create Microsoft 365 groups](manage-creation-of-groups.md) for information on how to configure this.</span></span>

## <a name="group-delete-restore-and-archiving"></a><span data-ttu-id="f209b-116">그룹 삭제, 복원 및 보관</span><span class="sxs-lookup"><span data-stu-id="f209b-116">Group delete, restore, and archiving</span></span>

<span data-ttu-id="f209b-117">Microsoft 365 그룹을 삭제 하면 기본적으로 30 일간 보존 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-117">When a Microsoft 365 group is deleted, by default it's retained for 30 days.</span></span> <span data-ttu-id="f209b-118">이 30일의 기간을 "일시 삭제"라고 하며 이 기간 동안 그룹을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-118">This 30-day period is called "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="f209b-119">30일이 지나면 그룹 및 관련 콘텐츠가 영구적으로 삭제되며 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-119">After 30 days, the group and associated content is permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="f209b-120">채팅, 파일 또는 메일을 보존 하기 위한 보존 정책이 적용 된 경우 해당 항목은 그룹을 삭제 한 후에도 보존 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-120">If you have retention policies in place to retain chat, files, or mail, those items will be preserved after the group is deleted.</span></span> <span data-ttu-id="f209b-121">자세한 내용은 [보존 정책에 대 한](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) 자세한 정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f209b-121">See [Learn about retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) for details.</span></span>

<span data-ttu-id="f209b-122">그룹에 연결 된 서비스 중 하나 이상에 있는 콘텐츠를 보존 하는 것은 아니지만 그룹화 하려면 [보관 그룹, 팀 및 Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f209b-122">If you want to delete a group but preserve the content from one or more of the group-connected services, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information.</span></span>

## <a name="group-naming-policy"></a><span data-ttu-id="f209b-123">그룹 명명 정책</span><span class="sxs-lookup"><span data-stu-id="f209b-123">Group naming policy</span></span>

<span data-ttu-id="f209b-124">그룹 명명 정책을 통해 다음과 같은 두 가지 방법으로 그룹을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-124">A groups naming policy can help you govern groups in two ways:</span></span>

- <span data-ttu-id="f209b-125">접두사/접미사 명명 정책을 사용 하 여 그룹 이름 및 해당 연결 된 전자 메일 주소에 대 한 시작 또는 끝에 고정 문자열이 나 Azure AD 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-125">A prefix/suffix naming policy can be used to enforce fixed strings or Azure AD attributes at the beginning or end of a group name and its associated email address.</span></span> <span data-ttu-id="f209b-126">이렇게 하면 그룹 이름에 부서 이름이 나 지역이 포함 된 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-126">By doing this, you can ensure the inclusion of, for example, department names or regions in group names.</span></span>
- <span data-ttu-id="f209b-127">차단 된 단어 정책은 임원 이름과 같은 특정 단어가 그룹 이름에 사용 되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-127">A blocked words policy can ensure that certain words, such as the names of executives, are not used in group names.</span></span>

<span data-ttu-id="f209b-128">그룹에 연결 된 서비스에서 그룹을 만들 때 명명 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-128">Naming policies are applied when groups are created from any of the group-connected services.</span></span>

<span data-ttu-id="f209b-129">그룹에 대해 명명 정책을 사용 하기로 결정 한 경우 [Microsoft 365 groups 명명 정책을](groups-naming-policy.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f209b-129">If you decide to use naming policies for groups, see [Microsoft 365 Groups naming policy](groups-naming-policy.md).</span></span>

## <a name="group-expiration-policy"></a><span data-ttu-id="f209b-130">그룹 만료 정책</span><span class="sxs-lookup"><span data-stu-id="f209b-130">Group expiration policy</span></span>

<span data-ttu-id="f209b-131">만료 기간 및 해당 기간 끝에 도달 하 고 갱신 되지 않은 그룹은 삭제 되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-131">You can specify an expiration period and any group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="f209b-132">만료 기간은 그룹을 만들 때 또는 마지막으로 갱신 된 날짜에 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-132">The expiration period begins when the group is created, or on the date it was last renewed.</span></span>

<span data-ttu-id="f209b-133">그룹 만료로 설정 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="f209b-133">Once you set groups to expire:</span></span>
- <span data-ttu-id="f209b-134">그룹 소유자는 만료로 인해 그룹 갱신을 알리는 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-134">Owners of the group are notified to renew the group as the expiration nears.</span></span>
- <span data-ttu-id="f209b-135">활성 그룹은 자동으로 갱신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-135">Active groups are renewed automatically.</span></span>
- <span data-ttu-id="f209b-136">갱신 되지 않은 그룹은 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-136">Any group that is not renewed is deleted.</span></span>
- <span data-ttu-id="f209b-137">삭제 된 그룹은 그룹 소유자 또는 관리자가 30 일 이내에 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-137">Any group that is deleted can be restored within 30 days by the group owners or the admin.</span></span>

<span data-ttu-id="f209b-138">만료 정책은 더 이상 사용 되지 않는 그룹을 삭제 하 여 sprawl 그룹을 제한 하는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-138">Expiration policies are a good way to limit group sprawl by ensuring that groups that are no longer in use are deleted.</span></span> <span data-ttu-id="f209b-139">그룹 만료 정책을 만들려면 [Microsoft 365 그룹 만료 정책을](microsoft-365-groups-expiration-policy.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f209b-139">If you want to create a group expiration policy, see [Microsoft 365 Group Expiration Policy](microsoft-365-groups-expiration-policy.md).</span></span>
