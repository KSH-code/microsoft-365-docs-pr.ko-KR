---
title: 레거시 eDiscovery 도구 만료
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Exchange Online의 원본 위치 eDiscovery 및 원본 위치 유지 및 해당 PowerShell cmdlet은 2020의 처음 절반에서 만료 됩니다. 검색 사서함 cmdlet 및 Office 365 Advanced eDiscovery v 1.0은 동일한 기간 내에도 폐기 됩니다.
ms.openlocfilehash: 2d1f319986d761135e2c22b1d5882797f90f910c
ms.sourcegitcommit: 9ba28b255640c7b22f627613430dc69191bfaede
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2020
ms.locfileid: "43158439"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a><span data-ttu-id="3f9f2-104">레거시 eDiscovery 도구 만료</span><span class="sxs-lookup"><span data-stu-id="3f9f2-104">Retirement of legacy eDiscovery tools</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f9f2-105">Microsoft는 공개 상태 상황을 평가 했으며이로 인해 고객에 게 미치는 영향을 이해 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-105">Microsoft has been evaluating the public health situation, and we understand the impact this is having on our customers.</span></span> <span data-ttu-id="3f9f2-106">강력 하 게 파트너와 협력 하 고 글로벌 시민을 맡고 싶습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-106">We want to be strong partners and responsible global citizens.</span></span> <span data-ttu-id="3f9f2-107">이 문서에 설명 된 레거시 eDiscovery 도구에 대 한 예약 된 만료는 3 개월까지 지연 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-107">To ease one of the many burdens you are facing, we are going to delay the scheduled retirement for the legacy eDiscovery tools described in this article by three months.</span></span> <span data-ttu-id="3f9f2-108">**업데이트 된 만료 날짜는 아래에 반영 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="3f9f2-108">**The updated retirement dates are reflected below.**</span></span>

<span data-ttu-id="3f9f2-109">Microsoft는 지난 몇 년 동안 Exchange Online에서 전자 메일 콘텐츠를 검색, 미리 보기 및 내보내는 데 사용할 수 있는 eDiscovery 도구를 제공 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-109">Over the years, Microsoft has provided eDiscovery tools that let you search, preview, and export email content from Exchange Online.</span></span> <span data-ttu-id="3f9f2-110">그러나 이러한 도구는 더 이상 SharePoint Online 및 Office 365 그룹과 같은 다른 Office 365 서비스에서 비 Exchange 콘텐츠를 검색 하는 효율적인 방법을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-110">However, these tools no longer offer an effective way to search for non-Exchange content in other Office 365 services, such as SharePoint Online and Office 365 Groups.</span></span> <span data-ttu-id="3f9f2-111">이 문제를 해결 하기 위해 Microsoft는 광범위 한 Office 365 콘텐츠를 검색 하는 데 도움이 되는 기타 eDiscovery 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-111">To address this, Microsoft offers other eDiscovery tools that help you search for a wide variety of Office 365 content.</span></span> <span data-ttu-id="3f9f2-112">그리고 [Microsoft 365 준수 센터](https://compliance.microsoft.com)의 최신 eDiscovery 기능을 최신 및 강력 하 게 통합 하는 것이 어려운 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-112">And we've been working hard to incorporate the most current and powerful eDiscovery functionality in the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span> <span data-ttu-id="3f9f2-113">이를 통해 조직은 Exchange Online을 비롯 한 여러 Office 365 서비스에서 콘텐츠에 대 한 법적, 내부 및 기타 문서 요청에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-113">This allows organizations to respond to legal, internal, and other document requests for content across many Office 365 services, including Exchange Online.</span></span>

<span data-ttu-id="3f9f2-114">Microsoft 365 준수 센터에서 새롭게 향상 된 eDiscovery 기능을 사용 하는 경우 Exchange Online 및 Office 365에서 전자 메일 콘텐츠를 검색 하는 데 관련 된 다음과 같은 eDiscovery 관련 기능과 기능이 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-114">As a result of this new and improved eDiscovery functionality in the Microsoft 365 compliance center, we're retiring the following eDiscovery-related features and functionality related to searching for email content in Exchange Online and Office 365:</span></span>

- <span data-ttu-id="3f9f2-115">Exchange 관리 센터의 원본 [위치 eDiscovery](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) 및 [현재 위치 유지](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)</span><span class="sxs-lookup"><span data-stu-id="3f9f2-115">[In-Place eDiscovery](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) and [In-Place Holds](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) in the Exchange admin center.</span></span>

- <span data-ttu-id="3f9f2-116">원본 위치 eDiscovery 및 원본 위치 유지를 지 원하는 Exchange Online PowerShell cmdlet (이러한 cmdlet은*new-mailboxsearch* cmdlet으로 집합적으로 식별 됨)</span><span class="sxs-lookup"><span data-stu-id="3f9f2-116">The Exchange Online PowerShell cmdlets that support In-Place eDiscovery and In-Place Holds (these cmdlets are collectively identified as \**-MailboxSearch* cmdlets).</span></span> <span data-ttu-id="3f9f2-117">여기에는 다음 cmdlet이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-117">This includes the following cmdlets:</span></span>

  - [<span data-ttu-id="3f9f2-118">New-mailboxsearch</span><span class="sxs-lookup"><span data-stu-id="3f9f2-118">New-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-mailboxsearch)

  - [<span data-ttu-id="3f9f2-119">시작-New-mailboxsearch</span><span class="sxs-lookup"><span data-stu-id="3f9f2-119">Start-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-mailboxsearch)

  - [<span data-ttu-id="3f9f2-120">New-mailboxsearch</span><span class="sxs-lookup"><span data-stu-id="3f9f2-120">Stop-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/stop-mailboxsearch)

  - [<span data-ttu-id="3f9f2-121">New-mailboxsearch</span><span class="sxs-lookup"><span data-stu-id="3f9f2-121">Set-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-mailboxsearch)

   > [!NOTE]
   > <span data-ttu-id="3f9f2-122">[New-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-mailboxsearch) 및 [new-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/remove-mailboxsearch) cmdlet은 기타 \* \* \* \*-new-mailboxsearch \* \* \* cmdlet이 사용 중지 된 후에 사용할 수 있으므로 다른 eDiscovery 및 유지 도구로 전환할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-122">The [Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-mailboxsearch) and [Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/remove-mailboxsearch) cmdlets will be available after the other \*\*\*\*-MailboxSearch\*\*\* cmdlets are retired so that you can use them to help in your transition to other eDiscovery and hold tools.</span></span> <span data-ttu-id="3f9f2-123">그러나 아래에 언급 된 특정 날짜 이후에는 Microsoft 지원에서 이러한 두 cmdlet을 더 이상 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-123">However, after a certain date (cited below) Microsoft Support will no longer supports these two cmdlets.</span></span>

