---
title: 콘텐츠를 자동으로 보존하거나 삭제하는 보존 정책에 대해 자세히 알아보기
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
description: 보존 정책을 사용하여 콘텐츠를 보존할지, 삭제할지, 아니면 보존한 다음 삭제할지 사전에 결정할 수 있습니다. 조직 전체 또는 특정 위치 또는 사용자에게 단일 정책을 적용할 수 있고 모든 콘텐츠 또는 특정 조건에 부합하는 콘텐츠에 정책을 적용할 수 있습니다.
ms.openlocfilehash: 6f518ac1ba615ca81f8e45f803d26c54b43d775b
ms.sourcegitcommit: 252b1d1d8ae735b99bf46e27c08353afc330aef3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "44231881"
---
# <a name="learn-about-retention-policies"></a><span data-ttu-id="d86ae-103">보존 정책에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="d86ae-103">Learn about retention policies</span></span>

><span data-ttu-id="d86ae-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="d86ae-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="d86ae-p101">대부분의 조직에서는 전자 메일, 문서, 인스턴트 메시지 등을 비롯하여 데이터의 양과 복잡성이 계속해서 매일 증가하고 있습니다. 이러한 정보를 효과적으로 관리하거나 제어하는 일은 다음 작업을 수행해야 하므로 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-p101">For most organizations, the volume and complexity of their data is increasing daily—email, documents, instant messages, and more. Effectively managing or governing this information is important because you need to:</span></span>
  
- <span data-ttu-id="d86ae-107">최소 기간 동안 콘텐츠를 보존하도록 요구하는 **산업 규정 및 내부 정책을 사전에 준수**합니다. 예를 들어 Sarbanes-Oxley Act는 7년 동안 특정 유형의 콘텐츠를 보존하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-107">**Comply proactively with industry regulations and internal policies** that require you to retain content for a minimum period of time—for example, the Sarbanes-Oxley Act might require you to retain certain types of content for seven years.</span></span> 
    
- <span data-ttu-id="d86ae-108">**소송 또는 보안 위반 시 위험 감소** - 더 이상 보존할 필요가 없는 오래된 콘텐츠를 영구적으로 삭제</span><span class="sxs-lookup"><span data-stu-id="d86ae-108">**Reduce your risk in the event of litigation or a security breach** by permanently deleting old content that you're no longer required to keep.</span></span> 
    
- <span data-ttu-id="d86ae-109">**조직에서 효과적이면서 좀 더 민첩하게 지식을 공유하도록 지원** - 사용자가 관련이 있는 최신 콘텐츠만 사용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-109">**Help your organization to share knowledge effectively and be more agile** by ensuring that your users work only with content that's current and relevant to them.</span></span> 
    
<span data-ttu-id="d86ae-p102">보존 정책은 이러한 모든 목표를 달성하는 데 도움을 줄 수 있습니다. 일반적으로 콘텐츠를 관리하려면 다음 두 가지 작업이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-p102">A retention policy can help you achieve all of these goals. Managing content commonly requires two actions:</span></span>
  
- <span data-ttu-id="d86ae-112">**보존** - 콘텐츠가 보존 기간이 끝나기 전에 영구적으로 삭제되지 않도록 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-112">**Retaining** content so that it can't be permanently deleted before the end of the retention period.</span></span> 
    
- <span data-ttu-id="d86ae-113">**삭제** - 보존 기간이 끝나면 콘텐츠를 영구적으로 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-113">**Deleting** content permanently at the end of the retention period.</span></span> 
    
<span data-ttu-id="d86ae-114">보존 정책을 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-114">With a retention policy, you can:</span></span>
  
- <span data-ttu-id="d86ae-115">콘텐츠를 보존할지, 삭제할지, 아니면 보존했다가 삭제할지를 사전에 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-115">Decide proactively whether to retain content, delete content, or both—retain and then delete the content.</span></span>
    
- <span data-ttu-id="d86ae-116">전체 조직 또는 특정 위치나 사용자에 단일 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-116">Apply a single policy to the entire organization or specific locations or users.</span></span>
    
