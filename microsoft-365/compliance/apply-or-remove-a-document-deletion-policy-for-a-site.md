---
title: 사이트에 문서 삭제 정책 적용 또는 제거
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3e92668-f9b2-46ee-8e5e-c623870588b6
description: 조직은 규정 준수, 법률 및 기타 규정 때문에 특정 기간 동안 문서 보존이 필요한 경우가 많습니다. 그렇지만 필요 이상으로 오랫동안 문서를 보존하면 조직은 법적 위험에 노출될 수 있습니다. 이러한 이유로 조직은 사이트에 대해 문서 삭제 정책을 만들었을 수 있습니다. 예를 들어 일반 비즈니스 문서는 만들고 5년 후에 삭제해야 할 수도 있습니다.
ms.openlocfilehash: f04b693a68da36b37524fe5c1fd2e00fab6c2bc6
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42079860"
---
# <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="803c5-105">사이트에 문서 삭제 정책 적용 또는 제거</span><span class="sxs-lookup"><span data-stu-id="803c5-105">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="803c5-106">조직은 특정 기간 동안 문서를 보존 하도록 요구 하는 규정 준수, 법률 또는 기타 규정에 따라 종종 좌우 됩니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-106">Organizations are often subject to compliance, legal, or other regulations that require them to retain documents for a certain period of time.</span></span> <span data-ttu-id="803c5-107">그렇지만 필요 이상으로 오랫동안 문서를 보존하면 조직은 법적 위험에 노출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-107">However, retaining documents for longer than required can expose the organization to legal risk.</span></span> <span data-ttu-id="803c5-108">이러한 이유 때문에 조직에서 사이트&mdash;에 대 한 문서 삭제 정책을 만들었을 수 있습니다. 예를 들어 일반 비즈니스 문서를 만든 후 5 년 후에 삭제 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-108">For this reason, your organization may have created a document deletion policy for your site&mdash;for example, general business documents might be required to be deleted five years after they were created.</span></span>
  
<span data-ttu-id="803c5-109">조직에 따라 다음과 같은 문서 삭제 정책이 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-109">Depending on your organization, a document deletion policy might be:</span></span>
  
- <span data-ttu-id="803c5-110">**필수** 사이트 소유자는 필수 정책을 거부할 수 없으며, 사이트에 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-110">**Mandatory** A site owner can't opt out of a mandatory policy, which is automatically applied to the site.</span></span> 
    
- <span data-ttu-id="803c5-111">**기본** 기본 정책은 사이트에 자동으로 적용되지만 사이트 소유자는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-111">**Default** A default policy is automatically applied to a site, but a site owner can:</span></span> 
    
  - <span data-ttu-id="803c5-112">사용 가능한 다른 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-112">Choose another policy if available.</span></span>
    
  - <span data-ttu-id="803c5-113">사이트의 콘텐츠와 관련이 없는 경우 정책 전체를 옵트아웃 합니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-113">Opt out of the policy entirely if it isn't relevant to the content in the site.</span></span>
    
- <span data-ttu-id="803c5-114">**필수 및 기본이 아님** 이 경우 사이트에 정책이 자동으로 적용되지 않으며 사이트 소유자가 직접 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-114">**Neither mandatory nor default** In this case, no policy is automatically applied to the site, and the site owner needs to take action to apply one.</span></span> 
    
<span data-ttu-id="803c5-115">문서 삭제 정책에는 둘 이상의 규칙이&mdash;포함 될 수 있습니다. 예를 들어 한 규칙에서 만든 후 1 년 후에 문서를 삭제 한다고 말할 수 있지만 다른 규칙을 통해 마지막으로 수정한 후 1 년 후에 문서를 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-115">A document deletion policy may contain more than one rule&mdash;for example, one rule might say delete documents one year after they were created, but another rule might say delete documents one year after they were last modified.</span></span> <span data-ttu-id="803c5-116">정책에 규칙이 둘 이상 포함 되어 있는 경우 사이트에 가장 적합 한 규칙을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-116">If a policy contains more than one rule, you can select the rule that best applies to your site.</span></span> <span data-ttu-id="803c5-117">해당 사이트 내의 모든 라이브러리에 삭제 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-117">The delete rule will be applied to all libraries within the site.</span></span> <span data-ttu-id="803c5-118">한 사이트에서 한 번에 하나의 정책 및 규칙만 활성 상태일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-118">Only one policy and one rule can be active in a site at one time.</span></span> <span data-ttu-id="803c5-119">정책과 마찬가지로 규칙을 기본값으로 설정 하 여 정책이 적용 될 때 자동으로 적용 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-119">Like a policy, a rule can be set as default, so that it's applied automatically when the policy is applied.</span></span>
  
