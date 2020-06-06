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
ms.openlocfilehash: c75f468aa98c8fa9e45cd596c62a7509310fdca5
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588135"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-atp-safe-links"></a><span data-ttu-id="9b2e4-103">ATP 안전한 링크를 사용 하 여 사용자 지정 쓰기 방지 Url 목록 설정</span><span class="sxs-lookup"><span data-stu-id="9b2e4-103">Set up a custom do-not-rewrite URLs list using ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b2e4-104">이 문서는 [Office 365 Advanced Threat Protection](office-365-atp.md)이 있는 비즈니스 고객을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="9b2e4-105">Outlook의 안전한 링크에 대 한 정보를 검색 하는 개인 사용자는 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="9b2e4-106">[Office 365 ATP (Advanced Threat Protection](office-365-atp.md) )를 사용 하는 경우 조직에 [사용자 지정 차단 된 url](set-up-a-custom-blocked-urls-list-atp.md)이 있을 수 있으며, 사용자가 전자 메일 메시지 또는 특정 Office 문서에서 웹 주소 (url)를 클릭할 때 이러한 url로 이동 하는 것이 방지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a [custom blocked URLs](set-up-a-custom-blocked-urls-list-atp.md), such that when people click on web addresses (URLs) in email messages or certain Office documents, they are prevented from going to those URLs.</span></span> <span data-ttu-id="9b2e4-107">조직에서 조직의 특정 그룹에 대해 사용자 지정 "다시 쓰지 않음" 목록을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-107">Your organization can also have custom "do not rewrite" lists for specific groups in your organization.</span></span> <span data-ttu-id="9b2e4-108">"다시 쓰지 않음" 목록을 사용 하면 일부 사용자가 [Office 365의 ATP 안전한 링크](atp-safe-links.md)에 의해 차단 되는 url을 방문할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-108">A "do not rewrite" list enables some people to visit URLs that are otherwise blocked by [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="9b2e4-109">이 문서에서는 ATP 안전한 링크 검색에서 제외 되는 Url 목록과 몇 가지 중요 한 사항을 염두에 두고 있는지를 지정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-109">This article describes how to specify a list of URLs that are excluded from ATP Safe Links scanning, and a few important points to keep in mind.</span></span>

## <a name="set-up-a-do-not-rewrite-list"></a><span data-ttu-id="9b2e4-110">"다시 쓰지 않음" 목록 설정</span><span class="sxs-lookup"><span data-stu-id="9b2e4-110">Set up a "do not rewrite" list</span></span>

<span data-ttu-id="9b2e4-111">ATP 안전한 링크 보호에서는 조직의 차단 된 Url 목록과 "다시 쓰지 않음" 목록 등 여러 목록을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-111">ATP Safe Links protection uses several lists, including your organization's blocked URLs list and the "do not rewrite" lists for exceptions.</span></span> <span data-ttu-id="9b2e4-112">필요한 사용 권한이 있는 경우 사용자 지정 "다시 쓰지 않음" 목록을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-112">If you have the necessary permissions, you can set up your custom "do not rewrite" lists.</span></span> <span data-ttu-id="9b2e4-113">조직의 특정 받는 사람에 게 적용 되는 안전 링크 정책을 추가 하거나 편집할 때이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-113">You do this when you add or edit Safe Links policies that apply to specific recipients in your organization.</span></span>

<span data-ttu-id="9b2e4-114">ATP 정책을 편집 하거나 정의 하려면 적절 한 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-114">To edit (or define) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="9b2e4-115">다음 표에는 몇 가지 예가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-115">The following table includes some examples.</span></span> <span data-ttu-id="9b2e4-116">자세한 내용은 [Security & 준수 센터의 사용 권한을](permissions-in-the-security-and-compliance-center.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-116">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

|<span data-ttu-id="9b2e4-117">역할</span><span class="sxs-lookup"><span data-stu-id="9b2e4-117">Role</span></span>  |<span data-ttu-id="9b2e4-118">할당 된 위치/방법</span><span class="sxs-lookup"><span data-stu-id="9b2e4-118">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="9b2e4-119">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="9b2e4-119">global administrator</span></span> |<span data-ttu-id="9b2e4-120">Microsoft 365을 구매 하기 위해 등록 하는 사람은 기본적으로 전역 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-120">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="9b2e4-121">자세한 내용은 [Microsoft 365 관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-121">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="9b2e4-122">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="9b2e4-122">Security Administrator</span></span> |<span data-ttu-id="9b2e4-123">Azure Active Directory 관리 센터 ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="9b2e4-123">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="9b2e4-124">Exchange Online 조직 관리</span><span class="sxs-lookup"><span data-stu-id="9b2e4-124">Exchange Online Organization Management</span></span> |<span data-ttu-id="9b2e4-125">Exchange 관리 센터 ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) )</span><span class="sxs-lookup"><span data-stu-id="9b2e4-125">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="9b2e4-126">또는</span><span class="sxs-lookup"><span data-stu-id="9b2e4-126">or</span></span> <br>  <span data-ttu-id="9b2e4-127">PowerShell cmdlet ( [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)참조)</span><span class="sxs-lookup"><span data-stu-id="9b2e4-127">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span></span> |

