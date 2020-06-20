---
title: 콘텐츠 검색을 사용 하 여 타사 가져온 데이터 검색
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
description: 콘텐츠 검색 eDiscovery 도구를 사용 하면 쿼리를 만들어 타사 데이터 원본에서 Microsoft 365의 사서함으로 가져온 항목을 검색할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 916a780bccc3f24d509991e8ac72f31b374757d4
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819098"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a><span data-ttu-id="70c6e-103">콘텐츠 검색을 사용 하 여 사용자 지정 파트너 커넥터로 가져온 타사 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="70c6e-103">Use Content Search to search third-party data imported by a custom partner connector</span></span>

<span data-ttu-id="70c6e-104">보안 & 준수 센터에서 [콘텐츠 검색 eDiscovery 도구](content-search.md) 를 사용 하 여 타사 데이터 원본에서 Microsoft 365의 사서함으로 가져온 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c6e-104">You can use the [Content Search eDiscovery tool](content-search.md) in the Security & Compliance Center to search for items imported to mailboxes in Microsoft 365 from a third-party data source.</span></span> <span data-ttu-id="70c6e-105">가져온 모든 타사 데이터 항목을 검색 하는 쿼리를 만들 수도 있고, 특정 타사 데이터 항목을 검색 하는 쿼리를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c6e-105">You can create a query to search all imported third-party data items or you can create a query to search specific third-party data items.</span></span> <span data-ttu-id="70c6e-106">또한 타사 데이터를 보존 하기 위해 쿼리 기반 보존 정책 또는 쿼리 기반 eDiscovery 유지를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c6e-106">Also, you can also create a query-based retention policy or a query-based eDiscovery hold to preserve third-party data.</span></span>
  
