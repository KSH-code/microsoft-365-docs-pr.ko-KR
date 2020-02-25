---
title: Office 365 그룹 명명 정책
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Office 365 그룹에 대 한 명명 정책을 만드는 방법을 알아봅니다.
ms.openlocfilehash: 50ea076e22680a444cb9acf04466a7e7d052bb7a
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245490"
---
# <a name="office-365-groups-naming-policy"></a><span data-ttu-id="456f6-103">Office 365 그룹 명명 정책</span><span class="sxs-lookup"><span data-stu-id="456f6-103">Office 365 Groups naming policy</span></span>

<span data-ttu-id="456f6-104">그룹 명명 정책을 사용 하 여 조직의 사용자가 만든 그룹에 대 한 일관 된 명명 전략을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-104">You use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="456f6-105">명명 정책을 통해 그룹, 구성원, 지리적 위치 또는 그룹을 만든 사용자의 기능을 식별 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="456f6-106">또한 명명 정책은 주소록의 그룹을 분류 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="456f6-107">정책을 사용 하 여 그룹 이름 및 별칭에 특정 단어를 사용 하지 못하도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="456f6-108">명명 정책은 모든 그룹 작업 (예: Outlook, Microsoft 팀, SharePoint, Planner, Yammer 등)에 걸쳐 만들어지는 그룹에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc).</span></span> <span data-ttu-id="456f6-109">그룹 이름과 그룹 별칭에 모두 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="456f6-110">사용자가 그룹을 만들 때와 기존 그룹에 대 한 그룹 이름 또는 별칭을 편집한 경우에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="456f6-111">Office 365 그룹 명명 정책은 Office 365 그룹에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-111">An Office 365 group naming policy only applies to Office 365 Groups.</span></span> <span data-ttu-id="456f6-112">Exchange Online에서 만든 메일 그룹에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="456f6-113">메일 그룹에 대 한 명명 정책을 만들려면 [메일 그룹 명명 정책 만들기](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="456f6-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="456f6-114">그룹 명명 정책은 다음과 같은 기능으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="456f6-115">**접두사 접미사 명명 정책**: 접두사 또는 접미사를 사용 하 여 그룹 명명 규칙을 정의할 수 있습니다 (예: "GRP\_US\_내 그룹\_엔지니어링").</span><span class="sxs-lookup"><span data-stu-id="456f6-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "GRP\_US\_My Group\_Engineering").</span></span> <span data-ttu-id="456f6-116">접두사/접미사는 고정 문자열이 나 [부서]와 같은 사용자 특성으로, 그룹을 만드는 사용자에 따라 대체 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="456f6-117">**사용자 지정 차단 된 단어**: 사용자가 만든 그룹에서 차단 되는 조직에 대 한 차단 되는 단어 집합을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-117">**Custom Blocked Words**: You can upload a set of blocked words specific to their organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="456f6-118">(예: "CEO, 급여, HR").</span><span class="sxs-lookup"><span data-stu-id="456f6-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="456f6-119">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="456f6-119">Licensing requirements</span></span>

<span data-ttu-id="456f6-120">Office 365 그룹에 대해 Azure AD 명명 정책을 사용 하려면 하나 이상의 Office 365 그룹 구성원 인 각 고유 사용자 (게스트 포함)에 대해 Azure Active Directory Premium P1 라이선스 또는 Azure AD Basic .EDU 라이선스를 소유 하 고 있지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-120">Using Azure AD naming policy for Office 365 groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Office 365 groups.</span></span>
<span data-ttu-id="456f6-121">이는 그룹 명명 정책을 만드는 관리자 에게도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-121">This is also required for the administrator that creates the Groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="456f6-122">접두사 접미사 명명 정책</span><span class="sxs-lookup"><span data-stu-id="456f6-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="456f6-123">접두사와 접미사는 고정 문자열이 나 사용자 특성 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="456f6-124">고정 문자열</span><span class="sxs-lookup"><span data-stu-id="456f6-124">Fixed strings</span></span>

