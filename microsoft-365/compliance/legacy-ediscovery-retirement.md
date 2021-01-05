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
description: In-Place eDiscovery 및 In-Place Hold(및 해당 PowerShell cmdlet)는 2020년 상반기부터 사용 중지됩니다. 또한 Search-Mailbox cmdlet 및 Advanced eDiscovery v1.0도 동일한 기간 내에 사용 중지됩니다.
ms.openlocfilehash: a40cc67b29e33d61d6750792f6a773622a73f678
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750881"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a><span data-ttu-id="ffdcc-104">eDiscovery 도구의 사용 중지</span><span class="sxs-lookup"><span data-stu-id="ffdcc-104">Retirement of legacy eDiscovery tools</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ffdcc-105">Microsoft는 공공 건강 상황을 평가해 오고 있으며, 이로인이 고객에게 미치는 영향에 대해 이해하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-105">Microsoft has been evaluating the public health situation, and we understand the impact this is having on our customers.</span></span> <span data-ttu-id="ffdcc-106">우리는 강력한 파트너이자 책임 있는 전역 시민이 되고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-106">We want to be strong partners and responsible global citizens.</span></span> <span data-ttu-id="ffdcc-107">직면하고 있는 많은 부담 중 하나를 완화하기 위해 이 문서에 설명된 레거시 eDiscovery 도구의 예정된 사용 중지를 3개월 연기할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-107">To ease one of the many burdens you are facing, we are going to delay the scheduled retirement for the legacy eDiscovery tools described in this article by three months.</span></span> <span data-ttu-id="ffdcc-108">**업데이트된 사용 중지 날짜는 아래와 같습니다.**</span><span class="sxs-lookup"><span data-stu-id="ffdcc-108">**The updated retirement dates are reflected below.**</span></span>

<span data-ttu-id="ffdcc-109">수년 동안 Microsoft는 Exchange Online에서 전자 메일 콘텐츠를 검색, 미리 보고 내보낼 수 있는 eDiscovery 도구를 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-109">Over the years, Microsoft has provided eDiscovery tools that let you search, preview, and export email content from Exchange Online.</span></span> <span data-ttu-id="ffdcc-110">그러나 이러한 도구는 더 이상 SharePoint Online 및 Microsoft 365 그룹과 같은 다른 Microsoft 365 서비스에서 비 Exchange 콘텐츠를 검색하는 효과적인 방법을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-110">However, these tools no longer offer an effective way to search for non-Exchange content in other Microsoft 365 services, such as SharePoint Online and Microsoft 365 Groups.</span></span> <span data-ttu-id="ffdcc-111">이 문제를 해결하기 위해 Microsoft는 다양한 Microsoft 365 콘텐츠를 검색하는 데 도움이 되는 다른 eDiscovery 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-111">To address this, Microsoft offers other eDiscovery tools that help you search for a wide variety of Microsoft 365 content.</span></span> <span data-ttu-id="ffdcc-112">Microsoft 365 규정 준수 센터에서 가장 강력하고 강력한 eDiscovery 기능을 통합하기 위해 [노력해 오고 있습니다.](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="ffdcc-112">And we've been working hard to incorporate the most current and powerful eDiscovery functionality in the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span> <span data-ttu-id="ffdcc-113">이를 통해 조직은 Exchange Online을 비롯한 여러 Microsoft 365 서비스에서 콘텐츠에 대한 법적, 내부 및 기타 문서 요청에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-113">This allows organizations to respond to legal, internal, and other document requests for content across many Microsoft 365 services, including Exchange Online.</span></span>

<span data-ttu-id="ffdcc-114">Microsoft 365 규정 준수 센터의 새로운 eDiscovery 기능과 향상된 eDiscovery 기능으로 인해 Exchange Online 및 Microsoft 365에서 전자 메일 콘텐츠 검색과 관련된 다음과 같은 eDiscovery 관련 기능이 사용 중지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-114">As a result of this new and improved eDiscovery functionality in the Microsoft 365 compliance center, we're retiring the following eDiscovery-related features and functionality related to searching for email content in Exchange Online and Microsoft 365:</span></span>

- <span data-ttu-id="ffdcc-115">Exchange 관리 센터의 [In-Place eDiscovery](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) 및 [In-Place Holds](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)</span><span class="sxs-lookup"><span data-stu-id="ffdcc-115">[In-Place eDiscovery](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) and [In-Place Holds](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) in the Exchange admin center.</span></span>

