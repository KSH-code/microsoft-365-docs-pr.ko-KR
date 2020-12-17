---
title: Microsoft 365 그룹 이름 정책
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Microsoft 365 그룹에 대한 이름 정책을 만드는 방법을 배워야 합니다.
ms.openlocfilehash: 9bc0a4c7e1ae6ad532c97b442a2bc50880a942fc
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698678"
---
# <a name="microsoft-365-groups-naming-policy"></a><span data-ttu-id="b0c35-103">Microsoft 365 그룹 이름 정책</span><span class="sxs-lookup"><span data-stu-id="b0c35-103">Microsoft 365 groups naming policy</span></span>

<span data-ttu-id="b0c35-104">그룹 이름 정책을 사용하여 조직의 사용자가 만든 그룹에 대해 일관된 이름 전략을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-104">You can use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="b0c35-105">명명 정책은 사용자와 그룹, 구성원 자격, 지리적 지역 또는 그룹을 만든 사용자를 식별하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="b0c35-106">또한 이름 정책은 주소 책에서 그룹을 분류하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="b0c35-107">이 정책을 사용하여 특정 단어가 그룹 이름 및 별칭에 사용되지 못하도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="b0c35-108">이름 정책은 모든 그룹 워크로드(예: Outlook, Microsoft Teams, SharePoint, Planner, Yammer 등)에서 만들어진 그룹에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="b0c35-109">그룹 이름과 그룹 별칭에 모두 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="b0c35-110">이 설정은 사용자가 그룹을 만들고 기존 그룹에 대해 그룹 이름 또는 별칭을 편집할 때 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="b0c35-111">Microsoft 365 그룹 이름 정책은 Microsoft 365 그룹에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-111">A Microsoft 365 group naming policy only applies to Microsoft 365 groups.</span></span> <span data-ttu-id="b0c35-112">Exchange Online에서 만든 메일 그룹에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="b0c35-113">메일 그룹에 대한 이름 정책을 만들 수 있습니다. 메일 그룹 이름 정책 [만들기를 참조합니다.](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)</span><span class="sxs-lookup"><span data-stu-id="b0c35-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="b0c35-114">그룹 이름 정책은 다음 기능으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="b0c35-115">**접두사-접미사** 명명 정책: 접두사 또는 접미어를 사용하여 그룹의 명명 규칙(예: "US \_ My Group Engineering")을 정의할 수 \_ 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering").</span></span> <span data-ttu-id="b0c35-116">접두사/접미사는 고정 문자열 또는 [Department] 같은 사용자 특성일 수 있습니다. 이 특성은 그룹을 만드는 사용자를 기반으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="b0c35-117">**사용자 지정 차단** 단어: 사용자가 만든 그룹에서 차단되는 조직 관련 차단 단어 집합을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-117">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="b0c35-118">(예: "CEO, 급여, HR").</span><span class="sxs-lookup"><span data-stu-id="b0c35-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="b0c35-119">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b0c35-119">Licensing requirements</span></span>

<span data-ttu-id="b0c35-120">Microsoft 365 그룹에 대해 Azure AD 이름 지정 정책을 사용하려면 사용자가 소유해야 하지만 하나 이상의 Microsoft 365 그룹의 구성원인 각 고유 사용자(게스트 포함)에 대해 Azure Active Directory Premium P1 라이선스 또는 Azure AD Basic EDU 라이선스를 할당할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-120">Using Azure AD naming policy for Microsoft 365 Groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="b0c35-121">그룹 이름 정책을 만드는 관리자에게도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-121">This is also required for the administrator that creates the groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="b0c35-122">Prefix-Suffix 이름 정책</span><span class="sxs-lookup"><span data-stu-id="b0c35-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="b0c35-123">접두사와 접미사는 고정 문자열 또는 사용자 특성일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="b0c35-124">고정 문자열</span><span class="sxs-lookup"><span data-stu-id="b0c35-124">Fixed strings</span></span>

