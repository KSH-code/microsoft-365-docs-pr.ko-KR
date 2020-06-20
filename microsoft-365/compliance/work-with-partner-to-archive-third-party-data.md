---
title: 타사 데이터를 저장하는 데 파트너와 협력
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Salesforce Chatter, Yahoo Messenger 또는 Yammer와 같은 데이터 원본에서 타사 데이터를 가져오도록 사용자 지정 커넥터를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: f76ceda12bf48d26454a47e4b0b5d6ad42fbe55d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817043"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a><span data-ttu-id="e0e5e-103">타사 데이터를 저장하는 데 파트너와 협력</span><span class="sxs-lookup"><span data-stu-id="e0e5e-103">Work with a partner to archive third-party data</span></span>

<span data-ttu-id="e0e5e-104">Microsoft 파트너와 협력 하 여 타사 데이터 원본에서 Microsoft 365로 데이터를 가져오고 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-104">You can work with a Microsoft Partner to import and archive data from a third-party data source to Microsoft 365.</span></span> <span data-ttu-id="e0e5e-105">파트너는 타사 데이터 원본에서 정기적으로 항목을 추출 하 고 해당 항목을 가져오기 위해 구성 된 사용자 지정 커넥터를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-105">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items.</span></span> <span data-ttu-id="e0e5e-106">파트너 커넥터는 항목의 콘텐츠를 데이터 원본에서 전자 메일 메시지 형식으로 변환한 다음 항목을 사서함에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-106">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes.</span></span> <span data-ttu-id="e0e5e-107">타사 데이터를 가져온 후에는이 데이터에 소송 보존, 콘텐츠 검색, 원본 위치 보관, 감사 및 Microsoft 365 고정 정책 등의 Microsoft 365 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-107">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to this data.</span></span>
  
<span data-ttu-id="e0e5e-108">타사 데이터를 가져오기 위해 Microsoft 파트너와 함께 작업 하는 데 필요한 프로세스 및 단계의 개요는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-108">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data.</span></span>

