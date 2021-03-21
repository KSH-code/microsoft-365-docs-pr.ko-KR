---
title: 데이터 이동 도중 및 이후
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.collection: SPO_Content
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: f47e3e09-b1dc-4b80-b6ea-fd6e0933407f
f1.keywords:
- NOCSH
description: 데이터 이동은 Microsoft가 테넌트의 서비스 및 관련 데이터를 새 데이터 센터 지역으로 이동할 때 발생하는 백 엔드 작업입니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 14563a695e5c092f9bddfbdfdcb758f90cea32c0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929423"
---
# <a name="during-and-after-your-data-move"></a><span data-ttu-id="4c637-103">데이터 이동 도중 및 이후</span><span class="sxs-lookup"><span data-stu-id="4c637-103">During and after your data move</span></span>

<span data-ttu-id="4c637-p101">데이터 이동은 최종 사용자에게 최소의 영향만 미치는 백 엔드 작업입니다. Microsoft에서 사용자의 테넌트의 각 서비스 및 연결된 데이터를 새 데이터 센터 지역으로 이동하는 동안 필요한 작업은 없습니다. 사용자에게 최소한의 영향만 미치면서, 백그라운드에서 사전에 데이터 전송 및 유효성 검사가 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-p101">Data moves are a back-end operation with minimal impact to end-users. No action is required while Microsoft moves each service and associated data for your tenant to a new datacenter geo. Data transfer and validation occur in the background in advance with minimal impact to users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4c637-107">서비스마다 다른 시간에 이동이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-107">Moves occur at different times for each service.</span></span> <span data-ttu-id="4c637-108">결과적으로 다른 시간에 각 서비스의 기능이 제한된다는 설명이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-108">As a result, you'll see the described reduced functionality for each service at a different time.</span></span> 
  
<span data-ttu-id="4c637-109">각 Exchange Online, SharePoint Online 및 Teams 채팅 서비스가 완료된 경우 Microsoft 365 메시지 센터에서 확인을 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="4c637-109">Watch the Microsoft 365 Message Center for confirmation when moves for each of Exchange Online, SharePoint Online, and Teams chat service complete.</span></span> <span data-ttu-id="4c637-110">아래 표에 표시된 것 처럼 등록 기간이 끝나고 최대 24개월이 걸릴 수 있습니다. 휴지의 핵심 고객 데이터를 새 데이터 센터 지역으로 이동하는 데는 최대 24개월이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-110">As shown in the table below, it can take up to 24 months after the end of the enrollment period to complete core customer data at rest moves to the new datacenter geo.</span></span>   

