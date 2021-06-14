---
title: 보존 정책 및 보존 레이블 정책에 대한 제한 사항
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: 보존 정책 및 보존 레이블 정책에 대한 정책당 최대 정책 및 항목 수 이해
ms.openlocfilehash: 92647911cfc3435c2d88ce5caa0624a34467a60f
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908104"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a><span data-ttu-id="b7959-103">보존 정책 및 보존 레이블 정책에 대한 제한 사항</span><span class="sxs-lookup"><span data-stu-id="b7959-103">Limits for retention policies and retention label policies</span></span>

><span data-ttu-id="b7959-104">*[보안 및 규정 준수에 대한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="b7959-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="b7959-105">[보존 정책 및 보존 레이블 정책](retention.md#retention-policies-and-retention-labels)을 사용하여 조직의 데이터를 자동으로 보존하거나 삭제하는 경우 알아야 할 최대 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-105">When you use [retention policies and retention label policies](retention.md#retention-policies-and-retention-labels) to automatically retain or delete data for your organization, there are some maximum numbers to be aware of.</span></span>

## <a name="maximum-number-of-policies-per-tenant"></a><span data-ttu-id="b7959-106">테넌트당 최대 정책 수</span><span class="sxs-lookup"><span data-stu-id="b7959-106">Maximum number of policies per tenant</span></span>

<span data-ttu-id="b7959-107">단일 테넌트의 경우 최대 10,000개 정책(모든 구성)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-107">A single tenant can have a maximum of 10,000 policies (any configuration).</span></span> <span data-ttu-id="b7959-108">이 최대 수에는 다양한 보존 정책과 DLP 정책, 정보 장벽, eDiscovery 보존 및 민감도 레이블과 같은 규정 준수 정책이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-108">This maximum number includes the different policies for retention, and other policies for compliance such as policies for DLP, information barriers, eDiscovery holds, and sensitivity labels.</span></span>

<span data-ttu-id="b7959-109">이 10,000개의 정책 제한 내에서 워크로드당 보존을 위한 최대 정책 수에 몇 가지 제한도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-109">Within this 10,000 policies limit, there are also some limits on the maximum number of policies for retention per workload:</span></span>

- <span data-ttu-id="b7959-110">Exchange(모든 구성): 1,800</span><span class="sxs-lookup"><span data-stu-id="b7959-110">Exchange (any configuration): 1,800</span></span>
- <span data-ttu-id="b7959-111">SharePoint 또는 OneDrive: (모든 사이트가 자동으로 포함됨): 13</span><span class="sxs-lookup"><span data-stu-id="b7959-111">SharePoint or OneDrive: (all sites automatically included): 13</span></span>
- <span data-ttu-id="b7959-112">SharePoint 또는 OneDrive(특정 위치 포함 또는 제외): 2,600</span><span class="sxs-lookup"><span data-stu-id="b7959-112">SharePoint or OneDrive (specific locations included or excluded): 2,600</span></span>

<span data-ttu-id="b7959-113">Microsoft Teams 및 Yammer에 대한 보존 정책은 사서함을 사용하여 보존 목적으로 데이터를 저장하지만 Exchange Online의 최대 정책 수는 Teams 및 Yammer에 대한 보존 정책을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-113">Although retention policies for Microsoft Teams and Yammer use mailboxes to store data for retention purposes, the maximum number of policies for Exchange Online exclude retention policies for Teams and Yammer.</span></span>

## <a name="maximum-number-of-items-per-policy"></a><span data-ttu-id="b7959-114">정책당 최대 항목 수</span><span class="sxs-lookup"><span data-stu-id="b7959-114">Maximum number of items per policy</span></span>

<span data-ttu-id="b7959-115">선택적 구성을 사용하여 특정 사용자, 특정 Microsoft 365 그룹 또는 특정 사이트에 대한 보존 설정의 범위를 지정하는 경우 다음의 정책별 몇 가지 제한 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-115">If you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of:</span></span> 

<span data-ttu-id="b7959-116">보존 정책당 최대 항목 수:</span><span class="sxs-lookup"><span data-stu-id="b7959-116">Maximum numbers of items per policy for retention:</span></span>

- <span data-ttu-id="b7959-117">Exchange 사서함: 1,000</span><span class="sxs-lookup"><span data-stu-id="b7959-117">Exchange mailboxes: 1,000</span></span>
- <span data-ttu-id="b7959-118">Microsoft 365 그룹: 1,000</span><span class="sxs-lookup"><span data-stu-id="b7959-118">Microsoft 365 Groups: 1,000</span></span>
- <span data-ttu-id="b7959-119">Teams 채널 메시지: 1,000</span><span class="sxs-lookup"><span data-stu-id="b7959-119">Teams channel messages: 1,000</span></span>
- <span data-ttu-id="b7959-120">Teams 채팅: 1,000</span><span class="sxs-lookup"><span data-stu-id="b7959-120">Teams chats: 1,000</span></span>
- <span data-ttu-id="b7959-121">Yammer 커뮤니티 메시지: 1,000</span><span class="sxs-lookup"><span data-stu-id="b7959-121">Yammer community messages: 1,000</span></span>
- <span data-ttu-id="b7959-122">Yammer 사용자 메시지: 1,000</span><span class="sxs-lookup"><span data-stu-id="b7959-122">Yammer user messages: 1,000</span></span>
- <span data-ttu-id="b7959-123">SharePoint 사이트: 100</span><span class="sxs-lookup"><span data-stu-id="b7959-123">SharePoint sites: 100</span></span>
- <span data-ttu-id="b7959-124">OneDrive 계정: 100</span><span class="sxs-lookup"><span data-stu-id="b7959-124">OneDrive accounts: 100</span></span>

<span data-ttu-id="b7959-125">비즈니스용 Skype는 특정 사용자로 범위가 지정되어야 하며 정책당 지원되는 최대 수는 1,000개입니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-125">Skype for Business has to be scoped to specific users and the maximum number supported per policy is 1,000.</span></span>

<span data-ttu-id="b7959-126">이러한 제한 사항은 정책당로 적용되므로 특정 포함 또는 제외를 사용하여 이러한 수를 검토해야 하는 경우 동일한 보존 설정을 가진 추가 정책을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-126">Because these limitations are per policy, if you need to use specific inclusions or exclusions that result in going over these numbers, you can create additional policies that have the same retention settings.</span></span> <span data-ttu-id="b7959-127">이러한 이유로 여러 보존 정책을 사용하는 일부 [예제 시나리오 및 솔루션](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers)은 다음 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b7959-127">See the next section for some [example scenarios and solutions](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) that use multiple retention policies for this reason.</span></span>

<span data-ttu-id="b7959-128">그러나 여러 정책으로 인해 관리 오버헤드가 증가하므로 포함 및 제외가 정말 필요한지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-128">However, multiple policies result in higher administrative overheads, so always confirm whether you really need inclusions and exclusions.</span></span> <span data-ttu-id="b7959-129">전체 위치에 적용되는 기본 구성에는 제한이 없으며, 이 구성 선택은 여러 정책을 만들고 유지하는 것보다 더 나은 솔루션이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-129">Remember that the default configuration that applies to the entire location doesn't have any limitations, and this configuration choice might be a better solution than creating and maintaining multiple policies.</span></span>

> [!TIP]
> <span data-ttu-id="b7959-130">이 시나리오에 대해 여러 정책을 생성하고 유지 관리해야하는 경우 보다 효율적인 구성을 위해 [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels)을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-130">If do you need to create and maintain multiple policies for this scenario, consider using [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) for more efficient configuration.</span></span>

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a><span data-ttu-id="b7959-131">최대 수 초과를 방지하는 여러 정책을 사용하는 예</span><span class="sxs-lookup"><span data-stu-id="b7959-131">Examples of using multiple policies to avoid exceeding maximum numbers</span></span>

<span data-ttu-id="b7959-132">다음 예제는 보존 정책의 위치만 지정할 수 없는 경우에 대한 몇 가지 설계 솔루션을 제공하며, 이전 섹션에서 설명한 최대 항목 수를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-132">The following examples provide some design solutions for when you can't specify just the location for a retention policy, and must take into account the maximum number of items documented in the previous section.</span></span>

<span data-ttu-id="b7959-133">Exchange 예제:</span><span class="sxs-lookup"><span data-stu-id="b7959-133">Exchange example:</span></span>

- <span data-ttu-id="b7959-134">**요구 사항**: 사용자 사서함이 40,000개 이상인 조직에서 대부분의 사용자는 7년 동안 전자 메일을 보존해야 하지만 식별된 사용자(425명)의 하위 집합은 5년 동안만 전자 메일을 보존해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-134">**Requirement**: In an organization that has over 40,000 user mailboxes, most users must have their email retained for 7 years but a subset of identified users (425) must have their email retained for only 5 years.</span></span>

- <span data-ttu-id="b7959-135">**솔루션**: 보존 기간이 7년인 Exchange 전자 메일에 대해 하나의 보존 정책을 생성하고 사용자 하위 집합을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-135">**Solution**: Create one retention policy for Exchange email with a retention period of 7 years and exclude the subset of users.</span></span> <span data-ttu-id="b7959-136">그런 다음 보존 기간이 5년인 Exchange 전자 메일에 대한 두 번째 보존 정책을 생성하고 사용자 하위 집합을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-136">Then create a second retention policy for Exchange email with a retention period of 5 years and include the subset of users.</span></span> 
    
    <span data-ttu-id="b7959-137">두 경우 모두 포함 및 제외된 수는 단일 정책에 대해 지정된 최대 사서함 수보다 적으며, 두 번째 정책보다 [보존 기간이 길기 때문에](retention.md#the-principles-of-retention-or-what-takes-precedence) 사용자 하위 집합은 첫 번째 정책에서 명시적으로 제외되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-137">In both cases, the number included and excluded is below the maximum number of specified mailboxes for a single policy, and the subset of users must be explicitly excluded from the first policy because it has a [longer retention period](retention.md#the-principles-of-retention-or-what-takes-precedence) than the second policy.</span></span> <span data-ttu-id="b7959-138">사용자 하위 집합에서 더 긴 보존 정책이 필요한 경우 첫 번째 정책에서 제외할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-138">If the subset of users required a longer retention policy, you wouldn't need to exclude them from the first policy.</span></span>
     
    <span data-ttu-id="b7959-139">이 솔루션을 사용하면 새로 참가한 사람이 있으면 해당 우편함이 7년 동안 자동으로 첫 번째 정책에 포함되며 지원되는 최대 수에 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-139">With this solution, if anybody new joins the organization, their mailbox is automatically included in the first policy for 7 years and there is no impact to the maximum numbers supported.</span></span> <span data-ttu-id="b7959-140">그러나 5년 보존 기간이 필요한 새 사용자는 포함 및 제외 수에 추가되며 이 제한은 1,000에 도달하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-140">However, new users that require the 5-year retention period add to the include and exclude numbers, and this limit would be reached at 1,000.</span></span>

<span data-ttu-id="b7959-141">SharePoint 예제</span><span class="sxs-lookup"><span data-stu-id="b7959-141">SharePoint example:</span></span>

- <span data-ttu-id="b7959-142">**요구 사항**: 한 조직에서 SharePoint 사이트는 수천 개이지만 2,000개 사이트만 10년 보존 기간이 필요하며 8,000개 사이트에서는 4년 보존 기간이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-142">**Requirement**: An organization has several thousand SharePoint sites but only 2,000 sites require a retention period of 10 years, and 8,000 sites require a retention period of 4 years.</span></span>

- <span data-ttu-id="b7959-143">**솔루션**: 100개의 특정 사이트를 포함하는 10년의 보존 기간으로 SharePoint용 20개 보존 정책을 생성하고, 100개의 특정 사이트를 포함하는 4년의 보존 기간으로 SharePoint용 80개 보존 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-143">**Solution**: Create 20 retention policies for SharePoint with a retention period of 10 years that includes 100 specific sites, and create 80 retention policies for SharePoint with a retention period of 4 years that includes 100 specific sites.</span></span>
    
    <span data-ttu-id="b7959-144">모든 SharePoint 사이트를 보유할 필요는 없으므로 특정 사이트를 지정하는 보존 정책을 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-144">Because you don't need to retain all SharePoint sites, you must create retention policies that specify the specific sites.</span></span> <span data-ttu-id="b7959-145">보존 정책은 100개 이상의 지정된 사이트를 지원하지 않으므로 두 보존 기간에 대해 여러 정책을 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-145">Because a retention policy doesn't support more than 100 specified sites, you must create multiple policies for the two retention periods.</span></span> <span data-ttu-id="b7959-146">이러한 보존 정책에는 최대 개수의 사이트가 포함되므로 보존해야 하는 다음 새 사이트에는 보존 기간에 관계없이 새 보존 정책이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-146">These retention policies  have the maximum number of included sites, so the next new site that needs retaining would require a new retention policy, irrespective of the retention period.</span></span>

## <a name="maximum-number-of-items-for-disposition"></a><span data-ttu-id="b7959-147">처리용 최대 항목 수</span><span class="sxs-lookup"><span data-stu-id="b7959-147">Maximum number of items for disposition</span></span>

<span data-ttu-id="b7959-148">[콘텐츠 처리](disposition.md)에는 몇 가지 유의해야 할 한도가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7959-148">For the [disposition of content](disposition.md), there are some limits to be aware of:</span></span>

- <span data-ttu-id="b7959-149">각 보존 레이블의 스테이지당 처리 보류 항목 1,000,000개</span><span class="sxs-lookup"><span data-stu-id="b7959-149">1,000,000 items pending disposition per stage for each retention label</span></span>

- <span data-ttu-id="b7959-150">항목이 처리되고 난 후 최대 7년간 처리 증거(해당 기간의 보존 레이블당 최대 한도 항목 1,000,000개).</span><span class="sxs-lookup"><span data-stu-id="b7959-150">Proof of disposition for up to seven years after the item was disposed, with a limit of 1,000,000 items per retention label for that period.</span></span> 
    
<span data-ttu-id="b7959-151">이 레코드로 표시된 항목의 최대 한도인 1,000,000개 이상에 대한 처리 증거가 필요하다면 [Microsoft 지원](../business-video/get-help-support.md)에 문의해 주세요.</span><span class="sxs-lookup"><span data-stu-id="b7959-151">If you need proof of disposition higher than this limit of 1,000,000 for items that are marked as records, contact [Microsoft Support](../business-video/get-help-support.md).</span></span>