<span data-ttu-id="456f6-125">그룹 작업의 GAL 및 왼쪽 탐색 창에 있는 그룹을 구별 하는 데 도움이 되는 짧은 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-125">You can use short strings that can help you differentiate groups in the GAL and Left nav of the group workloads.</span></span> <span data-ttu-id="456f6-126">일반적인 접두사 접미사 중 일부는 ' Grp\_Name ', '\#name ', '\_name '과 같은 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-126">Some of the common prefixes suffixes are Keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="456f6-127">특성만</span><span class="sxs-lookup"><span data-stu-id="456f6-127">Attributes</span></span>

<span data-ttu-id="456f6-128">[부서] 그룹과 같은 그룹을 만든 사람과이를 [Country] like에서 만든 위치를 식별 하는 데 도움이 되는 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="456f6-129">**예제**</span><span class="sxs-lookup"><span data-stu-id="456f6-129">**Examples**</span></span>|<span data-ttu-id="456f6-130">Policy = "GRP [GroupName] [부서]"</span><span class="sxs-lookup"><span data-stu-id="456f6-130">Policy = "GRP [GroupName] [Department]"</span></span>|
||<span data-ttu-id="456f6-131">사용자의 부서 = 공학</span><span class="sxs-lookup"><span data-stu-id="456f6-131">User's department = Engineering</span></span>|
||<span data-ttu-id="456f6-132">만든 그룹 이름 = "그룹 엔지니어링 그룹화"</span><span class="sxs-lookup"><span data-stu-id="456f6-132">Created group name = "GRP My Group Engineering"</span></span>|

<span data-ttu-id="456f6-133">지원 되는 Azure Active Directory (Azure AD) 특성은 [부서], [Company], [Office], [StateOrProvince], [CountryOrRegion], [Title]입니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], [Title]</span></span>

- <span data-ttu-id="456f6-134">지원 되지 않는 사용자 특성은 고정 문자열로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-134">Unsupported user attributes are considered as fixed strings.</span></span> <span data-ttu-id="456f6-135">예:.</span><span class="sxs-lookup"><span data-stu-id="456f6-135">E.g.</span></span> <span data-ttu-id="456f6-136">"[postalCode]"</span><span class="sxs-lookup"><span data-stu-id="456f6-136">"[postalCode]"</span></span>

- <span data-ttu-id="456f6-137">Extension 특성 및 사용자 지정 특성은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-137">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="456f6-138">조직의 모든 사용자에 대해 값이 채워진 특성을 사용 하 고 값이 더 긴 특성을 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-138">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="456f6-139">검색할 사항</span><span class="sxs-lookup"><span data-stu-id="456f6-139">Things to look out for</span></span>

- <span data-ttu-id="456f6-140">정책 생성 중 총 접두사 및 접미사 문자열 길이는 53 자로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-140">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="456f6-141">접두사와 접미사는 그룹 이름 및 그룹 별칭에서 지원 되는 특수 문자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-141">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="456f6-142">접두사 및 접미사에 그룹 별칭에서 허용 되지 않는 특수 문자가 포함 되어 있으면 그룹 별칭에 해당 문자를 제거 하 고 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-142">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are removed and applied to the group alias.</span></span> <span data-ttu-id="456f6-143">따라서 그룹 이름에 적용 되는 접두사와 접미사는 그룹 별칭에 적용 된 접두 번호와 접미사가 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-143">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

- <span data-ttu-id="456f6-144">Yammer \#Office 365 연결 된 그룹을 사용 하는 경우에는 이름 지정 정책에 @,, \[ \] \<, 및와 \>같은 문자를 사용 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="456f6-145">이러한 문자가 이름 지정 정책에 있는 경우 일반 Yammer 사용자는 그룹을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="456f6-146">사용자 지정 차단 된 단어</span><span class="sxs-lookup"><span data-stu-id="456f6-146">Custom blocked words</span></span>

<span data-ttu-id="456f6-147">그룹 이름 및 별칭에서 차단 되는 차단 된 단어의 쉼표로 구분 된 목록을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-147">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="456f6-148">차단 된 단어 확인은 사용자가 입력 한 그룹 이름에 대해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-148">The blocked words check is done on the user entered group name.</span></span> <span data-ttu-id="456f6-149">사용자가 ' darnit '를 입력 하 고 '\_접두사 '가 명명 정책 인 경우 '\_접두사 darnit '가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-149">So if user enters 'darnit' and 'Prefix\_' is the naming policy, 'Prefix\_darnit' will fail.</span></span>