<span data-ttu-id="b0c35-125">GAL에서 그룹을 차별화하고 그룹 작업의 왼쪽 탐색을 차별화하는 데 도움이 되는 짧은 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="b0c35-126">일반적인 접두사 접미사 중 일부는 'Grp \_ Name', \# 'Name', \_ 'Name' 같은 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="b0c35-127">특성</span><span class="sxs-lookup"><span data-stu-id="b0c35-127">Attributes</span></span>

<span data-ttu-id="b0c35-128">[Department]과 같은 그룹을 만든 사용자와 [국가]에서 그룹을 만든 위치를 식별하는 데 도움이 되는 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

<span data-ttu-id="b0c35-129">예제:</span><span class="sxs-lookup"><span data-stu-id="b0c35-129">Examples:</span></span>

- <span data-ttu-id="b0c35-130">Policy = "GRP [GroupName] [Department]"</span><span class="sxs-lookup"><span data-stu-id="b0c35-130">Policy = "GRP [GroupName] [Department]"</span></span>
- <span data-ttu-id="b0c35-131">사용자의 부서 = 엔지니어링</span><span class="sxs-lookup"><span data-stu-id="b0c35-131">User's department = Engineering</span></span>
- <span data-ttu-id="b0c35-132">만든 그룹 이름 = "GRP 내 그룹 엔지니어링"</span><span class="sxs-lookup"><span data-stu-id="b0c35-132">Created group name = "GRP My Group Engineering"</span></span>

<span data-ttu-id="b0c35-133">지원되는 Azure AD(Azure Active Directory) 특성은 [부서], [회사], [Office], [StateOrProvince], [CountryOrRegion], [Title]입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="b0c35-134">지원되지 않는 사용자 특성은 고정 문자열(예: [postalCode])로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-134">Unsupported user attributes are considered as fixed strings, for example [postalCode].</span></span>

- <span data-ttu-id="b0c35-135">확장 특성 및 사용자 지정 특성은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-135">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="b0c35-136">조직의 모든 사용자에 대해 값이 채워진 특성을 사용하며 값이 더 긴 특성을 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-136">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="b0c35-137">살펴보아야 할 것</span><span class="sxs-lookup"><span data-stu-id="b0c35-137">Things to look out for</span></span>

- <span data-ttu-id="b0c35-138">정책을 만들 때 전체 접두사와 접미사 문자열 길이는 53자로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-138">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="b0c35-139">접두사와 접미사는 그룹 이름 및 그룹 별칭에서 지원되는 특수 문자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-139">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="b0c35-140">접두사와 접미사에 그룹 별칭에서 허용되지 않는 특수 문자가 포함되어 있는 경우 그룹 이름에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-140">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="b0c35-141">따라서 이 경우 그룹 이름에 적용된 접두사와 접미사는 그룹 별칭에 적용된 접두사와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-141">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b0c35-142">이름의 시작이나 끝을 제외한 그룹 이름의 아무 곳에나 기간(.) 또는 하이픈(-)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-142">A period (.) or a hyphen (-) is permitted anywhere in the group name, except at the beginning or end of the name.</span></span> <span data-ttu-id="b0c35-143">밑선(_)은 이름의 시작 또는 끝을 포함하여 그룹 이름의 아무 곳에나 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-143">An underscore (_) is permitted anywhere in the group name, including at the beginning or end of the name.</span></span>

- <span data-ttu-id="b0c35-144">Office 365 Yammer 그룹을 사용하는 경우 이름 정책에 \# @, . \[ \] \<, and \></span><span class="sxs-lookup"><span data-stu-id="b0c35-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="b0c35-145">이러한 문자가 이름 정책에 있는 경우 일반 Yammer 사용자가 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

> [!Tip]
> - <span data-ttu-id="b0c35-146">짧은 문자열을 접미사로 사용</span><span class="sxs-lookup"><span data-stu-id="b0c35-146">Use short strings as suffix.</span></span>
> - <span data-ttu-id="b0c35-147">값과 함께 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-147">Use attributes with values.</span></span>
> - <span data-ttu-id="b0c35-148">창의적이지 말고 총 이름 길이는 최대 264자입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-148">Don't be too creative, total name length has a maximum of 264 characters.</span></span>
> - <span data-ttu-id="b0c35-149">조직에서 차단된 특정 단어를 업로드하여 사용을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-149">Upload your organization specific blocked words to restrict usage.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="b0c35-150">사용자 지정 차단된 단어</span><span class="sxs-lookup"><span data-stu-id="b0c35-150">Custom blocked words</span></span>

