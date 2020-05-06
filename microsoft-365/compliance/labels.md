---
title: 보존 레이블 개요
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 보존 레이블을 사용하여 조직 전체의 데이터를 관리하여 분류하고 해당 분류에 따라 보존 규칙을 시행하십시오. 보존 레이블을 사용하여 Microsoft 365용 레코드 관리 솔루션을 구현할 수도 있습니다.
ms.openlocfilehash: 6496c5f82ee21e2085568f5e623fc6ee75145b8a
ms.sourcegitcommit: f5cecd77e63ae8b47743d4f6dc3135f5decaf28b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2020
ms.locfileid: "43949315"
---
# <a name="overview-of-retention-labels"></a><span data-ttu-id="f5ca1-104">보존 레이블 개요</span><span class="sxs-lookup"><span data-stu-id="f5ca1-104">Overview of retention labels</span></span>

><span data-ttu-id="f5ca1-105">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="f5ca1-105">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="f5ca1-p102">조직 전체에서 산업 규정 및 내부 정책을 준수하기 위해 다른 작업이 수행되어야 하는 다음과 같은 다른 형식의 콘텐츠가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p102">Across your organization, you probably have different types of content that require different actions taken on them in order to comply with industry regulations and internal policies. For example, you might have:</span></span>
  
- <span data-ttu-id="f5ca1-108">최소 기간 동안 **보존**해야 하는 세금 양식</span><span class="sxs-lookup"><span data-stu-id="f5ca1-108">Tax forms that need to be **retained** for a minimum period of time.</span></span> 
    
- <span data-ttu-id="f5ca1-109">특정 기간에 도달할 때 **영구적으로 삭제**되어야 하는 보도 자료</span><span class="sxs-lookup"><span data-stu-id="f5ca1-109">Press materials that need to be **permanently deleted** when they reach a certain age.</span></span> 
    
- <span data-ttu-id="f5ca1-110">**보존**되었다가 **영구적으로 삭제**되어야 하는 경쟁업체 연구 자료</span><span class="sxs-lookup"><span data-stu-id="f5ca1-110">Competitive research that needs to be both **retained** and then **permanently deleted**.</span></span> 
    
- <span data-ttu-id="f5ca1-111">편집하거나 삭제할 수 없게 **기록으로 표시**해야 하는 취업 비자</span><span class="sxs-lookup"><span data-stu-id="f5ca1-111">Work visas that must be **marked as a record** so that they can't be edited or deleted.</span></span> 
    

<span data-ttu-id="f5ca1-p103">이러한 모든 경우에 Microsoft 365에서 보존 레이블은 올바른 콘텐츠에 대해 올바른 작업을 수행하는 데 도움이 될 수 있습니다. 보존 레이블을 사용하여 거버넌스를 위해 조직의 데이터를 분류하고 해당 분류에 따라 보존 규칙을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p103">In all of these cases, retention labels in Microsoft 365 can help you take the right actions on the right content. With retention labels, you can classify data across your organization for governance, and enforce retention rules based on that classification.</span></span>

<span data-ttu-id="f5ca1-114">보존 레이블을 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-114">With retention labels, you can:</span></span>
  
- <span data-ttu-id="f5ca1-p104">웹용 Outlook, Outlook 2010 이상, OneDrive, SharePoint 및 Microsoft 365 그룹에서 Outlook 콘텐츠에 **조직의 사용자가 보존 레이블을 수동으로 적용할 수 있게 합니다**. 사용자는 종종 자신이 사용하고 있는 콘텐츠의 형식을 가장 잘 알고 있기 때문에 콘텐츠를 분류하여 적절한 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p104">**Enable people in your organization to apply a retention label manually** to content in Outlook on the web, Outlook 2010 and later, OneDrive, SharePoint, and Microsoft 365 Groups. Users often know best what type of content they're working with, so they can classify it and have the appropriate policy applied.</span></span> 
    
- <span data-ttu-id="f5ca1-117">콘텐츠에 다음이 포함된 경우처럼 특정 조건과 일치하는 경우 **콘텐츠에 보존 레이블을 자동으로 적용**합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-117">**Apply retention labels to content automatically** if it matches specific conditions, such as when the content contains:</span></span> 
    
    - <span data-ttu-id="f5ca1-118">특정 중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="f5ca1-118">Specific types of sensitive information.</span></span>
    
    - <span data-ttu-id="f5ca1-119">만든 쿼리와 일치하는 특정 키워드</span><span class="sxs-lookup"><span data-stu-id="f5ca1-119">Specific keywords that match a query you create.</span></span>
    
    - <span data-ttu-id="f5ca1-120">학습 가능한 분류자에 대한 패턴 일치</span><span class="sxs-lookup"><span data-stu-id="f5ca1-120">Pattern matches for a trainable classifier.</span></span>
    
  <span data-ttu-id="f5ca1-121">콘텐츠에 자동으로 보존 레이블을 적용하는 기능도 다음과 같은 이유로 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-121">The ability to apply retention labels to content automatically is important because:</span></span>
    
     - <span data-ttu-id="f5ca1-122">사용자에게 모든 분류를 교육할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-122">You don't need to train your users on all of your classifications.</span></span>
    
     - <span data-ttu-id="f5ca1-123">모든 콘텐츠를 올바르게 분류하기 위해 사용자에게 의존할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-123">You don't need to rely on users to classify all content correctly.</span></span>
    
   - <span data-ttu-id="f5ca1-124">사용자가 더 이상 데이터 거버넌스 정책을 알아야 할 필요가 없으며, 그 대신 업무에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-124">Users no longer need to know about data governance policies - they can instead focus on their work.</span></span>

- <span data-ttu-id="f5ca1-p105">전자 메일 문서를 포함하는 **기록 관리를 Office 365에서 구현**합니다. 보존 레이블을 사용하여 콘텐츠를 기록으로 분류할 수 있습니다. 이 경우 레이블을 변경하거나 제거할 수 없으며 콘텐츠를 편집하거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p105">**Implement records management across Office 365**, including both email and documents. You can use a retention label to classify content as a record. When this happens, the label can't be changed or removed, and the content can't be edited or deleted.</span></span> 

- <span data-ttu-id="f5ca1-128">SharePoint의 **문서 라이브러리, 폴더 또는 문서 집합에 기본 보존 레이블을 적용**하여 해당 위치에 도착하는 모든 문서가 기본 보존 레이블을 상속하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-128">**Apply a default retention label to a document library, folder, or document set** in SharePoint, so that all documents that arrive in that location inherit the default retention label.</span></span>  
    
<span data-ttu-id="f5ca1-129">Microsoft 365 규정 준수 센터, Microsoft 365 보안 센터 또는보안 및 준수 센터에서 보존 레이블을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-129">You create retention labels in the Microsoft 365 compliance center, Microsoft 365 security center, or the Security & Compliance Center.</span></span>

## <a name="how-retention-labels-work-with-retention-label-policies"></a><span data-ttu-id="f5ca1-130">보존 레이블이 보존 레이블 정책에 작동하는 방식</span><span class="sxs-lookup"><span data-stu-id="f5ca1-130">How retention labels work with retention label policies</span></span>

<span data-ttu-id="f5ca1-131">콘텐츠를 분류할 수 있도록 조직의 사용자에게 보존 레이블을 제공하는 작업은 2단계 프로세스입니다. 먼저 보존 레이블을 만든 다음 선택한 위치에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-131">Making retention labels available to people in your organization so that they can classify content is a two-step process: first you create the retention labels, and then you publish them to the locations you choose.</span></span> <span data-ttu-id="f5ca1-132">보존 레이블을 게시하면 보존 레이블 정책이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-132">When you publish retention labels, a retention label policy gets created.</span></span>
  
![레이블의 역할 및 작업 다이어그램](../media/4082bc7d-c04c-4b9a-8a26-7f12565d3311.png)
  
<span data-ttu-id="f5ca1-134">보존 레이블은 한 개 이상의 보존 레이블 정책에 포함되는 독립적인 재사용 가능한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-134">Retention labels are independent, reusable building blocks that are included in one or more retention label policies.</span></span> <span data-ttu-id="f5ca1-135">보존 레이블 정책의 기본 목적은 보존 레이블 집합을 그룹화하고 해당 레이블을 표시할 위치를 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-135">The primary purpose of a retention label policy is to group a set of retention labels and specify the locations where you want those labels to appear.</span></span>
  
