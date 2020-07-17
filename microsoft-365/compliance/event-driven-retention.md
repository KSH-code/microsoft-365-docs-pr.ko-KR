---
title: 이벤트가 발생할 때 보존 시작
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
ms.openlocfilehash: 15330c5be34d0cd482b83b4aab5f229cecf2a447
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126861"
---
# <a name="start-retention-when-an-event-occurs"></a><span data-ttu-id="f8cf9-103">이벤트가 발생할 때 보존 시작</span><span class="sxs-lookup"><span data-stu-id="f8cf9-103">Start retention when an event occurs</span></span>

><span data-ttu-id="f8cf9-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*</span><span class="sxs-lookup"><span data-stu-id="f8cf9-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="f8cf9-p101">콘텐츠를 보존할 때 보존 기간은 대개 콘텐츠의 사용 기간을 기준으로 합니다. 예를 들어, 문서를 만들고 7년 동안 보존한 후 삭제할 수 있습니다. 그렇지만 [보존 레이블](labels.md)을 구성할 때 특정 유형의 이벤트가 발생하는 경우를 기준으로 보존 기간을 지정할 수도 있습니다. 이벤트는 보존 기간의 시작을 트리거하며, 해당 유형의 이벤트에 적용된 보존 레이블이 있는 모든 콘텐츠에 대해 레이블 보존 작업이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-p101">When you retain content, the retention period is often based on the age of the content. For example, you might retain documents for seven years after they're created and then delete them. But when you configure [retention labels](labels.md), you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="f8cf9-109">이벤트 구동 보존 사용 예제:</span><span class="sxs-lookup"><span data-stu-id="f8cf9-109">Examples for using event-driven retention:</span></span>
  
- <span data-ttu-id="f8cf9-110">**직원 퇴사** 직원이 조직을 떠나는 시점부터 10년 동안 직원 레코드를 보유해야 한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-110">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="f8cf9-111">10년이 지난 후에는 해당 직원의 고용, 성과 및 퇴직에 관련된 모든 문서를 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-111">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee must be disposed.</span></span> <span data-ttu-id="f8cf9-112">10년의 보존 기간을 트리거하는 이벤트는 직원 퇴사입니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-112">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="f8cf9-113">**계약 만료** 예를 들어, 계약과 관련된 모든 레코드를 계약이 만료되는 시간으로부터 5년 동안 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-113">**Contract expiration** Suppose that all records related to contracts must be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="f8cf9-114">5년 보존 기간을 트리거하는 이벤트는 계약 만료입니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-114">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="f8cf9-p104">**제품 수명** 조직은 기술 사양과 같은 콘텐츠에 대해 제품의 마지막 제조일과 관련된 보존 요구 사항을 유지할 수 있습니다. 이 경우 마지막 제조일이 보존 기간을 트리거하는 이벤트가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-p104">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="f8cf9-p105">이벤트 구동 보존은 일반적으로 기록 관리 프로세스의 일부로 사용됩니다. 이것은 다음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-p105">Event-driven retention is typically used as part of a records-management process. This means that:</span></span>
  
- <span data-ttu-id="f8cf9-119">이벤트 기반의 레이블은 대개 콘텐츠를 레코드로 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-119">Labels based on events also usually classify content as a record.</span></span> <span data-ttu-id="f8cf9-120">자세한 내용은 [레코드에 대해 자세히 알아보기](records.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-120">For more information, see [Learn about records](records.md).</span></span>

- <span data-ttu-id="f8cf9-121">레코드로 분류되었으나 해당 이벤트 트리거가 아직 발생하지 않은 문서는 문서의 보존 기간을 트리거하는 이벤트가 발생할 때까지 무기한 보존됩니다(기록을 영구히 삭제할 수 없음).</span><span class="sxs-lookup"><span data-stu-id="f8cf9-121">A document that's been classified as a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="f8cf9-122">이벤트 기반의 보존 레이블은 일반적으로 보존 기간이 끝나면 처리 검토를 트리거하므로 레코드 관리자는 콘텐츠를 수동으로 검토 및 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-122">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose of the content.</span></span> <span data-ttu-id="f8cf9-123">자세한 내용은 [콘텐츠 처리](disposition.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-123">For more information, see [Disposition of content](disposition.md).</span></span>
    