<span data-ttu-id="456f6-150">하위 문자열 검색은 수행 되지 않습니다. 특히 오류를 발생 시키려면 사용자가 입력 한 이름과 사용자 지정 차단 된 단어 사이에 정확 하 게 일치 하는 이름이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-150">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span> <span data-ttu-id="456f6-151">' Ass '이 차단 된 경우에도 사용자가 ' Class '와 같은 일반적인 단어 중 일부를 사용할 수 있도록 하위 문자열 검색이 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-151">Sub-string search isn't done so that users can use some of the common words like 'Class' even if 'ass' is a blocked word.</span></span>

<span data-ttu-id="456f6-152">다음 **항목을 확인 해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="456f6-152">**Things to look out for**:</span></span>

- <span data-ttu-id="456f6-153">차단 된 단어는 대/소문자를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-153">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="456f6-154">사용자가 차단 된 단어를 입력 하면 그룹 클라이언트는 차단 된 단어와 함께 오류 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-154">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="456f6-155">차단 된 단어에는 문자 제한이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-155">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="456f6-156">차단 된 단어로 설정할 수 있는 5000 단어의 상한선이 한도입니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-156">There is an upper limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="456f6-157">관리 재정의</span><span class="sxs-lookup"><span data-stu-id="456f6-157">Admin override</span></span>

<span data-ttu-id="456f6-158">선택적 관리자는 모든 그룹 작업 및 끝점에서 이러한 정책 으로부터 제외 되므로 이러한 차단 된 단어를 사용 하 여 그룹을 만들고 원하는 명명 규칙을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-158">Selective administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions.</span></span> <span data-ttu-id="456f6-159">다음은 그룹 명명 정책에서 제외 된 관리자 역할 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-159">The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="456f6-160">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="456f6-160">Global admin</span></span>

- <span data-ttu-id="456f6-161">파트너 계층 1 지원</span><span class="sxs-lookup"><span data-stu-id="456f6-161">Partner Tier 1 Support</span></span>

- <span data-ttu-id="456f6-162">파트너 계층 2 지원</span><span class="sxs-lookup"><span data-stu-id="456f6-162">Partner Tier 2 Support</span></span>

- <span data-ttu-id="456f6-163">사용자 계정 관리자</span><span class="sxs-lookup"><span data-stu-id="456f6-163">User account admin</span></span>

- <span data-ttu-id="456f6-164">디렉터리 작성자</span><span class="sxs-lookup"><span data-stu-id="456f6-164">Directory writers</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="456f6-165">명명 정책을 설정 하는 방법</span><span class="sxs-lookup"><span data-stu-id="456f6-165">How to set up the naming policy</span></span>

