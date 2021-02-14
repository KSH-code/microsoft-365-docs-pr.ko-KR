---
title: 정보 관리 정책 만들기 및 적용
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/16/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 8ccac9e4-3a50-49fa-a95b-d186032a6ee3
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
description: 정보 관리 정책을 설정하여 정보가 보관된 기간을 제어하고 해당 정보를 사용하는 사용자 추적하는 방법을 배워야 합니다.
ms.openlocfilehash: 2519f039e7495d01a828aee564ce1a6caf41342d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817997"
---
# <a name="create-and-apply-information-management-policies"></a><span data-ttu-id="fb867-103">정보 관리 정책 만들기 및 적용</span><span class="sxs-lookup"><span data-stu-id="fb867-103">Create and apply information management policies</span></span>

<span data-ttu-id="fb867-104">조직에서는 정보 관리 정책을 사용하여 콘텐츠를 보존하는 기간을 제어하고, 콘텐츠로 무엇을 하는지 감사하고, 문서에 바코드 또는 레이블을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-104">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents.</span></span> <span data-ttu-id="fb867-105">정책은 법률 및 정부 규정 또는 내부 비즈니스 프로세스를 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-105">A policy can help enforce compliance with legal and governmental regulations or internal business processes.</span></span> <span data-ttu-id="fb867-106">관리자는 문서를 추적하는 방법과 문서 보존 기간을 제어하는 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-106">As an administrator, you can set up a policy to control how to track documents and how long to retain documents.</span></span>
  
<span data-ttu-id="fb867-107">정보 관리 정책은 사이트 계층 구조에서 가장 넓은 위치부터 가장 좁은 위치까지 세 가지 위치에 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-107">You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:</span></span>
  
- <span data-ttu-id="fb867-108">사이트 모음 내의 여러 콘텐츠 형식에 사용할 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-108">Create a policy to use on multiple content types within a site collection.</span></span>
    
- <span data-ttu-id="fb867-109">사이트 콘텐츠 형식에 대한 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-109">Create a policy for a site content type.</span></span>
    
- <span data-ttu-id="fb867-110">목록 또는 라이브러리에 대한 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-110">Create a policy for a list or library.</span></span>
    
<span data-ttu-id="fb867-111">자세한 내용은 정보 관리 정책 [소개를 참조하십시오.](intro-to-info-mgmt-policies.md)</span><span class="sxs-lookup"><span data-stu-id="fb867-111">For more information, see [Introduction to information management policies](intro-to-info-mgmt-policies.md).</span></span>
  
## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a><span data-ttu-id="fb867-112">사이트 모음 내의 여러 콘텐츠 형식에 대한 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="fb867-112">Create a policy for multiple content types within a site collection</span></span>
<span data-ttu-id="fb867-113"><a name="__toc261001590"> </a></span><span class="sxs-lookup"><span data-stu-id="fb867-113"><a name="__toc261001590"> </a></span></span>

<span data-ttu-id="fb867-114">사이트 모음 내의 특정 형식의 모든 문서에 정보 정책이 적용되도록 보장하기 위해 사이트 모음 수준에서 정책을 만들고 나중에 콘텐츠 형식에 정책을 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-114">To ensure that an information policy is applied to all documents of a certain type within a site collection, consider creating the policy at the site collection level and then later apply the policy to content types.</span></span> <span data-ttu-id="fb867-115">이러한 정책을 사이트 모음 정책이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-115">These are referred to as site collection policies.</span></span> 
  