![레이블, 레이블 정책 및 위치 다이어그램](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
1. <span data-ttu-id="f5ca1-137">보존 레이블을 게시하면 보존 레이블 정책에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-137">When you publish retention labels, they're included in a retention label policy.</span></span> <span data-ttu-id="f5ca1-138">보존 라벨 이름은 변경할 수 없습니다. 즉, 라벨 이름을 만든 후에는 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-138">Retention label names are immutable, which means that they and cannot be edited after they're created.</span></span>


2. <span data-ttu-id="f5ca1-139">하나의 보존 레이블이 여러 보존 레이블 정책에 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-139">A single retention label can be included in many retention label policies.</span></span>

3. <span data-ttu-id="f5ca1-140">하나의 위치가 여러 보존 레이블 정책에 포함될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-140">A single location can also be included in many retention label policies.</span></span>    
    
3. <span data-ttu-id="f5ca1-141">보존 레이블 정책은 보존 레이블을 게시할 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-141">Retention label policies specify the locations to publish the retention labels.</span></span>
    
## <a name="only-one-retention-label-at-a-time"></a><span data-ttu-id="f5ca1-142">한 번에 하나의 보존 레이블만</span><span class="sxs-lookup"><span data-stu-id="f5ca1-142">Only one retention label at a time</span></span>

<span data-ttu-id="f5ca1-143">전자 메일 또는 문서와 같은 콘텐츠에는 한 번에 하나씩 단일 보존 레이블만 할당될 수 있다는 점에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-143">It's important to know that content like an email or document can have only a single retention label assigned to it at a time:</span></span>
  
- <span data-ttu-id="f5ca1-144">최종 사용자가 수동으로 할당한 보존 레이블의 경우, 할당된 보존 레이블을 제거하거나 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-144">For retention labels assigned manually by end users, people can remove or change the retention label that's assigned.</span></span>
    
- <span data-ttu-id="f5ca1-145">콘텐츠에 자동 적용 레이블이 할당된 경우 최종 사용자가 자동 적용 레이블을 수동 할당 보존 레이블로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-145">If content has an auto-apply label assigned, an auto-apply label can be replaced by a retention label assigned manually by an end user.</span></span>
    
- <span data-ttu-id="f5ca1-146">최종 사용자가 콘텐츠에 수동으로 보존 레이블을 할당한 경우 자동 적용 레이블로 수동 할당 보존 레이블을 대신할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-146">If content has a retention label assigned manually by an end user, an auto-apply label cannot replace the manually assigned retention label.</span></span>
    
- <span data-ttu-id="f5ca1-147">자동 적용 레이블을 할당하는 여러 규칙이 있고 콘텐츠가 여러 규칙의 조건을 충족하는 경우 가장 오래된 규칙에 대한 보존 레이블이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-147">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the retention label for the oldest rule is assigned.</span></span>
    
<span data-ttu-id="f5ca1-p109">수동으로 할당된 레이블은 명시적으로 할당되고, 자동 적용 레이블은 암시적으로 할당됩니다. 또한 명시적 보존 레이블은 암시적 레이블보다 우선합니다. 자세한 내용은 아래 섹션에서 [보존 원칙 또는 우선 순위](#the-principles-of-retention-or-what-takes-precedence)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p109">Manually assigned labels are explicitly assigned; auto-apply labels are implicitly assigned; an explicit retention label takes precedence over an implicit label. For more information, see the below section on [The principles of retention, or what takes precedence?](#the-principles-of-retention-or-what-takes-precedence).</span></span>

<span data-ttu-id="f5ca1-p110">이 섹션의 모든 정보는 보존 레이블에만 적용됩니다. 하나의 콘텐츠 항목에 보존 레이블 1개 외에 민감도 레이블이 1개만 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p110">All the information in this section applies only to retention labels. Note that an item of content can also have one sensitivity label applied to it, in addition to one retention label.</span></span>
  
## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="f5ca1-152">보존 레이블이 적용되는 데 걸리는 시간</span><span class="sxs-lookup"><span data-stu-id="f5ca1-152">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="f5ca1-153">보존 레이블을 게시하거나 자동 적용할 경우 즉시 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-153">When you publish or auto-apply retention labels, they don't take effect immediately:</span></span>
  
1. <span data-ttu-id="f5ca1-154">먼저 관리 센터에서 레이블 정책을 정책의 위치로 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-154">First the label policy needs to be synced from the admin center to the locations in the policy.</span></span>
    
2. <span data-ttu-id="f5ca1-155">그런 다음 위치에는 게시된 보존 레이블을 최종 사용자에게 제공하거나 레이블을 콘텐츠에 자동 적용하기 위한 시간이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-155">Then the location may require time to make published retention labels available to end users or time to auto-apply labels to content.</span></span> <span data-ttu-id="f5ca1-156">여기에 걸리는 시간은 보존 레이블의 위치와 유형에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-156">How long this takes depends on the location and type of retention label.</span></span>
    
### <a name="published-retention-labels"></a><span data-ttu-id="f5ca1-157">게시된 보존 레이블</span><span class="sxs-lookup"><span data-stu-id="f5ca1-157">Published retention labels</span></span>

<span data-ttu-id="f5ca1-p112">SharePoint 또는 OneDrive에 보존 레이블을 게시하면 해당 보존 레이블이 최종 사용자에 게 표시되기까지 하루가 걸릴 수 있습니다. 또한 보존 레이블을 Exchange에 게시하는 경우 해당 보존 레이블이 최종 사용자에게 표시되기까지 7일이 걸릴 수 있으며, 사서함에는 10MB 이상의 데이터가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p112">If you publish retention labels to SharePoint or OneDrive, it can take one day for those retention labels to appear for end users. In addition, if you publish retention labels to Exchange, it can take 7 days for those retention labels to appear for end users, and the mailbox needs to contain at least 10 MB of data.</span></span>
  
![수동 레이블이 적용되는 경우를 나타내는 다이어그램](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a><span data-ttu-id="f5ca1-161">보존 레이블 작동 적용</span><span class="sxs-lookup"><span data-stu-id="f5ca1-161">Auto-apply retention labels</span></span>

<span data-ttu-id="f5ca1-162">특정 조건과 일치하는 콘텐츠에 보존 레이블을 자동으로 적용하는 경우 보존 레이블이 조건과 일치하는 모든 기존 콘텐츠에 적용되는 데 7일이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-162">If you auto-apply retention labels to content matching specific conditions, it can take seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![자동 적용 레이블이 적용되는 경우를 나타내는 다이어그램](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a><span data-ttu-id="f5ca1-164">Exchange에 게시된 보존 레이블의 상태를 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="f5ca1-164">How to check on the status of retention labels published to Exchange</span></span>

<span data-ttu-id="f5ca1-p113">Exchange Online에서는 7일 간격으로 실행되는 프로세스를 통해 최종 사용자가 보존 레이블을 사용할 수 있게 됩니다. Powershell을 사용하여 이 프로세스가 마지막으로 실행된 시간 및 다시 실행될 시간을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p113">In Exchange Online, retention labels are made available to end users by a process that runs every seven days. By using Powershell, you can see when this process last ran and thus determine when it will run again.</span></span>
  
1. <span data-ttu-id="f5ca1-167">[Exchange Online PowerShell에 연결합니다](https://go.microsoft.com/fwlink/?linkid=799773).</span><span class="sxs-lookup"><span data-stu-id="f5ca1-167">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span></span>
    
2. <span data-ttu-id="f5ca1-168">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-168">Run these commands.</span></span>
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
   ```

<span data-ttu-id="f5ca1-169">결과에서 `ELCLastSuccessTimeStamp`(UTC) 속성은 시스템에서 사서함을 마지막으로 처리한 시간을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-169">In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox.</span></span> <span data-ttu-id="f5ca1-170">정책을 만든 이후로 이러한 처리가 발생하지 않은 경우 레이블은 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-170">If it has not happened since the time you created the policy, the labels are not going to appear.</span></span> <span data-ttu-id="f5ca1-171">강제로 처리하려면 `Start-ManagedFolderAssistant -Identity <user>`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-171">To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.</span></span>
    
<span data-ttu-id="f5ca1-172">웹용 Outlook에 레이블이 나타나야 하는데 나타나지 않으면 브라우저에서 캐시를 지워야 합니다(Ctrl + F5).</span><span class="sxs-lookup"><span data-stu-id="f5ca1-172">If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).</span></span>
    
## <a name="retention-label-policies-and-locations"></a><span data-ttu-id="f5ca1-173">보존 레이블 정책 및 위치</span><span class="sxs-lookup"><span data-stu-id="f5ca1-173">Retention label policies and locations</span></span>

<span data-ttu-id="f5ca1-174">보존 레이블이 수행하는 작업에 따라, 다양한 유형의 보존 레이블을 여러 다른 위치에 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-174">Different types of retention labels can be published to different locations, depending on what the retention label does.</span></span>
  
|<span data-ttu-id="f5ca1-175">**보존 레이블...**</span><span class="sxs-lookup"><span data-stu-id="f5ca1-175">**If the retention label is…**</span></span>|<span data-ttu-id="f5ca1-176">**레이블 정책을 적용할 수 있는 대상...**</span><span class="sxs-lookup"><span data-stu-id="f5ca1-176">**Then the label policy can be applied to…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f5ca1-177">최종 사용자에게 게시</span><span class="sxs-lookup"><span data-stu-id="f5ca1-177">Published to end users</span></span>  <br/> |<span data-ttu-id="f5ca1-178">Exchange, SharePoint, OneDrive, Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="f5ca1-178">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
|<span data-ttu-id="f5ca1-179">중요한 정보 유형에 따라 자동으로 적용</span><span class="sxs-lookup"><span data-stu-id="f5ca1-179">Auto-applied based on sensitive information types</span></span>  <br/> |<span data-ttu-id="f5ca1-180">Exchange(모든 사서함만), SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="f5ca1-180">Exchange (all mailboxes only), SharePoint, OneDrive</span></span>  <br/> |
|<span data-ttu-id="f5ca1-181">쿼리에 따라 자동 적용</span><span class="sxs-lookup"><span data-stu-id="f5ca1-181">Auto-applied based on a query</span></span>  <br/> |<span data-ttu-id="f5ca1-182">Exchange, SharePoint, OneDrive, Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="f5ca1-182">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
   
<span data-ttu-id="f5ca1-183">Exchange에서 자동 적용 보존 레이블(쿼리 및 중요한 정보 유형 모두에 대한)은 현재 사서함에 있는 모든 항목(미사용 데이터)이 아닌 새로 전송된 메시지(전송 중인 데이터)에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-183">In Exchange, auto-apply retention labels (for both queries and sensitive information types) are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest).</span></span> <span data-ttu-id="f5ca1-184">또한 민감한 정보 유형에 대한 자동 적용 보존 레이블은 모든 사서함에만 적용되며 특정 사서함을 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-184">Also, auto-apply retention labels for sensitive information types can apply only to all mailboxes; you can't select the specific mailboxes.</span></span>
  
<span data-ttu-id="f5ca1-185">Exchange 공용 폴더 및 Skype는 레이블을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-185">Exchange public folders and Skype do not support labels.</span></span>
  
## <a name="how-retention-labels-enforce-retention"></a><span data-ttu-id="f5ca1-186">보존 레이블이 보존을 적용하는 방법</span><span class="sxs-lookup"><span data-stu-id="f5ca1-186">How retention labels enforce retention</span></span>

<span data-ttu-id="f5ca1-187">보존 레이블은 보존 정책이 할 수 있는 것과 같은 보존 작업을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-187">Retention labels can enforce the same retention actions that a retention policy can.</span></span> <span data-ttu-id="f5ca1-188">보존 레이블을 사용하여 정교한 콘텐츠 계획(또는 파일 계획)을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-188">You can use retention labels to implement a sophisticated content plan (or file plan).</span></span> <span data-ttu-id="f5ca1-189">보존 작업이 작동하는 방법에 대한 자세한 내용은 [보존 정책 개요](retention-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-189">For more information on how retention works, see [Overview of retention policies](retention-policies.md).</span></span>
  
<span data-ttu-id="f5ca1-p117">또한 보존 레이블에는 보존 정책이 아니라 보존 레이블에서만 사용할 수 있는 2가지 보존 옵션이 있습니다. 보존 레이블을 사용하면 다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p117">In addition, a retention label has two retention options that are available only in a retention label and not in a retention policy. With a retention label, you can:</span></span>
  
- <span data-ttu-id="f5ca1-p118">SharePoint 및 OneDrive 문서가 삭제되기 전에 검토될 수 있도록 보존 기간이 끝나면 처리 검토를 트리거합니다. 자세한 내용은 [콘텐츠 처리](disposition.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p118">Trigger a disposition review at the end of the retention period, so that SharePoint and OneDrive documents must be reviewed before they can be deleted. For more information, see [Disposition of content](disposition.md).</span></span>
    
- <span data-ttu-id="f5ca1-194">보존 기간은 콘텐츠 사용 기간이나 마지막으로 수정되었을 때가 아니라 콘텐츠에 레이블이 지정될 때 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-194">Start the retention period from when the content was labeled, instead of the age of the content or when it was last modified.</span></span> <span data-ttu-id="f5ca1-195">해당 옵션은 SharePoint 사이트 및 OneDrive 계정의 콘텐츠에만 적용됨을 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-195">This option applies only to content in SharePoint sites and OneDrive accounts.</span></span> <span data-ttu-id="f5ca1-196">Exchange 전자 메일의 경우 보존 기간은 사용자가 선택한 옵션에 상관없이 항상 메시지를 보냈거나 받은 날짜를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-196">For Exchange email, the retention period is always based on the date when the message was sent or received, no matter which option you choose here.</span></span>
    
![레이블 관련 옵션이 있는 보존 설정](../media/c49118c9-6279-4661-94db-deffa76e27ac.png)
  
## <a name="where-published-retention-labels-can-appear-to-end-users"></a><span data-ttu-id="f5ca1-198">게시된 보존 레이블이 최종 사용자에게 표시될 수 있는 위치</span><span class="sxs-lookup"><span data-stu-id="f5ca1-198">Where published retention labels can appear to end users</span></span>

<span data-ttu-id="f5ca1-199">최종 사용자가 콘텐츠에 보존 레이블을 할당하면 해당 레이블을 다음에 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-199">If your retention label will be assigned to content by end users, you can publish it to:</span></span>
  
- <span data-ttu-id="f5ca1-200">웹용 Outlook</span><span class="sxs-lookup"><span data-stu-id="f5ca1-200">Outlook on the web</span></span>
    
- <span data-ttu-id="f5ca1-201">Outlook 2010 이상</span><span class="sxs-lookup"><span data-stu-id="f5ca1-201">Outlook 2010 and later</span></span>
    
- <span data-ttu-id="f5ca1-202">OneDrive</span><span class="sxs-lookup"><span data-stu-id="f5ca1-202">OneDrive</span></span>
    
- <span data-ttu-id="f5ca1-203">SharePoint</span><span class="sxs-lookup"><span data-stu-id="f5ca1-203">SharePoint</span></span>
    
- <span data-ttu-id="f5ca1-204">Microsoft 365 그룹(웹용 Outlook의 그룹 사이트 및 그룹 사서함)</span><span class="sxs-lookup"><span data-stu-id="f5ca1-204">Microsoft 365 groups (both the group site and group mailbox in Outlook on the web)</span></span>
    
<span data-ttu-id="f5ca1-205">아래 섹션에서는 다양한 앱에서 레이블이 조직의 사용자에게 표시되는 방식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-205">The sections that follow explain how labels appear in different apps to people in your organization.</span></span>
  
### <a name="outlook-on-the-web"></a><span data-ttu-id="f5ca1-206">웹용 Outlook</span><span class="sxs-lookup"><span data-stu-id="f5ca1-206">Outlook on the web</span></span>

<span data-ttu-id="f5ca1-207">웹용 Outlook에서 항목에 레이블을 지정하려면 마우스 오른쪽 단추로 항목 \> **정책 할당**을 클릭하고 \> 보존 레이블을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-207">To label an item in Outlook on the web, right-click the item \> **Assign policy** \> choose the retention label.</span></span> 
  
![웹용 Outlook의 정책 할당 메뉴](../media/146a23cf-e478-4595-b2e8-f707fc4e6ea3.png)
  
<span data-ttu-id="f5ca1-p120">해당 보존 레이블이 적용된 후에는 항목 맨 위에서 해당 보존 레이블과 수행되는 작업을 볼 수 있습니다. 전자 메일 분류되고 연결된 보존 기간이 있으면 전자 메일이 만료될 시기를 한눈에 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p120">After the retention label is applied, you can view that retention label and what action it takes at the top of the item. If an email is classified and has an associated retention period, you can know at a glance when the email will expire.</span></span>
  
![웹용 Outlook에서 전자 메일에 할당된 레이블](../media/16f6c91b-5eab-4574-9d13-6d12be00a783.png)
  
<span data-ttu-id="f5ca1-212">폴더에 보존 레이블을 적용할 수도 있습니다. 이러한 경우 다음을 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-212">You can also apply retention labels to folders, in which case:</span></span>
  
- <span data-ttu-id="f5ca1-p121">보존 레이블이 명시적으로 적용된 항목을 **제외**하고 폴더의 모든 항목에는 자동으로 같은 보존 레이블이 지정됩니다. 명시적으로 레이블이 지정된 항목은 기존 보존 레이블이 유지됩니다. 자세한 내용은 아래에서 보존 원칙에 대한 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p121">All items in the folder automatically get the same retention label, **except** for items that have had a retention label applied explicitly to them. Explicitly labeled items keep their existing retention label. For more information, see the below section on the principles of retention.</span></span> 
    
- <span data-ttu-id="f5ca1-216">폴더의 기본 보존 레이블을 변경하거나 제거하는 경우 명시적 보존 레이블이 지정된 항목을 **제외**하고 폴더의 모든 항목에 대해서도 보존 레이블이 변경되거나 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-216">If you change or remove the default retention label for a folder, the retention label's also changed or removed for all items in the folder, **except** items with explicit retention labels.</span></span> 
    
- <span data-ttu-id="f5ca1-217">기본 보존 레이블이 있는 항목을 한 폴더에서 다른 기본 보존 레이블이 있는 다른 폴더로 이동하면 항목에 새 기본 보존 레이블이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-217">If you move an item with a default retention label from one folder to another folder with a different default retention label, the item gets the new default retention label.</span></span>
    
- <span data-ttu-id="f5ca1-218">기본 보존 레이블이 있는 항목을 한 폴더에서 기본 보존 레이블이 없는 다른 폴더로 이동하면 이전의 기본 보존 레이블이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-218">If you move an item with a default retention label from one folder to another folder with no default retention label, the old default retention label is removed.</span></span>
    
### <a name="outlook-2010-and-later"></a><span data-ttu-id="f5ca1-219">Outlook 2010 이상</span><span class="sxs-lookup"><span data-stu-id="f5ca1-219">Outlook 2010 and later</span></span>

<span data-ttu-id="f5ca1-220">Outlook 데스크톱 클라이언트에서 항목에 레이블을 지정하려면 해당 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-220">To label an item in the Outlook desktop client, select the item.</span></span> <span data-ttu-id="f5ca1-221">리본 메뉴의 **홈** 탭에서 **정책 할당**을 클릭한 다음, 보존 레이블을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-221">On the **Home** tab on the ribbon, click **Assign Policy**, and then choose the retention label.</span></span> 
  
![정책 할당 단추](../media/30684dea-dd73-4e4a-9185-8e29f403b6ca.png)
  
<span data-ttu-id="f5ca1-223">항목을 마우스 오른쪽 단추로 클릭하고, 상황에 맞는 메뉴에서 **정책 할당**를 클릭한 다음, 보존 레이블을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-223">You can also right-click an item, click **Assign Policy** in the context menu, and then choose the retention label.</span></span> 

<span data-ttu-id="f5ca1-224">보존 레이블이 적용된 후 항목 맨 위에서 해당 보존 레이블과 해당 레이블이 수행하는 작업을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-224">After the retention label is applied, you can view that retention label and what action it takes at the top of the item.</span></span> <span data-ttu-id="f5ca1-225">연결된 보존 기간이 있는 보존 레이블이 전자 메일에 적용된 경우, 해당 전자 메일이 만료되는 시간을 한눈에 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-225">If an email has a retention label applied that has an associated retention period, you can see at a glance when the email expires.</span></span>
  
<span data-ttu-id="f5ca1-226">폴더에 보존 레이블을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-226">You can also apply retention labels to folders.</span></span> <span data-ttu-id="f5ca1-227">이 내용은 웹용 Outlook에서와 마찬가지로 Outlook 2010 이상에서도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-227">This works the same in Outlook 2010 and later as it does in Outlook on the web.</span></span> <span data-ttu-id="f5ca1-228">자세한 내용은 이전 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-228">See the previous section for more info.</span></span>
  
### <a name="onedrive-and-sharepoint"></a><span data-ttu-id="f5ca1-229">OneDrive 및 SharePoint</span><span class="sxs-lookup"><span data-stu-id="f5ca1-229">OneDrive and SharePoint</span></span>

<span data-ttu-id="f5ca1-230">OneDrive 또는 SharePoint에서 문서(OneNote 파일 포함)에 레이블을 지정하려면 오른쪽 위 모서리에서 항목 \>을 선택하고 **세부 정보 창 열기**![정보 창 아이콘](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **보존 레이블 적용**을 선택한 후 \> 보존 레이블을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-230">To label a document (including OneNote files) in OneDrive or SharePoint, select the item \> in the upper-right corner, choose **Open the details pane**![Information pane icon](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **Apply retention label** \> choose the retention label.</span></span> 
  
<span data-ttu-id="f5ca1-231">폴더 또는 문서 집합에 보존 레이블을 적용할 수도 있으며, 문서 라이브러리에 대해 기본 보존 레이블을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-231">You can also apply a retention label to a folder or document set, and you can set a default retention label for a document library.</span></span> <span data-ttu-id="f5ca1-232">자세한 내용은 아래 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-232">See the section below for more information.</span></span>
  
![SharePoint의 항목에 대해 레이블 목록 적용](../media/151cc83c-da57-45b0-9cd1-fd2f28a31083.png)
  
<span data-ttu-id="f5ca1-234">항목에 보존 레이블이 적용된 후에는 항목을 선택하면 세부 정보 창에서 해당 레이블을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-234">After a retention label is applied to an item, you can view it in the details pane when that item's selected.</span></span>
  
![세부 정보 창에 표시되는 적용된 레이블](../media/d06e585e-29f7-4c8c-afef-629c97268b8e.png)
  
<span data-ttu-id="f5ca1-p126">**레이블** 열 또는 **기록 항목임** 열이 포함된 라이브러리의 보기를 만들 수도 있습니다. 이 경우 모든 항목에 할당된 보존 레이블과 기록에 해당하는 항목을 한눈에 확인할 수 있습니다. 그렇지만 **기록 항목임** 열을 기준으로는 보기를 필터링할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p126">You can also create a view of the library that contains the **Labels** column or **Item is a Record** column, so that you can see at a glance the retention labels assigned to all items and which items are records. Note, however, that you can't filter the view by the **Item is a Record** column.</span></span> 
  
![사용자 지정 보기에 표시된 레이블에 대한 라이브러리 열](../media/e3392627-c0a3-405e-bb57-55f27c34cfdd.png)
  
### <a name="microsoft-365-groups"></a><span data-ttu-id="f5ca1-239">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="f5ca1-239">Microsoft 365 Groups</span></span>

<span data-ttu-id="f5ca1-p127">Microsoft 365 그룹에 보존 레이블을 게시하면 웹용 Outlook의 그룹 사이트와 그룹 사서함에 보존 레이블에 나타납니다. 콘텐츠에 보존 레이블을 적용하는 환경은 전자 메일 및 문서에 대해 위에 표시된 환경과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p127">When you publish retention labels to a Microsoft 365 group, the retention labels appear in both the group site and group mailbox in Outlook on the web. The experience of applying a retention label to content is identical to that shown above for email and documents.</span></span>

<span data-ttu-id="f5ca1-p128">Microsoft 365 그룹 콘텐츠를 보존하려면 Microsoft 365 그룹 위치를 사용해야 합니다. Microsoft 365 그룹이 Exchange 사서함을 보유하고 있더라도 전체 Exchange 위치를 포함하는 보존 정책이 Microsoft 365 그룹 사서함의 콘텐츠를 포함하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p128">To retain content for a Microsoft 365 group, you need to use the Microsoft 365 Groups location. Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire Exchange location won't include content in Microsoft 365 group mailboxes.</span></span>

<span data-ttu-id="f5ca1-244">또한 Exchange 위치를 사용하여 특정 그룹 사서함을 포함하거나 제외할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-244">In addition, it's not possible to use the Exchange location to include or exclude a specific group mailbox.</span></span> <span data-ttu-id="f5ca1-245">초기에 Exchange 위치가 선택될 그룹 사서함을 허용하더라도 보존 정책을 저장하려고 시도할 때 “RemoteGroupMailbox”가 Exchange 위치에 유효하지 않은 선택이라는 오류가 나타나게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-245">Although the Exchange location initially allows a group mailbox to be selected, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span>
  
## <a name="applying-a-retention-label-automatically-based-on-conditions"></a><span data-ttu-id="f5ca1-246">조건에 따라 자동으로 보존 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="f5ca1-246">Applying a retention label automatically based on conditions</span></span>

<span data-ttu-id="f5ca1-247">보존 레이블의 가장 강력한 기능 중 하나는 특정 조건과 일치하는 콘텐츠에 자동으로 레이블을 적용하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-247">One of the most powerful features of retention labels is the ability to apply them automatically to content that matches certain conditions.</span></span> <span data-ttu-id="f5ca1-248">이 경우 조직의 사용자는 레이블을 적용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-248">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="f5ca1-249">Microsoft 365에서 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-249">Microsoft 365 does the work for them.</span></span>
  
![자동 적용 레이블의 역할 및 작업 다이어그램](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)
  
<span data-ttu-id="f5ca1-251">자동 적용 보존 레이블은 다음과 같은 기능 때문에 강력합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-251">Auto-apply retention labels are powerful because:</span></span>
  
- <span data-ttu-id="f5ca1-252">사용자에게 모든 분류를 교육할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-252">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="f5ca1-253">모든 콘텐츠를 올바르게 분류하기 위해 사용자에게 의존할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-253">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="f5ca1-254">사용자가 더 이상 데이터 거버넌스 정책을 알아야 할 필요가 없으며, 업무에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-254">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="f5ca1-255">콘텐츠에 다음이 포함될 경우 콘텐츠에 자동으로 보존 레이블을 적용하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-255">You can choose to apply retention labels to content automatically when that content contains:</span></span>
  
- [<span data-ttu-id="f5ca1-256">특정 중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="f5ca1-256">Specific types of sensitive information</span></span>](#auto-apply-retention-labels-to-content-with-specific-types-of-sensitive-information)
    
- [<span data-ttu-id="f5ca1-257">만든 쿼리와 일치하는 특정 키워드</span><span class="sxs-lookup"><span data-stu-id="f5ca1-257">Specific keywords that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="f5ca1-258">학습 가능한 분류자와 일치</span><span class="sxs-lookup"><span data-stu-id="f5ca1-258">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifers)
    
![자동 적용 레이블에 대한 조건 페이지 선택](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

<span data-ttu-id="f5ca1-260">구성한 조건과 일치하는 모든 콘텐츠에 자동 적용 보존 레이블을 적용하는 데 최대 7일이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-260">It can take up to seven days for auto-apply retention labels to be applied to all content that matches the conditions you've configured.</span></span>
  
> [!TIP]
> <span data-ttu-id="f5ca1-261">SharePont에서 관리 속성을 사용하여 보존 레이블을 자동 적용하고 이벤트 중심 보존을 구현하는 방법에 대한 자세한 시나리오는 [보존 레이블로 SharePoint 문서의 수명 주기 관리](auto-apply-retention-labels-scenario.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-261">See [Manage the lifecycle of SharePoint documents with retention labels](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="auto-apply-retention-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="f5ca1-262">특정 유형의 중요한 정보가 있는 콘텐츠에 보존 레이블 자동 적용</span><span class="sxs-lookup"><span data-stu-id="f5ca1-262">Auto-apply retention labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="f5ca1-263">중요한 정보에 대한 자동 적용 보존 레이블을 만들면 DLP(데이터 손실 방지) 정책을 만들 때 같은 정책 템플릿 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-263">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="f5ca1-264">각 정책 템플릿은 특정 중요한 정보 유형을 찾도록 미리 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-264">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="f5ca1-265">예를 들어, 여기에 표시된 템플릿은 미국 ITIN, SSN 및 여권 번호를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-265">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="f5ca1-266">DLP에 대한 자세한 내용은 [데이터 손실 방지 정책 개요](data-loss-prevention-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-266">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![중요한 정보 유형을 갖는 정책 템플릿](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="f5ca1-p132">정책 템플릿을 선택한 후 임의 유형의 중요한 정보를 추가하거나 제거하고, 인스턴스 수 및 일치 정확도를 변경할 수 있습니다. 여기에 표시된 예제에서는 다음 경우에만 보존 레이블이 자동 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p132">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="f5ca1-p133">콘텐츠에 이러한 세 가지 중요한 정보 유형 중 어느 하나의 1~9개 인스턴스가 포함되어 있습니다. **max** 값을 삭제하여 **any**로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p133">The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="f5ca1-p134">검색된 중요한 정보 유형은 75 이상의 일치 정확도(또는 신뢰도)를 갖습니다. 많은 중요한 정보 유형은 여러 패턴으로 정의되고, 일치 정확도가 더 높은 패턴에서는 더 많은 증거(예: 키워드, 날짜 또는 주소)가 검색되어야 합니다. 일치 정확도가 더 낮은 패턴은 증거가 덜 요구합니다. 간단히 말해서 **min** 일치 정확도가 더 낮을수록 콘텐츠가 조건과 일치하기가 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p134">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75. Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence. Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="f5ca1-275">이 옵션에 대한 자세한 내용은 [더 쉽게 또는 더 어렵게 일치하도록 규칙 조정](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-275">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![중요한 정보 유형을 식별하기 위한 옵션](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="f5ca1-277">키워드 또는 검색 가능 속성이 있는 콘텐츠에 레이블 자동 적용</span><span class="sxs-lookup"><span data-stu-id="f5ca1-277">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="f5ca1-p135">특정 조건을 충족하는 콘텐츠에 레이블을 자동으로 적용할 수 있습니다. 현재 사용 가능한 조건은 특정 단어, 구 또는 검색 가능 속성 값을 포함하는 콘텐츠에만 레이블을 적용하도록 지원합니다. AND, OR 및 NOT과 같은 검색 연산자를 사용하여 쿼리를 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p135">You can auto-apply labels to content that satisfies certain conditions. The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="f5ca1-281">쿼리 구문에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-281">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="f5ca1-282">KQL(키워드 쿼리 언어) 구문 참조</span><span class="sxs-lookup"><span data-stu-id="f5ca1-282">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="f5ca1-p136">쿼리 기반 레이블은 검색 인덱스를 사용하여 콘텐츠를 식별합니다. 유효한 검색 가능 속성에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p136">Query-based labels use the search index to identify content. For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="f5ca1-285">콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건</span><span class="sxs-lookup"><span data-stu-id="f5ca1-285">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="f5ca1-286">SharePoint Server에서 크롤링 및 관리 속성의 개요</span><span class="sxs-lookup"><span data-stu-id="f5ca1-286">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="f5ca1-287">예제 쿼리:</span><span class="sxs-lookup"><span data-stu-id="f5ca1-287">Examples queries:</span></span>

- <span data-ttu-id="f5ca1-288">Exchange</span><span class="sxs-lookup"><span data-stu-id="f5ca1-288">Exchange</span></span>
    - <span data-ttu-id="f5ca1-289">subject:"Quarterly Financials"</span><span class="sxs-lookup"><span data-stu-id="f5ca1-289">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="f5ca1-290">recipients:garthf</span><span class="sxs-lookup"><span data-stu-id="f5ca1-290">recipients:garthf</span></span><!--nolink--><span data-ttu-id="f5ca1-291">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5ca1-291">@contoso.com</span></span>
- <span data-ttu-id="f5ca1-292">SharePoint 및 비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="f5ca1-292">SharePoint and OneDrive for Business</span></span>
    - <span data-ttu-id="f5ca1-293">contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="f5ca1-293">contenttype:contract</span></span>
    - <span data-ttu-id="f5ca1-294">site:https</span><span class="sxs-lookup"><span data-stu-id="f5ca1-294">site:https</span></span><!--nolink--><span data-ttu-id="f5ca1-295">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="f5ca1-295">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![쿼리 편집기](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


### <a name="auto-apply-labels-to-content-by-using-trainable-classifers"></a><span data-ttu-id="f5ca1-297">학습 가능한 분류자를 사용하여 콘텐츠에 레이블 자동 적용</span><span class="sxs-lookup"><span data-stu-id="f5ca1-297">Auto-apply labels to content by using trainable classifers</span></span>

<span data-ttu-id="f5ca1-298">학습 가능한 분류자 옵션을 선택할 때 기본 분류자 중 하나 또는 사용자 지정 분류자를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-298">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="f5ca1-299">기본 분류자에는 **공격 언어**, **이력서**, **소스 코드**, **대상 희롱**, **비속어** 및 **위협**이 포함됩니다:</span><span class="sxs-lookup"><span data-stu-id="f5ca1-299">The built-in classifiers include **Offensive Language**, **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![학습 가능한 분류자 선택](../media/retention-label-classifers.png)

<span data-ttu-id="f5ca1-301">이 옵션을 사용하여 레이블을 자동으로 적용하려면 SharePoint Online 사이트 및 사서함에 10MB 이상의 데이터가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-301">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="f5ca1-302">학습 가능한 분류자에 대한 자세한 내용은 [학습 가능한 분류자 시작(미리 보기)](classifier-getting-started-with.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-302">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="f5ca1-303">구성 예는 [분류자를 준비하고 기본 제공 분류자를 사용하는 방법](classifier-using-a-ready-to-use-classifier.md#how-to-prepare-for-and-use-a-built-in-classifier)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-303">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-prepare-for-and-use-a-built-in-classifier).</span></span>


## <a name="applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set"></a><span data-ttu-id="f5ca1-304">SharePoint 라이브러리, 폴더 또는 문서 집합의 모든 콘텐츠에 기본 보존 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="f5ca1-304">Applying a default retention label to all content in a SharePoint library, folder, or document set</span></span>

<span data-ttu-id="f5ca1-305">사용자가 개별 문서에 보존 레이블을 적용할 수 있도록 하는 것 외에, SharePoint 라이브러리, 폴더 또는 문서 집합의 모든 문서에 기본 보존 레이블이 적용되도록 해당 위치에 기본 보존 레이블을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-305">In addition to enabling people to apply a retention label to individual documents, you can also apply a default retention label to a SharePoint library, folder, or document set, so that all documents in that location get the default retention label.</span></span>
  
<span data-ttu-id="f5ca1-306">문서 라이브러리의 경우 이 작업은 문서 라이브러리의 **라이브러리 설정** 페이지에서 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-306">For a document library, this is done on the **Library settings** page for a document library.</span></span> <span data-ttu-id="f5ca1-307">기본 보존 레이블을 선택하는 경우 라이브러리의 기존 항목에 적용하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-307">When you choose the default retention label, you can also choose to apply it to existing items in the library.</span></span> 
  
<span data-ttu-id="f5ca1-308">예를 들어 마케팅 자료에 대한 태그가 있고 특정 문서 라이브러리에 해당 유형의 콘텐츠만 포함된다는 것을 알 경우 마케팅 자료 태그를 해당 라이브러리의 모든 문서에 대한 기본 태그로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-308">For example, if you have a tag for marketing materials, and you know a specific document library contains only that type of content, you can make the Marketing Materials tag the default for all documents in that library.</span></span>
  
![라이브러리 설정 페이지의 레이블 적용 옵션](../media/0787d651-63dc-43b4-8768-716a5ecc64ec.png)
  
<span data-ttu-id="f5ca1-310">라이브러리, 폴더 또는 문서 집합의 기존 항목에 기본 보존 레이블을 적용하는 경우 다음 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-310">If you apply a default retention label to existing items in the library, folder, or document set:</span></span>
  
- <span data-ttu-id="f5ca1-311">명시적으로 적용된 보존 레이블이 있는 항목(예: 레코드)의 경우를 **제외하고** 라이브러리, 폴더 또는 문서의 모든 항목에 자동으로 같은 보존 레이블이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-311">All items in the library, folder, or document set automatically get the same retention label, **except** for items that have had a retention label applied explicitly to them (such as records).</span></span> <span data-ttu-id="f5ca1-312">명시적으로 레이블이 지정된 항목은 기존 레이블을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-312">Explicitly labeled items keep their existing label.</span></span> <span data-ttu-id="f5ca1-313">자세한 내용은 [보존 원칙 또는 우선 순위](#the-principles-of-retention-or-what-takes-precedence)에 대한 아래 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-313">For more information, see the below section on [The principles of retention, or what takes precedence](#the-principles-of-retention-or-what-takes-precedence).</span></span>
    
- <span data-ttu-id="f5ca1-314">라이브러리, 폴더 또는 문서 집합의 기본 보존 레이블을 변경하거나 제거하는 경우 명시적 보존 레이블이 지정된 항목(예: 레코드)을 **제외하고** 라이브러리, 폴더 또는 문서 집합의 모든 항목에 대해서도 보존 레이블이 변경되거나 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-314">If you change or remove the default retention label for a library, folder, or document set, the retention label is also changed or removed for all items in the library, folder, or document set, **except** items with explicit retention labels (such as records).</span></span>
    
- <span data-ttu-id="f5ca1-315">한 사이트 컬렉션, 라이브러리, 폴더 또는 문서 집합에서 기본 보존 레이블이 있는 항목을 다른 사이트 컬렉션, 라이브러리, 폴더 또는 다른 레이블이 있는 문서 집합으로 이동하면 새 위치에 다른 기본 보존 레이블이 있더라도 해당 항목은 기존의 기본 보존 레이블을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-315">If you move an item with a default retention label from one site collection, library, folder, or document set to another site collection, library, folder, or document set that has a different label, the item keeps its existing default retention label, even if the new location has a different default retention label.</span></span> <span data-ttu-id="f5ca1-316">항목을 이동하기 전에 레이블이 없으면 새 위치의 기본 보존 레이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-316">If the item does not have a label before moving, it will take on the default retention label of the new location.</span></span>

<span data-ttu-id="f5ca1-317">**레코드:** 라이브러리, 폴더 또는 문서 집합에 기본 레코드 레이블을 적용하면 해당 위치 내의 모든 개별 항목에 레코드 레이블이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-317">**Records:** If you apply a default record label to a library, folder, or document set, then a record label is applied to all the individual items within those locations.</span></span> <span data-ttu-id="f5ca1-318">새 항목을 레코드 레이블을 사용하여 위치로 이동하면 해당 항목에 레코드 레이블이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-318">When you move a new item into a location with a record label, that item is labeled a record.</span></span> <span data-ttu-id="f5ca1-319">그러나 콘텐츠를 레코드로 선언하지 않는 레이블로 기본 보존 레이블을 변경하는 경우 해당 작업은 개별 항목에서 레코드 레이블을 제거하지 **않습니다**. 해당 항목은 레코드 레이블을 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-319">However, if you change the default retention label to a label that doesn't declare content as a record, that action **does not** remove the record label from the individual items; those items retain their record label.</span></span> <span data-ttu-id="f5ca1-320">사이트 모음 관리자는 레코드 항목의 보존 레이블을 명시적으로 제거하거나 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-320">Only a site collection admin can explicitly remove or change the retention label of record items.</span></span>

<span data-ttu-id="f5ca1-321">콘텐츠를 레코드로 선언하는 보존 레이블에 대한 자세한 내용은 [레코드 개요](records.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-321">For more information about retention labels that declare content as a record, see [Overview of records](records.md).</span></span>
    
## <a name="applying-a-retention-label-to-email-by-using-rules"></a><span data-ttu-id="f5ca1-322">규칙을 사용하여 전자 메일에 보존 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="f5ca1-322">Applying a retention label to email by using rules</span></span>

<span data-ttu-id="f5ca1-323">Outlook 2010 이상에서는 보존 레이블 또는 보존 정책을 적용하는 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-323">In Outlook 2010 or later, you can create rules to apply a retention label or retention policy.</span></span>
  
<span data-ttu-id="f5ca1-324">예를 들어, 특정 메일 그룹에서 보내고 받은 모든 메시지에 특정 보존 레이블을 적용하는 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-324">For example, you can create a rule that applies a specific retention label to all messages sent to or from a specific distribution group.</span></span>
  
<span data-ttu-id="f5ca1-325">규칙을 만들려면 마우스 오른쪽 단추로 항목 \> **규칙** \> **규칙 만들기** \> **고급 옵션** \> **규칙 마법사** \> **보존 정책 적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-325">To create a rule, right-click an item \> **Rules** \> **Create Rule** \> **Advanced Options** \> **Rules Wizard** \> **apply retention policy**.</span></span>
  
![보존 정책을 적용하는 옵션이 포함된 규칙 마법사](../media/eeb2407c-15b6-4224-99cf-e0a00034d8ea.png)
  
## <a name="classifying-content-without-applying-any-actions"></a><span data-ttu-id="f5ca1-327">작업을 적용하지 않고 콘텐츠 분류</span><span class="sxs-lookup"><span data-stu-id="f5ca1-327">Classifying content without applying any actions</span></span>

<span data-ttu-id="f5ca1-p142">보존 레이블을 만들 때 아래에 표시된 것처럼 보존이나 기타 작업을 설정하지 않고 그대로 만들 수 있습니다. 이 경우 작업을 적용하지 않고 보존 레이블을 단순히 텍스트 레이블로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p142">When you create a retention label, you can do so without turning on any retention or other actions, as shown below. In this case, you can use a retention label simply as a text label, without enforcing any actions.</span></span>
  
<span data-ttu-id="f5ca1-330">예를 들어, 작업 없이 “나중에 검토”라는 보존 레이블을 만든 다음, 해당 보존 레이블을 중요한 정보 유형을 갖는 콘텐츠 또는 쿼리된 콘텐츠에 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-330">For example, you can create a retention label named "Review later" with no actions, and then auto-apply that retention label to content with sensitive information types or queried content.</span></span>
  
![보존이 해제된 레이블 설정 페이지](../media/17ce863b-a823-426e-aaad-83718465f762.png)
  
## <a name="using-retention-labels-for-records-management"></a><span data-ttu-id="f5ca1-332">기록 관리에 보존 레이블 사용</span><span class="sxs-lookup"><span data-stu-id="f5ca1-332">Using retention labels for records management</span></span>
    
<span data-ttu-id="f5ca1-333">보존 레이블을 사용하여 콘텐츠를 레코드로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-333">You can use retention labels to declare content as a record.</span></span> <span data-ttu-id="f5ca1-334">따라서 Office 365에서 일관된 단일 레코드 관리 전략을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-334">This lets you implement a single, consistent records-management strategy across Office 365.</span></span> <span data-ttu-id="f5ca1-335">자세한 내용은 [레코드 개요](records.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-335">For more information, see [Overview of records](records.md).</span></span>
  
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="f5ca1-336">보존 레이블을 DLP 정책의 조건으로 사용</span><span class="sxs-lookup"><span data-stu-id="f5ca1-336">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="f5ca1-p144">보존 레이블은 콘텐츠에 보존 작업을 적용할 수 있습니다. 또한 보존 레이블을 DLP(데이터 손실 방지) 정책의 조건으로 사용할 수 있고, DLP 정책은 특정 레이블이 있는 콘텐츠에 대해 액세스 제한과 같은 기타 작업을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p144">A retention label can enforce retention actions on content. In addition, you can use a retention label as a condition in a data loss prevention (DLP) policy, and the DLP policy can enforce other actions, such as restricting access, on content that contains a specific label.</span></span> 
  
<span data-ttu-id="f5ca1-339">자세한 내용은 [보존 레이블을 DLP 정책의 조건으로 사용하기](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-339">For more information, see [Using a retention label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>
  
## <a name="monitor-retention-labels"></a><span data-ttu-id="f5ca1-340">보존 레이블 모니터링</span><span class="sxs-lookup"><span data-stu-id="f5ca1-340">Monitor retention labels</span></span>

<span data-ttu-id="f5ca1-p145">보존 레이블을 게시하거나 자동으로 적용한 후에 의도대로 콘텐츠에 적용되는지 확인할 수 있습니다. 보존 레이블을 모니터링하려면 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p145">After you publish or auto-apply your retention labels, you'll want to verify that they're being applied to content as you intended. To monitor your retention labels, you can use the:</span></span>
  
- <span data-ttu-id="f5ca1-p146">**레이블 활동 탐색기**. 이 탐색기(아래 그림 참조)를 사용하면 지난 30일 동안 SharePoint 및 비즈니스용 OneDrive에서 사용된 모든 콘텐츠를 빠르게 검색하고 해당 보존 레이블 활동을 볼 수 있습니다. 자세한 내용은 [문서에 대한 레이블 활동 보기](view-label-activity-for-documents.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p146">**Label Activity Explorer**. With the explorer (shown below), you can quickly search and view retention label activity for all content across SharePoint and OneDrive for Business over the past 30 days. For more information, see [View label activity for documents](view-label-activity-for-documents.md).</span></span>

- <span data-ttu-id="f5ca1-346">**레이블 분석** 페이지.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-346">**Label analytics** page.</span></span> <span data-ttu-id="f5ca1-347">Microsoft 365 규정 준수 센터 및 Microsoft 365 보안 센터에서 빠르게 상단 레이블 및 레이블이 적용된 위치를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-347">In the Microsoft 365 compliance center and Microsoft 365 security center, you can quickly view your top labels and where they're applied.</span></span> <span data-ttu-id="f5ca1-348">특정 레이블이 포함된 모든 콘텐츠를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-348">You can also view all content with a specific label.</span></span> <span data-ttu-id="f5ca1-349">자세한 내용은 [레이블 분석을 사용한 레이블 사용량 보기](label-analytics.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-349">For more information, see [View label usage with label analytics](label-analytics.md).</span></span>
    
- <span data-ttu-id="f5ca1-p148">**데이터 거버넌스 보고서**. 이러한 보고서를 사용하면 지난 90일 동안 Exchange, SharePoint 및 비즈니스용 OneDrive에서 사용된 모든 콘텐츠에 대한 보존 레이블 추세 및 활동을 빠르게 확인할 수 있습니다. 자세한 내용은 [데이터 거버넌스 보고서 보기](view-the-data-governance-reports.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p148">**Data governance reports**. With these reports, you can quickly view retention label trends and activity for all content across Exchange, SharePoint, and OneDrive for Business over the past 90 days. For more information, see [View the data governance reports](view-the-data-governance-reports.md).</span></span>
    
![레이블 활동 탐색기](../media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it"></a><span data-ttu-id="f5ca1-354">콘텐츠 검색을 사용하여 특정 보존 레이블이 적용된 모든 콘텐츠 찾기</span><span class="sxs-lookup"><span data-stu-id="f5ca1-354">Using Content Search to find all content with a specific retention label applied to it</span></span>

<span data-ttu-id="f5ca1-355">사용자가 콘텐츠에 보존 레이블을 할당하거나 레이블이 자동 적용된 후에 콘텐츠 검색을 사용하여 특정 보존 레이블로 분류된 모든 콘텐츠를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-355">After retention labels are assigned to content, either by users or auto-applied, you can use content search to find all content that's classified with a specific retention label.</span></span>
  
<span data-ttu-id="f5ca1-p149">콘텐츠 검색을 만들 때 **준수 태그** 조건을 선택한 후 전체 레이블 이름 또는 레이블 이름 일부를 입력하고 와일드카드를 사용합니다. 자세한 내용은 [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p149">When you create a content search, choose the **Compliance Tag** condition, and then enter the complete label name or part of the label name and use a wildcard. For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
![준수 태그 조건](../media/82d6af16-59f8-462f-babb-c894b2917018.png)
  
## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="f5ca1-359">보존 원칙 또는 우선 순위</span><span class="sxs-lookup"><span data-stu-id="f5ca1-359">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="f5ca1-p150">콘텐츠에 각기 다른 작업(보존, 삭제 또는 둘 다) 및 보존 기간을 지정하는 여러 보존 정책이 적용될 수 있습니다. 우선 순위는 어떨까요? 분명한 것은 가장 높은 수준에서 한 정책을 통해 보존되는 콘텐츠가 다른 정책에 의해 영구적으로 삭제될 수 없다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p150">It's possible or even likely that content might have several retention policies applied to it, each with a different action (retain, delete, or both) and retention period. What takes precedence? At the highest level, rest assured that content being retained by one policy can't be permanently deleted by another policy.</span></span>
  
![보존 원칙 다이어그램](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
<span data-ttu-id="f5ca1-364">보존 작업이 있는 여러 다른 레이블이 콘텐츠에 적용되는 방식을 이해하려면 다음과 같은 보존 원칙에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-364">To understand how different labels with retention actions are applied to content, keep these principles of retention in mind:</span></span>
  
1. <span data-ttu-id="f5ca1-p151">**보존이 삭제보다 우선합니다.** 한 보존 정책은 3년 후에 Exchange 전자 메일을 삭제하도록 지정하지만 다른 보존 정책은 5년 동안 Exchange 전자 메일을 보존했다가 삭제하도록 지정하는 경우를 가정해보세요. 3년에 도달한 모든 콘텐츠는 삭제되고 사용자가 볼 수 없게 숨겨지지만, 5년에 도달할 때까지 복구 가능한 항목 폴더에 보존되었다가 영구적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p151">**Retention wins over deletion.** Suppose that one retention policy says to delete Exchange email after three years, but another retention policy says to retain Exchange email for five years and then delete it. Any content that reaches three years old will be deleted and hidden from the users' view, but still retained in the Recoverable Items folder until the content reaches five years old, when it will be permanently deleted.</span></span> 
    
2. <span data-ttu-id="f5ca1-p152">**가장 긴 보존 기간이 우선합니다.** 콘텐츠에 여러 콘텐츠 보존 정책이 적용되는 경우 가장 긴 보존 기간이 끝날 때까지 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p152">**The longest retention period wins.** If content's subject to multiple policies that retain content, it will be retained until the end of the longest retention period.</span></span> 
    
3. <span data-ttu-id="f5ca1-p153">**명시적 포함이 암시적 포함보다 우선합니다.** 이것은 다음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p153">**Explicit inclusion wins over implicit inclusion.** This means:</span></span> 
    
    1. <span data-ttu-id="f5ca1-372">보존 설정이 포함된 보존 레이블이 사용자에 의해 수동으로 항목(예: Exchange 전자 메일 또는 OneDrive 문서)에 할당된 경우 해당 보존 레이블은 사이트 또는 사서함 수준에서 할당된 정책이나 문서 라이브러리에 의해 할당된 기본 보존 레이블보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-372">If a retention label with retention settings is manually assigned by a user to an item, such as an Exchange email or OneDrive document, that retention label takes precedence over both a policy assigned at the site or mailbox level and a default retention label assigned by the document library.</span></span> <span data-ttu-id="f5ca1-373">예를 들어 명시적 보존 레이블에서 10년 동안 보존하라고 하지만, 사이트에 할당된 보존 정책에서 5년 동안만 보존하라고 한다면 보존 레이블이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-373">For example, if the explicit retention label says to retain for 10 years, but the retention policy assigned to the site says to retain for only five years, the retention label takes precedence.</span></span> <span data-ttu-id="f5ca1-374">자동 적용 보존 레이블은 Office 365에 의해 자동으로 적용되므로 명시적이 아니라 암시적으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-374">Auto-applied retention labels are considered implicit, not explicit, because they're applied automatically by Office 365.</span></span>
    
    2. <span data-ttu-id="f5ca1-375">보존 정책에 특정 사용자의 사서함 또는 OneDrive용 비즈니스 계정과 같은 특정 위치가 포함되는 경우 해당 정책이 모든 사용자의 사서함 또는 비즈니스용 OneDrive 계정에 적용되지만 해당 사용자의 사서함을 특별히 포함하지 않는 다른 보존 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-375">If a retention policy includes a specific location, such as a specific user's mailbox or OneDrive for Business account, that policy takes precedence over another retention policy that applies to all users' mailboxes or OneDrive for Business accounts but doesn't specifically include that user's mailbox.</span></span>
    
4. <span data-ttu-id="f5ca1-p155">**가장 짧은 삭제 기간이 우선적으로 적용됩니다.** 마찬가지로 콘텐츠에 여러 콘텐츠 삭제 정책이 적용되는 경우(보존 없음) 가장 짧은 보존 기간이 끝나면 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p155">**The shortest deletion period wins.** Similarly, if content's subject to multiple policies that delete content (with no retention), it will be deleted at the end of the shortest retention period.</span></span> 
    
<span data-ttu-id="f5ca1-378">보존 원칙은 위에서 아래로 균형을 깨는 흐름처럼 작동한다는 점을 이해하도록 합니다. 모든 정책 또는 레이블에 의해 적용되는 규칙이 하나의 수준에서 동일한 경우 규칙이 적용되는 우선 순위를 결정하기 위해 흐름은 아래의 다음 수준으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-378">Understand that the principles of retention work as a tie-breaking flow from top to bottom: If the rules applied by all policies or labels are the same at one level, the flow moves down to the next level to determine precedence for which rule is applied.</span></span>
  
<span data-ttu-id="f5ca1-p156">마지막으로, 보존 정책 또는 레이블은 eDiscovery 보류 상태인 콘텐츠를 영구적으로 삭제할 수 없습니다. 보류가 해제되면 다시 위에 설명된 정리 프로세스가 해당 콘텐츠에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p156">Finally, a retention policy or label cannot permanently delete any content that's on hold for eDiscovery. When the hold is released, the content again becomes eligible for the cleanup process described above.</span></span>

### <a name="precedence-for-auto-labeling-with-trainable-classifiers"></a><span data-ttu-id="f5ca1-381">학습 가능한 분류 기준을 사용한 자동 레이블링 우선 순위</span><span class="sxs-lookup"><span data-stu-id="f5ca1-381">Precedence for auto-labeling with trainable classifiers</span></span>

<span data-ttu-id="f5ca1-382">학습 가능한 분류 기준으로 구성된 모든 보존 레이블이 동시에 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-382">All retention labels that are configured for trainable classifiers are evaluated simultaneously.</span></span> <span data-ttu-id="f5ca1-383">교육 가능한 분류 기준이 둘 이상인 항목이 감지되면 다음 기준을 사용하여 적용할 보존 레이블을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-383">If an item is detected by more than one trainable classifier, the following criteria is used to determine which retention label to apply:</span></span>

1. <span data-ttu-id="f5ca1-384">유지 전용 또는 유지 및 삭제용으로 구성된 보존 레이블은 삭제 전용으로 구성된 보존 레이블보다 우선 순위가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-384">Retention labels configured for retain-only or retain and then delete have a higher priority over retention labels that are configured for delete-only.</span></span>

2. <span data-ttu-id="f5ca1-385">보존 전용 또는 보존 및 삭제용으로 구성된 보존 레이블의 경우 가장 긴 보존 기간 동안 구성된 보존 레이블이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-385">For retention labels that are configured for retain-only or retain and then delete, the retention label that is configured for the longest retention period wins.</span></span>

3. <span data-ttu-id="f5ca1-386">삭제 전용으로 구성된 보존 레이블의 경우 가장 짧은 기간 동안 구성된 보존 레이블이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-386">For retention labels that are configured for delete-only, the retention label that has been configured for the shortest period wins.</span></span>

4. <span data-ttu-id="f5ca1-387">동작과 기간이 같은 보존 레이블에는 유지되는 보존 레이블 선택이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-387">Retention labels with the same action and the same period result in a retention label selection that is non-deterministic.</span></span>

## <a name="use-retention-labels-instead-of-these-features"></a><span data-ttu-id="f5ca1-388">이러한 기능 대신 보존 레이블 사용</span><span class="sxs-lookup"><span data-stu-id="f5ca1-388">Use retention labels instead of these features</span></span>

<span data-ttu-id="f5ca1-p158">보존 레이블은 Exchange, SharePoint, OneDrive 및 Microsoft 365 그룹을 포함하여 Office 365의 전체 조직 및 해당 콘텐츠에서 쉽게 사용할 수 있습니다. Microsoft 365의 임의 위치에서 콘텐츠를 분류하거나 기록을 관리해야 하는 경우 보존 레이블을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p158">Retention labels can easily be made available to an entire organization and its content across Office 365, including Exchange, SharePoint, OneDrive, and Microsoft 365 Groups. If you need to classify content or manage records anywhere in Microsoft 365, we recommend that you use retention labels.</span></span>
  
<span data-ttu-id="f5ca1-391">이전에 Office 365에서 콘텐츠를 분류하거나 레코드를 관리하는 데 사용된 다른 여러 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-391">There are several other features that have previously been used to classify content or manage records in Office 365.</span></span> <span data-ttu-id="f5ca1-392">이러한 기능은 아래에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-392">These are listed below.</span></span> <span data-ttu-id="f5ca1-393">이러한 기능은 보존 레이블과 함께 계속해서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-393">These features will continue to work side by side with retention labels.</span></span> <span data-ttu-id="f5ca1-394">보존 레이블 구현이 이전 기능과 다른 경우가 있기는 하지만, 보존 레이블이 발전하면서 앞으로 Office 365에서 레코드를 더 편리하게 관리할 수 있게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-394">While there are instances where the implementation of retention labels differs from previous features, the evolution of retention labels will drive the future of records management across Office 365.</span></span> <span data-ttu-id="f5ca1-395">따라서 앞으로 데이터 거버넌스의 경우 이러한 기능 대신 보존 레이블을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-395">Therefore, moving forward, for data governance, we recommend that you use retention labels instead of these features.</span></span>
  
### <a name="exchange-online"></a><span data-ttu-id="f5ca1-396">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f5ca1-396">Exchange Online</span></span>

- <span data-ttu-id="f5ca1-397">[보존 태그 및 보존 정책](https://go.microsoft.com/fwlink/?linkid=846125)[[MRM(메시징 기록 관리)라고도 함]](https://go.microsoft.com/fwlink/?linkid=846126)(삭제만 해당)</span><span class="sxs-lookup"><span data-stu-id="f5ca1-397">[Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (Deletion only)</span></span> 
    
### <a name="sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="f5ca1-398">SharePoint Online 및 비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="f5ca1-398">SharePoint Online and OneDrive for Business</span></span>

- <span data-ttu-id="f5ca1-399">[ 현재 위치 기록 관리 구성](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a)(보존)</span><span class="sxs-lookup"><span data-stu-id="f5ca1-399">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (Retention)</span></span> 
    
- <span data-ttu-id="f5ca1-400">[기록 센터 소개](https://support.office.com/article/bae6ca5a-7b19-40e0-b433-e3613a747c2c) (보존)</span><span class="sxs-lookup"><span data-stu-id="f5ca1-400">[Introduction to the Records Center](https://support.office.com/article/bae6ca5a-7b19-40e0-b433-e3613a747c2c) (Retention)</span></span> 
    
- <span data-ttu-id="f5ca1-401">[정보 관리 정책](intro-to-info-mgmt-policies.md)(삭제만 해당)</span><span class="sxs-lookup"><span data-stu-id="f5ca1-401">[Information management policies](intro-to-info-mgmt-policies.md) (Deletion only)</span></span> 
    
## <a name="permissions"></a><span data-ttu-id="f5ca1-402">권한</span><span class="sxs-lookup"><span data-stu-id="f5ca1-402">Permissions</span></span>

<span data-ttu-id="f5ca1-403">보존 레이블을 만드는 규정 준수 팀의 구성원은 보안 및 준수 센터에 대한 사용 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-403">Members of your compliance team who will create retention labels need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="f5ca1-404">기본적으로 테넌트 관리자는 이 위치에 액세스할 수 있으며, 준수 관리자 및 기타 사용자에게 테넌트 관리를 위한 모든 권한을 부여하지는 않으면서, 보안 및 준수 센터에 대한 액세스 권한을 부여할 수 있습니다. 이렇게 하기 위해 보안 및 준수 센터의 **권한** 페이지로 이동한 후 **준수 관리자** 역할 그룹을 편집하고 해당 역할 그룹에 구성원을 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-404">By default, your tenant admin has access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security &amp; Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span> 
  
<span data-ttu-id="f5ca1-405">자세한 내용은 [사용자에게 보안 &amp; 준수 센터에 대한 액세스 권한 부여하기](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-405">For more information, see [Give users access to the Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="f5ca1-p161">이러한 정책은 보존 레이블 및 레이블 정책을 만들고 적용하는 데만 필요합니다. 정책 적용을 위해서는 콘텐츠에 액세스하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-p161">These permissions are required only to create and apply retention labels and a label policy. Policy enforcement does not require access to the content.</span></span>  
## <a name="find-the-powershell-cmdlets-for-labels"></a><span data-ttu-id="f5ca1-408">레이블에 대한 PowerShell cmdlet 찾기</span><span class="sxs-lookup"><span data-stu-id="f5ca1-408">Find the PowerShell cmdlets for labels</span></span>

<span data-ttu-id="f5ca1-409">레이블 cmdlet을 사용하려면 다음 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-409">To use the label cmdlets, you need to:</span></span>
  
1. [<span data-ttu-id="f5ca1-410">보안 및 준수 센터 PowerShell에 연결하기</span><span class="sxs-lookup"><span data-stu-id="f5ca1-410">Connect to the Security & Compliance Center Powershell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. <span data-ttu-id="f5ca1-411">다음 보안 및 준수 센터 cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ca1-411">Use these Security & Compliance Center cmdlets:</span></span>

  - [<span data-ttu-id="f5ca1-412">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="f5ca1-412">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetag)

  - [<span data-ttu-id="f5ca1-413">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="f5ca1-413">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-compliancetag)

  - [<span data-ttu-id="f5ca1-414">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="f5ca1-414">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-compliancetag)

  - [<span data-ttu-id="f5ca1-415">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="f5ca1-415">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-compliancetag)

  - [<span data-ttu-id="f5ca1-416">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="f5ca1-416">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/enable-compliancetagstorage)

  - [<span data-ttu-id="f5ca1-417">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="f5ca1-417">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetagstorage)

  - [<span data-ttu-id="f5ca1-418">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="f5ca1-418">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy)

  - [<span data-ttu-id="f5ca1-419">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="f5ca1-419">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy)

  - [<span data-ttu-id="f5ca1-420">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="f5ca1-420">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy)

  - [<span data-ttu-id="f5ca1-421">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="f5ca1-421">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy)

  - [<span data-ttu-id="f5ca1-422">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="f5ca1-422">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule)

  - [<span data-ttu-id="f5ca1-423">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="f5ca1-423">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule)

  - [<span data-ttu-id="f5ca1-424">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="f5ca1-424">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule)

  - [<span data-ttu-id="f5ca1-425">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="f5ca1-425">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule)