[<span data-ttu-id="e0e5e-109">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="e0e5e-109">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="e0e5e-110">2 단계: 타사 데이터 사서함 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="e0e5e-110">Step 2: Create and configure a third-party data mailbox</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="e0e5e-111">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="e0e5e-111">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="e0e5e-112">4단계: 파트너에게 정보 제공</span><span class="sxs-lookup"><span data-stu-id="e0e5e-112">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="e0e5e-113">5 단계: Azure Active Directory에서 타사 데이터 커넥터 등록</span><span class="sxs-lookup"><span data-stu-id="e0e5e-113">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="e0e5e-114">타사 데이터 가져오기 프로세스의 작동 방식</span><span class="sxs-lookup"><span data-stu-id="e0e5e-114">How the third-party data import process works</span></span>

<span data-ttu-id="e0e5e-115">다음 그림 및 설명은 파트너와 함께 작업 하는 경우 타사 데이터 가져오기 프로세스의 작동 방식에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-115">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>
  
![타사 데이터 가져오기 프로세스의 작동 방식](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="e0e5e-117">고객은 선택한 파트너와 함께 작업 하 여 타사 데이터 원본에서 항목을 추출 하 고 해당 항목을 Microsoft 365로 가져오는 커넥터를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-117">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Microsoft 365.</span></span>
    
2. <span data-ttu-id="e0e5e-118">파트너 커넥터가 타사 API (예약 또는 구성 된 기준)를 통해 타사 데이터 원본에 연결 하 고 데이터 원본에서 항목을 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-118">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="e0e5e-119">파트너 커넥터는 항목의 내용을 전자 메일 메시지 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-119">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="e0e5e-120">메시지 형식 스키마에 대 한 [자세한 내용은 More information](#more-information) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-120">See the [More information](#more-information) section for a description of the message-format schema.</span></span> 
    
3. <span data-ttu-id="e0e5e-121">파트너 커넥터는 잘 알려진 끝점을 통해 EWS (Exchange 웹 서비스)를 사용 하 여 Microsoft 365의 Azure 서비스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-121">Partner connector connects to the Azure service in Microsoft 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="e0e5e-122">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-122">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox.</span></span> <span data-ttu-id="e0e5e-123">Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span><span class="sxs-lookup"><span data-stu-id="e0e5e-123">Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
   1. <span data-ttu-id="e0e5e-124">**사용자 계정에 해당 하는 사용자 ID가 있는 항목:** 파트너 커넥터가 타사 데이터 원본 항목의 사용자 ID를 Office 365의 특정 사용자 ID에 매핑할 수 있는 경우 해당 항목은 사용자의 복구 가능한 항목 폴더에 있는 **제거** 폴더에 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-124">**Items that have a user ID that corresponds to an user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="e0e5e-125">제거 폴더의 항목에는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-125">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="e0e5e-126">그러나 eDiscovery 도구를 사용 하 여 제거 폴더에서 항목을 검색할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-126">However, you can use eDiscovery tools to search for items in the Purges folder.</span></span>
    
   1. <span data-ttu-id="e0e5e-127">**사용자 계정에 해당 하는 사용자 ID가 없는 항목:** 파트너 커넥터가 항목의 사용자 ID를 특정 사용자 ID에 매핑할 수 없는 경우 항목은 타사 데이터 사서함의 **받은 편지함** 폴더에 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-127">**Items that don't have a user ID that corresponds to an user account:** If the partner connector can't map the user ID of an item to a specific user ID, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="e0e5e-128">받은 편지함에 항목을 가져올 수 있으면 관리자 또는 조직의 누군가가 타사 사서함에 로그인하여 이러한 항목을 보고 관리할 수 있으며 파트너 커넥터 구성을 조정해야 하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-128">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="e0e5e-129">1단계: 타사 데이터 파트너 찾기</span><span class="sxs-lookup"><span data-stu-id="e0e5e-129">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="e0e5e-130">Microsoft 365에서 타사 데이터를 보관 하기 위한 주요 구성 요소는 타사 데이터 원본에서 데이터를 캡처하고 Office 365로 가져오는 Microsoft 파트너를 찾고 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-130">A key component for archiving third-party data in Microsoft 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365.</span></span> <span data-ttu-id="e0e5e-131">데이터를 가져온 후에는 조직의 다른 Microsoft 데이터 (예: Exchange의 전자 메일, SharePoint의 문서 및 비즈니스용 OneDrive)와 함께 보관 하 고 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-131">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="e0e5e-132">파트너는 조직의 타사 데이터 원본 (예: BlackBerry, Facebook, Google +,: Thomson Reuters, Twitter)에서 데이터를 추출 하는 커넥터를 만들고 해당 데이터를 Exchange 사서함에 전자 메일 메시지로 가져오는 Office 365 API에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-132">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="e0e5e-133">다음 섹션에는 Office 365에서 타사 데이터를 보관 하기 위한 프로그램에 참여 하는 Microsoft 파트너 (지원 되는 타사 데이터 원본)이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-133">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="e0e5e-134">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="e0e5e-134">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="e0e5e-135">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="e0e5e-135">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="e0e5e-136">Globanet</span><span class="sxs-lookup"><span data-stu-id="e0e5e-136">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="e0e5e-137">OpenText</span><span class="sxs-lookup"><span data-stu-id="e0e5e-137">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="e0e5e-138">Smarsh</span><span class="sxs-lookup"><span data-stu-id="e0e5e-138">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="e0e5e-139">Verba</span><span class="sxs-lookup"><span data-stu-id="e0e5e-139">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="e0e5e-140">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="e0e5e-140">17a-4 LLC</span></span>

<span data-ttu-id="e0e5e-141">[17a-4 LLC](https://www.17a-4.com) 에서는 다음 타사 데이터 원본을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-141">[17a-4 LLC](https://www.17a-4.com) supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="e0e5e-142">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="e0e5e-142">BlackBerry</span></span>
    
- <span data-ttu-id="e0e5e-143">Bloomberg Data Streams</span><span class="sxs-lookup"><span data-stu-id="e0e5e-143">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="e0e5e-144">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="e0e5e-144">Cisco Jabber</span></span>
    
- <span data-ttu-id="e0e5e-145">FactSet</span><span class="sxs-lookup"><span data-stu-id="e0e5e-145">FactSet</span></span>
    
- <span data-ttu-id="e0e5e-146">HipChat</span><span class="sxs-lookup"><span data-stu-id="e0e5e-146">HipChat</span></span>
    
- <span data-ttu-id="e0e5e-147">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="e0e5e-147">InvestEdge</span></span>
    
- <span data-ttu-id="e0e5e-148">LivePerson</span><span class="sxs-lookup"><span data-stu-id="e0e5e-148">LivePerson</span></span>
    
- <span data-ttu-id="e0e5e-149">MessageLabs Data Streams</span><span class="sxs-lookup"><span data-stu-id="e0e5e-149">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="e0e5e-150">OpenText</span><span class="sxs-lookup"><span data-stu-id="e0e5e-150">OpenText</span></span>
    
- <span data-ttu-id="e0e5e-151">Oracle/ATG 'click-to-call' Live Help</span><span class="sxs-lookup"><span data-stu-id="e0e5e-151">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="e0e5e-152">Pivot IMTRADER</span><span class="sxs-lookup"><span data-stu-id="e0e5e-152">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="e0e5e-153">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="e0e5e-153">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="e0e5e-154">MindAlign</span><span class="sxs-lookup"><span data-stu-id="e0e5e-154">MindAlign</span></span>
    
- <span data-ttu-id="e0e5e-155">Sitrion One(Newsgator)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-155">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="e0e5e-156">비즈니스용 Skype(Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-156">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="e0e5e-157">비즈니스용 Skype Online(Lync Online)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-157">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="e0e5e-158">SQL 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="e0e5e-158">SQL Databases</span></span>
    
- <span data-ttu-id="e0e5e-159">Squawker</span><span class="sxs-lookup"><span data-stu-id="e0e5e-159">Squawker</span></span>
    
- <span data-ttu-id="e0e5e-160">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="e0e5e-160">Thomson Reuters Eikon Messenger</span></span>
  

  
### <a name="archivesocial"></a><span data-ttu-id="e0e5e-161">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="e0e5e-161">ArchiveSocial</span></span>

<span data-ttu-id="e0e5e-162">[ArchiveSocial](https://www.archivesocial.com) 에서는 다음의 타사 데이터 원본을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-162">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="e0e5e-163">Facebook</span><span class="sxs-lookup"><span data-stu-id="e0e5e-163">Facebook</span></span>
    
- <span data-ttu-id="e0e5e-164">Flickr</span><span class="sxs-lookup"><span data-stu-id="e0e5e-164">Flickr</span></span>
    
- <span data-ttu-id="e0e5e-165">명령이 있는 agram</span><span class="sxs-lookup"><span data-stu-id="e0e5e-165">Instagram</span></span>
    
- <span data-ttu-id="e0e5e-166">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="e0e5e-166">LinkedIn</span></span>
    
- <span data-ttu-id="e0e5e-167">유 이율</span><span class="sxs-lookup"><span data-stu-id="e0e5e-167">Pinterest</span></span>
    
- <span data-ttu-id="e0e5e-168">Twitter</span><span class="sxs-lookup"><span data-stu-id="e0e5e-168">Twitter</span></span>
    
- <span data-ttu-id="e0e5e-169">YouTube</span><span class="sxs-lookup"><span data-stu-id="e0e5e-169">YouTube</span></span>
    
- <span data-ttu-id="e0e5e-170">Vimeo</span><span class="sxs-lookup"><span data-stu-id="e0e5e-170">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="e0e5e-171">Globanet</span><span class="sxs-lookup"><span data-stu-id="e0e5e-171">Globanet</span></span>

<span data-ttu-id="e0e5e-172">[Globanet](https://www.globanet.com) 에서는 다음의 타사 데이터 원본을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-172">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="e0e5e-173">AOL with Pivot Client </span><span class="sxs-lookup"><span data-stu-id="e0e5e-173">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="e0e5e-174">BlackBerry Call Logs(v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-174">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e0e5e-175">BlackBerry Messenger(v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-175">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e0e5e-176">BlackBerry PIN(v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-176">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e0e5e-177">BlackBerry SMS(v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-177">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e0e5e-178">Bloomberg Chat</span><span class="sxs-lookup"><span data-stu-id="e0e5e-178">Bloomberg Chat</span></span>
    
- <span data-ttu-id="e0e5e-179">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="e0e5e-179">Bloomberg Mail</span></span>
    
- <span data-ttu-id="e0e5e-180">Box</span><span class="sxs-lookup"><span data-stu-id="e0e5e-180">Box</span></span>
    
- <span data-ttu-id="e0e5e-181">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="e0e5e-181">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="e0e5e-182">Cisco IM &amp; 현재 상태 서버 (v10, v 10.5.1 SU1, v 11.0, v 11.5 SU2)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-182">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="e0e5e-183">Cisco Webex 팀</span><span class="sxs-lookup"><span data-stu-id="e0e5e-183">Cisco Webex Teams</span></span>

- <span data-ttu-id="e0e5e-184">Citrix 작업 영역 &amp; sharefile</span><span class="sxs-lookup"><span data-stu-id="e0e5e-184">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="e0e5e-185">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="e0e5e-185">CrowdCompass</span></span>

- <span data-ttu-id="e0e5e-186">사용자 지정 구분 텍스트 파일</span><span class="sxs-lookup"><span data-stu-id="e0e5e-186">Custom-delimited text files</span></span>
    
- <span data-ttu-id="e0e5e-187">사용자 지정 XML 파일</span><span class="sxs-lookup"><span data-stu-id="e0e5e-187">Custom XML files</span></span>
    
- <span data-ttu-id="e0e5e-188">Facebook (페이지)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-188">Facebook (Pages)</span></span>
    
- <span data-ttu-id="e0e5e-189">Factset</span><span class="sxs-lookup"><span data-stu-id="e0e5e-189">Factset</span></span>
    
- <span data-ttu-id="e0e5e-190">FXConnect</span><span class="sxs-lookup"><span data-stu-id="e0e5e-190">FXConnect</span></span>
    
- <span data-ttu-id="e0e5e-191">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="e0e5e-191">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="e0e5e-192">Jive</span><span class="sxs-lookup"><span data-stu-id="e0e5e-192">Jive</span></span>
    
- <span data-ttu-id="e0e5e-193">Macgregor XIP</span><span class="sxs-lookup"><span data-stu-id="e0e5e-193">Macgregor XIP</span></span>

- <span data-ttu-id="e0e5e-194">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e0e5e-194">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="e0e5e-195">Microsoft 비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="e0e5e-195">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="e0e5e-196">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e0e5e-196">Microsoft Teams</span></span>
       
- <span data-ttu-id="e0e5e-197">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="e0e5e-197">Microsoft Yammer</span></span>
    
- <span data-ttu-id="e0e5e-198">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="e0e5e-198">Mobile Guard</span></span>
    
- <span data-ttu-id="e0e5e-199">Pivot</span><span class="sxs-lookup"><span data-stu-id="e0e5e-199">Pivot</span></span>
    
- <span data-ttu-id="e0e5e-200">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="e0e5e-200">Salesforce Chatter</span></span>

- <span data-ttu-id="e0e5e-201">비즈니스용 Skype Online</span><span class="sxs-lookup"><span data-stu-id="e0e5e-201">Skype for Business Online</span></span>
    
- <span data-ttu-id="e0e5e-202">비즈니스용 Skype, 버전 2007 R2 - 2016(온-프레미스)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-202">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="e0e5e-203">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="e0e5e-203">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="e0e5e-204">Symphony</span><span class="sxs-lookup"><span data-stu-id="e0e5e-204">Symphony</span></span>
    
- <span data-ttu-id="e0e5e-205">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="e0e5e-205">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="e0e5e-206">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="e0e5e-206">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="e0e5e-207">Thomson Reuters Dealings 3000 / FX Trading</span><span class="sxs-lookup"><span data-stu-id="e0e5e-207">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="e0e5e-208">Twitter</span><span class="sxs-lookup"><span data-stu-id="e0e5e-208">Twitter</span></span>
    
- <span data-ttu-id="e0e5e-209">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="e0e5e-209">UBS Chat</span></span>
    
- <span data-ttu-id="e0e5e-210">YouTube</span><span class="sxs-lookup"><span data-stu-id="e0e5e-210">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="e0e5e-211">OpenText</span><span class="sxs-lookup"><span data-stu-id="e0e5e-211">OpenText</span></span>

<span data-ttu-id="e0e5e-212">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) 에서는 다음의 타사 데이터 원본을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-212">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="e0e5e-213">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="e0e5e-213">Axs Encrypted</span></span>
    
- <span data-ttu-id="e0e5e-214">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="e0e5e-214">Axs Exchange</span></span>
    
- <span data-ttu-id="e0e5e-215">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="e0e5e-215">Axs Local Archive</span></span>
    
- <span data-ttu-id="e0e5e-216">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="e0e5e-216">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="e0e5e-217">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="e0e5e-217">Axs Signed</span></span>
    
- <span data-ttu-id="e0e5e-218">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="e0e5e-218">Bloomberg</span></span>
    
- <span data-ttu-id="e0e5e-219">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="e0e5e-219">Thomson Reuters</span></span>
  
### <a name="smarsh"></a><span data-ttu-id="e0e5e-220">Smarsh</span><span class="sxs-lookup"><span data-stu-id="e0e5e-220">Smarsh</span></span>

<span data-ttu-id="e0e5e-221">[Smarsh](https://www.smarsh.com) 에서는 다음의 타사 데이터 원본을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-221">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="e0e5e-222">AIM</span><span class="sxs-lookup"><span data-stu-id="e0e5e-222">AIM</span></span>
    
- <span data-ttu-id="e0e5e-223">American Idol</span><span class="sxs-lookup"><span data-stu-id="e0e5e-223">American Idol</span></span>
    
- <span data-ttu-id="e0e5e-224">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="e0e5e-224">Apple Juice</span></span>
    
- <span data-ttu-id="e0e5e-225">AOL with Pivot client</span><span class="sxs-lookup"><span data-stu-id="e0e5e-225">AOL with Pivot client</span></span>
    
- <span data-ttu-id="e0e5e-226">Ares</span><span class="sxs-lookup"><span data-stu-id="e0e5e-226">Ares</span></span>
    
- <span data-ttu-id="e0e5e-227">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="e0e5e-227">Bazaar Voice</span></span>
    
- <span data-ttu-id="e0e5e-228">Bear Share</span><span class="sxs-lookup"><span data-stu-id="e0e5e-228">Bear Share</span></span>
    
- <span data-ttu-id="e0e5e-229">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="e0e5e-229">Bit Torrent</span></span>
    
- <span data-ttu-id="e0e5e-230">BlackBerry Call Logs(v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-230">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e0e5e-231">BlackBerry Messenger(v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-231">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e0e5e-232">BlackBerry PIN(v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-232">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e0e5e-233">BlackBerry SMS(v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-233">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e0e5e-234">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="e0e5e-234">Bloomberg Mail</span></span>
    
- <span data-ttu-id="e0e5e-235">셀 신뢰</span><span class="sxs-lookup"><span data-stu-id="e0e5e-235">CellTrust</span></span>
    
- <span data-ttu-id="e0e5e-236">Chat Import</span><span class="sxs-lookup"><span data-stu-id="e0e5e-236">Chat Import</span></span>
    
- <span data-ttu-id="e0e5e-237">Chat Real Time Logging and Policy</span><span class="sxs-lookup"><span data-stu-id="e0e5e-237">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="e0e5e-238">Chatter</span><span class="sxs-lookup"><span data-stu-id="e0e5e-238">Chatter</span></span>
    
- <span data-ttu-id="e0e5e-239">Cisco IM &amp; 현재 상태 서버 (v 9.0.1, v 9.1, v 9.1.1 SU1, v10, v 10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-239">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="e0e5e-240">Cisco Unified Presence Server(v8.6.3, v8.6.4, v8.6.5)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-240">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="e0e5e-241">Collaboration Import</span><span class="sxs-lookup"><span data-stu-id="e0e5e-241">Collaboration Import</span></span>
    
- <span data-ttu-id="e0e5e-242">Collaboration Real Time Logging</span><span class="sxs-lookup"><span data-stu-id="e0e5e-242">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="e0e5e-243">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="e0e5e-243">Direct Connect</span></span>
    
- <span data-ttu-id="e0e5e-244">Facebook</span><span class="sxs-lookup"><span data-stu-id="e0e5e-244">Facebook</span></span>
    
- <span data-ttu-id="e0e5e-245">FactSet</span><span class="sxs-lookup"><span data-stu-id="e0e5e-245">FactSet</span></span>
    
- <span data-ttu-id="e0e5e-246">FastTrack</span><span class="sxs-lookup"><span data-stu-id="e0e5e-246">FastTrack</span></span>
    
- <span data-ttu-id="e0e5e-247">Gnutella</span><span class="sxs-lookup"><span data-stu-id="e0e5e-247">Gnutella</span></span>
    
- <span data-ttu-id="e0e5e-248">Google +</span><span class="sxs-lookup"><span data-stu-id="e0e5e-248">Google+</span></span>
    
- <span data-ttu-id="e0e5e-249">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="e0e5e-249">GoToMyPC</span></span>
    
- <span data-ttu-id="e0e5e-250">Hopster</span><span class="sxs-lookup"><span data-stu-id="e0e5e-250">Hopster</span></span>
    
- <span data-ttu-id="e0e5e-251">HubConnex</span><span class="sxs-lookup"><span data-stu-id="e0e5e-251">HubConnex</span></span>
    
- <span data-ttu-id="e0e5e-252">IBM Connections(v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-252">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="e0e5e-253">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="e0e5e-253">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="e0e5e-254">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="e0e5e-254">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="e0e5e-255">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="e0e5e-255">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="e0e5e-256">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="e0e5e-256">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="e0e5e-257">IBM SameTime Community(v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-257">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="e0e5e-258">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="e0e5e-258">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="e0e5e-259">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="e0e5e-259">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="e0e5e-260">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="e0e5e-260">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="e0e5e-261">아이스/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="e0e5e-261">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="e0e5e-262">IM Import</span><span class="sxs-lookup"><span data-stu-id="e0e5e-262">IM Import</span></span>
    
- <span data-ttu-id="e0e5e-263">IM Real Time Logging and Policy</span><span class="sxs-lookup"><span data-stu-id="e0e5e-263">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="e0e5e-264">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="e0e5e-264">Indii Messenger</span></span>
    
- <span data-ttu-id="e0e5e-265">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="e0e5e-265">Instant Bloomberg</span></span>
    
- <span data-ttu-id="e0e5e-266">IRC</span><span class="sxs-lookup"><span data-stu-id="e0e5e-266">IRC</span></span>
    
- <span data-ttu-id="e0e5e-267">Jive</span><span class="sxs-lookup"><span data-stu-id="e0e5e-267">Jive</span></span>
    
- <span data-ttu-id="e0e5e-268">Jive 6 Real Time Logging(v6, v7)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-268">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="e0e5e-269">Jive Import</span><span class="sxs-lookup"><span data-stu-id="e0e5e-269">Jive Import</span></span>
    
- <span data-ttu-id="e0e5e-270">JXTA</span><span class="sxs-lookup"><span data-stu-id="e0e5e-270">JXTA</span></span>
    
- <span data-ttu-id="e0e5e-271">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="e0e5e-271">LinkedIn</span></span>
    
- <span data-ttu-id="e0e5e-272">Microsoft Lync(2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-272">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="e0e5e-273">MFTP</span><span class="sxs-lookup"><span data-stu-id="e0e5e-273">MFTP</span></span>
    
- <span data-ttu-id="e0e5e-274">Microsoft Lync 2013 Voice</span><span class="sxs-lookup"><span data-stu-id="e0e5e-274">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="e0e5e-275">Microsoft SharePoint(2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-275">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="e0e5e-276">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e0e5e-276">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="e0e5e-277">Microsoft UC(Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-277">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="e0e5e-278">MindAlign</span><span class="sxs-lookup"><span data-stu-id="e0e5e-278">MindAlign</span></span>
    
- <span data-ttu-id="e0e5e-279">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="e0e5e-279">Mobile Guard</span></span>
    
- <span data-ttu-id="e0e5e-280">수신</span><span class="sxs-lookup"><span data-stu-id="e0e5e-280">MSN</span></span>
    
- <span data-ttu-id="e0e5e-281">My Space</span><span class="sxs-lookup"><span data-stu-id="e0e5e-281">My Space</span></span>
    
- <span data-ttu-id="e0e5e-282">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="e0e5e-282">NEONetwork</span></span>
    
- <span data-ttu-id="e0e5e-283">Office 365 Lync Dedicated</span><span class="sxs-lookup"><span data-stu-id="e0e5e-283">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="e0e5e-284">Office 365 Shared IM</span><span class="sxs-lookup"><span data-stu-id="e0e5e-284">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="e0e5e-285">유 이율</span><span class="sxs-lookup"><span data-stu-id="e0e5e-285">Pinterest</span></span>
    
- <span data-ttu-id="e0e5e-286">Pivot</span><span class="sxs-lookup"><span data-stu-id="e0e5e-286">Pivot</span></span>
    
- <span data-ttu-id="e0e5e-287">QQ</span><span class="sxs-lookup"><span data-stu-id="e0e5e-287">QQ</span></span>
    
- <span data-ttu-id="e0e5e-288">비즈니스용 Skype 2015</span><span class="sxs-lookup"><span data-stu-id="e0e5e-288">Skype for Business 2015</span></span>
    
- <span data-ttu-id="e0e5e-289">SoftEther</span><span class="sxs-lookup"><span data-stu-id="e0e5e-289">SoftEther</span></span>
    
- <span data-ttu-id="e0e5e-290">Symphony</span><span class="sxs-lookup"><span data-stu-id="e0e5e-290">Symphony</span></span>
    
- <span data-ttu-id="e0e5e-291">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="e0e5e-291">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="e0e5e-292">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="e0e5e-292">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="e0e5e-293">한자</span><span class="sxs-lookup"><span data-stu-id="e0e5e-293">Tor</span></span>
    
- <span data-ttu-id="e0e5e-294">TTT</span><span class="sxs-lookup"><span data-stu-id="e0e5e-294">TTT</span></span>
    
- <span data-ttu-id="e0e5e-295">Twitter</span><span class="sxs-lookup"><span data-stu-id="e0e5e-295">Twitter</span></span>
    
- <span data-ttu-id="e0e5e-296">WinMX</span><span class="sxs-lookup"><span data-stu-id="e0e5e-296">WinMX</span></span>
    
- <span data-ttu-id="e0e5e-297">Winny</span><span class="sxs-lookup"><span data-stu-id="e0e5e-297">Winny</span></span>
    
- <span data-ttu-id="e0e5e-298">Yahoo</span><span class="sxs-lookup"><span data-stu-id="e0e5e-298">Yahoo</span></span>
    
- <span data-ttu-id="e0e5e-299">Yammer</span><span class="sxs-lookup"><span data-stu-id="e0e5e-299">Yammer</span></span>
    
- <span data-ttu-id="e0e5e-300">YouTube</span><span class="sxs-lookup"><span data-stu-id="e0e5e-300">YouTube</span></span>
    

### <a name="verba"></a><span data-ttu-id="e0e5e-301">Verba</span><span class="sxs-lookup"><span data-stu-id="e0e5e-301">Verba</span></span>

<span data-ttu-id="e0e5e-302">[Verba](https://www.verba.com) 는 다음 타사 데이터 원본을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-302">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="e0e5e-303">Avaya Aura Video</span><span class="sxs-lookup"><span data-stu-id="e0e5e-303">Avaya Aura Video</span></span>
    
- <span data-ttu-id="e0e5e-304">Avaya Aura Voice</span><span class="sxs-lookup"><span data-stu-id="e0e5e-304">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="e0e5e-305">Avtec Radio</span><span class="sxs-lookup"><span data-stu-id="e0e5e-305">Avtec Radio</span></span>
    
- <span data-ttu-id="e0e5e-306">Bosch/Telex Radio</span><span class="sxs-lookup"><span data-stu-id="e0e5e-306">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="e0e5e-307">BroadSoft Video</span><span class="sxs-lookup"><span data-stu-id="e0e5e-307">BroadSoft Video</span></span>
    
- <span data-ttu-id="e0e5e-308">BroadSoft Voice</span><span class="sxs-lookup"><span data-stu-id="e0e5e-308">BroadSoft Voice</span></span>
    
- <span data-ttu-id="e0e5e-309">Centile Voice</span><span class="sxs-lookup"><span data-stu-id="e0e5e-309">Centile Voice</span></span>
    
- <span data-ttu-id="e0e5e-310">Cisco Jabber IM</span><span class="sxs-lookup"><span data-stu-id="e0e5e-310">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="e0e5e-311">Cisco UC Video</span><span class="sxs-lookup"><span data-stu-id="e0e5e-311">Cisco UC Video</span></span>
    
- <span data-ttu-id="e0e5e-312">Cisco UC Voice</span><span class="sxs-lookup"><span data-stu-id="e0e5e-312">Cisco UC Voice</span></span>
    
- <span data-ttu-id="e0e5e-313">Cisco c s p/c h i v 비디오</span><span class="sxs-lookup"><span data-stu-id="e0e5e-313">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="e0e5e-314">Cisco c s p/c h 음성</span><span class="sxs-lookup"><span data-stu-id="e0e5e-314">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="e0e5e-315">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="e0e5e-315">ESChat Radio</span></span>
    
- <span data-ttu-id="e0e5e-316">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="e0e5e-316">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="e0e5e-317">IP Trade Voice</span><span class="sxs-lookup"><span data-stu-id="e0e5e-317">IP Trade Voice</span></span>
    
- <span data-ttu-id="e0e5e-318">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="e0e5e-318">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="e0e5e-319">Microsoft UC(Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-319">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="e0e5e-320">Mitel MiContact Center for Lync(prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="e0e5e-320">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="e0e5e-321">Oracle/Acme Packet Session Border Controller Video</span><span class="sxs-lookup"><span data-stu-id="e0e5e-321">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="e0e5e-322">Oracle/Acme Packet Session Border Controller Voice</span><span class="sxs-lookup"><span data-stu-id="e0e5e-322">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="e0e5e-323">Singtel Mobile Voice</span><span class="sxs-lookup"><span data-stu-id="e0e5e-323">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="e0e5e-324">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="e0e5e-324">SIPREC Video</span></span>
    
-  <span data-ttu-id="e0e5e-325">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="e0e5e-325">SIPREC Voice</span></span> 
    
- <span data-ttu-id="e0e5e-326">비즈니스용 Skype/Lync IM</span><span class="sxs-lookup"><span data-stu-id="e0e5e-326">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="e0e5e-327">비즈니스용 Skype/Lync Video</span><span class="sxs-lookup"><span data-stu-id="e0e5e-327">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="e0e5e-328">비즈니스용 Skype/Lync Voice</span><span class="sxs-lookup"><span data-stu-id="e0e5e-328">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="e0e5e-329">Speakerbus Voice</span><span class="sxs-lookup"><span data-stu-id="e0e5e-329">Speakerbus Voice</span></span>
    
- <span data-ttu-id="e0e5e-330">Standard SIP/H.323 Video</span><span class="sxs-lookup"><span data-stu-id="e0e5e-330">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="e0e5e-331">Standard SIP/H.323 Voice</span><span class="sxs-lookup"><span data-stu-id="e0e5e-331">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="e0e5e-332">Truphone Voice</span><span class="sxs-lookup"><span data-stu-id="e0e5e-332">Truphone Voice</span></span>
    
- <span data-ttu-id="e0e5e-333">TwistedPair Radio</span><span class="sxs-lookup"><span data-stu-id="e0e5e-333">TwistedPair Radio</span></span>
    
- <span data-ttu-id="e0e5e-334">Windows 데스크톱 컴퓨터 화면</span><span class="sxs-lookup"><span data-stu-id="e0e5e-334">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="e0e5e-335">2단계: Office 365에서 타사 데이터 사서함 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="e0e5e-335">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="e0e5e-336">다음은 Office 365로 데이터를 가져오기 위한 타사 데이터 사서함을 만들고 구성 하는 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-336">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365.</span></span> <span data-ttu-id="e0e5e-337">앞에서 설명한 것 처럼 파트너 커넥터에서 항목의 사용자 ID를 사용자 계정에 매핑할 수 없는 경우에는이 사서함으로 항목을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-337">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an user account.</span></span>
  
 <span data-ttu-id="e0e5e-338">**Microsoft 365 관리 센터에서이 작업 완료**</span><span class="sxs-lookup"><span data-stu-id="e0e5e-338">**Complete these tasks in the Microsoft 365 admin center**</span></span>
  
1. <span data-ttu-id="e0e5e-339">사용자 계정을 만들고이 계정에 Exchange Online 계획 2 라이선스를 할당 합니다. [Office 365에 사용자 추가를](https://go.microsoft.com/fwlink/p/?LinkId=692098)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-339">Create a user account and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="e0e5e-340">계획 2 라이선스는 사서함을 소송 보존 상태로 설정 하거나 저장소 할당량이 무제한 인 보관 사서함을 사용 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-340">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="e0e5e-341">타사 데이터 사서함에 대 한 사용자 계정을 Office 365의 **Exchange 관리자** 관리자 역할에 추가 합니다. [Office 365에서 관리자 역할 할당을](https://go.microsoft.com/fwlink/p/?LinkId=532393)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-341">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e0e5e-342">이 사용자 계정의 자격 증명을 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-342">Write down the credentials for this user account.</span></span> <span data-ttu-id="e0e5e-343">4단계에서 설명한 것처럼 파트너에게 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-343">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="e0e5e-344">**Exchange 관리 센터에서 다음 작업 완료**</span><span class="sxs-lookup"><span data-stu-id="e0e5e-344">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="e0e5e-345">조직의 주소록 및 기타 주소 목록에서 타사 데이터 사서함을 숨깁니다. [사용자 사서함 관리](https://go.microsoft.com/fwlink/p/?LinkId=616058)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-345">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="e0e5e-346">또는 다음 PowerShell 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-346">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="e0e5e-347">Administrators 또는 규정 준수 관리자가 Outlook 데스크톱 클라이언트에서 타사 데이터 사서함을 열 수 있도록 타사 데이터 사서함에 대 한 **FullAccess** 권한을 할당 합니다. [받는 사람의 사용 권한 관리를](https://go.microsoft.com/fwlink/p/?LinkId=692104)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-347">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="e0e5e-348">타사 데이터 사서함에 대해 다음과 같은 준수 관련 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-348">Enable the following compliance-related features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="e0e5e-349">보관 사서함을 사용 하도록 설정 합니다. [보관 사서함 사용](enable-archive-mailboxes.md) 및 [무제한 보관 사용](enable-unlimited-archiving.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-349">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="e0e5e-350">이렇게 하면 타사 데이터 항목을 보관 사서함으로 이동 하는 보관 정책을 설정 하 여 기본 사서함의 저장 공간을 확보할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-350">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="e0e5e-351">이를 통해 타사 데이터에 대해 무제한 저장소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-351">This provides you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="e0e5e-352">타사 데이터 사서함에 소송 보존을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-352">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="e0e5e-353">보안 및 준수 센터에서 Microsoft 365 보존 정책을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-353">You can also apply a Microsoft 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="e0e5e-354">이 사서함을 보류 상태로 두면 타사 데이터 항목 (무기한 또는 지정 된 기간 동안)이 유지 되 고 사서함에서 제거 되는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-354">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="e0e5e-355">다음 항목 중 하나를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-355">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="e0e5e-356">사서함을 소송 자료 보존으로 설정</span><span class="sxs-lookup"><span data-stu-id="e0e5e-356">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="e0e5e-357">보존 정책 개요</span><span class="sxs-lookup"><span data-stu-id="e0e5e-357">Overview of retention policies</span></span>](retention-policies.md)
    
    - <span data-ttu-id="e0e5e-358">타사 데이터 사서함에 대 한 소유자, 대리인 및 관리자 액세스에 대 한 사서함 감사 로깅을 사용 하도록 설정 합니다. [사서함 감사 사용](enable-mailbox-auditing.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-358">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="e0e5e-359">이렇게 하면 타사 데이터 사서함에 대 한 액세스 권한이 있는 모든 사용자가 수행한 모든 작업을 감사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-359">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="e0e5e-360">3단계: 타사 데이터에 대한 사용자 사서함 구성</span><span class="sxs-lookup"><span data-stu-id="e0e5e-360">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="e0e5e-361">다음 단계는 타사 데이터를 지원하도록 사용자 사서함을 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-361">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="e0e5e-362">Exchange 관리 센터를 사용 하거나 해당 Windows PowerShell cmdlet을 사용 하 여 이러한 작업을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-362">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="e0e5e-363">각 사용자에 대해 보관 사서함을 사용 하도록 설정 합니다. [보관 사서함 사용](enable-archive-mailboxes.md) 및 [무제한 보관 사용](enable-unlimited-archiving.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-363">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="e0e5e-364">사용자 사서함을 소송 보존으로 설정 하거나 Microsoft 365 보관 정책을 적용 합니다. 다음 항목 중 하나를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-364">Place user mailboxes on Litigation Hold or apply a Microsoft 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="e0e5e-365">사서함을 소송 자료 보존으로 설정</span><span class="sxs-lookup"><span data-stu-id="e0e5e-365">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="e0e5e-366">보존 정책 개요</span><span class="sxs-lookup"><span data-stu-id="e0e5e-366">Overview of retention policies</span></span>](retention-policies.md)
    
    <span data-ttu-id="e0e5e-367">앞서 언급한 것처럼 사서함을 보존하면 타사 데이터 원본의 항목을 보존하는 기간을 설정하거나 항목을 무기한 보존하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-367">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="e0e5e-368">4단계: 파트너에게 정보 제공</span><span class="sxs-lookup"><span data-stu-id="e0e5e-368">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="e0e5e-369">마지막 단계는 조직에 연결 하 여 데이터를 사용자 사서함 및 타사 데이터 사서함으로 가져오기 위해 커넥터를 구성할 수 있도록 파트너에 게 다음 정보를 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-369">The final step is to provide your partner with the following information so they can configure the connector to connect to your organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="e0e5e-370">Office 365에서 Azure 서비스에 연결 하는 데 사용 되는 끝점:</span><span class="sxs-lookup"><span data-stu-id="e0e5e-370">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="e0e5e-371">2 단계에서 만든 타사 데이터 사서함의 로그인 자격 증명 (Microsoft 365 사용자 ID 및 암호)입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-371">The sign-in credentials (Microsoft 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="e0e5e-372">이러한 자격 증명은 파트너 커넥터가 항목을 액세스하고 사용자 사서함 및 타사 데이터 사서함으로 가져올 수 있도록 하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-372">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="e0e5e-373">5 단계: Azure Active Directory에서 타사 데이터 커넥터 등록</span><span class="sxs-lookup"><span data-stu-id="e0e5e-373">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="e0e5e-374">2018 년 9 월 30 일부 부터는 Office 365의 Azure 서비스가 Exchange Online의 최신 인증을 사용 하 여 데이터를 가져오기 위해 조직에 연결을 시도 하는 타사 데이터 커넥터를 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-374">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your organization to import data.</span></span> <span data-ttu-id="e0e5e-375">이러한 변경이 발생 하는 이유는 최신 인증이 이전에 설명한 끝점을 사용 하 여 Azure 서비스에 연결 하는 타사 커넥터에 대 한 허용 목록을 기반으로 하는 현재 방법 보다 더 많은 보안을 제공 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-375">The reason for this change is that modern authentication provides more security than the current method, which was based on an allow list for third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="e0e5e-376">최신 인증 방법을 사용 하 여 타사 데이터 커넥터에서 Office 365에 연결할 수 있도록 하려면 조직의 관리자가 해당 커넥터를 Azure Active Directory의 신뢰할 수 있는 서비스 응용 프로그램으로 등록 하는 것이 동의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-376">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="e0e5e-377">이 작업은 사용 권한 요청을 수락 하 여 커넥터가 Azure Active Directory에서 조직의 데이터에 액세스할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-377">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="e0e5e-378">이 요청을 수락 하면 타사 데이터 커넥터가 엔터프라이즈 응용 프로그램으로 Azure Active Directory에 추가 되 고 서비스 사용자로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-378">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="e0e5e-379">승인 프로세스에 대 한 자세한 내용은 [테 넌 트 관리자 동의](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-379">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="e0e5e-380">커넥터 등록을 위한 요청에 액세스 하 고 수락 하는 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-380">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="e0e5e-381">[이 페이지로](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) 이동 하 여 전역 관리자의 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-381">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of a global administrator.</span></span>

   <span data-ttu-id="e0e5e-382">다음 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-382">The following dialog box is displayed.</span></span> <span data-ttu-id="e0e5e-383">Carets를 확장 하 여 커넥터에 할당 되는 사용 권한을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-383">You can expand the carets to review the permissions that will be assigned to the connector.</span></span>

   ![사용 권한 요청 대화 상자가 표시 됩니다.](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. <span data-ttu-id="e0e5e-385">**Accept(동의함)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-385">Click **Accept**.</span></span>

<span data-ttu-id="e0e5e-386">요청을 수락 하면 [Azure portal](https://portal.azure.com) 이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-386">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="e0e5e-387">조직의 응용 프로그램 목록을 보려면 **Azure Active Directory**  >  **Enterprise 응용 프로그램**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-387">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="e0e5e-388">Office 365 타사 데이터 커넥터가 **엔터프라이즈 응용 프로그램** 블레이드에서 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-388">The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0e5e-389">Azure Active Directory에 타사 데이터 커넥터를 등록 하지 않으면, 2018 년 9 월 30 일 이후에는 타사 데이터를 조직의 사서함으로 가져올 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-389">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="e0e5e-390">참고 5 단계에 나와 있는 절차에 따라 기존 타사 데이터 커넥터 (9 월 30 일 이전에는 2018)도 Azure Active Directory에 등록 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-390">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="e0e5e-391">타사 데이터 커넥터에 대 한 동의 해지</span><span class="sxs-lookup"><span data-stu-id="e0e5e-391">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="e0e5e-392">조직이 Azure Active Directory에서 타사 데이터 커넥터를 등록 하기 위해 권한 요청을 consents 후에는 조직에서 언제 든 지 해당 동의를 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-392">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="e0e5e-393">그러나 커넥터에 대 한 동의를 취소 하는 것은 타사 데이터 원본의 데이터를 더 이상 Office 365로 가져올 수 없다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-393">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="e0e5e-394">타사 데이터 커넥터에 대 한 동의를 해지 하려면 Azure portal에서 **엔터프라이즈 응용 프로그램** 블레이드를 사용 하 여 Azure Active Directory에서 해당 서비스 사용자를 삭제 하거나 Office 365 PowerShell의 [(new-msolserviceprincipal에서 제거](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) 를 사용 하 여 응용 프로그램을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-394">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span></span> <span data-ttu-id="e0e5e-395">Azure Active Directory PowerShell에서 [AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-395">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="e0e5e-396">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e0e5e-396">More information</span></span>

- <span data-ttu-id="e0e5e-397">앞서 설명한 것처럼 타사 데이터 원본의 항목을 Exchange 사서함에 전자 메일 메시지로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-397">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="e0e5e-398">파트너 커넥터는 Office 365 API에 필요한 스키마를 사용 하 여 항목을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-398">The partner connector imports the item using a schema required by the Office 365 API.</span></span> <span data-ttu-id="e0e5e-399">다음 표에서는 타사 데이터 원본 항목을 Exchange 사서함에 전자 메일 메시지로 가져온 후, 타사 데이터 원본 항목에 대한 메시지 속성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-399">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="e0e5e-400">또한 이 표는 메시지 속성이 필수인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-400">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="e0e5e-401">필수 속성은 채워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-401">Mandatory properties must be populated.</span></span> <span data-ttu-id="e0e5e-402">항목에 필수 속성이 없는 경우에는 Office 365로 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-402">If an item is missing a mandatory property, it won't be imported to Office 365.</span></span> <span data-ttu-id="e0e5e-403">가져오기 프로세스를 진행 하면 항목을 가져오지 못한 이유와 해당 속성이 누락 된 이유를 설명 하는 오류 메시지가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-403">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span><br/><br/>
    
    |<span data-ttu-id="e0e5e-404">**메시지 속성**</span><span class="sxs-lookup"><span data-stu-id="e0e5e-404">**Message property**</span></span>|<span data-ttu-id="e0e5e-405">**강제?**</span><span class="sxs-lookup"><span data-stu-id="e0e5e-405">**Mandatory?**</span></span>|<span data-ttu-id="e0e5e-406">**설명**</span><span class="sxs-lookup"><span data-stu-id="e0e5e-406">**Description**</span></span>|<span data-ttu-id="e0e5e-407">**예제 값**</span><span class="sxs-lookup"><span data-stu-id="e0e5e-407">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e0e5e-408">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="e0e5e-408">**FROM**</span></span> <br/> |<span data-ttu-id="e0e5e-409">예</span><span class="sxs-lookup"><span data-stu-id="e0e5e-409">Yes</span></span>  <br/> |<span data-ttu-id="e0e5e-410">타사 데이터 원본 항목을 처음 만들었거나 보낸 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-410">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="e0e5e-411">파트너 커넥터는 원본 항목 (예: Twitter 핸들)의 사용자 ID를 모든 참가자 (시작 및 대상 필드의 사용자)의 사용자 계정에 매핑하도록 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-411">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to an user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="e0e5e-412">메시지 복사본을 모든 참가자의 사서함으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-412">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="e0e5e-413">항목에서 사용자 계정에 매핑할 수 없는 참가자가 없는 경우 Office 365에서 타사 보관 사서함으로 항목을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-413">If none of the participants from the item can be mapped to an user account, the item will be imported to the third-party archiving mailbox in Office 365.</span></span>  <br/> <br/> <span data-ttu-id="e0e5e-414">항목을 보낸 사람으로 식별 된 참석자는 해당 항목을 가져올 조직의 활성 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-414">The participant who's identified as the sender of the item must have an active mailbox in the organization that the item is being imported to.</span></span> <span data-ttu-id="e0e5e-415">보낸 사람에게 활성 사서함이 없으면 다음과 같은 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-415">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="e0e5e-416">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="e0e5e-416">**TO**</span></span> <br/> |<span data-ttu-id="e0e5e-417">예</span><span class="sxs-lookup"><span data-stu-id="e0e5e-417">Yes</span></span>  <br/> |<span data-ttu-id="e0e5e-418">데이터 원본의 항목을 받은 사람입니다(해당되는 경우).</span><span class="sxs-lookup"><span data-stu-id="e0e5e-418">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="e0e5e-419">**제목**</span><span class="sxs-lookup"><span data-stu-id="e0e5e-419">**SUBJECT**</span></span> <br/> |<span data-ttu-id="e0e5e-420">아니요</span><span class="sxs-lookup"><span data-stu-id="e0e5e-420">No</span></span>  <br/> |<span data-ttu-id="e0e5e-421">원본 항목의 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-421">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="e0e5e-422">**종료일**</span><span class="sxs-lookup"><span data-stu-id="e0e5e-422">**DATE**</span></span> <br/> |<span data-ttu-id="e0e5e-423">예</span><span class="sxs-lookup"><span data-stu-id="e0e5e-423">Yes</span></span>  <br/> |<span data-ttu-id="e0e5e-424">항목이 처음으로 작성 되거나 고객 데이터 원본에 게시 된 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-424">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="e0e5e-425">예를 들어, Twitter 메시지가 tweeted 된 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-425">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="e0e5e-426">**보내기**</span><span class="sxs-lookup"><span data-stu-id="e0e5e-426">**BODY**</span></span> <br/> |<span data-ttu-id="e0e5e-427">아니요</span><span class="sxs-lookup"><span data-stu-id="e0e5e-427">No</span></span>  <br/> |<span data-ttu-id="e0e5e-428">메시지 또는 게시물의 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-428">The contents of the message or post.</span></span> <span data-ttu-id="e0e5e-429">일부 데이터 원본의 경우 이 속성의 콘텐츠는 **SUBJECT** 속성의 콘텐츠와 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-429">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="e0e5e-430">가져오기 프로세스 중에 파트너 커넥터는 가능한 한 콘텐츠 원본에서 완전 한 충실도를 유지 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-430">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="e0e5e-431">가능한 경우 원본 항목의 본문에서 가져온 파일, 그래픽 또는 기타 콘텐츠가 이 속성에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-431">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="e0e5e-432">그렇지 않은 경우 원본 항목의 콘텐츠가 **ATTACHMENT** 속성에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-432">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="e0e5e-433">이 속성의 내용은 파트너 커넥터와 원본 플랫폼의 기능에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-433">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="e0e5e-434">**덧붙인**</span><span class="sxs-lookup"><span data-stu-id="e0e5e-434">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="e0e5e-435">아니요</span><span class="sxs-lookup"><span data-stu-id="e0e5e-435">No</span></span>  <br/> |<span data-ttu-id="e0e5e-436">데이터 원본의 항목 (예: Twitter 또는 인스턴트 메시징 대화에 있는 tweet)에 첨부 된 파일이 있거나 이미지를 포함 하는 경우, 파트너 연결에서는 먼저 **BODY** 속성에 첨부 파일을 포함 하 려 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-436">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="e0e5e-437">이것이 가능 하지 않으면 \* \* ATTACHMENT \* \* 속성에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-437">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="e0e5e-438">첨부 파일의 다른 예로는 Facebook의 좋아요, 콘텐츠 원본의 메타데이터, 메시지 또는 게시물에 대한 응답이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-438">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="e0e5e-439">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="e0e5e-439">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="e0e5e-440">예</span><span class="sxs-lookup"><span data-stu-id="e0e5e-440">Yes</span></span>  <br/> | <span data-ttu-id="e0e5e-441">파트너 커넥터가 만들어서 채우는 다중 값 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-441">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="e0e5e-442">이 속성의 형식은 `IPM.NOTE.Source.Event` 입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-442">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="e0e5e-443">(이 속성은로 시작 해야 합니다 `IPM.NOTE` .</span><span class="sxs-lookup"><span data-stu-id="e0e5e-443">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="e0e5e-444">이 형식은 메시지 클래스의 형식과 유사 `IPM.NOTE.X` 합니다. 이 속성에는 다음 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-444">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="e0e5e-445">`Source`: 타사 데이터 원본을 나타냅니다. 예: Twitter, Facebook 또는 BlackBerry를 예로 들 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-445">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="e0e5e-446">`Event`: 항목을 생성 한 타사 데이터 원본에서 수행한 작업의 유형을 나타냅니다. 예를 들어, Twitter에 있는 tweet 또는 Facebook의 게시물입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-446">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="e0e5e-447">이벤트는 데이터 원본에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-447">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="e0e5e-448">이 속성의 한 가지 목적은 항목이 시작된 데이터 원본이나 이벤트의 유형에 따라 특정 항목을 필터링하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-448">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="e0e5e-449">예를 들어 eDiscovery 검색에서 특정 사용자가 게시한 모든 트윗을 찾는 검색 쿼리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-449">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="e0e5e-450">Office 365에서 사서함에 항목을 성공적으로 가져오면 고유한 식별자가 HTTP 응답의 일부로 다시 발신자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-450">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="e0e5e-451">이 식별자는 `x-IngestionCorrelationID` 종단 간 항목 추적을 위해 파트너의 후속 문제 해결을 위해 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-451">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="e0e5e-452">파트너는 이 정보를 수집하고 적절하게 기록해두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-452">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="e0e5e-453">이 식별자를 나타내는 HTTP 응답의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-453">Here's an example of an HTTP response showing this identifier:</span></span>

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- <span data-ttu-id="e0e5e-454">보안 및 준수 센터의 콘텐츠 검색 도구를 사용 하 여 타사 데이터 원본에서 사서함으로 가져온 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-454">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes from a third-party data source.</span></span> <span data-ttu-id="e0e5e-455">이러한 가져온 항목을 구체적으로 검색 하려면 콘텐츠 검색의 키워드 상자에 다음과 같은 메시지 속성-값 쌍을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-455">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="e0e5e-456">**`kind:externaldata`**:이 속성-값 쌍을 사용 하 여 모든 타사 데이터 형식을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-456">**`kind:externaldata`**: Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="e0e5e-457">예를 들어 타사 데이터 원본에서 가져온 항목과 가져온 항목의 Subject 속성에 "contoso" 라는 단어가 포함 된 항목을 검색 하려면 keyword 쿼리를 사용 `kind:externaldata AND subject:contoso` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-457">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="e0e5e-458">**`itemclass:ipm.externaldata.<third-party data type>`**:이 속성-값 쌍을 사용 하 여 지정 된 타사 데이터 형식만 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-458">**`itemclass:ipm.externaldata.<third-party data type>`**: Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="e0e5e-459">예를 들어 Subject 속성에서 "contoso" 라는 단어가 포함 된 Facebook 데이터만 검색 하려면 keyword 쿼리를 사용 `itemclass:ipm.externaldata.Facebook* AND subject:contoso` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-459">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="e0e5e-460">속성의 타사 데이터 형식에 사용할 값의 전체 목록은 `itemclass` [Office 365로 가져온 타사 데이터를 검색 하려면 사용 콘텐츠 검색](use-content-search-to-search-third-party-data-that-was-imported.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-460">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span></span>
    
   <span data-ttu-id="e0e5e-461">콘텐츠 검색 사용 및 키워드 검색 쿼리를 만드는 방법에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0e5e-461">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="e0e5e-462">Office 365의 콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="e0e5e-462">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="e0e5e-463">콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건</span><span class="sxs-lookup"><span data-stu-id="e0e5e-463">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 