|<span data-ttu-id="4c637-111">**등록 국가가 있는 고객**</span><span class="sxs-lookup"><span data-stu-id="4c637-111">**Customers with signup country in**</span></span>|<span data-ttu-id="4c637-112">**모든 이동 완료 시기**</span><span class="sxs-lookup"><span data-stu-id="4c637-112">**All moves completed by**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4c637-113">오스트레일리아, 뉴질랜드, 피지</span><span class="sxs-lookup"><span data-stu-id="4c637-113">Australia, New Zealand, Fiji</span></span>  <br/> |<span data-ttu-id="4c637-114">2022년 7월 1일</span><span class="sxs-lookup"><span data-stu-id="4c637-114">July 1, 2022</span></span>  <br/> |
|<span data-ttu-id="4c637-115">일본</span><span class="sxs-lookup"><span data-stu-id="4c637-115">Japan</span></span>  <br/> |<span data-ttu-id="4c637-116">2022년 7월 1일</span><span class="sxs-lookup"><span data-stu-id="4c637-116">July 1, 2022</span></span>  <br/> |
|<span data-ttu-id="4c637-117">인도</span><span class="sxs-lookup"><span data-stu-id="4c637-117">India</span></span>  <br/> |<span data-ttu-id="4c637-118">2022년 7월 1일</span><span class="sxs-lookup"><span data-stu-id="4c637-118">July 1, 2022</span></span>  <br/> |
|<span data-ttu-id="4c637-119">캐나다</span><span class="sxs-lookup"><span data-stu-id="4c637-119">Canada</span></span>  <br/> |<span data-ttu-id="4c637-120">2022년 7월 1일</span><span class="sxs-lookup"><span data-stu-id="4c637-120">July 1, 2022</span></span>  <br/> |
|<span data-ttu-id="4c637-121">대한민국</span><span class="sxs-lookup"><span data-stu-id="4c637-121">South Korea</span></span>  <br/> |<span data-ttu-id="4c637-122">2022년 7월 1일</span><span class="sxs-lookup"><span data-stu-id="4c637-122">July 1, 2022</span></span>  <br/> |
|<span data-ttu-id="4c637-123">영국</span><span class="sxs-lookup"><span data-stu-id="4c637-123">United Kingdom</span></span>  <br/> |<span data-ttu-id="4c637-124">2022년 7월 1일</span><span class="sxs-lookup"><span data-stu-id="4c637-124">July 1, 2022</span></span>  <br/> |
|<span data-ttu-id="4c637-125">프랑스</span><span class="sxs-lookup"><span data-stu-id="4c637-125">France</span></span>  <br/> |<span data-ttu-id="4c637-126">2022년 7월 1일</span><span class="sxs-lookup"><span data-stu-id="4c637-126">July 1, 2022</span></span>  <br/> |
|<span data-ttu-id="4c637-127">아랍에미리트</span><span class="sxs-lookup"><span data-stu-id="4c637-127">United Arab Emirates</span></span>  <br/> |<span data-ttu-id="4c637-128">2022년 7월 1일</span><span class="sxs-lookup"><span data-stu-id="4c637-128">July 1, 2022</span></span>  <br/> |
|<span data-ttu-id="4c637-129">남아프리카 공화국</span><span class="sxs-lookup"><span data-stu-id="4c637-129">South Africa</span></span>  <br/> |<span data-ttu-id="4c637-130">2022년 7월 1일</span><span class="sxs-lookup"><span data-stu-id="4c637-130">July 1, 2022</span></span>  <br/> |
|<span data-ttu-id="4c637-131">스위스, 리히텐스테인</span><span class="sxs-lookup"><span data-stu-id="4c637-131">Switzerland, Liechtenstein</span></span>  <br/> |<span data-ttu-id="4c637-132">2022년 7월 1일</span><span class="sxs-lookup"><span data-stu-id="4c637-132">July 1, 2022</span></span>  <br/> |
|<span data-ttu-id="4c637-133">노르웨이</span><span class="sxs-lookup"><span data-stu-id="4c637-133">Norway</span></span>  <br/> |<span data-ttu-id="4c637-134">2022년 11월 1일</span><span class="sxs-lookup"><span data-stu-id="4c637-134">November 1, 2022</span></span>  <br/> |
|<span data-ttu-id="4c637-135">독일</span><span class="sxs-lookup"><span data-stu-id="4c637-135">Germany</span></span>  <br/> |<span data-ttu-id="4c637-136">2023년 5월 1일</span><span class="sxs-lookup"><span data-stu-id="4c637-136">May 1, 2023</span></span>  <br/> |
|<span data-ttu-id="4c637-137">브라질</span><span class="sxs-lookup"><span data-stu-id="4c637-137">Brazil</span></span>  <br/> |<span data-ttu-id="4c637-138">2023년 6월 1일</span><span class="sxs-lookup"><span data-stu-id="4c637-138">June 1, 2023</span></span>  <br/> |

## <a name="exchange-online"></a><span data-ttu-id="4c637-139">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4c637-139">Exchange Online</span></span>

<span data-ttu-id="4c637-140">각 사용자를 새 데이터 센터 지역으로 이동하는 데 시간이 걸리므로 일부 사용자는 다른 사용자가 새 데이터 센터 지역으로 이동되는 동안 이전 데이터 센터 지역에 계속 남아 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-140">Because it takes time to move each user to the new datacenter geo for a single tenant, some users will still be in the old datacenter geo during the move, while others will be in the new datacenter geo.</span></span> <span data-ttu-id="4c637-141">즉, 여러 사서함에 액세스하는 데 관련된 일부 기능은 이동 프로세스의 기간 동안 완전히 작동하지 않을 수 있습니다(주 동안 지속될 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="4c637-141">This means that some features that involve accessing multiple mailboxes may not fully work during a period of the move process, which can last weeks.</span></span> <span data-ttu-id="4c637-142">이러한 기능은 다음 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-142">These features are described in the following sections.</span></span>
  
### <a name="open-shared-folder-in-outlook-web-access"></a><span data-ttu-id="4c637-143">Outlook Web Access에서 "공유 폴더" 열기 </span><span class="sxs-lookup"><span data-stu-id="4c637-143">Open "Shared Folder" in Outlook Web Access</span></span>