- <span data-ttu-id="d86ae-117">모든 콘텐츠 또는 특정 조건을 충족하는 콘텐츠(예: 특정 키워드 또는 [특정 유형의 중요 정보](what-the-sensitive-information-types-look-for.md)를 포함하는 콘텐츠)에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-117">Apply a policy to all content or to content when it meets specific conditions, such as content containing keywords or [types of sensitive information](what-the-sensitive-information-types-look-for.md).</span></span>
    
<span data-ttu-id="d86ae-p103">콘텐츠가 보존 정책을 따르는 경우라도 콘텐츠는 원래 위치에 그대로 보존되므로 아무 것도 변경되지 않는 것과 같이, 계속해서 콘텐츠를 편집하고 사용할 수 있습니다. 그러나 보존 정책을 따르는 콘텐츠를 다른 사용자가 편집 또는 삭제한 경우에는 해당 콘텐츠에 대한 보존 정책이 적용되는 동안 원본 콘텐츠의 복사본이 보존되는 안전한 위치에 저장됩니다. 자세한 내용은 해당 페이지에서 [보존 정책이 원래 위치의 콘텐츠에 적용되는 방식](#how-a-retention-policy-works-with-content-in-place) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d86ae-p103">When content is subject to a retention policy, people can continue to edit and work with the content as if nothing's changed. The content is retained in place, in its original location. But if someone edits or deletes content that's subject to the retention policy, a copy of the original content is saved to a secure location where it's retained while the retention policy for that content is in effect. For more information, see the [How a retention policy works with content in place](#how-a-retention-policy-works-with-content-in-place) section on this page</span></span>
  
<span data-ttu-id="d86ae-122">또한 일부 조직에서는 SEC(증권 거래 위원회) 규칙 17a-4와 같은 규정을 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-122">Additionally, some organizations have to comply with regulations such as Securities and Exchange Commission (SEC) Rule 17a-4.</span></span> <span data-ttu-id="d86ae-123">해당 규정은 보존 정책이 설정된 후에 해제되거나 제한이 거의 없도록 설정될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-123">This regulation requires that after a retention policy is turned on, it cannot be turned off or made less restrictive.</span></span> <span data-ttu-id="d86ae-124">해당 요구 사항을 위해서는 **보존 잠금**을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-124">To meet this requirement, you can use **Preservation Lock**.</span></span> <span data-ttu-id="d86ae-125">정책을 잠그면 관리자를 비롯한 어느 누구도 보존 정책을 해제하거나 제한이 거의 없도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-125">After a retention policy's been locked, no one (including an administrator) can turn off the retention policy or make it less restrictive.</span></span> <span data-ttu-id="d86ae-126">자세한 내용은 해당 페이지에서 [보존 잠금을 사용하여 규정 요구 사항 준수](#use-preservation-lock-to-comply-with-regulatory-requirements) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d86ae-126">For more information, see the [Use Preservation Lock to comply with regulatory requirements](#use-preservation-lock-to-comply-with-regulatory-requirements) section on this page.</span></span>

## <a name="how-a-retention-policy-works-with-content-in-place"></a><span data-ttu-id="d86ae-127">보존 정책이 원본 위치의 콘텐츠에 작동하는 방식</span><span class="sxs-lookup"><span data-stu-id="d86ae-127">How a retention policy works with content in place</span></span>

<span data-ttu-id="d86ae-128">보존 정책에 사이트나 사서함과 같은 위치를 포함하면 콘텐츠가 원본 위치에 남아 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-128">When you include a location such as a site or mailbox in a retention policy, the content remains in its original location.</span></span> <span data-ttu-id="d86ae-129">사용자는 아무것도 변경된 사항이 없는 것처럼 계속해서 문서나 사서함을 사용하여 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-129">People can continue to work with their documents or mail as if nothing's changed.</span></span> <span data-ttu-id="d86ae-130">그러나 사용자가 보존 정책에 포함된 콘텐츠를 편집하거나 삭제하는 경우에는 해당 정책이 적용된 시점의 콘텐츠 사본이 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-130">But if they edit or delete content that's included in the retention policy, a copy of the content is retained as it existed when you applied the policy.</span></span>
  
- <span data-ttu-id="d86ae-131">SharePoint 및 OneDrive 사이트의 경우: 사본은 **자료 보존** 라이브러리에 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-131">For SharePoint and OneDrive sites: The copy is retained in the **Preservation Hold** library.</span></span> <span data-ttu-id="d86ae-132">자료 보존 라이브러리는 사이트에 대한 저장소 할당량을 사용한다는 점에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="d86ae-132">Be aware that the Preservation Hold library consumes storage quota for the site.</span></span>

- <span data-ttu-id="d86ae-133">전자 메일 및 공용 폴더의 경우: **복구 가능한 항목** 폴더에 복사본이 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-133">For email and public folders: The copy is retained in the **Recoverable Items** folder.</span></span> 

- <span data-ttu-id="d86ae-134">Teams 콘텐츠의 경우: Exchange **복구 가능한 항목** 폴더에 복사본이 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-134">For Teams content: The copy is retained in the Exchange **Recoverable Items** folder.</span></span>

- <span data-ttu-id="d86ae-135">Microsoft 365 그룹([이전 Office 365 그룹](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601))의 경우:</span><span class="sxs-lookup"><span data-stu-id="d86ae-135">For Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)):</span></span> 
    - <span data-ttu-id="d86ae-136">Exchange **복구 가능한 항목** 폴더에 그룹 사서함이 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-136">The group mailbox is retained in the Exchange **Recoverable Items** folder.</span></span>
    - <span data-ttu-id="d86ae-137">모든 사이트 콘텐츠는 **자료 보존** 라이브러리에 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-137">Any site content is retained in the **Preservation Hold** library.</span></span>