- <span data-ttu-id="3f9f2-124">Exchange Online PowerShell의 [검색 사서함](https://docs.microsoft.com/powershell/module/exchange/mailboxes/search-mailbox?view=exchange-ps) cmdlet</span><span class="sxs-lookup"><span data-stu-id="3f9f2-124">The [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/search-mailbox?view=exchange-ps) cmdlet in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="3f9f2-125">Exchange 웹 서비스 API에서 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-125">The following operations in the Exchange Web Services API:</span></span>

   - [<span data-ttu-id="3f9f2-126">GetSearchableMailboxes</span><span class="sxs-lookup"><span data-stu-id="3f9f2-126">GetSearchableMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [<span data-ttu-id="3f9f2-127">SearchMailboxes</span><span class="sxs-lookup"><span data-stu-id="3f9f2-127">SearchMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [<span data-ttu-id="3f9f2-128">SetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="3f9f2-128">SetHoldOnMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [<span data-ttu-id="3f9f2-129">GetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="3f9f2-129">GetHoldOnMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- <span data-ttu-id="3f9f2-130">Office [365 Advanced ediscovery v 1.0](office-365-advanced-ediscovery.md)-Office 365 보안 & 준수 센터의 핵심 ediscovery 사례를 통해 액세스 되는 고급 ediscovery의 첫 번째 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-130">[Office 365 Advanced eDiscovery v1.0](office-365-advanced-ediscovery.md), which is the first version of Advanced eDiscovery that's accessed through a Core eDiscovery case in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="3f9f2-131">Advanced eDiscovery v 1.0의 만료는 핵심 eDiscovery 사례를 만들고 관리 하는 기능에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-131">The retirement of Advanced eDiscovery v1.0 doesn't impact your ability to create and manage Core eDiscovery cases.</span></span>

> [!NOTE]
> <span data-ttu-id="3f9f2-132">폐기 중인 eDiscovery 기능은 클라우드 기반 버전의 Microsoft 365 및 Office 365에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-132">The eDiscovery functionality being retired only applies to cloud-based versions of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="3f9f2-133">온-프레미스 버전의 Exchange 및 SharePoint에서 eDiscovery 기능은 계속 해 서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-133">eDiscovery functionality in on-premises versions of Exchange and SharePoint will still be supported until further notice.</span></span>

<span data-ttu-id="3f9f2-134">이 문서의 다음 섹션에서는 폐기 되는 각 기능에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-134">The following sections in this article provide guidance about each feature being retired.</span></span> <span data-ttu-id="3f9f2-135">이 정보는 만료 된 도구 대신 사용할 수 있는 timeline 및 대체 도구를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-135">This information including timelines and alternative tools that you can use instead of the retired tool.</span></span>

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a><span data-ttu-id="3f9f2-136">Exchange 관리 센터의 원본 위치 eDiscovery 및 현재 위치 유지</span><span class="sxs-lookup"><span data-stu-id="3f9f2-136">In-Place eDiscovery and In-Place Holds in the Exchange admin center</span></span> 

<span data-ttu-id="3f9f2-137">원래 알림 2017 년 7 월 1 일에는 EAC (Exchange 관리 센터)의 원본 위치 eDiscovery & 보류 기능이 폐기 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-137">As per the original announcement on July 1, 2017, the In-Place eDiscovery & Hold functionality in the Exchange admin center (EAC) is being retired.</span></span> <span data-ttu-id="3f9f2-138">EAC의 원본 위치 eDiscovery & 보류 페이지를 사용 하 여 Exchange Online에서 콘텐츠를 검색 하 고, 유지 하 고, 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-138">The In-Place eDiscovery & Holds page in the EAC allowed you to search, hold, and export content from Exchange Online.</span></span> <span data-ttu-id="3f9f2-139">또한 원본 위치 eDiscovery를 사용 하면 검색 결과를 검색 사서함으로 복사 하 여 사용자 또는 다른 eDiscovery 관리자가 콘텐츠를 검토 하 고 법적, 규정 및 공개 요청에 사용할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-139">In-Place eDiscovery also let you copy search results to a discovery mailbox so that you or other eDiscovery managers could review content and make it available for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="3f9f2-140">이러한 모든 기능 (검색 결과를 검색 사서함으로 복사 하는 것을 제외)은 이제 [microsoft 365 준수 센터](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) 의 콘텐츠 검색, EDiscovery 및 고급 eDiscovery 도구 (microsoft 365 서비스에 대 한 향상 된 기능, 안정성 및 지원)에서 제공 되므로 가능한 한 빨리 이러한 도구를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-140">Because all of these capabilities (except for copying search results to a discovery mailbox) are now available in the content search, eDiscovery and Advanced eDiscovery tools in the [Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) (with improved functionality, reliability, and support for a wide range of Microsoft 365 services), we recommend that you start using these tools as soon as possible.</span></span> <span data-ttu-id="3f9f2-141">아래 표에는 이러한 다른 eDiscovery 도구로 전환할 때 사용할 수 있는 도구와 원본 위치 eDiscovery 및 원본 위치 유지를 사용 하지 않는 도구가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-141">To help you in the transition to these other eDiscovery tools, the table below lists the tools you can use instead of In-Place eDiscovery and In-Place Hold.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="3f9f2-142">영향을 받는 조직의 범위</span><span class="sxs-lookup"><span data-stu-id="3f9f2-142">Scope of affected organizations</span></span>

- <span data-ttu-id="3f9f2-143">Office 365 및 Microsoft 365 Enterprise 조직</span><span class="sxs-lookup"><span data-stu-id="3f9f2-143">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="3f9f2-144">Office 365 및 Microsoft 365 교육 기관</span><span class="sxs-lookup"><span data-stu-id="3f9f2-144">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="3f9f2-145">Office 365 및 Microsoft 365 정부 기관 여기에는 GCC, GCC High 및 DoD가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-145">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="3f9f2-146">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="3f9f2-146">Office 365 Germany</span></span>

### <a name="timeline-for-retirement"></a><span data-ttu-id="3f9f2-147">만료에 대 한 시간 표시 막대</span><span class="sxs-lookup"><span data-stu-id="3f9f2-147">Timeline for retirement</span></span>

- <span data-ttu-id="3f9f2-148">2020 년 7 월 1 일: 새 검색 및 보류를 만들 수는 없지만 기존 검색을 계속 실행 하 고 편집 하 고 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-148">July 1, 2020: You won't be able to create new searches and holds, but you can still run, edit, and delete existing searches at your own risk.</span></span> <span data-ttu-id="3f9f2-149">Microsoft Support는 EAC에서 더 이상 원본 위치 eDiscovery & 보존 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-149">Microsoft Support will no longer In-Place eDiscovery & Holds in the EAC.</span></span>

- <span data-ttu-id="3f9f2-150">2020: EAC의 원본 위치 eDiscovery & 보존 기능은 읽기 전용 모드에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-150">October 1, 2020: The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="3f9f2-151">즉, 기존 검색 및 보류만 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-151">This means you'll only be able to remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="3f9f2-152">대체 도구</span><span class="sxs-lookup"><span data-stu-id="3f9f2-152">Alternative tools</span></span>

<span data-ttu-id="3f9f2-153">다음 표에서는 폐기 중인 기존 기능을 대체 하는 데 사용할 수 있는 기타 도구에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-153">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="3f9f2-154"><strong>동작</strong></span><span class="sxs-lookup"><span data-stu-id="3f9f2-154"><strong>Functionality</strong></span></span></th>
<th><span data-ttu-id="3f9f2-155"><strong>대체 도구</strong></span><span class="sxs-lookup"><span data-stu-id="3f9f2-155"><strong>Alternative tool</strong></span></span></th>
<th><span data-ttu-id="3f9f2-156"><strong>Comments</strong></span><span class="sxs-lookup"><span data-stu-id="3f9f2-156"><strong>Comments</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="3f9f2-157">법적 목적을 위한 검색, 내보내기 및 보관</span><span class="sxs-lookup"><span data-stu-id="3f9f2-157">Search, export, and hold for legal purposes</span></span></td>
<td><span data-ttu-id="3f9f2-158">Microsoft 365 준수 센터의 핵심 eDiscovery 사례</span><span class="sxs-lookup"><span data-stu-id="3f9f2-158">Core eDiscovery cases in the Microsoft 365 compliance center</span></span> </td>
<td><p><span data-ttu-id="3f9f2-159">핵심 eDiscovery 사례의 기능을 사용 하면 원본 위치 eDiscovery 및 원본 위치 유지에 대 한 기능 패리티가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-159">Using the capabilities of core eDiscovery cases provide the functional parity to In-Place eDiscovery and In-Place Holds.</span></span> <span data-ttu-id="3f9f2-160">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-160">This includes the following:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="3f9f2-161">수백만 위치로 검색 확장</span><span class="sxs-lookup"><span data-stu-id="3f9f2-161">Search scales to millions of locations</span></span></p>
</li>
<li>
<p><span data-ttu-id="3f9f2-162">콘텐츠 검색, 내보내기 및 보류를 위한 더 높은 안정성</span><span class="sxs-lookup"><span data-stu-id="3f9f2-162">Higher reliability for searching, exporting, and placing content on hold</span></span></p>
</li>
<li>
<p><span data-ttu-id="3f9f2-163">Office 365 응용 프로그램에 저장 된 Exchange Online, SharePoint Online, 비즈니스용 OneDrive, 비즈니스용 Skype, Microsoft 팀, Yammer 그룹, Office 365 그룹 및 기타 콘텐츠에 대 한 콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="3f9f2-163">Searching for content in for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, Yammer Groups, Office 365 Groups, and other content stored in Office 365 applications</span></span></p></li></ul>
<p><span data-ttu-id="3f9f2-164">자세한 내용은 <a href="https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations">Office 365에서 법적 조사 관리</a>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-164">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations"> Manage legal investigations in Office 365</a>.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3f9f2-165">보존을 위해 보류</span><span class="sxs-lookup"><span data-stu-id="3f9f2-165">Hold for retention purposes</span></span></td>
<td><span data-ttu-id="3f9f2-166">Microsoft 365 준수 센터의 보존 정책</span><span class="sxs-lookup"><span data-stu-id="3f9f2-166">Retention policies in the Microsoft 365 compliance center</span></span></td>
<td><p><span data-ttu-id="3f9f2-167">보존 정책을 사용 하 여 콘텐츠를 보존 하 고 원할 경우 보존 기간이 만료 된 후에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-167">You can use Retention policies to retain content and, if desired, delete it after the retention period expires.</span></span> <span data-ttu-id="3f9f2-168">기타 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-168">Other capabilities include:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="3f9f2-169">전체 조직에 정책 적용</span><span class="sxs-lookup"><span data-stu-id="3f9f2-169">Applying policies to your entire organization</span></span> </p>
</li><li>
<p><span data-ttu-id="3f9f2-170">Exchange Online, SharePoint Online, 비즈니스용 OneDrive, 비즈니스용 Skype, Microsoft 팀 및 Office 365 그룹 등의 특정 콘텐츠 위치에 정책 적용</span><span class="sxs-lookup"><span data-stu-id="3f9f2-170">Applying policies to specific content locations such as Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, and Office 365 Groups</span></span></p></li>
<li>
<p><span data-ttu-id="3f9f2-171">특정 사용자에 게 정책 적용</span><span class="sxs-lookup"><span data-stu-id="3f9f2-171">Applying policies to specific users</span></span></p></li></ul>
<p><span data-ttu-id="3f9f2-172">자세한 내용은 <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies">보존 정책 개요</a>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-172">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies"> Overview of retention policies</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3f9f2-173">검토를 위해 전자 메일 검색 결과를 검색 사서함으로 복사</span><span class="sxs-lookup"><span data-stu-id="3f9f2-173">Copy email search results to a discovery mailbox for review</span></span></td><td><span data-ttu-id="3f9f2-174">Advanced eDiscovery v 2.0에서 집합 검토</span><span class="sxs-lookup"><span data-stu-id="3f9f2-174">Review sets in Advanced eDiscovery v2.0</span></span></td>
<td><p><span data-ttu-id="3f9f2-175">Microsoft 365의 콘텐츠를 검토 하는 것이 훨씬 쉬워졌습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-175">Reviewing content in Microsoft 365 has never been easier.</span></span> <span data-ttu-id="3f9f2-176">검토 집합에는 다음을 비롯 하 여 검토에 필요한 시간 및 데이터를 줄이는 데 도움이 되는 다양 한 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-176">Review sets have many great capabilities to help reduce the amount of time and data needed to review, including:</span></span></p>
<ul>
<li><p><span data-ttu-id="3f9f2-177">빠른 검색 쿼리를 수행 하 고 검토 집합의 콘텐츠 필터링</span><span class="sxs-lookup"><span data-stu-id="3f9f2-177">Perform fast search queries and filter content in a review set</span></span></p></li>
<li><p><span data-ttu-id="3f9f2-178">검토 집합의 콘텐츠를 분석 합니다. 여기에는 전자 메일 스레딩, 거의 중복 검색, 테마 분석 및 예측 코딩이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-178">Analyze content in a review set; this includes email threading, near-duplicate detection, Themes analysis, and Predictive coding</span></span></p></li>
<li><p><span data-ttu-id="3f9f2-179">검토 집합에서 문서 태그 지정</span><span class="sxs-lookup"><span data-stu-id="3f9f2-179">Tag documents in a review set</span></span></p></li>
<li><p><span data-ttu-id="3f9f2-180">변호사 클라이언트 권한 콘텐츠를 식별 하는 데 도움이 되는 태그 지정 제안</span><span class="sxs-lookup"><span data-stu-id="3f9f2-180">Tagging suggestions to help identify attorney  client privilege content</span></span></p></li></ul>
<p><span data-ttu-id="3f9f2-181">자세한 내용은 M<a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">icrosoft 365의 고급 eDiscovery 솔루션 개요</a>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-181">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Overview of the Advanced eDiscovery solution in Microsoft 365</a>.</span></span></p>
<p>
<p><span data-ttu-id="3f9f2-182">또는 검색 결과를 PST 파일로 내보낸 다음 Microsoft 365 가져오기 서비스를 사용 하 여 Pst를 검색 사서함으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-182">Alternatively, you can export search results to PST files and then use Microsoft 365 Import service to import the PSTs to a discovery mailbox.</span></span> <span data-ttu-id="3f9f2-183">단계별 지침은 <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">네트워크 업로드를 사용 하 여 PST 파일을 Office 365에 가져오기</a>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-183">For step-by-step instruction, see <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">Use network upload to import PST files to Office 365</a>.</span></span>
</tr>
<tr class=even>
  <td><span data-ttu-id="3f9f2-184">한 사서함에서 다른 사서함으로 메시지 복사</span><span class="sxs-lookup"><span data-stu-id="3f9f2-184">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="3f9f2-185"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">사서함에 사용 권한 할당</a></span><span class="sxs-lookup"><span data-stu-id="3f9f2-185"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="3f9f2-186">사용자에 게 다른 사용자의 전자 메일에 대 한 액세스 권한을 부여 하려면 (예: 직원이 조직을 떠나는 경우 다른 사용자에 게 이전 직원의 전자 메일에 액세스할 수 있는 경우) 해당 사용자에 게 이전 직원의 사서함에 대 한 액세스 권한을 할당 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-186">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="3f9f2-187">따라서 사서함 항목을 다른 사용자 사서함 또는 공유 사서함으로 복사 하는 대신 사용자에 게 원본 사서함에 액세스 하기 위한 권한을 할당 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-187">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
  
  </tr>
<tr class="odd">
<td><span data-ttu-id="3f9f2-188">복구 가능한 항목 폴더에서 항목 복원</span><span class="sxs-lookup"><span data-stu-id="3f9f2-188">Restore items from the Recoverable Items folder</span></span></td>
  <td><span data-ttu-id="3f9f2-189"><a href="https://docs.microsoft.com/powershell/module/exchange/mailboxes/Restore-RecoverableItems">복원-RecoverableItems</span><span class="sxs-lookup"><span data-stu-id="3f9f2-189"><a href="https://docs.microsoft.com/powershell/module/exchange/mailboxes/Restore-RecoverableItems">Restore-RecoverableItems</span></span></td>
  <td><span data-ttu-id="3f9f2-190">항목에 대해 삭제 된 항목 보존 기간이 만료 되지 않은 경우 사서함에서 영구적으로 삭제 된 항목 ( <i>일시 삭제</i> 된 항목으로도 알려짐)을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-190">You can restore permanently deleted items (also known as <i>soft-deleted</i> items) in mailboxes, as long as the deleted item retention period for an item hasn't expired.</span></span> <span data-ttu-id="3f9f2-191">자세한 내용은 <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Exchange Online의 복구 가능한 항목 폴더</a>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-191">For more information, see <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Recoverable Items folder in Exchange Online</a>.</span></span></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a><span data-ttu-id="3f9f2-192">원본 위치 eDiscovery 및 현재 위치 유지 관련 Faq</span><span class="sxs-lookup"><span data-stu-id="3f9f2-192">FAQs about In-Place eDiscovery and In-Place Holds</span></span>

<span data-ttu-id="3f9f2-193">**EAC의 원본 위치 eDiscovery & 보존 기능을 사용 하 여 변호사가 검토를 위해 검색 사서함에 검색할 검색 결과를 복사 합니다. 현재 어떤 옵션을 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="3f9f2-193">**I use the copy search results functionality of In-Place eDiscovery & Holds in the EAC to copy search results to a discovery mailbox for review by attorneys. What options do I have now?**</span></span>

<span data-ttu-id="3f9f2-194">이 기능은 오늘 두 가지 방법으로 복제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-194">There are two ways to replicate this functionality today.</span></span> <span data-ttu-id="3f9f2-195">첫 번째는 [Advanced eDiscovery v 2.0에서 검토 집합](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set)을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-195">The first is to use [review sets in Advanced eDiscovery v2.0](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set).</span></span> <span data-ttu-id="3f9f2-196">검토 집합에는 문서, 태그 지정, 전자 메일 스레딩, 중복 그룹화, 테마 분석 및 예측 코딩 같은 전통적인 검토 도구에 표시 되는 것과 동일한 기능이 많이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-196">Review sets have many of the same capabilities you see in a traditional review tool like fast search of documents, tagging, email threading, near duplicate grouping, themes analysis, and predictive coding.</span></span> <span data-ttu-id="3f9f2-197">검토를 위해 검색 사서함을 계속 사용 하려는 경우 두 번째 옵션은 검색 결과를 PST 파일로 내보낸 다음 Microsoft 준수 센터의 [pst 가져오기 기능](use-network-upload-to-import-pst-files.md) 을 사용 하 여 해당 pst 파일을 검색 사서함으로 가져오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-197">If you still want to use discovery mailboxes for review, the second option is to export search results to PST files and then import the PST files to a discovery mailbox by using the [PST import feature](use-network-upload-to-import-pst-files.md) in the Microsoft compliance center.</span></span>

<span data-ttu-id="3f9f2-198">**EDiscovery 관리자가 새 도구를 사용 하 여 검색할 수 있는 콘텐츠 위치 (예: 사서함 또는 사이트)를 제어 하려면 어떻게 해야 합니까?**</span><span class="sxs-lookup"><span data-stu-id="3f9f2-198">**How do I control which content locations (such as mailboxes or sites) that can an eDiscovery manager can search using the new tools?**</span></span>

<span data-ttu-id="3f9f2-199">Microsoft 365 준수 센터에서는 또한 [준수 경계](set-up-compliance-boundaries.md) 를 사용 하 여 eDiscovery 관리자가 검색할 수 있는 콘텐츠 위치를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-199">The Microsoft 365 compliance center also uses [compliance boundaries](set-up-compliance-boundaries.md) to control which content locations an eDiscovery Manager can search.</span></span> <span data-ttu-id="3f9f2-200">규정 준수 경계는 지리적 boarders을 준수 하기 위해 필요한 기관 경계 또는 국내 기업에 머물러 있어야 하는 정부 기관에서 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-200">Compliance boundaries are useful in government entities that need to stay within agency boundaries or multi-national corporations required to respect geographical boarders.</span></span>

<span data-ttu-id="3f9f2-201">**현재 검색 및 보류를 Microsoft 365 준수 센터로 어떻게 이동할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="3f9f2-201">**How can I move my current searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="3f9f2-202">PowerShell을 사용 하 여 원본 위치 eDiscovery 검색을 마이그레이션하고 EAC에서 보류 상태로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-202">It's possible to migrate In-Place eDiscovery searches and holds from the EAC by using PowerShell.</span></span> <span data-ttu-id="3f9f2-203">자세한 내용은 [EAC에서 검색 및 보류에서 Microsoft 365 준수 센터로 마이그레이션을](https://go.microsoft.com/fwlink/?linkid=2114224)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-203">For instructions, see [Migrate searches and holds from the EAC to the Microsoft 365 compliance center](https://go.microsoft.com/fwlink/?linkid=2114224).</span></span>

## <a name="-mailboxsearch-cmdlets"></a><span data-ttu-id="3f9f2-204">\*-New-mailboxsearch cmdlet</span><span class="sxs-lookup"><span data-stu-id="3f9f2-204">\*-MailboxSearch cmdlets</span></span>

<span data-ttu-id="3f9f2-205">Exchange 관리 센터에서 2017 년 7 월 1 일에 발표 된 원래 공지와 마찬가지로, 원본 위치 eDiscovery & 보류 기능 및 해당 \*\* \*\*\* 하는 new-mailboxsearch cmdlet을 사용 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-205">As per the original notice announced on July 1, 2017 in the Exchange admin center, the In-Place eDiscovery & Hold functionality and the corresponding **\*-MailboxSearch** cmdlets are being retired.</span></span> <span data-ttu-id="3f9f2-206">이러한 cmdlet은 사용자에 게 법적, 규정 및 공개 요청에 대 한 사서함 콘텐츠를 검색, 유지 및 내보낼 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-206">These cmdlets provide users the ability to search, hold, and export mailbox content for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="3f9f2-207">이제 이러한 기능을 [<span class="underline">Microsoft 365 준수 센터</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) 및 Office 365 Security & 준수 센터 PowerShell에서 향상 된 성능 및 확장성으로 사용할 수 있기 때문에 이러한 향상 된 cmdlet을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-207">Because these capabilities are now available in the [<span class="underline">Microsoft 365 compliance center</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) and Office 365 Security & Compliance Center PowerShell with improved performance and scalability, you should using these improved cmdlets.</span></span> <span data-ttu-id="3f9f2-208">이러한 cmdlet에는 [<span class="underline"> \*-remove-compliancecase</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase), [<span class="underline"> \*-ComplianceSearch</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch), [<span class="underline"> \*-new-caseholdpolicy</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy), [<span class="underline"> \*-new-caseholdrule</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule)및 [<span class="underline"> \*-new-compliancesearchaction</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction)가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-208">These cmdlets include [<span class="underline">\*-ComplianceCase</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase), [<span class="underline">\*-ComplianceSearch</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch), [<span class="underline">\*-CaseHoldPolicy</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy), [<span class="underline">\*-CaseHoldRule</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule), and [<span class="underline">\*-ComplianceSearchAction</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction).</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="3f9f2-209">영향을 받는 조직의 범위</span><span class="sxs-lookup"><span data-stu-id="3f9f2-209">Scope of affected organizations</span></span>

- <span data-ttu-id="3f9f2-210">Office 365 및 Microsoft 365 Enterprise 조직</span><span class="sxs-lookup"><span data-stu-id="3f9f2-210">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="3f9f2-211">Office 365 및 Microsoft 365 교육 기관</span><span class="sxs-lookup"><span data-stu-id="3f9f2-211">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="3f9f2-212">Office 365 및 Microsoft 365 정부 기관 여기에는 GCC, GCC High 및 DoD가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-212">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="3f9f2-213">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="3f9f2-213">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="3f9f2-214">타임라인</span><span class="sxs-lookup"><span data-stu-id="3f9f2-214">Timeline</span></span>

- <span data-ttu-id="3f9f2-215">7 월 1 일, 2020 **: 새 원본** 위치 eDiscovery 검색 및 원본 위치 유지를 만들 수는 없지만, cmdlet을 사용 하 여 기존 검색을 실행, 편집 및 삭제 하 고 사용자의 위험에도 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-215">July 1, 2020: You won't be able to use **New-MailboxSearch** to create new In-Place eDiscovery searches and In-Place Holds, but you can still use cmdlets to run, edit, and delete existing searches and holds at your own risk.</span></span> <span data-ttu-id="3f9f2-216">Microsoft Support는 이러한 유형의 검색 및 보존에 대 한 지원을 더 이상 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-216">Microsoft Support will no longer provide assistance for these types of searches and holds.</span></span>

- <span data-ttu-id="3f9f2-217">2020 년 10 월 1 일: 앞에서 설명한 것 처럼 EAC의 원본 위치 eDiscovery &는 읽기 전용 모드에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-217">October 1, 2020: As previously stated, The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="3f9f2-218">이는 또한 **new-mailboxsearch**, **new-mailboxsearch**또는 **new-mailboxsearch** cmdlet을 사용할 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-218">That also means that you won't be able to use the **New-MailboxSearch**, **Start-MailboxSearch**, or **Set-MailboxSearch** cmdlets.</span></span> <span data-ttu-id="3f9f2-219">기존 검색 및 보류만 가져오고 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-219">You'll only be able to get and remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="3f9f2-220">대체 도구</span><span class="sxs-lookup"><span data-stu-id="3f9f2-220">Alternative tools</span></span>

<span data-ttu-id="3f9f2-221">다음 표에서는 폐기 중인 기존 기능을 대체 하는 데 사용할 수 있는 기타 도구에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-221">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="3f9f2-222"><strong>동작</strong></span><span class="sxs-lookup"><span data-stu-id="3f9f2-222"><strong>Functionality</strong></span></span></th>
<th><span data-ttu-id="3f9f2-223"><strong>대체 도구</strong></span><span class="sxs-lookup"><span data-stu-id="3f9f2-223"><strong>Alternative tools</strong></span></span></th>
<th><span data-ttu-id="3f9f2-224"><strong>Comments</strong></span><span class="sxs-lookup"><span data-stu-id="3f9f2-224"><strong>Comments</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="3f9f2-225">검색 및 내보내기</span><span class="sxs-lookup"><span data-stu-id="3f9f2-225">Search and export</span></span></td>
<td><p><span data-ttu-id="3f9f2-226"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="3f9f2-226"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="3f9f2-227"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction"><span class="underline">\*-New-compliancesearchaction</span></a></span><span class="sxs-lookup"><span data-stu-id="3f9f2-227"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p><span data-ttu-id="3f9f2-228"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">\*-Remove-compliancecase</span></a></span><span class="sxs-lookup"><span data-stu-id="3f9f2-228"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="3f9f2-229">ComplianceSearch 및 New-compliancesearchaction cmdlet은 공동 작업을 통해 콘텐츠를 검색 하 고 내보내는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-229">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="3f9f2-230"><strong>새 검색</strong>을 만들고 <strong>ComplianceSearch</strong> <strong>cmdlet을 사용</strong>하 여 검색 예측을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-230">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="3f9f2-231">그런 다음 <strong>new-compliancesearchaction</strong> cmdlet을 사용 하 여 검색 결과를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-231">Then you can use the <strong>New-ComplianceSearchAction</strong> cmdlet to export the search results.</span></span> <span data-ttu-id="3f9f2-232">이러한 검색 결과를 로컬 컴퓨터에 다운로드 하려면 Microsoft 365 준수 센터에서 코어 eDiscovery 도구를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-232">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p>
<p>
<p><span data-ttu-id="3f9f2-233"><strong>참고:</strong> 이러한 cmdlet을 사용 하 여 코어 eDiscovery 사례와 관련 되지 않은 검색을 만드는 경우 이러한 검색은 Microsoft 365 준수 센터의 <strong>콘텐츠 검색</strong> 페이지에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-233"><strong>Note:</strong> If you use these cmdlets to create searches that aren't associated with a core eDiscovery case, these searches will be located on the <strong>Content search</strong> page in the Microsoft 365 compliance center.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3f9f2-234">사서함의 콘텐츠를 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-234">Hold content in a mailbox</span></span></td>
<td><p><span data-ttu-id="3f9f2-235"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy"><span class="underline">\*-New-caseholdpolicy</span></a></span><span class="sxs-lookup"><span data-stu-id="3f9f2-235"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span></span></p>
<p><span data-ttu-id="3f9f2-236"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule"><span class="underline">\*-New-caseholdrule</span></a></span><span class="sxs-lookup"><span data-stu-id="3f9f2-236"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule"><span class="underline">\*-CaseHoldRule</span></a></span></span></p>
<p><span data-ttu-id="3f9f2-237"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">\*-Remove-compliancecase</span></a></span><span class="sxs-lookup"><span data-stu-id="3f9f2-237"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="3f9f2-238">Microsoft 365 준수 센터의 보류는 Remove-compliancecase와 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-238">Holds in the Microsoft 365 compliance center must be associated with a ComplianceCase.</span></span> <span data-ttu-id="3f9f2-239">먼저 준수 사례를 만든 다음 New-caseholdpolicy 및 New-caseholdrule를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-239">First, create the compliance case, and then create a CaseHoldPolicy and a CaseHoldRule.</span></span></p>
<p><span data-ttu-id="3f9f2-240"><strong>참고:</strong> 만들기 New-caseholdrule 없이 New-caseholdpolicy를 만들면 New-caseholdrule가 만들어지고 New-caseholdpolicy에 연결 될 때까지 보류가 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-240"><strong>Note:</strong> Creating a CaseHoldPolicy without a creating CaseHoldRule will render the hold inoperable until the CaseHoldRule is created and associated to the CaseHoldPolicy.</span></span> <span data-ttu-id="3f9f2-241">자세한 내용은 cmdlet 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-241">See the cmdlet documentation for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3f9f2-242">검색 결과를 검색 사서함으로 복사</span><span class="sxs-lookup"><span data-stu-id="3f9f2-242">Copy search results to a discovery mailbox</span></span></td>
<td><span data-ttu-id="3f9f2-243">없음</span><span class="sxs-lookup"><span data-stu-id="3f9f2-243">None</span></span></td>
<td><span data-ttu-id="3f9f2-244">이 기능은 모든 Microsoft 365 서비스에 대 한 액세스를 제공 하지 않으므로 직접 대체할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-244">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="3f9f2-245">다른 해결 방법에 대 한 다음 FAQ를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-245">See the following FAQ below for alternative solutions.</span></span></td>
</tr>
  <tr class=even>
  <td><span data-ttu-id="3f9f2-246">한 사서함에서 다른 사서함으로 메시지 복사</span><span class="sxs-lookup"><span data-stu-id="3f9f2-246">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="3f9f2-247"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">사서함에 사용 권한 할당</a></span><span class="sxs-lookup"><span data-stu-id="3f9f2-247"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="3f9f2-248">사용자에 게 다른 사용자의 전자 메일에 대 한 액세스 권한을 부여 하려면 (예: 직원이 조직을 떠나는 경우 다른 사용자에 게 이전 직원의 전자 메일에 액세스할 수 있는 경우) 해당 사용자에 게 이전 직원의 사서함에 대 한 액세스 권한을 할당 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-248">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="3f9f2-249">따라서 사서함 항목을 다른 사용자 사서함 또는 공유 사서함으로 복사 하는 대신 사용자에 게 원본 사서함에 액세스 하기 위한 권한을 할당 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-249">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a><span data-ttu-id="3f9f2-250">Faq \***-new-mailboxsearch** cmdlet</span><span class="sxs-lookup"><span data-stu-id="3f9f2-250">FAQs about \***-MailboxSearch** cmdlets</span></span>

<span data-ttu-id="3f9f2-251">**복사 검색을 사용 하 여 다른 eDiscovery 및 법적 조사를 위해 전자 메일 메시지 또는 인스턴트 메시지를 내보냅니다. 이러한 cmdlet이 만료 된 후에는 어떤 다른 옵션을 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="3f9f2-251">**We use Copy Search to export email messages or instant Messages for purposes other eDiscovery and legal investigations. What other options do we have after these cmdlets are retired?**</span></span>

<span data-ttu-id="3f9f2-252">[<span class="underline">Microsoft Graph api</span>](https://developer.microsoft.com/en-us/graph) 는 분석을 위해 데이터를 추출 하는 여러 가지 방법과 \*\* \*new-mailboxsearch\*\* cmdlet 보다 탄력적이 고 확장성이 뛰어난 기타 목적을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-252">The [<span class="underline">Microsoft Graph APIs</span>](https://developer.microsoft.com/en-us/graph) provide a number of methods for extracting data for analysis and other purposes that are far more resilient and scalable than the using the **\*-MailboxSearch** cmdlets.</span></span>

<span data-ttu-id="3f9f2-253">**내 검색 및 보류를 Microsoft 365 준수 센터로 마이그레이션하려면 어떻게 해야 합니까?**</span><span class="sxs-lookup"><span data-stu-id="3f9f2-253">**How can I migrate my searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="3f9f2-254">PowerShell 스크립트를 사용 하 여 원본 위치 eDiscovery 검색 및 보류를 Exchange 관리 센터에서 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-254">It's possible to migrate In-Place eDiscovery searches and holds from the Exchange admin center by using a PowerShell script.</span></span> <span data-ttu-id="3f9f2-255">자세한 내용은 [마이그레이션 레거시 eDiscovery 검색 및 보류를 Microsoft 365 준수 센터로 마이그레이션을](migrate-legacy-eDiscovery-searches-and-holds.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-255">For more information, see [Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center](migrate-legacy-eDiscovery-searches-and-holds.md).</span></span>

<span data-ttu-id="3f9f2-256">**Cmdlet이 만료 된 후에도 검색을 계속 해 서 제거 하거나 검색할 수 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="3f9f2-256">**After the cmdlets are retired, will I still be able to remove or retrieve searches?**</span></span>

<span data-ttu-id="3f9f2-257">예, 검색을 만들고 수정 하는 기능을 제거 하는 경우에도 **new-mailboxsearch** 및 **new-mailboxsearch** 를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-257">Yes, although we're removing the ability to create and modify searches, you'll still be able to use **Get-MailboxSearch** and **Remove-MailboxSearch** until further notice.</span></span> <span data-ttu-id="3f9f2-258">그러나 만료 날짜가 되 고 Microsoft 지원에서 더 이상 지원을 제공할 수 없는 경우 이러한 cmdlet의 사용은 사용자의 책임을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-258">However, the use of these cmdlets will be at your own risk after the retirement dates and Microsoft Support will no longer be able to provide assistance.</span></span>

## <a name="search-mailbox-cmdlet"></a><span data-ttu-id="3f9f2-259">검색-사서함 cmdlet</span><span class="sxs-lookup"><span data-stu-id="3f9f2-259">Search-Mailbox cmdlet</span></span>

<span data-ttu-id="3f9f2-260">Exchange Online PowerShell의 **검색 사서함** cmdlet은 처음에 2018에서 시작 하는 cmdlet 출력에 경고를 발표 했을 때까지 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-260">The **Search-Mailbox** cmdlet in Exchange Online PowerShell is being retired as originally announced in a warning in the cmdlet output starting back in 2018.</span></span> <span data-ttu-id="3f9f2-261">**검색 사서함** cmdlet은 원래 사용자의 사서함을 검색 하 고 악성 콘텐츠를 제거 하는 데 사용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-261">The **Search-Mailbox** cmdlet was originally used to search a user's mailbox and purge malicious content.</span></span> <span data-ttu-id="3f9f2-262">Office 365 Security & 준수 센터 PowerShell에서 **ComplianceSearch** 및 **new-compliancesearchaction** cmdlet을 사용 하 여 콘텐츠를 검색 하 고 제거 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-262">We recommend that you start using the **New-ComplianceSearch** and **New-ComplianceSearchAction** cmdlets in Office 365 Security & Compliance Center PowerShell to search for and purge content.</span></span> <span data-ttu-id="3f9f2-263">기본 제공 되는 보안 환경에서 [<span class="underline">microsoft 365 보안 기능은</span>](https://docs.microsoft.com/microsoft-365/security/) 전자 메일 및 기타 다양 한 Microsoft 서비스에 대 한 강력한 위협 방지 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-263">For a built-in security experience, the [<span class="underline">Microsoft 365 security features</span>](https://docs.microsoft.com/microsoft-365/security/) provide robust threat protection for email and many other Microsoft services.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="3f9f2-264">영향을 받는 조직의 범위</span><span class="sxs-lookup"><span data-stu-id="3f9f2-264">Scope of affected organizations</span></span>

- <span data-ttu-id="3f9f2-265">Office 365 및 Microsoft 365 Enterprise 조직</span><span class="sxs-lookup"><span data-stu-id="3f9f2-265">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="3f9f2-266">Office 365 및 Microsoft 365 교육 기관</span><span class="sxs-lookup"><span data-stu-id="3f9f2-266">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="3f9f2-267">Office 365 및 Microsoft 365 정부 기관 여기에는 GCC, GCC High 및 DoD가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-267">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="3f9f2-268">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="3f9f2-268">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="3f9f2-269">타임라인</span><span class="sxs-lookup"><span data-stu-id="3f9f2-269">Timeline</span></span>

-  <span data-ttu-id="3f9f2-270">2020 년 7 월 1 일: **검색 사서함** cmdlet을 더 이상 사용할 수 없으며 Microsoft Support에서 더 이상 지원을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-270">July 1, 2020: The **Search-Mailbox** cmdlet will no longer be available and Microsoft Support will no longer provide assistance.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="3f9f2-271">대체 도구</span><span class="sxs-lookup"><span data-stu-id="3f9f2-271">Alternative tools</span></span>

<span data-ttu-id="3f9f2-272">다음 표에서는 폐기 중인 기존 기능을 대체 하는 데 사용할 수 있는 기타 도구에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-272">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="3f9f2-273"><strong>동작</strong></span><span class="sxs-lookup"><span data-stu-id="3f9f2-273"><strong>Functionality</strong></span></span></th>
<th><span data-ttu-id="3f9f2-274"><strong>대체 도구</strong></span><span class="sxs-lookup"><span data-stu-id="3f9f2-274"><strong>Alternative tools</strong></span></span></th>
<th><span data-ttu-id="3f9f2-275"><strong>Comments</strong></span><span class="sxs-lookup"><span data-stu-id="3f9f2-275"><strong>Comments</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="3f9f2-276">사서함 검색</span><span class="sxs-lookup"><span data-stu-id="3f9f2-276">Search a mailbox</span></span></td>
<td><p><span data-ttu-id="3f9f2-277"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="3f9f2-277"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="3f9f2-278"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">\*-New-compliancesearchaction</span></a></span><span class="sxs-lookup"><span data-stu-id="3f9f2-278"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></a></p></td>
<td><p><span data-ttu-id="3f9f2-279">ComplianceSearch 및 New-compliancesearchaction cmdlet은 공동 작업을 통해 콘텐츠를 검색 하 고 내보내는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-279">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="3f9f2-280"><strong>새 검색</strong>을 만들고 <strong>ComplianceSearch</strong> <strong>cmdlet을 사용</strong>하 여 검색 예측을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-280">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="3f9f2-281">그런 다음 <strong>new-compliancesearchaction-Export</strong> 명령을 사용 하 여 검색 결과를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-281">Then you can use the <strong>New-ComplianceSearchAction -Export</strong> command to export the search results.</span></span> <span data-ttu-id="3f9f2-282">이러한 검색 결과를 로컬 컴퓨터에 다운로드 하려면 Microsoft 365 준수 센터에서 코어 eDiscovery 도구를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-282">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="3f9f2-283">사서함에서 메시지 제거</span><span class="sxs-lookup"><span data-stu-id="3f9f2-283">Purge messages from a mailbox</span></span></td>
<td><p><span data-ttu-id="3f9f2-284"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="3f9f2-284"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="3f9f2-285"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">\*-New-compliancesearchaction</span></a></span><span class="sxs-lookup"><span data-stu-id="3f9f2-285"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="3f9f2-286">ComplianceSearch 및 New-compliancesearchaction cmdlet은 상호 작용 하 여 콘텐츠를 검색 하 고 제거 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-286">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and purge content.</span></span> <span data-ttu-id="3f9f2-287"><strong>ComplianceSearch</strong> 및 <strong>ComplianceSearch</strong> cmdlet을 사용 하 여 검색을 만들고 실행 한 후에는 <strong>new-compliancesearchaction-PurgeType</strong> 명령을 통해 콘텐츠를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-287">You can create and run a search with <strong>New-ComplianceSearch</strong> and <strong>New-ComplianceSearch</strong> cmdlets, and then you can purge the content by using <strong>New-ComplianceSearchAction -Purge -PurgeType</strong> command.</span></span> <span data-ttu-id="3f9f2-288">자세한 내용은 <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">메시지 검색 및 삭제</span></a>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-288">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Search for and delete messages</span></a>.</span></span></p>
</td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3f9f2-289">사서함에서 대량 전자 메일 삭제</span><span class="sxs-lookup"><span data-stu-id="3f9f2-289">Delete bulk email from a mailbox</span></span></td>
<td><p><span data-ttu-id="3f9f2-290"><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">사서함에 대한 보관 및 삭제 정책 설정</span></a></span><span class="sxs-lookup"><span data-stu-id="3f9f2-290"><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Set up an archive and deletion policy for mailboxes</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="3f9f2-291">관리자는 항목을 사용자의 보관 사서함으로 자동으로 이동 하 고 사서함에서 항목을 자동으로 삭제 하는 보관 및 삭제 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-291">Admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox.</span></span></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="3f9f2-292">검색 결과를 검색 사서함으로 복사</span><span class="sxs-lookup"><span data-stu-id="3f9f2-292">Copy search results to a discovery mailbox</span></span></td>
<td> </td>
<td><span data-ttu-id="3f9f2-293">이 기능은 모든 Microsoft 365 서비스에 대 한 액세스를 제공 하지 않으므로 직접 대체할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-293">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="3f9f2-294">대체 해결 방법은 <strong>\*-new-mailboxsearch cmdlet</strong> 섹션의 faq를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-294">See the FAQs in the <strong>\*-MailboxSearch cmdlets</strong> section for alternative solutions.</span></span> </td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a><span data-ttu-id="3f9f2-295">Exchange 웹 서비스 API 작업</span><span class="sxs-lookup"><span data-stu-id="3f9f2-295">Exchange Web Services API operations</span></span>

<span data-ttu-id="3f9f2-296">Exchange 웹 서비스 API에서 이러한 작업은 exchange 관리 센터의 원본 위치 eDiscovery & 보류 기능 및 exchange Online PowerShell의 해당 \*\* \*new-mailboxsearch\*\* cmdlet에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-296">These operations in the Exchange Web Services API are used by the In-Place eDiscovery & Holds feature in the Exchange admin center and the corresponding **\*-MailboxSearch** cmdlets in Exchange Online PowerShell.</span></span> <span data-ttu-id="3f9f2-297">다른 레거시 eDiscovery 도구를 중지 하는 경우에도 회수 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-297">They will also be retired as part of retiring the other legacy eDiscovery tools.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="3f9f2-298">영향을 받는 조직의 범위</span><span class="sxs-lookup"><span data-stu-id="3f9f2-298">Scope of affected organizations</span></span>

- <span data-ttu-id="3f9f2-299">Office 365 및 Microsoft 365 Enterprise 조직</span><span class="sxs-lookup"><span data-stu-id="3f9f2-299">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="3f9f2-300">Office 365 및 Microsoft 365 교육 기관</span><span class="sxs-lookup"><span data-stu-id="3f9f2-300">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="3f9f2-301">Office 365 및 Microsoft 365 정부 기관 여기에는 GCC, GCC High 및 DoD가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-301">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="3f9f2-302">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="3f9f2-302">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="3f9f2-303">타임라인</span><span class="sxs-lookup"><span data-stu-id="3f9f2-303">Timeline</span></span>

- <span data-ttu-id="3f9f2-304">2020 년 7 월 1 일: GetSearchableMailboxes, Search우편함, SetHoldOnMailboxes 및 GetHoldOnMailboxes 작업을 더 이상 사용할 수 없으며 Microsoft Support에서 더 이상 지원을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-304">July 1, 2020: The GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes, and GetHoldOnMailboxes operations will no longer be available, and Microsoft Support will no longer provide assistance.</span></span>

## <a name="advanced-ediscovery-v10"></a><span data-ttu-id="3f9f2-305">Advanced eDiscovery v 1.0</span><span class="sxs-lookup"><span data-stu-id="3f9f2-305">Advanced eDiscovery v1.0</span></span>

<span data-ttu-id="3f9f2-306">Advanced ediscovery **로 전환을**클릭 하 여 코어 ediscovery 사례에서 사용할 수 있는 advanced ediscovery 버전의 advanced ediscovery v 1.0이 만료 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-306">Advanced eDiscovery v1.0, which is the version of Advanced eDiscovery available in a core eDiscovery case by clicking **Switch to Advanced eDiscovery**, is being retired.</span></span> <span data-ttu-id="3f9f2-307">해당 기능은 Microsoft 365 준수 센터의 새로운 [고급 eDiscovery 솔루션](https://aka.ms/edisco) 으로 대체 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-307">Its functionality has been replaced by the new [Advanced eDiscovery solution](https://aka.ms/edisco) in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="3f9f2-308">조직에서 Advanced eDiscovery v 1.0을 사용 하 고 있는지 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="3f9f2-308">To determine if your organization is using Advanced eDiscovery v1.0:</span></span>

1. <span data-ttu-id="3f9f2-309">[Office 365 Security & 준수 센터로](https://protection.office.com)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-309">Go to the [Office 365 Security & Compliance Center](https://protection.office.com).</span></span>

2. <span data-ttu-id="3f9f2-310">보안 & 준수 센터의 왼쪽 탐색 창에서 **ediscovery > ediscovery**를 클릭 하 고 코어 eDiscovery 사례를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-310">In the left navigation pane of the Security & Compliance Center, click **eDiscovery > eDiscovery**, and open a Core eDiscovery case.</span></span>

3. <span data-ttu-id="3f9f2-311">**고급 ediscovery로 전환** 단추가 표시 되 면이 단추를 클릭 하면 사용 중지 되 고 있는 1.0 버전의 고급 ediscovery로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-311">If you see the **Switch to Advanced eDiscovery** button, then clicking it will take you to the 1.0 version of Advanced eDiscovery, which is being retired.</span></span> <span data-ttu-id="3f9f2-312">핵심 eDiscovery에서 사례를 만들고 관리 하는 기능은 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-312">The ability to create and manage cases in Core eDiscovery won't be affected.</span></span> <span data-ttu-id="3f9f2-313">Advanced eDiscovery v 1.0에서 사례 데이터를 추가 및 분석 하는 기능 ( **Advanced ediscovery로 전환을**클릭 하는 것)은 폐기 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-313">Only the ability to add and analyze case data in Advanced eDiscovery v1.0 (by clicking **Switch to Advanced eDiscovery**) is being retired.</span></span>

<span data-ttu-id="3f9f2-314">Microsoft 365 ( *Advanced eDiscovery v 2.0*이 라고도 함)의 새로운 고급 ediscovery 솔루션은 원래 솔루션의 모든 기능을 제공 하지만, 해당 콘텐츠를 수집한 다음 custodian가 fast search 쿼리, 태그 지정 및 분석 기능을 활용 하 여 관련 문서를 cull 수 있도록 하는 검토 집합에 추가 하는 365 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-314">The new Advanced eDiscovery solution in Microsoft 365 (also known as *Advanced eDiscovery v2.0*) provides all of the capabilities of the original solution, but now includes a custodian-based approach of identifying content in other Microsoft 365 services, collecting that content, and then adding it to a review set where reviewers can take advantage of fast search queries, tagging, and analytics features to help cull relevant documents.</span></span> <span data-ttu-id="3f9f2-315">이제 고급 eDiscovery에는 Microsoft 및 Microsoft 이외의 파일 형식에 대 한 향상 된 처리 및 기본 뷰어가 포함 되어 있으므로 전체 파일 형식 목록과 지원 [되는 메타](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery)데이터 [필드가 여기에](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-315">Advanced eDiscovery now includes improved processing and native viewers for both Microsoft and non-Microsoft file types, a full list of file types is [here](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) and supported metadata fields are [here](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery).</span></span> <span data-ttu-id="3f9f2-316">또한 새로운 고급 eDiscovery 솔루션은 다른 서비스의 콘텐츠에 보류를 적용 하 고, 보류를 사용자에 게 알리고, custodian 응답을 고급 eDiscovery 사례 내에서 추적할 수 있도록 하는 강력한 custodian 유지 관리 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-316">Also, the new Advanced eDiscovery solution provides a powerful custodian holds management feature that lets you apply holds to content in different services, notify users of the holds, and track custodian responses, all within an Advanced eDiscovery case.</span></span>

<span data-ttu-id="3f9f2-317">Advanced eDiscovery v 2.0에 액세스 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-317">To access Advanced eDiscovery v2.0:</span></span>

1. <span data-ttu-id="3f9f2-318">[Microsoft 365 준수 센터로](https://compliance.microsoft.com)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-318">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="3f9f2-319">Microsoft 365 준수 센터의 왼쪽 탐색 창에서 **모두 표시**를 클릭 한 다음 **eDiscovery > 고급**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-319">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Advanced**.</span></span>

<span data-ttu-id="3f9f2-320">지금은 eDiscovery 워크플로를 새 고급 eDiscovery 기능으로 전환 하기 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-320">At this time, we recommend that you begin to transition your eDiscovery workflow to the new Advanced eDiscovery functionality.</span></span> <span data-ttu-id="3f9f2-321">기존 사례에서는 여전히 고급 eDiscovery v 1.0에 액세스할 수 있지만 Microsoft Support는 2020 년 10 월 1 일 이후에는 지원을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-321">Although you'll still be able to access Advanced eDiscovery v1.0 in existing cases, Microsoft Support won't provide support after October 1, 2020.</span></span> <span data-ttu-id="3f9f2-322">자세한 내용은 다음 시간 표시 막대를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-322">See the following timeline for more details.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="3f9f2-323">영향을 받는 조직의 범위</span><span class="sxs-lookup"><span data-stu-id="3f9f2-323">Scope of affected organizations</span></span>

- <span data-ttu-id="3f9f2-324">Office 365 및 Microsoft 365 Enterprise 조직</span><span class="sxs-lookup"><span data-stu-id="3f9f2-324">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="3f9f2-325">Office 365 및 Microsoft 365 교육 기관</span><span class="sxs-lookup"><span data-stu-id="3f9f2-325">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="3f9f2-326">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="3f9f2-326">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="3f9f2-327">타임라인</span><span class="sxs-lookup"><span data-stu-id="3f9f2-327">Timeline</span></span>

- <span data-ttu-id="3f9f2-328">2020 년 7 월 1 일: 새 고급 eDiscovery v 1.0 사례를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-328">July 1, 2020: You won't be able to create new Advanced eDiscovery v1.0  cases.</span></span>

- <span data-ttu-id="3f9f2-329">2020 년 10 월 1 일: 모든 경우에 새 데이터 (고급 eDiscovery에 대 한 검색 결과 준비)를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-329">October 1, 2020: You won't be able to add new data (Prepare search results for Advanced eDiscovery) to any cases.</span></span> <span data-ttu-id="3f9f2-330">기존 사례에서 데이터 작업을 계속 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-330">You'll be able to continue working with data in existing cases at your own risk.</span></span> <span data-ttu-id="3f9f2-331">Microsoft Support에서는 더 이상 지원을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-331">Microsoft Support will no longer provide assistance.</span></span> 

### <a name="alternative-tools"></a><span data-ttu-id="3f9f2-332">대체 도구</span><span class="sxs-lookup"><span data-stu-id="3f9f2-332">Alternative tools</span></span>

<span data-ttu-id="3f9f2-333">Microsoft 365 준수 센터의 [고급 eDiscovery 솔루션](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) 입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f2-333">The [Advanced eDiscovery solution](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) in the Microsoft 365 compliance center.</span></span>
