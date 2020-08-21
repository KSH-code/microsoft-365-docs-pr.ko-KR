---
title: ATP 안전한 링크를 사용하여 사용자 지정 문서 다시 작성 방지 URL 목록 설정
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
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
description: Office 365 ATP 안전한 링크 정책에서 사용자 그룹에 대한 사용자 지정 차단URL 및 재작성 안 함 URL 목록을 설정방법을 알아봅니다.
ms.openlocfilehash: 9ec9c92e038aee33c716405916df009e3f4c60c5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825236"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-atp-safe-links"></a><span data-ttu-id="9e7b3-103">ATP 안전한 링크를 사용하여 사용자 지정 문서 다시 작성 방지 URL 목록 설정</span><span class="sxs-lookup"><span data-stu-id="9e7b3-103">Set up a custom do-not-rewrite URLs list using ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e7b3-104">이 문서는 [Office 365 Advanced Threat Protection](office-365-atp.md)이 있는 비즈니스 고객을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="9e7b3-105">Outlook의 안전한 링크에 대한 정보를 찾고 있는 홈 사용자는 고급 [연결 Outlook.com 감사를 참조하세요.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="9e7b3-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="9e7b3-106">[Office 365 ATP(Advanced Threat Protection)를](office-365-atp.md) 사용하는 경우, 조직에서 사용자의 전자 메일 메시지나 특정 Office 문서에서 웹 주소(URL)를 클릭할 때 사용자가 해당 URL로 이동할 수 없는 등의 차단된 URL을 사용할 수 있습니다. [custom blocked URLs](set-up-a-custom-blocked-urls-list-atp.md)</span><span class="sxs-lookup"><span data-stu-id="9e7b3-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a [custom blocked URLs](set-up-a-custom-blocked-urls-list-atp.md), such that when people click on web addresses (URLs) in email messages or certain Office documents, they are prevented from going to those URLs.</span></span> <span data-ttu-id="9e7b3-107">또한 조직의 특정 그룹에 대해 사용자 지정 "재작성 안 함"목록을 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-107">Your organization can also have custom "do not rewrite" lists for specific groups in your organization.</span></span> <span data-ttu-id="9e7b3-108">"다시 쓰지 않음" 목록을 사용하면 일부 사용자가 [Office 365에서 ATP 안전한 링크를 통해 차단한 URL을 방문할 수 있습니다.](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="9e7b3-108">A "do not rewrite" list enables some people to visit URLs that are otherwise blocked by [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="9e7b3-109">이 문서에서는 ATP 안전한 링크 검사에서 제외되는 URL 목록 및 고려해야 할 몇 가지 중요한 사항을 명시합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-109">This article describes how to specify a list of URLs that are excluded from ATP Safe Links scanning, and a few important points to keep in mind.</span></span>

> [!NOTE]
> <span data-ttu-id="9e7b3-110">조직에서 안전 링크 정책을 사용하는 경우 타사 피싱 테스트에 "재작성 안 함" 목록만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-110">If your organization use Safe Links policies, the "do not rewrite" list is the only supported method for third party phishing tests.</span></span>

## <a name="set-up-a-do-not-rewrite-list"></a><span data-ttu-id="9e7b3-111">"재작성 안 함" 목록 설정</span><span class="sxs-lookup"><span data-stu-id="9e7b3-111">Set up a "do not rewrite" list</span></span>

<span data-ttu-id="9e7b3-112">ATP 안전한 링크 보호는 조직의 차단된 URL 목록과 예외를 위해 "재쓰지 않음" 목록 등의 여러 목록을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-112">ATP Safe Links protection uses several lists, including your organization's blocked URLs list and the "do not rewrite" lists for exceptions.</span></span> <span data-ttu-id="9e7b3-113">필요한 권한이 있는 경우 사용자 지정 "다시 쓰지 않습니다"라는 목록을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-113">If you have the necessary permissions, you can set up your custom "do not rewrite" lists.</span></span> <span data-ttu-id="9e7b3-114">이는 조직의 특정 받는 사람에게 적용되는 안전 링크 정책을 추가하거나 편집할 때 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-114">You do this when you add or edit Safe Links policies that apply to specific recipients in your organization.</span></span>

<span data-ttu-id="9e7b3-115">ATP 정책을 편집하거나 정의하려면 적절한 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-115">To edit (or define) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="9e7b3-116">다음 표에 몇 가지 예제가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-116">The following table includes some examples.</span></span> <span data-ttu-id="9e7b3-117">자세한 내용은 보안 서비스 [및 준수 센터의 사용 & 참조하십시오.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="9e7b3-117">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

|<span data-ttu-id="9e7b3-118">역할</span><span class="sxs-lookup"><span data-stu-id="9e7b3-118">Role</span></span>|<span data-ttu-id="9e7b3-119">할당된 위치/방법</span><span class="sxs-lookup"><span data-stu-id="9e7b3-119">Where/how assigned</span></span>|
|---|---|
|<span data-ttu-id="9e7b3-120">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="9e7b3-120">global administrator</span></span>|<span data-ttu-id="9e7b3-121">기본적으로 Microsoft 365를 시작하기 위해 등록하는 사람은 전역 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-121">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="9e7b3-122">[(자세한 내용은 Microsoft 365 관리자 역할](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 정보를 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="9e7b3-122">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="9e7b3-123">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="9e7b3-123">Security Administrator</span></span>|<span data-ttu-id="9e7b3-124">Azure Active Directory 관리 [https://aad.portal.azure.com](https://aad.portal.azure.com) 센터()</span><span class="sxs-lookup"><span data-stu-id="9e7b3-124">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="9e7b3-125">Exchange Online 조직 관리</span><span class="sxs-lookup"><span data-stu-id="9e7b3-125">Exchange Online Organization Management</span></span>|<span data-ttu-id="9e7b3-126">Exchange 관리 [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) 센터(</span><span class="sxs-lookup"><span data-stu-id="9e7b3-126">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="9e7b3-127">또는</span><span class="sxs-lookup"><span data-stu-id="9e7b3-127">or</span></span> <br>  <span data-ttu-id="9e7b3-128">PowerShell [cmdlet(Exchange Online PowerShell 참조)](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="9e7b3-128">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span></span>|
|

> [!TIP]
> <span data-ttu-id="9e7b3-129">역할 및 사용 권한에 대한 자세한 내용은 보안 [센터의 보안 그룹& 참조하세요.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="9e7b3-129">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a><span data-ttu-id="9e7b3-130">사용자 지정 "재작성 안 함" URL 목록을 보거나 편집하려면</span><span class="sxs-lookup"><span data-stu-id="9e7b3-130">To view or edit a custom "do not rewrite" URLs list</span></span>

1. <span data-ttu-id="9e7b3-131">이동하여 [https://protection.office.com](https://protection.office.com) 회사 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-131">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="9e7b3-132">왼쪽 탐색 창에 **위협 관리 정책** \> **안전** 링크 \> **아래.**</span><span class="sxs-lookup"><span data-stu-id="9e7b3-132">In the left navigation, under **Threat management** \> **Policy** \> **Safe Links**.</span></span>

3. <span data-ttu-id="9e7b3-133">특정 받는 **사람에게 적용되는 정책** 섹션에서 새로 만들기(새 단추는 더하기 기호( )와 유사함)을 **New** **+** 선택하여 새 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-133">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)) to create a new policy.</span></span> <span data-ttu-id="9e7b3-134">또는 기존 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-134">(Alternatively, you can edit an existing policy.)</span></span><br/><span data-ttu-id="9e7b3-135">![새로 만들기 선택하여 특정 메일 받는 사람에 대한 안전 링크 정책 추가](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="9e7b3-135">![Choose New to add a Safe Links policy for specific email recipients](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>

4. <span data-ttu-id="9e7b3-136">정책의 이름과 설명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-136">Specify a name and description for your policy.</span></span>

5. <span data-ttu-id="9e7b3-137">따라서 **ON** 사용자가 링크를 클릭할 때 알려진 악성 링크 목록과 관련하여 URL이 다시 작성되고 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-137">Turn **ON** URLs will be rewritten and checked against a list of known malicious links when user clicks on the link.</span></span>

6. <span data-ttu-id="9e7b3-138">다음 **URL을 다시 쓰지 않는 URL 섹션에서** 유효한 URL 입력 상자를 선택하고 **URL을** 입력한 후에 더하기 기호(+)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-138">In the **Do not rewrite the following URLs** section, select the **Enter a valid URL** box, enter a URL, and then choose the plus sign (+).</span></span>

7. <span data-ttu-id="9e7b3-139">적용 **대상 섹션에서** 받는 **사람이 구성원인지**확인한 다음 정책에 포함할 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-139">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy.</span></span> <span data-ttu-id="9e7b3-140">**추가를**선택한 후 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e7b3-140">Choose **Add**, and then choose **OK**.</span></span>

8. <span data-ttu-id="9e7b3-141">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-141">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="9e7b3-142">조직의 차단된 URL 목록을 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-142">Make sure to review your organization's custom list of blocked URLs.</span></span> <span data-ttu-id="9e7b3-143">[ATP 안전한 링크를 사용하여 차단된 사용자 지정 URL 목록을 설정하는 방법을 참조하세요.](set-up-a-custom-blocked-urls-list-atp.md)</span><span class="sxs-lookup"><span data-stu-id="9e7b3-143">See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-atp.md).</span></span>

## <a name="important-points-to-keep-in-mind"></a><span data-ttu-id="9e7b3-144">주의해야 할 중요 사항</span><span class="sxs-lookup"><span data-stu-id="9e7b3-144">Important points to keep in mind</span></span>

- <span data-ttu-id="9e7b3-145">"다시 쓰지 않습니다"목록에 지정하는 URL은 지정된 받는 사람에 대한 ATP 안전한 링크 검사에서 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-145">Any URLs that you specify in the "do not rewrite" list are excluded from ATP Safe Links scanning for the recipients that you specify.</span></span>

- <span data-ttu-id="9e7b3-146">사용자 환경을 개선하기 위해 일반적으로 사용되는 내부 URL을 "재작성 안 함" 목록에 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-146">Consider adding commonly used internal URLs to the "do not rewrite" list to improve the user experience.</span></span> <span data-ttu-id="9e7b3-147">예를 들어 비즈니스용 Skype, Sharepoint 등의 온-프레미스 서비스가 있는 경우 목록에 해당 URL을 추가하여 검사에서 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-147">For example, if you have on-premises services, such as Skype for Business or Sharepoint, you can add their URLs to the list to exclude them from scanning.</span></span>

- <span data-ttu-id="9e7b3-148">"다시 쓰지 않는" 목록에 이미 URL 목록이 있는 경우 해당 목록을 검토하고 와일드카드를 적절히 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-148">If you already have a list of URLs in your "do not rewrite" list, make sure to review that list and add wildcards as appropriate.</span></span> <span data-ttu-id="9e7b3-149">예를 들어 기존 목록에 입력문자가 있고 정책에 하위 경로를 포함하려면 항목에 `https://contoso.com/a` `https://contoso.com/a/b` 와일드카드를 `https://contoso.com/a/*` 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-149">For example, if your existing list has an entry like `https://contoso.com/a` and you want to include subpaths like `https://contoso.com/a/b` in your policy, add a wildcard to your entry so it looks like `https://contoso.com/a/*`.</span></span>

- <span data-ttu-id="9e7b3-150">ATP 안전한 링크 정책에 "재작성 안 함" 목록을 지정할 때는 최대 3개의 와일드카드()를 포함할 수 \* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-150">When you specify a "do not rewrite" list for an ATP Safe Links policy, you can include up to three wildcards (\*).</span></span> <span data-ttu-id="9e7b3-151">와일드카드에는 접두사 또는 하위 도메인이 명시적으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-151">Wildcards explicitly include prefixes or subdomains.</span></span> <span data-ttu-id="9e7b3-152">예를 들어, 사용자가 지정한 도메인의 하위 도메인 및 경로를 방문할 `contoso.com` `*.contoso.com/*` 수 `*.contoso.com/*` 있도록 하므로 항목이 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-152">For example, the entry `contoso.com` is not the same as `*.contoso.com/*`, because `*.contoso.com/*` allows people to visit subdomains and paths in the specified domain.</span></span>

<span data-ttu-id="9e7b3-153">다음 표에는 입력할 수 있는 항목과 입력 항목의 영향에 대한 예제가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-153">The following table lists examples of what you can enter and what effect those entries have.</span></span>

****

|<span data-ttu-id="9e7b3-154">예제 항목</span><span class="sxs-lookup"><span data-stu-id="9e7b3-154">Example Entry</span></span>|<span data-ttu-id="9e7b3-155">속성 기능</span><span class="sxs-lookup"><span data-stu-id="9e7b3-155">What It Does</span></span>|
|---|---|
|`contoso.com`|<span data-ttu-id="9e7b3-156">받는 사람이 하위 도메인 또는 경로와 `https://contoso.com` 같은 사이트만 방문할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-156">Allows recipients to visit a site like `https://contoso.com` but not subdomains or paths.</span></span>|
|`*.contoso.com/*`|<span data-ttu-id="9e7b3-157">받는 사람이 , 또는 와 같은 도메인, 하위 도메인 및 경로를 `https://www.contoso.com` `https://www.contoso.com` 방문할 `https://maps.contoso.com` 수 `https://www.contoso.com/a` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e7b3-157">Allows recipients to visit a domain, subdomains, and paths, such as `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `https://www.contoso.com/a`.</span></span> <br/><br/> <span data-ttu-id="9e7b3-158">이 항목은 사기성이 있는 사이트가 포함되어 있거나 같지 않을 때보다 `*contoso.com*` 본질적으로 더 `https://www.falsecontoso.com` 좋습니다. `https://www.false.contoso.completelyfalse.com`</span><span class="sxs-lookup"><span data-stu-id="9e7b3-158">This entry is inherently better than `*contoso.com*`, because it doesn't include potentially fraudulent sites, like `https://www.falsecontoso.com` or `https://www.false.contoso.completelyfalse.com`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="9e7b3-159">특정 받는 사람이 사이트(예: 하위 `https://contoso.com/a` 경로는 제외)를 방문할 수 있습니다. `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="9e7b3-159">Allows specific recipients to visit a site like `https://contoso.com/a`, but not subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a/*`|<span data-ttu-id="9e7b3-160">특정 받는 사람이 사이트(예: `https://contoso.com/a``https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="9e7b3-160">Allows specific recipients to visit a site like `https://contoso.com/a` and subpaths like `https://contoso.com/a/b`</span></span>|
|
