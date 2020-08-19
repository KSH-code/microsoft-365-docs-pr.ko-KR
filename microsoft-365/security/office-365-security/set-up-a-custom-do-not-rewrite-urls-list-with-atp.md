---
title: ATP 안전한 링크를 사용 하 여 사용자 지정 쓰기 방지 Url 목록 설정
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365 ATP 안전한 링크 정책의 사용자 그룹에 대 한 사용자 지정 차단 Url을 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 17828566769f438439eebcb4e460ecac1147a648
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46798333"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-atp-safe-links"></a><span data-ttu-id="06e84-103">ATP 안전한 링크를 사용 하 여 사용자 지정 쓰기 방지 Url 목록 설정</span><span class="sxs-lookup"><span data-stu-id="06e84-103">Set up a custom do-not-rewrite URLs list using ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06e84-104">이 문서는 [Office 365 Advanced Threat Protection](office-365-atp.md)이 있는 비즈니스 고객을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="06e84-105">Outlook의 안전한 링크에 대 한 정보를 검색 하는 개인 사용자는 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="06e84-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="06e84-106">[Office 365 ATP (Advanced Threat Protection](office-365-atp.md) )를 사용 하는 경우 조직에 [사용자 지정 차단 된 url](set-up-a-custom-blocked-urls-list-atp.md)이 있을 수 있으며, 사용자가 전자 메일 메시지 또는 특정 Office 문서에서 웹 주소 (url)를 클릭할 때 이러한 url로 이동 하는 것이 방지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a [custom blocked URLs](set-up-a-custom-blocked-urls-list-atp.md), such that when people click on web addresses (URLs) in email messages or certain Office documents, they are prevented from going to those URLs.</span></span> <span data-ttu-id="06e84-107">조직에서 조직의 특정 그룹에 대해 사용자 지정 "다시 쓰지 않음" 목록을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-107">Your organization can also have custom "do not rewrite" lists for specific groups in your organization.</span></span> <span data-ttu-id="06e84-108">"다시 쓰지 않음" 목록을 사용 하면 일부 사용자가 [Office 365의 ATP 안전한 링크](atp-safe-links.md)에 의해 차단 되는 url을 방문할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-108">A "do not rewrite" list enables some people to visit URLs that are otherwise blocked by [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="06e84-109">이 문서에서는 ATP 안전한 링크 검색에서 제외 되는 Url 목록과 몇 가지 중요 한 사항을 염두에 두고 있는지를 지정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-109">This article describes how to specify a list of URLs that are excluded from ATP Safe Links scanning, and a few important points to keep in mind.</span></span>

> [!NOTE]
> <span data-ttu-id="06e84-110">조직에서 안전한 링크 정책을 사용 하는 경우 타사 피싱 테스트에서는 "다시 쓰지 않음" 목록만 지원 되는 유일한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-110">If your organization use Safe Links policies, the "do not rewrite" list is the only supported method for third party phishing tests.</span></span>

## <a name="set-up-a-do-not-rewrite-list"></a><span data-ttu-id="06e84-111">"다시 쓰지 않음" 목록 설정</span><span class="sxs-lookup"><span data-stu-id="06e84-111">Set up a "do not rewrite" list</span></span>

<span data-ttu-id="06e84-112">ATP 안전한 링크 보호에서는 조직의 차단 된 Url 목록과 "다시 쓰지 않음" 목록 등 여러 목록을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-112">ATP Safe Links protection uses several lists, including your organization's blocked URLs list and the "do not rewrite" lists for exceptions.</span></span> <span data-ttu-id="06e84-113">필요한 사용 권한이 있는 경우 사용자 지정 "다시 쓰지 않음" 목록을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-113">If you have the necessary permissions, you can set up your custom "do not rewrite" lists.</span></span> <span data-ttu-id="06e84-114">조직의 특정 받는 사람에 게 적용 되는 안전 링크 정책을 추가 하거나 편집할 때이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-114">You do this when you add or edit Safe Links policies that apply to specific recipients in your organization.</span></span>

<span data-ttu-id="06e84-115">ATP 정책을 편집 하거나 정의 하려면 적절 한 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-115">To edit (or define) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="06e84-116">다음 표에는 몇 가지 예가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-116">The following table includes some examples.</span></span> <span data-ttu-id="06e84-117">자세한 내용은 [Security & 준수 센터의 사용 권한을](permissions-in-the-security-and-compliance-center.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="06e84-117">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

|<span data-ttu-id="06e84-118">역할</span><span class="sxs-lookup"><span data-stu-id="06e84-118">Role</span></span>|<span data-ttu-id="06e84-119">할당 된 위치/방법</span><span class="sxs-lookup"><span data-stu-id="06e84-119">Where/how assigned</span></span>|
|---|---|
|<span data-ttu-id="06e84-120">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="06e84-120">global administrator</span></span>|<span data-ttu-id="06e84-121">Microsoft 365을 구매 하기 위해 등록 하는 사람은 기본적으로 전역 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-121">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="06e84-122">자세한 내용은 [Microsoft 365 관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="06e84-122">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="06e84-123">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="06e84-123">Security Administrator</span></span>|<span data-ttu-id="06e84-124">Azure Active Directory 관리 센터 ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="06e84-124">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="06e84-125">Exchange Online 조직 관리</span><span class="sxs-lookup"><span data-stu-id="06e84-125">Exchange Online Organization Management</span></span>|<span data-ttu-id="06e84-126">Exchange 관리 센터 ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) )</span><span class="sxs-lookup"><span data-stu-id="06e84-126">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="06e84-127">또는</span><span class="sxs-lookup"><span data-stu-id="06e84-127">or</span></span> <br>  <span data-ttu-id="06e84-128">PowerShell cmdlet ( [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)참조)</span><span class="sxs-lookup"><span data-stu-id="06e84-128">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span></span>|
|

> [!TIP]
> <span data-ttu-id="06e84-129">역할 및 사용 권한에 대 한 자세한 내용은 [보안 & 준수 센터의 사용 권한을](permissions-in-the-security-and-compliance-center.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="06e84-129">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a><span data-ttu-id="06e84-130">사용자 지정 "다시 쓰지 않음" Url 목록을 보거나 편집 하려면</span><span class="sxs-lookup"><span data-stu-id="06e84-130">To view or edit a custom "do not rewrite" URLs list</span></span>

1. <span data-ttu-id="06e84-131">으로 이동 하 여 [https://protection.office.com](https://protection.office.com) 회사 또는 학교 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-131">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="06e84-132">왼쪽 탐색 창의 **위협 관리** \> **정책** \> **안전한 링크**아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-132">In the left navigation, under **Threat management** \> **Policy** \> **Safe Links**.</span></span>

3. <span data-ttu-id="06e84-133">**특정 받는 사람에 게 적용 되는 정책** 섹션에서 **새로** 만들기 (새로 만들기 단추를 더하기 기호 ()와 유사)를 선택 **+** 하 여 새 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-133">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)) to create a new policy.</span></span> <span data-ttu-id="06e84-134">또는 기존 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-134">(Alternatively, you can edit an existing policy.)</span></span><br/><span data-ttu-id="06e84-135">![특정 전자 메일 받는 사람에 대 한 안전한 링크 정책을 추가 하려면 새로 만들기를 선택 합니다.](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="06e84-135">![Choose New to add a Safe Links policy for specific email recipients](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>

4. <span data-ttu-id="06e84-136">정책에 대 한 이름 및 설명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-136">Specify a name and description for your policy.</span></span>

5. <span data-ttu-id="06e84-137">Url **켜기** 는 사용자가 링크를 클릭할 때 알려진 악성 링크 목록에 대해 다시 작성 되 고 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-137">Turn **ON** URLs will be rewritten and checked against a list of known malicious links when user clicks on the link.</span></span>

6. <span data-ttu-id="06e84-138">**다음 url을 다시 쓰지** 않음 구역에서 **올바른 url 입력** 상자를 선택 하 고 url을 입력 한 다음 더하기 기호 (+)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-138">In the **Do not rewrite the following URLs** section, select the **Enter a valid URL** box, enter a URL, and then choose the plus sign (+).</span></span>

7. <span data-ttu-id="06e84-139">**적용 대상** 섹션에서 **받는 사람**을 선택 하 고 정책에 포함할 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-139">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy.</span></span> <span data-ttu-id="06e84-140">**추가**를 선택한 다음 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-140">Choose **Add**, and then choose **OK**.</span></span>

8. <span data-ttu-id="06e84-141">Url 추가가 완료 되 면 화면의 오른쪽 아래 모서리에서 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-141">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="06e84-142">조직의 차단 된 Url의 사용자 지정 목록을 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-142">Make sure to review your organization's custom list of blocked URLs.</span></span> <span data-ttu-id="06e84-143">[ATP 안전한 링크를 사용 하 여 차단 된 사용자 지정 url 목록 설정를](set-up-a-custom-blocked-urls-list-atp.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="06e84-143">See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-atp.md).</span></span>

## <a name="important-points-to-keep-in-mind"></a><span data-ttu-id="06e84-144">염두에 두어야 할 중요 사항</span><span class="sxs-lookup"><span data-stu-id="06e84-144">Important points to keep in mind</span></span>

- <span data-ttu-id="06e84-145">"다시 쓰지 않음" 목록에서 지정 하는 Url은 지정 된 받는 사람에 대 한 ATP 안전한 링크 검색에서 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-145">Any URLs that you specify in the "do not rewrite" list are excluded from ATP Safe Links scanning for the recipients that you specify.</span></span>

- <span data-ttu-id="06e84-146">일반적으로 사용 되는 내부 Url을 "다시 쓰지 않음" 목록에 추가 하 여 사용자 환경을 개선 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-146">Consider adding commonly used internal URLs to the "do not rewrite" list to improve the user experience.</span></span> <span data-ttu-id="06e84-147">예를 들어 비즈니스용 Skype 또는 Sharepoint와 같은 온-프레미스 서비스를 사용 하는 경우 해당 Url을 목록에 추가 하 여 검색에서 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-147">For example, if you have on-premises services, such as Skype for Business or Sharepoint, you can add their URLs to the list to exclude them from scanning.</span></span>

- <span data-ttu-id="06e84-148">"다시 쓰지 않음" 목록에 이미 Url 목록이 있는 경우 해당 목록을 검토 하 고 와일드 카드를 적절 하 게 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-148">If you already have a list of URLs in your "do not rewrite" list, make sure to review that list and add wildcards as appropriate.</span></span> <span data-ttu-id="06e84-149">예를 들어 기존 목록에 항목이 있는 경우 `https://contoso.com/a` 정책에 하위 경로를 포함 하려면 `https://contoso.com/a/b` 항목에 와일드 카드를 추가 하 여 표시 `https://contoso.com/a/*` 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-149">For example, if your existing list has an entry like `https://contoso.com/a` and you want to include subpaths like `https://contoso.com/a/b` in your policy, add a wildcard to your entry so it looks like `https://contoso.com/a/*`.</span></span>

- <span data-ttu-id="06e84-150">ATP 안전한 링크 정책에 대 한 "다시 쓰지 않음" 목록을 지정 하는 경우 최대 3 개의 와일드 카드 ()를 포함할 수 있습니다 \* .</span><span class="sxs-lookup"><span data-stu-id="06e84-150">When you specify a "do not rewrite" list for an ATP Safe Links policy, you can include up to three wildcards (\*).</span></span> <span data-ttu-id="06e84-151">와일드 카드에 접두사 또는 하위 도메인이 명시적으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-151">Wildcards explicitly include prefixes or subdomains.</span></span> <span data-ttu-id="06e84-152">예를 들어 항목은 `contoso.com` `*.contoso.com/*` `*.contoso.com/*` 지정 된 도메인의 하위 도메인과 경로를 방문 하도록 허용 하므로와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-152">For example, the entry `contoso.com` is not the same as `*.contoso.com/*`, because `*.contoso.com/*` allows people to visit subdomains and paths in the specified domain.</span></span>

<span data-ttu-id="06e84-153">다음 표에는 입력 가능한 항목과 해당 항목이 갖는 영향에 대 한 예가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-153">The following table lists examples of what you can enter and what effect those entries have.</span></span>

****

|<span data-ttu-id="06e84-154">예제 항목</span><span class="sxs-lookup"><span data-stu-id="06e84-154">Example Entry</span></span>|<span data-ttu-id="06e84-155">수행 하는 작업</span><span class="sxs-lookup"><span data-stu-id="06e84-155">What It Does</span></span>|
|---|---|
|`contoso.com`|<span data-ttu-id="06e84-156">받는 사람이 하위 도메인 또는 경로를 제외 하 고 사이트를 방문할 수 있도록 허용 `https://contoso.com` 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e84-156">Allows recipients to visit a site like `https://contoso.com` but not subdomains or paths.</span></span>|
|`*.contoso.com/*`|<span data-ttu-id="06e84-157">받는 사람이,, 또는 등의 도메인, 하위 도메인과 경로를 방문할 수 있습니다 `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` `https://www.contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="06e84-157">Allows recipients to visit a domain, subdomains, and paths, such as `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `https://www.contoso.com/a`.</span></span> <br/><br/> <span data-ttu-id="06e84-158">이 항목은 `*contoso.com*` 다음과 같이 잠재적으로 사기성 사이트를 포함 하지 않기 때문에 기본적으로 더 좋습니다. `https://www.falsecontoso.com``https://www.false.contoso.completelyfalse.com`</span><span class="sxs-lookup"><span data-stu-id="06e84-158">This entry is inherently better than `*contoso.com*`, because it doesn't include potentially fraudulent sites, like `https://www.falsecontoso.com` or `https://www.false.contoso.completelyfalse.com`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="06e84-159">특정 받는 사람이 같은 사이트를 방문 하 되 하위 경로는 볼 수 `https://contoso.com/a` 없습니다. `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="06e84-159">Allows specific recipients to visit a site like `https://contoso.com/a`, but not subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a/*`|<span data-ttu-id="06e84-160">특정 받는 사람이 같은 사이트와 같은 하위 경로를 방문할 수 있도록 허용 `https://contoso.com/a``https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="06e84-160">Allows specific recipients to visit a site like `https://contoso.com/a` and subpaths like `https://contoso.com/a/b`</span></span>|
|
