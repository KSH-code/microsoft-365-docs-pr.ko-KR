---
title: 콘텐츠 검색을 사용하여 타사에서 가져온 데이터 검색
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: 콘텐츠 검색 eDiscovery 도구를 사용하여 쿼리를 만들어 타사 데이터 원본에서 Microsoft 365의 사서함으로 가져온 항목을 검색합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 24ca63cf78b85f7b8b5181d5babd16058b641128
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324574"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a><span data-ttu-id="1bd9a-103">콘텐츠 검색을 사용하여 사용자 지정 파트너 커넥터에서 가져온 타사 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="1bd9a-103">Use Content Search to search third-party data imported by a custom partner connector</span></span>

<span data-ttu-id="1bd9a-104">보안 및 준수 센터의 콘텐츠 검색 [eDiscovery](content-search.md) 도구를 & 타사 데이터 원본에서 Microsoft 365의 사서함으로 가져온 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd9a-104">You can use the [Content Search eDiscovery tool](content-search.md) in the Security & Compliance Center to search for items imported to mailboxes in Microsoft 365 from a third-party data source.</span></span> <span data-ttu-id="1bd9a-105">가져온 모든 타사 데이터 항목을 검색하는 쿼리를 만들거나 쿼리를 만들어 특정 타사 데이터 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd9a-105">You can create a query to search all imported third-party data items or you can create a query to search specific third-party data items.</span></span> <span data-ttu-id="1bd9a-106">또한 쿼리 기반 보존 정책 또는 쿼리 기반 eDiscovery 보류를 만들어 타사 데이터를 보존할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd9a-106">Also, you can also create a query-based retention policy or a query-based eDiscovery hold to preserve third-party data.</span></span>
  
