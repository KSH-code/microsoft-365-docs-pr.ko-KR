---
title: Microsoft 365 그룹 명명 정책
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
- Adm_TOC
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Microsoft 365 그룹에 대 한 명명 정책을 만드는 방법을 알아봅니다.
ms.openlocfilehash: 0072abf4f249af544e8234fdedec584a71c214a7
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662768"
---
# <a name="microsoft-365-groups-naming-policy"></a><span data-ttu-id="2fa96-103">Microsoft 365 그룹 명명 정책</span><span class="sxs-lookup"><span data-stu-id="2fa96-103">Microsoft 365 groups naming policy</span></span>

<span data-ttu-id="2fa96-104">그룹 명명 정책을 사용 하 여 조직의 사용자가 만든 그룹에 대 한 일관 된 명명 전략을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-104">You can use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="2fa96-105">명명 정책을 통해 그룹, 구성원, 지리적 위치 또는 그룹을 만든 사용자의 기능을 식별 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="2fa96-106">또한 명명 정책은 주소록의 그룹을 분류 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="2fa96-107">정책을 사용 하 여 그룹 이름 및 별칭에 특정 단어를 사용 하지 못하도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="2fa96-108">명명 정책은 모든 그룹 작업 (예: Outlook, Microsoft 팀, SharePoint, Planner, Yammer 등)에 걸쳐 만들어지는 그룹에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="2fa96-109">그룹 이름과 그룹 별칭에 모두 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="2fa96-110">사용자가 그룹을 만들 때와 기존 그룹에 대 한 그룹 이름 또는 별칭을 편집한 경우에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="2fa96-111">Microsoft 365 그룹 명명 정책은 Microsoft 365 그룹에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-111">A Microsoft 365 group naming policy only applies to Microsoft 365 groups.</span></span> <span data-ttu-id="2fa96-112">Exchange Online에서 만든 메일 그룹에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="2fa96-113">메일 그룹에 대 한 명명 정책을 만들려면 [메일 그룹 명명 정책 만들기](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2fa96-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="2fa96-114">그룹 명명 정책은 다음과 같은 기능으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="2fa96-115">**접두사 접미사 명명 정책**: 접두사 또는 접미사를 사용 하 여 그룹 명명 규칙을 정의할 수 있습니다 (예: "US \_ My Group \_ 엔지니어링").</span><span class="sxs-lookup"><span data-stu-id="2fa96-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering").</span></span> <span data-ttu-id="2fa96-116">접두사/접미사는 고정 문자열이 나 [부서]와 같은 사용자 특성으로, 그룹을 만드는 사용자에 따라 대체 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="2fa96-117">**사용자 지정 차단 된 단어**: 사용자가 만든 그룹에서 차단 되는 조직에 대 한 차단 되는 단어 집합을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-117">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="2fa96-118">(예: "CEO, 급여, HR").</span><span class="sxs-lookup"><span data-stu-id="2fa96-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="2fa96-119">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2fa96-119">Licensing requirements</span></span>

<span data-ttu-id="2fa96-120">Microsoft 365 그룹에 대해 Azure AD 명명 정책을 사용 하려면 하나 이상의 Microsoft 365 그룹 구성원 인 각 고유 사용자 (게스트 포함)에 대해 Azure Active Directory Premium P1 라이선스 또는 Azure AD Basic .EDU 라이선스를 소유 하 고 있지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-120">Using Azure AD naming policy for Microsoft 365 Groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="2fa96-121">이는 그룹 명명 정책을 만드는 관리자 에게도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-121">This is also required for the administrator that creates the groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="2fa96-122">접두사 접미사 명명 정책</span><span class="sxs-lookup"><span data-stu-id="2fa96-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="2fa96-123">접두사와 접미사는 고정 문자열이 나 사용자 특성 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="2fa96-124">고정 문자열</span><span class="sxs-lookup"><span data-stu-id="2fa96-124">Fixed strings</span></span>