<span data-ttu-id="70c6e-107">타사 데이터를 가져오는 파트너와 Microsoft 365로 가져올 수 있는 타사 데이터 형식 목록을 사용 하는 방법에 대 한 자세한 내용은 [Office 365에서 파트너와 협력 하](work-with-partner-to-archive-third-party-data.md)여 타사 데이터 보관을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="70c6e-107">For more information about working with a partner to import third-party data and a list of the third-party data types that you can import to Microsoft 365, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70c6e-108">이 문서의 지침은 사용자 지정 파트너 커넥터로 가져온 타사 데이터에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70c6e-108">The guidance in this article only applies to third-party data that was imported by a custom partner connector.</span></span> <span data-ttu-id="70c6e-109">이 문서는 Microsoft 준수 센터에서 타사 [데이터 커넥터](archiving-third-party-data.md#third-party-data-connectors) 를 사용 하 여 가져온 타사 데이터에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70c6e-109">This article doesn't apply to third-party data that is imported by using the [third-party data connectors](archiving-third-party-data.md#third-party-data-connectors) in the Microsoft compliance center.</span></span>
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="70c6e-110">모든 타사 데이터를 검색 하기 위한 쿼리 만들기</span><span class="sxs-lookup"><span data-stu-id="70c6e-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="70c6e-111">Office 365로 가져온 모든 타사 데이터 형식을 검색 하거나 보류 하려면 `kind:externaldata` 콘텐츠 검색의 키워드 상자에 메시지 속성-값 쌍을 사용 하거나 쿼리 기반 보존을 만들 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c6e-111">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold.</span></span> <span data-ttu-id="70c6e-112">예를 들어 모든 타사 데이터 원본에서 가져온 항목을 검색 하 고 가져온 항목의 Subject 속성에 "contoso" 라는 단어를 포함 하려면 다음 쿼리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c6e-112">For example, to search for items imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```powershell
kind:externaldata AND subject:contoso
```

<span data-ttu-id="70c6e-113">이전 keyword 쿼리 예제에는 subject 속성이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c6e-113">The previous keyword query example includes the subject property.</span></span> <span data-ttu-id="70c6e-114">키워드 쿼리에 포함할 수 있는 타사 데이터 항목의 기타 속성 목록은 [Office 365에서 타사 데이터를 보관 하기 위한 파트너와 작업](work-with-partner-to-archive-third-party-data.md#more-information)의 "추가 정보" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="70c6e-114">For a list of other properties for third-party data items that can include in a keyword query, see the "More information" section in [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="70c6e-115">타사 데이터를 검색 하 고 유지 하기 위한 쿼리를 만들 때 조건을 사용 하 여 검색 결과의 범위를 좁힐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c6e-115">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results.</span></span> <span data-ttu-id="70c6e-116">콘텐츠 검색 쿼리를 만드는 방법에 대 한 자세한 내용은 [키워드 쿼리 및 검색 조건을](keyword-queries-and-search-conditions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="70c6e-116">For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="70c6e-117">특정 유형의 타사 데이터를 검색 하기 위한 쿼리 만들기</span><span class="sxs-lookup"><span data-stu-id="70c6e-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="70c6e-118">모든 유형의 타사 데이터를 검색 하는 대신 콘텐츠 검색의 키워드 상자에 있는 다음 메시지 *속성* 을 사용 하 여 타사 데이터의 지정만 검색 하는 쿼리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c6e-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message *property:value* pair in the keyword box for a Content Search:</span></span>
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="70c6e-119">예를 들어 Subject 속성에서 "contoso" 라는 단어가 포함 된 Facebook 데이터를 검색 하려면 다음 쿼리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c6e-119">For example, to search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="70c6e-120">다음 표에서는 검색할 수 있는 타사 데이터 형식 및 `itemclass:` 해당 유형의 타사 데이터를 특별히 검색 하기 위해 message 속성에 사용할 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="70c6e-120">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data.</span></span> <span data-ttu-id="70c6e-121">쿼리 구문은 대/소문자를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70c6e-121">The query syntax isn't case-sensitive.</span></span> 
  
|<span data-ttu-id="70c6e-122">**타사 데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="70c6e-122">**Third-party data type**</span></span>|<span data-ttu-id="70c6e-123">**속성 값 `itemclass:`**</span><span class="sxs-lookup"><span data-stu-id="70c6e-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="70c6e-124">AIM</span><span class="sxs-lookup"><span data-stu-id="70c6e-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="70c6e-125">American Idol</span><span class="sxs-lookup"><span data-stu-id="70c6e-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="70c6e-126">AOL with Pivot Client </span><span class="sxs-lookup"><span data-stu-id="70c6e-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="70c6e-127">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="70c6e-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="70c6e-128">Ares</span><span class="sxs-lookup"><span data-stu-id="70c6e-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="70c6e-129">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="70c6e-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="70c6e-130">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="70c6e-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="70c6e-131">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="70c6e-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="70c6e-132">Axs 자리 표시자</span><span class="sxs-lookup"><span data-stu-id="70c6e-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="70c6e-133">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="70c6e-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="70c6e-134">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="70c6e-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="70c6e-135">Bearshare</span><span class="sxs-lookup"><span data-stu-id="70c6e-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="70c6e-136">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="70c6e-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="70c6e-137">Blackberry</span><span class="sxs-lookup"><span data-stu-id="70c6e-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="70c6e-138">BlackBerry 통화 로그</span><span class="sxs-lookup"><span data-stu-id="70c6e-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="70c6e-139">BlackBerry Messenger</span><span class="sxs-lookup"><span data-stu-id="70c6e-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="70c6e-140">BlackBerry PIN</span><span class="sxs-lookup"><span data-stu-id="70c6e-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="70c6e-141">BlackBerry SMS</span><span class="sxs-lookup"><span data-stu-id="70c6e-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="70c6e-142">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="70c6e-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="70c6e-143">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="70c6e-143">Bloomberg Mail</span></span>  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|<span data-ttu-id="70c6e-144">Bloomberg 메시징</span><span class="sxs-lookup"><span data-stu-id="70c6e-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="70c6e-145">Box</span><span class="sxs-lookup"><span data-stu-id="70c6e-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="70c6e-146">Cisco IM &amp; 현재 상태 서버</span><span class="sxs-lookup"><span data-stu-id="70c6e-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="70c6e-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="70c6e-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="70c6e-148">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="70c6e-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="70c6e-149">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="70c6e-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="70c6e-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="70c6e-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="70c6e-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="70c6e-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="70c6e-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="70c6e-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="70c6e-153">Flickr</span><span class="sxs-lookup"><span data-stu-id="70c6e-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="70c6e-154">Gnutella</span><span class="sxs-lookup"><span data-stu-id="70c6e-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="70c6e-155">Google +</span><span class="sxs-lookup"><span data-stu-id="70c6e-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="70c6e-156">Google 대화</span><span class="sxs-lookup"><span data-stu-id="70c6e-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="70c6e-157">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="70c6e-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="70c6e-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="70c6e-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="70c6e-159">Hopster</span><span class="sxs-lookup"><span data-stu-id="70c6e-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="70c6e-160">HubConnex</span><span class="sxs-lookup"><span data-stu-id="70c6e-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="70c6e-161">IBM 연결</span><span class="sxs-lookup"><span data-stu-id="70c6e-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="70c6e-162">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="70c6e-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="70c6e-163">얼음 채팅</span><span class="sxs-lookup"><span data-stu-id="70c6e-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|<span data-ttu-id="70c6e-164">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="70c6e-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="70c6e-165">명령이 있는 agram</span><span class="sxs-lookup"><span data-stu-id="70c6e-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="70c6e-166">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="70c6e-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="70c6e-167">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="70c6e-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="70c6e-168">IRC</span><span class="sxs-lookup"><span data-stu-id="70c6e-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="70c6e-169">Jive</span><span class="sxs-lookup"><span data-stu-id="70c6e-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="70c6e-170">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="70c6e-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="70c6e-171">JXTA</span><span class="sxs-lookup"><span data-stu-id="70c6e-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="70c6e-172">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="70c6e-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="70c6e-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="70c6e-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="70c6e-174">Microsoft UC</span><span class="sxs-lookup"><span data-stu-id="70c6e-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="70c6e-175">마인드 맞춤</span><span class="sxs-lookup"><span data-stu-id="70c6e-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="70c6e-176">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="70c6e-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="70c6e-177">수신</span><span class="sxs-lookup"><span data-stu-id="70c6e-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="70c6e-178">MySpace</span><span class="sxs-lookup"><span data-stu-id="70c6e-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="70c6e-179">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="70c6e-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="70c6e-180">OpenNap</span><span class="sxs-lookup"><span data-stu-id="70c6e-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="70c6e-181">유 이율</span><span class="sxs-lookup"><span data-stu-id="70c6e-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="70c6e-182">Pivot</span><span class="sxs-lookup"><span data-stu-id="70c6e-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="70c6e-183">QQ</span><span class="sxs-lookup"><span data-stu-id="70c6e-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="70c6e-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="70c6e-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="70c6e-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="70c6e-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="70c6e-186">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="70c6e-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="70c6e-187">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="70c6e-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="70c6e-188">SoftEther</span><span class="sxs-lookup"><span data-stu-id="70c6e-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="70c6e-189">Squawker</span><span class="sxs-lookup"><span data-stu-id="70c6e-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="70c6e-190">Symphony</span><span class="sxs-lookup"><span data-stu-id="70c6e-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="70c6e-191">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="70c6e-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="70c6e-192">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="70c6e-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="70c6e-193">한자</span><span class="sxs-lookup"><span data-stu-id="70c6e-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="70c6e-194">TTT</span><span class="sxs-lookup"><span data-stu-id="70c6e-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="70c6e-195">Twitter</span><span class="sxs-lookup"><span data-stu-id="70c6e-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="70c6e-196">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="70c6e-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="70c6e-197">Vimeo</span><span class="sxs-lookup"><span data-stu-id="70c6e-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="70c6e-198">WinMX</span><span class="sxs-lookup"><span data-stu-id="70c6e-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="70c6e-199">Winny</span><span class="sxs-lookup"><span data-stu-id="70c6e-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="70c6e-200">!</span><span class="sxs-lookup"><span data-stu-id="70c6e-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="70c6e-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="70c6e-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="70c6e-202">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="70c6e-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="70c6e-203">YouTube</span><span class="sxs-lookup"><span data-stu-id="70c6e-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
