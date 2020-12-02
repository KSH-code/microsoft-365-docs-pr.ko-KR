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
ms.openlocfilehash: cf8ce1dc2ca77e2ba028d0c35f58cd0ab419b32d
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477627"
---
# <a name="start-retention-when-an-event-occurs"></a><span data-ttu-id="ea244-103">이벤트가 발생할 때 보존 시작</span><span class="sxs-lookup"><span data-stu-id="ea244-103">Start retention when an event occurs</span></span>

><span data-ttu-id="ea244-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*</span><span class="sxs-lookup"><span data-stu-id="ea244-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="ea244-p101">콘텐츠를 보존할 때 보존 기간은 대개 콘텐츠의 사용 기간을 기준으로 합니다. 예를 들어, 문서를 만들고 7년 동안 보존한 후 삭제할 수 있습니다. 그렇지만 [보존 레이블](retention.md#retention-labels)을 구성할 때 특정 유형의 이벤트가 발생하는 경우를 기준으로 보존 기간을 지정할 수도 있습니다. 이벤트는 보존 기간의 시작을 트리거하며, 해당 유형의 이벤트에 적용된 보존 레이블이 있는 모든 콘텐츠에 대해 레이블 보존 작업이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-p101">When you retain content, the retention period is often based on the age of the content. For example, you might retain documents for seven years after they're created and then delete them. But when you configure [retention labels](retention.md#retention-labels), you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="ea244-109">이벤트 기반 보존 사용 예제:</span><span class="sxs-lookup"><span data-stu-id="ea244-109">Examples for using event-based retention:</span></span>
  
- <span data-ttu-id="ea244-110">**직원 퇴사** 직원이 조직을 떠나는 시점부터 10년 동안 직원 레코드를 보유해야 한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-110">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="ea244-111">10년이 지난 후에는 해당 직원의 고용, 성과 및 퇴직에 관련된 모든 문서를 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-111">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee must be disposed.</span></span> <span data-ttu-id="ea244-112">10년의 보존 기간을 트리거하는 이벤트는 직원 퇴사입니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-112">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="ea244-113">**계약 만료** 예를 들어, 계약과 관련된 모든 레코드를 계약이 만료되는 시간으로부터 5년 동안 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-113">**Contract expiration** Suppose that all records related to contracts must be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="ea244-114">5년 보존 기간을 트리거하는 이벤트는 계약 만료입니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-114">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="ea244-p104">**제품 수명** 조직은 기술 사양과 같은 콘텐츠에 대해 제품의 마지막 제조일과 관련된 보존 요구 사항을 유지할 수 있습니다. 이 경우 마지막 제조일이 보존 기간을 트리거하는 이벤트가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-p104">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="ea244-p105">이벤트 기반 보존은 일반적으로 기록 관리 프로세스의 일부로 사용됩니다. 이것은 다음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-p105">Event-based retention is typically used as part of a records-management process. This means that:</span></span>
  
- <span data-ttu-id="ea244-119">이벤트 기반의 보존 레이블 또한 일반적으로 레코드 관리 솔루션의 일환으로 항목을 레코드로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-119">Retention labels based on events also usually mark items as a record, as a part of a records management solution.</span></span> <span data-ttu-id="ea244-120">자세한 내용은 [레코드 관리에 대한 자세한 정보](records-management.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea244-120">For more information, see [Learn about records management](records-management.md).</span></span>

- <span data-ttu-id="ea244-121">레코드로 선언되었으나 해당 이벤트 트리거가 아직 발생하지 않은 문서는 문서의 보존 기간을 트리거하는 이벤트가 발생할 때까지 무기한 보존됩니다(레코드를 영구히 삭제할 수 없음).</span><span class="sxs-lookup"><span data-stu-id="ea244-121">A document that's been declared a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="ea244-122">이벤트 기반의 보존 레이블은 일반적으로 보존 기간이 끝나면 처리 검토를 트리거하므로 레코드 관리자는 콘텐츠를 수동으로 검토 및 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-122">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose of the content.</span></span> <span data-ttu-id="ea244-123">자세한 내용은 [콘텐츠 처리](disposition.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea244-123">For more information, see [Disposition of content](disposition.md).</span></span>
    

<span data-ttu-id="ea244-124">이벤트 기반의 보존 레이블은 Microsoft 365의 모든 보존 레이블과 같은 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-124">A retention label based on an event has the same capabilities as any retention label in Microsoft 365.</span></span> <span data-ttu-id="ea244-125">자세한 내용은 [보존 정책 및 보존 레이블에 대해 알아보기](retention.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea244-125">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="ea244-126">이벤트 유형, 레이블, 이벤트 및 자산 ID 간 관계 이해</span><span class="sxs-lookup"><span data-stu-id="ea244-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="ea244-127">이벤트 기반 보존을 성공적으로 사용하려면 다음과 같은 다이어그램 및 설명에 있는 것처럼 이벤트 유형, 보존 레이블, 이벤트 및 자산 ID 간 관계를 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-127">To successfully use event-based retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![다이어그램 1/2: 이벤트 유형, 레이블, 이벤트 및 자산 ID ](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![다이어그램 2/2: 이벤트 유형, 레이블, 이벤트 및 자산 ID ](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="ea244-130">콘텐츠 유형에 따라 보존 레이블을 작성한 후 이벤트 유형과 연관시킵니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-130">You create retention labels for different types of content and then associate them with a type of event.</span></span> <span data-ttu-id="ea244-131">예를 들어, 다양 한 유형의 제품 파일 및 기록에 대한 레이블은 해당 기록을 제품이 수명에 도달한 시점부터 10년 동안 보존해야 하므로 제품 수명이라는 이벤트 유형에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-131">For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="ea244-132">사용자(일반적으로 레코드 관리자)는 해당 보존 레이블을 콘텐츠에 적용하고, (SharePoint 및 OneDrive 문서의 경우에는) 각 항목에 대해 자산 ID를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-132">Users (typically records managers) apply those retention labels to content and (for documents in SharePoint and OneDrive) enter an asset ID for each item.</span></span> <span data-ttu-id="ea244-133">이 예에서 자산 ID는 조직에서 사용하는 제품 이름 또는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-133">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="ea244-134">따라서 각 제품의 레코드에는 보존 레이블이 할당되고 각 레코드는 자산 ID가 포함된 특성을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-134">Then, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="ea244-135">다이어그램은 조직의 모든 제품 레코드에 대한 **모든 콘텐츠** 를 표시하며 각 항목은 레코드가 있는 제품의 자산 ID를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-135">The diagram represents **all the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="ea244-p111">제품 수명은 이벤트 유형입니다. 특정 제품이 제품 수명에 도달하는 것이 이벤트입니다. 해당 이벤트 유형의 이벤트가 발생할 때(이 경우 제품이 수명 종료에 도달) 다음을 지정하는 이벤트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-p111">Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs—in this case, when a product reaches its end of life—you create an event that specifies:</span></span>
    
   - <span data-ttu-id="ea244-138">자산 ID(SharePoint 및 OneDrive 문서 관련)</span><span class="sxs-lookup"><span data-stu-id="ea244-138">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
   - <span data-ttu-id="ea244-p112">키워드(Exchange 항목 관련). 이 예제에서 조직은 Exchange 항목에 대한 키워드가 SharePoint 및 OneDrive 문서에 대한 자산 ID와 동일하도록 제품 레코드를 포함하는 메시지에 제품 코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-p112">Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is functionally the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
   - <span data-ttu-id="ea244-p113">이벤트가 발생한 날짜. 이 날짜는 보존 기간의 시작 날짜로 사용됩니다. 이 날짜는 현재, 과거 또는 미래의 날짜가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-p113">The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.</span></span>

4. <span data-ttu-id="ea244-144">이벤트를 작성한 후, 해당 이벤트 날짜는 해당 이벤트 유형의 보존 레이블이 있으며 지정된 자산 ID 또는 키워드를 포함하는 모든 콘텐츠와 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-144">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="ea244-145">모든 보존 레이블과 마찬가지로 이 동기화는 7일 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-145">Like any retention label, this synchronization can take up to seven days.</span></span> <span data-ttu-id="ea244-146">이전 다이어그램에서 빨간색 원으로 둘러싸인 모든 항목에는 이 이벤트를 통해 트리거되는 보존 기간이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-146">In the previous diagram, all the items circled in red have their retention period triggered by this event.</span></span> <span data-ttu-id="ea244-147">즉, 이 제품이 수명의 끝에 도달하면 해당 이벤트는 해당 제품의 레코드에 대한 보존 기간을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-147">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>

<span data-ttu-id="ea244-148">이벤트에 대해 자산 ID 또는 키워드를 지정하지 않으면 해당 이벤트 유형의 보존 레이블이 있는 **모든 콘텐츠** 가 이벤트에 의해 트리거된 보존 기간을 갖게 된다는 것을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-148">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a retention label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="ea244-149">이는 위의 다이어그램에서 모든 콘텐츠가 유지되기 시작한다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-149">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="ea244-150">이는 원치 않는 일일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-150">This might not be what you intend.</span></span>

<span data-ttu-id="ea244-151">마지막으로 각 보존 레이블에는 별도의 보존 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-151">Finally, remember that each retention label has its own retention settings.</span></span> <span data-ttu-id="ea244-152">이 예에서는 모든 레이블이 10년을 지정하지만 각 레이블의 보존 기간이 다른 경우 이벤트가 보존 레이블을 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-152">In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="ea244-153">이벤트 구동 보존 설정 방법</span><span class="sxs-lookup"><span data-stu-id="ea244-153">How to set up event-driven retention</span></span>

<span data-ttu-id="ea244-154">이벤트 구동 보존의 상위 레벨 워구동우우:</span><span class="sxs-lookup"><span data-stu-id="ea244-154">High-level workflow for event-driven retention:</span></span>
  
![이벤트 구동 보존을 설정하는 워크플로 다이어그램](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="ea244-156">SharePont에서 관리 속성을 사용하여 보존 레이블을 자동 적용하고 이벤트 중심 보존을 구현하는 방법에 대한 자세한 시나리오는 [보존 레이블로 SharePoint에서 문서의 수명 주기 관리](auto-apply-retention-labels-scenario.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea244-156">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="ea244-157">1단계: 보존 기간이 이벤트에 따라 조정되는 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="ea244-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="ea244-158">보존 레이블을 만들고 구성하려면 [보존 레이블 만들기 및 구성](create-retention-labels.md#create-and-configure-retention-labels)의 지침을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ea244-158">To create and configure your retention label, use the instructions from [Create and configure retention labels](create-retention-labels.md#create-and-configure-retention-labels).</span></span> <span data-ttu-id="ea244-159">이벤트 기반 보존에만 해당하는 경우 보존 레이블 만들기 마법사의 **보존 설정 정의** 페이지에서 **기반 보존 기간을 시작** 한 후 드롭다운 목록에서 기본 이벤트 유형 중 하나를 선택하거나 **새 이벤트 유형 만들기** 를 선택하여 직접 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-159">But specific to event-based retention, on the **Define retention settings** page of the Create retention label wizard, after **Start the retention period based on**, select one of the default event types from the dropdown list, or create your own by selecting **Create new event type**:</span></span>

![보존 레이블에 새 이벤트 유형 만들기](../media/SPRetention6.png)

<span data-ttu-id="ea244-161">이벤트 유형은 보존 레이블을 연결할 이벤트에 대한 일반적인 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-161">An event type is simply a general description of an event that you want to associate with a retention label.</span></span>

<span data-ttu-id="ea244-162">기본 이벤트 유형에는 손쉬운 식별을 위해 드롭다운 목록에 이름이 표시되는 **(이벤트 유형)** **레코드 관리** > **이벤트** > **이벤트 유형 관리** 를 참조하여 이벤트 유형을 보고 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-162">The default event types have **(event type)** after their name in the dropdown list for easier identification, and you can also see and create event type from the **Records management** > **Events** tab > **Manage event types**.</span></span>

<span data-ttu-id="ea244-163">이벤트 기반 보존에는 다음과 같은 보존 설정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-163">Event-based retention requires retention settings that:</span></span>
  
- <span data-ttu-id="ea244-164">콘텐츠를 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-164">Retain the content.</span></span>
    
- <span data-ttu-id="ea244-165">보존 기간이 끝나면 콘텐츠를 자동으로 삭제하거나 처리 검토를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-165">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
  
<span data-ttu-id="ea244-166">이벤트 기반 보존은 보통 레코드로 선언되는 콘텐츠에 사용되므로 콘텐츠를 [레코드](records-management.md#records)로 표시하는 옵션도 선택해야 하는지 확인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-166">Event-based retention is typically used for content that's declared a record, so this is a good time to check whether you also need to select the option that marks content as a [record](records-management.md#records).</span></span>

<span data-ttu-id="ea244-167">새 이벤트 유형을 만드는 대신 기존 이벤트 유형을 사용하고 있는 경우에는 3 단계로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-167">If you're using an existing event type rather than creating a new event type, skip to step 3.</span></span>

> [!NOTE]
> <span data-ttu-id="ea244-168">이벤트 유형을 선택하고 보존 레이블을 저장한 후에는 이벤트 유형을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-168">After you choose an event type and save the retention label, the event type cannot be changed.</span></span>

### <a name="step-2-create-a-new-event-type-for-your-label"></a><span data-ttu-id="ea244-169">단계 2: 레이블에 새 이벤트 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="ea244-169">Step 2: Create a new event type for your label</span></span>

<span data-ttu-id="ea244-170">보존 설정의 경우 **새 이벤트 유형 만들기** 를 선택했다면 이벤트 유형에 대한 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-170">For the retention settings, if you selected **Create new event type**, enter a name and description for your event type.</span></span> <span data-ttu-id="ea244-171">그 후 **다음**, **제출**, 그리고 **완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-171">Then select **Next**, **Submit**, and **Done**.</span></span>

<span data-ttu-id="ea244-172">**보존 설정 정의** 페이지에 돌아와서 **기준에 따라 보존 기간을 시작하려면** 드롭다운 목록을 사용하여 만든 이벤트 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-172">Back on the **Define retention settings** page, for **Start the retention period based on**, use the dropdown list to select the event type that you created.</span></span>

  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="ea244-173">3단계: 이벤트 기반 보존 레이블 게시 혹은 자동 적용</span><span class="sxs-lookup"><span data-stu-id="ea244-173">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="ea244-174">다른 보존 레이블과 마찬가지로 이벤트 기반 레이블을 게시하거나 자동 적용해야만 콘텐츠에 수동 또는 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-174">Just like any retention label, you need to publish or auto-apply an event-based label, for it to be manually or automatically applied to content:</span></span>
- [<span data-ttu-id="ea244-175">보존 레이블을 만들고 앱에 적용하기</span><span class="sxs-lookup"><span data-stu-id="ea244-175">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="ea244-176">보존 레이블을 콘텐츠에 자동으로 적용하기</span><span class="sxs-lookup"><span data-stu-id="ea244-176">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="ea244-177">4단계: 자산 ID 입력</span><span class="sxs-lookup"><span data-stu-id="ea244-177">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="ea244-178">이벤트 기반 레이블이 콘텐츠에 적용된 후 각 항목의 자산 ID를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-178">After an event-based label is applied to content, you can enter an asset ID for each item.</span></span> <span data-ttu-id="ea244-179">예를 들어 사용자의 조직은 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-179">For example, your organization might use:</span></span>
  
- <span data-ttu-id="ea244-180">특정 제품에 대한 콘텐츠만 보존하는 데 사용할 수 있는 제품 코드</span><span class="sxs-lookup"><span data-stu-id="ea244-180">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="ea244-181">특정 프로젝트에 대한 콘텐츠만 보존하는 데 사용할 수 있는 프로젝트 코드</span><span class="sxs-lookup"><span data-stu-id="ea244-181">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="ea244-182">특정 사람에 대한 콘텐츠만 보존하는 데 사용할 수 있는 직원 ID</span><span class="sxs-lookup"><span data-stu-id="ea244-182">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="ea244-183">자산 ID는 SharePoint 및 OneDrive에서 사용할 수 있는 또 다른 문서 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-183">Asset ID is simply another document property that's available in SharePoint and OneDrive.</span></span> <span data-ttu-id="ea244-184">조직에서 이미 다른 문서 속성 및 ID를 사용하여 콘텐츠를 분류하고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-184">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="ea244-185">이 경우에는 이벤트를 작성할 때 해당 속성 및 값을 사용할 수도 있습니다. 아래 6단계를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea244-185">If so, you can also use those properties and values when you create an event—see step 6 that follows.</span></span> <span data-ttu-id="ea244-186">중요한 점은 사용자가 문서 속성에서 일부 *속성:값* 조합을 사용하여 해당 항목을 이벤트 유형과 연결시켜야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-186">The important point is that you must use some *property:value* combination in the document properties to associate that item with an event type.</span></span>
  
![자산 ID를 입력하기 위한 텍스트 상자](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="ea244-188">5단계: 이벤트 만들기</span><span class="sxs-lookup"><span data-stu-id="ea244-188">Step 5: Create an event</span></span>

<span data-ttu-id="ea244-189">해당 이벤트 유형의 특정 인스턴스가 발생하면(예: 제품이 수명 종료에 도달), Microsoft 365 규정 준수 센터의 **레코드 관리** > **이벤트** 페이지로 가서 **+만들기** 를 선택하여 이벤트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-189">When a particular instance of that event type occurs, such as a product reaches its end of life, go to the **Records management** > **Events** page in the Microsoft 365 compliance center, and select **+ Create** to create an event.</span></span> <span data-ttu-id="ea244-190">여기에 이벤트를 만들어 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-190">You trigger the event by creating it, here.</span></span>

![이벤트 기반 보존 레이블에 대한 보존 시작을 트리거하는 이벤트 만들기](../media/create-event-records-management.png)

<span data-ttu-id="ea244-192">테넌트당 최대 100만 이벤트를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-192">Up to one million events are supported per tenant.</span></span>

### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="ea244-193">6단계: 2단계에서 레이블에 사용된 것과 동일한 이벤트 유형 선택</span><span class="sxs-lookup"><span data-stu-id="ea244-193">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="ea244-194">이벤트를 만들 때 2단계에서 보존 레이블 설정에 지정되는 동일한 이벤트 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-194">When you create the event, choose the same event type specified in the retention label settings in step 2.</span></span> <span data-ttu-id="ea244-195">예를 들어 **제품 수명** 을 레이블 설정의 이벤트 유형으로 선택했다면 이벤트를 만들 때 **제품 수명** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-195">For example, if you selected **Product Lifetime** as your event type for the label settings, select **Product Lifetime** when you create the event.</span></span> <span data-ttu-id="ea244-196">해당 이벤트 유형에 적용된 보존 레이블이 있는 콘텐츠에 대해서만 보존 기간이 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-196">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>

![이벤트 유형을 선택하기 위한 이벤트 설정 옵션](../media/choose-event-type-records-management.png)

<span data-ttu-id="ea244-198">또는 다양한 이벤트 유형을 포함하는 여러 보존 레이블 이벤트를 만들어야 하는 경우 **기존 레이블 선택** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-198">Alternatively, if you need to create an event for multiple retention labels that have different event types, select the **Choose Existing Labels** option.</span></span> <span data-ttu-id="ea244-199">그런 다음 이 이벤트와 연결하려는 이벤트 유형에 대해 구성된 레이블을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-199">Then, select the labels that are configured for the event types you want to associate with this event.</span></span>

### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="ea244-200">7단계: 키워드 또는 자산 ID 입력</span><span class="sxs-lookup"><span data-stu-id="ea244-200">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="ea244-201">이제 SharePoint 및 OneDrive 콘텐츠의 자산 ID 또는 Exchange 콘텐츠의 키워드를 지정하여 콘텐츠 범위를 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-201">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content, or keywords for Exchange content.</span></span> <span data-ttu-id="ea244-202">자산 ID의 경우 지정된 *속성:값* 쌍을 가진 콘텐츠에 대해서만 보존이 강제 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-202">For asset IDs, retention will be enforced only on content with the specified *property:value* pair.</span></span> <span data-ttu-id="ea244-203">자산 ID가 입력되지 않은 경우 해당 이벤트 유형의 레이블을 가진 모든 콘텐츠는 동일한 보존 날짜가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-203">If an asset ID is not entered, all content with labels of that event type get the same retention date applied to them.</span></span>

<span data-ttu-id="ea244-204">예를 들어 자산 ID 속성을 사용하는 경우 아래 표시된 자산 ID 상자에 `ComplianceAssetID:<value>`을(를) 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-204">For example: If you're using the Asset ID property, enter `ComplianceAssetID:<value>` in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="ea244-205">조직에서 이 이벤트 유형과 관련된 문서에 다른 속성 및 ID를 적용했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-205">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="ea244-206">예를 들어, 특정 제품의 레코드를 발견해야 하는 경우 ID는 사용자 지정 속성 ProductID와 "XYZ" 값의 조합일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-206">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="ea244-207">이 경우 아래 그림에 표시된 자산 ID 상자에 `ProductID:XYZ`을(를) 입력했습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-207">In this case, you'd enter `ProductID:XYZ` in the box for asset IDs shown in the following picture.</span></span>
  
<span data-ttu-id="ea244-208">Exchange 항목의 경우 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-208">For Exchange items, use keywords.</span></span> <span data-ttu-id="ea244-209">검색 연산자(예: AND, OR 및 NOT)를 사용하여 쿼리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-209">You can use a query by using search operators such as AND, OR, and NOT.</span></span> <span data-ttu-id="ea244-210">자세한 내용은 [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea244-210">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="ea244-211">마지막으로 이벤트가 발생한 날짜를 선택합니다. 이 날짜는 보존 기간의 시작 날짜로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-211">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="ea244-212">이벤트를 작성한 후, 이벤트 날짜는 해당 이벤트 유형, 자산 ID 및 키워드의 보존 레이블이 있는 모든 콘텐츠와 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-212">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords.</span></span> <span data-ttu-id="ea244-213">모든 보존 레이블과 마찬가지로 이 동기화는 최대 7일 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-213">As with any retention label, this synchronization can take up to seven days.</span></span>
  
![이벤트 설정 페이지](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

<span data-ttu-id="ea244-215">이벤트를 만든 후 보존 설정은 이미 레이블이 지정되고 인덱싱된 콘텐츠에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-215">After creating an event, the retention settings take effect for the content that's already labeled and indexed.</span></span> <span data-ttu-id="ea244-216">이벤트를 만든 후 새 콘텐츠에 보존 레이블을 추가한 경우에는 동일한 세부 정보를 사용하여 새 이벤트를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-216">If the retention label is added to new content after the event is created, you must create a new event with the same details.</span></span>

<span data-ttu-id="ea244-217">이벤트를 삭제해도 이미 레이블이 지정된 콘텐츠에 적용되는 보존 설정은 취소되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-217">Deleting an event doesn't cancel the retention settings that are now in effect for the content that's already labeled.</span></span> <span data-ttu-id="ea244-218">보존 설정을 취소하려면 동일한 세부 정보를 사용하여 새 이벤트를 만들되 날짜를 비워 두세요.</span><span class="sxs-lookup"><span data-stu-id="ea244-218">To do that, create a new event with the same details, but leave the date blank.</span></span> 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="ea244-219">콘텐츠 검색을 사용하여 특정 레이블 또는 자산 ID를 포함하는 모든 콘텐츠 찾기</span><span class="sxs-lookup"><span data-stu-id="ea244-219">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="ea244-220">콘텐츠에 보존 레이블이 할당된 후에 콘텐츠 검색을 사용하여 특정 보존 레이블로 분류되거나 특정 자산 ID를 포함하는 모든 콘텐츠를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-220">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID:</span></span>
  
- <span data-ttu-id="ea244-221">특정 보존 레이블이 있는 모든 콘텐츠를 찾으려면 **보존 레이블** 조건을 선택하고 전체 레이블 이름 또는 레이블 이름 일부를 입력하고 와일드카드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-221">To find all content with a specific retention label, choose the **Retention label** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="ea244-222">특정 자산 ID가 있는 모든 콘텐츠를 찾으려면 **ComplianceAssetID** 속성과 값(예: `ComplianceAssetID:<value>`)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-222">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, using the format `ComplianceAssetID:<value>`.</span></span> 
    
<span data-ttu-id="ea244-223">자세한 내용은 [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea244-223">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>

## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="ea244-224">PowerShell을 사용하여 이벤트 자동화</span><span class="sxs-lookup"><span data-stu-id="ea244-224">Automate events by using PowerShell</span></span>

<span data-ttu-id="ea244-225">PowerShell 스크립트를 사용하여 비즈니스 응용 프로그램에서 이벤트 기반 보존을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-225">You can use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="ea244-226">이벤트 기반 보존에 다음 PowerShell cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-226">The PowerShell cmdlets available for event-based retention:</span></span>
  
- [<span data-ttu-id="ea244-227">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="ea244-227">Get-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [<span data-ttu-id="ea244-228">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="ea244-228">New-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [<span data-ttu-id="ea244-229">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="ea244-229">Remove-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [<span data-ttu-id="ea244-230">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="ea244-230">Set-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [<span data-ttu-id="ea244-231">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="ea244-231">Get-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [<span data-ttu-id="ea244-232">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="ea244-232">New-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873003)
    

## <a name="automate-events-by-using-a-rest-api"></a><span data-ttu-id="ea244-233">REST API를 사용하여 이벤트 자동화하기</span><span class="sxs-lookup"><span data-stu-id="ea244-233">Automate events by using a REST API</span></span>

<span data-ttu-id="ea244-234">REST API를 사용하여 보존 시간 시작을 트리거하는 이벤트를 자동으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-234">You can use a REST API to automatically create the events that trigger the start of the retention time.</span></span>

<span data-ttu-id="ea244-235">REST API는 서비스 자원에 대한 액세스를 생성/검색/갱신/삭제하는 HTTP 조작(메소드) 세트를 지원하는 서비스 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-235">A REST API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="ea244-236">자세한 정보는 [REST API 요청/응답 구성 요소](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea244-236">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="ea244-237">Microsoft 365 REST API를 사용하여 POST 및 GET 메서드를 사용하여 이벤트를 만들고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-237">By using the Microsoft 365 REST API, events can be created and retrieved using the POST and GET methods.</span></span>

<span data-ttu-id="ea244-238">REST API를 사용할 수 있는 옵션은 다음과 같이 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-238">There are two options for using the REST API:</span></span>

- <span data-ttu-id="ea244-239">이벤트 발생을 자동으로 트리거하는 **Microsoft Power Automate 또는 유사한 응용 프로그램**</span><span class="sxs-lookup"><span data-stu-id="ea244-239">**Microsoft Power Automate or a similar application** to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="ea244-240">Microsoft Power Automate는 다른 시스템에 연결하기 위한 조정자이므로 사용자 지정 솔루션을 작성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-240">Microsoft Power Automate is an orchestrator for connecting to other systems, so you don't need to write a custom solution.</span></span> <span data-ttu-id="ea244-241">자세한 내용은 [Power Automate 웹 사이트](https://flow.microsoft.com/ko-KR/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea244-241">For more information, see the [Power Automate website](https://flow.microsoft.com/ko-KR/).</span></span>

- <span data-ttu-id="ea244-242">사용자 지정 솔루션의 일부인 PowerShell(버전 6 이상)을 사용하여 이벤트를 생성하기 위해 **REST API를 호출하는 PowerShell 또는 HTTP 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="ea244-242">**PowerShell or an HTTP client to call the REST API** to create events by using PowerShell (version 6 or later), which is part of a custom solution.</span></span>

<span data-ttu-id="ea244-243">전역 관리자로서 REST API를 사용하기 전에 보존 이벤트 호출에 사용할 URL을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-243">Before you use the REST API, as a global administrator, confirm the URL to use for the retention event call.</span></span> <span data-ttu-id="ea244-244">확인하려면 다음 REST API URL을 사용하여 POST 보존 이벤트 호출을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-244">To do this, run a GET retention event call by using the REST API URL:</span></span>

```console
https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
```

<span data-ttu-id="ea244-245">응답코드를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ea244-245">Check the response code.</span></span> <span data-ttu-id="ea244-246">302인 경우 응답 헤더의 위치 속성에서 리디렉션 URL을 가져오고 다음 지침에 `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` 대신 해당 URL을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ea244-246">If it's 302, get the redirected URL from the Location property of the response header and use that URL instead of `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` in the instructions that follow.</span></span>

<span data-ttu-id="ea244-247">자동으로 생성되는 이벤트는 Microsoft 365 규정 준수 센터 > **레코드 관리** >  **이벤트** 에서 보고 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-247">The events that get automatically created can be confirmed by viewing them in the Microsoft 365 compliance center > **Records management** >  **Events**.</span></span>

### <a name="use-microsoft-power-automate-to-create-the-event"></a><span data-ttu-id="ea244-248">Microsoft Power Automate를 사용하여 이벤트 만들기</span><span class="sxs-lookup"><span data-stu-id="ea244-248">Use Microsoft Power Automate to create the event</span></span>

<span data-ttu-id="ea244-249">Microsoft 365 REST API를 사용하여 이벤트를 생성하는 흐름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-249">Create a flow that creates an event using the Microsoft 365 REST API:</span></span>

![Flow를 사용해 이벤트 만들기](../media/automate-event-driven-retention-flow-1.png)

![Flow를 사용해 REST API 호출하기](../media/automate-event-driven-retention-flow-2.png)

#### <a name="create-an-event"></a><span data-ttu-id="ea244-252">이벤트 만들기</span><span class="sxs-lookup"><span data-stu-id="ea244-252">Create an event</span></span>

<span data-ttu-id="ea244-253">REST API를 호출하는 샘플 코드:</span><span class="sxs-lookup"><span data-stu-id="ea244-253">Sample code to call the REST API:</span></span>

- <span data-ttu-id="ea244-254">**메서드**: POST</span><span class="sxs-lookup"><span data-stu-id="ea244-254">**Method**: POST</span></span>
- <span data-ttu-id="ea244-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="ea244-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="ea244-256">**헤더**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="ea244-256">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="ea244-257">**Body**:</span><span class="sxs-lookup"><span data-stu-id="ea244-257">**Body**:</span></span>
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
    
- <span data-ttu-id="ea244-258">**인증**: 기본</span><span class="sxs-lookup"><span data-stu-id="ea244-258">**Authentication**: Basic</span></span>
- <span data-ttu-id="ea244-259">**사용자 이름**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="ea244-259">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="ea244-260">**암호**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="ea244-260">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="ea244-261">사용 가능한 매개 변수</span><span class="sxs-lookup"><span data-stu-id="ea244-261">Available parameters</span></span>


|<span data-ttu-id="ea244-262">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ea244-262">Parameters</span></span>|<span data-ttu-id="ea244-263">설명</span><span class="sxs-lookup"><span data-stu-id="ea244-263">Description</span></span>|<span data-ttu-id="ea244-264">참고</span><span class="sxs-lookup"><span data-stu-id="ea244-264">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="ea244-265"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="ea244-265"><d:Name></d:Name></span></span>|<span data-ttu-id="ea244-266">이벤트에 대해 고유한 이름을 제공하고,</span><span class="sxs-lookup"><span data-stu-id="ea244-266">Provide a unique name for the event,</span></span>|<span data-ttu-id="ea244-267">후행 공백 또는 문자 % \* \ & < \> \| # ?를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-267">Cannot contain trailing spaces or the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="ea244-268">, : ;</span><span class="sxs-lookup"><span data-stu-id="ea244-268">, : ;</span></span>|
|<span data-ttu-id="ea244-269"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="ea244-269"><d:EventType></d:EventType></span></span>|<span data-ttu-id="ea244-270">이벤트 유형 이름(또는 Guid)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-270">Enter event type name (or Guid),</span></span>|<span data-ttu-id="ea244-271">예제: "직원 퇴사."</span><span class="sxs-lookup"><span data-stu-id="ea244-271">Example: "Employee termination".</span></span> <span data-ttu-id="ea244-272">이벤트 유형은 보존 레이블과 관련되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-272">Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="ea244-273"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="ea244-273"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="ea244-274">“ComplianceAssetId:” + 직원 ID 입력</span><span class="sxs-lookup"><span data-stu-id="ea244-274">Enter "ComplianceAssetId:" + employee ID</span></span>|<span data-ttu-id="ea244-275">예제: "ComplianceAssetId:12345"</span><span class="sxs-lookup"><span data-stu-id="ea244-275">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="ea244-276"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="ea244-276"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="ea244-277">이벤트 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="ea244-277">Event Date and Time</span></span>|<span data-ttu-id="ea244-278">형식: yyyy-MM-ddTHH:mm:ssZ, 예제: 2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="ea244-278">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

###### <a name="response-codes"></a><span data-ttu-id="ea244-279">응답코드</span><span class="sxs-lookup"><span data-stu-id="ea244-279">Response codes</span></span>

| <span data-ttu-id="ea244-280">응답코드</span><span class="sxs-lookup"><span data-stu-id="ea244-280">Response Code</span></span> | <span data-ttu-id="ea244-281">설명</span><span class="sxs-lookup"><span data-stu-id="ea244-281">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="ea244-282">302</span><span class="sxs-lookup"><span data-stu-id="ea244-282">302</span></span>               | <span data-ttu-id="ea244-283">리디렉션</span><span class="sxs-lookup"><span data-stu-id="ea244-283">Redirect</span></span>              |
| <span data-ttu-id="ea244-284">201</span><span class="sxs-lookup"><span data-stu-id="ea244-284">201</span></span>               | <span data-ttu-id="ea244-285">만든 날짜</span><span class="sxs-lookup"><span data-stu-id="ea244-285">Created</span></span>               |
| <span data-ttu-id="ea244-286">403</span><span class="sxs-lookup"><span data-stu-id="ea244-286">403</span></span>               | <span data-ttu-id="ea244-287">인증 실패</span><span class="sxs-lookup"><span data-stu-id="ea244-287">Authorization Failed</span></span>  |
| <span data-ttu-id="ea244-288">401</span><span class="sxs-lookup"><span data-stu-id="ea244-288">401</span></span>               | <span data-ttu-id="ea244-289">인증 실패</span><span class="sxs-lookup"><span data-stu-id="ea244-289">Authentication Failed</span></span> |

##### <a name="get-events-based-on-a-time-range"></a><span data-ttu-id="ea244-290">이벤트를 시간 범위를 기준으로 가져오기</span><span class="sxs-lookup"><span data-stu-id="ea244-290">Get events based on a time range</span></span>

- <span data-ttu-id="ea244-291">**메서드**: GET</span><span class="sxs-lookup"><span data-stu-id="ea244-291">**Method**: GET</span></span>

- <span data-ttu-id="ea244-292">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="ea244-292">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="ea244-293">**헤더**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="ea244-293">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="ea244-294">**인증**: 기본</span><span class="sxs-lookup"><span data-stu-id="ea244-294">**Authentication**: Basic</span></span>

- <span data-ttu-id="ea244-295">**사용자 이름**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="ea244-295">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="ea244-296">**암호**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="ea244-296">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="ea244-297">응답코드</span><span class="sxs-lookup"><span data-stu-id="ea244-297">Response codes</span></span>

| <span data-ttu-id="ea244-298">응답코드</span><span class="sxs-lookup"><span data-stu-id="ea244-298">Response Code</span></span> | <span data-ttu-id="ea244-299">설명</span><span class="sxs-lookup"><span data-stu-id="ea244-299">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="ea244-300">200</span><span class="sxs-lookup"><span data-stu-id="ea244-300">200</span></span>               | <span data-ttu-id="ea244-301">확인, atom + xml의 이벤트 목록</span><span class="sxs-lookup"><span data-stu-id="ea244-301">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="ea244-302">404</span><span class="sxs-lookup"><span data-stu-id="ea244-302">404</span></span>               | <span data-ttu-id="ea244-303">찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="ea244-303">Not found</span></span>                         |
| <span data-ttu-id="ea244-304">302</span><span class="sxs-lookup"><span data-stu-id="ea244-304">302</span></span>               | <span data-ttu-id="ea244-305">리디렉션</span><span class="sxs-lookup"><span data-stu-id="ea244-305">Redirect</span></span>                          |
| <span data-ttu-id="ea244-306">401</span><span class="sxs-lookup"><span data-stu-id="ea244-306">401</span></span>               | <span data-ttu-id="ea244-307">인증 실패</span><span class="sxs-lookup"><span data-stu-id="ea244-307">Authorization Failed</span></span>              |
| <span data-ttu-id="ea244-308">403</span><span class="sxs-lookup"><span data-stu-id="ea244-308">403</span></span>               | <span data-ttu-id="ea244-309">인증 실패</span><span class="sxs-lookup"><span data-stu-id="ea244-309">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="ea244-310">이벤트 ID로 가져오기</span><span class="sxs-lookup"><span data-stu-id="ea244-310">Get an event by ID</span></span>

- <span data-ttu-id="ea244-311">**메서드**: GET</span><span class="sxs-lookup"><span data-stu-id="ea244-311">**Method**: GET</span></span>

- <span data-ttu-id="ea244-312">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="ea244-312">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="ea244-313">**헤더**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="ea244-313">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="ea244-314">**인증**: 기본</span><span class="sxs-lookup"><span data-stu-id="ea244-314">**Authentication**: Basic</span></span>

- <span data-ttu-id="ea244-315">**사용자 이름**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="ea244-315">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="ea244-316">**암호**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="ea244-316">**Password**: "Compliancepassword"</span></span>

###### <a name="response-codes"></a><span data-ttu-id="ea244-317">응답코드</span><span class="sxs-lookup"><span data-stu-id="ea244-317">Response codes</span></span>

| <span data-ttu-id="ea244-318">응답코드</span><span class="sxs-lookup"><span data-stu-id="ea244-318">Response Code</span></span> | <span data-ttu-id="ea244-319">설명</span><span class="sxs-lookup"><span data-stu-id="ea244-319">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="ea244-320">200</span><span class="sxs-lookup"><span data-stu-id="ea244-320">200</span></span>               | <span data-ttu-id="ea244-321">확인, 응답 본문에 atom + xml 이벤트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-321">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="ea244-322">404</span><span class="sxs-lookup"><span data-stu-id="ea244-322">404</span></span>               | <span data-ttu-id="ea244-323">찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="ea244-323">Not found</span></span>                                            |
| <span data-ttu-id="ea244-324">302</span><span class="sxs-lookup"><span data-stu-id="ea244-324">302</span></span>               | <span data-ttu-id="ea244-325">리디렉션</span><span class="sxs-lookup"><span data-stu-id="ea244-325">Redirect</span></span>                                             |
| <span data-ttu-id="ea244-326">401</span><span class="sxs-lookup"><span data-stu-id="ea244-326">401</span></span>               | <span data-ttu-id="ea244-327">인증 실패</span><span class="sxs-lookup"><span data-stu-id="ea244-327">Authorization Failed</span></span>                                 |
| <span data-ttu-id="ea244-328">403</span><span class="sxs-lookup"><span data-stu-id="ea244-328">403</span></span>               | <span data-ttu-id="ea244-329">인증 실패</span><span class="sxs-lookup"><span data-stu-id="ea244-329">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="ea244-330">이벤트 이름으로 받기</span><span class="sxs-lookup"><span data-stu-id="ea244-330">Get an event by name</span></span>

- <span data-ttu-id="ea244-331">**메서드**: GET</span><span class="sxs-lookup"><span data-stu-id="ea244-331">**Method**: GET</span></span>

- <span data-ttu-id="ea244-332">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="ea244-332">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="ea244-333">**헤더**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="ea244-333">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="ea244-334">**인증**: 기본</span><span class="sxs-lookup"><span data-stu-id="ea244-334">**Authentication**: Basic</span></span>

- <span data-ttu-id="ea244-335">**사용자 이름**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="ea244-335">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="ea244-336">**암호**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="ea244-336">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="ea244-337">응답코드</span><span class="sxs-lookup"><span data-stu-id="ea244-337">Response codes</span></span>

| <span data-ttu-id="ea244-338">응답코드</span><span class="sxs-lookup"><span data-stu-id="ea244-338">Response Code</span></span> | <span data-ttu-id="ea244-339">설명</span><span class="sxs-lookup"><span data-stu-id="ea244-339">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="ea244-340">200</span><span class="sxs-lookup"><span data-stu-id="ea244-340">200</span></span>               | <span data-ttu-id="ea244-341">확인, 응답 본문에 atom + xml 이벤트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-341">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="ea244-342">404</span><span class="sxs-lookup"><span data-stu-id="ea244-342">404</span></span>               | <span data-ttu-id="ea244-343">찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="ea244-343">Not found</span></span>                                            |
| <span data-ttu-id="ea244-344">302</span><span class="sxs-lookup"><span data-stu-id="ea244-344">302</span></span>               | <span data-ttu-id="ea244-345">리디렉션</span><span class="sxs-lookup"><span data-stu-id="ea244-345">Redirect</span></span>                                             |
| <span data-ttu-id="ea244-346">401</span><span class="sxs-lookup"><span data-stu-id="ea244-346">401</span></span>               | <span data-ttu-id="ea244-347">인증 실패</span><span class="sxs-lookup"><span data-stu-id="ea244-347">Authorization Failed</span></span>                                 |
| <span data-ttu-id="ea244-348">403</span><span class="sxs-lookup"><span data-stu-id="ea244-348">403</span></span>               | <span data-ttu-id="ea244-349">인증 실패</span><span class="sxs-lookup"><span data-stu-id="ea244-349">Authentication Failed</span></span>                                |

### <a name="use-powershell-or-any-http-client-to-create-the-event"></a><span data-ttu-id="ea244-350">PowerShell 또는 HTTP 클라이언트를 사용하여 이벤트 만들기</span><span class="sxs-lookup"><span data-stu-id="ea244-350">Use PowerShell or any HTTP client to create the event</span></span>

<span data-ttu-id="ea244-351">PowerShell은 버전 6 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-351">PowerShell must be version 6 or later.</span></span>

<span data-ttu-id="ea244-352">PowerShell 세션에서 다음 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ea244-352">In a PowerShell session, run the following script:</span></span>

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```