<span data-ttu-id="2fa96-125">그룹 작업의 GAL 및 왼쪽 탐색 창에 있는 그룹을 구별 하는 데 도움이 되는 짧은 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="2fa96-126">일반적인 접두사 접미사 중 일부는 ' Grp \_ Name ', ' \# name ', ' \_ name '과 같은 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="2fa96-127">특성만</span><span class="sxs-lookup"><span data-stu-id="2fa96-127">Attributes</span></span>

<span data-ttu-id="2fa96-128">[부서] 그룹과 같은 그룹을 만든 사람과이를 [Country] like에서 만든 위치를 식별 하는 데 도움이 되는 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

<span data-ttu-id="2fa96-129">예제:</span><span class="sxs-lookup"><span data-stu-id="2fa96-129">Examples:</span></span>

- <span data-ttu-id="2fa96-130">Policy = "GRP [GroupName] [부서]"</span><span class="sxs-lookup"><span data-stu-id="2fa96-130">Policy = "GRP [GroupName] [Department]"</span></span>
- <span data-ttu-id="2fa96-131">사용자의 부서 = 공학</span><span class="sxs-lookup"><span data-stu-id="2fa96-131">User's department = Engineering</span></span>
- <span data-ttu-id="2fa96-132">만든 그룹 이름 = "그룹 엔지니어링 그룹화"</span><span class="sxs-lookup"><span data-stu-id="2fa96-132">Created group name = "GRP My Group Engineering"</span></span>

<span data-ttu-id="2fa96-133">지원 되는 Azure Active Directory (Azure AD) 특성은 [부서], [Company], [Office], [StateOrProvince], [CountryOrRegion] 및 [Title]입니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="2fa96-134">지원 되지 않는 사용자 특성은 고정 문자열로 간주 됩니다 (예: [postalCode]).</span><span class="sxs-lookup"><span data-stu-id="2fa96-134">Unsupported user attributes are considered as fixed strings, for example [postalCode].</span></span>

- <span data-ttu-id="2fa96-135">Extension 특성 및 사용자 지정 특성은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-135">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="2fa96-136">조직의 모든 사용자에 대해 값이 채워진 특성을 사용 하 고 값이 더 긴 특성을 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-136">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="2fa96-137">검색할 사항</span><span class="sxs-lookup"><span data-stu-id="2fa96-137">Things to look out for</span></span>

- <span data-ttu-id="2fa96-138">정책 생성 중 총 접두사 및 접미사 문자열 길이는 53 자로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-138">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="2fa96-139">접두사와 접미사는 그룹 이름 및 그룹 별칭에서 지원 되는 특수 문자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-139">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="2fa96-140">접두사 및 접미사에 그룹 별칭에서 허용 되지 않는 특수 문자가 포함 되어 있으면 그룹 이름에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-140">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="2fa96-141">따라서 그룹 이름에 적용 되는 접두사와 접미사는 그룹 별칭에 적용 된 접두 번호와 접미사가 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-141">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

  > [!NOTE]
  > <span data-ttu-id="2fa96-142">이름을 시작 하거나 끝낼 때를 제외 하 고 그룹 이름의 모든 위치에서 마침표 (.) 또는 하이픈 (-)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-142">A period (.) or a hyphen (-) is permitted anywhere in the group name, except at the beginning or end of the name.</span></span> <span data-ttu-id="2fa96-143">이름 시작 부분이 나 끝 부분을 포함 하 여 그룹 이름의 모든 위치에서 밑줄 (_)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-143">An underscore (_) is permitted anywhere in the group name, including at the beginning or end of the name.</span></span>

- <span data-ttu-id="2fa96-144">Yammer Office 365 연결 된 그룹을 사용 하는 경우에는 이름 지정 정책에서 @,,,,에 다음 문자를 사용 하지 않도록 \# \[ \] \<, and \> 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="2fa96-145">이러한 문자가 이름 지정 정책에 있는 경우 일반 Yammer 사용자는 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

