---
title: 이벤트 구동 보존 개요
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-may2020
- seo-marvel-jun2020
description: 일반적으로 레코드 관리 솔루션의 일부는 사용자가 식별하는 이벤트에 기반하여 보존 기간을 시작하는 보존 레이블을 구성할 수 있습니다.
ms.openlocfilehash: 1e716cc886e8378308054d4f2eedf961045f4486
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817807"
---
# <a name="overview-of-event-driven-retention"></a><span data-ttu-id="06c4c-103">이벤트 구동 보존 개요</span><span class="sxs-lookup"><span data-stu-id="06c4c-103">Overview of event-driven retention</span></span>

><span data-ttu-id="06c4c-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="06c4c-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="06c4c-105">When you retain content, the retention period is often based on the age of the content - for example, you might retain documents for seven years after they're created and then delete them.</span><span class="sxs-lookup"><span data-stu-id="06c4c-105">When you retain content, the retention period is often based on the age of the content - for example, you might retain documents for seven years after they're created and then delete them.</span></span> <span data-ttu-id="06c4c-106">But with retention labels in Microsoft 365, you can also base a retention period on when a specific type of event occurs.</span><span class="sxs-lookup"><span data-stu-id="06c4c-106">But with retention labels in Microsoft 365, you can also base a retention period on when a specific type of event occurs.</span></span> <span data-ttu-id="06c4c-107">The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span><span class="sxs-lookup"><span data-stu-id="06c4c-107">The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="06c4c-108">예를 들어 다음에 대해 이벤트 구동 보존이 적용된 레이블을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-108">For example, you can use labels with event-driven retention for:</span></span>
  
- <span data-ttu-id="06c4c-109">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span><span class="sxs-lookup"><span data-stu-id="06c4c-109">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="06c4c-110">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee need to be disposed.</span><span class="sxs-lookup"><span data-stu-id="06c4c-110">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee need to be disposed.</span></span> <span data-ttu-id="06c4c-111">The event that triggers the 10-year retention period is the employee leaving the organization.</span><span class="sxs-lookup"><span data-stu-id="06c4c-111">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="06c4c-112">**Contract expiration** Suppose that all records related to contracts need to be retained for five years from the time the contract expires.</span><span class="sxs-lookup"><span data-stu-id="06c4c-112">**Contract expiration** Suppose that all records related to contracts need to be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="06c4c-113">The event that triggers the five-year retention period is the expiration of the contract.</span><span class="sxs-lookup"><span data-stu-id="06c4c-113">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="06c4c-114">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications.</span><span class="sxs-lookup"><span data-stu-id="06c4c-114">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications.</span></span> <span data-ttu-id="06c4c-115">In this case, the last manufacturing date is the event that triggers the retention period.</span><span class="sxs-lookup"><span data-stu-id="06c4c-115">In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="06c4c-116">Event-driven retention is typically used as part of a records-management process.</span><span class="sxs-lookup"><span data-stu-id="06c4c-116">Event-driven retention is typically used as part of a records-management process.</span></span> <span data-ttu-id="06c4c-117">This means that:</span><span class="sxs-lookup"><span data-stu-id="06c4c-117">This means that:</span></span>
  