<span data-ttu-id="4c637-144">일부 사용자는 "공유 폴더" 기능을 사용하여 Outlook Web Access에서 다른 사서함(사용자가 읽기 또는 쓰기 권한을 가졌다)에서 공유 메일 폴더를 여는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-144">Some users open a shared mail folder from another mailbox (that the user has read or write permissions to) in Outlook Web Access using the "Shared Folder" feature.</span></span> <span data-ttu-id="4c637-145">다음 표에서는 사서함을 이동하는 동안 공유 폴더에 대한 액세스가 작동하는 방식에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-145">The following table describes how access to shared folders works during a mailbox move.</span></span> <span data-ttu-id="4c637-146">공유 사서함에 대한 모든 권한이 있는 사용자는 이동하는 동안 Outlook Web Access를 사용하여 사서함을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-146">Please note that users with full permissions to a shared mailbox can open the mailbox by using Outlook Web Access during the move.</span></span> 
  
|<span data-ttu-id="4c637-147">**구성**</span><span class="sxs-lookup"><span data-stu-id="4c637-147">**Configuration**</span></span>|<span data-ttu-id="4c637-148">**설명**</span><span class="sxs-lookup"><span data-stu-id="4c637-148">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4c637-149">사용자에게 다른 사서함에 대한 사서함 폴더 권한이 있음</span><span class="sxs-lookup"><span data-stu-id="4c637-149">User has mailbox folder permission to another mailbox</span></span>  <br/> |<span data-ttu-id="4c637-150">제한될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-150">Potentially limited.</span></span>  <br/> <span data-ttu-id="4c637-151">테넌트 이동 중에 사용자 A와 사서함 B가 같은 지역이 아닌 경우 사용자 A가 사서함 B의 특정 폴더에 대한 권한만 있는 경우 Outlook Web Access에서 사서함 B의 폴더를 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-151">If User A and Mailbox B aren't in the same geo during the tenant move, User A can't open Mailbox B's folder in Outlook Web Access if User A only has permission to a specific folder in Mailbox B.</span></span>  <br/> <span data-ttu-id="4c637-152">공유 폴더를 추가하려면 왼쪽 탐색 패널에서 사용자 이름을 마우스 오른쪽 단추로 클릭하고 **공유 폴더 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-152">To add a shared folder, right-click the user name in the left navigation panel and select **Add shared folder**.</span></span>  <br/> |
|<span data-ttu-id="4c637-153">사용자에게 다른 사서함에 대한 모든 사서함 권한이 있음</span><span class="sxs-lookup"><span data-stu-id="4c637-153">User with full mailbox permission to another mailbox</span></span>  <br/> |<span data-ttu-id="4c637-154">완전히 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-154">Fully supported.</span></span>  <br/> <span data-ttu-id="4c637-155">사용자 A가 사서함 B에 대한 "모든 권한" 권한이 있는 경우 사용자 A는 Outlook Web Access의 왼쪽 탐색 패널에서 공유 폴더를 클릭하여 사서함 B가 있는 창을 열 수 있습니다.  사용자는 이동 중에 부정적인 영향 없이 Outlook Web Access를 사용하여 공유 사서함을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-155">If User A has "Full Access" permission to Mailbox B, then User A can click the shared folder in the left navigation panel in Outlook Web Access to open a window showing Mailbox B.  A user can open a shared mailbox using Outlook Web Access during the move without any adverse impact.</span></span> <span data-ttu-id="4c637-156">이러한 제한 사항은 사서함의 폴더 수준 공유에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-156">The limitation only applies to folder-level sharing in a mailbox.</span></span>           |
  
## <a name="sharepoint-online"></a><span data-ttu-id="4c637-157">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4c637-157">SharePoint Online</span></span>

<span data-ttu-id="4c637-158">SharePoint Online을 이동하면 다음 서비스에 대한 데이터도 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-158">When SharePoint Online is moved, data for the following services is also moved:</span></span>
  
- <span data-ttu-id="4c637-159">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="4c637-159">One Drive for Business</span></span>
    
- <span data-ttu-id="4c637-160">Microsoft 365 비디오 서비스</span><span class="sxs-lookup"><span data-stu-id="4c637-160">Microsoft 365 Video services</span></span>
    
- <span data-ttu-id="4c637-161">브라우저의 Office</span><span class="sxs-lookup"><span data-stu-id="4c637-161">Office in a browser</span></span>
    
- <span data-ttu-id="4c637-162">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="4c637-162">Microsoft 365 Apps for enterprise</span></span>
    
- <span data-ttu-id="4c637-163">Visio Pro for Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4c637-163">Visio Pro for Microsoft 365</span></span>
    
<span data-ttu-id="4c637-164">SharePoint Online 데이터 이동을 완료하면 다음과 같은 몇 가지 효과가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-164">After we've completed moving your SharePoint Online data, you might see the some of the following effects.</span></span>
  