<span data-ttu-id="b0c35-151">그룹 이름 및 별칭에서 차단될 차단된 단어의 콤보로 구분된 목록을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-151">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="b0c35-152">하위 문자열 검색은 수행하지 않습니다. 특히, 사용자가 입력한 이름과 사용자 지정 차단 단어 간의 정확한 일치는 실패를 트리거하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-152">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span>

<span data-ttu-id="b0c35-153">**다음에 대해 살펴보아야 할 사항:**</span><span class="sxs-lookup"><span data-stu-id="b0c35-153">**Things to look out for**:</span></span>

- <span data-ttu-id="b0c35-154">차단된 단어는 대소문자 미구분입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-154">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="b0c35-155">사용자가 차단된 단어를 입력하면 그룹 클라이언트에 차단된 단어가 있는 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-155">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="b0c35-156">사용되는 차단된 단어에는 문자 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-156">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="b0c35-157">차단된 단어로 설정할 수 있는 단어는 5,000개로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-157">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="b0c35-158">관리자 다시 설정</span><span class="sxs-lookup"><span data-stu-id="b0c35-158">Admin override</span></span>

<span data-ttu-id="b0c35-159">일부 관리자는 차단된 단어와 원하는 이름 규칙을 사용하여 그룹을 만들 수 있도록 모든 그룹 워크로드 및 끝점에서 이러한 정책에서 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-159">Some administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions.</span></span> <span data-ttu-id="b0c35-160">다음은 그룹 명명 정책에서 제외된 관리자 역할 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-160">The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="b0c35-161">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="b0c35-161">Global admin</span></span>

- <span data-ttu-id="b0c35-162">파트너 계층 1 지원</span><span class="sxs-lookup"><span data-stu-id="b0c35-162">Partner Tier 1 Support</span></span>

- <span data-ttu-id="b0c35-163">파트너 계층 2 지원</span><span class="sxs-lookup"><span data-stu-id="b0c35-163">Partner Tier 2 Support</span></span>

- <span data-ttu-id="b0c35-164">사용자 계정 관리자</span><span class="sxs-lookup"><span data-stu-id="b0c35-164">User account admin</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="b0c35-165">이름 정책을 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="b0c35-165">How to set up the naming policy</span></span>

<span data-ttu-id="b0c35-166">이름 정책을 설정하는 경우:</span><span class="sxs-lookup"><span data-stu-id="b0c35-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="b0c35-167">[Azure Active Directory의](https://aad.portal.azure.com) **관리 아래에서** 그룹을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0c35-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="b0c35-168">설정 **아래에서** **이름 정책 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0c35-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="b0c35-169">그룹 이름 **정책 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="b0c35-170">현재 **정책에서** 접두사나 접미사 또는 둘 다를 요구할지 선택하고 적절한 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="b0c35-171">각 **줄에 대해 특성과** **문자열을** 선택한 다음 특성 또는 문자열을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c35-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="b0c35-172">필요한 접두사와 접미사를 추가한 후 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0c35-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Azure Active Directory의 그룹 이름 정책 설정 스크린샷](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a><span data-ttu-id="b0c35-174">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b0c35-174">Related topics</span></span>

[<span data-ttu-id="b0c35-175">공동 작업 거버넌스 계획 단계별</span><span class="sxs-lookup"><span data-stu-id="b0c35-175">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="b0c35-176">공동 작업 거버넌스 계획 만들기</span><span class="sxs-lookup"><span data-stu-id="b0c35-176">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="b0c35-177">그룹 설정 구성을 위한 Azure Active Directory cmdlet</span><span class="sxs-lookup"><span data-stu-id="b0c35-177">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
