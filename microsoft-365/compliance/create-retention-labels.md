---
title: 보존 레이블 만들기, 게시 및 자동 적용
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
description: Office 365 환경에서 필요한 사항은 보존하고 필요하지 않은 사항은 삭제하기 위해 보존 레이블을 만들고, 게시하고 자동 적용하기 위한 지침입니다.
ms.openlocfilehash: 4a9343ddfe07bbc4bf535759a39268915fd83ca1
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352245"
---
# <a name="create-publish-and-auto-apply-retention-labels"></a><span data-ttu-id="ed5b1-103">보존 레이블 만들기, 게시 및 자동 적용</span><span class="sxs-lookup"><span data-stu-id="ed5b1-103">Create, publish, and auto-apply retention labels</span></span>

><span data-ttu-id="ed5b1-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="ed5b1-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="ed5b1-105">다음 정보를 사용하여 [보존 레이블](labels.md)을 만드는 데 도움을 받은 후, 보존 레이블을 문서 및 전자 메일에 자동으로 적용하거나 사용자가 수동으로 적용할 수 있도록 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-105">Use the following information to help you create [retention labels](labels.md), and then automatically apply them to documents and emails, or publish them so that users can manually apply them.</span></span>

<span data-ttu-id="ed5b1-106">보존 레이블은 필요한 사항은 보존하고 필요하지 않은 사항은 삭제하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-106">Retention labels help you retain what you need and delete what you don't.</span></span> <span data-ttu-id="ed5b1-107">또한 Microsoft 365 데이터에 대한 [레코드 관리](records-management.md) 솔루션의 일부로 항목을 레코드로 선언하는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-107">They are also used to declare an item as a record as part of a [records management](records-management.md) solution for your Microsoft 365 data.</span></span>

<span data-ttu-id="ed5b1-108">보존 레이블을 만들고 구성하는 위치는 레코드 관리를 사용 중인지 여부에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-108">Where you create and configure your retention labels depend on whether you're using records management or not.</span></span> <span data-ttu-id="ed5b1-109">두 시나리오 모두에 대한 지침이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-109">Instructions are provided for both scenarios.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ed5b1-110">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="ed5b1-110">Before you begin</span></span>

<span data-ttu-id="ed5b1-111">보존 레이블을 만드는 규정 준수 팀의 구성원은 보안 및 준수 센터에 대한 사용 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-111">Members of your compliance team who will create retention labels need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="ed5b1-112">기본적으로 테넌트 관리자는 이 위치에 액세스할 수 있으며, 준수 관리자 및 기타 사용자에게 테넌트 관리를 위한 모든 권한을 부여하지는 않으면서, 보안 및 준수 센터에 대한 액세스 권한을 부여할 수 있습니다. 이렇게 하기 위해 보안 및 준수 센터의 **권한** 페이지로 이동한 후 **준수 관리자** 역할 그룹을 편집하고 해당 역할 그룹에 구성원을 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-112">By default, your tenant admin has access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security &amp; Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span> 
  