> [!Tip]
> - <span data-ttu-id="2fa96-146">짧은 문자열을 접미사로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-146">Use short strings as suffix.</span></span>
> - <span data-ttu-id="2fa96-147">값과 함께 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-147">Use attributes with values.</span></span>
> - <span data-ttu-id="2fa96-148">창의적인 작업이 너무 많으면 총 이름 길이는 최대 264 자입니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-148">Don't be too creative, total name length has a maximum of 264 characters.</span></span>
> - <span data-ttu-id="2fa96-149">조직의 특정 차단 된 단어를 업로드 하 여 사용을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-149">Upload your organization specific blocked words to restrict usage.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="2fa96-150">사용자 지정 차단 된 단어</span><span class="sxs-lookup"><span data-stu-id="2fa96-150">Custom blocked words</span></span>

<span data-ttu-id="2fa96-151">그룹 이름 및 별칭에서 차단 되는 차단 된 단어의 쉼표로 구분 된 목록을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-151">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="2fa96-152">하위 문자열 검색은 수행 되지 않습니다. 특히 오류를 발생 시키려면 사용자가 입력 한 이름과 사용자 지정 차단 된 단어 사이에 정확 하 게 일치 하는 이름이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-152">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span>

<span data-ttu-id="2fa96-153">다음 **항목을 확인 해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="2fa96-153">**Things to look out for**:</span></span>

- <span data-ttu-id="2fa96-154">차단 된 단어는 대/소문자를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-154">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="2fa96-155">사용자가 차단 된 단어를 입력 하면 그룹 클라이언트는 차단 된 단어와 함께 오류 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-155">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="2fa96-156">차단 된 단어에는 문자 제한이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-156">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="2fa96-157">차단 된 단어로 설정할 수 있는 5000 단어는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-157">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="2fa96-158">관리 재정의</span><span class="sxs-lookup"><span data-stu-id="2fa96-158">Admin override</span></span>

<span data-ttu-id="2fa96-159">일부 관리자는 모든 그룹 작업 및 끝점에서 이러한 정책에 의해 제외 되므로 이러한 차단 된 단어를 사용 하 여 그룹을 만들고 원하는 명명 규칙을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-159">Some administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions.</span></span> <span data-ttu-id="2fa96-160">다음은 그룹 명명 정책에서 제외 된 관리자 역할 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-160">The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="2fa96-161">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="2fa96-161">Global admin</span></span>

- <span data-ttu-id="2fa96-162">파트너 계층 1 지원</span><span class="sxs-lookup"><span data-stu-id="2fa96-162">Partner Tier 1 Support</span></span>

- <span data-ttu-id="2fa96-163">파트너 계층 2 지원</span><span class="sxs-lookup"><span data-stu-id="2fa96-163">Partner Tier 2 Support</span></span>

- <span data-ttu-id="2fa96-164">사용자 계정 관리자</span><span class="sxs-lookup"><span data-stu-id="2fa96-164">User account admin</span></span>

- <span data-ttu-id="2fa96-165">디렉터리 작성자</span><span class="sxs-lookup"><span data-stu-id="2fa96-165">Directory writers</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="2fa96-166">명명 정책을 설정 하는 방법</span><span class="sxs-lookup"><span data-stu-id="2fa96-166">How to set up the naming policy</span></span>

<span data-ttu-id="2fa96-167">명명 정책을 설정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-167">To set up a naming policy:</span></span>

1. <span data-ttu-id="2fa96-168">[Azure Active Directory](https://aad.portal.azure.com)의 **관리**에서 **그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-168">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="2fa96-169">**설정**아래에서 **이름 지정 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-169">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="2fa96-170">**그룹 명명 정책** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-170">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="2fa96-171">**현재 정책**에서 접두사 또는 접미사를 필요한 경우 또는 둘 다를 선택 하 고 해당 하는 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-171">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="2fa96-172">각 줄에 대해 **특성** 및 **문자열** 을 선택한 다음 특성 또는 문자열을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-172">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="2fa96-173">필요한 접두 번호와 접미사를 추가한 후 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa96-173">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Azure Active Directory의 그룹 명명 정책 설정 스크린샷](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a><span data-ttu-id="2fa96-175">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2fa96-175">Related topics</span></span>

[<span data-ttu-id="2fa96-176">그룹 설정 구성을 위한 Azure Active Directory cmdlet</span><span class="sxs-lookup"><span data-stu-id="2fa96-176">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