- <span data-ttu-id="ffdcc-116">In-Place eDiscovery 및 In-Place 보류를 지원하는 Exchange Online PowerShell cmdlet(이러한 cmdlet은 \**-MailboxSearch* cmdlet으로 총체적으로 식별됩니다).</span><span class="sxs-lookup"><span data-stu-id="ffdcc-116">The Exchange Online PowerShell cmdlets that support In-Place eDiscovery and In-Place Holds (these cmdlets are collectively identified as \**-MailboxSearch* cmdlets).</span></span> <span data-ttu-id="ffdcc-117">여기에는 다음 cmdlet이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-117">This includes the following cmdlets:</span></span>

  - [<span data-ttu-id="ffdcc-118">New-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="ffdcc-118">New-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-mailboxsearch)

  - [<span data-ttu-id="ffdcc-119">Start-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="ffdcc-119">Start-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/start-mailboxsearch)

  - [<span data-ttu-id="ffdcc-120">Stop-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="ffdcc-120">Stop-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/stop-mailboxsearch)

  - [<span data-ttu-id="ffdcc-121">Set-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="ffdcc-121">Set-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > <span data-ttu-id="ffdcc-122">[Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch) 및 [Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/remove-mailboxsearch) cmdlet은 다른 \*\*\*\*-MailboxSearch\*\*_ cmdlet이 사용 중지된 후에 사용할 수 있으므로 다른 eDiscovery 및 유지 도구로의 전환에 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-122">The [Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch) and [Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/remove-mailboxsearch) cmdlets will be available after the other \*\*\*\*-MailboxSearch\*\*_ cmdlets are retired so that you can use them to help in your transition to other eDiscovery and hold tools.</span></span> <span data-ttu-id="ffdcc-123">그러나 특정 날짜(아래 참조)가 지난 후 Microsoft 지원에서 이 두 cmdlet을 더 이상 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-123">However, after a certain date (cited below) Microsoft Support will no longer supports these two cmdlets.</span></span>

- <span data-ttu-id="ffdcc-124">Exchange Online PowerShell의 [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/search-mailbox) cmdlet</span><span class="sxs-lookup"><span data-stu-id="ffdcc-124">The [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/search-mailbox) cmdlet in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="ffdcc-125">Exchange 웹 서비스 API의 다음 작업</span><span class="sxs-lookup"><span data-stu-id="ffdcc-125">The following operations in the Exchange Web Services API:</span></span>

   - [<span data-ttu-id="ffdcc-126">GetSearchableMailboxes</span><span class="sxs-lookup"><span data-stu-id="ffdcc-126">GetSearchableMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [<span data-ttu-id="ffdcc-127">SearchMailboxes</span><span class="sxs-lookup"><span data-stu-id="ffdcc-127">SearchMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [<span data-ttu-id="ffdcc-128">SetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="ffdcc-128">SetHoldOnMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [<span data-ttu-id="ffdcc-129">GetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="ffdcc-129">GetHoldOnMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- <span data-ttu-id="ffdcc-130">[Office 365 Advanced eDiscovery v1.0 - Office 365](office-365-advanced-ediscovery.md)보안 및 준수 센터의 Core eDiscovery 사례를 통해 액세스되는 첫 번째 고급 eDiscovery & 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-130">[Office 365 Advanced eDiscovery v1.0](office-365-advanced-ediscovery.md), which is the first version of Advanced eDiscovery that's accessed through a Core eDiscovery case in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="ffdcc-131">Advanced eDiscovery v1.0의 사용 중지는 Core eDiscovery 사례를 만들고 관리하는 능력에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-131">The retirement of Advanced eDiscovery v1.0 doesn't impact your ability to create and manage Core eDiscovery cases.</span></span>

> [!NOTE]
> <span data-ttu-id="ffdcc-132">사용 중지되는 eDiscovery 기능은 클라우드 기반 버전의 Microsoft 365 및 Office 365에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-132">The eDiscovery functionality being retired only applies to cloud-based versions of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="ffdcc-133">Exchange 및 SharePoint의 eDiscovery 기능은 추가 공지가 있을 때까지 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-133">eDiscovery functionality in on-premises versions of Exchange and SharePoint will still be supported until further notice.</span></span>

<span data-ttu-id="ffdcc-134">이 문서의 다음 섹션에서는 사용 중지되는 각 기능에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-134">The following sections in this article provide guidance about each feature being retired.</span></span> <span data-ttu-id="ffdcc-135">이 정보에는 사용 중지된 도구 대신 사용할 수 있는 타임라인 및 대체 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-135">This information including timelines and alternative tools that you can use instead of the retired tool.</span></span>

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a><span data-ttu-id="ffdcc-136">In-Place 관리 센터에서 eDiscovery In-Place 보류</span><span class="sxs-lookup"><span data-stu-id="ffdcc-136">In-Place eDiscovery and In-Place Holds in the Exchange admin center</span></span> 

<span data-ttu-id="ffdcc-137">2017년 7월 1일의 원래 발표에 따라 EAC(Exchange 관리 센터)의 In-Place eDiscovery & 보류 기능이 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-137">As per the original announcement on July 1, 2017, the In-Place eDiscovery & Hold functionality in the Exchange admin center (EAC) is being retired.</span></span> <span data-ttu-id="ffdcc-138">EAC의 In-Place eDiscovery & 페이지에서 Exchange Online에서 콘텐츠를 검색, 보류 및 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-138">The In-Place eDiscovery & Holds page in the EAC allowed you to search, hold, and export content from Exchange Online.</span></span> <span data-ttu-id="ffdcc-139">In-Place eDiscovery를 사용하면 검색 결과를 검색 사서함에 복사하여 사용자 또는 다른 eDiscovery 관리자가 콘텐츠를 검토하고 법률, 규정 및 공용 요청에 사용할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-139">In-Place eDiscovery also let you copy search results to a discovery mailbox so that you or other eDiscovery managers could review content and make it available for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="ffdcc-140">검색 결과를 검색 사서함에 복사하는 것을 제외한 이러한 모든 기능은 이제 [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) 준수 센터의 콘텐츠 검색, eDiscovery 및 Advanced eDiscovery 도구(향상된 기능, 안정성 및 광범위한 Microsoft 365 서비스에 대한 지원)에서 사용할 수 있기 때문에 가능한 한 빨리 이러한 도구를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-140">Because all of these capabilities (except for copying search results to a discovery mailbox) are now available in the content search, eDiscovery and Advanced eDiscovery tools in the [Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) (with improved functionality, reliability, and support for a wide range of Microsoft 365 services), we recommend that you start using these tools as soon as possible.</span></span> <span data-ttu-id="ffdcc-141">이러한 다른 eDiscovery 도구로의 전환을 지원하기 위해 아래 표에는 eDiscovery 및 In-Place 대신 사용할 수 있는 도구가 In-Place 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-141">To help you in the transition to these other eDiscovery tools, the table below lists the tools you can use instead of In-Place eDiscovery and In-Place Hold.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="ffdcc-142">영향을 받는 조직의 범위</span><span class="sxs-lookup"><span data-stu-id="ffdcc-142">Scope of affected organizations</span></span>

- <span data-ttu-id="ffdcc-143">Office 365 및 Microsoft 365 Enterprise 조직</span><span class="sxs-lookup"><span data-stu-id="ffdcc-143">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="ffdcc-144">Office 365 및 Microsoft 365 Education 조직</span><span class="sxs-lookup"><span data-stu-id="ffdcc-144">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="ffdcc-145">Office 365 및 Microsoft 365 Government 조직 여기에는 GCC, GCC High 및 DoD가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-145">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="ffdcc-146">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="ffdcc-146">Office 365 Germany</span></span>

### <a name="timeline-for-retirement"></a><span data-ttu-id="ffdcc-147">사용 중지 타임라인</span><span class="sxs-lookup"><span data-stu-id="ffdcc-147">Timeline for retirement</span></span>

- <span data-ttu-id="ffdcc-148">2020년 7월 1일: 새 검색 및 보류를 만들 수 없지만 기존 검색을 실행, 편집 및 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-148">July 1, 2020: You won't be able to create new searches and holds, but you can still run, edit, and delete existing searches at your own risk.</span></span> <span data-ttu-id="ffdcc-149">Microsoft 지원 서비스에서는 더 In-Place eDiscovery & 보류를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-149">Microsoft Support will no longer In-Place eDiscovery & Holds in the EAC.</span></span>

- <span data-ttu-id="ffdcc-150">2020년 10월 1일: In-Place eDiscovery & EAC의 보류 기능이 읽기 전용 모드로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-150">October 1, 2020: The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="ffdcc-151">즉, 기존 검색 및 보류만 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-151">This means you'll only be able to remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="ffdcc-152">대체 도구</span><span class="sxs-lookup"><span data-stu-id="ffdcc-152">Alternative tools</span></span>

<span data-ttu-id="ffdcc-153">다음 표에서는 사용 중지되는 기존 기능을 대체하는 데 사용할 수 있는 다른 도구에 대해 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-153">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ffdcc-154">기능</span><span class="sxs-lookup"><span data-stu-id="ffdcc-154">Functionality</span></span></th>
<th><span data-ttu-id="ffdcc-155">대체 도구</span><span class="sxs-lookup"><span data-stu-id="ffdcc-155">Alternative tool</span></span></th>
<th><span data-ttu-id="ffdcc-156">설명</span><span class="sxs-lookup"><span data-stu-id="ffdcc-156">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ffdcc-157">법적 목적으로 검색, 내보내기 및 보류</span><span class="sxs-lookup"><span data-stu-id="ffdcc-157">Search, export, and hold for legal purposes</span></span></td>
<td><span data-ttu-id="ffdcc-158">Microsoft 365 규정 준수 센터의 핵심 eDiscovery 사례</span><span class="sxs-lookup"><span data-stu-id="ffdcc-158">Core eDiscovery cases in the Microsoft 365 compliance center</span></span> </td>
<td><p><span data-ttu-id="ffdcc-159">핵심 eDiscovery 사례의 기능을 사용하여 eDiscovery 및 In-Place 보류에 In-Place 패리티를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-159">Using the capabilities of core eDiscovery cases provide the functional parity to In-Place eDiscovery and In-Place Holds.</span></span> <span data-ttu-id="ffdcc-160">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-160">This includes the following:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="ffdcc-161">검색 규모가 수백만 위치로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-161">Search scales to millions of locations</span></span></p>
</li>
<li>
<p><span data-ttu-id="ffdcc-162">콘텐츠를 검색, 내보내기 및 보류하기 위한 안정성 향상</span><span class="sxs-lookup"><span data-stu-id="ffdcc-162">Higher reliability for searching, exporting, and placing content on hold</span></span></p>
</li>
<li>
<p><span data-ttu-id="ffdcc-163">Exchange Online, SharePoint Online, 비즈니스용 OneDrive, 비즈니스용 Skype, Microsoft Teams, Yammer 그룹, Microsoft 365 그룹 및 Office 365 응용 프로그램에 저장된 기타 콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="ffdcc-163">Searching for content in for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, Yammer Groups, Microsoft 365 Groups, and other content stored in Office 365 applications</span></span></p></li></ul>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="ffdcc-164">보존 목적으로 보존</span><span class="sxs-lookup"><span data-stu-id="ffdcc-164">Hold for retention purposes</span></span></td>
<td><span data-ttu-id="ffdcc-165">Microsoft 365 규정 준수 센터의 보존 정책</span><span class="sxs-lookup"><span data-stu-id="ffdcc-165">Retention policies in the Microsoft 365 compliance center</span></span></td>
<td><p><span data-ttu-id="ffdcc-166">보존 정책을 사용하여 콘텐츠를 보존하고, 필요한 경우 보존 기간이 만료된 후 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-166">You can use Retention policies to retain content and, if desired, delete it after the retention period expires.</span></span> <span data-ttu-id="ffdcc-167">기타 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-167">Other capabilities include:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="ffdcc-168">전체 조직에 정책 적용</span><span class="sxs-lookup"><span data-stu-id="ffdcc-168">Applying policies to your entire organization</span></span> </p>
</li><li>
<p><span data-ttu-id="ffdcc-169">Exchange Online, SharePoint Online, 비즈니스용 OneDrive, 비즈니스용 Skype, Microsoft Teams 및 Office 365 그룹과 같은 특정 콘텐츠 위치에 정책 적용</span><span class="sxs-lookup"><span data-stu-id="ffdcc-169">Applying policies to specific content locations such as Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, and Office 365 Groups</span></span></p></li>
<li>
<p><span data-ttu-id="ffdcc-170">특정 사용자에게 정책 적용</span><span class="sxs-lookup"><span data-stu-id="ffdcc-170">Applying policies to specific users</span></span></p></li></ul>
<p><span data-ttu-id="ffdcc-171">자세한 내용은 보존 정책 및 보존 레이블에 <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies">대한 자세한 내용을 참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="ffdcc-171">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies"> Learn about retention policies and retention labels</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ffdcc-172">검토를 위해 전자 메일 검색 결과를 검색 사서함에 복사</span><span class="sxs-lookup"><span data-stu-id="ffdcc-172">Copy email search results to a discovery mailbox for review</span></span></td><td><span data-ttu-id="ffdcc-173">Advanced eDiscovery v2.0의 검토 집합</span><span class="sxs-lookup"><span data-stu-id="ffdcc-173">Review sets in Advanced eDiscovery v2.0</span></span></td>
<td><p><span data-ttu-id="ffdcc-174">Microsoft 365의 콘텐츠를 검토하는 것이 그 한 번 더 쉬워졌습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-174">Reviewing content in Microsoft 365 has never been easier.</span></span> <span data-ttu-id="ffdcc-175">검토 집합에는 다음을 포함하여 검토에 필요한 시간 및 데이터를 줄이는 데 도움이 되는 다양한 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-175">Review sets have many great capabilities to help reduce the amount of time and data needed to review, including:</span></span></p>
<ul>
<li><p><span data-ttu-id="ffdcc-176">빠른 검색 쿼리 수행 및 검토 집합에서 콘텐츠 필터링</span><span class="sxs-lookup"><span data-stu-id="ffdcc-176">Perform fast search queries and filter content in a review set</span></span></p></li>
<li><p><span data-ttu-id="ffdcc-177">검토 집합의 콘텐츠를 분석합니다. 여기에는 전자 메일 스레딩, 중복에 가까운 검색, 테마 분석 및 예측 코딩이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-177">Analyze content in a review set; this includes email threading, near-duplicate detection, Themes analysis, and Predictive coding</span></span></p></li>
<li><p><span data-ttu-id="ffdcc-178">검토 집합에서 문서 태그 지정</span><span class="sxs-lookup"><span data-stu-id="ffdcc-178">Tag documents in a review set</span></span></p></li>
<li><p><span data-ttu-id="ffdcc-179">변호사 클라이언트 권한 콘텐츠를 식별하는 데 도움이 되는 태그 지정 제안</span><span class="sxs-lookup"><span data-stu-id="ffdcc-179">Tagging suggestions to help identify attorney  client privilege content</span></span></p></li></ul>
<p><span data-ttu-id="ffdcc-180">자세한 내용은 M<a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">icrosoft 365의 고급 eDiscovery 솔루션 개요</a>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-180">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Overview of the Advanced eDiscovery solution in Microsoft 365</a>.</span></span></p>
<p>
<p><span data-ttu-id="ffdcc-181">또는 검색 결과를 PST 파일로 내보낼 수 있는 다음 Microsoft 365 가져오기 서비스를 사용하여 PST를 검색 사서함으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-181">Alternatively, you can export search results to PST files and then use Microsoft 365 Import service to import the PSTs to a discovery mailbox.</span></span> <span data-ttu-id="ffdcc-182">단계별 지침은 네트워크 업로드를 사용하여 PST 파일을 <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">Office 365로 가져오는 방법을 참조합니다.</a></span><span class="sxs-lookup"><span data-stu-id="ffdcc-182">For step-by-step instruction, see <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">Use network upload to import PST files to Office 365</a>.</span></span>
</tr>
<tr class=even>
  <td><span data-ttu-id="ffdcc-183">한 사서함에서 다른 사서함으로 메시지 복사</span><span class="sxs-lookup"><span data-stu-id="ffdcc-183">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="ffdcc-184"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">사서함에 사용 권한 할당</a></span><span class="sxs-lookup"><span data-stu-id="ffdcc-184"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="ffdcc-185">다른 사용자의 전자 메일(예: 직원이 조직을 떠나 이전 직원의 전자 메일에 대한 액세스 권한을 다른 사용자에게 제공해야 하는 경우)에 대한 액세스 권한을 부여하려면 이전 직원의 사서함에 액세스할 수 있는 권한을 해당 사용자에게 할당하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-185">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="ffdcc-186">따라서 사서함 항목을 다른 사용자 사서함이나 공유 사서함에 복사하는 대신 원본 사서함에 액세스할 수 있는 권한을 사용자에게 할당하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-186">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
  
  </tr>
<tr class="odd">
<td><span data-ttu-id="ffdcc-187">복구 가능한 항목 폴더에서 항목 복원</span><span class="sxs-lookup"><span data-stu-id="ffdcc-187">Restore items from the Recoverable Items folder</span></span></td>
  <td><span data-ttu-id="ffdcc-188"><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</span><span class="sxs-lookup"><span data-stu-id="ffdcc-188"><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</span></span></td>
  <td><span data-ttu-id="ffdcc-189">항목의 삭제된 항목 보존 기간이 <i></i> 만료되지 않은 경우 사서함에서 영구적으로 삭제된 항목(소프트 삭제된 항목)을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-189">You can restore permanently deleted items (also known as <i>soft-deleted</i> items) in mailboxes, as long as the deleted item retention period for an item hasn't expired.</span></span> <span data-ttu-id="ffdcc-190">자세한 내용은 <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Exchange Online의 복구 가능한 항목 폴더를 참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="ffdcc-190">For more information, see <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Recoverable Items folder in Exchange Online</a>.</span></span></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a><span data-ttu-id="ffdcc-191">eDiscovery 및 In-Place 보류에 In-Place FAQ</span><span class="sxs-lookup"><span data-stu-id="ffdcc-191">FAQs about In-Place eDiscovery and In-Place Holds</span></span>

<span data-ttu-id="ffdcc-192">_ *I use the copy search results functionality of In-Place eDiscovery & Holds in the EAC to copy search results to a discovery mailbox for review by attorney. 현재는 어떤 옵션을 사용할 수 있나요?*\*</span><span class="sxs-lookup"><span data-stu-id="ffdcc-192">_ *I use the copy search results functionality of In-Place eDiscovery & Holds in the EAC to copy search results to a discovery mailbox for review by attorneys. What options do I have now?*\*</span></span>

<span data-ttu-id="ffdcc-193">현재 이 기능을 복제하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-193">There are two ways to replicate this functionality today.</span></span> <span data-ttu-id="ffdcc-194">첫 번째는 [Advanced eDiscovery v2.0에서 검토 집합을 사용하는 것입니다.](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set)</span><span class="sxs-lookup"><span data-stu-id="ffdcc-194">The first is to use [review sets in Advanced eDiscovery v2.0](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set).</span></span> <span data-ttu-id="ffdcc-195">검토 집합에는 빠른 문서 검색, 태그 지정, 전자 메일 스레딩, 가까운 중복 그룹화, 테마 분석 및 예측 코딩과 같은 기존 검토 도구에서 볼 수 있는 여러 가지 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-195">Review sets have many of the same capabilities you see in a traditional review tool like fast search of documents, tagging, email threading, near duplicate grouping, themes analysis, and predictive coding.</span></span> <span data-ttu-id="ffdcc-196">검색 사서함을 계속 검토하려면 두 번째 옵션은 검색 결과를 PST 파일로 내보냈다가 Microsoft 준수 센터의 PST 가져오기 기능을 사용하여 [PST](use-network-upload-to-import-pst-files.md) 파일을 검색 사서함으로 가져오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-196">If you still want to use discovery mailboxes for review, the second option is to export search results to PST files and then import the PST files to a discovery mailbox by using the [PST import feature](use-network-upload-to-import-pst-files.md) in the Microsoft compliance center.</span></span>

<span data-ttu-id="ffdcc-197">**eDiscovery 관리자가 새 도구를 사용하여 검색할 수 있는 콘텐츠 위치(예: 사서함 또는 사이트)를 제어하는 방법**</span><span class="sxs-lookup"><span data-stu-id="ffdcc-197">**How do I control which content locations (such as mailboxes or sites) that can an eDiscovery manager can search using the new tools?**</span></span>

<span data-ttu-id="ffdcc-198">또한 Microsoft 365 규정 [](set-up-compliance-boundaries.md) 준수 센터는 준수 경계를 사용하여 eDiscovery 관리자가 검색할 수 있는 콘텐츠 위치를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-198">The Microsoft 365 compliance center also uses [compliance boundaries](set-up-compliance-boundaries.md) to control which content locations an eDiscovery Manager can search.</span></span> <span data-ttu-id="ffdcc-199">규정 준수 경계는 지리적 보드를 준수하는 데 필요한 기관 경계 또는 다국적 기업에 유지해야 하는 정부 기관에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-199">Compliance boundaries are useful in government entities that need to stay within agency boundaries or multi-national corporations required to respect geographical boarders.</span></span>

<span data-ttu-id="ffdcc-200">**현재 검색 및 보류를 Microsoft 365 규정 준수 센터로 이동하는 방법**</span><span class="sxs-lookup"><span data-stu-id="ffdcc-200">**How can I move my current searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="ffdcc-201">PowerShell을 사용하여 EAC에서 eDiscovery In-Place 및 보류를 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-201">It's possible to migrate In-Place eDiscovery searches and holds from the EAC by using PowerShell.</span></span> <span data-ttu-id="ffdcc-202">자세한 내용은 [EAC에서 Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2114224)규정 준수 센터로 검색 및 보류 마이그레이션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-202">For instructions, see [Migrate searches and holds from the EAC to the Microsoft 365 compliance center](https://go.microsoft.com/fwlink/?linkid=2114224).</span></span>

## <a name="-mailboxsearch-cmdlets"></a><span data-ttu-id="ffdcc-203">\*-MailboxSearch cmdlet</span><span class="sxs-lookup"><span data-stu-id="ffdcc-203">\*-MailboxSearch cmdlets</span></span>

<span data-ttu-id="ffdcc-204">Exchange 관리 센터에서 2017년 7월 1일 발표된 원래 공지에 따라 In-Place eDiscovery & 보류 기능 및 해당 **\* -MailboxSearch** cmdlet은 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-204">As per the original notice announced on July 1, 2017 in the Exchange admin center, the In-Place eDiscovery & Hold functionality and the corresponding **\*-MailboxSearch** cmdlets are being retired.</span></span> <span data-ttu-id="ffdcc-205">이러한 cmdlet은 사용자에게 법적, 규정 및 공용 요청에 대한 사서함 콘텐츠를 검색, 보류 및 내보낼 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-205">These cmdlets provide users the ability to search, hold, and export mailbox content for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="ffdcc-206">이러한 기능은 이제 [<span class="underline">Microsoft 365</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) 규정 준수 센터 및 Office 365 보안 & 준수 센터 PowerShell에서 사용할 수 있기 때문에 향상된 성능 및 확장성을 사용하여 이러한 cmdlet을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-206">Because these capabilities are now available in the [<span class="underline">Microsoft 365 compliance center</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) and Office 365 Security & Compliance Center PowerShell with improved performance and scalability, you should using these improved cmdlets.</span></span> <span data-ttu-id="ffdcc-207">이러한 cmdlet에는 [<span class="underline"> \* -ComplianceCase,</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase) [<span class="underline"> \* -ComplianceSearch,</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch) [<span class="underline"> \* -CaseHoldPolicy,</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy) [<span class="underline"> \* -CaseHoldRule</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule)및 [<span class="underline"> \* -ComplianceSearchAction이 포함됩니다.</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)</span><span class="sxs-lookup"><span data-stu-id="ffdcc-207">These cmdlets include [<span class="underline">\*-ComplianceCase</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase), [<span class="underline">\*-ComplianceSearch</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch), [<span class="underline">\*-CaseHoldPolicy</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy), [<span class="underline">\*-CaseHoldRule</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule), and [<span class="underline">\*-ComplianceSearchAction</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction).</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="ffdcc-208">영향을 받는 조직의 범위</span><span class="sxs-lookup"><span data-stu-id="ffdcc-208">Scope of affected organizations</span></span>

- <span data-ttu-id="ffdcc-209">Office 365 및 Microsoft 365 Enterprise 조직</span><span class="sxs-lookup"><span data-stu-id="ffdcc-209">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="ffdcc-210">Office 365 및 Microsoft 365 Education 조직</span><span class="sxs-lookup"><span data-stu-id="ffdcc-210">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="ffdcc-211">Office 365 및 Microsoft 365 Government 조직 여기에는 GCC, GCC High 및 DoD가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-211">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="ffdcc-212">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="ffdcc-212">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="ffdcc-213">시간 표시 막대</span><span class="sxs-lookup"><span data-stu-id="ffdcc-213">Timeline</span></span>

- <span data-ttu-id="ffdcc-214">2020년 7월 1일: **New-MailboxSearch를** 사용하여 새 In-Place eDiscovery 검색 및 In-Place 보류를 만들 수 없지만 여전히 cmdlet을 사용하여 기존 검색 및 보류를 실행, 편집 및 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-214">July 1, 2020: You won't be able to use **New-MailboxSearch** to create new In-Place eDiscovery searches and In-Place Holds, but you can still use cmdlets to run, edit, and delete existing searches and holds at your own risk.</span></span> <span data-ttu-id="ffdcc-215">Microsoft 지원 서비스에서는 더 이상 이러한 유형의 검색 및 보류에 대한 지원을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-215">Microsoft Support will no longer provide assistance for these types of searches and holds.</span></span>

- <span data-ttu-id="ffdcc-216">2020년 10월 1일: 앞서 설명한 In-Place eDiscovery & EAC의 보류 기능이 읽기 전용 모드로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-216">October 1, 2020: As previously stated, The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="ffdcc-217">즉, **New-MailboxSearch,** **Start-MailboxSearch** 또는 **Set-MailboxSearch** cmdlet을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-217">That also means that you won't be able to use the **New-MailboxSearch**, **Start-MailboxSearch**, or **Set-MailboxSearch** cmdlets.</span></span> <span data-ttu-id="ffdcc-218">기존 검색 및 보류만 찾아서 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-218">You'll only be able to get and remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="ffdcc-219">대체 도구</span><span class="sxs-lookup"><span data-stu-id="ffdcc-219">Alternative tools</span></span>

<span data-ttu-id="ffdcc-220">다음 표에서는 사용 중지되는 기존 기능을 대체하는 데 사용할 수 있는 다른 도구에 대해 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-220">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ffdcc-221">기능</span><span class="sxs-lookup"><span data-stu-id="ffdcc-221">Functionality</span></span></th>
<th><span data-ttu-id="ffdcc-222">대체 도구</span><span class="sxs-lookup"><span data-stu-id="ffdcc-222">Alternative tools</span></span></th>
<th><span data-ttu-id="ffdcc-223">설명</span><span class="sxs-lookup"><span data-stu-id="ffdcc-223">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ffdcc-224">검색 및 내보내기</span><span class="sxs-lookup"><span data-stu-id="ffdcc-224">Search and export</span></span></td>
<td><p><span data-ttu-id="ffdcc-225"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="ffdcc-225"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="ffdcc-226"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span><span class="sxs-lookup"><span data-stu-id="ffdcc-226"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p><span data-ttu-id="ffdcc-227"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span><span class="sxs-lookup"><span data-stu-id="ffdcc-227"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="ffdcc-228">ComplianceSearch 및 ComplianceSearchAction cmdlet은 함께 작동하여 콘텐츠를 검색하고 내보내는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-228">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="ffdcc-229">새 검색을 만들고 <strong>New-</strong>, <strong>Get-</strong>및 <strong>Start-ComplianceSearch</strong> cmdlet을 사용하여 검색 예상 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-229">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="ffdcc-230">그런 다음 <strong>New-ComplianceSearchAction</strong> cmdlet을 사용하여 검색 결과를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-230">Then you can use the <strong>New-ComplianceSearchAction</strong> cmdlet to export the search results.</span></span> <span data-ttu-id="ffdcc-231">Microsoft 365 규정 준수 센터의 핵심 eDiscovery 도구를 사용하여 해당 검색 결과를 로컬 컴퓨터에 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-231">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p>
<p>
<p><span data-ttu-id="ffdcc-232"><strong>참고:</strong> 이러한 cmdlet을 사용하여 핵심 eDiscovery 사례와 연결되지 않은 검색을 만드는 경우 이러한 검색은 <strong></strong> Microsoft 365 규정 준수 센터의 콘텐츠 검색 페이지에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-232"><strong>Note:</strong> If you use these cmdlets to create searches that aren't associated with a core eDiscovery case, these searches will be located on the <strong>Content search</strong> page in the Microsoft 365 compliance center.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ffdcc-233">사서함에 콘텐츠 보류</span><span class="sxs-lookup"><span data-stu-id="ffdcc-233">Hold content in a mailbox</span></span></td>
<td><p><span data-ttu-id="ffdcc-234"><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span><span class="sxs-lookup"><span data-stu-id="ffdcc-234"><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span></span></p>
<p><span data-ttu-id="ffdcc-235"><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">\*-CaseHoldRule</span></a></span><span class="sxs-lookup"><span data-stu-id="ffdcc-235"><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">\*-CaseHoldRule</span></a></span></span></p>
<p><span data-ttu-id="ffdcc-236"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span><span class="sxs-lookup"><span data-stu-id="ffdcc-236"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="ffdcc-237">Microsoft 365 규정 준수 센터의 보류는 ComplianceCase와 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-237">Holds in the Microsoft 365 compliance center must be associated with a ComplianceCase.</span></span> <span data-ttu-id="ffdcc-238">먼저 준수 사례를 만든 다음 CaseHoldPolicy 및 CaseHoldRule을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-238">First, create the compliance case, and then create a CaseHoldPolicy and a CaseHoldRule.</span></span></p>
<p><span data-ttu-id="ffdcc-239"><strong>참고:</strong> CaseHoldRule을 만들지 않고 CaseHoldPolicy를 만들면 CaseHoldRule이 만들어지며 CaseHoldPolicy에 연결될 때까지 보류를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-239"><strong>Note:</strong> Creating a CaseHoldPolicy without a creating CaseHoldRule will render the hold inoperable until the CaseHoldRule is created and associated to the CaseHoldPolicy.</span></span> <span data-ttu-id="ffdcc-240">자세한 내용은 cmdlet 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-240">See the cmdlet documentation for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ffdcc-241">검색 결과를 검색 사서함에 복사</span><span class="sxs-lookup"><span data-stu-id="ffdcc-241">Copy search results to a discovery mailbox</span></span></td>
<td><span data-ttu-id="ffdcc-242">없음</span><span class="sxs-lookup"><span data-stu-id="ffdcc-242">None</span></span></td>
<td><span data-ttu-id="ffdcc-243">일부 Microsoft 365 서비스에 대한 액세스 권한을 제공하지는 못하기 때문에 이 기능을 직접 대체할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-243">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="ffdcc-244">대체 솔루션에 대한 자세한 내용은 아래 FAQ를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-244">See the following FAQ below for alternative solutions.</span></span></td>
</tr>
  <tr class=even>
  <td><span data-ttu-id="ffdcc-245">한 사서함에서 다른 사서함으로 메시지 복사</span><span class="sxs-lookup"><span data-stu-id="ffdcc-245">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="ffdcc-246"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">사서함에 사용 권한 할당</a></span><span class="sxs-lookup"><span data-stu-id="ffdcc-246"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="ffdcc-247">다른 사용자의 전자 메일(예: 직원이 조직을 떠나 이전 직원의 전자 메일에 대한 액세스 권한을 다른 사용자에게 제공해야 하는 경우)에 대한 액세스 권한을 부여하려면 이전 직원의 사서함에 액세스할 수 있는 권한을 해당 사용자에게 할당하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-247">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="ffdcc-248">따라서 사서함 항목을 다른 사용자 사서함이나 공유 사서함에 복사하는 대신 원본 사서함에 액세스할 수 있는 권한을 사용자에게 할당하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-248">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a><span data-ttu-id="ffdcc-249">\***-MailboxSearch** cmdlet에 대한 FAQ</span><span class="sxs-lookup"><span data-stu-id="ffdcc-249">FAQs about \***-MailboxSearch** cmdlets</span></span>

<span data-ttu-id="ffdcc-250">**다른 eDiscovery 및 법적 조사를 위해 복사 검색을 사용하여 전자 메일 메시지 또는 인스턴트 메시지를 내보낼 수 있습니다. 이러한 cmdlet이 사용 중지된 후의 다른 옵션은 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="ffdcc-250">**We use Copy Search to export email messages or instant Messages for purposes other eDiscovery and legal investigations. What other options do we have after these cmdlets are retired?**</span></span>

<span data-ttu-id="ffdcc-251">[<span class="underline">Microsoft Graph API는</span>](https://developer.microsoft.com/en-us/graph) **\* -MailboxSearch** cmdlet을 사용하는 것보다 훨씬 복원력 및 확장성이 훨씬 더 높은 분석 및 기타 목적으로 데이터를 추출하는 다양한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-251">The [<span class="underline">Microsoft Graph APIs</span>](https://developer.microsoft.com/en-us/graph) provide a number of methods for extracting data for analysis and other purposes that are far more resilient and scalable than the using the **\*-MailboxSearch** cmdlets.</span></span>

<span data-ttu-id="ffdcc-252">**검색 및 보류를 Microsoft 365 규정 준수 센터로 마이그레이션하려면 어떻게 하나요?**</span><span class="sxs-lookup"><span data-stu-id="ffdcc-252">**How can I migrate my searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="ffdcc-253">PowerShell 스크립트를 사용하여 Exchange In-Place eDiscovery 검색 및 보류를 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-253">It's possible to migrate In-Place eDiscovery searches and holds from the Exchange admin center by using a PowerShell script.</span></span> <span data-ttu-id="ffdcc-254">자세한 내용은 [레거시 eDiscovery](migrate-legacy-eDiscovery-searches-and-holds.md)검색 및 Microsoft 365 준수 센터로 보류 마이그레이션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-254">For more information, see [Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center](migrate-legacy-eDiscovery-searches-and-holds.md).</span></span>

<span data-ttu-id="ffdcc-255">**cmdlet이 사용 중지된 후에도 검색을 제거하거나 검색할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="ffdcc-255">**After the cmdlets are retired, will I still be able to remove or retrieve searches?**</span></span>

<span data-ttu-id="ffdcc-256">예. 검색을 만들고 수정하는 기능을 제거하겠지만 추가 알림이 표시될 때까지 **Get-MailboxSearch** 및 **Remove-MailboxSearch를** 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-256">Yes, although we're removing the ability to create and modify searches, you'll still be able to use **Get-MailboxSearch** and **Remove-MailboxSearch** until further notice.</span></span> <span data-ttu-id="ffdcc-257">그러나 이러한 cmdlet의 사용은 사용 중지 날짜 이후에는 사용자 위험에 노출될 수 있으며 Microsoft 지원 서비스에서 더 이상 지원을 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-257">However, the use of these cmdlets will be at your own risk after the retirement dates and Microsoft Support will no longer be able to provide assistance.</span></span>

## <a name="search-mailbox-cmdlet"></a><span data-ttu-id="ffdcc-258">Search-Mailbox cmdlet</span><span class="sxs-lookup"><span data-stu-id="ffdcc-258">Search-Mailbox cmdlet</span></span>

<span data-ttu-id="ffdcc-259">Exchange Online PowerShell의 **Search-Mailbox** cmdlet은 2018년으로 다시 시작되는 cmdlet 출력의 경고에서 원래 발표된 그대로 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-259">The **Search-Mailbox** cmdlet in Exchange Online PowerShell is being retired as originally announced in a warning in the cmdlet output starting back in 2018.</span></span> <span data-ttu-id="ffdcc-260">**Search-Mailbox** cmdlet은 원래 사용자의 사서함을 검색하고 악성 콘텐츠를 삭제하는 데 사용되었다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-260">The **Search-Mailbox** cmdlet was originally used to search a user's mailbox and purge malicious content.</span></span> <span data-ttu-id="ffdcc-261">Office 365 보안 및 준수 센터 PowerShell에서 **New-ComplianceSearch** 및 **New-ComplianceSearchAction** cmdlet을 & 콘텐츠를 검색하고 삭제하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-261">We recommend that you start using the **New-ComplianceSearch** and **New-ComplianceSearchAction** cmdlets in Office 365 Security & Compliance Center PowerShell to search for and purge content.</span></span> <span data-ttu-id="ffdcc-262">기본 제공 보안 환경을 위해 [<span class="underline">Microsoft 365</span>](https://docs.microsoft.com/microsoft-365/security/) 보안 기능은 전자 메일 및 기타 여러 Microsoft 서비스에 강력한 위협 방지 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-262">For a built-in security experience, the [<span class="underline">Microsoft 365 security features</span>](https://docs.microsoft.com/microsoft-365/security/) provide robust threat protection for email and many other Microsoft services.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="ffdcc-263">영향을 받는 조직의 범위</span><span class="sxs-lookup"><span data-stu-id="ffdcc-263">Scope of affected organizations</span></span>

- <span data-ttu-id="ffdcc-264">Office 365 및 Microsoft 365 Enterprise 조직</span><span class="sxs-lookup"><span data-stu-id="ffdcc-264">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="ffdcc-265">Office 365 및 Microsoft 365 Education 조직</span><span class="sxs-lookup"><span data-stu-id="ffdcc-265">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="ffdcc-266">Office 365 및 Microsoft 365 Government 조직 여기에는 GCC, GCC High 및 DoD가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-266">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="ffdcc-267">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="ffdcc-267">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="ffdcc-268">시간 표시 막대</span><span class="sxs-lookup"><span data-stu-id="ffdcc-268">Timeline</span></span>

-  <span data-ttu-id="ffdcc-269">2020년 7월 1일: **Search-Mailbox** cmdlet을 더 이상 사용할 수 없습니다. Microsoft 지원에서 더 이상 지원을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-269">July 1, 2020: The **Search-Mailbox** cmdlet will no longer be available and Microsoft Support will no longer provide assistance.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="ffdcc-270">대체 도구</span><span class="sxs-lookup"><span data-stu-id="ffdcc-270">Alternative tools</span></span>

<span data-ttu-id="ffdcc-271">다음 표에서는 사용 중지되는 기존 기능을 대체하는 데 사용할 수 있는 다른 도구에 대해 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-271">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ffdcc-272">기능</span><span class="sxs-lookup"><span data-stu-id="ffdcc-272">Functionality</span></span></th>
<th><span data-ttu-id="ffdcc-273">대체 도구</span><span class="sxs-lookup"><span data-stu-id="ffdcc-273">Alternative tools</span></span></th>
<th><span data-ttu-id="ffdcc-274">설명</span><span class="sxs-lookup"><span data-stu-id="ffdcc-274">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ffdcc-275">사서함 검색</span><span class="sxs-lookup"><span data-stu-id="ffdcc-275">Search a mailbox</span></span></td>
<td><p><span data-ttu-id="ffdcc-276"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="ffdcc-276"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="ffdcc-277"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span><span class="sxs-lookup"><span data-stu-id="ffdcc-277"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></a></p></td>
<td><p><span data-ttu-id="ffdcc-278">ComplianceSearch 및 ComplianceSearchAction cmdlet은 함께 작동하여 콘텐츠를 검색하고 내보내는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-278">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="ffdcc-279">새 검색을 만들고 <strong>New-</strong>, <strong>Get-</strong>및 <strong>Start-ComplianceSearch</strong> cmdlet을 사용하여 검색 예상 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-279">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="ffdcc-280">그런 다음 <strong>New-ComplianceSearchAction -Export</strong> 명령을 사용하여 검색 결과를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-280">Then you can use the <strong>New-ComplianceSearchAction -Export</strong> command to export the search results.</span></span> <span data-ttu-id="ffdcc-281">Microsoft 365 규정 준수 센터의 핵심 eDiscovery 도구를 사용하여 해당 검색 결과를 로컬 컴퓨터에 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-281">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="ffdcc-282">사서함에서 대량 전자 메일 삭제</span><span class="sxs-lookup"><span data-stu-id="ffdcc-282">Delete bulk email from a mailbox</span></span></td>
<td><p><span data-ttu-id="ffdcc-283"><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">사서함에 대한 보관 및 삭제 정책 설정</span></a></span><span class="sxs-lookup"><span data-stu-id="ffdcc-283"><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Set up an archive and deletion policy for mailboxes</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="ffdcc-284">관리자는 항목을 사용자의 보관 사서함으로 자동으로 이동하고 사서함에서 항목을 자동으로 삭제하는 보관 및 삭제 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-284">Admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox.</span></span></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="ffdcc-285">검색 결과를 검색 사서함에 복사</span><span class="sxs-lookup"><span data-stu-id="ffdcc-285">Copy search results to a discovery mailbox</span></span></td>
<td> </td>
<td><span data-ttu-id="ffdcc-286">일부 Microsoft 365 서비스에 대한 액세스 권한을 제공하지는 못하기 때문에 이 기능을 직접 대체할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-286">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="ffdcc-287">대체 솔루션에 대한 자세한 내용은 <strong>\*-MailboxSearch cmdlets</strong> 섹션의 FAQ를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-287">See the FAQs in the <strong>\*-MailboxSearch cmdlets</strong> section for alternative solutions.</span></span> </td>
</tr>
<tr class=odd>
  <td><span data-ttu-id="ffdcc-288">한 사서함에서 다른 사서함으로 메시지 복사</span><span class="sxs-lookup"><span data-stu-id="ffdcc-288">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="ffdcc-289"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">사서함에 사용 권한 할당</a></span><span class="sxs-lookup"><span data-stu-id="ffdcc-289"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="ffdcc-290">다른 사용자의 전자 메일(예: 직원이 조직을 떠나 이전 직원의 전자 메일에 대한 액세스 권한을 다른 사용자에게 제공해야 하는 경우)에 대한 액세스 권한을 부여하려면 이전 직원의 사서함에 액세스할 수 있는 권한을 해당 사용자에게 할당하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-290">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="ffdcc-291">따라서 사서함 항목을 다른 사용자 사서함이나 공유 사서함에 복사하는 대신 원본 사서함에 액세스할 수 있는 권한을 사용자에게 할당하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-291">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
</tr>
<tr class=even>
  <td><span data-ttu-id="ffdcc-292">사서함에서 메시지 제거</span><span class="sxs-lookup"><span data-stu-id="ffdcc-292">Purge messages from a mailbox</span></span></td>
<td><p><span data-ttu-id="ffdcc-293"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="ffdcc-293"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="ffdcc-294"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span><span class="sxs-lookup"><span data-stu-id="ffdcc-294"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="ffdcc-295">ComplianceSearch 및 ComplianceSearchAction cmdlet은 함께 작동하여 콘텐츠를 검색하고 삭제하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-295">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and purge content.</span></span> <span data-ttu-id="ffdcc-296"><strong>New-ComplianceSearch</strong> 및 <strong>New-ComplianceSearch</strong> cmdlet을 사용하여 검색을 만들고 실행한 다음 <strong>New-ComplianceSearchAction -Purge -PurgeType</strong> 명령을 사용하여 콘텐츠를 지울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-296">You can create and run a search with <strong>New-ComplianceSearch</strong> and <strong>New-ComplianceSearch</strong> cmdlets, and then you can purge the content by using <strong>New-ComplianceSearchAction -Purge -PurgeType</strong> command.</span></span> <span data-ttu-id="ffdcc-297">자세한 내용은 <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">메시지 검색 및 삭제를 참조하세요.</span></a></span><span class="sxs-lookup"><span data-stu-id="ffdcc-297">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Search for and delete messages</span></a>.</span></span></p>
</td>
</tr>
<tr class="odd"> 
<td><span data-ttu-id="ffdcc-298">사서함에서 메시지 제거</span><span class="sxs-lookup"><span data-stu-id="ffdcc-298">Purge messages from a mailbox</span></span></td>
<td><span data-ttu-id="ffdcc-299"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">사서함에 사용 권한 할당</a></span><span class="sxs-lookup"><span data-stu-id="ffdcc-299"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
<td><span data-ttu-id="ffdcc-300">사서함에서 메시지를 제거하려면 직원의 사서함에 액세스할 수 있는 관리자 권한을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-300">To purge messages from a mailbox, assign an administrator permissions to access the employee's mailbox.</span></span> <span data-ttu-id="ffdcc-301">Outlook의 기본 제공 검색 및 보기 기능을 활용하면 메시지를 삭제하고 필요한 경우 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-301">Messages can be deleted and recycled as needed taking advantage of the built in search and viewing capabilities in Outlook.</span></span></td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a><span data-ttu-id="ffdcc-302">Exchange 웹 서비스 API 작업</span><span class="sxs-lookup"><span data-stu-id="ffdcc-302">Exchange Web Services API operations</span></span>

<span data-ttu-id="ffdcc-303">Exchange 웹 서비스 API의 이러한 작업은 Exchange 관리 센터의 In-Place eDiscovery & 보류 기능 및 Exchange Online PowerShell의 **\* 해당 -MailboxSearch** cmdlet에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-303">These operations in the Exchange Web Services API are used by the In-Place eDiscovery & Holds feature in the Exchange admin center and the corresponding **\*-MailboxSearch** cmdlets in Exchange Online PowerShell.</span></span> <span data-ttu-id="ffdcc-304">또한 다른 레거시 eDiscovery 도구의 사용 중지의 일부로도 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-304">They will also be retired as part of retiring the other legacy eDiscovery tools.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="ffdcc-305">영향을 받는 조직의 범위</span><span class="sxs-lookup"><span data-stu-id="ffdcc-305">Scope of affected organizations</span></span>

- <span data-ttu-id="ffdcc-306">Office 365 및 Microsoft 365 Enterprise 조직</span><span class="sxs-lookup"><span data-stu-id="ffdcc-306">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="ffdcc-307">Office 365 및 Microsoft 365 Education 조직</span><span class="sxs-lookup"><span data-stu-id="ffdcc-307">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="ffdcc-308">Office 365 및 Microsoft 365 Government 조직 여기에는 GCC, GCC High 및 DoD가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-308">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="ffdcc-309">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="ffdcc-309">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="ffdcc-310">시간 표시 막대</span><span class="sxs-lookup"><span data-stu-id="ffdcc-310">Timeline</span></span>

- <span data-ttu-id="ffdcc-311">2020년 7월 1일: GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes 및 GetHoldOnMailboxes 작업을 더 이상 사용할 수 없습니다. Microsoft 지원 서비스에서는 더 이상 지원을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-311">July 1, 2020: The GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes, and GetHoldOnMailboxes operations will no longer be available, and Microsoft Support will no longer provide assistance.</span></span>

## <a name="advanced-ediscovery-v10"></a><span data-ttu-id="ffdcc-312">Advanced eDiscovery v1.0</span><span class="sxs-lookup"><span data-stu-id="ffdcc-312">Advanced eDiscovery v1.0</span></span>

<span data-ttu-id="ffdcc-313">Advanced eDiscovery로 전환을 클릭하여 핵심 eDiscovery 사례에서 사용할 수 있는 Advanced eDiscovery 버전인 **Advanced eDiscovery** v1.0은 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-313">Advanced eDiscovery v1.0, which is the version of Advanced eDiscovery available in a core eDiscovery case by clicking **Switch to Advanced eDiscovery**, is being retired.</span></span> <span data-ttu-id="ffdcc-314">해당 기능은 Microsoft 365 규정 준수 센터의 새로운 [Advanced eDiscovery](https://aka.ms/edisco) 솔루션으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-314">Its functionality has been replaced by the new [Advanced eDiscovery solution](https://aka.ms/edisco) in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="ffdcc-315">조직에서 Advanced eDiscovery v1.0을 사용하는지 확인:</span><span class="sxs-lookup"><span data-stu-id="ffdcc-315">To determine if your organization is using Advanced eDiscovery v1.0:</span></span>

1. <span data-ttu-id="ffdcc-316">[Office 365](https://protection.office.com)보안 및 준수 & 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-316">Go to the [Office 365 Security & Compliance Center](https://protection.office.com).</span></span>

2. <span data-ttu-id="ffdcc-317">Security & 규정 준수 센터의 왼쪽 탐색 창에서 **eDiscovery > eDiscovery를** 클릭하고 Core eDiscovery 사례를 여는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-317">In the left navigation pane of the Security & Compliance Center, click **eDiscovery > eDiscovery**, and open a Core eDiscovery case.</span></span>

3. <span data-ttu-id="ffdcc-318">**Advanced eDiscovery로** 전환 단추가 표시되어 있는 경우 이 단추를 클릭하면 사용 중지되는 Advanced eDiscovery의 1.0 버전으로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-318">If you see the **Switch to Advanced eDiscovery** button, then clicking it will take you to the 1.0 version of Advanced eDiscovery, which is being retired.</span></span> <span data-ttu-id="ffdcc-319">Core eDiscovery에서 사례를 만들고 관리하는 능력은 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-319">The ability to create and manage cases in Core eDiscovery won't be affected.</span></span> <span data-ttu-id="ffdcc-320">Advanced eDiscovery v1.0(Advanced **eDiscovery로** 전환 클릭)에서 사례 데이터를 추가하고 분석하는 기능만 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-320">Only the ability to add and analyze case data in Advanced eDiscovery v1.0 (by clicking **Switch to Advanced eDiscovery**) is being retired.</span></span>

<span data-ttu-id="ffdcc-321">Microsoft 365의 새로운 *Advanced eDiscovery 솔루션(Advanced eDiscovery v2.0)은* 원래 솔루션의 모든 기능을 제공하지만, 이제 다른 Microsoft 365 서비스에서 콘텐츠를 식별하고, 해당 콘텐츠를 수집한 다음 검토자들이 빠른 검색 쿼리, 태그 지정 및 분석 기능을 활용하여 관련 문서를 선점하는 데 도움이 되는 검토 집합에 추가하는 상속자 기반 접근 방식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-321">The new Advanced eDiscovery solution in Microsoft 365 (also known as *Advanced eDiscovery v2.0*) provides all of the capabilities of the original solution, but now includes a custodian-based approach of identifying content in other Microsoft 365 services, collecting that content, and then adding it to a review set where reviewers can take advantage of fast search queries, tagging, and analytics features to help cull relevant documents.</span></span> <span data-ttu-id="ffdcc-322">Advanced eDiscovery에는 이제 Microsoft 파일 형식과 비 Microsoft 파일 형식 모두에 대한 향상된 [](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) 처리 및 기본 뷰어가 포함되어 있습니다. 여기에 파일 형식의 전체 목록이 있으며 지원되는 메타데이터 필드는 다음과 [같습니다.](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery)</span><span class="sxs-lookup"><span data-stu-id="ffdcc-322">Advanced eDiscovery now includes improved processing and native viewers for both Microsoft and non-Microsoft file types, a full list of file types is [here](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) and supported metadata fields are [here](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery).</span></span> <span data-ttu-id="ffdcc-323">또한 새로운 Advanced eDiscovery 솔루션은 고급 eDiscovery 사례 내에서 다양한 서비스의 콘텐츠에 보류를 적용하고, 사용자에게 보류를 알리고, 보유자 응답을 추적할 수 있는 강력한 보유 관리 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-323">Also, the new Advanced eDiscovery solution provides a powerful custodian holds management feature that lets you apply holds to content in different services, notify users of the holds, and track custodian responses, all within an Advanced eDiscovery case.</span></span>

<span data-ttu-id="ffdcc-324">Advanced eDiscovery v2.0에 액세스하는 경우:</span><span class="sxs-lookup"><span data-stu-id="ffdcc-324">To access Advanced eDiscovery v2.0:</span></span>

1. <span data-ttu-id="ffdcc-325">[Microsoft 365 규정 준수 센터로 이동 합니다.](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="ffdcc-325">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="ffdcc-326">Microsoft 365 규정 준수 센터의 왼쪽 탐색 창에서 모두 표시를 클릭한 다음 **eDiscovery**> 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-326">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Advanced**.</span></span>

<span data-ttu-id="ffdcc-327">이때 eDiscovery 워크플로를 새 Advanced eDiscovery 기능으로 전환하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-327">At this time, we recommend that you begin to transition your eDiscovery workflow to the new Advanced eDiscovery functionality.</span></span> <span data-ttu-id="ffdcc-328">필요한 경우 콘텐츠를 내보내고 오프라인으로 저장하여 Advanced eDiscovery 1.0 사례를 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-328">If required, you can archive your Advanced eDiscovery 1.0 cases by exporting the content and storing it offline.</span></span> <span data-ttu-id="ffdcc-329">2020년 12월 31일까지 기존 사례에서 Advanced eDiscovery v1.0에 계속 액세스할 수 있습니다. 그러나 Microsoft 지원은 2020년 10월 1일 이후에는 지원을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-329">Although you'll still be able to access Advanced eDiscovery v1.0 in existing cases until December 31, 2020, Microsoft Support won't provide support after October 1, 2020.</span></span> <span data-ttu-id="ffdcc-330">자세한 내용은 다음 타임라인을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-330">See the following timeline for more details.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="ffdcc-331">영향을 받는 조직의 범위</span><span class="sxs-lookup"><span data-stu-id="ffdcc-331">Scope of affected organizations</span></span>

- <span data-ttu-id="ffdcc-332">Office 365 및 Microsoft 365 Enterprise 조직</span><span class="sxs-lookup"><span data-stu-id="ffdcc-332">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="ffdcc-333">Office 365 및 Microsoft 365 Education 조직</span><span class="sxs-lookup"><span data-stu-id="ffdcc-333">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="ffdcc-334">Office 365 및 Microsoft 365 Government 조직 여기에는 GCC, GCC High 및 DoD가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-334">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="ffdcc-335">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="ffdcc-335">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="ffdcc-336">시간 표시 막대</span><span class="sxs-lookup"><span data-stu-id="ffdcc-336">Timeline</span></span>

- <span data-ttu-id="ffdcc-337">2020년 7월 1일: 새 Advanced eDiscovery v1.0 사례를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-337">July 1, 2020: You won't be able to create new Advanced eDiscovery v1.0  cases.</span></span>

- <span data-ttu-id="ffdcc-338">2020년 10월 1일: 모든 경우에 새 데이터(Advanced eDiscovery에 대한 검색 결과 준비)를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-338">October 1, 2020: You won't be able to add new data (Prepare search results for Advanced eDiscovery) to any cases.</span></span> <span data-ttu-id="ffdcc-339">기존 사례의 데이터 작업을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-339">You'll be able to continue working with data in existing cases at your own risk.</span></span> <span data-ttu-id="ffdcc-340">Microsoft 지원 서비스에서 더 이상 지원을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-340">Microsoft Support will no longer provide assistance.</span></span> 

- <span data-ttu-id="ffdcc-341">2020년 12월 31일: Advanced eDiscovery v1.0 사례에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-341">December 31, 2020: You won't be able to access Advanced eDiscovery v1.0 cases.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="ffdcc-342">대체 도구</span><span class="sxs-lookup"><span data-stu-id="ffdcc-342">Alternative tools</span></span>

<span data-ttu-id="ffdcc-343">Microsoft 365 규정 준수 센터의 Advanced [eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="ffdcc-343">The [Advanced eDiscovery solution](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) in the Microsoft 365 compliance center.</span></span>
