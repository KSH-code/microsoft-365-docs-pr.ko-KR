---
title: eDiscovery 도구의 사용 중지
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: In-Place eDiscovery 및 In-Place 보류(및 해당 PowerShell cmdlet)Exchange Online 2020년 상반기에는 사용 중지됩니다. 동일한 Search-Mailbox 기간 내에 Advanced eDiscovery v1.0도 사용 중지됩니다.
ms.openlocfilehash: 77a7daf36c86cd302f774e5a4b934148d3dfd5a7
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53340999"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a><span data-ttu-id="89b52-104">eDiscovery 도구의 사용 중지</span><span class="sxs-lookup"><span data-stu-id="89b52-104">Retirement of legacy eDiscovery tools</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89b52-105">이 문서에 설명된 레거시 eDiscovery 도구의 기능은 Microsoft 365 서비스에서 제거되거나 계속 사용할 수 있지만 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-105">The functionality of the legacy eDiscovery tools described in this article has either been removed from the Microsoft 365 service or is still available, but no longer supported.</span></span> <span data-ttu-id="89b52-106">사용 가능한 모든 기능은 예고 없이 제거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-106">Any functionality that's still available may be removed without notice.</span></span> <span data-ttu-id="89b52-107">이러한 레거시 도구를 계속 사용하는 경우 이 문서에 설명된 대안 중 하나 또는 Microsoft 365 규정 준수 센터 eDiscovery 도구로 마이그레이션하는 것이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-107">If you're still using any of these legacy tools, consider migrating to the eDiscovery tools in the Microsoft 365 compliance center or one of the alternatives described in this article.</span></span>