<span data-ttu-id="803c5-p104">마지막으로 문서 삭제 정책은 상속됩니다. 사이트에 대해 정책이나 규칙을 선택하면 선택한 항목이 모든 하위 사이트에 상속됩니다. 물론 하위 사이트 소유자가 다른 정책이나 규칙을 선택하여 상속을 끊을 수 있습니다. 정책이나 규칙을 선택할 때는 사이트 아래의 모든 하위 사이트의 콘텐츠를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-p104">Finally, document deletion policies are inherited. When you select a policy or rule for your site, that selection is inherited by all subsites, although an owner of a subsite can break inheritance by selecting a different policy or rule. When you select a policy or rule, consider the content of any subsites below your site.</span></span>
  
## <a name="view-the-document-deletion-policies-available-in-a-site-collection"></a><span data-ttu-id="803c5-123">사이트 모음에서 사용할 수 있는 문서 삭제 정책을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-123">View the document deletion policies available in a site collection</span></span>

<span data-ttu-id="803c5-p105">조직에서 사이트 모음마다 다른 정책을 할당할 수도 있습니다. 사이트 모음 수준에서 사이트 모음 소유자는 해당 사이트 모음에서 사용할 수 있는 모든 문서 삭제 정책을 볼 수 있습니다. 해당 정책이 사이트 모음 서식 파일(즉 이 서식 파일에서 만든 모든 사이트 모음)이나 이러한 특정 사이트 모음에서만 사용하도록 설정되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-p105">Your organization may assign different policies to different site collections. At the site collection level, an owner of a site collection can view all of the document deletion policies that are available to that site collection. The policies may have been made available to the site collection template (and therefore all site collections created from this template) or to this specific site collection.</span></span>
  
1. <span data-ttu-id="803c5-127">사이트 모음의 최상위 사이트에 있는 오른쪽 위 모서리에서 **설정** [기어 아이콘] \> **사이트 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-127">In the top-level site in the site collection, in the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="803c5-128">**사이트 모음 관리** \> **문서 삭제 정책**아래에서</span><span class="sxs-lookup"><span data-stu-id="803c5-128">Under **Site Collection Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="803c5-129">사이트 모음에 정책이 할당 되지 않은 경우 **문서 삭제 정책** 링크가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-129">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="803c5-130">또한 사이트에 정책이 할당 된 직후에 링크가 표시 되지 않으며, **문서 삭제 정책** 링크가 나타나면 정책이 할당 될 때까지 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-130">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="803c5-131">이 페이지에서는 다음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-131">On this page you can view:</span></span>
    
  - <span data-ttu-id="803c5-p107">현재 할당된 정책 및 관련된 규칙. 정책을 선택하면 오른쪽 창에 규칙이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-p107">The currently assigned policies and the associated rules. Select a policy to view the rules in the right pane.</span></span>
    
  - <span data-ttu-id="803c5-134">기본 정책(있는 경우)은 **기본** 열에 **예**가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-134">The default policy, if any, displays **Yes** in the **Default** column.</span></span> 
    
  - <span data-ttu-id="803c5-135">정책이 **필수**로 할당된 경우에는 목록 아래에 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-135">A message is displayed below the list if the policy has been assigned as **Mandatory**.</span></span>
    
<span data-ttu-id="803c5-p108">이 목록은 보기 전용입니다. 사이트 모음 소유자는 사용 가능한 모든 정책 및 규칙을 볼 수 있습니다. 정책을 적용하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="803c5-p108">This list is view only, for the site collection owner to see all of the available policies and rules. To apply a policy, see the next section.</span></span>
  
![사이트 모음에 할당된 문서 삭제 정책 보기](../media/f2c0433b-2bb5-407d-a364-ae07c9627176.png)
  
## <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="803c5-139">사이트에 문서 삭제 정책 적용 또는 제거</span><span class="sxs-lookup"><span data-stu-id="803c5-139">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="803c5-140">사이트 소유자나 사이트 모음 소유자의 경우 사이트에 적용하거나 완전히 거부할 수 있는 정책이 만들어져 있을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-140">As a site owner or site collection owner, your organization may have created policies that you can either apply to your site or opt out of entirely.</span></span>
  