- <span data-ttu-id="06c4c-118">Labels based on events also usually classify content as a record.</span><span class="sxs-lookup"><span data-stu-id="06c4c-118">Labels based on events also usually classify content as a record.</span></span> <span data-ttu-id="06c4c-119">For more information, see [Using Content Search to find all content with a specific retention label applied to it](labels.md#using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it).</span><span class="sxs-lookup"><span data-stu-id="06c4c-119">For more information, see [Using Content Search to find all content with a specific retention label applied to it](labels.md#using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it).</span></span>
    
- <span data-ttu-id="06c4c-120">기록으로 선언되었으나 해당 이벤트 트리거가 아직 발생하지 않은 문서는 문서의 보존 기간을 트리거하는 이벤트가 발생할 때까지 무기한 보존됩니다(기록을 영구히 삭제할 수 없음).</span><span class="sxs-lookup"><span data-stu-id="06c4c-120">A document that's been declared as a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="06c4c-121">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose the content.</span><span class="sxs-lookup"><span data-stu-id="06c4c-121">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose the content.</span></span> <span data-ttu-id="06c4c-122">For more information, see [Disposition of content](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="06c4c-122">For more information, see [Disposition of content](disposition.md).</span></span>
    
<span data-ttu-id="06c4c-123">이벤트 기반의 레이블은 Office 365의 모든 보존 레이블과 같은 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-123">A label based on an event has the same capabilities as any retention label in Microsoft  365.</span></span> <span data-ttu-id="06c4c-124">자세한 내용은 [보존 레이블에 대해 자세히 알아보기](labels.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06c4c-124">For more information, see [Learn about retention labels](labels.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="06c4c-125">이벤트 유형, 레이블, 이벤트 및 자산 ID 간 관계 이해</span><span class="sxs-lookup"><span data-stu-id="06c4c-125">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="06c4c-126">이벤트 구동 보존을 성공적으로 사용하려면 다음과 같은 다이어그램 및 설명에 있는 것처럼 이벤트 유형, 보존 레이블, 이벤트 및 자산 ID 간 관계를 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-126">To successfully use event-driven retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![이벤트 유형, 레이블, 이벤트 및 자산 ID의 다이어그램](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![이벤트 유형, 레이블, 이벤트 및 자산 ID의 다이어그램](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="06c4c-129">콘텐츠 유형에 따라 보존 레이블을 작성한 후 이벤트 유형과 연관시킵니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-129">You create retention labels for different types of content and then associate them with a type of event.</span></span> <span data-ttu-id="06c4c-130">예를 들어, 다양 한 유형의 제품 파일 및 기록에 대한 레이블은 해당 기록을 제품이 수명에 도달한 시점부터 10년 동안 보존해야 하므로 제품 수명이라는 이벤트 유형에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-130">For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="06c4c-131">사용자(일반적으로 레코드 관리자)는 해당 보존 레이블을 콘텐츠에 적용하고, SharePoint 및 OneDrive 문서의 경우에는 각 항목에 대해 자산 ID를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-131">Users (typically records managers) apply those retention labels to content and (for SharePoint and OneDrive documents) enter an asset ID for each item.</span></span> <span data-ttu-id="06c4c-132">이 예에서 자산 ID는 조직에서 사용하는 제품 이름 또는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-132">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="06c4c-133">따라서 각 제품의 레코드에는 보존 레이블이 할당되고 각 레코드는 자산 ID가 포함된 특성을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-133">Thus, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="06c4c-134">다이어그램은 조직의 모든 제품 레코드에 대한 **모든 콘텐츠**를 표시하며 각 항목은 레코드가 있는 제품의 자산 ID를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-134">The diagram represents **all of the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="06c4c-135">Product Lifetime is the event type; a specific product reaching end of life is an event.</span><span class="sxs-lookup"><span data-stu-id="06c4c-135">Product Lifetime is the event type; a specific product reaching end of life is an event.</span></span> <span data-ttu-id="06c4c-136">When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:</span><span class="sxs-lookup"><span data-stu-id="06c4c-136">When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:</span></span>
    
  - <span data-ttu-id="06c4c-137">자산 ID(SharePoint 및 OneDrive 문서 관련)</span><span class="sxs-lookup"><span data-stu-id="06c4c-137">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
  - <span data-ttu-id="06c4c-138">Keywords (for Exchange items).</span><span class="sxs-lookup"><span data-stu-id="06c4c-138">Keywords (for Exchange items).</span></span> <span data-ttu-id="06c4c-139">In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span><span class="sxs-lookup"><span data-stu-id="06c4c-139">In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
  - <span data-ttu-id="06c4c-140">The date when the event occurred.</span><span class="sxs-lookup"><span data-stu-id="06c4c-140">The date when the event occurred.</span></span> <span data-ttu-id="06c4c-141">This date is used as the start of the retention period.</span><span class="sxs-lookup"><span data-stu-id="06c4c-141">This date is used as the start of the retention period.</span></span> <span data-ttu-id="06c4c-142">This date can be the current, a past, or a future date.</span><span class="sxs-lookup"><span data-stu-id="06c4c-142">This date can be the current, a past, or a future date.</span></span>
    
4. <span data-ttu-id="06c4c-143">이벤트를 작성한 후, 해당 이벤트 날짜는 해당 이벤트 유형의 보존 레이블이 있으며 지정된 자산 ID 또는 키워드를 포함하는 모든 콘텐츠와 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-143">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="06c4c-144">모든 보존 레이블과 마찬가지로 이 동기화는 7일 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-144">Like any retention label, this synchronization can take up to 7 days.</span></span> <span data-ttu-id="06c4c-145">이전 다이어그램에서 빨간색 원으로 둘러싸인 모든 항목에는이 이벤트를 통해 트리거되는 보존 기간이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-145">In the previous diagram, all the items circled in red have their retention period triggered by this event .</span></span> <span data-ttu-id="06c4c-146">즉, 이 제품이 수명의 끝에 도달하면 해당 이벤트는 해당 제품의 레코드에 대한 보존 기간을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-146">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>
    
<span data-ttu-id="06c4c-147">이벤트에 대해 자산 ID 또는 키워드를 지정하지 않으면 해당 이벤트 유형의 레이블이 있는 **모든 콘텐츠**가 이벤트에 의해 트리거된 보존 기간을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-147">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="06c4c-148">이는 위의 다이어그램에서 모든 콘텐츠가 유지되기 시작한다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-148">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="06c4c-149">이는 원치 않는 일일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-149">This might not be what you intend.</span></span> 
  
<span data-ttu-id="06c4c-150">마지막으로 각 보존 레이블에는 별도의 보존 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-150">Finally, remember that each retention label has its own retention settings.</span></span> <span data-ttu-id="06c4c-151">이 예에서는 모든 레이블이 10년을 지정하지만 각 레이블의 보존 기간이 다른 경우 이벤트가 보존 레이블을 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-151">In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="06c4c-152">이벤트 구동 보존 설정 방법</span><span class="sxs-lookup"><span data-stu-id="06c4c-152">How to set up event-driven retention</span></span>

<span data-ttu-id="06c4c-153">이벤트 구동 보존의 상위 레벨 워구동우우:</span><span class="sxs-lookup"><span data-stu-id="06c4c-153">High-level workflow for event-driven retention:</span></span>
  
![이벤트 구동 보존을 설정하는 워크플로 다이어그램](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="06c4c-155">SharePont에서 관리 속성을 사용하여 보존 레이블을 자동 적용하고 이벤트 중심 보존을 구현하는 방법에 대한 자세한 시나리오는 [보존 레이블로 SharePoint 문서의 수명 주기 관리](auto-apply-retention-labels-scenario.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06c4c-155">See [Manage the lifecycle of SharePoint documents with retention labels](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="06c4c-156">1단계: 보존 기간이 이벤트에 따라 조정되는 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="06c4c-156">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="06c4c-157">Microsoft 365 규정 준수 센터의 왼쪽 탐색 창에서 **정보 거버넌스** > **레이블** > **레이블 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-157">In the Microsoft 365 compliance center, in the left navigation, select **Information governance** > **Labels** > **Create a label**.</span></span> <span data-ttu-id="06c4c-158">탐색 창에 **정보 관리**가 표시되지 않는 경우 아래로 스크롤하여 **모두 표시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-158">If **Information governance** does not display in the navigation pane, scroll down and select **Show all**.</span></span>
  
<span data-ttu-id="06c4c-159">When you create the label, turn on retention, and then choose the option shown below to retain or delete the content based on an event.</span><span class="sxs-lookup"><span data-stu-id="06c4c-159">When you create the label, turn on retention, and then choose the option shown below to retain or delete the content based on an event.</span></span> <span data-ttu-id="06c4c-160">This means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page.</span><span class="sxs-lookup"><span data-stu-id="06c4c-160">This means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page.</span></span> 
  
<span data-ttu-id="06c4c-161">이벤트 구동 보존은 일반적으로 레코드로 분류된 콘텐츠에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-161">Note that event-driven retention is typically used for content that's classified as a record.</span></span> <span data-ttu-id="06c4c-162">이러한 이유로 이벤트 기반의 보존 레이블을 작성할 때 일반적으로 **레이블을 사용하여 콘텐츠를 "레코드"로 분류**하기 위한 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-162">For this reason, when you create retention labels based on an event, you typically choose the option to **Use label to classify content as a "Record"**.</span></span>
  
<span data-ttu-id="06c4c-163">또한 이벤트 구동 보존에는 다음과 같은 보존 설정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-163">Also note that event-driven retention requires retention settings that:</span></span>
  
- <span data-ttu-id="06c4c-164">콘텐츠를 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-164">Retain the content.</span></span>
    
- <span data-ttu-id="06c4c-165">보존 기간이 끝나면 콘텐츠를 자동으로 삭제하거나 처리 검토를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-165">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
    
![이벤트를 기준으로 레이블을 지정하는 옵션](../media/a4902281-5196-4194-9737-f30231d95861.png)
  
### <a name="step-2-choose-an-event-type-for-that-label"></a><span data-ttu-id="06c4c-167">2단계: 해당 레이블에 대한 이벤트 유형 선택</span><span class="sxs-lookup"><span data-stu-id="06c4c-167">Step 2: Choose an event type for that label</span></span>

<span data-ttu-id="06c4c-168">레이블 설정에서 **이벤트** 기반의 레이블을 설정을 위한 옵션을 선택하면 **이벤트 유형 선택** 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-168">In the label settings, after you choose the option to base the label on an **event**, you'll see the option to **Choose an event type**.</span></span> <span data-ttu-id="06c4c-169">이벤트 유형은 레이블을 연결할 이벤트에 대한 일반적인 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-169">An event type is simply a general description of an event that you want to associate a label with.</span></span>
  
<span data-ttu-id="06c4c-170">예를 들어, 제품 수명이라는 이벤트 유형을 만드는 경우 레이블을 적용하려는 콘텐츠의 형식을 설명하는 이름(예: “제품 개발 파일” 또는 “제품 비즈니스 결정 기록”)을 사용하여 이벤트 기반 보존 레이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-170">For example, if you create an event type named Product Lifetime, you'll create event-based retention labels with names that describe what types of content you want the labels to be applied to, such as "Product development files" or "Product business decision records".</span></span>
  
<span data-ttu-id="06c4c-171">일단 이벤트 유형을 선택하고 보존 레이블을 만들고 나면 이벤트 유형을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-171">Note that once you choose an event type and create the retention label, the event type cannot be changed.</span></span>
  
![이벤트 유형을 만들거나 선택하는 옵션](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="06c4c-173">3단계: 이벤트 기반 보존 레이블 게시 혹은 자동 적용</span><span class="sxs-lookup"><span data-stu-id="06c4c-173">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="06c4c-174">다른 보존 레이블과 마찬가지로 이벤트 기반 레이블을 [게시하거나 자동 적용](create-retention-labels.md)해야만 콘텐츠에 수동 또는 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-174">Just like any retention label, you need to [publish or auto-apply](create-retention-labels.md) an event-based label, so that it's manually or automatically applied to content.</span></span>

> [!NOTE]
> <span data-ttu-id="06c4c-175">**레코드 관리** > **파일 계획** 탭 혹은 **데이터 관리** > **레이블** 탭에서 이벤트 중심의 보존 레이블을 선택하는 경우, **레이블 자동 적용** 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-175">If you select an event-driven retention label from **Records Management** > **File plan** tab or **Data governance** > **Labels** tab, the **Auto-apply a label** button is not available.</span></span>
> 
> <span data-ttu-id="06c4c-176">이 단추 대신 다음 위치 중 하나에서 레이블 또는 정책 목록 위에 있는 **레이블 자동 적용** 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-176">Instead of this button, use the **Auto-apply a label** option above the list of labels or policies from one of the following locations:</span></span>
> - <span data-ttu-id="06c4c-177">**레코드 관리** > **레이블 정책** 탭</span><span class="sxs-lookup"><span data-stu-id="06c4c-177">**Records management** > **Label policies** tab</span></span>
> - <span data-ttu-id="06c4c-178">**데이터 관리** > **레이블** 탭 또는 **레이블 정책** 탭</span><span class="sxs-lookup"><span data-stu-id="06c4c-178">**Data governance** > **Labels** tab or **Label policies** tab</span></span>


![보존 레이블 게시 또는 자동 적용 옵션](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="06c4c-180">4단계: 자산 ID 입력</span><span class="sxs-lookup"><span data-stu-id="06c4c-180">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="06c4c-181">After an event-driven label is applied to content, you can enter an asset ID for each item.</span><span class="sxs-lookup"><span data-stu-id="06c4c-181">After an event-driven label is applied to content, you can enter an asset ID for each item.</span></span> <span data-ttu-id="06c4c-182">For example, your organization might use:</span><span class="sxs-lookup"><span data-stu-id="06c4c-182">For example, your organization might use:</span></span>
  
- <span data-ttu-id="06c4c-183">특정 제품에 대한 콘텐츠만 보존하는 데 사용할 수 있는 제품 코드</span><span class="sxs-lookup"><span data-stu-id="06c4c-183">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="06c4c-184">특정 프로젝트에 대한 콘텐츠만 보존하는 데 사용할 수 있는 프로젝트 코드</span><span class="sxs-lookup"><span data-stu-id="06c4c-184">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="06c4c-185">특정 사람에 대한 콘텐츠만 보존하는 데 사용할 수 있는 직원 ID</span><span class="sxs-lookup"><span data-stu-id="06c4c-185">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="06c4c-186">자산 ID는 SharePoint 및 비즈니스용 OneDrive에서는 또 다른 문서 속성일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-186">Understand that Asset ID is simply another document property in SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="06c4c-187">조직에서 이미 다른 문서 속성 및 ID를 사용하여 콘텐츠를 분류하고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-187">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="06c4c-188">이 경우에는 이벤트를 작성할 때 해당 속성 및 값을 사용할 수도 있습니다. 아래 6단계를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06c4c-188">If so, you can also use those properties and values when you create an event - see step 6 that follows.</span></span> <span data-ttu-id="06c4c-189">중요한 점은 조직이 문서 속성에서 일부 특성:값 조합을 사용하여 해당 항목을 이벤트 유형과 연결시켜야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-189">The important point is that your organization must use some property:value combination in the document properties to associate that item with an event type.</span></span>
  
![자산 ID를 입력하기 위한 텍스트 상자](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="06c4c-191">5단계: 이벤트 만들기</span><span class="sxs-lookup"><span data-stu-id="06c4c-191">Step 5: Create an event</span></span>

<span data-ttu-id="06c4c-192">When a particular instance of that event type occurs - for example, a product reaches its end of life - go to the **Records management** > **Events** page in the Microsoft 365 compliance center and create an event.</span><span class="sxs-lookup"><span data-stu-id="06c4c-192">When a particular instance of that event type occurs - for example, a product reaches its end of life - go to the **Records management** > **Events** page in the Microsoft 365 compliance center and create an event.</span></span> <span data-ttu-id="06c4c-193">You need to manually trigger an event by creating it.</span><span class="sxs-lookup"><span data-stu-id="06c4c-193">You need to manually trigger an event by creating it.</span></span>
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="06c4c-194">6단계: 2단계에서 레이블에 사용된 것과 동일한 이벤트 유형 선택</span><span class="sxs-lookup"><span data-stu-id="06c4c-194">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="06c4c-195">이벤트를 작성할 때 2단계에서 보존 레이블에 사용되는 동일한 이벤트 유형(예: 제품 수명)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-195">When you create the event, choose the same event type used by the retention label in step 2 - for example, Product Lifetime.</span></span> <span data-ttu-id="06c4c-196">해당 이벤트 유형에 적용된 보존 레이블이 있는 콘텐츠에 대해서만 보존 기간이 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-196">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>
  
![이벤트 유형을 선택하기 위한 이벤트 설정 옵션](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="06c4c-198">7단계: 키워드 또는 자산 ID 입력</span><span class="sxs-lookup"><span data-stu-id="06c4c-198">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="06c4c-199">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content or keywords for Exchange content.</span><span class="sxs-lookup"><span data-stu-id="06c4c-199">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content or keywords for Exchange content.</span></span> <span data-ttu-id="06c4c-200">For asset IDs, retention will be enforced only on content with the specified property:value pair.</span><span class="sxs-lookup"><span data-stu-id="06c4c-200">For asset IDs, retention will be enforced only on content with the specified property:value pair.</span></span> <span data-ttu-id="06c4c-201">If an asset ID is not entered, **all content** with labels of that event type get the same retention date applied to them.</span><span class="sxs-lookup"><span data-stu-id="06c4c-201">If an asset ID is not entered, **all content** with labels of that event type get the same retention date applied to them.</span></span> 
  
<span data-ttu-id="06c4c-202">자산 ID는 SharePoint 및 비즈니스용 OneDrive에서는 또 다른 문서 속성일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-202">Understand that Asset ID is simply another document property in SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="06c4c-203">자산 ID 속성을 사용하는 경우, 아래 표시된 자산 ID 상자에 ComplianceAssetID:\<value\>를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-203">If you're using the Asset ID property, you would enter ComplianceAssetID:\<value\> in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="06c4c-204">Your organization might have applied other properties and IDs to the documents related to this event type.</span><span class="sxs-lookup"><span data-stu-id="06c4c-204">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="06c4c-205">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span><span class="sxs-lookup"><span data-stu-id="06c4c-205">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="06c4c-206">In this case, you'd enter ProductID:XYZ in the box for asset IDs shown below.</span><span class="sxs-lookup"><span data-stu-id="06c4c-206">In this case, you'd enter ProductID:XYZ in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="06c4c-207">For Exchange items, you can include keywords.</span><span class="sxs-lookup"><span data-stu-id="06c4c-207">For Exchange items, you can include keywords.</span></span> <span data-ttu-id="06c4c-208">You can refine your query by using search operators like AND, OR, and NOT.</span><span class="sxs-lookup"><span data-stu-id="06c4c-208">You can refine your query by using search operators like AND, OR, and NOT.</span></span> <span data-ttu-id="06c4c-209">For more information on operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="06c4c-209">For more information on operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="06c4c-210">마지막으로 이벤트가 발생한 날짜를 선택합니다. 이 날짜는 보존 기간의 시작 날짜로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-210">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="06c4c-211">이벤트를 작성한 후, 이벤트 날짜는 해당 이벤트 유형, 자산 ID 및 키워드의 보존 레이블이 있는 모든 콘텐츠와 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-211">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords.</span></span> <span data-ttu-id="06c4c-212">모든 보존 레이블과 마찬가지로 이 동기화는 7일 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-212">Like any retention label, this synchronization can take up to 7 days.</span></span>
  
![이벤트 설정 페이지](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)
  
## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="06c4c-214">콘텐츠 검색을 사용하여 특정 레이블 또는 자산 ID를 포함하는 모든 콘텐츠 찾기</span><span class="sxs-lookup"><span data-stu-id="06c4c-214">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="06c4c-215">콘텐츠에 보존 레이블이 할당된 후에 콘텐츠 검색을 사용하여 특정 보존 레이블로 분류되거나 특정 자산 ID를 포함하는 모든 콘텐츠를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-215">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID.</span></span>
  
<span data-ttu-id="06c4c-216">콘텐츠 검색을 만들 경우 다음이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-216">When you create a content search:</span></span>
  
- <span data-ttu-id="06c4c-217">특정 보존 레이블이 있는 모든 콘텐츠를 찾으려면 **준수 태그** 조건을 선택하고 전체 레이블 이름 또는 레이블 이름 일부를 입력하고 와일드카드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-217">To find all content with a specific retention label, choose the **Compliance Tag** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="06c4c-218">특정 자산 ID가 있는 모든 콘텐츠를 찾으려면 **ComplianceAssetID** 속성과 값(예: ComplianceAssetID:\<value\>)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-218">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, like ComplianceAssetID:\<value\>.</span></span> 
    
<span data-ttu-id="06c4c-219">자세한 내용은 [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06c4c-219">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="permissions"></a><span data-ttu-id="06c4c-220">사용 권한</span><span class="sxs-lookup"><span data-stu-id="06c4c-220">Permissions</span></span>

<span data-ttu-id="06c4c-221">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role.</span><span class="sxs-lookup"><span data-stu-id="06c4c-221">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role.</span></span> <span data-ttu-id="06c4c-222">We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span><span class="sxs-lookup"><span data-stu-id="06c4c-222">We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="06c4c-223">자세한 내용은 [사용자에게 Office 365 보안 및 준수 센터에 대한 액세스 권한 부여](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06c4c-223">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="06c4c-224">PowerShell을 사용하여 이벤트 자동화</span><span class="sxs-lookup"><span data-stu-id="06c4c-224">Automate events by using PowerShell</span></span>

<span data-ttu-id="06c4c-225">In the admin center, you can only create events manually; it's not possible to automatically trigger an event when it occurs.</span><span class="sxs-lookup"><span data-stu-id="06c4c-225">In the admin center, you can only create events manually; it's not possible to automatically trigger an event when it occurs.</span></span> <span data-ttu-id="06c4c-226">However, you can use a Rest API to trigger events automatically; for more information, see [Automate event-based retention](automate-event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="06c4c-226">However, you can use a Rest API to trigger events automatically; for more information, see [Automate event-based retention](automate-event-driven-retention.md).</span></span>

<span data-ttu-id="06c4c-227">PowerShell 스크립트를 사용하여 비즈니스 응용 프로그램에서 이벤트 기반 보존을 자동화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-227">You can also use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="06c4c-228">이벤트 구동 보존에 다음 PowerShell cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c4c-228">The PowerShell cmdlets available for event-driven retention:</span></span>
  
- [<span data-ttu-id="06c4c-229">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="06c4c-229">Get-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [<span data-ttu-id="06c4c-230">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="06c4c-230">New-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [<span data-ttu-id="06c4c-231">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="06c4c-231">Remove-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [<span data-ttu-id="06c4c-232">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="06c4c-232">Set-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [<span data-ttu-id="06c4c-233">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="06c4c-233">Get-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [<span data-ttu-id="06c4c-234">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="06c4c-234">New-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873003)
    