<span data-ttu-id="456f6-166">명명 정책을 설정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="456f6-167">[Azure Active Directory](https://aad.portal.azure.com)의 **관리**에서 **그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="456f6-168">**설정**아래에서 **이름 지정 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="456f6-169">**그룹 명명 정책** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="456f6-170">**현재 정책**에서 접두사 또는 접미사를 필요한 경우 또는 둘 다를 선택 하 고 해당 하는 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="456f6-171">각 줄에 대해 **특성** 및 **문자열** 을 선택한 다음 특성 또는 문자열을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="456f6-172">필요한 접두 번호와 접미사를 추가한 후 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Azure Active Directory의 그룹 명명 정책 설정 스크린샷](../media/groups-naming-policy-azure.png)

## <a name="naming-policy-experiences-across-office-365-apps"></a><span data-ttu-id="456f6-174">Office 365 앱 전반의 명명 정책 환경</span><span class="sxs-lookup"><span data-stu-id="456f6-174">Naming policy experiences across Office 365 apps</span></span>

<span data-ttu-id="456f6-175">사용자가 그룹 이름 및 별칭을 입력할 때 Office 365 앱은 접두사 및 접미사를 포함 하는 명명 정책 그룹 이름의 미리 보기를 표시 하도록 업데이트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-175">The Office 365 apps have been updated to show a preview of the naming policy group name (with prefixes and suffixes) when the user types in the group name and alias.</span></span> <span data-ttu-id="456f6-176">사용자가 차단 된 단어를 입력 하면 차단 되는 단어를 제거할 수 있도록 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-176">When the user enters blocked words, they'll see an error message so they can remove the blocked words.</span></span>

## <a name="outlook-on-the-web"></a><span data-ttu-id="456f6-177">웹용 Outlook</span><span class="sxs-lookup"><span data-stu-id="456f6-177">Outlook on the web</span></span>

<span data-ttu-id="456f6-178">웹에서 outlook (이전의 Outlook Web App 또는 OWA)은 사용자가 그룹 이름 또는 그룹 별칭을 입력할 때 이름이 데코레이팅된 이름으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-178">Outlook on the web (formerly known as Outlook Web App or OWA) shows the naming policy decorated name when the user types a group name or group alias.</span></span> <span data-ttu-id="456f6-179">사용자가 차단 된 사용자 지정 단어를 입력 하면 사용자가 제거할 수 있도록 차단 된 단어와 함께 오류 메시지가 UI에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-179">When an user enters a custom blocked word, an error message is shown in the UI along with the blocked word so that the user can remove it.</span></span> <span data-ttu-id="456f6-180">아래에는 웹 환경 스냅숏의 Outlook이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-180">Outlook on the web experience snapshots are shown below.</span></span>

![Office 365 그룹의 그룹 명명 정책의 나란히 보기](../media/1a21657a-c542-4d9e-ac7d-887ac542a9d9.png)

## <a name="outlook-desktop"></a><span data-ttu-id="456f6-182">Outlook 데스크톱</span><span class="sxs-lookup"><span data-stu-id="456f6-182">Outlook Desktop</span></span>

<span data-ttu-id="456f6-183">Outlook 데스크톱에서 만든 그룹은 명명 정책을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-183">Groups created in Outlook desktop are compliant with naming policy.</span></span> <span data-ttu-id="456f6-184">Outlook 데스크톱 앱은 아직 명명 정책의 미리 보기를 표시 하지 않으며 사용자가 그룹 이름을 입력할 때 차단 된 사용자 지정 단어 오류를 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-184">Outlook desktop app doesn't yet show the preview of the naming policy and doesn't return the custom blocked word errors, when the user enters the group name.</span></span> <span data-ttu-id="456f6-185">그러나 그룹 이름 또는 별칭에 사용자 지정 차단 단어가 있으면 create/edit를 선택 하면 명명 정책이 자동으로 적용 되 고 사용자에 게 오류가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-185">However, naming policy will be automatically applied on selecting create/edit and users will be presented with errors if there are custom blocked words in the group name or alias.</span></span>

## <a name="microsoft-teams"></a><span data-ttu-id="456f6-186">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="456f6-186">Microsoft Teams</span></span>

<span data-ttu-id="456f6-187">Microsoft 팀은 사용자가 팀 이름을 입력할 때 명명 정책을 데코레이팅된 이름으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-187">Microsoft Teams shows the naming policy decorated name when the user types a team name.</span></span> <span data-ttu-id="456f6-188">사용자가 차단 된 사용자 지정 단어를 입력 하면 사용자가 해당 단어를 제거할 수 있도록 차단 된 word와 함께 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-188">When a user enters a custom blocked word, an error message is shown along with the blocked word so that the user can remove it.</span></span>

![Microsoft 팀의 그룹 명명 정책 차단 됨 예](../media/7c904546-5853-4642-949a-a55dbb004eca.png)

## <a name="sharepoint"></a><span data-ttu-id="456f6-190">SharePoint</span><span class="sxs-lookup"><span data-stu-id="456f6-190">SharePoint</span></span>

<span data-ttu-id="456f6-191">SharePoint는 사용자가 사이트 이름 또는 그룹 전자 메일 주소를 입력할 때 이름 지정 정책 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-191">SharePoint shows the naming policy name when the user types a site name or group email address.</span></span> <span data-ttu-id="456f6-192">사용자가 차단 된 사용자 지정 단어를 입력 하면 사용자가 해당 단어를 제거할 수 있도록 차단 된 word와 함께 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-192">When an user enters a custom blocked word, an error message is shown, along with the blocked word so that the user can remove it.</span></span>

![그룹 명명 정책-SharePoint 사이트 차단 된 이름](../media/cf0d6158-fd32-4a93-ac24-2e037102c42c.png)

## <a name="microsoft-stream"></a><span data-ttu-id="456f6-194">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="456f6-194">Microsoft Stream</span></span>

<span data-ttu-id="456f6-195">Microsoft Stream은 사용자가 그룹 이름 또는 그룹 전자 메일 별칭을 입력할 때 명명 정책을 데코레이팅된 이름으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-195">Microsoft Stream shows the naming policy decorated name when the user types a group name or group email alias.</span></span> <span data-ttu-id="456f6-196">사용자가 차단 된 사용자 지정 단어를 입력 하면 사용자가 해당 메시지를 제거할 수 있도록 차단 된 단어와 함께 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-196">When an user enters a custom blocked word, an error message is shown with the blocked word so the user can remove it.</span></span>

![Microsoft Stream에 대 한 그룹 명명 정책 차단 된 예제](../media/9748f52a-3814-41a6-9ac1-4e8cd4c91011.png)

## <a name="outlook-ios-and-android-app"></a><span data-ttu-id="456f6-198">Outlook iOS 및 Android 앱</span><span class="sxs-lookup"><span data-stu-id="456f6-198">Outlook iOS and Android App</span></span>

<span data-ttu-id="456f6-199">Outlook 앱에서 만든 그룹은 명명 정책을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-199">Groups created in Outlook apps are compliant with naming policy.</span></span> <span data-ttu-id="456f6-200">Outlook mobile은 그룹 이름을 입력할 때 명명 정책 미리 보기를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-200">Outlook mobile shows the naming policy preview when entering the Group name.</span></span> <span data-ttu-id="456f6-201">사용자가 차단 된 사용자 지정 단어를 입력 하면 그룹을 만들 때 오류 메시지가 표시 되므로 사용자가 차단 된 단어를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-201">When a user enters a custom blocked word, an error message is shown on creating the group, so the user can remove the blocked word.</span></span>

## <a name="planner"></a><span data-ttu-id="456f6-202">Planner</span><span class="sxs-lookup"><span data-stu-id="456f6-202">Planner</span></span>

<span data-ttu-id="456f6-203">Planner는 명명 정책을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-203">Planner is compliant with naming policy.</span></span> <span data-ttu-id="456f6-204">Planner 계획 이름을 입력할 때 이름 지정 정책 미리 보기를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-204">Planner shows the naming policy preview when entering the Plan name.</span></span> <span data-ttu-id="456f6-205">사용자가 차단 된 사용자 지정 단어를 입력 하면 계획을 만들 때 오류 메시지가 표시 되므로 사용자가 차단 된 단어를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-205">When a user enters a custom blocked word, an error message is shown on creating the plan, so the user can remove the blocked word.</span></span>

![그룹 명명 정책-새 계획 차단 됨 만들기 예제](../media/ea692b44-3a56-4e6d-bcb8-8444fe5bbc4f.png)

## <a name="dynamics-365-for-customer-engagement"></a><span data-ttu-id="456f6-207">고객 계약에 대 한 Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="456f6-207">Dynamics 365 for Customer Engagement</span></span>

<span data-ttu-id="456f6-208">고객 계약에 대 한 Dynamics 365는 명명 정책을 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-208">Dynamics 365 for Customer Engagement is compliant with naming policy.</span></span> <span data-ttu-id="456f6-209">Dynamics 365은 사용자가 그룹 이름 또는 그룹 전자 메일 별칭을 입력할 때 이름이 데코레이팅된 이름 지정 정책을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-209">Dynamics 365 shows the naming policy decorated name when the user types a group name or group email alias.</span></span> <span data-ttu-id="456f6-210">사용자가 차단 된 사용자 지정 단어를 입력 하면 사용자가 해당 메시지를 제거할 수 있도록 차단 된 단어와 함께 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-210">When the user enters a custom blocked word, an error message is shown with the blocked word so the user can remove it.</span></span>

![Dynamics 365](../media/8190331c-6779-42bd-a6b3-f7007428c8ae.png)

## <a name="school-data-sync-sds"></a><span data-ttu-id="456f6-212">SDS (학교 데이터 동기화)</span><span class="sxs-lookup"><span data-stu-id="456f6-212">School Data Sync (SDS)</span></span>

<span data-ttu-id="456f6-213">SDS를 통해 만들어진 그룹은 명명 정책을 준수 하지만 명명 정책은 자동으로 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-213">Groups created through SDS comply with naming policy, but the naming policy isn't applied automatically.</span></span> <span data-ttu-id="456f6-214">SDS 관리자는 그룹을 만들어야 하는 클래스 이름에 접두사와 접미사를 추가한 다음 SDS에 업로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-214">SDS administrators have to append the prefixes and suffixes to class names for which groups need to be created and then upload to SDS.</span></span> <span data-ttu-id="456f6-215">그렇지 않으면 그룹 만들기/편집이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-215">Groups creation/edit would fail otherwise.</span></span>

## <a name="outlook-customer-manager-ocm"></a><span data-ttu-id="456f6-216">OCM (Outlook 고객 관리자)</span><span class="sxs-lookup"><span data-stu-id="456f6-216">Outlook Customer Manager (OCM)</span></span>

<span data-ttu-id="456f6-217">Outlook 고객 관리자는 명명 정책을 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-217">Outlook Customer Manager is compliant with naming policy.</span></span> <span data-ttu-id="456f6-218">명명 정책은 Outlook Customer Manager에서 만든 그룹에 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-218">The naming policy gets automatically applied to the group created in Outlook Customer Manager.</span></span> <span data-ttu-id="456f6-219">"모든 영업 팀" 내의 단어 중 일부가 사용자 지정 차단 된 단어로 정의 된 경우에는 OCM에서 그룹을 만들 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-219">If any of the words within "All Sales Team" is defined as a custom blocked word, the group creation in OCM will be blocked.</span></span> <span data-ttu-id="456f6-220">사용자가 OCM 그룹을 만들 수 없으며 OCM 앱을 사용 하지 못하도록 차단 됩니다. "</span><span class="sxs-lookup"><span data-stu-id="456f6-220">The user will not be able to create the OCM group and will be blocked from using the OCM app."</span></span>

## <a name="classroom-app"></a><span data-ttu-id="456f6-221">교실 앱</span><span class="sxs-lookup"><span data-stu-id="456f6-221">Classroom App</span></span>

<span data-ttu-id="456f6-222">강의실 앱에서 만든 그룹은 명명 정책을 준수 하지만, 명명 정책이 자동으로 적용 되지 않으며, 강의 그룹 이름을 입력 하는 동안에는 명명 정책 미리 보기가 사용자에 게 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-222">Groups created in classroom app comply with naming policy, but the naming policy isn't applied automatically, and the naming policy preview isn't shown to the users while entering a classroom group name.</span></span> <span data-ttu-id="456f6-223">사용자가 접두사와 접미사를 사용 하 여 데코레이팅된 교실 그룹 이름을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-223">So users would have to enter the decorated classroom group name with prefixes and suffixes.</span></span> <span data-ttu-id="456f6-224">그렇지 않으면 교실 그룹 만들기 또는 편집이 오류로 인해 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-224">Otherwise the classroom group create or edit will fail with errors.</span></span>

## <a name="power-bi"></a><span data-ttu-id="456f6-225">Power BI</span><span class="sxs-lookup"><span data-stu-id="456f6-225">Power BI</span></span>

<span data-ttu-id="456f6-226">Power BI 작업 영역에서 만들어진 그룹은 명명 정책을 준수 하지만 명명 정책은 자동으로 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-226">Groups created in Power BI workspaces comply with the naming policy, but the naming policy isn't applied automatically.</span></span> <span data-ttu-id="456f6-227">또한 명명 정책 미리 보기는 사용자가 Power BI 작업 영역 이름을 입력할 때 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-227">And, the naming policy preview isn't shown to users when they enter a Power BI workspace name.</span></span>

<span data-ttu-id="456f6-228">명명 정책이 적용 된 권장 이름은 작업 영역 만들기 또는 편집의 오류 세부 정보에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-228">The recommended name - with the naming policy applied - is shown in the error details on create or edit workspaces.</span></span> <span data-ttu-id="456f6-229">즉, 사용자는 접두사와 접미사로 데코레이팅된 작업 영역 이름을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-229">This means users have to enter the decorated workspace name with prefixes and suffixes.</span></span> <span data-ttu-id="456f6-230">그렇지 않으면 작업 영역 만들기 또는 편집이 오류로 인해 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-230">Otherwise the workspace create or edit will fail with errors.</span></span>

## <a name="yammer"></a><span data-ttu-id="456f6-231">Yammer</span><span class="sxs-lookup"><span data-stu-id="456f6-231">Yammer</span></span>

<span data-ttu-id="456f6-232">Azure Active Directory 계정을 사용 하 여 Yammer에 로그인 한 사용자가 그룹을 만들거나 그룹 이름을 편집 하는 경우 그룹 이름은 명명 정책을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-232">When a user signed in to Yammer with their Azure Active Directory account creates a group or edits a group name, the group name will comply with naming policy.</span></span> <span data-ttu-id="456f6-233">이는 Office 365 연결 된 그룹과 기타 모든 Yammer 그룹에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-233">This applies both to Office 365 connected groups and all other Yammer groups.</span></span>

<span data-ttu-id="456f6-234">명명 정책이 적용 되기 전에 Office 365 연결 된 그룹을 만든 경우에는 그룹 이름이 자동으로 이름 지정 정책을 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-234">If an Office 365 connected group was created before the naming policy is in place, the group name will not automatically follow the naming policies.</span></span> <span data-ttu-id="456f6-235">사용자가 그룹 이름을 편집할 때 접두사와 접미사를 추가 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-235">When a user edits the group name, they will be prompted to add the prefix and suffix.</span></span>

<span data-ttu-id="456f6-236">이름 정책에 Yammer 그룹 이름에 사용할 수 없는 문자가 포함 된 경우 관리자만 Yammer에서 연결 된 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-236">If the naming policy includes characters that can't be in Yammer group names, only admins will be able to create a connected group in Yammer.</span></span>

## <a name="staffhub"></a><span data-ttu-id="456f6-237">StaffHub</span><span class="sxs-lookup"><span data-stu-id="456f6-237">StaffHub</span></span>

<span data-ttu-id="456f6-238">StaffHub 팀은 명명 정책을 따르지 않지만 기본 Office 365 그룹에서는 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-238">StaffHub teams do not follow the naming policy, but the underlying Office 365 group does.</span></span> <span data-ttu-id="456f6-239">StaffHub 팀 이름은 접두사와 접미사를 적용 하지 않으며 사용자 지정 차단 된 단어를 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-239">StaffHub team name does not apply the prefixes and suffixes and does not check for custom blocked words.</span></span> <span data-ttu-id="456f6-240">그러나 StaffHub는 접두사와 접미사를 적용 하 고 기본 Office 365 그룹에서 차단 된 단어를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-240">But StaffHub does apply the prefixes and suffixes and removes blocked words from the underlying Office 365 group.</span></span>

## <a name="exchange-powershell"></a><span data-ttu-id="456f6-241">Exchange PowerShell(Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="456f6-241">Exchange PowerShell</span></span>

<span data-ttu-id="456f6-242">Exchange PowerShell cmdlet은 명명 정책을 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-242">Exchange PowerShell cmdlets are compliant with naming policy.</span></span> <span data-ttu-id="456f6-243">사용자는 그룹 이름 및 그룹 별칭에 명명 규칙을 사용 하지 않는 경우 제안 된 접두사 및 접미사와 사용자 지정 차단 단어에 대 한 적절 한 오류 메시지를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-243">Users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="azure-active-directory-powershell-cmdlets"></a><span data-ttu-id="456f6-244">Azure Active Directory PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="456f6-244">Azure Active Directory PowerShell cmdlets</span></span>

<span data-ttu-id="456f6-245">Azure Active Directory PowerShell cmdlet은 명명 정책을 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-245">Azure Active Directory PowerShell cmdlets are compliant with naming policy.</span></span> <span data-ttu-id="456f6-246">사용자는 그룹 이름 및 그룹 별칭에 명명 규칙을 사용 하지 않는 경우 제안 된 접두사 및 접미사와 사용자 지정 차단 단어에 대 한 적절 한 오류 메시지를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-246">Users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="exchange-admin-center"></a><span data-ttu-id="456f6-247">Exchange 관리 센터</span><span class="sxs-lookup"><span data-stu-id="456f6-247">Exchange admin center</span></span>

<span data-ttu-id="456f6-248">EAC (Exchange 관리 센터)는 명명 정책을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-248">The Exchange admin center (EAC) is compliant with naming policy.</span></span> <span data-ttu-id="456f6-249">만들기 또는 편집 작업 시 사용자는 그룹 이름 및 그룹 별칭에 명명 규칙을 사용 하지 않는 경우 제안 된 접두사 및 접미사와 사용자 지정 차단 단어에 대 한 적절 한 오류 메시지를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-249">On create or edit actions, users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="microsoft-365-admin-center"></a><span data-ttu-id="456f6-250">Microsoft 365 관리 센터</span><span class="sxs-lookup"><span data-stu-id="456f6-250">Microsoft 365 admin center</span></span>

<span data-ttu-id="456f6-251">Microsoft 365 관리 센터는 명명 정책을 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-251">The Microsoft 365 admin center is compliant with naming policy.</span></span> <span data-ttu-id="456f6-252">만들기 또는 편집 작업에서 이름 지정 정책이 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-252">On create or edit actions, naming policy will automatically get applied.</span></span> <span data-ttu-id="456f6-253">사용자가 차단 된 사용자 지정 단어를 입력 하면 해당 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-253">Users will get appropriate errors when they enter custom blocked words.</span></span> <span data-ttu-id="456f6-254">Microsoft 365 관리 센터에서 명명 정책의 미리 보기가 표시 되지 않고 사용자가 그룹 이름을 입력할 때 사용자 지정 차단 된 단어 오류가 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-254">The Microsoft 365 admin center doesn't yet show the preview of the naming policy and doesn't return the custom blocked word errors, when the user enters the group name.</span></span>

## <a name="azure-active-directory-portal"></a><span data-ttu-id="456f6-255">Azure Active Directory 포털</span><span class="sxs-lookup"><span data-stu-id="456f6-255">Azure Active Directory portal</span></span>

<span data-ttu-id="456f6-256">Azure Active Directory 포털이 명명 정책을 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-256">The Azure Active Directory portal is compliant with naming policy.</span></span> <span data-ttu-id="456f6-257">Azure Active Directory portal은 그룹 이름으로 들어갈 때 명명 정책 미리 보기를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-257">Azure Active Directory portal shows the naming policy preview when entering the Group name.</span></span> <span data-ttu-id="456f6-258">사용자가 차단 된 사용자 지정 단어를 입력 하면 그룹을 만들 때 오류 메시지가 표시 되므로 사용자가 차단 된 단어를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="456f6-258">When a user enters a custom blocked word, an error message is shown on creating the group, so the user can remove the blocked word.</span></span>

## <a name="more-articles-on-naming-policy"></a><span data-ttu-id="456f6-259">명명 정책에 대 한 추가 문서</span><span class="sxs-lookup"><span data-stu-id="456f6-259">More articles on naming policy</span></span>

[<span data-ttu-id="456f6-260">Azure Active Directory에서 Office 365 그룹에 대 한 명명 정책 적용</span><span class="sxs-lookup"><span data-stu-id="456f6-260">Enforce a naming policy for Office 365 groups in Azure Active Directory</span></span>](https://go.microsoft.com/fwlink/?linkid=868340)

[<span data-ttu-id="456f6-261">그룹 설정 구성을 위한 Azure Active Directory cmdlet</span><span class="sxs-lookup"><span data-stu-id="456f6-261">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