1. <span data-ttu-id="803c5-141">오른쪽 위 모서리에서 **설정** [기어 아이콘] \> **사이트 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-141">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="803c5-142">**사이트 관리** \> **문서 삭제 정책**아래에서</span><span class="sxs-lookup"><span data-stu-id="803c5-142">Under **Site Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="803c5-143">사이트 모음에 정책이 할당 되지 않은 경우 **문서 삭제 정책** 링크가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-143">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="803c5-144">또한 사이트에 정책이 할당 된 직후에 링크가 표시 되지 않으며, **문서 삭제 정책** 링크가 나타나면 정책이 할당 될 때까지 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-144">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="803c5-145">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-145">Do one of the following:</span></span>
    
  - <span data-ttu-id="803c5-146">**정책을 적용 하려면** 정책 \> 선택 정책 \> **저장**에서 규칙을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-146">**To apply a policy** Select a policy \> select a rule in that policy \> **Save**.</span></span>
    
    <span data-ttu-id="803c5-p110">한 사이트에서 한 번에 하나의 정책 및 규칙만 활성 상태일 수 있습니다. 조직에서 선택할 수 있는 여러 정책 및 규칙을 제공할 수도 있고 하나의 정책이나 규칙만 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-p110">Only one policy and one rule can be active in a site at one time. Your organization may provide several policies and rules to choose from, or only one policy or rule.</span></span>
    
    ![정책 선택 옵션](../media/f7c7c055-fca7-4a4f-bb97-63e35a65beac.png)
  
  - <span data-ttu-id="803c5-150">**정책을 거부 하려면 다음을 수행 합니다** . **옵트아웃 선택:** \> **저장**을 클릭 하 여 메모를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-150">**To opt out of a policy** Choose **Opt-Out: Do Note Delete** \> **Save**.</span></span>
    
    <span data-ttu-id="803c5-151">사이트 소유자는 사이트의 콘텐츠에 정책이 적용 되지 않는 것으로 확인 되는 경우 문서 삭제 정책을 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-151">As a site owner, you can opt out of a document deletion policy if you determine that the policy isn't applicable to the content in your site.</span></span> <span data-ttu-id="803c5-152">그러나 **필수**로 표시 된 정책은 거부할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-152">However, you can't opt out of a policy that has been marked as **Mandatory**.</span></span>
    
    ![옵트아웃 옵션](../media/efac709c-bef7-4a02-a09d-5bc7d2b4ec63.png)
  
## <a name="document-deletion-policies-override-other-policies"></a><span data-ttu-id="803c5-154">문서 삭제 정책은 다른 정책을 재정의함</span><span class="sxs-lookup"><span data-stu-id="803c5-154">Document deletion policies override other policies</span></span>

<span data-ttu-id="803c5-155">사이트에서 콘텐츠를 보존하거나 삭제하기 위한 다른 정책이 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-155">A site may use other policies for retaining and deleting content:</span></span>
  
- <span data-ttu-id="803c5-156">사이트 모음의 콘텐츠 형식 정책</span><span class="sxs-lookup"><span data-stu-id="803c5-156">Content type policies for the site collection.</span></span>
    
- <span data-ttu-id="803c5-157">목록 또는 라이브러리에 대한 정보 관리 정책</span><span class="sxs-lookup"><span data-stu-id="803c5-157">Information management policies for a list or library.</span></span>
    
<span data-ttu-id="803c5-158">콘텐츠 형식 정책 또는 목록이나 라이브러리에 대한 정보 관리 정책을 이미 사용하는 사이트에 문서 삭제 정책을 적용하는 경우 문서 삭제 정책이 유효한 동안 해당 정책은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-158">If you apply a document deletion policy to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the document deletion policy is in effect.</span></span> <span data-ttu-id="803c5-159">다른 정책이 무시 되 면 "이 사이트의 콘텐츠에 문서 삭제 정책이 사용 됩니다." 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-159">If other policies are ignored, you'll see the message "Content on this site uses Document Deletion Policies".</span></span>
  