<span data-ttu-id="ed5b1-113">자세한 내용은 [사용자에게 Office 365 보안 및 준수 센터에 대한 액세스 권한 부여](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-113">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="ed5b1-p104">이러한 정책은 보존 레이블 및 레이블 정책을 만들고 적용하는 데만 필요합니다. 정책 적용을 위해서는 콘텐츠에 액세스하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-p104">These permissions are required only to create and apply retention labels and a label policy. Policy enforcement does not require access to the content.</span></span>

## <a name="create-and-configure-retention-labels"></a><span data-ttu-id="ed5b1-116">보존 레이블 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="ed5b1-116">Create and configure retention labels</span></span>

1. <span data-ttu-id="ed5b1-117">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 다음의 위치 중 한 곳으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-117">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="ed5b1-118">레코드 관리를 사용하는 경우:</span><span class="sxs-lookup"><span data-stu-id="ed5b1-118">If you are using records management:</span></span>
        - <span data-ttu-id="ed5b1-119">**솔루션** > **레코드 관리** > **파일 계획** 탭 > **+ 레이블 만들기** > **보존 레이블**</span><span class="sxs-lookup"><span data-stu-id="ed5b1-119">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="ed5b1-120">레코드 관리를 사용하지 않는 경우:</span><span class="sxs-lookup"><span data-stu-id="ed5b1-120">If you are not using records management:</span></span>
       - <span data-ttu-id="ed5b1-121">**솔루션** > **정보 관리** > **레이블** tab > + **레이블 만들기**</span><span class="sxs-lookup"><span data-stu-id="ed5b1-121">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="ed5b1-122">바로 옵션이 표시되지 않나요?</span><span class="sxs-lookup"><span data-stu-id="ed5b1-122">Don't immediately see your option?</span></span> <span data-ttu-id="ed5b1-123">먼저 **모두 표시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-123">First select **Show all**.</span></span> 

2. <span data-ttu-id="ed5b1-124">마법사의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-124">Follow the prompts in the wizard.</span></span> <span data-ttu-id="ed5b1-125">레코드 관리를 사용하는 경우:</span><span class="sxs-lookup"><span data-stu-id="ed5b1-125">If you are using records management:</span></span>
    
    - <span data-ttu-id="ed5b1-126">파일 계획 설명자에 대한 자세한 내용은 [파일 계획 관리자의 개요](file-plan-manager.md)를 참조하세요</span><span class="sxs-lookup"><span data-stu-id="ed5b1-126">For information about the file plan descriptors, see [Overview of file plan manager](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="ed5b1-127">보존 레이블을 사용하여 콘텐츠를 레코드로 선언하려면 **레이블을 사용하여 콘텐츠를 “기록”으로 분류** 확인란을 체크합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-127">To use the retention label to declare content as a record, enable the checkbox **Use label to classify content as a "Record"**.</span></span>

3. <span data-ttu-id="ed5b1-128">이 단계를 반복하여 레이블을 더 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-128">Repeat these steps to create more labels.</span></span>

<span data-ttu-id="ed5b1-129">기존 레이블을 편집하려면 레이블을 선택하고 **레이블 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-129">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="ed5b1-130">그러면 2단계에서 레이블 설명과 설정을 변경할 수 있는 동일한 마법사가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-130">This starts the same wizard, which lets you change the label descriptions and settings in step 2.</span></span>

## <a name="publish-retention-labels-by-creating-a-retention-label-policy"></a><span data-ttu-id="ed5b1-131">보존 레이블 정책을 만들어 보존 레이블 게시</span><span class="sxs-lookup"><span data-stu-id="ed5b1-131">Publish retention labels by creating a retention label policy</span></span>

<span data-ttu-id="ed5b1-132">보존 레이블을 게시하여 사용자가 수동으로 적용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-132">Publish retention labels so that they can be manually applied by users.</span></span>

1. <span data-ttu-id="ed5b1-133">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 다음의 위치 중 한 곳으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-133">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="ed5b1-134">레코드 관리를 사용하는 경우:</span><span class="sxs-lookup"><span data-stu-id="ed5b1-134">If you are using records management:</span></span>
        - <span data-ttu-id="ed5b1-135">**솔루션** > **레코드 관리** > > **레이블 정책** 탭 > **레이블 게시**</span><span class="sxs-lookup"><span data-stu-id="ed5b1-135">**Solutions** > **Records management** > > **Label policies** tab > **Publish labels**</span></span>
    
    - <span data-ttu-id="ed5b1-136">레코드 관리를 사용하지 않는 경우:</span><span class="sxs-lookup"><span data-stu-id="ed5b1-136">If you are not using records management:</span></span>
        - <span data-ttu-id="ed5b1-137">**솔루션** > **정보 관리** > **레이블 정책** 탭 > **레이블 게시**</span><span class="sxs-lookup"><span data-stu-id="ed5b1-137">**Solutions** > **Information governance** > **Label policies** tab > **Publish labels**</span></span>
    
    <span data-ttu-id="ed5b1-138">바로 옵션이 표시되지 않나요?</span><span class="sxs-lookup"><span data-stu-id="ed5b1-138">Don't immediately see your option?</span></span> <span data-ttu-id="ed5b1-139">먼저 **모두 표시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-139">First select **Show all**.</span></span> 

2. <span data-ttu-id="ed5b1-140">마법사의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-140">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="ed5b1-141">위치를 구성하는 방법에 대한 자세한 내용은 이 페이지에서 [보존 레이블과 위치](#retention-labels-and-locations) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-141">For information about configuring the locations, see the [Retention labels and locations](#retention-labels-and-locations) section on this page.</span></span> 

## <a name="auto-apply-a-retention-label"></a><span data-ttu-id="ed5b1-142">보존 레이블 작동 적용</span><span class="sxs-lookup"><span data-stu-id="ed5b1-142">Auto-apply a retention label</span></span>

<span data-ttu-id="ed5b1-143">사용자가 지정한 조건을 기반으로 보존 레이블을 자동으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-143">Auto-apply a retention label, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="ed5b1-144">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 다음의 위치 중 한 곳으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-144">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="ed5b1-145">레코드 관리를 사용하는 경우: **정보 거버넌스**</span><span class="sxs-lookup"><span data-stu-id="ed5b1-145">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="ed5b1-146">**솔루션** > **레코드 관리** > **레이블 정책** 탭 > **레이블 자동 적용**</span><span class="sxs-lookup"><span data-stu-id="ed5b1-146">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply label**</span></span>
    
    - <span data-ttu-id="ed5b1-147">레코드 관리를 사용하지 않는 경우:</span><span class="sxs-lookup"><span data-stu-id="ed5b1-147">If you are not using records management:</span></span>
        - <span data-ttu-id="ed5b1-148">**솔루션** > **정보 거버넌스** > **레이블 정책** 탭 > **레이블 자동 적용**</span><span class="sxs-lookup"><span data-stu-id="ed5b1-148">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply label**</span></span>
    
    <span data-ttu-id="ed5b1-149">바로 옵션이 표시되지 않나요?</span><span class="sxs-lookup"><span data-stu-id="ed5b1-149">Don't immediately see your option?</span></span> <span data-ttu-id="ed5b1-150">먼저 **모두 표시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-150">First select **Show all**.</span></span> 

2. <span data-ttu-id="ed5b1-151">마법사의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-151">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="ed5b1-152">보존 레이블을 자동으로 적용하는 조건을 구성하는 방법에 대한 자세한 내용은이 페이지에서 [보존 레이블 자동 적용에 대한 조건 구성하기](#configuring-conditions-for-auto-apply-retention-labels) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-152">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="ed5b1-153">위치를 구성하는 방법에 대한 자세한 내용은 이 페이지의 다음 섹션 [보존 레이블과 위치](#retention-labels-and-locations)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-153">For information about configuring the locations, see the next section on this page, [Retention labels and locations](#retention-labels-and-locations).</span></span>

## <a name="retention-labels-and-locations"></a><span data-ttu-id="ed5b1-154">보존 레이블 및 위치</span><span class="sxs-lookup"><span data-stu-id="ed5b1-154">Retention labels and locations</span></span>

<span data-ttu-id="ed5b1-155">보존 레이블이 수행하는 작업에 따라, 다양한 유형의 보존 레이블을 여러 다른 위치에 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-155">Different types of retention labels can be published to different locations, depending on what the retention label does.</span></span>
  
|<span data-ttu-id="ed5b1-156">**보존 레이블...**</span><span class="sxs-lookup"><span data-stu-id="ed5b1-156">**If the retention label is…**</span></span>|<span data-ttu-id="ed5b1-157">**레이블 정책을 적용할 수 있는 대상...**</span><span class="sxs-lookup"><span data-stu-id="ed5b1-157">**Then the label policy can be applied to…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ed5b1-158">최종 사용자에게 게시</span><span class="sxs-lookup"><span data-stu-id="ed5b1-158">Published to end users</span></span>  <br/> |<span data-ttu-id="ed5b1-159">Exchange, SharePoint, OneDrive, Office 365 그룹</span><span class="sxs-lookup"><span data-stu-id="ed5b1-159">Exchange, SharePoint, OneDrive, Office 365 groups</span></span>  <br/> |
|<span data-ttu-id="ed5b1-160">중요한 정보 유형에 따라 자동으로 적용</span><span class="sxs-lookup"><span data-stu-id="ed5b1-160">Auto-applied based on sensitive information types</span></span>  <br/> |<span data-ttu-id="ed5b1-161">Exchange(모든 사서함만), SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="ed5b1-161">Exchange (all mailboxes only), SharePoint, OneDrive</span></span>  <br/> |
|<span data-ttu-id="ed5b1-162">쿼리에 따라 자동 적용</span><span class="sxs-lookup"><span data-stu-id="ed5b1-162">Auto-applied based on a query</span></span>  <br/> |<span data-ttu-id="ed5b1-163">Exchange, SharePoint, OneDrive, Office 365 그룹</span><span class="sxs-lookup"><span data-stu-id="ed5b1-163">Exchange, SharePoint, OneDrive, Office 365 groups</span></span>  <br/> |
   
<span data-ttu-id="ed5b1-164">Exchange에서 자동 적용 보존 레이블(쿼리 및 중요한 정보 유형 모두에 대한)은 현재 사서함에 있는 모든 항목(미사용 데이터)이 아닌 새로 전송된 메시지(전송 중인 데이터)에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-164">In Exchange, auto-apply retention labels (for both queries and sensitive information types) are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest).</span></span> <span data-ttu-id="ed5b1-165">또한 민감한 정보 유형에 대한 자동 적용 보존 레이블은 모든 사서함에만 적용되며 특정 사서함을 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-165">Also, auto-apply retention labels for sensitive information types can apply only to all mailboxes; you can't select the specific mailboxes.</span></span>
  
<span data-ttu-id="ed5b1-166">Exchange 공용 폴더와 Skype는 보존 레이블을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-166">Exchange public folders and Skype do not support retention labels.</span></span>


## <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="ed5b1-167">보존 레이블 자동 적용에 대한 조건 구성하기</span><span class="sxs-lookup"><span data-stu-id="ed5b1-167">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="ed5b1-168">콘텐츠에 다음이 포함될 경우, 콘텐츠에 자동으로 보존 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-168">You can apply retention labels to content automatically when that content contains:</span></span>
  
- [<span data-ttu-id="ed5b1-169">특정 중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="ed5b1-169">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)
    
- [<span data-ttu-id="ed5b1-170">만든 쿼리와 일치하는 특정 키워드</span><span class="sxs-lookup"><span data-stu-id="ed5b1-170">Specific keywords that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="ed5b1-171">학습 가능한 분류자와 일치</span><span class="sxs-lookup"><span data-stu-id="ed5b1-171">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![자동 적용 레이블에 대한 조건 페이지 선택](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

<span data-ttu-id="ed5b1-173">구성한 조건과 일치하는 모든 콘텐츠에 자동 적용 보존 레이블을 적용하는 데 최대 7일이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-173">It can take up to seven days for auto-apply retention labels to be applied to all content that matches the conditions you've configured.</span></span>

### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="ed5b1-174">특정 유형의 중요한 정보가 있는 콘텐츠에 레이블 자동 적용</span><span class="sxs-lookup"><span data-stu-id="ed5b1-174">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="ed5b1-175">중요한 정보에 대한 자동 적용 보존 레이블을 만들면 DLP(데이터 손실 방지) 정책을 만들 때 같은 정책 템플릿 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-175">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="ed5b1-176">각 정책 템플릿은 특정 중요한 정보 유형을 찾도록 미리 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-176">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="ed5b1-177">예를 들어, 여기에 표시된 템플릿은 미국 ITIN, SSN 및 여권 번호를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-177">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="ed5b1-178">DLP에 대한 자세한 내용은 [데이터 손실 방지 정책 개요](data-loss-prevention-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-178">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![중요한 정보 유형을 갖는 정책 템플릿](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="ed5b1-p112">정책 템플릿을 선택한 후 임의 유형의 중요한 정보를 추가하거나 제거하고, 인스턴스 수 및 일치 정확도를 변경할 수 있습니다. 여기에 표시된 예제에서는 다음 경우에만 보존 레이블이 자동 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-p112">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="ed5b1-p113">콘텐츠에 이러한 세 가지 중요한 정보 유형 중 어느 하나의 1~9개 인스턴스가 포함되어 있습니다. **max** 값을 삭제하여 **any**로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-p113">The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="ed5b1-p114">검색된 중요한 정보 유형은 75 이상의 일치 정확도(또는 신뢰도)를 갖습니다. 많은 중요한 정보 유형은 여러 패턴으로 정의되고, 일치 정확도가 더 높은 패턴에서는 더 많은 증거(예: 키워드, 날짜 또는 주소)가 검색되어야 합니다. 일치 정확도가 더 낮은 패턴은 증거가 덜 요구합니다. 간단히 말해서 **min** 일치 정확도가 더 낮을수록 콘텐츠가 조건과 일치하기가 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-p114">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75. Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence. Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="ed5b1-187">이 옵션에 대한 자세한 내용은 [더 쉽게 또는 더 어렵게 일치하도록 규칙 조정](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-187">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![중요한 정보 유형을 식별하기 위한 옵션](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="ed5b1-189">키워드 또는 검색 가능 속성이 있는 콘텐츠에 레이블 자동 적용</span><span class="sxs-lookup"><span data-stu-id="ed5b1-189">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="ed5b1-p115">특정 조건을 충족하는 콘텐츠에 레이블을 자동으로 적용할 수 있습니다. 현재 사용 가능한 조건은 특정 단어, 구 또는 검색 가능 속성 값을 포함하는 콘텐츠에만 레이블을 적용하도록 지원합니다. AND, OR 및 NOT과 같은 검색 연산자를 사용하여 쿼리를 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-p115">You can auto-apply labels to content that satisfies certain conditions. The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="ed5b1-193">쿼리 구문에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-193">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="ed5b1-194">KQL(키워드 쿼리 언어) 구문 참조</span><span class="sxs-lookup"><span data-stu-id="ed5b1-194">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="ed5b1-p116">쿼리 기반 레이블은 검색 인덱스를 사용하여 콘텐츠를 식별합니다. 유효한 검색 가능 속성에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-p116">Query-based labels use the search index to identify content. For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="ed5b1-197">콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건</span><span class="sxs-lookup"><span data-stu-id="ed5b1-197">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="ed5b1-198">SharePoint Server에서 크롤링 및 관리 속성의 개요</span><span class="sxs-lookup"><span data-stu-id="ed5b1-198">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="ed5b1-199">예제 쿼리:</span><span class="sxs-lookup"><span data-stu-id="ed5b1-199">Examples queries:</span></span>

- <span data-ttu-id="ed5b1-200">Exchange</span><span class="sxs-lookup"><span data-stu-id="ed5b1-200">Exchange</span></span>
    - <span data-ttu-id="ed5b1-201">subject:"Quarterly Financials"</span><span class="sxs-lookup"><span data-stu-id="ed5b1-201">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="ed5b1-202">recipients:garthf</span><span class="sxs-lookup"><span data-stu-id="ed5b1-202">recipients:garthf</span></span><!--nolink--><span data-ttu-id="ed5b1-203">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ed5b1-203">@contoso.com</span></span>
- <span data-ttu-id="ed5b1-204">SharePoint 및 OneDrive</span><span class="sxs-lookup"><span data-stu-id="ed5b1-204">SharePoint and OneDrive</span></span>
    - <span data-ttu-id="ed5b1-205">contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="ed5b1-205">contenttype:contract</span></span>
    - <span data-ttu-id="ed5b1-206">site:https</span><span class="sxs-lookup"><span data-stu-id="ed5b1-206">site:https</span></span><!--nolink--><span data-ttu-id="ed5b1-207">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="ed5b1-207">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![쿼리 편집기](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="ed5b1-209">학습 가능한 분류자를 사용하여 콘텐츠에 레이블 자동 적용</span><span class="sxs-lookup"><span data-stu-id="ed5b1-209">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="ed5b1-210">학습 가능한 분류자 옵션을 선택할 때 기본 분류자 중 하나 또는 사용자 지정 분류자를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-210">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="ed5b1-211">기본 제공 분류자에는 **이력서**, **SourceCode**, **대상 희롱**, **비속어**, **위협**이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-211">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![학습 가능한 분류자 선택](../media/retention-label-classifers.png)

<span data-ttu-id="ed5b1-213">이 옵션을 사용하여 레이블을 자동으로 적용하려면 SharePoint Online 사이트 및 사서함에 10MB 이상의 데이터가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-213">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="ed5b1-214">학습 가능한 분류자에 대한 자세한 내용은 [학습 가능한 분류자 시작(미리 보기)](classifier-getting-started-with.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-214">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="ed5b1-215">구성 예는 [분류자를 준비하고 기본 제공 분류자를 사용하는 방법](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-215">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="ed5b1-216">보존 레이블이 적용되는 데 걸리는 시간</span><span class="sxs-lookup"><span data-stu-id="ed5b1-216">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="ed5b1-217">보존 레이블을 게시하거나 자동 적용할 경우 즉시 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-217">When you publish or auto-apply retention labels, they don't take effect immediately:</span></span>
  
1. <span data-ttu-id="ed5b1-218">먼저 관리 센터에서 레이블 정책을 정책의 위치로 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-218">First the label policy needs to be synced from the admin center to the locations in the policy.</span></span>
    
2. <span data-ttu-id="ed5b1-219">그런 다음 위치에서는 게시된 보존 레이블을 최종 사용자에게 제공하거나 레이블을 콘텐츠에 자동 적용하기 위한 시간이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-219">Then the location might require time to make published retention labels available to end users or time to auto-apply labels to content.</span></span> <span data-ttu-id="ed5b1-220">여기에 걸리는 시간은 보존 레이블의 위치와 유형에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-220">How long this takes depends on the location and type of retention label.</span></span>
    
### <a name="published-retention-labels"></a><span data-ttu-id="ed5b1-221">게시된 보존 레이블</span><span class="sxs-lookup"><span data-stu-id="ed5b1-221">Published retention labels</span></span>

<span data-ttu-id="ed5b1-p119">SharePoint 또는 OneDrive에 보존 레이블을 게시하면 해당 보존 레이블이 최종 사용자에 게 표시되기까지 하루가 걸릴 수 있습니다. 또한 보존 레이블을 Exchange에 게시하는 경우 해당 보존 레이블이 최종 사용자에게 표시되기까지 7일이 걸릴 수 있으며, 사서함에는 10MB 이상의 데이터가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-p119">If you publish retention labels to SharePoint or OneDrive, it can take one day for those retention labels to appear for end users. In addition, if you publish retention labels to Exchange, it can take 7 days for those retention labels to appear for end users, and the mailbox needs to contain at least 10 MB of data.</span></span>
  
![수동 레이블이 적용되는 경우를 나타내는 다이어그램](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a><span data-ttu-id="ed5b1-225">보존 레이블 작동 적용</span><span class="sxs-lookup"><span data-stu-id="ed5b1-225">Auto-apply retention labels</span></span>

<span data-ttu-id="ed5b1-226">특정 조건과 일치하는 콘텐츠에 보존 레이블을 자동으로 적용하는 경우 보존 레이블이 조건과 일치하는 모든 기존 콘텐츠에 적용되는 데 7일이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-226">If you auto-apply retention labels to content matching specific conditions, it can take seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![자동 적용 레이블이 적용되는 경우를 나타내는 다이어그램](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a><span data-ttu-id="ed5b1-228">Exchange에 게시된 보존 레이블의 상태를 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="ed5b1-228">How to check on the status of retention labels published to Exchange</span></span>

<span data-ttu-id="ed5b1-p120">Exchange Online에서는 7일 간격으로 실행되는 프로세스를 통해 최종 사용자가 보존 레이블을 사용할 수 있게 됩니다. Powershell을 사용하여 이 프로세스가 마지막으로 실행된 시간 및 다시 실행될 시간을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-p120">In Exchange Online, retention labels are made available to end users by a process that runs every seven days. By using Powershell, you can see when this process last ran and thus determine when it will run again.</span></span>
  
1. <span data-ttu-id="ed5b1-231">[Exchange Online PowerShell에 연결합니다](https://go.microsoft.com/fwlink/?linkid=799773).</span><span class="sxs-lookup"><span data-stu-id="ed5b1-231">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span></span>
    
2. <span data-ttu-id="ed5b1-232">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-232">Run these commands.</span></span>
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
   ```

<span data-ttu-id="ed5b1-233">결과에서 `ELCLastSuccessTimeStamp`(UTC) 속성은 시스템에서 사서함을 마지막으로 처리한 시간을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-233">In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox.</span></span> <span data-ttu-id="ed5b1-234">정책을 만든 이후로 이러한 처리가 발생하지 않은 경우 레이블은 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-234">If it has not happened since the time you created the policy, the labels are not going to appear.</span></span> <span data-ttu-id="ed5b1-235">강제로 처리하려면 `Start-ManagedFolderAssistant -Identity <user>`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-235">To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.</span></span>
    
<span data-ttu-id="ed5b1-236">웹용 Outlook에 레이블이 나타나야 하는데 나타나지 않으면 브라우저에서 캐시를 지워야 합니다(Ctrl + F5).</span><span class="sxs-lookup"><span data-stu-id="ed5b1-236">If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).</span></span>
    

## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="ed5b1-237">보존 레이블과 해당 정책 업데이트하기</span><span class="sxs-lookup"><span data-stu-id="ed5b1-237">Updating retention labels and their policies</span></span>

<span data-ttu-id="ed5b1-238">보존 레이블, 보존 레이블 정책 또는 자동 적용 정책을 편집하거나 보존 레이블이 이미 콘텐츠에 적용된 경우, 새로 레이블이 적용된 콘텐츠 외에 이 콘텐츠에 업데이트된 설정이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-238">If you edit a retention label, retention label policy, or auto-apply policy and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly labeled.</span></span>

## <a name="find-the-powershell-cmdlets-for-retention-labels"></a><span data-ttu-id="ed5b1-239">보존 레이블에 대한 PowerShell cmdlet 찾기</span><span class="sxs-lookup"><span data-stu-id="ed5b1-239">Find the PowerShell cmdlets for retention labels</span></span>

<span data-ttu-id="ed5b1-240">보존 레이블 cmdlet을 사용하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-240">To use the retention label cmdlets:</span></span>
  
1. [<span data-ttu-id="ed5b1-241">Office 365 보안 및 준수 센터 PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="ed5b1-241">Connect to the Office 365 Security & Compliance Center Powershell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. <span data-ttu-id="ed5b1-242">다음 Office 365 보안 및 준수 센터 cmdlet 사용:</span><span class="sxs-lookup"><span data-stu-id="ed5b1-242">Use these Office 365 Security & Compliance Center cmdlets:</span></span>
    
    - [<span data-ttu-id="ed5b1-243">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="ed5b1-243">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)
    
    - [<span data-ttu-id="ed5b1-244">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="ed5b1-244">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)
    
    - [<span data-ttu-id="ed5b1-245">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="ed5b1-245">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)
    
    - [<span data-ttu-id="ed5b1-246">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="ed5b1-246">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)
    
    - [<span data-ttu-id="ed5b1-247">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="ed5b1-247">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)
    
    - [<span data-ttu-id="ed5b1-248">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="ed5b1-248">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)
    
    - [<span data-ttu-id="ed5b1-249">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="ed5b1-249">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)
    
    - [<span data-ttu-id="ed5b1-250">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="ed5b1-250">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)
    
    - [<span data-ttu-id="ed5b1-251">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="ed5b1-251">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)
    
    - [<span data-ttu-id="ed5b1-252">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="ed5b1-252">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)
    
    - [<span data-ttu-id="ed5b1-253">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="ed5b1-253">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)
    
    - [<span data-ttu-id="ed5b1-254">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="ed5b1-254">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)
    
    - [<span data-ttu-id="ed5b1-255">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="ed5b1-255">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)
    
    - [<span data-ttu-id="ed5b1-256">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="ed5b1-256">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)