### <a name="microsoft-365-video-services"></a><span data-ttu-id="4c637-165">Microsoft 365 비디오 서비스</span><span class="sxs-lookup"><span data-stu-id="4c637-165">Microsoft 365 Video Services</span></span>

- <span data-ttu-id="4c637-166">비디오에서는 SharePoint Online에서 콘텐츠의 나머지 부분에 대 한 이동을 보다 긴 데이터 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-166">The data move for video takes longer than the moves for the rest of your content in SharePoint Online.</span></span>
    
- <span data-ttu-id="4c637-167">SharePoint Online 콘텐츠가 이동된 후 비디오를 재생할 수 없는 시간 프레임이 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-167">After the SharePoint Online content is moved, there will be a time frame when videos aren't able to be played.</span></span>
    
- <span data-ttu-id="4c637-168">이전 데이터 센터에서 코드 변환된 복사본을 제거한 후 새로운 데이터 센터에서 다시 코드 변환을 수행하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-168">We're removing the trans-coded copies from the previous datacenter and transcoding them again in the new datacenter.</span></span>
    
### <a name="search"></a><span data-ttu-id="4c637-169">검색</span><span class="sxs-lookup"><span data-stu-id="4c637-169">Search</span></span>

<span data-ttu-id="4c637-170">SharePoint Online 데이터를 이동하는 과정에서 검색 인덱스 및 검색 설정을 새 위치로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-170">In the course of moving your SharePoint Online data, we migrate your search index and search settings to a new location.</span></span> <span data-ttu-id="4c637-171">SharePoint Online  데이터 이동을 완료할 때까지 원래 위치의 인덱스에서 사용자에게 계속 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-171">Until we've **completed** the move of your SharePoint Online data, we continue to serve your users from the index in the original location.</span></span> <span data-ttu-id="4c637-172">새 위치에서 검색은 SharePoint Online 데이터 이동을 완료한 후 자동으로 콘텐츠 크롤링을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-172">In the new location, search automatically starts crawling your content after we've completed moving your SharePoint Online data.</span></span> <span data-ttu-id="4c637-173">이 시점부터는 마이그레이션된 인덱스에서 고객의 사용자에게 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-173">From this point and onwards we serve your users from the migrated index.</span></span> <span data-ttu-id="4c637-174">마이그레이션 후 발생하는 콘텐츠 변경 내용은 크롤링하기 전까지 마이그레이션된 인덱스에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-174">Changes to your content that occurred after the migration aren't included in the migrated index until crawling picks them up.</span></span> <span data-ttu-id="4c637-175">대부분의 고객은 SharePoint Online 데이터 이동을 완료한 직후에 결과가 덜 신선하다는 사실은 인식하지 못하지만 일부 고객은 처음 24~48시간 동안 신선도 감소를 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-175">Most customers don't notice that results are less fresh right after we've completed moving their SharePoint Online data, but some customers might experience reduced freshness in the first 24-48 hours</span></span> 
  
<span data-ttu-id="4c637-176">영향을 받는 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-176">The following search features are affected:</span></span>
  
- <span data-ttu-id="4c637-177">검색 결과 및 검색 웹 파트: 마이그레이션 후 발생한 변경 내용은 크롤링하기 전까지 결과에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-177">Search results and Search Web Parts: Results don't include changes that occurred after the migration until crawling picks them up.</span></span> 
    
- <span data-ttu-id="4c637-178">Delve: 마이그레이션 후 발생한 변경 내용은 크롤링하기 전까지 Delve에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-178">Delve: Delve doesn't include changes that occurred after the migration until crawling picks them up.</span></span>
    
- <span data-ttu-id="4c637-179">사이트의 인기도 및 검색 보고서: 새 위치의 Excel 보고서 수에는 SharePoint Online 데이터 이동을 완료한 후 실행된 사용 현황 보고서의 마이그레이션 횟수 및 개수만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-179">Popularity and Search Reports for the site: Counts for Excel reports in the new location only include migrated counts and counts from usage reports that have run after we completed moving your SharePoint Online data.</span></span> <span data-ttu-id="4c637-180">중간 기간의 모든 수는 손실되며 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-180">Any counts from the interim period are lost and can't be recovered.</span></span> <span data-ttu-id="4c637-181">이 기간은 일반적으로 이틀 정도입니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-181">This period is typically a couple of days.</span></span> <span data-ttu-id="4c637-182">일부 고객은 손실되는 기간이 더 짧거나 길 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-182">Some customers might experience shorter or longer losses.</span></span>
    