<span data-ttu-id="803c5-160">즉, 사이트에서 구조화된 콘텐츠용으로 만들어진 정책(정보 관리 정책 및 콘텐츠 형식 정책)이나 구조화되지 않은 콘텐츠용으로 만들어진 정책(문서 삭제 정책)만 사용하도록 계획하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-160">This means you should plan for a site to use only policies meant for structured content (information management policies and content type policies) or unstructured content (document deletion policies), not both.</span></span> <span data-ttu-id="803c5-161">문서 삭제 정책을 선택 취소 하면 경고가 표시 되지 않으며 다른 유형의 정책은 계속 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-161">If you opt out of a document deletion policy, the warning won't be displayed and other types of policies will continue to work.</span></span>
  
<span data-ttu-id="803c5-162">사이트 정책은 문서 삭제 정책의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-162">Site policies are not affected by document deletion policies.</span></span>
  
### <a name="determine-if-content-type-policies-are-being-ignored"></a><span data-ttu-id="803c5-163">콘텐츠 형식 정책이 무시되는지 여부 확인</span><span class="sxs-lookup"><span data-stu-id="803c5-163">Determine if content type policies are being ignored</span></span>

<span data-ttu-id="803c5-164">사이트에서 콘텐츠 형식 정책을 사용하고 있으며 이러한 메시지가 표시되면 해당 정책이 더 이상 적용되지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-164">If your site was using content type policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="803c5-165">콘텐츠 형식 정책을 복원 하려면 앞에서 설명한 것 처럼 옵트아웃 (opt out) 옵션을 사용할 수 있는 경우 사이트에서 문서 삭제 정책을 제거 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-165">To restore the content type policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="803c5-166">옵트아웃 (opt out) 옵션을 선택 하지 않은 경우에는 문서 삭제 정책이 필수 이며 조직의 규정 준수 관리자에 게 문의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-166">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
1. <span data-ttu-id="803c5-167">오른쪽 위 모서리에서 **설정** [기어 아이콘] \> **사이트 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-167">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="803c5-168">**사이트 관리** \> **콘텐츠 형식 정책 서식 파일**에서</span><span class="sxs-lookup"><span data-stu-id="803c5-168">Under **Site Administration** \> **Content Type Policy Templates**.</span></span>
    
    ![문서 삭제 정책이 사용 되 고 있는 사이트에 대 한 경고](../media/4cc3d703-9aff-4695-9670-f78c291c0010.png)
  
### <a name="determine-if-information-management-policies-are-being-ignored"></a><span data-ttu-id="803c5-170">정보 관리 정책이 무시되는지 여부 확인</span><span class="sxs-lookup"><span data-stu-id="803c5-170">Determine if information management policies are being ignored</span></span>

<span data-ttu-id="803c5-171">사이트에서 정보 관리 정책을 사용하고 있으며 이러한 메시지가 표시되면 해당 정책이 더 이상 적용되지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-171">If your site was using information management policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="803c5-172">정보 관리 정책을 복원 하려면 앞에서 설명한 것 처럼 옵트아웃 (opt out) 옵션을 사용할 수 있는 경우 사이트에서 문서 삭제 정책을 제거 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-172">To restore the information management policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="803c5-173">옵트아웃 (opt out) 옵션을 선택 하지 않은 경우에는 문서 삭제 정책이 필수 이며 조직의 규정 준수 관리자에 게 문의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-173">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
- <span data-ttu-id="803c5-174">목록 또는 라이브러리 \> 의 경우 **사용 권한 및 관리** \> **정보 관리 정책 설정**아래의 리본 메뉴 **라이브러리** 탭 \> **라이브러리 설정** \> 에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803c5-174">For a list or library, on the Ribbon \> **Library** tab \> **Library Settings** \> under **Permissions and Management** \> **Information Management Policy Settings**.</span></span>
    
    ![문서 삭제 정책이 사용 되 고 있는 사이트에 대 한 경고](../media/3f043057-a741-4cd8-a165-6d139b986064.png)
  
## <a name="see-also"></a><span data-ttu-id="803c5-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="803c5-176">See also</span></span>

[<span data-ttu-id="803c5-177">문서 삭제 정책 개요</span><span class="sxs-lookup"><span data-stu-id="803c5-177">Overview of document deletion policies</span></span>](document-deletion-policies.md)
  
[<span data-ttu-id="803c5-178">문서 삭제 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="803c5-178">Create a document deletion policy</span></span>](create-a-document-deletion-policy.md)