<span data-ttu-id="f8cf9-124">이벤트 기반의 레이블은 Office 365의 모든 보존 레이블과 같은 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-124">A label based on an event has the same capabilities as any retention label in Microsoft  365.</span></span> <span data-ttu-id="f8cf9-125">자세한 내용은 [보존 정책 및 보존 레이블에 대해 알아보기](retention.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-125">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="f8cf9-126">이벤트 유형, 레이블, 이벤트 및 자산 ID 간 관계 이해</span><span class="sxs-lookup"><span data-stu-id="f8cf9-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="f8cf9-127">이벤트 구동 보존을 성공적으로 사용하려면 다음과 같은 다이어그램 및 설명에 있는 것처럼 이벤트 유형, 보존 레이블, 이벤트 및 자산 ID 간 관계를 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-127">To successfully use event-driven retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![이벤트 유형, 레이블, 이벤트 및 자산 ID의 다이어그램](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![이벤트 유형, 레이블, 이벤트 및 자산 ID의 다이어그램](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="f8cf9-130">콘텐츠 유형에 따라 보존 레이블을 작성한 후 이벤트 유형과 연관시킵니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-130">You create retention labels for different types of content and then associate them with a type of event.</span></span> <span data-ttu-id="f8cf9-131">예를 들어, 다양 한 유형의 제품 파일 및 기록에 대한 레이블은 해당 기록을 제품이 수명에 도달한 시점부터 10년 동안 보존해야 하므로 제품 수명이라는 이벤트 유형에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-131">For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="f8cf9-132">사용자(일반적으로 레코드 관리자)는 해당 보존 레이블을 콘텐츠에 적용하고, SharePoint 및 OneDrive 문서의 경우에는 각 항목에 대해 자산 ID를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-132">Users (typically records managers) apply those retention labels to content and (for SharePoint and OneDrive documents) enter an asset ID for each item.</span></span> <span data-ttu-id="f8cf9-133">이 예에서 자산 ID는 조직에서 사용하는 제품 이름 또는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-133">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="f8cf9-134">따라서 각 제품의 레코드에는 보존 레이블이 할당되고 각 레코드는 자산 ID가 포함된 특성을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-134">Thus, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="f8cf9-135">다이어그램은 조직의 모든 제품 레코드에 대한 **모든 콘텐츠**를 표시하며 각 항목은 레코드가 있는 제품의 자산 ID를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-135">The diagram represents **all of the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="f8cf9-p111">제품 수명은 이벤트 유형입니다. 특정 제품이 제품 수명에 도달하는 것이 이벤트입니다. 해당 이벤트 유형의 이벤트가 발생할 때(이 경우 제품이 수명 종료에 도달) 다음을 지정하는 이벤트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-p111">Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:</span></span>
    
  - <span data-ttu-id="f8cf9-138">자산 ID(SharePoint 및 OneDrive 문서 관련)</span><span class="sxs-lookup"><span data-stu-id="f8cf9-138">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
  - <span data-ttu-id="f8cf9-p112">키워드(Exchange 항목 관련). 이 예제에서 조직은 Exchange 항목에 대한 키워드가 SharePoint 및 OneDrive 문서에 대한 자산 ID와 동일하도록 제품 레코드를 포함하는 메시지에 제품 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-p112">Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
  - <span data-ttu-id="f8cf9-p113">이벤트가 발생한 날짜. 이 날짜는 보존 기간의 시작 날짜로 사용됩니다. 이 날짜는 현재, 과거 또는 미래의 날짜가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-p113">The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.</span></span>
    
4. <span data-ttu-id="f8cf9-144">이벤트를 작성한 후, 해당 이벤트 날짜는 해당 이벤트 유형의 보존 레이블이 있으며 지정된 자산 ID 또는 키워드를 포함하는 모든 콘텐츠와 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-144">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="f8cf9-145">모든 보존 레이블과 마찬가지로 이 동기화는 7일 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-145">Like any retention label, this synchronization can take up to 7 days.</span></span> <span data-ttu-id="f8cf9-146">이전 다이어그램에서 빨간색 원으로 둘러싸인 모든 항목에는 이 이벤트를 통해 트리거되는 보존 기간이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-146">In the previous diagram, all the items circled in red have their retention period triggered by this event.</span></span> <span data-ttu-id="f8cf9-147">즉, 이 제품이 수명의 끝에 도달하면 해당 이벤트는 해당 제품의 레코드에 대한 보존 기간을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-147">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>
    
<span data-ttu-id="f8cf9-148">이벤트에 대해 자산 ID 또는 키워드를 지정하지 않으면 해당 이벤트 유형의 레이블이 있는 **모든 콘텐츠**가 이벤트에 의해 트리거된 보존 기간을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-148">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="f8cf9-149">이는 위의 다이어그램에서 모든 콘텐츠가 유지되기 시작한다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-149">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="f8cf9-150">이는 원치 않는 일일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-150">This might not be what you intend.</span></span> 
  
<span data-ttu-id="f8cf9-151">마지막으로 각 보존 레이블에는 별도의 보존 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-151">Finally, remember that each retention label has its own retention settings.</span></span> <span data-ttu-id="f8cf9-152">이 예에서는 모든 레이블이 10년을 지정하지만 각 레이블의 보존 기간이 다른 경우 이벤트가 보존 레이블을 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-152">In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="f8cf9-153">이벤트 구동 보존 설정 방법</span><span class="sxs-lookup"><span data-stu-id="f8cf9-153">How to set up event-driven retention</span></span>

<span data-ttu-id="f8cf9-154">이벤트 구동 보존의 상위 레벨 워구동우우:</span><span class="sxs-lookup"><span data-stu-id="f8cf9-154">High-level workflow for event-driven retention:</span></span>
  
![이벤트 구동 보존을 설정하는 워크플로 다이어그램](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="f8cf9-156">SharePont에서 관리 속성을 사용하여 보존 레이블을 자동 적용하고 이벤트 중심 보존을 구현하는 방법에 대한 자세한 시나리오는 [보존 레이블로 SharePoint 문서의 수명 주기 관리](auto-apply-retention-labels-scenario.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-156">See [Manage the lifecycle of SharePoint documents with retention labels](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="f8cf9-157">1단계: 보존 기간이 이벤트에 따라 조정되는 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="f8cf9-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="f8cf9-158">보존 레이블을 만들고 구성하려면 [보존 레이블 만들기 및 구성하기](create-retention-labels.md#create-and-configure-retention-labels)의 지침을 사용하고, 보존을 켤 때 이벤트를 기준으로 콘텐츠를 보존하거나 삭제하는 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-158">To create and configure your retention label, use the instructions from [Create and configure retention labels](create-retention-labels.md#create-and-configure-retention-labels) and when you turn on retention, choose the option to retain or delete the content based on an event.</span></span> <span data-ttu-id="f8cf9-159">이 설정은 **이벤트** 페이지에서 이벤트를 작성할 때 5단계까지 보존 설정이 적용되지 않음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-159">This setting means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page.</span></span> 
  
<span data-ttu-id="f8cf9-160">이벤트 구동 보존은 보통 레코드로 분류되는 콘텐츠에 사용되므로 콘텐츠를 레코드로 표시하는 옵션도 선택해야 하는지 확인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-160">Event-driven retention is typically used for content that's classified as a record, so this is a good time to check whether you also need to select the option that marks content as a record.</span></span>
  
<span data-ttu-id="f8cf9-161">이벤트 구동 보존에는 다음과 같은 보존 설정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-161">Event-driven retention requires retention settings that:</span></span>
  
- <span data-ttu-id="f8cf9-162">콘텐츠를 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-162">Retain the content.</span></span>
    
- <span data-ttu-id="f8cf9-163">보존 기간이 끝나면 콘텐츠를 자동으로 삭제하거나 처리 검토를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-163">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
    
![이벤트를 기준으로 레이블을 지정하는 옵션](../media/a4902281-5196-4194-9737-f30231d95861.png)

### <a name="step-2-choose-an-event-type-for-that-label"></a><span data-ttu-id="f8cf9-165">2단계: 해당 레이블에 대한 이벤트 유형 선택</span><span class="sxs-lookup"><span data-stu-id="f8cf9-165">Step 2: Choose an event type for that label</span></span>

<span data-ttu-id="f8cf9-166">레이블 설정에서 **이벤트** 기반의 레이블을 설정을 위한 옵션을 선택하면 **이벤트 유형 선택** 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-166">In the label settings, after you choose the option to base the label on an **event**, you'll see the option to **Choose an event type**.</span></span> <span data-ttu-id="f8cf9-167">이벤트 유형은 레이블을 연결할 이벤트에 대한 일반적인 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-167">An event type is simply a general description of an event that you want to associate a label with.</span></span>
  
<span data-ttu-id="f8cf9-168">예를 들어, 제품 수명이라는 이벤트 유형을 만드는 경우 레이블을 적용하려는 콘텐츠의 형식을 설명하는 이름(예: “제품 개발 파일” 또는 “제품 비즈니스 결정 기록”)을 사용하여 이벤트 기반 보존 레이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-168">For example, if you create an event type named Product Lifetime, you'll create event-based retention labels with names that describe what types of content you want the labels to be applied to, such as "Product development files" or "Product business decision records".</span></span>

<span data-ttu-id="f8cf9-169">기본 제공된 이벤트 유형 중 하나를 선택하거나 직접 이벤트 유형을 만들고 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-169">Select one of the built-in event types, or create your own and then select it.</span></span>

<span data-ttu-id="f8cf9-170">이벤트 유형을 선택하고 보존 레이블을 저장한 후에는 이벤트 유형을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-170">After you choose an event type and save the retention label, the event type cannot be changed.</span></span>
  
![이벤트 유형을 만들거나 선택하는 옵션](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="f8cf9-172">3단계: 이벤트 기반 보존 레이블 게시 혹은 자동 적용</span><span class="sxs-lookup"><span data-stu-id="f8cf9-172">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="f8cf9-173">다른 보존 레이블과 마찬가지로 이벤트 기반 레이블을 게시하거나 자동 적용해야만 콘텐츠에 수동 또는 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-173">Just like any retention label, you need to publish or auto-apply an event-based label, for it to be manually or automatically applied to content:</span></span>
- [<span data-ttu-id="f8cf9-174">보존 레이블을 만들고 앱에 적용하기</span><span class="sxs-lookup"><span data-stu-id="f8cf9-174">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="f8cf9-175">보존 레이블을 콘텐츠에 자동으로 적용하기</span><span class="sxs-lookup"><span data-stu-id="f8cf9-175">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)


> [!NOTE]
> <span data-ttu-id="f8cf9-176">**레코드 관리** > **파일 계획** 탭 또는 **데이터 관리** > **레이블** 탭에서 이벤트 기반 보존 레이블을 선택하는 경우 **레이블 자동 적용** 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-176">If you select an event-based retention label from **Records Management** > **File plan** tab or **Data governance** > **Labels** tab, the **Auto-apply a label** button is not available.</span></span>
> 
> <span data-ttu-id="f8cf9-177">이 단추 대신 다음 위치 중 하나에서 레이블 또는 정책 목록 위에 있는 **레이블 자동 적용** 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-177">Instead of this button, use the **Auto-apply a label** option above the list of labels or policies from one of the following locations:</span></span>
> - <span data-ttu-id="f8cf9-178">**레코드 관리** > **레이블 정책** 탭</span><span class="sxs-lookup"><span data-stu-id="f8cf9-178">**Records management** > **Label policies** tab</span></span>
> - <span data-ttu-id="f8cf9-179">**데이터 관리** > **레이블** 탭 또는 **레이블 정책** 탭</span><span class="sxs-lookup"><span data-stu-id="f8cf9-179">**Data governance** > **Labels** tab or **Label policies** tab</span></span>


![보존 레이블 게시 또는 자동 적용 옵션](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="f8cf9-181">4단계: 자산 ID 입력</span><span class="sxs-lookup"><span data-stu-id="f8cf9-181">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="f8cf9-182">이벤트 기반 레이블이 콘텐츠에 적용된 후 각 항목의 자산 ID를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-182">After an event-based label is applied to content, you can enter an asset ID for each item.</span></span> <span data-ttu-id="f8cf9-183">예를 들어 사용자의 조직은 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-183">For example, your organization might use:</span></span>
  
- <span data-ttu-id="f8cf9-184">특정 제품에 대한 콘텐츠만 보존하는 데 사용할 수 있는 제품 코드</span><span class="sxs-lookup"><span data-stu-id="f8cf9-184">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="f8cf9-185">특정 프로젝트에 대한 콘텐츠만 보존하는 데 사용할 수 있는 프로젝트 코드</span><span class="sxs-lookup"><span data-stu-id="f8cf9-185">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="f8cf9-186">특정 사람에 대한 콘텐츠만 보존하는 데 사용할 수 있는 직원 ID</span><span class="sxs-lookup"><span data-stu-id="f8cf9-186">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="f8cf9-187">자산 ID는 SharePoint 및 OneDrive에서 사용할 수 있는 또 다른 문서 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-187">Asset ID is simply another document property that's available in SharePoint and OneDrive.</span></span> <span data-ttu-id="f8cf9-188">조직에서 이미 다른 문서 속성 및 ID를 사용하여 콘텐츠를 분류하고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-188">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="f8cf9-189">이 경우에는 이벤트를 작성할 때 해당 속성 및 값을 사용할 수도 있습니다. 아래 6단계를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-189">If so, you can also use those properties and values when you create an event - see step 6 that follows.</span></span> <span data-ttu-id="f8cf9-190">중요한 점은 사용자가 문서 속성에서 일부 *속성:값* 조합을 사용하여 해당 항목을 이벤트 유형과 연결시켜야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-190">The important point is that you must use some *property:value* combination in the document properties to associate that item with an event type.</span></span>
  
![자산 ID를 입력하기 위한 텍스트 상자](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="f8cf9-192">5단계: 이벤트 만들기</span><span class="sxs-lookup"><span data-stu-id="f8cf9-192">Step 5: Create an event</span></span>

<span data-ttu-id="f8cf9-193">해당 이벤트 유형의 특정 인스턴스가 발생하면(예: 제품이 수명 종료에 도달) Microsoft 365 규정 준수 센터의 **레코드 관리** > **이벤트** 페이지로 가서 이벤트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-193">When a particular instance of that event type occurs, such as a product reaches its end of life, go to the **Records management** > **Events** page in the Microsoft 365 compliance center and create an event.</span></span> <span data-ttu-id="f8cf9-194">이벤트를 만들어 트리거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-194">You trigger an event by creating it.</span></span>
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="f8cf9-195">6단계: 2단계에서 레이블에 사용된 것과 동일한 이벤트 유형 선택</span><span class="sxs-lookup"><span data-stu-id="f8cf9-195">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="f8cf9-196">이벤트를 작성할 때 2단계에서 보존 레이블에 사용되는 동일한 이벤트 유형(예: 제품 수명)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-196">When you create the event, choose the same event type used by the retention label in step 2 - for example, Product Lifetime.</span></span> <span data-ttu-id="f8cf9-197">해당 이벤트 유형에 적용된 보존 레이블이 있는 콘텐츠에 대해서만 보존 기간이 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-197">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>
  
![이벤트 유형을 선택하기 위한 이벤트 설정 옵션](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="f8cf9-199">7단계: 키워드 또는 자산 ID 입력</span><span class="sxs-lookup"><span data-stu-id="f8cf9-199">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="f8cf9-200">이제 SharePoint 및 OneDrive 콘텐츠의 자산 ID 또는 Exchange 콘텐츠의 키워드를 지정하여 콘텐츠 범위를 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-200">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content, or keywords for Exchange content.</span></span> <span data-ttu-id="f8cf9-201">자산 ID의 경우 지정된 *속성:값* 쌍을 가진 콘텐츠에 대해서만 보존이 강제 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-201">For asset IDs, retention will be enforced only on content with the specified *property:value* pair.</span></span> <span data-ttu-id="f8cf9-202">자산 ID가 입력되지 않은 경우 해당 이벤트 유형의 레이블을 가진 모든 콘텐츠는 동일한 보존 날짜가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-202">If an asset ID is not entered, all content with labels of that event type get the same retention date applied to them.</span></span>

<span data-ttu-id="f8cf9-203">예를 들어 자산 ID 속성을 사용하는 경우 아래 표시된 자산 ID 상자에 `ComplianceAssetID:<value>`을(를) 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-203">For example: If you're using the Asset ID property, enter `ComplianceAssetID:<value>` in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="f8cf9-204">조직에서 이 이벤트 유형과 관련된 문서에 다른 속성 및 ID를 적용했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-204">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="f8cf9-205">예를 들어, 특정 제품의 레코드를 발견해야 하는 경우 ID는 사용자 지정 속성 ProductID와 "XYZ" 값의 조합일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-205">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="f8cf9-206">이 경우 아래 그림에 표시된 자산 ID 상자에 `ProductID:XYZ`을(를) 입력했습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-206">In this case, you'd enter `ProductID:XYZ` in the box for asset IDs shown in the following picture.</span></span>
  
<span data-ttu-id="f8cf9-207">Exchange 항목의 경우 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-207">For Exchange items, use keywords.</span></span> <span data-ttu-id="f8cf9-208">검색 연산자(예: AND, OR 및 NOT)를 사용하여 쿼리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-208">You can use a query by using search operators such as AND, OR, and NOT.</span></span> <span data-ttu-id="f8cf9-209">자세한 내용은 [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-209">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="f8cf9-210">마지막으로 이벤트가 발생한 날짜를 선택합니다. 이 날짜는 보존 기간의 시작 날짜로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-210">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="f8cf9-211">이벤트를 작성한 후, 이벤트 날짜는 해당 이벤트 유형, 자산 ID 및 키워드의 보존 레이블이 있는 모든 콘텐츠와 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-211">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords.</span></span> <span data-ttu-id="f8cf9-212">모든 보존 레이블과 마찬가지로 이 동기화는 최대 7일 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-212">As with any retention label, this synchronization can take up to seven days.</span></span>
  
![이벤트 설정 페이지](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

<span data-ttu-id="f8cf9-214">이벤트를 만든 후 보존 설정은 이미 레이블이 지정되고 인덱싱된 콘텐츠에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-214">After creating an event, the retention settings take effect for the content that's already labeled and indexed.</span></span> <span data-ttu-id="f8cf9-215">이벤트를 만든 후 새 콘텐츠에 보존 레이블을 추가한 경우에는 동일한 세부 정보를 사용하여 새 이벤트를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-215">If the retention label is added to new content after the event is created, you must create a new event with the same details.</span></span>

<span data-ttu-id="f8cf9-216">이벤트를 삭제해도 이미 레이블이 지정된 콘텐츠에 적용되는 보존 설정은 취소되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-216">Deleting an event doesn't cancel the retention settings that are now in effect for the content that's already labeled.</span></span> <span data-ttu-id="f8cf9-217">보존 설정을 취소하려면 동일한 세부 정보를 사용하여 새 이벤트를 만들되 날짜를 비워 두세요.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-217">To do that, create a new event with the same details, but leave the date blank.</span></span> 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="f8cf9-218">콘텐츠 검색을 사용하여 특정 레이블 또는 자산 ID를 포함하는 모든 콘텐츠 찾기</span><span class="sxs-lookup"><span data-stu-id="f8cf9-218">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="f8cf9-219">콘텐츠에 보존 레이블이 할당된 후에 콘텐츠 검색을 사용하여 특정 보존 레이블로 분류되거나 특정 자산 ID를 포함하는 모든 콘텐츠를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-219">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID:</span></span>
  
- <span data-ttu-id="f8cf9-220">특정 보존 레이블이 있는 모든 콘텐츠를 찾으려면 **준수 레이블** 조건을 선택하고 전체 레이블 이름 또는 레이블 이름 일부를 입력하고 와일드카드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-220">To find all content with a specific retention label, choose the **Compliance label** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="f8cf9-221">특정 자산 ID가 있는 모든 콘텐츠를 찾으려면 **ComplianceAssetID** 속성과 값(예: `ComplianceAssetID:<value>`)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-221">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, using the format `ComplianceAssetID:<value>`.</span></span> 
    
<span data-ttu-id="f8cf9-222">자세한 내용은 [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-222">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="permissions"></a><span data-ttu-id="f8cf9-223">사용 권한</span><span class="sxs-lookup"><span data-stu-id="f8cf9-223">Permissions</span></span>

<span data-ttu-id="f8cf9-p129">**이벤트** 페이지에 액세스하기 위해 검토자는 **처리 관리** 역할 및 **보기 전용 감사 로그** 역할이 있는 역할 그룹의 구성원이어야 합니다. 처리 검토자라는 새 역할 그룹을 만들고, 이러한 두 역할을 해당 역할 그룹에 추가한 후 역할 그룹에 구성원을 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-p129">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="f8cf9-226">자세한 내용은 [사용자에게 Office 365 보안 및 준수 센터에 대한 액세스 권한 부여](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-226">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="f8cf9-227">PowerShell을 사용하여 이벤트 자동화</span><span class="sxs-lookup"><span data-stu-id="f8cf9-227">Automate events by using PowerShell</span></span>

<span data-ttu-id="f8cf9-228">Microsoft 365 규정 준수 센터에서는 이벤트를 수동으로 만들 수 있으며, 이벤트가 발생할 때 이벤트를 자동으로 트리거하는 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-228">The Microsoft 365 compliance center lets you create events manually and doesn't support automatically triggering an event when it occurs.</span></span> <span data-ttu-id="f8cf9-229">그러나 Rest API를 사용하여 이벤트를 자동으로 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-229">However, you can use a Rest API to trigger events automatically.</span></span> <span data-ttu-id="f8cf9-230">자세한 내용은 [이벤트 기반 보존 자동화하기](automate-event-driven-retention.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-230">For more information, see [Automate event-based retention](automate-event-driven-retention.md).</span></span>

<span data-ttu-id="f8cf9-231">PowerShell 스크립트를 사용하여 비즈니스 응용 프로그램에서 이벤트 기반 보존을 자동화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-231">You can also use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="f8cf9-232">이벤트 기반 보존에 다음 PowerShell cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8cf9-232">The PowerShell cmdlets available for event-based retention:</span></span>
  
- [<span data-ttu-id="f8cf9-233">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="f8cf9-233">Get-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [<span data-ttu-id="f8cf9-234">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="f8cf9-234">New-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [<span data-ttu-id="f8cf9-235">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="f8cf9-235">Remove-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [<span data-ttu-id="f8cf9-236">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="f8cf9-236">Set-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [<span data-ttu-id="f8cf9-237">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="f8cf9-237">Get-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [<span data-ttu-id="f8cf9-238">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="f8cf9-238">New-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873003)
    

