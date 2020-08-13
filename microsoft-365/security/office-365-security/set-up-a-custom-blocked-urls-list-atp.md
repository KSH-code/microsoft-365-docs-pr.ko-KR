---
title: ATP 안전한 링크를 사용 하 여 차단 된 사용자 지정 Url 목록 설정
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365 Advanced Threat Protection을 사용 하 여 조직에 대해 차단 된 Url 목록을 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 5f863a3ba61278d0bec5304034ed75d343f93c77
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656650"
---
# <a name="set-up-a-custom-blocked-urls-list-using-atp-safe-links"></a><span data-ttu-id="17d8d-103">ATP 안전한 링크를 사용 하 여 차단 된 사용자 지정 Url 목록 설정</span><span class="sxs-lookup"><span data-stu-id="17d8d-103">Set up a custom blocked URLs list using ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="17d8d-104">이 문서는 [Office 365 Advanced Threat Protection](office-365-atp.md)이 있는 비즈니스 고객을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="17d8d-105">Outlook의 안전한 링크에 대 한 정보를 검색 하는 개인 사용자는 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="17d8d-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="17d8d-106">[Office 365 ATP (Advanced Threat Protection](office-365-atp.md) )를 사용 하는 경우 조직에는 차단 된 웹 사이트 주소 (url)의 사용자 지정 목록이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked.</span></span> <span data-ttu-id="17d8d-107">URL이 차단 되 면 차단 된 URL에 대 한 링크를 클릭 하는 사용자는 다음 이미지와 비슷한 [경고 페이지로](atp-safe-links-warning-pages.md) 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-107">When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span>