> [!NOTE]
> <span data-ttu-id="d86ae-138">자료 보존 라이브러리는 사이트의 저장소 할당량에서 제외되지 않은 저장소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-138">The Preservation Hold library consumes storage that isn't exempt from a site's storage quota.</span></span> <span data-ttu-id="d86ae-139">SharePoint 및 Microsoft 365 그룹에 대한 보존 정책을 사용하는 경우 저장소를 늘려야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-139">You might need to increase your storage when you use retention policies for SharePoint and Microsoft 365 groups.</span></span>
> 
<span data-ttu-id="d86ae-140">대부분의 사용자는 해당 보안 위치 및 보존된 콘텐츠를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-140">These secure locations and the retained content are not visible to most people.</span></span> <span data-ttu-id="d86ae-141">보존 정책을 사용하면 사용자는 해당 콘텐츠에 정책이 적용되어 있다는 사실을 알 필요도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-141">With a retention policy, people do not even need to know that their content is subject to the policy.</span></span>

<span data-ttu-id="d86ae-142">보존 정책에서 다양한 작업을 수행하는 방법에 대한 자세한 내용은 다음의 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d86ae-142">For more detailed information about how retention policies work with different workloads, see the following articles:</span></span>

- [<span data-ttu-id="d86ae-143">SharePoint 및 OneDrive의 보존 정책에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="d86ae-143">Learn about retention policies for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="d86ae-144">Microsoft Teams의 보존 정책에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="d86ae-144">Learn about retention policies for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="d86ae-145">Exchange의 보존 정책에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="d86ae-145">Learn about retention policies for Exchange</span></span>](retention-policies-exchange.md)

## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="d86ae-146">보존 원칙 또는 우선 순위</span><span class="sxs-lookup"><span data-stu-id="d86ae-146">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="d86ae-147">콘텐츠에 작업(보존, 삭제 또는 보존한 다음 삭제) 및 보존 기간이 각기 다른 여러 보존 정책이 적용되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-147">It's possible or even likely that content might have several retention policies applied to it, each with a different action (retain, delete, or retain and then delete) and retention period.</span></span> <span data-ttu-id="d86ae-148">우선 순위는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="d86ae-148">What takes precedence?</span></span> <span data-ttu-id="d86ae-149">가장 높은 수준에서 한 보존 정책으로 보존되는 콘텐츠가 다른 보존 정책으로 영구히 삭제될 수 없다는 점을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-149">At the highest level, rest assured that content being retained by one retention policy can't be permanently deleted by another retention policy.</span></span>
  