- <span data-ttu-id="4c637-183">비디오 포털: 비디오 포털의 조회수 및 통계는 Excel 보고서 통계에 따라 달라지므로 Excel 보고서의 손실 기간만큼 비디오 포털에 대한 조회수 및 통계가 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-183">Video Portal: View counts and statistics for the Video Portal depend on the statistics for Excel Reports, so view counts and statistics for the Video Portal are lost for the same time period as for the Excel reports.</span></span>
    
- <span data-ttu-id="4c637-184">eDiscovery: 마이그레이션하는 동안 변경된 항목은 크롤링하기 전까지 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-184">eDiscovery: Items that changed during the migration aren't shown until crawling picks up the changes.</span></span>
    
- <span data-ttu-id="4c637-185">DLP(데이터 손실 방지): 항목의 변경 내용을 크롤링하기 전까지는 항목에 정책이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-185">Data Loss Protection (DLP): Policies aren't enforced on items that change until crawling picks up the changes.</span></span>

## <a name="microsoft-teams"></a><span data-ttu-id="4c637-186">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4c637-186">Microsoft Teams</span></span>

<span data-ttu-id="4c637-187">Microsoft는 Exchange Online, SharePoint Online 및 비즈니스용 OneDrive 외에도 Teams 채팅 서비스 데이터를 로컬 데이터 센터로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-187">In addition to Exchange Online, SharePoint Online, and OneDrive for Business, Microsoft will migrate Teams chat service data to the local datacenter.</span></span>

- <span data-ttu-id="4c637-188">비공개 메시지 및 채널 메시지를 비롯한 Teams 채팅 메시지</span><span class="sxs-lookup"><span data-stu-id="4c637-188">Teams chat messages, including private messages and channel messages.</span></span>
- <span data-ttu-id="4c637-189">채팅에 사용되는 Teams 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-189">Teams images used in chats.</span></span>

<span data-ttu-id="4c637-190">Teams 파일은 SharePoint Online에 저장되고 Teams 채팅 파일은 비즈니스용 OneDrive에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-190">Teams files are stored in SharePoint Online and Teams chat files are stored in OneDrive for Business.</span></span> <span data-ttu-id="4c637-191">음성 메일, 일정, 채팅 기록 및 연락처는 Exchange Online에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-191">Voicemail, calendar, chat history, and contacts are stored in Exchange Online.</span></span> <span data-ttu-id="4c637-192">대부분의 경우 Exchange Online, SharePoint Online 및 비즈니스용 OneDrive는 로컬 데이터 센터 지역의 고객이 이미 사용하며 적합한 고객 국가에 대한 Microsoft 365 마이그레이션 프로그램의 일부로도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-192">In many cases, Exchange Online, SharePoint Online and OneDrive for Business are already used by the customer in the local datacenter geo and are also part of the Microsoft 365 migration program for eligible customer countries.</span></span>

## <a name="skype-for-business"></a><span data-ttu-id="4c637-193">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="4c637-193">Skype for Business</span></span>

<span data-ttu-id="4c637-194">비즈니스용 Skype 이동은 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-194">Skype for Business moves are no longer available.</span></span>  <span data-ttu-id="4c637-195">[비즈니스용 Skype Online은](/lifecycle/announcements/skype-for-business-online-retirement) 2021년 7월 31에 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-195">[Skype for Business Online will be retired](/lifecycle/announcements/skype-for-business-online-retirement) on July 31, 2021.</span></span> <span data-ttu-id="4c637-196">그 이후에는 서비스에 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c637-196">After that time, the service will no longer be accessible.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="4c637-197">관련 주제</span><span class="sxs-lookup"><span data-stu-id="4c637-197">Related topics</span></span> 
 
[<span data-ttu-id="4c637-198">데이터 이동을 요청하는 방법</span><span class="sxs-lookup"><span data-stu-id="4c637-198">How to request your data move</span></span>](request-your-data-move.md)
    
[<span data-ttu-id="4c637-199">데이터 이동 일반 FAQ</span><span class="sxs-lookup"><span data-stu-id="4c637-199">Data move general FAQ</span></span>](data-move-faq.md)
  
[<span data-ttu-id="4c637-200">새 데이터 센터 Microsoft Dynamics CRM Online</span><span class="sxs-lookup"><span data-stu-id="4c637-200">New datacenter geos for Microsoft Dynamics CRM Online</span></span>](/power-platform/admin/new-datacenter-regions)
  
[<span data-ttu-id="4c637-201">지역별로 Azure 서비스</span><span class="sxs-lookup"><span data-stu-id="4c637-201">Azure services by region</span></span>](https://azure.microsoft.com/regions/)