![이 사이트는 차단 됨](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

<span data-ttu-id="17d8d-109">차단 된 Url 목록은 조직의 Microsoft 365 for business security team에 의해 정의 되며,이 목록은 Office 365 ATP 안전한 링크 정책에서 다루는 조직의 모든 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-109">The blocked URLs list is defined by your organization's Microsoft 365 for business security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span>

<span data-ttu-id="17d8d-110">이 문서를 읽으면 [Office 365에서 ATP 안전한 링크](atp-safe-links.md)에 대 한 조직의 사용자 지정 차단 된 url 목록을 설정 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-110">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>

## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="17d8d-111">차단 된 Url의 사용자 지정 목록 보기 또는 편집</span><span class="sxs-lookup"><span data-stu-id="17d8d-111">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="17d8d-112">[Office 365의 ATP 안전한 링크](atp-safe-links.md) 는 조직의 사용자 지정 차단 된 url 목록을 포함 하 여 여러 목록을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-112">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list.</span></span> <span data-ttu-id="17d8d-113">필요한 사용 권한이 있는 경우 조직의 사용자 지정 목록을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-113">If you have the necessary permissions, you can set up your organization's custom list.</span></span> <span data-ttu-id="17d8d-114">조직의 기본 안전 링크 정책을 편집 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-114">You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="17d8d-115">ATP 정책을 편집 하거나 정의 하려면 다음 표에 설명 된 역할 중 하나를 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-115">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

****

|<span data-ttu-id="17d8d-116">역할</span><span class="sxs-lookup"><span data-stu-id="17d8d-116">Role</span></span>|<span data-ttu-id="17d8d-117">할당 된 위치/방법</span><span class="sxs-lookup"><span data-stu-id="17d8d-117">Where/how assigned</span></span>|
|---|---|
|<span data-ttu-id="17d8d-118">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="17d8d-118">global administrator</span></span>|<span data-ttu-id="17d8d-119">Microsoft 365을 구매 하기 위해 등록 하는 사람은 기본적으로 전역 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-119">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="17d8d-120">자세한 내용은 [Microsoft 365 관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="17d8d-120">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="17d8d-121">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="17d8d-121">Security Administrator</span></span>|<span data-ttu-id="17d8d-122">Azure Active Directory 관리 센터 ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="17d8d-122">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="17d8d-123">Exchange Online 조직 관리</span><span class="sxs-lookup"><span data-stu-id="17d8d-123">Exchange Online Organization Management</span></span>|<span data-ttu-id="17d8d-124">Exchange 관리 센터 ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) )</span><span class="sxs-lookup"><span data-stu-id="17d8d-124">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="17d8d-125">또는</span><span class="sxs-lookup"><span data-stu-id="17d8d-125">or</span></span> <br>  <span data-ttu-id="17d8d-126">PowerShell cmdlet ( [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)참조)</span><span class="sxs-lookup"><span data-stu-id="17d8d-126">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span></span>|
|

> [!TIP]
> <span data-ttu-id="17d8d-127">역할 및 사용 권한에 대 한 자세한 내용은 [보안 & 준수 센터의 사용 권한을](permissions-in-the-security-and-compliance-center.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="17d8d-127">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="17d8d-128">사용자 지정 차단 된 Url 목록을 보거나 편집 하려면</span><span class="sxs-lookup"><span data-stu-id="17d8d-128">To view or edit a custom blocked URLs list</span></span>

1. <span data-ttu-id="17d8d-129">으로 이동 하 여 [https://protection.office.com](https://protection.office.com) 회사 또는 학교 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-129">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="17d8d-130">왼쪽 탐색 창의 **위협 관리**에서 **정책** \> **안전한 링크**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-130">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>

3. <span data-ttu-id="17d8d-131">**전체 조직에 적용 되는 정책** 섹션에서 **기본값**을 선택 하 고 **편집** (편집 단추는 연필과 유사)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-131">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="17d8d-132">![안전한 링크 보호에 대 한 기본 정책을 편집 하려면 편집을 클릭 합니다.](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="17d8d-132">![Click Edit to edit your default policy for Safe Links protection](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="17d8d-133">이렇게 하면 차단 된 Url 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-133">This enables you to view your list of blocked URLs.</span></span> <span data-ttu-id="17d8d-134">처음에는 여기에 나열 된 Url이 없을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-134">At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="17d8d-135">![기본 안전 링크 정책의 차단 된 Url 목록](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="17d8d-135">![Blocked URLs list in the default Safe Links policy](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>

4. <span data-ttu-id="17d8d-136">**올바른 Url 입력** 상자를 선택 하 고 URL을 입력 한 다음 더하기 기호 ()를 선택 합니다 **+** .</span><span class="sxs-lookup"><span data-stu-id="17d8d-136">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span>

5. <span data-ttu-id="17d8d-137">Url 추가가 완료 되 면 화면의 오른쪽 아래 모서리에서 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-137">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>

## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="17d8d-138">염두에 두어야 할 몇 가지 사항</span><span class="sxs-lookup"><span data-stu-id="17d8d-138">A few things to keep in mind</span></span>

<span data-ttu-id="17d8d-139">목록에 Url을 추가 하는 동안 다음 사항을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-139">While you add URLs to your list, keep the following points in mind:</span></span>

- <span data-ttu-id="17d8d-140">URL의 끝에 슬래시 ()를 포함 하지 마십시오 **/** .</span><span class="sxs-lookup"><span data-stu-id="17d8d-140">Do not include a forward slash ( **/**) at the end of the URL.</span></span> <span data-ttu-id="17d8d-141">예를 들어를 입력 하는 대신 `https://www.contoso.com/` 를 입력 `https://www.contoso.com` 합니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-141">For example, instead of entering `https://www.contoso.com/`, enter `https://www.contoso.com`.</span></span>

- <span data-ttu-id="17d8d-142">도메인 전용 URL (like 또는)을 지정할 수 `contoso.com` 있습니다 `tailspintoys.com` .</span><span class="sxs-lookup"><span data-stu-id="17d8d-142">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`).</span></span> <span data-ttu-id="17d8d-143">이렇게 하면 도메인을 포함 하는 모든 URL의 클릭이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-143">This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="17d8d-144">`toys.contoso.com*`전체 도메인을 차단 하지 않고 하위 도메인을 지정할 수 있습니다 (like) `contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="17d8d-144">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`).</span></span> <span data-ttu-id="17d8d-145">하위 도메인이 포함 된 URL을 클릭 하는 것을 차단 하지만 전체 도메인이 포함 된 URL을 클릭 하는 것을 차단 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-145">This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>

- <span data-ttu-id="17d8d-146">URL 당 최대 3 개의 와일드 카드 별표 ()를 포함할 수 있습니다 \* .</span><span class="sxs-lookup"><span data-stu-id="17d8d-146">You can include up to three wildcard asterisks (\*) per URL.</span></span> <span data-ttu-id="17d8d-147">다음 표에는 입력 가능한 항목과 해당 항목이 갖는 영향에 대 한 몇 가지 예가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-147">The following table lists some examples of what you can enter and what effect those entries have.</span></span>

****

|<span data-ttu-id="17d8d-148">예제 항목</span><span class="sxs-lookup"><span data-stu-id="17d8d-148">Example Entry</span></span>|<span data-ttu-id="17d8d-149">수행 하는 작업</span><span class="sxs-lookup"><span data-stu-id="17d8d-149">What It Does</span></span>|
|---|---|
|<span data-ttu-id="17d8d-150">`contoso.com` 또는 `*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="17d8d-150">`contoso.com` or `*contoso.com*`</span></span>|<span data-ttu-id="17d8d-151">는과 같은 도메인, 하위 도메인과 경로를 차단 `https://www.contoso.com` `https://sub.contoso.com` 하며`https://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="17d8d-151">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="17d8d-152">사이트를 차단 `https://contoso.com/a` 하지만 추가 하위 경로는 제외 합니다.`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="17d8d-152">Blocks a site `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a*`|<span data-ttu-id="17d8d-153">사이트 `https://contoso.com/a` 및 추가 하위 경로를 차단 합니다.`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="17d8d-153">Blocks a site `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`</span></span>|
|`https://toys.contoso.com*`|<span data-ttu-id="17d8d-154">하위 도메인 (이 경우 "장난감")을 차단 하지만 클릭은 다른 도메인 Url (예 `https://contoso.com` , 또는 `https://home.contoso.com` )을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-154">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>|
|

> [!NOTE]
> <span data-ttu-id="17d8d-155">기본적으로 Office 365 ATP 안전한 링크 기본 정책의 차단 된 URL 목록에는 500 Url만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-155">By default, you can only add 500 URLs to the blocked URL list in the Office 365 ATP Safe Links default policy.</span></span>

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="17d8d-156">조직의 특정 사용자에 대 한 예외를 정의 하는 방법</span><span class="sxs-lookup"><span data-stu-id="17d8d-156">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="17d8d-157">특정 그룹에서 다른 사용자에 대해 차단 될 수 있는 Url을 볼 수 있도록 하려면 특정 받는 사람에 게 적용 되는 ATP 안전한 링크 정책을 지정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17d8d-157">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients.</span></span> <span data-ttu-id="17d8d-158">[ATP 안전한 링크를 사용 하 여 사용자 지정 "재작성 금지" url 목록 설정를](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="17d8d-158">See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