1. <span data-ttu-id="fb867-116">사이트 모음 홈 페이지의 제목 표시줄에 \>  ![ 있는 설정 SharePoint 2016 설정 단추입니다.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span><span class="sxs-lookup"><span data-stu-id="fb867-116">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span></span> <span data-ttu-id="fb867-117">\> **사이트 설정**.</span><span class="sxs-lookup"><span data-stu-id="fb867-117">\> **Site Settings**.</span></span>
    
    <span data-ttu-id="fb867-118">SharePoint 그룹에 연결된 사이트에서 설정을 **클릭하고** 사이트 콘텐츠를 클릭한 다음 사이트 설정을 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="fb867-118">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="fb867-119">사이트 설정 페이지의 **사이트 모음 관리 콘텐츠 형식** 정책 서식 파일 아래에 \> **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fb867-119">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
![사이트 설정 페이지의 콘텐츠 형식 정책 템플릿 링크](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="fb867-121">정책 페이지에서 \> **만들기**.</span><span class="sxs-lookup"><span data-stu-id="fb867-121">On the Policies page \> **Create**.</span></span> 
    
4. <span data-ttu-id="fb867-122">정책의 이름과 설명을 입력한 다음 사용자에게 정책의 이름을 설명하는 간단한 정책 설명을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-122">Enter a name and description for the policy, and then write a brief policy statement that explains to users what the policy is for.</span></span>
    
5. <span data-ttu-id="fb867-123">사이트 콘텐츠 형식에 대한 정책을 만드는 방법에 대한 다음 섹션을 참조하여 정책과 연결하려는 기능을 설정하는 방법을 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="fb867-123">See the next section on creating policies for a site content type to learn how to set up the features you want to associate with the policy.</span></span> 
    
6. <span data-ttu-id="fb867-124">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-124">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-site-content-type"></a><span data-ttu-id="fb867-125">사이트 콘텐츠 형식에 대한 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="fb867-125">Create a policy for a site content type</span></span>
<span data-ttu-id="fb867-126"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="fb867-126"><a name="__create_a_policy"> </a></span></span>

<span data-ttu-id="fb867-127">콘텐츠 형식에 정보 관리 정책을 추가하면 정책 기능을 여러 목록 또는 라이브러리와 쉽게 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-127">Adding an information management policy to a content type makes it easy to associate policy features with multiple lists or libraries.</span></span> <span data-ttu-id="fb867-128">콘텐츠 형식에 기존 정보 관리 정책을 추가하거나 개별 콘텐츠 형식에 대한 고유한 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-128">You can choose to add an existing information management policy to a content type or create a unique policy specific to an individual content type.</span></span>
  
 <span data-ttu-id="fb867-129">목록과 관련이 있는 콘텐츠 형식에 정보 관리 정책을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-129">You can also add an information management policy to a content type that is specific to lists.</span></span> <span data-ttu-id="fb867-130">이 경우 콘텐츠 형식을 사용하는 해당 목록의 항목에만 정책을 적용하는 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-130">This has the effect of applying the policy only to items in that list that are using the content type.</span></span> 
  
1. <span data-ttu-id="fb867-131">사이트 모음 홈 페이지의 제목 표시줄에 \>  ![ 있는 설정 SharePoint 2016 설정 단추입니다.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span><span class="sxs-lookup"><span data-stu-id="fb867-131">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span></span> <span data-ttu-id="fb867-132">\> **사이트 설정**.</span><span class="sxs-lookup"><span data-stu-id="fb867-132">\> **Site Settings**.</span></span>
    
    <span data-ttu-id="fb867-133">SharePoint 그룹에 연결된 사이트에서 설정을 **클릭하고** 사이트 콘텐츠를 클릭한 다음 사이트 설정을 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="fb867-133">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="fb867-134">사이트 설정 페이지의 웹 디자이너 갤러리 **사이트 콘텐츠** 형식 아래에 \> **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fb867-134">On the Site Settings page, under **Web Designer Galleries** \> **Site content types**.</span></span>
  
![사이트 설정 페이지의 사이트 콘텐츠 형식 링크](../media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
3. <span data-ttu-id="fb867-136">사이트 콘텐츠 형식 설정 페이지에서 정책을 추가할 콘텐츠 형식을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-136">On the Site Content Type Settings page, select the content type that you want to add a policy to.</span></span>
    
4. <span data-ttu-id="fb867-137">사이트 콘텐츠 형식 페이지의 **설정** \> **정보 관리 정책 설정 아래에 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fb867-137">On the Site Content Type page, under **Settings** \> **Information management policy settings**.</span></span>
    
5. <span data-ttu-id="fb867-138">정책 편집 페이지에서 정책의 이름과 설명을 입력한 다음 사용자에게 정책의 이름을 설명하는 간단한 설명을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-138">On the Edit Policy page, enter a name and description for the policy, and then write a brief description that explains to users what the policy is for.</span></span>
    
6. <span data-ttu-id="fb867-139">다음 섹션에서 정보 관리 정책에 추가할 개별 정책 기능을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-139">In the next sections, select the individual policy features that you want to add to your information management policy.</span></span> 
  
![콘텐츠 정책 유형](../media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
7. <span data-ttu-id="fb867-141">해당 정책이 적용된 문서 및 항목에 대한 보존 기간을 지정하려면 보존 사용을 선택한 다음 보존 기간 및 항목이 만료될 때 수행할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-141">To specify a retention period for documents and items that are subject to this policy, choose **Enable Retention**, and then specify the retention period and the actions that you want to occur when the items expire.</span></span>
    
    <span data-ttu-id="fb867-142">보존 기간을 지정하는 경우</span><span class="sxs-lookup"><span data-stu-id="fb867-142">To specify a retention period</span></span>
    
||||||<span data-ttu-id="fb867-143">**1.**</span><span class="sxs-lookup"><span data-stu-id="fb867-143">**1.**</span></span>|<span data-ttu-id="fb867-144">\*\*Choose \*\*Add a retention stage for records...\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="fb867-144">\*\*Choose \*\*Add a retention stage for records…\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="fb867-145">2.</span><span class="sxs-lookup"><span data-stu-id="fb867-145">2.</span></span>  <br/> | <span data-ttu-id="fb867-146">보존 기간 옵션을 선택하여 문서 또는 항목이 만료로 설정된 시기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-146">Select a retention period option to specify when documents or items are set to expire.</span></span> <span data-ttu-id="fb867-147">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-147">Do one of the following:</span></span>  <br/>  <span data-ttu-id="fb867-148">날짜 속성에 따라 만료 날짜를 설정하려면 **이벤트** 아래에서 항목에 대한 날짜 속성을 기반으로 한 다음 문서 또는 항목 동작(예: 만든 날짜 또는 수정) 및 이 작업 이후의 시간 증분(예: 일, 월 또는 년 수)을 \> 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-148">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span>  <br/>  <span data-ttu-id="fb867-149">사용자 지정 보존 수식을 사용하여 만료를 확인한 후 이 서버에 설치된 사용자 지정 보존 **수식으로 설정(Set by a custom retention formula)을 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="fb867-149">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span>  <br/> <span data-ttu-id="fb867-150">> [!NOTE]> 이 옵션은 관리자가 사용자 지정 수식을 설정한 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-150">> [!NOTE]>  This option is only available if a custom formula has been set up by your administrator.</span></span>           |
||||||<span data-ttu-id="fb867-151">3.</span><span class="sxs-lookup"><span data-stu-id="fb867-151">3.</span></span>  <br/> |<span data-ttu-id="fb867-152">워크플로 **시작 옵션은** 이미 워크플로가 연결된 목록, 라이브러리 또는 콘텐츠 형식에 대한 정책을 정의하는 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-152">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it.</span></span> <span data-ttu-id="fb867-153">그런 다음 선택할 워크플로를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-153">You will then be given a choice of workflows to choose from.</span></span>  <br/> |
||||||<span data-ttu-id="fb867-154">4.</span><span class="sxs-lookup"><span data-stu-id="fb867-154">4.</span></span>  <br/> |<span data-ttu-id="fb867-155">되풀이 **섹션에서** 이 단계의 작업 **반복...** 작업을 다시 실행하려는 자주 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-155">In the **Recurrence** section, select **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span>  <br/> <span data-ttu-id="fb867-156">> [!NOTE]> 이 옵션은 선택한 작업을 반복할 수 있는 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-156">> [!NOTE]>  This option is only available if the action you selected can be repeated.</span></span> <span data-ttu-id="fb867-157">예를 들어 영구 삭제 작업의 경우 재발을 **설정할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="fb867-157">For example, you cannot set recurrence for the action **Permanently Delete**.</span></span>           |
||||||<span data-ttu-id="fb867-158">5.</span><span class="sxs-lookup"><span data-stu-id="fb867-158">5.</span></span>  <br/> |<span data-ttu-id="fb867-159">확인을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fb867-159">Chose **OK**.</span></span>  <br/> |
   
1. <span data-ttu-id="fb867-160">해당 정책이 적용된 문서 및 항목에 대한 감사를 사용하도록 설정하려면 감사 사용을 선택한 다음 감사할 이벤트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-160">To enable auditing for the documents and items that are subject to this policy, choose **Enable Auditing**, and then specify the events you want to audit.</span></span>
    
    <span data-ttu-id="fb867-161">감사를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="fb867-161">To enable auditing</span></span>
    
||||||<span data-ttu-id="fb867-162">1.\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="fb867-162">\*\*\*\*1.\*\*\*\*</span></span>|<span data-ttu-id="fb867-163">On the Edit Policy page,\*\* **under** **Auditing** **\>** **Enable auditing** \*\*, and then select the check boxes next to the events you want to keep an audit trail for.\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="fb867-163">\*\*\*\*On the Edit Policy page,\*\* **under** **Auditing** **\>** **Enable auditing** \*\*, and then select the check boxes next to the events you want to keep an audit trail for.\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="fb867-164">**2.**</span><span class="sxs-lookup"><span data-stu-id="fb867-164">**2.**</span></span> <br/> |<span data-ttu-id="fb867-165">**사용자에게 이러한 바코드를**  문서에 삽입할지 묻는 메시지를 표시하고 저장하거나 인쇄하기 전에 바코드를 삽입하라는 메시지를 **사용자에게 표시로 선택해야 합니다.** </span><span class="sxs-lookup"><span data-stu-id="fb867-165">**To prompt users to insert these barcodes into documents,** **choose** **Prompt users to insert a barcode before saving or printing** **.**</span></span> <br/> |
||||||<span data-ttu-id="fb867-166">**3.**</span><span class="sxs-lookup"><span data-stu-id="fb867-166">**3.**</span></span> <br/> |<span data-ttu-id="fb867-167">**CHOOSE** **OK** \*\* to apply the auditing feature to the policy.</span><span class="sxs-lookup"><span data-stu-id="fb867-167">**Choose** **OK** \*\* to apply the auditing feature to the policy.</span></span> ** <br/> |
|||||||<span data-ttu-id="fb867-168">감사 정책 기능을 사용하면 조직에서 문서에 대한 감사 내역을 만들고 분석하고 작업 목록, 문제점 목록, 토론 그룹, 일정 등의 항목을 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-168">The Auditing Policy feature enables organizations to create and analyze audit trails for documents and to list items such as task lists, issues lists, discussion groups, and calendars.</span></span> <span data-ttu-id="fb867-169">이 정책 기능은 콘텐츠를 보거나 편집 또는 삭제하는 경우와 같은 이벤트를 기록하는 감사 로그를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-169">This policy feature provides an audit log that records events, such as when content is viewed, edited, or deleted.</span></span>  <br/> |
|||||||<span data-ttu-id="fb867-170">감사를 정보 관리 정책의 일부로 사용하도록 설정하면 관리자는 Microsoft Excel 기반의 정책 사용 현황 보고서에서 감사 데이터를 보고 현재 사용 현황을 요약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-170">When auditing is enabled as part of an information management policy, administrators can view the audit data in policy usage reports that are based in Microsoft Excel and that summarize current usage.</span></span> <span data-ttu-id="fb867-171">관리자는 이러한 보고서를 사용하여 조직 내에서 정보가 사용되는 방식을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-171">Administrators can use these reports to determine how information is being used within the organization.</span></span> <span data-ttu-id="fb867-172">이러한 보고서는 조직이 규정 준수를 확인하고 문서화하거나 잠재적인 문제를 조사하는 데에도 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-172">These reports can also help organizations to verify and document their regulatory compliance or to investigate potential concerns.</span></span>  <br/> |
|||||||<span data-ttu-id="fb867-173">감사 로그에는 이벤트 이름, 이벤트의 날짜 및 시간, 해당 작업을 수행한 사용자의 시스템 이름과 같은 정보가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-173">The audit log records the following information: event name, date and time of the event, and system name of the user who performed the action.</span></span>  <br/> |
   
1. <span data-ttu-id="fb867-174">정책의 일부로 바코드를 사용할 수 있는 경우 바코드가 적용되는 문서의 헤더 영역에 문서 속성에 추가되고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-174">When barcodes are enabled as part of a policy, they are added to document properties and displayed in the header area of the document to which the barcode is applied.</span></span> <span data-ttu-id="fb867-175">레이블과 마찬가지로 바코드도 문서에서 수동으로 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-175">Like labels, barcodes can also be manually removed from a document.</span></span> <span data-ttu-id="fb867-176">항목을 인쇄하거나 저장하는 경우 사용자에게 바코드를 포함하라는 메시지가 표시될지 또는 2010  Office 릴리스 프로그램의 삽입 탭을 사용하여 바코드를 수동으로 삽입해야 하는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-176">You can specify whether users should be prompted to include the barcode when printing or saving an item or if the barcode should be inserted manually using the **Insert** tab in 2010 Office release programs.</span></span> 
    
    <span data-ttu-id="fb867-177">바코드를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="fb867-177">To enable barcodes</span></span>
    
||||||<span data-ttu-id="fb867-178">1.\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="fb867-178">\*\*\*\*1.\*\*\*\*</span></span>|<span data-ttu-id="fb867-179">\*\*정책 편집 페이지의 바코드  \> \*\*아래에서 바코드를 사용하도록 설정합니다.\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="fb867-179">**On the Edit Policy page, under **Barcodes**\> **Enable Barcodes**.**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="fb867-180">**2.**</span><span class="sxs-lookup"><span data-stu-id="fb867-180">**2.**</span></span> <br/> |<span data-ttu-id="fb867-181">사용자에게 이러한 바코드를 문서에 삽입할지 묻는 메시지를 표시하고 저장하거나 인쇄하기 전에 바코드를 삽입하라는 메시지를 **사용자에게 표시로 선택해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fb867-181">To prompt users to insert these barcodes into documents, choose **Prompt users to insert a barcode before saving or printing**.</span></span>  <br/> |
||||||<span data-ttu-id="fb867-182">**3.**</span><span class="sxs-lookup"><span data-stu-id="fb867-182">**3.**</span></span> <br/> |<span data-ttu-id="fb867-183">**확인을** 선택하면 정책에 바코드 기능을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-183">Choose **OK** to apply the barcode feature to the policy.</span></span>  <br/> |
|||||||
 <span data-ttu-id="fb867-184">바코드 정책은 코드 39 표준 바코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-184">The barcode policy generates Code 39 standard barcodes.</span></span> <span data-ttu-id="fb867-185">각 바코드 이미지에는 바코드 값을 나타내는 바코드 기호 아래에 있는 텍스트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-185">Each barcode image includes text below the barcode symbol that represents the barcode value.</span></span> <span data-ttu-id="fb867-186">이렇게 하면 하드웨어를 스캔할 수 없는 경우에도 바코드 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-186">This enables the barcode data to be used even when scanning hardware is not available.</span></span> <span data-ttu-id="fb867-187">사용자는 검색 상자에 바코드 번호를 수동으로 입력하여 사이트에서 항목을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-187">Users can manually type the barcode number into the search box to locate the item on a site.</span></span>  <br/> |
   
1. <span data-ttu-id="fb867-188">해당 정책이 적용된 문서에 레이블이 있도록 설정하려면 레이블 사용을 선택한 다음 레이블에 대해 원하는 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-188">To require that documents that are subject to this policy have labels, choose **Enable Labels**, and then specify the settings that you want for the labels.</span></span>
    
    <span data-ttu-id="fb867-189">레이블을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="fb867-189">To enable labels</span></span>
    
||||||<span data-ttu-id="fb867-190">**1.**</span><span class="sxs-lookup"><span data-stu-id="fb867-190">**1.**</span></span>|<span data-ttu-id="fb867-191">\*\*사용자가 문서에 레이블을 추가해야 하려면 저장하거나 인쇄하기 전에 사용자에게 레이블을 삽입할지 묻는 **메시지 표시를 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="fb867-191">\*\*To require users to add a label to a document, choose **Prompt users to insert a label before saving or printing**.</span></span>  <br/> <span data-ttu-id="fb867-192">> [!NOTE]> 레이블을 선택적으로 사용하려면 이 확인란을 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-192">> [!NOTE]>  If you want labels to be optional, do not select this check box.</span></span>        **|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="fb867-193">2.</span><span class="sxs-lookup"><span data-stu-id="fb867-193">2.</span></span>  <br/> |<span data-ttu-id="fb867-194">레이블을 삽입한 후 변경할 수 없는 레이블을 잠그기 위해 레이블을 추가한 후 변경 금지를 **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="fb867-194">To lock a label so that it cannot be changed after it has been inserted, choose **Prevent changes to labels after they are added**.</span></span>  <br/>  <span data-ttu-id="fb867-195">이 설정은 레이블이 Word, Excel 또는 PowerPoint와 같은 클라이언트 응용 프로그램 내의 항목에 삽입된 후 레이블 텍스트를 업데이트할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-195">This setting prevents the label text from updating once the label has been inserted into an item within a client application such as Word, Excel, or PowerPoint.</span></span> <span data-ttu-id="fb867-196">이 문서나 항목의 속성이 업데이트될 때 레이블을 업데이트하려면 이 확인란을 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-196">If you want the label to be updated when the properties for this document or item are updated, do not select this check box.</span></span>  <br/> |
||||||<span data-ttu-id="fb867-197">3.</span><span class="sxs-lookup"><span data-stu-id="fb867-197">3.</span></span>  <br/> |<span data-ttu-id="fb867-198">레이블 서식 상자에 레이블을 표시할 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-198">In the Label format box, enter the text for the label as you want it to be displayed.</span></span> <span data-ttu-id="fb867-199">레이블에는 최대 10개 열 참조가 포함될 수 있습니다. 각 참조는 최대 255자까지 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-199">Labels can contain up to 10 column references, each of which can be up to 255 characters long.</span></span> <span data-ttu-id="fb867-200">레이블의 형식을 만들 수 있도록 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-200">To create the format for your label, do the following:</span></span>  <br/> <span data-ttu-id="fb867-201">레이블에 포함할 열의 이름을 표시하려는 순서대로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-201">Type the names of the columns that you want to include in the label in the order in which you want them to appear.</span></span> <span data-ttu-id="fb867-202">정책 편집 페이지의 예제와 같이 열 이름을 중괄호()로 {} 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-202">Enclose the column names in curly brackets ({}), as shown in the example on the Edit Policy page.</span></span>  <br/> <span data-ttu-id="fb867-203">정책 편집 페이지의 예제와 같이 대괄호 외부의 열을 식별하는 단어를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-203">Type words to identify the columns outside the brackets, as shown in the example on the Edit Policy page.</span></span>  <br/> |
||||||<span data-ttu-id="fb867-204">4.</span><span class="sxs-lookup"><span data-stu-id="fb867-204">4.</span></span>  <br/> |<span data-ttu-id="fb867-205">줄 끝을 추가하려는 경우 줄을 표시하려는 **\n을** 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-205">To add a line break, enter **\n** where you want the line break to appear.</span></span>  <br/> |
||||||<span data-ttu-id="fb867-206">5.</span><span class="sxs-lookup"><span data-stu-id="fb867-206">5.</span></span>  <br/> |<span data-ttu-id="fb867-207">원하는 글꼴 크기와 스타일을 선택하고 문서 내에서 레이블을 왼쪽, 가운데 또는 오른쪽으로 배치할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-207">Select the font size and style that you want, and specify whether you want the label positioned left, center, or right within the document.</span></span>  <br/>  <span data-ttu-id="fb867-208">사용자의 컴퓨터에서 사용할 수 있는 글꼴 및 스타일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-208">Select a font and style that are available on the users' computers.</span></span> <span data-ttu-id="fb867-209">글꼴 크기에 따라 레이블에 표시할 수 있는 텍스트의 양이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-209">The size of the font affects how much text can be displayed on the label.</span></span>  <br/> |
||||||<span data-ttu-id="fb867-210">6.</span><span class="sxs-lookup"><span data-stu-id="fb867-210">6.</span></span>  <br/> |<span data-ttu-id="fb867-211">레이블의 높이와 너비를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-211">Enter the height and width of the label.</span></span> <span data-ttu-id="fb867-212">레이블의 높이와 너비로는 0.625센티미터에서 50센티미터 사이의 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-212">Label height can range from .25 inches to 20 inches, and label width can range from .25 inches to 20 inches.</span></span> <span data-ttu-id="fb867-213">레이블 텍스트는 항상 레이블 이미지 내에서 세로 가운데에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-213">Label text is always vertically centered within the label image.</span></span>  <br/> |
||||||<span data-ttu-id="fb867-214">7.</span><span class="sxs-lookup"><span data-stu-id="fb867-214">7.</span></span>  <br/> |<span data-ttu-id="fb867-215">새로 **고침을** 선택하면 레이블 콘텐츠를 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-215">Choose **Refresh** to preview the label content.</span></span>  <br/> |
   
1. <span data-ttu-id="fb867-216">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-216">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a><span data-ttu-id="fb867-217">목록, 라이브러리 또는 폴더에 대한 정책(위치 기반 보존 정책) 만들기</span><span class="sxs-lookup"><span data-stu-id="fb867-217">Create a policy for a list, library or folder (location-based retention policy)</span></span>
<span data-ttu-id="fb867-218"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="fb867-218"><a name="__create_a_policy"> </a></span></span>

<span data-ttu-id="fb867-219">특정 목록, 라이브러리 또는 폴더에만 적용되는 보존 정책을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-219">You can define a retention policy that applies only to a specific list, library or folder.</span></span> <span data-ttu-id="fb867-220">그러나 이러한 방식으로 보존 정책을 만드는 경우 다른 목록, 라이브러리, 폴더 또는 사이트에서 이 정책을 다시 사용할 수 없습니다. 또한 위치 기반 정책에 사이트 모음 정책을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-220">However, if you create a retention policy this way, you cannot reuse this policy on other lists, libraries, folders or sites, and you cannot apply a site collection policy to a location based policy.</span></span>
  
<span data-ttu-id="fb867-221">단일 위치의 모든 콘텐츠 유형에 단일 보존 정책을 적용하려는 경우 위치 기반 보존을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-221">If you want to apply a single retention policy to all types of content in a single location, you will most likely want to use location-based retention.</span></span> <span data-ttu-id="fb867-222">대부분의 경우 모든 콘텐츠 형식에 대해 보존 정책이 지정되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-222">In most other cases, you will want to verify that a retention policy is specified for all content types.</span></span>
  
 <span data-ttu-id="fb867-223">상속을 중단하고 자식 수준에서 새 보존 정책을 정의하지 않는 한 각 하위는 상위의 보존 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-223">Each subfolder inherits the retention policy of its parent, unless you choose to break inheritance and define a new retention policy at the child level.</span></span> 
  
<span data-ttu-id="fb867-224">목록 또는 라이브러리에 대한 보존이 아니라 정보 관리 정책을 정의하려면 해당 목록 또는 라이브러리에 연결된 각 개별 목록 콘텐츠 형식에 대한 정보 관리 정책을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-224">If you want to define an information management policy other than retention to a list or library, you need to define an information management policy for each individual list content type associated with that list or library.</span></span>
  
 <span data-ttu-id="fb867-225">콘텐츠 형식에서 목록 또는 라이브러리에 대한 위치 기반 정책으로 전환하기로 결정한 경우 보존 정책만 위치 기반 정책으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-225">If at any point you decide to switch from content type to location-based policies for a list or library, only the retention policy will be used as the location-based policy.</span></span> <span data-ttu-id="fb867-226">다른 모든 관리 정책(감사, 바코드 및 바코드)은 연결된 콘텐츠 형식에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-226">All other management policies (audits, barcodes, and barcodes) will be inherited from the associated content types.</span></span> 
  
 <span data-ttu-id="fb867-227">라이브러리 및 폴더 기반 보존 기능을 비활성화하여 사이트 모음에 대해 위치 기반 정책을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-227">Location based policies can be disabled for a site collection by deactivating the Library and Folder Based Retention feature.</span></span> <span data-ttu-id="fb867-228">이를 통해 사이트 모음 관리자는 콘텐츠 형식 정책이 목록 관리자의 위치 기반 정책에 의해 재배치되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-228">This enables site collection administrators to ensure that their content type policies are not overridden by a list administrator's location based policies.</span></span> 
  
<span data-ttu-id="fb867-229">목록 또는 라이브러리에 대한 정보 관리 정책 설정을 변경하려면 적어도 목록 관리 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-229">You need at least the Manage Lists permission to change the information management policy settings for a list or library.</span></span>
  
1. <span data-ttu-id="fb867-230">정보 관리 정책을 지정할 목록 또는 라이브러리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-230">Navigate to the list or library for which you want to specify an information management policy.</span></span> 
    
2. <span data-ttu-id="fb867-231">리본 메뉴에서  라이브러리 또는 목록 **탭** \> **라이브러리 설정** 또는 목록 **설정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fb867-231">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="fb867-232">SharePoint Online에서 설정을 **클릭한** 다음 **목록** 설정 또는 라이브러리 설정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fb867-232">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="fb867-233">사용 **권한 및 관리** 정보 관리 정책 \> **설정에서**.</span><span class="sxs-lookup"><span data-stu-id="fb867-233">Under **Permissions and Management**\> **Information management policy settings**.</span></span>
  
![문서 라이브러리 설정 페이지의 정보 관리 정책 링크](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="fb867-235">정보 관리 정책 설정 페이지에서 목록 또는 라이브러리의 보존 원본이 라이브러리 및 폴더로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-235">On the Information Management Policy Settings page, make sure that the source of retention for the list or library is set to Library and Folders.</span></span> 
  
<span data-ttu-id="fb867-236">콘텐츠 **형식이** 원본으로 표시될 경우 원본 변경을 클릭한 다음 라이브러리 및 **폴더를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fb867-236">If **Content Type** appears as the source, click **Change Source**, and then click **Library and Folders**.</span></span> <span data-ttu-id="fb867-237">콘텐츠 형식 보존 정책은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-237">You are alerted that content type retention policies will be ignored.</span></span> <span data-ttu-id="fb867-238">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-238">Choose **OK**.</span></span> 
    
5. <span data-ttu-id="fb867-239">정책 편집 페이지의 **라이브러리** 기반 보존 일정에서 만들 정책에 대한 간단한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-239">On the Edit Policy page, under **Library Based Retention Schedule**, enter a brief description for the policy you are creating.</span></span> 
    
6. <span data-ttu-id="fb867-240">보존 **단계 추가 선택...**</span><span class="sxs-lookup"><span data-stu-id="fb867-240">Choose **Add a retention stage…**</span></span>
    
     <span data-ttu-id="fb867-241">레코드 아래에서 레코드에 대해 서로 다른 보존 단계 정의 옵션을 선택하여 레코드에 대한 다양한 보존 정책을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-241">Note that under Records, you can choose to define different retention policies for records by selecting the Define different retention stages for records option.</span></span> 
    
7. <span data-ttu-id="fb867-242">스테이지 속성 대화 상자에서 보존 기간 옵션을 선택하여 문서 또는 항목이 만료될 것으로 설정된 시기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-242">In the Stage properties dialog, select a retention period option to specify when documents or items are set to expire.</span></span> <span data-ttu-id="fb867-243">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-243">Do one of the following:</span></span>
    
  - <span data-ttu-id="fb867-244">날짜 속성에 따라 만료 날짜를 설정하려면 **이벤트** 아래에서 항목에 대한 날짜 속성을 기반으로 한 다음 문서 또는 항목 동작(예: 만든 날짜 또는 수정) 및 이 작업 이후의 시간 증분(예: 일, 월 또는 년 수)을 \> 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-244">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span> 
    
  - <span data-ttu-id="fb867-245">사용자 지정 보존 수식을 사용하여 만료를 확인한 후 이 서버에 설치된 사용자 지정 보존 **수식으로 설정(Set by a custom retention formula)을 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="fb867-245">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="fb867-246">이 옵션은 관리자가 사용자 지정 수식을 설정한 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-246">This option is only available if a custom formula has been set up by your administrator.</span></span> 
  
  - <span data-ttu-id="fb867-247">작업 **아래에서** 문서나 항목이 만료될 때 수행될 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-247">Under **Action**, specify what you want to happen when the document or item expires.</span></span> <span data-ttu-id="fb867-248">문서 또는 항목에 대해 특정 작업이 수행될 수 있도록 설정하려면(예: 지우기) 목록에서 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-248">To enable a specific action to happen to the document or item (such as deletion), select an action from the list.</span></span> 
    
8. <span data-ttu-id="fb867-249">워크플로 **시작 옵션은** 이미 워크플로가 연결된 목록, 라이브러리 또는 콘텐츠 형식에 대한 정책을 정의하는 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-249">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it.</span></span> <span data-ttu-id="fb867-250">그런 다음 선택할 워크플로를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-250">You will then be given a choice of workflows to choose from.</span></span> 
    
9. <span data-ttu-id="fb867-251">**되풀이에서** 이 **단계의 작업을 반복합니다.** 작업을 다시 실행하려는 자주 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-251">Under **Recurrence**, choose **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="fb867-252">이 옵션은 선택한 작업을 반복할 수 있는 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-252">This option is only available if the action you selected can be repeated.</span></span> <span data-ttu-id="fb867-253">예를 들어 영구 삭제 작업의 경우 재발을 **설정할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="fb867-253">For example, you cannot set recurrence for the action **Permanently Delete**.</span></span> 
  
10. <span data-ttu-id="fb867-254">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-254">Choose **OK**.</span></span>
    
## <a name="apply-a-site-collection-policy-to-a-content-type"></a><span data-ttu-id="fb867-255">콘텐츠 형식에 사이트 모음 정책 적용</span><span class="sxs-lookup"><span data-stu-id="fb867-255">Apply a site collection policy to a content type</span></span>
<span data-ttu-id="fb867-256"><a name="__apply_a_site"> </a></span><span class="sxs-lookup"><span data-stu-id="fb867-256"><a name="__apply_a_site"> </a></span></span>

<span data-ttu-id="fb867-257">사이트에 대한 정보 관리 정책이 사이트 모음 정책으로 이미 만들어진 경우 콘텐츠 형식에 정책 중 하나를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-257">If information management policies have already been created for your site as site collection policies, you can apply one of the policies to a content type.</span></span> <span data-ttu-id="fb867-258">이렇게 하면 동일한 상위 콘텐츠 형식을 공유하지 않는 사이트 모음의 여러 콘텐츠 형식에 동일한 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-258">By doing this, you can apply the same policy to multiple content types in a site collection that do not share the same parent content type.</span></span>
  
 <span data-ttu-id="fb867-259">사이트 모음의 여러 콘텐츠 형식에 정책을 적용하고 Managed Metadata Service를 구성한 경우 콘텐츠 형식 게시를 사용하여 여러 사이트 모음에 정보 관리 정책을 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-259">If you want to apply policies to multiple content types in a site collection, and you have a Managed Metadata Service configured, you can use Content Type Publishing to publish out information management polices to multiple site collections.</span></span> <span data-ttu-id="fb867-260">자세한 내용은 [사이트](#apply-a-policy-across-site-collections) 모음 전체에 정책 적용 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb867-260">See the section [Apply a policy across site collections](#apply-a-policy-across-site-collections) for more information.</span></span> 
  
1. <span data-ttu-id="fb867-261">정책을 적용할 콘텐츠 형식이 포함된 목록 또는 라이브러리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-261">Navigate to the list or library that contains the content type to which you want to apply a policy.</span></span>
    
2. <span data-ttu-id="fb867-262">리본 메뉴에서  라이브러리 또는 목록 **탭** \> **라이브러리 설정** 또는 목록 **설정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fb867-262">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="fb867-263">SharePoint Online에서 설정을 **클릭한** 다음 **목록** 설정 또는 라이브러리 설정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fb867-263">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="fb867-264">사용 **권한 및 관리 정보 관리** 정책 설정 \> **아래**</span><span class="sxs-lookup"><span data-stu-id="fb867-264">Under **Permissions and Management** \> **Information management policy settings**.</span></span>
  
![문서 라이브러리 설정 페이지의 정보 관리 정책 링크](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="fb867-266">정책 원본이 콘텐츠 형식으로 설정되어  있는지 확인하고 **콘텐츠** 형식 정책에서 정책을 적용할 콘텐츠 형식을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-266">Verify that the policy source is set to **Content Types**, and under **Content Type Policies** select the content type you want to apply the policy to.</span></span> 
    
5. <span data-ttu-id="fb867-267">정책 **사용 정책** 지정 \> **아래에서 사이트** 모음 정책을 선택하고 목록에서 적용할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-267">Under **Specify the Policy** \> **Use a site collection policy**, and then select the policy that you want to apply from the list.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="fb867-268">사이트 모음 **정책** 사용 옵션을 사용할 수 없는 경우 사이트 모음에 대해 사이트 모음 정책이 정의되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-268">If the **Use a site collection policy** option is not available, no site collection policies have been defined for the site collection.</span></span> 
  
6. <span data-ttu-id="fb867-269">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-269">Choose **OK**.</span></span>
    
     <span data-ttu-id="fb867-270">사용하려는 목록 또는 라이브러리가 여러 콘텐츠 형식의 관리를  지원하는 경우 콘텐츠 형식에서 정보 관리 정책을 지정할 콘텐츠 형식을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-270">If the list or library you are working with supports the management of multiple content types, under **Content Types** you can choose the content type for which you want to specify an information management policy.</span></span> <span data-ttu-id="fb867-271">그러면 위 5단계로 바로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-271">This will take you directly to Step 5 above.</span></span> 
    
## <a name="apply-a-policy-across-site-collections"></a><span data-ttu-id="fb867-272">여러 사이트 모음에 정책 적용</span><span class="sxs-lookup"><span data-stu-id="fb867-272">Apply a policy across site collections</span></span>
<span data-ttu-id="fb867-273"><a name="__toc260646789"> </a></span><span class="sxs-lookup"><span data-stu-id="fb867-273"><a name="__toc260646789"> </a></span></span>

<span data-ttu-id="fb867-274">Managed Metadata Service 응용 프로그램을 사용하여 콘텐츠 형식 게시를 설정하여 사이트 모음에서 콘텐츠 형식을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-274">Share content types across site collections by using a Managed Metadata service application to set up content type publishing.</span></span> <span data-ttu-id="fb867-275">콘텐츠 형식 게시를 사용하면 콘텐츠 형식을 중앙에서 만들어 업데이트할 수 있고 업데이트를 여러 하위 사이트 모음 또는 웹 응용 프로그램에 게시할 수 있기 때문에 사이트 전체에서 콘텐츠 및 메타데이터를 일관되게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-275">Content type publishing helps you manage content and metadata consistently across your sites because content types can be created and updated centrally, and updates can be published out to multiple subscribing site collections or Web applications.</span></span>
  
## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a><span data-ttu-id="fb867-276">기존 정책에서 여러 사이트 모음에 사용할 서식 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="fb867-276">Create a template from an existing policy to use across site collections</span></span>
<span data-ttu-id="fb867-277"><a name="__toc262125409"> </a></span><span class="sxs-lookup"><span data-stu-id="fb867-277"><a name="__toc262125409"> </a></span></span>

<span data-ttu-id="fb867-278">정보 관리 정책을 정의한 다음 여러 사이트 모음에서 필요한 경우 사용할 서식 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-278">You can define an information management policy and then create a template from it to use as needed across multiple site collections.</span></span> <span data-ttu-id="fb867-279">정보 정책을 백업하려는 경우 이 방법을 사용할 수도 있습니다. 또는 사이트 모음에서 하나의 정책을 적용하기 위해 콘텐츠 형식 게시를 사용하는 대체 방법으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-279">This method can be used if you want to have a backup of your information policies, or it can also be used as an alternate method to using content type publishing for applying one policy across site collections.</span></span> <span data-ttu-id="fb867-280">한 사이트 모음에서 정책을 내보낼 때 저장된 위치나 다른 사이트 모음으로 가져와서 정책의 서식 파일 또는 백업을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-280">You create a template or backup of the policy by exporting the policy from one site collection and then importing it to a saved location or to another site collection.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="fb867-281">정책 템플릿 집합을 만드는 방법으로 내보내기/가져오기 기능을 사용하는 경우 정책 .xml 파일에 고유 식별자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-281">If you using the export/import feature as a way to make a set of policy templates, keep in mind that a unique identifier exists in the policy .xml file.</span></span> <span data-ttu-id="fb867-282">따라서 이 고유 식별자를 변경하지 않으면 해당 정책을 두 번 이상 사이트로 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-282">Because of this, you cannot import that policy into a site more than once without changing this unique identifier.</span></span> 
  
### <a name="export-a-policy"></a><span data-ttu-id="fb867-283">정책 내보내기</span><span class="sxs-lookup"><span data-stu-id="fb867-283">Export a policy</span></span>
<span data-ttu-id="fb867-284"><a name="__toc260646790"> </a></span><span class="sxs-lookup"><span data-stu-id="fb867-284"><a name="__toc260646790"> </a></span></span>

1. <span data-ttu-id="fb867-285">사이트 모음 홈 페이지에서 사이트 **설정이** 있는 설정 작은 설정 기어를 선택합니다. 사이트 ![ ](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> 설정.</span><span class="sxs-lookup"><span data-stu-id="fb867-285">On the site collection home page, choose **Settings**![Small Settings gear that took the place of Site Settings.](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="fb867-286">SharePoint 그룹에 연결된 사이트에서 설정을 **클릭하고** 사이트 콘텐츠를 클릭한 다음 사이트 설정을 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="fb867-286">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="fb867-287">사이트 설정 페이지의 **사이트 모음 관리 콘텐츠 형식** 정책 서식 파일 아래에 \> **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fb867-287">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
![사이트 설정 페이지의 콘텐츠 형식 정책 템플릿 링크](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="fb867-289">스크롤을 아래쪽 내보내기로 \> 내보낼 정책을 \> **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fb867-289">Choose the policy you want to export \> scroll to the bottom \> **Export**.</span></span>
    
4. <span data-ttu-id="fb867-290">파일을 저장하거나 열지 묻는 메시지에서 저장을 선택한 다음 파일을 저장할 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-290">At the prompt to save or open the file, choose **Save**, and then select a location to save the file to.</span></span> <span data-ttu-id="fb867-291">정책을 가져오는 사이트 모음에서 사용할 수 있는 위치를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-291">Be sure to select a location that is available to the site collections that are importing the policy.</span></span>
    
5. <span data-ttu-id="fb867-292">완료 다운로드 대화 상자가 표시되면 **닫기 를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fb867-292">When the Download Complete dialog is displayed, choose **Close**.</span></span>
    
### <a name="import-a-policy-to-a-different-site-collection"></a><span data-ttu-id="fb867-293">다른 사이트 모음으로 정책 가져오기</span><span class="sxs-lookup"><span data-stu-id="fb867-293">Import a policy to a different site collection</span></span>
<span data-ttu-id="fb867-294"><a name="__toc260646791"> </a></span><span class="sxs-lookup"><span data-stu-id="fb867-294"><a name="__toc260646791"> </a></span></span>

<span data-ttu-id="fb867-295">정보 관리 정책을 가져오면 특정 사이트 모음 내의 사이트 또는 목록 수준에서 여러 콘텐츠 형식에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-295">Importing an information management policy enables you to apply it to multiple content types at the site or list level within any given site collection.</span></span> <span data-ttu-id="fb867-296">이렇게 하면 두 가지 이점이 있습니다. 즉, 각 콘텐츠 형식에 정책을 다시 정의하고 적용할 필요가 없습니다. 정책을 한 곳만 변경하여 정책 수정을 보다 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-296">The benefits of doing this are twofold: you don't have to re-define and apply the policy on each content type, and you can more easily manage policy modifications by making changes to the policy in just one place.</span></span>
  
1. <span data-ttu-id="fb867-297">정책을 적용할 사이트 모음 홈 페이지에서 사이트 설정이 있는 설정 작은 설정 기어를 선택합니다. 사이트 ![ ](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> 설정.</span><span class="sxs-lookup"><span data-stu-id="fb867-297">On the home page of the site collection to which you want to apply the policy, choose **Settings**![Small Settings gear that took the place of Site Settings.](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="fb867-298">SharePoint 그룹에 연결된 사이트에서 설정을 **클릭하고** 사이트 콘텐츠를 클릭한 다음 사이트 설정을 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="fb867-298">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="fb867-299">사이트 설정 페이지의 **사이트 모음 관리 콘텐츠 형식** 정책 서식 파일 아래에 \> **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fb867-299">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span>
    
3. <span data-ttu-id="fb867-300">정책 페이지에서 \> **가져오기** \> **찾아보기를** 사용하여 정책의 XML 파일을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-300">On the Policies page \> **Import** \> **Browse** to find the XML file for the policy.</span></span> 
    
4. <span data-ttu-id="fb867-301">정책을 저장한 XML 파일 열기 를 \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fb867-301">Select the XML file in which the policy has been saved \> **Open**.</span></span> 
    
5. <span data-ttu-id="fb867-302">사이트 모음 정책 가져오기 페이지에서 정책을 사이트 모음에 \>  추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-302">On the Import a Site Collection Policy page \> **Import** to add the policy to the site collection.</span></span> 
    
<span data-ttu-id="fb867-303">이제 가져온 정책을 사이트 또는 목록 수준에서 하나 또는 여러 콘텐츠 형식에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-303">Your imported policy can now be applied to one or many content types at the site or list level.</span></span> 
  
<span data-ttu-id="fb867-304">조직에서는 정보 관리 정책을 사용하여 콘텐츠를 보존하는 기간을 제어하고, 콘텐츠로 무엇을 하는지 감사하고, 문서에 바코드 또는 레이블을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-304">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents.</span></span> <span data-ttu-id="fb867-305">정책은 법률 및 정부 규정 또는 내부 비즈니스 프로세스를 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-305">A policy can help enforce compliance with legal and governmental regulations or internal business processes.</span></span> <span data-ttu-id="fb867-306">관리자는 문서를 추적하는 방법과 문서 보존 기간을 제어하는 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-306">As an administrator, you can set up a policy to control how to track documents and how long to retain documents.</span></span>

<span data-ttu-id="fb867-307">정보 관리 정책은 사이트 계층 구조에서 가장 넓은 위치부터 가장 좁은 위치까지 세 가지 위치에 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-307">You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:</span></span>
- <span data-ttu-id="fb867-308">사이트 모음 내의 여러 콘텐츠 형식에 사용할 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-308">Create a policy to use on multiple content types within a site collection.</span></span>
- <span data-ttu-id="fb867-309">사이트 콘텐츠 형식에 대한 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-309">Create a policy for a site content type.</span></span>
- <span data-ttu-id="fb867-310">목록 또는 라이브러리에 대한 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb867-310">Create a policy for a list or library.</span></span>

<span data-ttu-id="fb867-311">자세한 내용은 정보 관리 정책 [소개를 참조하십시오.](intro-to-info-mgmt-policies.md)</span><span class="sxs-lookup"><span data-stu-id="fb867-311">For more information, see [Introduction to information management policies](intro-to-info-mgmt-policies.md).</span></span>
  