![보존 원칙 다이어그램](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
<span data-ttu-id="d86ae-151">여러 다른 보존 정책 콘텐츠에 적용되는 방식을 이해하려면 다음과 같은 보존 원칙에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-151">To understand how different retention policies are applied to content, keep these principles of retention in mind:</span></span>
  
1. <span data-ttu-id="d86ae-152">**삭제보다 보존 우선.**</span><span class="sxs-lookup"><span data-stu-id="d86ae-152">**Retention wins over deletion.**</span></span> <span data-ttu-id="d86ae-153">한 보존 정책에서는 3년 후 Exchange 전자 메일을 삭제하도록 구성하지만 다른 보존 정책에서는 5년 동안 Exchange 전자 메일을 보존한 다음 삭제하도록 구성한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-153">Suppose that one retention policy is configured to delete Exchange email after three years, but another retention policy is configured to retain Exchange email for five years and then delete it.</span></span> <span data-ttu-id="d86ae-154">3년에 도달하는 모든 콘텐츠는 삭제되고 사용자의 보기에서 숨겨지지만, 콘텐츠가 영구적으로 삭제되는 5년에 도달하기까지는 복구 가능한 항목 폴더에 여전히 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-154">Any content that reaches three years old will be deleted and hidden from the users' view, but still retained in the Recoverable Items folder until the content reaches five years old, when it is permanently deleted.</span></span> 
    
2. <span data-ttu-id="d86ae-155">**가장 긴 보존 기간 우선.**</span><span class="sxs-lookup"><span data-stu-id="d86ae-155">**The longest retention period wins.**</span></span> <span data-ttu-id="d86ae-156">콘텐츠가 콘텐츠를 보존하는 여러 보존 정책의 적용을 받는 경우 가장 긴 보존 기간이 끝날 때까지 콘텐츠는 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-156">If content is subject to multiple retention policies that retain content, it will be retained until the end of the longest retention period.</span></span> 
    
3. <span data-ttu-id="d86ae-157">**암시적 포함보다 명시적 포함 우선.**</span><span class="sxs-lookup"><span data-stu-id="d86ae-157">**Explicit inclusion wins over implicit inclusion.**</span></span> <span data-ttu-id="d86ae-158">의미는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-158">This means:</span></span> 
    
    1. <span data-ttu-id="d86ae-159">보존 설정이 포함된 보존 레이블이 사용자에 의해 수동으로 항목(예: Exchange 전자 메일 또는 OneDrive 문서)에 할당된 경우 해당 보존 레이블이 사이트 또는 사서함 수준에서 할당된 보존 정책이나 문서 라이브러리에 의해 할당된 기본 보존 레이블보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-159">If a retention label with retention settings is manually assigned by a user to an item, such as an Exchange email or OneDrive document, that retention label takes precedence over both a retention policy assigned at the site or mailbox level and a default retention label assigned by the document library.</span></span> <span data-ttu-id="d86ae-160">예를 들어 명시적 보존 레이블에서 10년 동안 콘텐츠를 보존하기로 구성하지만 사이트에 할당된 보존 정책에서 5년 동안만 콘텐츠를 보존하기로 구성한다면 보존 레이블이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-160">For example, if the explicit retention label is configured to retain content for 10 years, but the retention policy assigned to the site is configured to retain content for only five years, the retention label takes precedence.</span></span> <span data-ttu-id="d86ae-161">자동 적용 보존 레이블은 Microsoft 365에서 자동으로 적용하므로 명시적이 아니라 암시적으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-161">Auto-applied retention labels are considered implicit rather than explicit, because they're applied automatically by Microsoft 365.</span></span>
    
    2. <span data-ttu-id="d86ae-162">보존 정책에 특정 사용자의 사서함 또는 OneDrive 계정과 같이 특정 위치가 포함되는 경우 해당 보존 정책이 모든 사용자의 사서함 또는 OneDrive 계정에 적용되지만 특히 해당 사용자의 사서함을 포함하지 않는 다른 보존 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-162">If a retention policy includes a specific location, such as a specific user's mailbox or OneDrive account, that retention policy takes precedence over another retention policy that applies to all users' mailboxes or OneDrive accounts but doesn't specifically include that user's mailbox.</span></span>
    
4. <span data-ttu-id="d86ae-163">**가장 짧은 삭제 기간이 우선합니다.**</span><span class="sxs-lookup"><span data-stu-id="d86ae-163">**The shortest deletion period wins.**</span></span> <span data-ttu-id="d86ae-164">마찬가지로 콘텐츠에 보존 기간 없이 콘텐츠를 삭제하는 여러 보존 정책이 적용되는 경우 해당 콘텐츠는 가장 짧은 보존 기간이 끝나면 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-164">Similarly, if content is subject to multiple retention policies that delete content without a retention period, that content will be deleted at the end of the shortest retention period.</span></span> 
    
<span data-ttu-id="d86ae-165">보존 원칙은 위에서 아래로 균형을 깨는 흐름처럼 작동한다는 점을 이해하세요. 모든 보존 정책 또는 보존 레이블에 의해 적용되는 규칙이 하나의 수준에서 동일한 경우 규칙이 적용되는 우선 순위를 결정하기 위해 흐름은 다음 수준으로 아래로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-165">Understand that the principles of retention work as a tie-breaking flow from top to bottom: If the rules applied by all retention policies or retention labels are the same at one level, the flow moves down to the next level to determine precedence for which rule is applied.</span></span>
  
<span data-ttu-id="d86ae-166">마지막으로, 보존 정책 또는 보존 레이블은 eDiscovery에 대해 보류된 모든 콘텐츠를 영구히 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-166">Finally, a retention policy or retention label cannot permanently delete any content that's on hold for eDiscovery.</span></span> <span data-ttu-id="d86ae-167">보류가 해제되면 콘텐츠는 다시 위에서 설명한 정리 프로세스의 적용을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-167">When the hold is released, the content again becomes eligible for the cleanup process described above.</span></span>

## <a name="use-preservation-lock-to-comply-with-regulatory-requirements"></a><span data-ttu-id="d86ae-168">보존 잠금을 사용하여 규정 요구 사항을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-168">Use Preservation Lock to comply with regulatory requirements</span></span>

<span data-ttu-id="d86ae-169">일부 조직에서는 보존 정책을 설정한 후에 해제하거나 제한 사항이 거의 없이 설정할 수 없는 SEC(증권 거래 위원회) 규칙 17a-4와 같은 규제 기구에서 정의한 규칙을 준수해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-169">Some organizations might need to comply with rules defined by regulatory bodies such as the Securities and Exchange Commission (SEC) Rule 17a-4, which requires that after a retention policy is turned on, it cannot be turned off or made less restrictive.</span></span> 

<span data-ttu-id="d86ae-170">보존 잠금은 조직이 관리자를 비롯하여 어떠한 사용자도 정책을 해제하거나 제한 사항이 거의 없이 설정할 수 없도록 보존 정책을 잠그기 때문에 관련 규정 요구 사항을 충족할 수 있도록 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-170">Preservation Lock ensures your organization can meet such regulatory requirements because it locks a retention policy so that no one—including the administrator—can turn off the policy or make it less restrictive.</span></span>
  
<span data-ttu-id="d86ae-171">보존 정책이 잠기는 경우:</span><span class="sxs-lookup"><span data-stu-id="d86ae-171">When a retention policy is locked:</span></span>

- <span data-ttu-id="d86ae-172">누구도 해당 정책을 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-172">No one can it turn off</span></span>
- <span data-ttu-id="d86ae-173">위치는 추가할 수 있지만 제거할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-173">Locations can be added but not removed</span></span> 
- <span data-ttu-id="d86ae-174">보존 기간 동안에 해당 정책이 적용된 콘텐츠를 수정하거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-174">Content subject to the policy can't be modified or deleted during the retention period</span></span>
- <span data-ttu-id="d86ae-175">보존 기간을 연장할 수 있지만 줄일 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-175">You can extend a retention period but not decrease it</span></span>

<span data-ttu-id="d86ae-176">요약하면 잠겨 있는 정책은 늘리거나 확장할 수 있지만 줄이거나 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-176">In summary, a locked retention policy can be increased or extended, but it can't be reduced or turned off.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d86ae-177">보존 정책을 잠그기 전에 해당 정책의 영향을 이해하고 조직에서 규정 준수 요구 사항을 충족하는 데 해당 정책이 필요한 지 여부를 확인하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-177">Before you lock a retention policy, it's critical that you understand the impact and confirm whether it's required for your organization to meet compliance requirements.</span></span>

## <a name="releasing-a-retention-policy"></a><span data-ttu-id="d86ae-178">보존 정책 해제</span><span class="sxs-lookup"><span data-stu-id="d86ae-178">Releasing a retention policy</span></span>

<span data-ttu-id="d86ae-179">보존 정책에 보존 잠금이 없으면 언제든지 보존 정책을 끄거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-179">Providing your retention policy doesn't have a Preservation Lock, you can turn off or delete a retention policy at any time.</span></span> 

<span data-ttu-id="d86ae-180">이렇게 하면 자료 보존 라이브러리에 보존되어 있는 모든 SharePoint 또는 OneDrive 콘텐츠가 바로 영구적으로 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-180">When you do so, any SharePoint or OneDrive content that's being retained in the Preservation Hold library is not immediately and permanently deleted.</span></span> <span data-ttu-id="d86ae-181">실수로 데이터가 손실되는 것을 방지하기 위해 30일간의 유예 기간이 있습니다. 이 기간에는 자료 보존 라이브러리에서 해당 정책에 대한 콘텐츠 만료가 발생하지 않으므로 필요한 경우 콘텐츠를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-181">Instead, to help prevent inadvertent data loss, there is a 30-day grace period, during which content expiration for that policy does not happen in the Preservation Hold library, so that you can restore any content from there, if needed.</span></span> 

<span data-ttu-id="d86ae-182">또한 유예 기간 동안 보존 정책을 다시 켜면 해당 정책에 대한 콘텐츠가 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-182">You can also turn on the retention policy again during the grace period, and no content will be deleted for that policy.</span></span>

<span data-ttu-id="d86ae-183">SharePoint 및 OneDrive의 30일간의 유예 기간은 Exchange의 30일 지연 기간에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-183">This 30-day grace period in SharePoint and OneDrive corresponds to the 30-day delay hold in Exchange.</span></span> <span data-ttu-id="d86ae-184">자세한 내용은 [지연되는 사서함 관리](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d86ae-184">For more information, see [Managing mailboxes on delay hold](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

## <a name="use-a-retention-policy-instead-of-older-features"></a><span data-ttu-id="d86ae-185">이전 기능 대신 보존 정책 사용</span><span class="sxs-lookup"><span data-stu-id="d86ae-185">Use a retention policy instead of older features</span></span>

<span data-ttu-id="d86ae-186">조직 전체 및 Exchange Online, SharePoint Online, OneDrive 및 Microsoft 365 그룹을 비롯하여 Microsoft 365 전체 위치에 손쉽게 단일 보존 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-186">A single retention policy can easily apply to an entire organization and locations across Microsoft 365, including Exchange Online, SharePoint Online, OneDrive, and Microsoft 365 groups.</span></span> <span data-ttu-id="d86ae-187">Microsoft 365의 어느 곳에서든 콘텐츠를 보존하거나 삭제하려는 경우에는 보존 정책을 사용하고 필요에 따라 이를 [보존 레이블](labels.md)과 함께 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-187">If you need to retain or delete content anywhere in Microsoft 365, we recommend that you use a retention policy and optionally supplement this with [retention labels](labels.md).</span></span>
  
<span data-ttu-id="d86ae-188">이전에 Microsoft 365에서 다른 구성을 사용하여 콘텐츠를 보존하거나 삭제한 경우 보존 정책 및 보존 레이블과 함께 계속해서 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-188">If you have previously used other configurations to retain or delete content in Microsoft 365, they will continue to work side by side with retention policies and retention labels.</span></span> <span data-ttu-id="d86ae-189">하지만 앞으로는 보존 정책 및 보존 레이블을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-189">However, we recommend that going forward, you use retention policies and retention labels instead.</span></span> <span data-ttu-id="d86ae-190">Microsoft 365 전체에서 콘텐츠의 보존 및 삭제를 중앙에서 관리하는 단일 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-190">They provide you with a single mechanism to centrally manage both retention and deletion of content across Microsoft 365.</span></span>

<span data-ttu-id="d86ae-191">사용했을 수도 있는 이전 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-191">The older features that you might have used:</span></span>
  
<span data-ttu-id="d86ae-192">**Exchange Online의 이전 기능:**</span><span class="sxs-lookup"><span data-stu-id="d86ae-192">**Older features from Exchange Online:**</span></span>

- <span data-ttu-id="d86ae-193">[Office 365 보안 및 준수 센터에서 eDiscovery 사례 관리](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)(eDiscovery 보류)</span><span class="sxs-lookup"><span data-stu-id="d86ae-193">[Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery) (eDiscovery hold)</span></span> 
    
- <span data-ttu-id="d86ae-194">[원본 위치 유지 및 소송 보존](https://go.microsoft.com/fwlink/?linkid=846124)(eDiscovery 보류)</span><span class="sxs-lookup"><span data-stu-id="d86ae-194">[In-Place Hold and Litigation Hold](https://go.microsoft.com/fwlink/?linkid=846124) (eDiscovery hold)</span></span> 

- [<span data-ttu-id="d86ae-195">Exchange Online 사서함의 보류 유형을 식별하는 방법</span><span class="sxs-lookup"><span data-stu-id="d86ae-195">How to identify the type of hold placed on an Exchange Online mailbox</span></span>](identify-a-hold-on-an-exchange-online-mailbox.md)
    
- <span data-ttu-id="d86ae-196">[MRM(메시징 레코드 관리)](https://go.microsoft.com/fwlink/?linkid=846126)이라고도 하는 [보존 태그 및 보존 정책](https://go.microsoft.com/fwlink/?linkid=846125) (삭제만 해당)</span><span class="sxs-lookup"><span data-stu-id="d86ae-196">[Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (deletion only)</span></span>
    
<span data-ttu-id="d86ae-197">**SharePoint 및 OneDrive의 이전 기능:**</span><span class="sxs-lookup"><span data-stu-id="d86ae-197">**Older features from SharePoint and OneDrive:**</span></span>

- <span data-ttu-id="d86ae-198">[Office 365 보안 및 준수 센터에서 eDiscovery 사례 관리](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)(eDiscovery 보류)</span><span class="sxs-lookup"><span data-stu-id="d86ae-198">[Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery) (eDiscovery hold)</span></span> 
    
- <span data-ttu-id="d86ae-199">[eDiscovery 센터에서 사례에 콘텐츠 추가 및 원본 우 위치 유지](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center)(eDiscovery 보류)</span><span class="sxs-lookup"><span data-stu-id="d86ae-199">[Add content to a case and place sources on hold in the eDiscovery Center](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (eDiscovery hold)</span></span> 
    
- <span data-ttu-id="d86ae-200">[문서 삭제 정책 개요](https://docs.microsoft.com/microsoft-365/compliance/document-deletion-policies) (삭제만 해당)</span><span class="sxs-lookup"><span data-stu-id="d86ae-200">[Overview of document deletion policies](https://docs.microsoft.com/microsoft-365/compliance/document-deletion-policies) (deletion only)</span></span> 
    
- <span data-ttu-id="d86ae-201">[현재 위치 레코드 관리 구성](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (보존만 해당)</span><span class="sxs-lookup"><span data-stu-id="d86ae-201">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (retention only)</span></span> 
    
- <span data-ttu-id="d86ae-202">[사이트 폐쇄 및 삭제에 대한 정책 사용](https://support.microsoft.com/ko-KR/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (삭제만 해당)</span><span class="sxs-lookup"><span data-stu-id="d86ae-202">[Use policies for site closure and deletion](https://support.microsoft.com/ko-KR/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (deletion only)</span></span> 
    
- <span data-ttu-id="d86ae-203">[정보 관리 정책](intro-to-info-mgmt-policies.md) (삭제만 해당)</span><span class="sxs-lookup"><span data-stu-id="d86ae-203">[Information management policies](intro-to-info-mgmt-policies.md) (deletion only)</span></span>
     
<span data-ttu-id="d86ae-204">이전에 정보 거버넌스 용도로 eDiscovery 보류를 사용한 적이 있는 경우 사전 규정 준수를 위해 보존 정책을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-204">If you've previously used any of the eDiscovery holds for the purpose of information governance, for proactive compliance, use a retention policy instead.</span></span> <span data-ttu-id="d86ae-205">보류 전용으로 eDiscovery를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-205">Use eDiscovery for holds only.</span></span>
  
### <a name="retention-policies-and-sharepoint-content-type-policies-or-information-management-policies"></a><span data-ttu-id="d86ae-206">보존 정책 및 SharePoint 콘텐츠 유형 정책 또는 정보 관리 정책</span><span class="sxs-lookup"><span data-stu-id="d86ae-206">Retention policies and SharePoint content type policies or information management policies</span></span>

<span data-ttu-id="d86ae-207">콘텐츠 유형 정책 또는 정보 관리 정책에 대해 SharePoint 사이트를 구성하여 목록이나 라이브러리에 대한 콘텐츠를 보존하는 경우 보존 정책이 유효하는 동안 해당 정책은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-207">If you have configured SharePoint sites for content type policies or information management policies to retain content for a list or library, those policies are ignored while a retention policy is in effect.</span></span> 
  
### <a name="preservation-policies-are-converted-to-retention-policies"></a><span data-ttu-id="d86ae-208">보류 정책을 보존 정책으로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-208">Preservation policies are converted to retention policies</span></span>

<span data-ttu-id="d86ae-209">보류 정책을 사용하여 사서함, SharePoint 또는 OneDrive 사이트, 공용 폴더에서 데이터를 보존하는 경우 해당 정책은 보존 작업을 전용으로 하는 보존 정책으로 자동 전환됩니다. 해당 보존 정책은 콘텐츠를 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-209">If you were using a preservation policy to retain data in mailboxes, SharePoint or OneDrive sites, or public folders: That policy has been automatically converted to a retention policy that uses only the retain action—the policy won't delete content.</span></span> <span data-ttu-id="d86ae-210">구성된 보류 정책과 동일한 결과에 대해 변경 사항은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-210">No changes are needed from you for the same outcome as your configured preservation policy.</span></span>

<span data-ttu-id="d86ae-211">구성된 보류 정책은 [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)의 **정책** 페이지나 [보안 &amp; 규정 준수 센터](https://protection.office.com/)의 **정보 거버넌스** 아래 **보존** 페이지에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-211">You can find any configured preservation policies on the **Policies** page in the [Microsoft 365 compliance center](https://compliance.microsoft.com/), or on the **Retention** page under **Information governance** in the [Security &amp; Compliance Center](https://protection.office.com/).</span></span> <span data-ttu-id="d86ae-212">보류 정책을 편집하여 보존 기간을 변경할 수 있지만 위치를 추가하거나 제거하는 등의 다른 변경은 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d86ae-212">You can edit a preservation policy to change the retention period, but you can't make other changes, such as adding or removing locations.</span></span> 


## <a name="related-information"></a><span data-ttu-id="d86ae-213">관련 정보</span><span class="sxs-lookup"><span data-stu-id="d86ae-213">Related information</span></span>

- [<span data-ttu-id="d86ae-214">보존 정책 생성 및 구성</span><span class="sxs-lookup"><span data-stu-id="d86ae-214">Create and configure retention policies</span></span>](create-retention-policies.md)
- [<span data-ttu-id="d86ae-215">보존 레이블에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="d86ae-215">Learn about retention labels</span></span>](labels.md)
- [<span data-ttu-id="d86ae-216">SharePoint Online 제한 사항</span><span class="sxs-lookup"><span data-stu-id="d86ae-216">SharePoint Online Limits</span></span>](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [<span data-ttu-id="d86ae-217">Microsoft Teams의 제한 사항 및 사양</span><span class="sxs-lookup"><span data-stu-id="d86ae-217">Limits and specifications for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [<span data-ttu-id="d86ae-218">SEC 규칙 17a-4 준수</span><span class="sxs-lookup"><span data-stu-id="d86ae-218">Comply with SEC Rule 17a-4</span></span>](use-exchange-online-to-comply-with-sec-rule-17a-4.md)