<span data-ttu-id="1bd9a-107">파트너와 협력하여 타사 데이터를 가져오고 Microsoft 365로 가져올 수 있는 타사 데이터 형식 목록은 Office [365에서](work-with-partner-to-archive-third-party-data.md)타사 데이터를 보관하는 파트너와 협력을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bd9a-107">For more information about working with a partner to import third-party data and a list of the third-party data types that you can import to Microsoft 365, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1bd9a-108">이 문서의 지침은 사용자 지정 파트너 커넥터에서 가져온 타사 데이터에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bd9a-108">The guidance in this article only applies to third-party data that was imported by a custom partner connector.</span></span> <span data-ttu-id="1bd9a-109">이 문서는 Microsoft 규정 준수 센터에서 타사 데이터 [](archiving-third-party-data.md#third-party-data-connectors) 커넥터를 사용하여 가져온 타사 데이터에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd9a-109">This article doesn't apply to third-party data that is imported by using the [third-party data connectors](archiving-third-party-data.md#third-party-data-connectors) in the Microsoft compliance center.</span></span>
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="1bd9a-110">모든 타사 데이터를 검색하는 쿼리 만들기</span><span class="sxs-lookup"><span data-stu-id="1bd9a-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="1bd9a-111">Office 365로 가져온 모든 유형의 타사 데이터를 검색하거나 보류하기 위해 콘텐츠 검색 또는 쿼리 기반 보류를 만들 때 키워드 상자에 메시지 속성 값 쌍을 사용할 수  `kind:externaldata` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd9a-111">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold.</span></span> <span data-ttu-id="1bd9a-112">예를 들어 타사 데이터 원본에서 가져온 항목을 검색하고 가져온 항목의 Subject 속성에 "contoso"라는 단어를 포함하기 위해 다음 쿼리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1bd9a-112">For example, to search for items imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```powershell
kind:externaldata AND subject:contoso
```

<span data-ttu-id="1bd9a-113">이전 키워드 쿼리 예제에는 제목 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd9a-113">The previous keyword query example includes the subject property.</span></span> <span data-ttu-id="1bd9a-114">키워드 쿼리에 포함할 수 있는 타사 데이터 항목에 대한 다른 속성 목록은 Office [365에서](work-with-partner-to-archive-third-party-data.md#more-information)타사 데이터를 보관하는 파트너와의 작업에서 "추가 정보" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bd9a-114">For a list of other properties for third-party data items that can include in a keyword query, see the "More information" section in [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="1bd9a-115">타사 데이터를 검색하고 보유하는 쿼리를 만들 때 조건을 사용하여 검색 결과 범위를 좁힐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd9a-115">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results.</span></span> <span data-ttu-id="1bd9a-116">콘텐츠 검색 쿼리를 만드는 데 대한 자세한 내용은 콘텐츠 검색에 대한 키워드 쿼리 및 [검색 조건을 참조하세요.](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="1bd9a-116">For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="1bd9a-117">특정 유형의 타사 데이터를 검색하는 쿼리 만들기</span><span class="sxs-lookup"><span data-stu-id="1bd9a-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="1bd9a-118">모든 형식의 타사 데이터를 검색하는 대신 콘텐츠 검색에 대한 키워드 상자의 값 쌍을 사용하여 특정  형식의 타사 데이터만 검색하는 쿼리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd9a-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message *property: value* pair in the keyword box for a Content Search:</span></span>
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="1bd9a-119">예를 들어 Subject 속성에 "contoso"라는 단어가 포함된 Facebook 데이터를 검색하기 위해 다음 쿼리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1bd9a-119">For example, to search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="1bd9a-120">다음 표에는 검색할 수 있는 타사 데이터 형식과 메시지 속성에서 해당 형식의 타사 데이터를 구체적으로 검색하는 데 사용할  `itemclass:` 값이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bd9a-120">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data.</span></span> <span data-ttu-id="1bd9a-121">쿼리 구문은 대소문자 구분이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd9a-121">The query syntax isn't case-sensitive.</span></span> 
  
|<span data-ttu-id="1bd9a-122">**타사 데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="1bd9a-122">**Third-party data type**</span></span>|<span data-ttu-id="1bd9a-123">**속성  `itemclass:` 값**</span><span class="sxs-lookup"><span data-stu-id="1bd9a-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1bd9a-124">AIM</span><span class="sxs-lookup"><span data-stu-id="1bd9a-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="1bd9a-125">American Idol</span><span class="sxs-lookup"><span data-stu-id="1bd9a-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="1bd9a-126">AOL with Pivot Client </span><span class="sxs-lookup"><span data-stu-id="1bd9a-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="1bd9a-127">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="1bd9a-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="1bd9a-128">Ares</span><span class="sxs-lookup"><span data-stu-id="1bd9a-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="1bd9a-129">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="1bd9a-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="1bd9a-130">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="1bd9a-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="1bd9a-131">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="1bd9a-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="1bd9a-132">Axs Placeholder</span><span class="sxs-lookup"><span data-stu-id="1bd9a-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="1bd9a-133">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="1bd9a-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="1bd9a-134">바자르보ice</span><span class="sxs-lookup"><span data-stu-id="1bd9a-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="1bd9a-135">Bearshare</span><span class="sxs-lookup"><span data-stu-id="1bd9a-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="1bd9a-136">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="1bd9a-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="1bd9a-137">Blackberry</span><span class="sxs-lookup"><span data-stu-id="1bd9a-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="1bd9a-138">BlackBerry 통화 로그</span><span class="sxs-lookup"><span data-stu-id="1bd9a-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="1bd9a-139">BlackBerry Messenger</span><span class="sxs-lookup"><span data-stu-id="1bd9a-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="1bd9a-140">BlackBerry PIN</span><span class="sxs-lookup"><span data-stu-id="1bd9a-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="1bd9a-141">BlackBerry SMS</span><span class="sxs-lookup"><span data-stu-id="1bd9a-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="1bd9a-142">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="1bd9a-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="1bd9a-143">블룸버그 메시지</span><span class="sxs-lookup"><span data-stu-id="1bd9a-143">Bloomberg Message</span></span>  <br/> | `ipm.externaldata.conversation.Bloomberg Message*` <br/> |
|<span data-ttu-id="1bd9a-144">Bloomberg Messaging</span><span class="sxs-lookup"><span data-stu-id="1bd9a-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="1bd9a-145">Box</span><span class="sxs-lookup"><span data-stu-id="1bd9a-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="1bd9a-146">Cisco IM &amp; Presence Server</span><span class="sxs-lookup"><span data-stu-id="1bd9a-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="1bd9a-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="1bd9a-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="1bd9a-148">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="1bd9a-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="1bd9a-149">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="1bd9a-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="1bd9a-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="1bd9a-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="1bd9a-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="1bd9a-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="1bd9a-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="1bd9a-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="1bd9a-153">Flickr</span><span class="sxs-lookup"><span data-stu-id="1bd9a-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="1bd9a-154">Gnutella</span><span class="sxs-lookup"><span data-stu-id="1bd9a-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="1bd9a-155">Google+</span><span class="sxs-lookup"><span data-stu-id="1bd9a-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="1bd9a-156">Google Talk</span><span class="sxs-lookup"><span data-stu-id="1bd9a-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="1bd9a-157">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="1bd9a-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="1bd9a-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="1bd9a-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="1bd9a-159">홉스터</span><span class="sxs-lookup"><span data-stu-id="1bd9a-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="1bd9a-160">HubConnex</span><span class="sxs-lookup"><span data-stu-id="1bd9a-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="1bd9a-161">IBM Connections</span><span class="sxs-lookup"><span data-stu-id="1bd9a-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="1bd9a-162">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="1bd9a-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="1bd9a-163">ICE 채팅</span><span class="sxs-lookup"><span data-stu-id="1bd9a-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.conversation.Ice Chat*` <br/> |
|<span data-ttu-id="1bd9a-164">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="1bd9a-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="1bd9a-165">인자</span><span class="sxs-lookup"><span data-stu-id="1bd9a-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="1bd9a-166">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="1bd9a-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="1bd9a-167">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="1bd9a-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="1bd9a-168">IRC</span><span class="sxs-lookup"><span data-stu-id="1bd9a-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="1bd9a-169">Jive</span><span class="sxs-lookup"><span data-stu-id="1bd9a-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="1bd9a-170">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="1bd9a-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="1bd9a-171">JXTA</span><span class="sxs-lookup"><span data-stu-id="1bd9a-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="1bd9a-172">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="1bd9a-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="1bd9a-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="1bd9a-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="1bd9a-174">Microsoft UC</span><span class="sxs-lookup"><span data-stu-id="1bd9a-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="1bd9a-175">마음 맞춤</span><span class="sxs-lookup"><span data-stu-id="1bd9a-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="1bd9a-176">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="1bd9a-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="1bd9a-177">MSN</span><span class="sxs-lookup"><span data-stu-id="1bd9a-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="1bd9a-178">MySpace</span><span class="sxs-lookup"><span data-stu-id="1bd9a-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="1bd9a-179">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="1bd9a-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="1bd9a-180">OpenNap</span><span class="sxs-lookup"><span data-stu-id="1bd9a-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="1bd9a-181">Pinterest</span><span class="sxs-lookup"><span data-stu-id="1bd9a-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="1bd9a-182">Pivot</span><span class="sxs-lookup"><span data-stu-id="1bd9a-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="1bd9a-183">QQ</span><span class="sxs-lookup"><span data-stu-id="1bd9a-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="1bd9a-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="1bd9a-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="1bd9a-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="1bd9a-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="1bd9a-186">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="1bd9a-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="1bd9a-187">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="1bd9a-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="1bd9a-188">SoftEther</span><span class="sxs-lookup"><span data-stu-id="1bd9a-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="1bd9a-189">스쿼커</span><span class="sxs-lookup"><span data-stu-id="1bd9a-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="1bd9a-190">Symphony</span><span class="sxs-lookup"><span data-stu-id="1bd9a-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="1bd9a-191">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="1bd9a-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="1bd9a-192">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="1bd9a-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="1bd9a-193">Tor</span><span class="sxs-lookup"><span data-stu-id="1bd9a-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="1bd9a-194">TTT</span><span class="sxs-lookup"><span data-stu-id="1bd9a-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="1bd9a-195">Twitter</span><span class="sxs-lookup"><span data-stu-id="1bd9a-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="1bd9a-196">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="1bd9a-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="1bd9a-197">Vimeo</span><span class="sxs-lookup"><span data-stu-id="1bd9a-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="1bd9a-198">WinMX</span><span class="sxs-lookup"><span data-stu-id="1bd9a-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="1bd9a-199">Winny</span><span class="sxs-lookup"><span data-stu-id="1bd9a-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="1bd9a-200">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1bd9a-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="1bd9a-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="1bd9a-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="1bd9a-202">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="1bd9a-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="1bd9a-203">YouTube</span><span class="sxs-lookup"><span data-stu-id="1bd9a-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