<span data-ttu-id="89b52-108">수년 동안 Microsoft는 전자 메일 콘텐츠를 검색, 미리 보기 및 내보낼 수 있는 eDiscovery 도구를 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="89b52-108">Over the years, Microsoft has provided eDiscovery tools that let you search, preview, and export email content from Exchange Online.</span></span> <span data-ttu-id="89b52-109">그러나 이러한 도구는 더 이상 Exchange Online 및 Microsoft 365 SharePoint 그룹과 같은 다른 Microsoft 365 서비스에서 비영구 콘텐츠를 검색하는 효과적인 Microsoft 365 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-109">However, these tools no longer offer an effective way to search for non-Exchange content in other Microsoft 365 services, such as SharePoint Online and Microsoft 365 Groups.</span></span> <span data-ttu-id="89b52-110">이를 해결하기 위해 Microsoft는 다양한 전자 메일 콘텐츠를 검색하는 데 도움이 되는 다른 eDiscovery Microsoft 365 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-110">To address this, Microsoft offers other eDiscovery tools that help you search for a wide variety of Microsoft 365 content.</span></span> <span data-ttu-id="89b52-111">또한 현재 및 강력한 eDiscovery 기능을 에 통합하기 위해 노력해 [Microsoft 365 규정 준수 센터.](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="89b52-111">And we've been working hard to incorporate the most current and powerful eDiscovery functionality in the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span> <span data-ttu-id="89b52-112">이를 통해 조직은 조직을 비롯한 여러 Microsoft 365 서비스에서 콘텐츠에 대한 법적, 내부 및 기타 문서 요청에 대응할 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="89b52-112">This allows organizations to respond to legal, internal, and other document requests for content across many Microsoft 365 services, including Exchange Online.</span></span>

<span data-ttu-id="89b52-113">Microsoft 365 규정 준수 센터 eDiscovery의 새로운 기능과 향상된 기능으로 인해 Exchange Online 및 2013에서 전자 메일 콘텐츠 검색과 관련된 다음과 같은 eDiscovery 관련 기능이 Exchange Online Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="89b52-113">As a result of this new and improved eDiscovery functionality in the Microsoft 365 compliance center, we're retiring the following eDiscovery-related features and functionality related to searching for email content in Exchange Online and Microsoft 365:</span></span>

- <span data-ttu-id="89b52-114">[Exchange](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) 관리 센터의 Exchange. [](/exchange/security-and-compliance/create-or-remove-in-place-holds)</span><span class="sxs-lookup"><span data-stu-id="89b52-114">[In-Place eDiscovery](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) and [In-Place Holds](/exchange/security-and-compliance/create-or-remove-in-place-holds) in the Exchange admin center.</span></span>

- <span data-ttu-id="89b52-115">Exchange Online 및 In-Place 보류를 지원하는 Exchange Online PowerShell cmd In-Place let입니다(이러한 cmdlet은 \**-MailboxSearch* cmdlet으로 총체적으로 식별됩니다).</span><span class="sxs-lookup"><span data-stu-id="89b52-115">The Exchange Online PowerShell cmdlets that support In-Place eDiscovery and In-Place Holds (these cmdlets are collectively identified as \**-MailboxSearch* cmdlets).</span></span> <span data-ttu-id="89b52-116">여기에는 다음 cmdlet이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-116">This includes the following cmdlets:</span></span>

  - [<span data-ttu-id="89b52-117">New-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="89b52-117">New-MailboxSearch</span></span>](/powershell/module/exchange/new-mailboxsearch)

  - [<span data-ttu-id="89b52-118">Start-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="89b52-118">Start-MailboxSearch</span></span>](/powershell/module/exchange/start-mailboxsearch)

  - [<span data-ttu-id="89b52-119">Stop-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="89b52-119">Stop-MailboxSearch</span></span>](/powershell/module/exchange/stop-mailboxsearch)

  - [<span data-ttu-id="89b52-120">Set-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="89b52-120">Set-MailboxSearch</span></span>](/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > <span data-ttu-id="89b52-121">[Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch) 및 [Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) cmdlet은 다른 \*\*\*\*-MailboxSearch\*\*\* cmdlet이 사용 중지된 후에 사용할 수 있으므로 다른 eDiscovery 및 유지 도구로의 전환에 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-121">The [Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch) and [Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) cmdlets will be available after the other \*\*\*\*-MailboxSearch\*\*\* cmdlets are retired so that you can use them to help in your transition to other eDiscovery and hold tools.</span></span> <span data-ttu-id="89b52-122">그러나 특정 날짜(아래 참조)가 지난 후 Microsoft 지원에서 더 이상 이러한 두 cmdlet을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-122">However, after a certain date (cited below) Microsoft Support will no longer supports these two cmdlets.</span></span>

- <span data-ttu-id="89b52-123">PowerShell에서 [검색-Exchange Online](/powershell/module/exchange/search-mailbox) cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-123">The [Search-Mailbox](/powershell/module/exchange/search-mailbox) cmdlet in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="89b52-124">웹 서비스 API의 Exchange 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-124">The following operations in the Exchange Web Services API:</span></span>

   - [<span data-ttu-id="89b52-125">GetSearchableMailboxes</span><span class="sxs-lookup"><span data-stu-id="89b52-125">GetSearchableMailboxes</span></span>](/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [<span data-ttu-id="89b52-126">SearchMailboxes</span><span class="sxs-lookup"><span data-stu-id="89b52-126">SearchMailboxes</span></span>](/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [<span data-ttu-id="89b52-127">SetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="89b52-127">SetHoldOnMailboxes</span></span>](/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [<span data-ttu-id="89b52-128">GetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="89b52-128">GetHoldOnMailboxes</span></span>](/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- <span data-ttu-id="89b52-129">[Office 365 Advanced eDiscovery v1.0은](./overview-ediscovery-20.md)Advanced eDiscovery 보안 및 준수 센터의 Core eDiscovery 사례를 통해 액세스되는 Office 365 & 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-129">[Office 365 Advanced eDiscovery v1.0](./overview-ediscovery-20.md), which is the first version of Advanced eDiscovery that's accessed through a Core eDiscovery case in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="89b52-130">v1.Advanced eDiscovery 사용 중지는 핵심 eDiscovery 사례를 만들고 관리하는 능력에 영향을 끼치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-130">The retirement of Advanced eDiscovery v1.0 doesn't impact your ability to create and manage Core eDiscovery cases.</span></span>

> [!NOTE]
> <span data-ttu-id="89b52-131">사용 중지되는 eDiscovery 기능은 클라우드 기반 버전의 Microsoft 365 Office 365.</span><span class="sxs-lookup"><span data-stu-id="89b52-131">The eDiscovery functionality being retired only applies to cloud-based versions of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="89b52-132">Exchange 및 SharePoint 버전의 eDiscovery 기능은 추가 공지가 있을 때까지 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-132">eDiscovery functionality in on-premises versions of Exchange and SharePoint will still be supported until further notice.</span></span>

<span data-ttu-id="89b52-133">이 문서의 다음 섹션에서는 사용 중지되는 각 기능에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-133">The following sections in this article provide guidance about each feature being retired.</span></span> <span data-ttu-id="89b52-134">이 정보에는 사용 중지된 도구 대신 사용할 수 있는 타임라인 및 대체 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-134">This information including timelines and alternative tools that you can use instead of the retired tool.</span></span>

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a><span data-ttu-id="89b52-135">In-Place 관리 In-Place eDiscovery 및 Exchange 보류</span><span class="sxs-lookup"><span data-stu-id="89b52-135">In-Place eDiscovery and In-Place Holds in the Exchange admin center</span></span> 

<span data-ttu-id="89b52-136">2017년 7월 1일의 원래 공지에 따라 EAC(Exchange 관리 센터)의 In-Place eDiscovery & 보류 기능이 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-136">As per the original announcement on July 1, 2017, the In-Place eDiscovery & Hold functionality in the Exchange admin center (EAC) is being retired.</span></span> <span data-ttu-id="89b52-137">EAC의 In-Place eDiscovery & 보류 페이지에서 콘텐츠를 검색, 보류 및 내보낼 수 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="89b52-137">The In-Place eDiscovery & Holds page in the EAC allowed you to search, hold, and export content from Exchange Online.</span></span> <span data-ttu-id="89b52-138">In-Place eDiscovery를 사용하면 검색 결과를 검색 사서함에 복사하여 사용자 또는 다른 eDiscovery 관리자가 콘텐츠를 검토하고 법률, 규정 및 공용 요청에 사용할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-138">In-Place eDiscovery also let you copy search results to a discovery mailbox so that you or other eDiscovery managers could review content and make it available for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="89b52-139">검색 결과를 검색 사서함에 복사하는 기능을 제외한 이러한 모든 기능을 이제 콘텐츠 검색에서 사용할 수 있기 때문에 Microsoft 365 규정 준수 센터(향상된 기능, 안정성 및 다양한 Microsoft 365 서비스에 대한 지원으로) eDiscovery 및 Advanced eDiscovery 도구를 사용할 수 있기 때문에 이러한 도구를 최대한 빨리 사용하는 것이 좋습니다. [](./microsoft-365-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="89b52-139">Because all of these capabilities (except for copying search results to a discovery mailbox) are now available in the content search, eDiscovery and Advanced eDiscovery tools in the [Microsoft 365 compliance center](./microsoft-365-compliance-center.md) (with improved functionality, reliability, and support for a wide range of Microsoft 365 services), we recommend that you start using these tools as soon as possible.</span></span> <span data-ttu-id="89b52-140">이러한 다른 eDiscovery 도구로의 전환을 지원하기 위해 아래 표에는 eDiscovery 및 보류를 사용하는 대신 사용할 In-Place In-Place 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-140">To help you in the transition to these other eDiscovery tools, the table below lists the tools you can use instead of In-Place eDiscovery and In-Place Hold.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="89b52-141">영향을 받는 조직의 범위</span><span class="sxs-lookup"><span data-stu-id="89b52-141">Scope of affected organizations</span></span>

- <span data-ttu-id="89b52-142">Office 365 및 Microsoft 365 Enterprise 조직</span><span class="sxs-lookup"><span data-stu-id="89b52-142">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="89b52-143">Office 365 및 Microsoft 365 Education 조직</span><span class="sxs-lookup"><span data-stu-id="89b52-143">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="89b52-144">Office 365 Microsoft 365 조직; 여기에는 GCC, GCC High 및 DoD가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-144">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="89b52-145">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="89b52-145">Office 365 Germany</span></span>

### <a name="timeline-for-retirement"></a><span data-ttu-id="89b52-146">사용 중지 타임라인</span><span class="sxs-lookup"><span data-stu-id="89b52-146">Timeline for retirement</span></span>

- <span data-ttu-id="89b52-147">2020년 7월 1일: 새 검색 및 보류를 만들 수 없지만 기존 검색을 실행, 편집 및 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-147">July 1, 2020: You won't be able to create new searches and holds, but you can still run, edit, and delete existing searches at your own risk.</span></span> <span data-ttu-id="89b52-148">Microsoft 지원은 더 이상 eDiscovery In-Place eDiscovery & 보류를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-148">Microsoft Support will no longer In-Place eDiscovery & Holds in the EAC.</span></span>

- <span data-ttu-id="89b52-149">2020년 10월 1일: In-Place eDiscovery & EAC의 보류 기능이 읽기 전용 모드로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-149">October 1, 2020: The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="89b52-150">즉, 기존 검색 및 보류만 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-150">This means you'll only be able to remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="89b52-151">대체 도구</span><span class="sxs-lookup"><span data-stu-id="89b52-151">Alternative tools</span></span>

<span data-ttu-id="89b52-152">다음 표에서는 사용 중지되는 기존 기능을 대체하는 데 사용할 수 있는 다른 도구에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-152">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="89b52-153">기능</span><span class="sxs-lookup"><span data-stu-id="89b52-153">Functionality</span></span></th>
<th><span data-ttu-id="89b52-154">대체 도구</span><span class="sxs-lookup"><span data-stu-id="89b52-154">Alternative tool</span></span></th>
<th><span data-ttu-id="89b52-155">설명</span><span class="sxs-lookup"><span data-stu-id="89b52-155">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="89b52-156">법적 목적으로 검색, 내보내기 및 보류</span><span class="sxs-lookup"><span data-stu-id="89b52-156">Search, export, and hold for legal purposes</span></span></td>
<td><span data-ttu-id="89b52-157">핵심 eDiscovery 사례의 Microsoft 365 규정 준수 센터</span><span class="sxs-lookup"><span data-stu-id="89b52-157">Core eDiscovery cases in the Microsoft 365 compliance center</span></span> </td>
<td><p><span data-ttu-id="89b52-158">핵심 eDiscovery 사례의 기능을 사용하여 eDiscovery 및 보류를 In-Place 기능 패리티를 In-Place 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-158">Using the capabilities of core eDiscovery cases provide the functional parity to In-Place eDiscovery and In-Place Holds.</span></span> <span data-ttu-id="89b52-159">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-159">This includes the following:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="89b52-160">검색이 수백만 위치에 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-160">Search scales to millions of locations</span></span></p>
</li>
<li>
<p><span data-ttu-id="89b52-161">콘텐츠를 검색, 내보내기 및 보류하기 위한 안정성 향상</span><span class="sxs-lookup"><span data-stu-id="89b52-161">Higher reliability for searching, exporting, and placing content on hold</span></span></p>
</li>
<li>
<p><span data-ttu-id="89b52-162">Exchange Online, SharePoint Online, 비즈니스용 OneDrive, 비즈니스용 Skype, Microsoft Teams, Yammer 그룹, Microsoft 365 그룹 및 Office 365 응용 프로그램에 저장된 기타 콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="89b52-162">Searching for content in for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, Yammer Groups, Microsoft 365 Groups, and other content stored in Office 365 applications</span></span></p></li></ul>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="89b52-163">보존 목적으로 보존</span><span class="sxs-lookup"><span data-stu-id="89b52-163">Hold for retention purposes</span></span></td>
<td><span data-ttu-id="89b52-164">정책의 Microsoft 365 규정 준수 센터</span><span class="sxs-lookup"><span data-stu-id="89b52-164">Retention policies in the Microsoft 365 compliance center</span></span></td>
<td><p><span data-ttu-id="89b52-165">보존 정책을 사용하여 콘텐츠를 보존하고, 필요한 경우 보존 기간이 만료된 후 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-165">You can use Retention policies to retain content and, if desired, delete it after the retention period expires.</span></span> <span data-ttu-id="89b52-166">기타 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-166">Other capabilities include:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="89b52-167">전체 조직에 정책 적용</span><span class="sxs-lookup"><span data-stu-id="89b52-167">Applying policies to your entire organization</span></span> </p>
</li><li>
<p><span data-ttu-id="89b52-168">Exchange Online, SharePoint Online, 비즈니스용 OneDrive, 비즈니스용 Skype, Microsoft Teams 및 Office 365 그룹과 같은 특정 콘텐츠 위치에 정책 적용</span><span class="sxs-lookup"><span data-stu-id="89b52-168">Applying policies to specific content locations such as Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, and Office 365 Groups</span></span></p></li>
<li>
<p><span data-ttu-id="89b52-169">특정 사용자에게 정책 적용</span><span class="sxs-lookup"><span data-stu-id="89b52-169">Applying policies to specific users</span></span></p></li></ul>
<p><span data-ttu-id="89b52-170">자세한 내용은 보존 정책 및 보존 레이블에 대해 자세히를 <a href="/microsoft-365/compliance/retention-policies">참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="89b52-170">For more information, see <a href="/microsoft-365/compliance/retention-policies"> Learn about retention policies and retention labels</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="89b52-171">검토를 위해 전자 메일 검색 결과를 검색 사서함에 복사</span><span class="sxs-lookup"><span data-stu-id="89b52-171">Copy email search results to a discovery mailbox for review</span></span></td><td><span data-ttu-id="89b52-172">v2.Advanced eDiscovery 검토 집합</span><span class="sxs-lookup"><span data-stu-id="89b52-172">Review sets in Advanced eDiscovery v2.0</span></span></td>
<td><p><span data-ttu-id="89b52-173">한 번 더 쉽게 Microsoft 365 콘텐츠를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-173">Reviewing content in Microsoft 365 has never been easier.</span></span> <span data-ttu-id="89b52-174">검토 집합에는 다음을 포함하여 검토에 필요한 시간 및 데이터를 줄이는 데 도움이 되는 다양한 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-174">Review sets have many great capabilities to help reduce the amount of time and data needed to review, including:</span></span></p>
<ul>
<li><p><span data-ttu-id="89b52-175">빠른 검색 쿼리 수행 및 검토 집합에서 콘텐츠 필터링</span><span class="sxs-lookup"><span data-stu-id="89b52-175">Perform fast search queries and filter content in a review set</span></span></p></li>
<li><p><span data-ttu-id="89b52-176">검토 집합의 콘텐츠 분석 여기에는 전자 메일 스레딩, 중복에 가까운 검색, 테마 분석 및 예측 코딩이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-176">Analyze content in a review set; this includes email threading, near-duplicate detection, Themes analysis, and Predictive coding</span></span></p></li>
<li><p><span data-ttu-id="89b52-177">검토 집합에서 문서 태그 지정</span><span class="sxs-lookup"><span data-stu-id="89b52-177">Tag documents in a review set</span></span></p></li>
<li><p><span data-ttu-id="89b52-178">변호사 클라이언트 권한 콘텐츠를 식별하는 데 도움이 되는 태그 지정 제안</span><span class="sxs-lookup"><span data-stu-id="89b52-178">Tagging suggestions to help identify attorney  client privilege content</span></span></p></li></ul>
<p><span data-ttu-id="89b52-179">자세한 내용은 M<a href="/microsoft-365/compliance/overview-ediscovery-20">icrosoft 365의 고급 eDiscovery 솔루션 개요</a>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89b52-179">For more information, see <a href="/microsoft-365/compliance/overview-ediscovery-20">Overview of the Advanced eDiscovery solution in Microsoft 365</a>.</span></span></p>
<p>
<p><span data-ttu-id="89b52-180">또는 검색 결과를 PST 파일로 내보낼 수 있습니다. 그런 다음 가져오기 Microsoft 365 사용하여 PST를 검색 사서함으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-180">Alternatively, you can export search results to PST files and then use Microsoft 365 Import service to import the PSTs to a discovery mailbox.</span></span> <span data-ttu-id="89b52-181">단계별 지침은 네트워크 업로드를 사용하여 PST 파일을 로 가져오기 <a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">Office 365.</a></span><span class="sxs-lookup"><span data-stu-id="89b52-181">For step-by-step instruction, see <a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">Use network upload to import PST files to Office 365</a>.</span></span>
</tr>
<tr class=even>
  <td><span data-ttu-id="89b52-182">한 사서함에서 다른 사서함으로 메시지 복사</span><span class="sxs-lookup"><span data-stu-id="89b52-182">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="89b52-183"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">사서함에 사용 권한 할당</a></span><span class="sxs-lookup"><span data-stu-id="89b52-183"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="89b52-184">다른 사용자의 전자 메일(예: 직원이 조직을 떠나 이전 직원의 전자 메일에 대한 액세스 권한을 다른 사용자에게 제공해야 하는 경우)에 액세스 권한을 부여하려면 이전 직원의 사서함에 액세스할 수 있는 권한을 해당 사용자에게 할당하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-184">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="89b52-185">따라서 사서함 항목을 다른 사용자 사서함 또는 공유 사서함에 복사하는 대신 원본 사서함에 액세스하는 데 필요한 사용 권한을 사용자에게 할당하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-185">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user the permissions necessary to access the source mailbox.</span></span></td>
  
  </tr>
<tr class="odd">
<td><span data-ttu-id="89b52-186">복구 가능한 항목 폴더에서 항목 복원</span><span class="sxs-lookup"><span data-stu-id="89b52-186">Restore items from the Recoverable Items folder</span></span></td>
  <td><span data-ttu-id="89b52-187"><a href="/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</span><span class="sxs-lookup"><span data-stu-id="89b52-187"><a href="/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</span></span></td>
  <td><span data-ttu-id="89b52-188">항목에 대한 삭제된 항목 보존 기간이 만료되지 않은 한 사서함에서 영구적으로 삭제된 항목(소프트 삭제된 항목)을 복원할 수 있습니다. <i></i></span><span class="sxs-lookup"><span data-stu-id="89b52-188">You can restore permanently deleted items (also known as <i>soft-deleted</i> items) in mailboxes, as long as the deleted item retention period for an item hasn't expired.</span></span> <span data-ttu-id="89b52-189">자세한 내용은 에서 <a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">복구 가능한 항목 폴더를 Exchange Online.</a></span><span class="sxs-lookup"><span data-stu-id="89b52-189">For more information, see <a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Recoverable Items folder in Exchange Online</a>.</span></span></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a><span data-ttu-id="89b52-190">eDiscovery 및 In-Place 보류에 In-Place FAQ</span><span class="sxs-lookup"><span data-stu-id="89b52-190">FAQs about In-Place eDiscovery and In-Place Holds</span></span>

<span data-ttu-id="89b52-191">**I use the copy search results functionality of In-Place eDiscovery & Holds in the EAC to copy search results to a discovery mailbox for review by attorneys. 현재는 어떤 옵션이 있나요?**</span><span class="sxs-lookup"><span data-stu-id="89b52-191">**I use the copy search results functionality of In-Place eDiscovery & Holds in the EAC to copy search results to a discovery mailbox for review by attorneys. What options do I have now?**</span></span>

<span data-ttu-id="89b52-192">현재 이 기능을 복제하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-192">There are two ways to replicate this functionality today.</span></span> <span data-ttu-id="89b52-193">첫 번째는 [v2.Advanced eDiscovery 검토 집합을 사용하는 것입니다.](./view-documents-in-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="89b52-193">The first is to use [review sets in Advanced eDiscovery v2.0](./view-documents-in-review-set.md).</span></span> <span data-ttu-id="89b52-194">검토 집합에는 빠른 문서 검색, 태그 지정, 전자 메일 스레딩, 중복에 가까운 그룹화, 테마 분석 및 예측 코딩과 같은 기존 검토 도구에서 볼 수 있는 여러 가지 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-194">Review sets have many of the same capabilities you see in a traditional review tool like fast search of documents, tagging, email threading, near duplicate grouping, themes analysis, and predictive coding.</span></span> <span data-ttu-id="89b52-195">검색 사서함을 계속 검토하려면 두 번째 옵션은 검색 결과를 PST 파일로 내보냈다가 Microsoft 준수 센터의 PST 가져오기 기능을 사용하여 [PST](use-network-upload-to-import-pst-files.md) 파일을 검색 사서함으로 가져오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-195">If you still want to use discovery mailboxes for review, the second option is to export search results to PST files and then import the PST files to a discovery mailbox by using the [PST import feature](use-network-upload-to-import-pst-files.md) in the Microsoft compliance center.</span></span>

<span data-ttu-id="89b52-196">**eDiscovery 관리자가 새 도구를 사용하여 검색할 수 있는 콘텐츠 위치(예: 사서함 또는 사이트)를 제어하는 방법**</span><span class="sxs-lookup"><span data-stu-id="89b52-196">**How do I control which content locations (such as mailboxes or sites) that can an eDiscovery manager can search using the new tools?**</span></span>

<span data-ttu-id="89b52-197">또한 Microsoft 365 규정 준수 센터 준수 경계를 사용하여 eDiscovery 관리자가 검색할 수 있는 콘텐츠 위치를 제어합니다. [](set-up-compliance-boundaries.md)</span><span class="sxs-lookup"><span data-stu-id="89b52-197">The Microsoft 365 compliance center also uses [compliance boundaries](set-up-compliance-boundaries.md) to control which content locations an eDiscovery Manager can search.</span></span> <span data-ttu-id="89b52-198">규정 준수 경계는 지리적 보드를 준수하는 데 필요한 기관 경계 또는 다국적 기업에 유지해야 하는 정부 기관에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-198">Compliance boundaries are useful in government entities that need to stay within agency boundaries or multi-national corporations required to respect geographical boarders.</span></span>

<span data-ttu-id="89b52-199">**현재 검색 및 보류를 현재 검색으로 이동하는 Microsoft 365 규정 준수 센터?**</span><span class="sxs-lookup"><span data-stu-id="89b52-199">**How can I move my current searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="89b52-200">PowerShell을 사용하여 EAC에서 eDiscovery In-Place 및 보류를 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-200">It's possible to migrate In-Place eDiscovery searches and holds from the EAC by using PowerShell.</span></span> <span data-ttu-id="89b52-201">자세한 내용은 [EAC에서](./migrate-legacy-ediscovery-searches-and-holds.md)검색 및 보류를 마이그레이션을 Microsoft 365 규정 준수 센터.</span><span class="sxs-lookup"><span data-stu-id="89b52-201">For instructions, see [Migrate searches and holds from the EAC to the Microsoft 365 compliance center](./migrate-legacy-ediscovery-searches-and-holds.md).</span></span>

## <a name="-mailboxsearch-cmdlets"></a><span data-ttu-id="89b52-202">\*-MailboxSearch cmdlet</span><span class="sxs-lookup"><span data-stu-id="89b52-202">\*-MailboxSearch cmdlets</span></span>

<span data-ttu-id="89b52-203">Exchange 관리 센터에서 2017년 7월 1일 발표된 원래 공지에 따라 In-Place eDiscovery & 보류 기능 및 해당 **\* -MailboxSearch** cmdlet은 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-203">As per the original notice announced on July 1, 2017 in the Exchange admin center, the In-Place eDiscovery & Hold functionality and the corresponding **\*-MailboxSearch** cmdlets are being retired.</span></span> <span data-ttu-id="89b52-204">이러한 cmdlet은 법적, 규정 및 공용 요청에 대한 사서함 콘텐츠를 검색, 보류 및 내보낼 수 있는 기능을 사용자에게 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-204">These cmdlets provide users the ability to search, hold, and export mailbox content for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="89b52-205">이러한 기능은 이제 향상된 [<span class="underline">성능과</span>](./microsoft-365-compliance-center.md) 확장성을 통해 Microsoft 365 규정 준수 센터 및 Office 365 Security & Compliance Center PowerShell에서 사용할 수 있기 때문에 이러한 향상된 cmdlet을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-205">Because these capabilities are now available in the [<span class="underline">Microsoft 365 compliance center</span>](./microsoft-365-compliance-center.md) and Office 365 Security & Compliance Center PowerShell with improved performance and scalability, you should using these improved cmdlets.</span></span> <span data-ttu-id="89b52-206">이러한 cmdlet에는 [<span class="underline"> \* -ComplianceCase,</span>](/powershell/module/exchange/get-compliancecase) [<span class="underline"> \* -ComplianceSearch,</span>](/powershell/module/exchange/get-compliancesearch) [<span class="underline"> \* -CaseHoldPolicy,</span>](/powershell/module/exchange/get-caseholdpolicy) [<span class="underline"> \* -CaseHoldRule</span>](/powershell/module/exchange/get-caseholdrule)및 [<span class="underline"> \* -ComplianceSearchAction이 포함됩니다.</span>](/powershell/module/exchange/get-compliancesearchaction)</span><span class="sxs-lookup"><span data-stu-id="89b52-206">These cmdlets include [<span class="underline">\*-ComplianceCase</span>](/powershell/module/exchange/get-compliancecase), [<span class="underline">\*-ComplianceSearch</span>](/powershell/module/exchange/get-compliancesearch), [<span class="underline">\*-CaseHoldPolicy</span>](/powershell/module/exchange/get-caseholdpolicy), [<span class="underline">\*-CaseHoldRule</span>](/powershell/module/exchange/get-caseholdrule), and [<span class="underline">\*-ComplianceSearchAction</span>](/powershell/module/exchange/get-compliancesearchaction).</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="89b52-207">영향을 받는 조직의 범위</span><span class="sxs-lookup"><span data-stu-id="89b52-207">Scope of affected organizations</span></span>

- <span data-ttu-id="89b52-208">Office 365 및 Microsoft 365 Enterprise 조직</span><span class="sxs-lookup"><span data-stu-id="89b52-208">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="89b52-209">Office 365 및 Microsoft 365 Education 조직</span><span class="sxs-lookup"><span data-stu-id="89b52-209">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="89b52-210">Office 365 Microsoft 365 조직; 여기에는 GCC, GCC High 및 DoD가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-210">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="89b52-211">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="89b52-211">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="89b52-212">시간 표시 막대</span><span class="sxs-lookup"><span data-stu-id="89b52-212">Timeline</span></span>

- <span data-ttu-id="89b52-213">2020년 7월 1일: **New-MailboxSearch를** 사용하여 새 In-Place eDiscovery 검색 및 In-Place 보류를 만들 수 없지만 cmdlet을 사용하여 기존 검색 및 보류를 실행, 편집 및 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-213">July 1, 2020: You won't be able to use **New-MailboxSearch** to create new In-Place eDiscovery searches and In-Place Holds, but you can still use cmdlets to run, edit, and delete existing searches and holds at your own risk.</span></span> <span data-ttu-id="89b52-214">Microsoft 지원은 더 이상 이러한 유형의 검색 및 보류에 대한 지원을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-214">Microsoft Support will no longer provide assistance for these types of searches and holds.</span></span>

- <span data-ttu-id="89b52-215">2020년 10월 1일: 앞서 설명한 In-Place eDiscovery & EAC의 보류 기능은 읽기 전용 모드로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-215">October 1, 2020: As previously stated, The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="89b52-216">즉, **New-MailboxSearch,** **Start-MailboxSearch** 또는 **Set-MailboxSearch** cmdlet을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-216">That also means that you won't be able to use the **New-MailboxSearch**, **Start-MailboxSearch**, or **Set-MailboxSearch** cmdlets.</span></span> <span data-ttu-id="89b52-217">기존 검색 및 보류만 검색 및 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-217">You'll only be able to get and remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="89b52-218">대체 도구</span><span class="sxs-lookup"><span data-stu-id="89b52-218">Alternative tools</span></span>

<span data-ttu-id="89b52-219">다음 표에서는 사용 중지되는 기존 기능을 대체하는 데 사용할 수 있는 다른 도구에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-219">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="89b52-220">기능</span><span class="sxs-lookup"><span data-stu-id="89b52-220">Functionality</span></span></th>
<th><span data-ttu-id="89b52-221">대체 도구</span><span class="sxs-lookup"><span data-stu-id="89b52-221">Alternative tools</span></span></th>
<th><span data-ttu-id="89b52-222">설명</span><span class="sxs-lookup"><span data-stu-id="89b52-222">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="89b52-223">검색 및 내보내기</span><span class="sxs-lookup"><span data-stu-id="89b52-223">Search and export</span></span></td>
<td><p><span data-ttu-id="89b52-224"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="89b52-224"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="89b52-225"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span><span class="sxs-lookup"><span data-stu-id="89b52-225"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p><span data-ttu-id="89b52-226"><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span><span class="sxs-lookup"><span data-stu-id="89b52-226"><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="89b52-227">ComplianceSearch 및 ComplianceSearchAction cmdlet은 함께 작동하여 콘텐츠를 검색하고 내보내는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-227">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="89b52-228">새 검색을 만들고 <strong>New-</strong>, <strong>Get-</strong>및 <strong>Start-ComplianceSearch</strong> cmdlet을 사용하여 검색 예상 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-228">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="89b52-229">그런 다음 <strong>New-ComplianceSearchAction</strong> cmdlet을 사용하여 검색 결과를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-229">Then you can use the <strong>New-ComplianceSearchAction</strong> cmdlet to export the search results.</span></span> <span data-ttu-id="89b52-230">검색 결과를 로컬 컴퓨터에 다운로드하려면 Microsoft 365 규정 준수 센터 핵심 eDiscovery 도구를 계속 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-230">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p>
<p>
<p><span data-ttu-id="89b52-231"><strong>참고:</strong> 이러한 cmdlet을 사용하여 핵심 eDiscovery 사례와 연결되지 않은 검색을 만드는 경우 이러한 검색은 <strong></strong> 해당 cmdlet의 콘텐츠 검색 페이지에 Microsoft 365 규정 준수 센터.</span><span class="sxs-lookup"><span data-stu-id="89b52-231"><strong>Note:</strong> If you use these cmdlets to create searches that aren't associated with a core eDiscovery case, these searches will be located on the <strong>Content search</strong> page in the Microsoft 365 compliance center.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="89b52-232">사서함에 콘텐츠 보류</span><span class="sxs-lookup"><span data-stu-id="89b52-232">Hold content in a mailbox</span></span></td>
<td><p><span data-ttu-id="89b52-233"><a href="/powershell/module/exchange/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span><span class="sxs-lookup"><span data-stu-id="89b52-233"><a href="/powershell/module/exchange/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span></span></p>
<p><span data-ttu-id="89b52-234"><a href="/powershell/module/exchange/get-caseholdrule"><span class="underline">\*-CaseHoldRule</span></a></span><span class="sxs-lookup"><span data-stu-id="89b52-234"><a href="/powershell/module/exchange/get-caseholdrule"><span class="underline">\*-CaseHoldRule</span></a></span></span></p>
<p><span data-ttu-id="89b52-235"><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span><span class="sxs-lookup"><span data-stu-id="89b52-235"><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="89b52-236">보류 Microsoft 365 규정 준수 센터 ComplianceCase와 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-236">Holds in the Microsoft 365 compliance center must be associated with a ComplianceCase.</span></span> <span data-ttu-id="89b52-237">먼저 준수 사례를 만든 다음 CaseHoldPolicy 및 CaseHoldRule을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-237">First, create the compliance case, and then create a CaseHoldPolicy and a CaseHoldRule.</span></span></p>
<p><span data-ttu-id="89b52-238"><strong>참고:</strong> CaseHoldRule을 만들지 않고 CaseHoldPolicy를 만들면 CaseHoldRule이 만들어지며 CaseHoldPolicy에 연결될 때까지 보류를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-238"><strong>Note:</strong> Creating a CaseHoldPolicy without a creating CaseHoldRule will render the hold inoperable until the CaseHoldRule is created and associated to the CaseHoldPolicy.</span></span> <span data-ttu-id="89b52-239">자세한 내용은 cmdlet 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="89b52-239">See the cmdlet documentation for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="89b52-240">검색 사서함에 검색 결과 복사</span><span class="sxs-lookup"><span data-stu-id="89b52-240">Copy search results to a discovery mailbox</span></span></td>
<td><span data-ttu-id="89b52-241">없음</span><span class="sxs-lookup"><span data-stu-id="89b52-241">None</span></span></td>
<td><span data-ttu-id="89b52-242">모든 Microsoft 365 서비스에 대한 액세스 권한을 제공하지는 못하기 때문에 이 기능을 직접적으로 대체할 Microsoft 365 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-242">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="89b52-243">대체 솔루션에 대한 자세한 내용은 아래 FAQ를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89b52-243">See the following FAQ below for alternative solutions.</span></span></td>
</tr>
  <tr class=even>
  <td><span data-ttu-id="89b52-244">한 사서함에서 다른 사서함으로 메시지 복사</span><span class="sxs-lookup"><span data-stu-id="89b52-244">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="89b52-245"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">사서함에 사용 권한 할당</a></span><span class="sxs-lookup"><span data-stu-id="89b52-245"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="89b52-246">다른 사용자의 전자 메일(예: 직원이 조직을 떠나 이전 직원의 전자 메일에 대한 액세스 권한을 다른 사용자에게 제공해야 하는 경우)에 액세스 권한을 부여하려면 이전 직원의 사서함에 액세스할 수 있는 권한을 해당 사용자에게 할당하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-246">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="89b52-247">따라서 사서함 항목을 다른 사용자 사서함 또는 공유 사서함에 복사하는 대신 원본 사서함에 액세스할 수 있는 사용자 권한을 할당하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-247">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a><span data-ttu-id="89b52-248">\***-MailboxSearch** cmdlet에 대한 FAQ</span><span class="sxs-lookup"><span data-stu-id="89b52-248">FAQs about \***-MailboxSearch** cmdlets</span></span>

<span data-ttu-id="89b52-249">**다른 eDiscovery 및 법적 조사를 위해 복사 검색을 사용하여 전자 메일 메시지 또는 인스턴트 메시지를 내보낼 수 있습니다. 이러한 cmdlet이 사용 중지된 후 사용할 수 있는 다른 옵션은 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="89b52-249">**We use Copy Search to export email messages or instant Messages for purposes other eDiscovery and legal investigations. What other options do we have after these cmdlets are retired?**</span></span>

<span data-ttu-id="89b52-250">[<span class="underline">Microsoft Graph</span>](https://developer.microsoft.com/en-us/graph) API는 **\* -MailboxSearch** cmdlet을 사용하는 것보다 훨씬 복원력 및 확장성이 훨씬 더 높은 분석 및 기타 목적으로 데이터를 추출하는 다양한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-250">The [<span class="underline">Microsoft Graph APIs</span>](https://developer.microsoft.com/en-us/graph) provide a number of methods for extracting data for analysis and other purposes that are far more resilient and scalable than the using the **\*-MailboxSearch** cmdlets.</span></span>

<span data-ttu-id="89b52-251">**검색 및 보류를 검색 및 보류 Microsoft 365 규정 준수 센터?**</span><span class="sxs-lookup"><span data-stu-id="89b52-251">**How can I migrate my searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="89b52-252">PowerShell 스크립트를 사용하여 In-Place eDiscovery 검색 및 보류를 Exchange 관리 센터에서 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-252">It's possible to migrate In-Place eDiscovery searches and holds from the Exchange admin center by using a PowerShell script.</span></span> <span data-ttu-id="89b52-253">자세한 내용은 [Migrate legacy eDiscovery searches and holds to the Microsoft 365 규정 준수 센터.](migrate-legacy-eDiscovery-searches-and-holds.md)</span><span class="sxs-lookup"><span data-stu-id="89b52-253">For more information, see [Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center](migrate-legacy-eDiscovery-searches-and-holds.md).</span></span>

<span data-ttu-id="89b52-254">**cmdlet이 사용 중지된 후에도 검색을 제거하거나 검색할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="89b52-254">**After the cmdlets are retired, will I still be able to remove or retrieve searches?**</span></span>

<span data-ttu-id="89b52-255">예. 검색을 만들고 수정하는 기능을 제거하기는 하지만 추가 알림이 있을 때까지 **Get-MailboxSearch** 및 **Remove-MailboxSearch를** 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-255">Yes, although we're removing the ability to create and modify searches, you'll still be able to use **Get-MailboxSearch** and **Remove-MailboxSearch** until further notice.</span></span> <span data-ttu-id="89b52-256">그러나 이러한 cmdlet의 사용은 퇴직일 이후에는 사용자 위험에 노출될 수 있으며 Microsoft 지원 서비스에서 더 이상 지원을 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-256">However, the use of these cmdlets will be at your own risk after the retirement dates and Microsoft Support will no longer be able to provide assistance.</span></span>

## <a name="search-mailbox-cmdlet"></a><span data-ttu-id="89b52-257">Search-Mailbox cmdlet</span><span class="sxs-lookup"><span data-stu-id="89b52-257">Search-Mailbox cmdlet</span></span>

<span data-ttu-id="89b52-258">Exchange Online PowerShell의 **Search-Mailbox** cmdlet은 2018년 다시 시작되는 cmdlet 출력의 경고에서 원래 발표된 그대로 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-258">The **Search-Mailbox** cmdlet in Exchange Online PowerShell is being retired as originally announced in a warning in the cmdlet output starting back in 2018.</span></span> <span data-ttu-id="89b52-259">**Search-Mailbox** cmdlet은 원래 사용자의 사서함을 검색하고 악성 콘텐츠를 삭제하는 데 사용되었다.</span><span class="sxs-lookup"><span data-stu-id="89b52-259">The **Search-Mailbox** cmdlet was originally used to search a user's mailbox and purge malicious content.</span></span> <span data-ttu-id="89b52-260">Office 365 Security & PowerShell에서 **New-ComplianceSearch** 및 **New-ComplianceSearchAction** cmdlet을 사용하여 콘텐츠를 검색하고 삭제하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-260">We recommend that you start using the **New-ComplianceSearch** and **New-ComplianceSearchAction** cmdlets in Office 365 Security & Compliance Center PowerShell to search for and purge content.</span></span> <span data-ttu-id="89b52-261">기본 제공 보안 환경을 위해 [<span class="underline"></span>](../security/index.yml) Microsoft 365 보안 기능은 전자 메일 및 기타 많은 보안 기능에 강력한 위협 방지 기능을 Microsoft 서비스.</span><span class="sxs-lookup"><span data-stu-id="89b52-261">For a built-in security experience, the [<span class="underline">Microsoft 365 security features</span>](../security/index.yml) provide robust threat protection for email and many other Microsoft services.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="89b52-262">영향을 받는 조직의 범위</span><span class="sxs-lookup"><span data-stu-id="89b52-262">Scope of affected organizations</span></span>

- <span data-ttu-id="89b52-263">Office 365 및 Microsoft 365 Enterprise 조직</span><span class="sxs-lookup"><span data-stu-id="89b52-263">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="89b52-264">Office 365 및 Microsoft 365 Education 조직</span><span class="sxs-lookup"><span data-stu-id="89b52-264">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="89b52-265">Office 365 Microsoft 365 조직; 여기에는 GCC, GCC High 및 DoD가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-265">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="89b52-266">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="89b52-266">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="89b52-267">시간 표시 막대</span><span class="sxs-lookup"><span data-stu-id="89b52-267">Timeline</span></span>

-  <span data-ttu-id="89b52-268">2020년 7월 1일: **Search-Mailbox** cmdlet을 더 이상 사용할 수 없습니다. Microsoft 지원에서 더 이상 지원을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-268">July 1, 2020: The **Search-Mailbox** cmdlet will no longer be available and Microsoft Support will no longer provide assistance.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="89b52-269">대체 도구</span><span class="sxs-lookup"><span data-stu-id="89b52-269">Alternative tools</span></span>

<span data-ttu-id="89b52-270">다음 표에서는 사용 중지되는 기존 기능을 대체하는 데 사용할 수 있는 다른 도구에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-270">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="89b52-271">기능</span><span class="sxs-lookup"><span data-stu-id="89b52-271">Functionality</span></span></th>
<th><span data-ttu-id="89b52-272">대체 도구</span><span class="sxs-lookup"><span data-stu-id="89b52-272">Alternative tools</span></span></th>
<th><span data-ttu-id="89b52-273">설명</span><span class="sxs-lookup"><span data-stu-id="89b52-273">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="89b52-274">사서함 검색</span><span class="sxs-lookup"><span data-stu-id="89b52-274">Search a mailbox</span></span></td>
<td><p><span data-ttu-id="89b52-275"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="89b52-275"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="89b52-276"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span><span class="sxs-lookup"><span data-stu-id="89b52-276"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></a></p></td>
<td><p><span data-ttu-id="89b52-277">ComplianceSearch 및 ComplianceSearchAction cmdlet은 함께 작동하여 콘텐츠를 검색하고 내보내는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-277">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="89b52-278">새 검색을 만들고 <strong>New-</strong>, <strong>Get-</strong>및 <strong>Start-ComplianceSearch</strong> cmdlet을 사용하여 검색 예상 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-278">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="89b52-279">그런 다음 <strong>New-ComplianceSearchAction -Export</strong> 명령을 사용하여 검색 결과를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-279">Then you can use the <strong>New-ComplianceSearchAction -Export</strong> command to export the search results.</span></span> <span data-ttu-id="89b52-280">검색 결과를 로컬 컴퓨터에 다운로드하려면 Microsoft 365 규정 준수 센터 핵심 eDiscovery 도구를 계속 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-280">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="89b52-281">사서함에서 대량 전자 메일 삭제</span><span class="sxs-lookup"><span data-stu-id="89b52-281">Delete bulk email from a mailbox</span></span></td>
<td><p><span data-ttu-id="89b52-282"><a href="/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes"><span class="underline">사서함에 대한 보관 및 삭제 정책 설정</span></a></span><span class="sxs-lookup"><span data-stu-id="89b52-282"><a href="/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes"><span class="underline">Set up an archive and deletion policy for mailboxes</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="89b52-283">관리자는 항목을 사용자의 보관 사서함으로 자동 이동하고 사서함에서 항목을 자동으로 삭제하는 보관 및 삭제 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-283">Admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox.</span></span></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="89b52-284">검색 사서함에 검색 결과 복사</span><span class="sxs-lookup"><span data-stu-id="89b52-284">Copy search results to a discovery mailbox</span></span></td>
<td> </td>
<td><span data-ttu-id="89b52-285">모든 Microsoft 365 서비스에 대한 액세스 권한을 제공하지는 못하기 때문에 이 기능을 직접적으로 대체할 Microsoft 365 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-285">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="89b52-286">대체 솔루션에 대한 자세한 내용은 <strong>\*-MailboxSearch cmdlets</strong> 섹션의 FAQ를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89b52-286">See the FAQs in the <strong>\*-MailboxSearch cmdlets</strong> section for alternative solutions.</span></span> </td>
</tr>
<tr class=odd>
  <td><span data-ttu-id="89b52-287">한 사서함에서 다른 사서함으로 메시지 복사</span><span class="sxs-lookup"><span data-stu-id="89b52-287">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="89b52-288"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">사서함에 사용 권한 할당</a></span><span class="sxs-lookup"><span data-stu-id="89b52-288"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="89b52-289">다른 사용자의 전자 메일(예: 직원이 조직을 떠나 이전 직원의 전자 메일에 대한 액세스 권한을 다른 사용자에게 제공해야 하는 경우)에 액세스 권한을 부여하려면 이전 직원의 사서함에 액세스할 수 있는 권한을 해당 사용자에게 할당하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-289">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="89b52-290">따라서 사서함 항목을 다른 사용자 사서함 또는 공유 사서함에 복사하는 대신 원본 사서함에 액세스할 수 있는 권한을 사용자에게 할당하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-290">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permission to access the source mailbox.</span></span></td>
</tr>
<tr class=even>
  <td><span data-ttu-id="89b52-291">사서함에서 메시지 제거</span><span class="sxs-lookup"><span data-stu-id="89b52-291">Purge messages from a mailbox</span></span></td>
<td><p><span data-ttu-id="89b52-292"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="89b52-292"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="89b52-293"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span><span class="sxs-lookup"><span data-stu-id="89b52-293"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="89b52-294">ComplianceSearch 및 ComplianceSearchAction cmdlet은 함께 작동하여 콘텐츠를 검색하고 삭제하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-294">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and purge content.</span></span> <span data-ttu-id="89b52-295"><strong>New-ComplianceSearch</strong> 및 <strong>New-ComplianceSearch</strong> cmdlet을 사용하여 검색을 만들고 실행한 다음 <strong>New-ComplianceSearchAction -Purge -PurgeType</strong> 명령을 사용하여 콘텐츠를 지울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-295">You can create and run a search with <strong>New-ComplianceSearch</strong> and <strong>New-ComplianceSearch</strong> cmdlets, and then you can purge the content by using <strong>New-ComplianceSearchAction -Purge -PurgeType</strong> command.</span></span> <span data-ttu-id="89b52-296">자세한 내용은 메시지 검색 <a href="/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">및 삭제를 참조하세요.</span></a></span><span class="sxs-lookup"><span data-stu-id="89b52-296">For more information, see <a href="/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Search for and delete messages</span></a>.</span></span></p>
</td>
</tr>
<tr class="odd"> 
<td><span data-ttu-id="89b52-297">사서함에서 메시지 제거</span><span class="sxs-lookup"><span data-stu-id="89b52-297">Purge messages from a mailbox</span></span></td>
<td><span data-ttu-id="89b52-298"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">사서함에 사용 권한 할당</a></span><span class="sxs-lookup"><span data-stu-id="89b52-298"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
<td><span data-ttu-id="89b52-299">사서함에서 메시지를 제거하려면 직원의 사서함에 액세스할 수 있는 관리자 권한을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-299">To purge messages from a mailbox, assign an administrator permissions to access the employee's mailbox.</span></span> <span data-ttu-id="89b52-300">메시지는 메시지의 기본 제공 검색 및 보기 기능을 사용하여 필요한 경우 삭제하고 재활용할 수 Outlook.</span><span class="sxs-lookup"><span data-stu-id="89b52-300">Messages can be deleted and recycled as needed taking advantage of the built-in search and viewing capabilities in Outlook.</span></span></td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a><span data-ttu-id="89b52-301">Exchange 웹 서비스 API 작업</span><span class="sxs-lookup"><span data-stu-id="89b52-301">Exchange Web Services API operations</span></span>

<span data-ttu-id="89b52-302">Exchange 웹 서비스 API의 이러한 작업은 Exchange 관리 센터의 In-Place eDiscovery & 보류 기능 및 Exchange Online PowerShell의 해당 **\* -MailboxSearch** cmdlet에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-302">These operations in the Exchange Web Services API are used by the In-Place eDiscovery & Holds feature in the Exchange admin center and the corresponding **\*-MailboxSearch** cmdlets in Exchange Online PowerShell.</span></span> <span data-ttu-id="89b52-303">또한 다른 레거시 eDiscovery 도구의 사용 중지의 일부로도 사용이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-303">They will also be retired as part of retiring the other legacy eDiscovery tools.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="89b52-304">영향을 받는 조직의 범위</span><span class="sxs-lookup"><span data-stu-id="89b52-304">Scope of affected organizations</span></span>

- <span data-ttu-id="89b52-305">Office 365 및 Microsoft 365 Enterprise 조직</span><span class="sxs-lookup"><span data-stu-id="89b52-305">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="89b52-306">Office 365 및 Microsoft 365 Education 조직</span><span class="sxs-lookup"><span data-stu-id="89b52-306">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="89b52-307">Office 365 Microsoft 365 조직; 여기에는 GCC, GCC High 및 DoD가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-307">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="89b52-308">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="89b52-308">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="89b52-309">시간 표시 막대</span><span class="sxs-lookup"><span data-stu-id="89b52-309">Timeline</span></span>

- <span data-ttu-id="89b52-310">2020년 7월 1일: GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes 및 GetHoldOnMailboxes 작업을 더 이상 사용할 수 없습니다. Microsoft 지원은 더 이상 지원을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-310">July 1, 2020: The GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes, and GetHoldOnMailboxes operations will no longer be available, and Microsoft Support will no longer provide assistance.</span></span>

## <a name="advanced-ediscovery-v10"></a><span data-ttu-id="89b52-311">Advanced eDiscovery v1.0</span><span class="sxs-lookup"><span data-stu-id="89b52-311">Advanced eDiscovery v1.0</span></span>

<span data-ttu-id="89b52-312">Advanced eDiscovery v1.0(핵심 eDiscovery 사례에서 사용할 수 있는 Advanced eDiscovery 버전인 v1.0은 Advanced eDiscovery 사용 중지됩니다. </span><span class="sxs-lookup"><span data-stu-id="89b52-312">Advanced eDiscovery v1.0, which is the version of Advanced eDiscovery available in a core eDiscovery case by clicking **Switch to Advanced eDiscovery**, is being retired.</span></span> <span data-ttu-id="89b52-313">해당 기능은 새 응용 Advanced eDiscovery [](./ediscovery.md) 솔루션으로 Microsoft 365 규정 준수 센터.</span><span class="sxs-lookup"><span data-stu-id="89b52-313">Its functionality has been replaced by the new [Advanced eDiscovery solution](./ediscovery.md) in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="89b52-314">조직에서 v1.0을 Advanced eDiscovery 확인:</span><span class="sxs-lookup"><span data-stu-id="89b52-314">To determine if your organization is using Advanced eDiscovery v1.0:</span></span>

1. <span data-ttu-id="89b52-315">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-315">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="89b52-316">준수 센터의 왼쪽 탐색 창에서 **eDiscovery**> Core를 클릭하고 Core eDiscovery 사례를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-316">In the left navigation pane of the compliance center, click **eDiscovery > Core**, and open a Core eDiscovery case.</span></span>

3. <span data-ttu-id="89b52-317">다음으로 전환 **단추가 Advanced eDiscovery** 클릭하면 사용 중지되는 1.0 버전의 Advanced eDiscovery 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-317">If you see the **Switch to Advanced eDiscovery** button, then clicking it will take you to the 1.0 version of Advanced eDiscovery, which is being retired.</span></span> <span data-ttu-id="89b52-318">Core eDiscovery에서 사례를 만들고 관리하는 능력은 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-318">The ability to create and manage cases in Core eDiscovery won't be affected.</span></span> <span data-ttu-id="89b52-319">v1.0으로 전환을 클릭하여 Advanced eDiscovery v1.0에서 사례 데이터를 추가하고 분석하는 Advanced eDiscovery **기능만** 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-319">Only the ability to add and analyze case data in Advanced eDiscovery v1.0 (by clicking **Switch to Advanced eDiscovery**) is being retired.</span></span>

<span data-ttu-id="89b52-320">Microsoft 365(Advanced eDiscovery *v2.0)의* 새로운 Advanced eDiscovery 솔루션은 원래 솔루션의 모든 기능을 제공하지만 이제 다른 Microsoft 365 서비스에서 콘텐츠를 식별하고 해당 콘텐츠를 수집한 다음 검토자는 빠른 검색 쿼리, 태그 지정 및 분석 기능을 활용하여 관련 문서를 선회하는 데 도움이 되는 검토 집합에 추가하는 관리자 기반 접근 방식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-320">The new Advanced eDiscovery solution in Microsoft 365 (also known as *Advanced eDiscovery v2.0*) provides all of the capabilities of the original solution, but now includes a custodian-based approach of identifying content in other Microsoft 365 services, collecting that content, and then adding it to a review set where reviewers can take advantage of fast search queries, tagging, and analytics features to help cull relevant documents.</span></span> <span data-ttu-id="89b52-321">Advanced eDiscovery Microsoft 파일 형식과 비 Microsoft 파일 형식 모두에 대한 향상된 처리 및 기본 [](./supported-filetypes-ediscovery20.md) 뷰어가 포함되어 있습니다. 여기에 파일 형식의 전체 목록이 있으며 지원되는 메타데이터 필드는 다음과 [같습니다.](./document-metadata-fields-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="89b52-321">Advanced eDiscovery now includes improved processing and native viewers for both Microsoft and non-Microsoft file types, a full list of file types is [here](./supported-filetypes-ediscovery20.md) and supported metadata fields are [here](./document-metadata-fields-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="89b52-322">또한 새로운 Advanced eDiscovery 솔루션에서는 다른 서비스의 콘텐츠에 보류를 적용하고, 보류를 사용자에게 알리고, 보유자 응답을 추적할 수 있는 강력한 보유 관리 기능을 Advanced eDiscovery 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-322">Also, the new Advanced eDiscovery solution provides a powerful custodian holds management feature that lets you apply holds to content in different services, notify users of the holds, and track custodian responses, all within an Advanced eDiscovery case.</span></span>

<span data-ttu-id="89b52-323">Advanced eDiscovery v2.0에 액세스하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-323">To access Advanced eDiscovery v2.0:</span></span>

1. <span data-ttu-id="89b52-324">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-324">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="89b52-325">Microsoft 365 규정 준수 센터의 왼쪽 탐색 창에서 **모두 표시** 를 클릭한 다음 **eDiscovery > Advanced** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-325">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Advanced**.</span></span>

<span data-ttu-id="89b52-326">이때 eDiscovery 워크플로를 새 Advanced eDiscovery 전환하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-326">At this time, we recommend that you begin to transition your eDiscovery workflow to the new Advanced eDiscovery functionality.</span></span> <span data-ttu-id="89b52-327">필요한 경우 콘텐츠를 내보내고 Advanced eDiscovery 1.0 사례를 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-327">If necessary, you can archive your Advanced eDiscovery 1.0 cases by exporting the content and storing it offline.</span></span> <span data-ttu-id="89b52-328">2020년 12월 31일까지는 기존 사례에서 Advanced eDiscovery v1.0에 계속 액세스할 수 있습니다. 그러나 Microsoft 지원은 2020년 10월 1일 이후에는 지원을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-328">Although you'll still be able to access Advanced eDiscovery v1.0 in existing cases until December 31, 2020, Microsoft Support won't provide support after October 1, 2020.</span></span> <span data-ttu-id="89b52-329">자세한 내용은 다음 타임라인을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89b52-329">See the following timeline for more details.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="89b52-330">영향을 받는 조직의 범위</span><span class="sxs-lookup"><span data-stu-id="89b52-330">Scope of affected organizations</span></span>

- <span data-ttu-id="89b52-331">Office 365 및 Microsoft 365 Enterprise 조직</span><span class="sxs-lookup"><span data-stu-id="89b52-331">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="89b52-332">Office 365 및 Microsoft 365 Education 조직</span><span class="sxs-lookup"><span data-stu-id="89b52-332">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="89b52-333">Office 365 Microsoft 365 조직; 여기에는 GCC, GCC High 및 DoD가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-333">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="89b52-334">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="89b52-334">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="89b52-335">시간 표시 막대</span><span class="sxs-lookup"><span data-stu-id="89b52-335">Timeline</span></span>

- <span data-ttu-id="89b52-336">2020년 7월 1일: v1.0 사례에서 새 Advanced eDiscovery 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-336">July 1, 2020: You won't be able to create new Advanced eDiscovery v1.0  cases.</span></span>

- <span data-ttu-id="89b52-337">2020년 10월 1일: 모든 경우에 새 데이터(검색 결과 준비)를 Advanced eDiscovery 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-337">October 1, 2020: You won't be able to add new data (Prepare search results for Advanced eDiscovery) to any cases.</span></span> <span data-ttu-id="89b52-338">기존 사례의 데이터를 계속 사용하여 작업을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-338">You'll be able to continue working with data in existing cases at your own risk.</span></span> <span data-ttu-id="89b52-339">Microsoft 지원이 더 이상 지원을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-339">Microsoft Support will no longer provide assistance.</span></span> 

- <span data-ttu-id="89b52-340">2020년 12월 31일: v1.0 사례에 액세스할 Advanced eDiscovery 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89b52-340">December 31, 2020: You won't be able to access Advanced eDiscovery v1.0 cases.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="89b52-341">대체 도구</span><span class="sxs-lookup"><span data-stu-id="89b52-341">Alternative tools</span></span>

<span data-ttu-id="89b52-342">Advanced eDiscovery [솔루션이](./overview-ediscovery-20.md) Microsoft 365 규정 준수 센터.</span><span class="sxs-lookup"><span data-stu-id="89b52-342">The [Advanced eDiscovery solution](./overview-ediscovery-20.md) in the Microsoft 365 compliance center.</span></span>