> [!TIP]
> <span data-ttu-id="9b2e4-128">역할 및 사용 권한에 대 한 자세한 내용은 [보안 & 준수 센터의 사용 권한을](permissions-in-the-security-and-compliance-center.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-128">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a><span data-ttu-id="9b2e4-129">사용자 지정 "다시 쓰지 않음" Url 목록을 보거나 편집 하려면</span><span class="sxs-lookup"><span data-stu-id="9b2e4-129">To view or edit a custom "do not rewrite" URLs list</span></span>

1. <span data-ttu-id="9b2e4-130">으로 이동 하 여 [https://protection.office.com](https://protection.office.com) 회사 또는 학교 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-130">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="9b2e4-131">왼쪽 탐색 창의 **위협 관리** \> **정책** \> **안전한 링크**아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-131">In the left navigation, under **Threat management** \> **Policy** \> **Safe Links**.</span></span>

3. <span data-ttu-id="9b2e4-132">**특정 받는 사람에 게 적용 되는 정책** 섹션에서 **새로** 만들기 (새로 만들기 단추를 더하기 기호 ()와 유사)를 선택 **+** 하 여 새 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-132">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)) to create a new policy.</span></span> <span data-ttu-id="9b2e4-133">또는 기존 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-133">(Alternatively, you can edit an existing policy.)</span></span><br/><span data-ttu-id="9b2e4-134">![특정 전자 메일 받는 사람에 대 한 안전한 링크 정책을 추가 하려면 새로 만들기를 선택 합니다.](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="9b2e4-134">![Choose New to add a Safe Links policy for specific email recipients](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>

4. <span data-ttu-id="9b2e4-135">정책에 대 한 이름 및 설명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-135">Specify a name and description for your policy.</span></span>

5. <span data-ttu-id="9b2e4-136">**다음 url을 다시 쓰지** 않음 구역에서 **올바른 url 입력** 상자를 선택 하 고 url을 입력 한 다음 더하기 기호 (+)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-136">In the **Do not rewrite the following URLs** section, select the **Enter a valid URL** box, and then type a URL, and then choose the plus sign (+).</span></span>

6. <span data-ttu-id="9b2e4-137">**적용 대상** 섹션에서 **받는 사람**을 선택 하 고 정책에 포함할 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-137">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy.</span></span> <span data-ttu-id="9b2e4-138">**추가**를 선택한 다음 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-138">Choose **Add**, and then choose **OK**.</span></span>

7. <span data-ttu-id="9b2e4-139">Url 추가가 완료 되 면 화면의 오른쪽 아래 모서리에서 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-139">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="9b2e4-140">조직의 차단 된 Url의 사용자 지정 목록을 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-140">Make sure to review your organization's custom list of blocked URLs.</span></span> <span data-ttu-id="9b2e4-141">[ATP 안전한 링크를 사용 하 여 차단 된 사용자 지정 url 목록 설정를](set-up-a-custom-blocked-urls-list-atp.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-141">See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-atp.md).</span></span>

## <a name="important-points-to-keep-in-mind"></a><span data-ttu-id="9b2e4-142">염두에 두어야 할 중요 사항</span><span class="sxs-lookup"><span data-stu-id="9b2e4-142">Important points to keep in mind</span></span>

- <span data-ttu-id="9b2e4-143">"다시 쓰지 않음" 목록에서 지정 하는 Url은 지정 된 받는 사람에 대 한 ATP 안전한 링크 검색에서 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-143">Any URLs that you specify in the "do not rewrite" list are excluded from ATP Safe Links scanning for the recipients that you specify.</span></span>

- <span data-ttu-id="9b2e4-144">"다시 쓰지 않음" 목록에 이미 Url 목록이 있는 경우 해당 목록을 검토 하 고 와일드 카드를 적절 하 게 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-144">If you already have a list of URLs in your "do not rewrite" list, make sure to review that list and add wildcards as appropriate.</span></span> <span data-ttu-id="9b2e4-145">예를 들어 기존 목록에 항목이 있는 경우 `https://contoso.com/a` 정책에 하위 경로를 포함 하려면 `https://contoso.com/a/b` 항목에 와일드 카드를 추가 하 여 표시 `https://contoso.com/a/*` 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-145">For example, if your existing list has an entry like `https://contoso.com/a` and you want to include subpaths like `https://contoso.com/a/b` in your policy, add a wildcard to your entry so it looks like `https://contoso.com/a/*`.</span></span>

- <span data-ttu-id="9b2e4-146">ATP 안전한 링크 정책에 대해 "다시 쓰지 않음" 목록을 지정 하는 경우 최대 3 개의 와일드 카드 별표 ()를 포함할 수 있습니다 \* .</span><span class="sxs-lookup"><span data-stu-id="9b2e4-146">When you specify a "do not rewrite" list for an ATP Safe Links policy, you can include up to three wildcard asterisks (\*).</span></span> <span data-ttu-id="9b2e4-147">와일드 카드 ( \* )는 접두사 또는 하위 도메인을 명시적으로 포함 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-147">Wildcards (\*) are used to explicitly include prefixes or subdomains.</span></span> <span data-ttu-id="9b2e4-148">이 항목은 `contoso.com` `*.contoso.com/*` 지정 된 `*.contoso.com/*` 도메인에서 peoples가 하위 도메인과 경로를 방문 하도록 허용 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-148">The entry `contoso.com` is not the same as `*.contoso.com/*`, because `*.contoso.com/*` allow peoples to visit subdomains and paths in the specified domain.</span></span>

<span data-ttu-id="9b2e4-149">다음 표에는 입력 가능한 항목과 해당 항목이 갖는 영향에 대 한 예가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-149">The following table lists examples of what you can enter and what effect those entries have.</span></span>

|<span data-ttu-id="9b2e4-150">**예제 항목**</span><span class="sxs-lookup"><span data-stu-id="9b2e4-150">**Example Entry**</span></span>|<span data-ttu-id="9b2e4-151">**수행 하는 작업**</span><span class="sxs-lookup"><span data-stu-id="9b2e4-151">**What It Does**</span></span>|
|:-----|:-----|
|`contoso.com`|<span data-ttu-id="9b2e4-152">받는 사람이 하위 도메인 또는 경로를 제외 하 고 사이트를 방문할 수 있도록 허용 `https://contoso.com` 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e4-152">Allows recipients to visit a site like `https://contoso.com` but not subdomains or paths.</span></span>|
|`*.contoso.com/*`|<span data-ttu-id="9b2e4-153">받는 사람이,, 또는 등의 도메인, 하위 도메인과 경로를 방문할 수 있습니다 `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` `https://www.contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="9b2e4-153">Allows recipients to visit a domain, subdomains, and paths, such as `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `https://www.contoso.com/a`.</span></span> <br/><br/> <span data-ttu-id="9b2e4-154">이 항목은 `*contoso.com*` 다음과 같이 잠재적으로 사기성 사이트를 포함 하지 않기 때문에 기본적으로 더 좋습니다. `https://www.falsecontoso.com``https://www.false.contoso.completelyfalse.com`</span><span class="sxs-lookup"><span data-stu-id="9b2e4-154">This entry is inherently better than `*contoso.com*`, because it doesn't include potentially fraudulent sites, like `https://www.falsecontoso.com` or `https://www.false.contoso.completelyfalse.com`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="9b2e4-155">특정 받는 사람이 같은 사이트를 방문 하 되 하위 경로는 볼 수 `https://contoso.com/a` 없습니다.`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="9b2e4-155">Allows specific recipients to visit a site like `https://contoso.com/a`, but not subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a/*`|<span data-ttu-id="9b2e4-156">특정 받는 사람이 같은 사이트와 같은 하위 경로를 방문할 수 있도록 허용 `https://contoso.com/a``https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="9b2e4-156">Allows specific recipients to visit a site like `https://contoso.com/a` and subpaths like `https://contoso.com/a/b`</span></span>|
