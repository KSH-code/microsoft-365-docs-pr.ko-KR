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
description: Salesforce Chatter, Yahoo Messenger 또는 Yammer.
ms.openlocfilehash: 2026e3c584cb0bc467a2db3903c51b7ed50e51e1
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228762"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a><span data-ttu-id="ebc59-103">타사 데이터를 저장하는 데 파트너와 협력</span><span class="sxs-lookup"><span data-stu-id="ebc59-103">Work with a partner to archive third-party data</span></span>

<span data-ttu-id="ebc59-104">Microsoft 파트너와 협력하여 타사 데이터 원본에서 데이터 원본으로 데이터를 가져와 보관할 수 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebc59-104">You can work with a Microsoft Partner to import and archive data from a third-party data source to Microsoft 365.</span></span> <span data-ttu-id="ebc59-105">파트너는 타사 데이터 원본에서 항목을 추출하여 정기적으로 해당 항목을 가져오도록 구성된 사용자 지정 커넥터를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-105">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items.</span></span> <span data-ttu-id="ebc59-106">파트너 커넥터는 데이터 원본에서 전자 메일 메시지 형식으로 항목의 내용을 변환한 다음 사서함에 항목을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-106">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes.</span></span> <span data-ttu-id="ebc59-107">타사 데이터를 가져온 후 소송 보존Microsoft 365 eDiscovery, In-Place 보관, 감사 및 보존 정책과 같은 Microsoft 365 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-107">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, and Microsoft 365 retention policies to this data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebc59-108">이 [문서의](communication-compliance.md) 통신 준수 Microsoft 365 파트너 커넥터가 가져온 타사 데이터에는 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-108">The [Communication compliance](communication-compliance.md) solution in Microsoft 365 can't be applied to the third-party data imported by partner connectors mentioned in this article.</span></span>

<span data-ttu-id="ebc59-109">다음은 타사 데이터를 가져오기 위해 Microsoft 파트너와 협력하는 데 필요한 프로세스 및 단계에 대한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-109">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data.</span></span>

[<span data-ttu-id="ebc59-110">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="ebc59-110">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="ebc59-111">2단계: 타사 데이터 사서함 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="ebc59-111">Step 2: Create and configure a third-party data mailbox</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365)

[<span data-ttu-id="ebc59-112">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="ebc59-112">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="ebc59-113">4단계: 파트너에게 정보 제공</span><span class="sxs-lookup"><span data-stu-id="ebc59-113">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="ebc59-114">5단계: 타사 데이터 커넥터를 등록합니다Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ebc59-114">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="ebc59-115">타사 데이터 가져오기 프로세스의 작동 방식</span><span class="sxs-lookup"><span data-stu-id="ebc59-115">How the third-party data import process works</span></span>

<span data-ttu-id="ebc59-116">다음 그림 및 설명은 파트너와 함께 작업할 때 타사 데이터 가져오기 프로세스가 작동하는 방식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-116">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>

![타사 데이터 가져오기 프로세스의 작동 방식](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)

1. <span data-ttu-id="ebc59-118">고객은 선택한 파트너와 협력하여 타사 데이터 원본에서 항목을 추출한 다음 해당 항목을 가져오는 커넥터를 구성하여 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebc59-118">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Microsoft 365.</span></span>

2. <span data-ttu-id="ebc59-119">파트너 커넥터는 타사 API(예약 또는 구성에 따라)를 통해 타사 데이터 원본에 연결하고 데이터 원본에서 항목을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-119">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="ebc59-120">파트너 커넥터는 항목의 내용을 전자 메일 메시지 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-120">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="ebc59-121">메시지 형식에 [대한 설명은 추가](#more-information) 정보 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ebc59-121">See the [More information](#more-information) section for a description of the message-format schema.</span></span>

3. <span data-ttu-id="ebc59-122">파트너 커넥터는 잘 알려진 끝점을 통해 Microsoft 365 EWS(Exchange 웹 서비스)를 사용하여 Exchange Azure 서비스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-122">Partner connector connects to the Azure service in Microsoft 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>

4. <span data-ttu-id="ebc59-p103">항목은 특정 사용자의 사서함 또는 "범용" 타사 데이터 사서함으로 가져오기됩니다. 항목을 특정 사용자 사서함으로 가져올지 또는 타사 데이터 사서함으로 가져올지는 다음 기준을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-p103">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>

   1. <span data-ttu-id="ebc59-125">사용자 계정에 해당하는 사용자 ID가 있는 **항목:** 파트너 커넥터가 타사 데이터 원본에 있는 항목의 사용자 ID를 Microsoft 365 사용자의 복구 가능한 항목 폴더에 있는 제거  폴더에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-125">**Items that have a user ID that corresponds to a user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Microsoft 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="ebc59-126">제거 폴더의 항목에는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-126">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="ebc59-127">그러나 eDiscovery 도구를 사용하여 제거 폴더의 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-127">However, you can use eDiscovery tools to search for items in the Purges folder.</span></span>

   1. <span data-ttu-id="ebc59-128">사용자 계정에 해당하는 사용자 ID가 없는 **항목:** 파트너 커넥터에서 항목의 사용자 ID를 특정 사용자 ID에 매핑할 수 없는 경우  항목이 타사 데이터 사서함의 받은 편지함 폴더에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-128">**Items that don't have a user ID that corresponds to a user account:** If the partner connector can't map the user ID of an item to a specific user ID, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="ebc59-129">받은 편지함에 항목을 가져올 수 있으면 관리자 또는 조직의 누군가가 타사 사서함에 로그인하여 이러한 항목을 보고 관리할 수 있으며 파트너 커넥터 구성을 조정해야 하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-129">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>

## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="ebc59-130">1단계: 타사 데이터 파트너 찾기</span><span class="sxs-lookup"><span data-stu-id="ebc59-130">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="ebc59-131">타사 데이터를 보관하는 주요 구성 요소는 Microsoft 365 데이터 원본에서 데이터를 캡처하여 데이터 원본으로 가져오는 전문 Microsoft 파트너를 찾아서 작업하는 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebc59-131">A key component for archiving third-party data in Microsoft 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Microsoft 365.</span></span> <span data-ttu-id="ebc59-132">데이터를 가져온 후 조직의 다른 Microsoft 데이터(예: 조직의 다른 Microsoft 데이터와 함께 보관 및 보존할 수 Exchange 및 SharePoint 및 문서)비즈니스용 OneDrive.</span><span class="sxs-lookup"><span data-stu-id="ebc59-132">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="ebc59-133">파트너는 조직의 타사 데이터 원본(예: BlackBerry, Facebook, Google+, Thomson Reuters, Twitter 및 YouTube)에서 데이터를 추출하고 해당 데이터를 전자 메일 메시지로 Exchange 사서함으로 가져오는 Microsoft 365 API에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-133">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to a Microsoft 365 API that imports items to Exchange mailboxes as email messages.</span></span>

<span data-ttu-id="ebc59-134">다음 섹션에서는 타사 데이터를 보관하기 위한 프로그램에 참여하는 Microsoft 파트너(및 해당 파트너가 지원하는 타사 데이터 원본)를 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebc59-134">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Microsoft 365.</span></span>

[<span data-ttu-id="ebc59-135">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="ebc59-135">17a-4 LLC</span></span>](#17a-4-llc)

[<span data-ttu-id="ebc59-136">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="ebc59-136">ArchiveSocial</span></span>](#archivesocial)

[<span data-ttu-id="ebc59-137">Veritas</span><span class="sxs-lookup"><span data-stu-id="ebc59-137">Veritas</span></span>](#veritas)

[<span data-ttu-id="ebc59-138">OpenText</span><span class="sxs-lookup"><span data-stu-id="ebc59-138">OpenText</span></span>](#opentext)

[<span data-ttu-id="ebc59-139">Smarsh</span><span class="sxs-lookup"><span data-stu-id="ebc59-139">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="ebc59-140">Verba</span><span class="sxs-lookup"><span data-stu-id="ebc59-140">Verba</span></span>](#verba)

### <a name="17a-4-llc"></a><span data-ttu-id="ebc59-141">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="ebc59-141">17a-4 LLC</span></span>

<span data-ttu-id="ebc59-142">[17a-4 LLC는](https://www.17a-4.com) 다음과 같은 타사 데이터 원본을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-142">[17a-4 LLC](https://www.17a-4.com) supports the following third-party data sources:</span></span>

- <span data-ttu-id="ebc59-143">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="ebc59-143">BlackBerry</span></span>

- <span data-ttu-id="ebc59-144">Bloomberg Data Streams</span><span class="sxs-lookup"><span data-stu-id="ebc59-144">Bloomberg Data Streams</span></span>

- <span data-ttu-id="ebc59-145">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="ebc59-145">Cisco Jabber</span></span>

- <span data-ttu-id="ebc59-146">FactSet</span><span class="sxs-lookup"><span data-stu-id="ebc59-146">FactSet</span></span>

- <span data-ttu-id="ebc59-147">HipChat</span><span class="sxs-lookup"><span data-stu-id="ebc59-147">HipChat</span></span>

- <span data-ttu-id="ebc59-148">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="ebc59-148">InvestEdge</span></span>

- <span data-ttu-id="ebc59-149">LivePerson</span><span class="sxs-lookup"><span data-stu-id="ebc59-149">LivePerson</span></span>

- <span data-ttu-id="ebc59-150">MessageLabs Data Streams</span><span class="sxs-lookup"><span data-stu-id="ebc59-150">MessageLabs Data Streams</span></span>

- <span data-ttu-id="ebc59-151">OpenText</span><span class="sxs-lookup"><span data-stu-id="ebc59-151">OpenText</span></span>

- <span data-ttu-id="ebc59-152">Oracle/ATG 'click-to-call' Live Help</span><span class="sxs-lookup"><span data-stu-id="ebc59-152">Oracle/ATG 'click-to-call' Live Help</span></span>

- <span data-ttu-id="ebc59-153">Pivot IMTRADER</span><span class="sxs-lookup"><span data-stu-id="ebc59-153">Pivot IMTRADER</span></span>

- <span data-ttu-id="ebc59-154">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="ebc59-154">Microsoft SharePoint</span></span>

- <span data-ttu-id="ebc59-155">MindAlign</span><span class="sxs-lookup"><span data-stu-id="ebc59-155">MindAlign</span></span>

- <span data-ttu-id="ebc59-156">Sitrion One(Newsgator)</span><span class="sxs-lookup"><span data-stu-id="ebc59-156">Sitrion One (Newsgator)</span></span>

- <span data-ttu-id="ebc59-157">비즈니스용 Skype(Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="ebc59-157">Skype for Business (Lync/OCS)</span></span>

- <span data-ttu-id="ebc59-158">비즈니스용 Skype Online(Lync Online)</span><span class="sxs-lookup"><span data-stu-id="ebc59-158">Skype for Business Online (Lync Online)</span></span>

- <span data-ttu-id="ebc59-159">SQL 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="ebc59-159">SQL Databases</span></span>

- <span data-ttu-id="ebc59-160">스쿼워커</span><span class="sxs-lookup"><span data-stu-id="ebc59-160">Squawker</span></span>

- <span data-ttu-id="ebc59-161">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="ebc59-161">Thomson Reuters Eikon Messenger</span></span>

### <a name="archivesocial"></a><span data-ttu-id="ebc59-162">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="ebc59-162">ArchiveSocial</span></span>

<span data-ttu-id="ebc59-163">[ArchiveSocial은](https://www.archivesocial.com) 다음과 같은 타사 데이터 원본을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-163">[ArchiveSocial](https://www.archivesocial.com) supports the following third-party data sources:</span></span>

- <span data-ttu-id="ebc59-164">Facebook</span><span class="sxs-lookup"><span data-stu-id="ebc59-164">Facebook</span></span>

- <span data-ttu-id="ebc59-165">Flickr</span><span class="sxs-lookup"><span data-stu-id="ebc59-165">Flickr</span></span>

- <span data-ttu-id="ebc59-166">인스 타마</span><span class="sxs-lookup"><span data-stu-id="ebc59-166">Instagram</span></span>

- <span data-ttu-id="ebc59-167">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="ebc59-167">LinkedIn</span></span>

- <span data-ttu-id="ebc59-168">Pinterest</span><span class="sxs-lookup"><span data-stu-id="ebc59-168">Pinterest</span></span>

- <span data-ttu-id="ebc59-169">Twitter</span><span class="sxs-lookup"><span data-stu-id="ebc59-169">Twitter</span></span>

- <span data-ttu-id="ebc59-170">YouTube</span><span class="sxs-lookup"><span data-stu-id="ebc59-170">YouTube</span></span>

- <span data-ttu-id="ebc59-171">Vimeo</span><span class="sxs-lookup"><span data-stu-id="ebc59-171">Vimeo</span></span>

### <a name="veritas"></a><span data-ttu-id="ebc59-172">Veritas</span><span class="sxs-lookup"><span data-stu-id="ebc59-172">Veritas</span></span>

<span data-ttu-id="ebc59-173">[Veritas는](https://www.globanet.com) 다음과 같은 타사 데이터 원본을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-173">[Veritas](https://www.globanet.com) supports the following third-party data sources:</span></span>

- <span data-ttu-id="ebc59-174">AOL with Pivot Client </span><span class="sxs-lookup"><span data-stu-id="ebc59-174">AOL with Pivot Client</span></span>

- <span data-ttu-id="ebc59-175">BlackBerry Call Logs(v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ebc59-175">BlackBerry Call Logs (v5, v10, v12)</span></span>

- <span data-ttu-id="ebc59-176">BlackBerry Messenger(v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ebc59-176">BlackBerry Messenger (v5, v10, v12)</span></span>

- <span data-ttu-id="ebc59-177">BlackBerry PIN(v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ebc59-177">BlackBerry PIN (v5, v10, v12)</span></span>

- <span data-ttu-id="ebc59-178">BlackBerry SMS(v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ebc59-178">BlackBerry SMS (v5, v10, v12)</span></span>

- <span data-ttu-id="ebc59-179">Bloomberg Chat</span><span class="sxs-lookup"><span data-stu-id="ebc59-179">Bloomberg Chat</span></span>

- <span data-ttu-id="ebc59-180">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="ebc59-180">Bloomberg Mail</span></span>

- <span data-ttu-id="ebc59-181">Box</span><span class="sxs-lookup"><span data-stu-id="ebc59-181">Box</span></span>

- <span data-ttu-id="ebc59-182">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="ebc59-182">CipherCloud for Salesforce Chatter</span></span>

- <span data-ttu-id="ebc59-183">Cisco IM &amp; Presence Server(v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span><span class="sxs-lookup"><span data-stu-id="ebc59-183">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="ebc59-184">Cisco Webex Teams</span><span class="sxs-lookup"><span data-stu-id="ebc59-184">Cisco Webex Teams</span></span>

- <span data-ttu-id="ebc59-185">Citrix Workspace &amp; ShareFile</span><span class="sxs-lookup"><span data-stu-id="ebc59-185">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="ebc59-186">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="ebc59-186">CrowdCompass</span></span>

- <span data-ttu-id="ebc59-187">사용자 지정으로분할된 텍스트 파일</span><span class="sxs-lookup"><span data-stu-id="ebc59-187">Custom-delimited text files</span></span>

- <span data-ttu-id="ebc59-188">사용자 지정 XML 파일</span><span class="sxs-lookup"><span data-stu-id="ebc59-188">Custom XML files</span></span>

- <span data-ttu-id="ebc59-189">Facebook(Pages)</span><span class="sxs-lookup"><span data-stu-id="ebc59-189">Facebook (Pages)</span></span>

- <span data-ttu-id="ebc59-190">팩트 집합</span><span class="sxs-lookup"><span data-stu-id="ebc59-190">Factset</span></span>

- <span data-ttu-id="ebc59-191">FXConnect</span><span class="sxs-lookup"><span data-stu-id="ebc59-191">FXConnect</span></span>

- <span data-ttu-id="ebc59-192">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="ebc59-192">ICE Chat/YellowJacket</span></span>

- <span data-ttu-id="ebc59-193">Jive</span><span class="sxs-lookup"><span data-stu-id="ebc59-193">Jive</span></span>

- <span data-ttu-id="ebc59-194">Macgregor XIP</span><span class="sxs-lookup"><span data-stu-id="ebc59-194">Macgregor XIP</span></span>

- <span data-ttu-id="ebc59-195">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ebc59-195">Microsoft Exchange Server</span></span>

- <span data-ttu-id="ebc59-196">Microsoft 비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="ebc59-196">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="ebc59-197">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ebc59-197">Microsoft Teams</span></span>

- <span data-ttu-id="ebc59-198">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="ebc59-198">Microsoft Yammer</span></span>

- <span data-ttu-id="ebc59-199">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="ebc59-199">Mobile Guard</span></span>

- <span data-ttu-id="ebc59-200">Pivot</span><span class="sxs-lookup"><span data-stu-id="ebc59-200">Pivot</span></span>

- <span data-ttu-id="ebc59-201">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="ebc59-201">Salesforce Chatter</span></span>

- <span data-ttu-id="ebc59-202">비즈니스용 Skype Online</span><span class="sxs-lookup"><span data-stu-id="ebc59-202">Skype for Business Online</span></span>

- <span data-ttu-id="ebc59-203">비즈니스용 Skype, 버전 2007 R2 - 2016(온-프레미스)</span><span class="sxs-lookup"><span data-stu-id="ebc59-203">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>

- <span data-ttu-id="ebc59-204">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="ebc59-204">Slack Enterprise Grid</span></span>

- <span data-ttu-id="ebc59-205">Symphony</span><span class="sxs-lookup"><span data-stu-id="ebc59-205">Symphony</span></span>

- <span data-ttu-id="ebc59-206">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="ebc59-206">Thomson Reuters Eikon</span></span>

- <span data-ttu-id="ebc59-207">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="ebc59-207">Thomson Reuters Messenger</span></span>

- <span data-ttu-id="ebc59-208">Thomson Reuters Dealings 3000 / FX Trading</span><span class="sxs-lookup"><span data-stu-id="ebc59-208">Thomson Reuters Dealings 3000 / FX Trading</span></span>

- <span data-ttu-id="ebc59-209">Twitter</span><span class="sxs-lookup"><span data-stu-id="ebc59-209">Twitter</span></span>

- <span data-ttu-id="ebc59-210">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="ebc59-210">UBS Chat</span></span>

- <span data-ttu-id="ebc59-211">YouTube</span><span class="sxs-lookup"><span data-stu-id="ebc59-211">YouTube</span></span>

### <a name="opentext"></a><span data-ttu-id="ebc59-212">OpenText</span><span class="sxs-lookup"><span data-stu-id="ebc59-212">OpenText</span></span>

<span data-ttu-id="ebc59-213">[OpenText는](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) 다음과 같은 타사 데이터 원본을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-213">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span>

- <span data-ttu-id="ebc59-214">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="ebc59-214">Axs Encrypted</span></span>

- <span data-ttu-id="ebc59-215">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="ebc59-215">Axs Exchange</span></span>

- <span data-ttu-id="ebc59-216">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="ebc59-216">Axs Local Archive</span></span>

- <span data-ttu-id="ebc59-217">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="ebc59-217">Axs PlaceHolder</span></span>

- <span data-ttu-id="ebc59-218">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="ebc59-218">Axs Signed</span></span>

- <span data-ttu-id="ebc59-219">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="ebc59-219">Bloomberg</span></span>

- <span data-ttu-id="ebc59-220">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="ebc59-220">Thomson Reuters</span></span>

### <a name="smarsh"></a><span data-ttu-id="ebc59-221">Smarsh</span><span class="sxs-lookup"><span data-stu-id="ebc59-221">Smarsh</span></span>

<span data-ttu-id="ebc59-222">[Smarsh는](https://www.smarsh.com) 다음과 같은 타사 데이터 원본을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-222">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span>

- <span data-ttu-id="ebc59-223">AIM</span><span class="sxs-lookup"><span data-stu-id="ebc59-223">AIM</span></span>

- <span data-ttu-id="ebc59-224">American Idol</span><span class="sxs-lookup"><span data-stu-id="ebc59-224">American Idol</span></span>

- <span data-ttu-id="ebc59-225">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="ebc59-225">Apple Juice</span></span>

- <span data-ttu-id="ebc59-226">AOL with Pivot client</span><span class="sxs-lookup"><span data-stu-id="ebc59-226">AOL with Pivot client</span></span>

- <span data-ttu-id="ebc59-227">Ares</span><span class="sxs-lookup"><span data-stu-id="ebc59-227">Ares</span></span>

- <span data-ttu-id="ebc59-228">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="ebc59-228">Bazaar Voice</span></span>

- <span data-ttu-id="ebc59-229">Bear Share</span><span class="sxs-lookup"><span data-stu-id="ebc59-229">Bear Share</span></span>

- <span data-ttu-id="ebc59-230">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="ebc59-230">Bit Torrent</span></span>

- <span data-ttu-id="ebc59-231">BlackBerry Call Logs(v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ebc59-231">BlackBerry Call Logs (v5, v10, v12)</span></span>

- <span data-ttu-id="ebc59-232">BlackBerry Messenger(v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ebc59-232">BlackBerry Messenger (v5, v10, v12)</span></span>

- <span data-ttu-id="ebc59-233">BlackBerry PIN(v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ebc59-233">BlackBerry PIN (v5, v10, v12)</span></span>

- <span data-ttu-id="ebc59-234">BlackBerry SMS(v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ebc59-234">BlackBerry SMS (v5, v10, v12)</span></span>

- <span data-ttu-id="ebc59-235">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="ebc59-235">Bloomberg Mail</span></span>

- <span data-ttu-id="ebc59-236">CellTrust</span><span class="sxs-lookup"><span data-stu-id="ebc59-236">CellTrust</span></span>

- <span data-ttu-id="ebc59-237">Chat Import</span><span class="sxs-lookup"><span data-stu-id="ebc59-237">Chat Import</span></span>

- <span data-ttu-id="ebc59-238">Chat Real Time Logging and Policy</span><span class="sxs-lookup"><span data-stu-id="ebc59-238">Chat Real Time Logging and Policy</span></span>

- <span data-ttu-id="ebc59-239">Chatter</span><span class="sxs-lookup"><span data-stu-id="ebc59-239">Chatter</span></span>

- <span data-ttu-id="ebc59-240">Cisco IM &amp; Presence Server(v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="ebc59-240">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>

- <span data-ttu-id="ebc59-241">Cisco Unified Presence Server(v8.6.3, v8.6.4, v8.6.5)</span><span class="sxs-lookup"><span data-stu-id="ebc59-241">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>

- <span data-ttu-id="ebc59-242">Collaboration Import</span><span class="sxs-lookup"><span data-stu-id="ebc59-242">Collaboration Import</span></span>

- <span data-ttu-id="ebc59-243">Collaboration Real Time Logging</span><span class="sxs-lookup"><span data-stu-id="ebc59-243">Collaboration Real Time Logging</span></span>

- <span data-ttu-id="ebc59-244">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="ebc59-244">Direct Connect</span></span>

- <span data-ttu-id="ebc59-245">Facebook</span><span class="sxs-lookup"><span data-stu-id="ebc59-245">Facebook</span></span>

- <span data-ttu-id="ebc59-246">FactSet</span><span class="sxs-lookup"><span data-stu-id="ebc59-246">FactSet</span></span>

- <span data-ttu-id="ebc59-247">FastTrack</span><span class="sxs-lookup"><span data-stu-id="ebc59-247">FastTrack</span></span>

- <span data-ttu-id="ebc59-248">Gnutella</span><span class="sxs-lookup"><span data-stu-id="ebc59-248">Gnutella</span></span>

- <span data-ttu-id="ebc59-249">Google+</span><span class="sxs-lookup"><span data-stu-id="ebc59-249">Google+</span></span>

- <span data-ttu-id="ebc59-250">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="ebc59-250">GoToMyPC</span></span>

- <span data-ttu-id="ebc59-251">Hopster</span><span class="sxs-lookup"><span data-stu-id="ebc59-251">Hopster</span></span>

- <span data-ttu-id="ebc59-252">HubConnex</span><span class="sxs-lookup"><span data-stu-id="ebc59-252">HubConnex</span></span>

- <span data-ttu-id="ebc59-253">IBM Connections(v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span><span class="sxs-lookup"><span data-stu-id="ebc59-253">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>

- <span data-ttu-id="ebc59-254">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="ebc59-254">IBM Connections Chat Cloud</span></span>

- <span data-ttu-id="ebc59-255">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="ebc59-255">IBM Connections Social Cloud</span></span>

- <span data-ttu-id="ebc59-256">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="ebc59-256">IBM SameTime Advanced 8.5.2 IFR1</span></span>

- <span data-ttu-id="ebc59-257">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="ebc59-257">IBM SameTime Communicate 9.0</span></span>

- <span data-ttu-id="ebc59-258">IBM SameTime Community(v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span><span class="sxs-lookup"><span data-stu-id="ebc59-258">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>

- <span data-ttu-id="ebc59-259">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="ebc59-259">IBM SameTime Complete 9.0</span></span>

- <span data-ttu-id="ebc59-260">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="ebc59-260">IBM SameTime Conference 9.0</span></span>

- <span data-ttu-id="ebc59-261">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="ebc59-261">IBM SameTime Meeting 8.5.2 IFR1</span></span>

- <span data-ttu-id="ebc59-262">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="ebc59-262">ICE/YellowJacket</span></span>

- <span data-ttu-id="ebc59-263">IM Import</span><span class="sxs-lookup"><span data-stu-id="ebc59-263">IM Import</span></span>

- <span data-ttu-id="ebc59-264">IM Real Time Logging and Policy</span><span class="sxs-lookup"><span data-stu-id="ebc59-264">IM Real Time Logging and Policy</span></span>

- <span data-ttu-id="ebc59-265">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="ebc59-265">Indii Messenger</span></span>

- <span data-ttu-id="ebc59-266">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="ebc59-266">Instant Bloomberg</span></span>

- <span data-ttu-id="ebc59-267">IRC</span><span class="sxs-lookup"><span data-stu-id="ebc59-267">IRC</span></span>

- <span data-ttu-id="ebc59-268">Jive</span><span class="sxs-lookup"><span data-stu-id="ebc59-268">Jive</span></span>

- <span data-ttu-id="ebc59-269">Jive 6 Real Time Logging(v6, v7)</span><span class="sxs-lookup"><span data-stu-id="ebc59-269">Jive 6 Real Time Logging (v6, v7)</span></span>

- <span data-ttu-id="ebc59-270">Jive Import</span><span class="sxs-lookup"><span data-stu-id="ebc59-270">Jive Import</span></span>

- <span data-ttu-id="ebc59-271">JXTA</span><span class="sxs-lookup"><span data-stu-id="ebc59-271">JXTA</span></span>

- <span data-ttu-id="ebc59-272">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="ebc59-272">LinkedIn</span></span>

- <span data-ttu-id="ebc59-273">Microsoft Lync(2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="ebc59-273">Microsoft Lync (2010, 2013)</span></span>

- <span data-ttu-id="ebc59-274">MFTP</span><span class="sxs-lookup"><span data-stu-id="ebc59-274">MFTP</span></span>

- <span data-ttu-id="ebc59-275">Microsoft Lync 2013 Voice</span><span class="sxs-lookup"><span data-stu-id="ebc59-275">Microsoft Lync 2013 Voice</span></span>

- <span data-ttu-id="ebc59-276">Microsoft SharePoint(2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="ebc59-276">Microsoft SharePoint (2010, 2013)</span></span>

- <span data-ttu-id="ebc59-277">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ebc59-277">Microsoft SharePoint Online</span></span>

- <span data-ttu-id="ebc59-278">Microsoft UC(Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="ebc59-278">Microsoft UC (Unified Communications)</span></span>

- <span data-ttu-id="ebc59-279">MindAlign</span><span class="sxs-lookup"><span data-stu-id="ebc59-279">MindAlign</span></span>

- <span data-ttu-id="ebc59-280">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="ebc59-280">Mobile Guard</span></span>

- <span data-ttu-id="ebc59-281">MSN</span><span class="sxs-lookup"><span data-stu-id="ebc59-281">MSN</span></span>

- <span data-ttu-id="ebc59-282">My Space</span><span class="sxs-lookup"><span data-stu-id="ebc59-282">My Space</span></span>

- <span data-ttu-id="ebc59-283">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="ebc59-283">NEONetwork</span></span>

- <span data-ttu-id="ebc59-284">Microsoft 365 Lync 전용</span><span class="sxs-lookup"><span data-stu-id="ebc59-284">Microsoft 365 Lync Dedicated</span></span>

- <span data-ttu-id="ebc59-285">Microsoft 365 공유 IM</span><span class="sxs-lookup"><span data-stu-id="ebc59-285">Microsoft 365 Shared IM</span></span>

- <span data-ttu-id="ebc59-286">Pinterest</span><span class="sxs-lookup"><span data-stu-id="ebc59-286">Pinterest</span></span>

- <span data-ttu-id="ebc59-287">Pivot</span><span class="sxs-lookup"><span data-stu-id="ebc59-287">Pivot</span></span>

- <span data-ttu-id="ebc59-288">QQ</span><span class="sxs-lookup"><span data-stu-id="ebc59-288">QQ</span></span>

- <span data-ttu-id="ebc59-289">비즈니스용 Skype 2015</span><span class="sxs-lookup"><span data-stu-id="ebc59-289">Skype for Business 2015</span></span>

- <span data-ttu-id="ebc59-290">SoftEther</span><span class="sxs-lookup"><span data-stu-id="ebc59-290">SoftEther</span></span>

- <span data-ttu-id="ebc59-291">Symphony</span><span class="sxs-lookup"><span data-stu-id="ebc59-291">Symphony</span></span>

- <span data-ttu-id="ebc59-292">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="ebc59-292">Thomson Reuters Eikon</span></span>

- <span data-ttu-id="ebc59-293">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="ebc59-293">Thomson Reuters Messenger</span></span>

- <span data-ttu-id="ebc59-294">Tor</span><span class="sxs-lookup"><span data-stu-id="ebc59-294">Tor</span></span>

- <span data-ttu-id="ebc59-295">TTT</span><span class="sxs-lookup"><span data-stu-id="ebc59-295">TTT</span></span>

- <span data-ttu-id="ebc59-296">Twitter</span><span class="sxs-lookup"><span data-stu-id="ebc59-296">Twitter</span></span>

- <span data-ttu-id="ebc59-297">WinMX</span><span class="sxs-lookup"><span data-stu-id="ebc59-297">WinMX</span></span>

- <span data-ttu-id="ebc59-298">Winny</span><span class="sxs-lookup"><span data-stu-id="ebc59-298">Winny</span></span>

- <span data-ttu-id="ebc59-299">Yahoo</span><span class="sxs-lookup"><span data-stu-id="ebc59-299">Yahoo</span></span>

- <span data-ttu-id="ebc59-300">Yammer</span><span class="sxs-lookup"><span data-stu-id="ebc59-300">Yammer</span></span>

- <span data-ttu-id="ebc59-301">YouTube</span><span class="sxs-lookup"><span data-stu-id="ebc59-301">YouTube</span></span>


### <a name="verba"></a><span data-ttu-id="ebc59-302">Verba</span><span class="sxs-lookup"><span data-stu-id="ebc59-302">Verba</span></span>

<span data-ttu-id="ebc59-303">[Verba는](https://www.verba.com) 다음과 같은 타사 데이터 원본을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-303">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span>

- <span data-ttu-id="ebc59-304">Avaya Aura Video</span><span class="sxs-lookup"><span data-stu-id="ebc59-304">Avaya Aura Video</span></span>

- <span data-ttu-id="ebc59-305">Avaya Aura Voice</span><span class="sxs-lookup"><span data-stu-id="ebc59-305">Avaya Aura Voice</span></span>

- <span data-ttu-id="ebc59-306">Avtec Radio</span><span class="sxs-lookup"><span data-stu-id="ebc59-306">Avtec Radio</span></span>

- <span data-ttu-id="ebc59-307">Bosch/Telex Radio</span><span class="sxs-lookup"><span data-stu-id="ebc59-307">Bosch/Telex Radio</span></span>

- <span data-ttu-id="ebc59-308">BroadSoft Video</span><span class="sxs-lookup"><span data-stu-id="ebc59-308">BroadSoft Video</span></span>

- <span data-ttu-id="ebc59-309">BroadSoft Voice</span><span class="sxs-lookup"><span data-stu-id="ebc59-309">BroadSoft Voice</span></span>

- <span data-ttu-id="ebc59-310">Centile Voice</span><span class="sxs-lookup"><span data-stu-id="ebc59-310">Centile Voice</span></span>

- <span data-ttu-id="ebc59-311">Cisco Jabber IM</span><span class="sxs-lookup"><span data-stu-id="ebc59-311">Cisco Jabber IM</span></span>

- <span data-ttu-id="ebc59-312">Cisco UC Video</span><span class="sxs-lookup"><span data-stu-id="ebc59-312">Cisco UC Video</span></span>

- <span data-ttu-id="ebc59-313">Cisco UC Voice</span><span class="sxs-lookup"><span data-stu-id="ebc59-313">Cisco UC Voice</span></span>

- <span data-ttu-id="ebc59-314">Cisco UCCX/UCCE 비디오</span><span class="sxs-lookup"><span data-stu-id="ebc59-314">Cisco UCCX/UCCE Video</span></span>

- <span data-ttu-id="ebc59-315">Cisco UCCX/UCCE Voice</span><span class="sxs-lookup"><span data-stu-id="ebc59-315">Cisco UCCX/UCCE Voice</span></span>

- <span data-ttu-id="ebc59-316">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="ebc59-316">ESChat Radio</span></span>

- <span data-ttu-id="ebc59-317">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="ebc59-317">Geoman Contact Expert</span></span>

- <span data-ttu-id="ebc59-318">IP Trade Voice</span><span class="sxs-lookup"><span data-stu-id="ebc59-318">IP Trade Voice</span></span>

- <span data-ttu-id="ebc59-319">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="ebc59-319">Luware LUCS Contact Center</span></span>

- <span data-ttu-id="ebc59-320">Microsoft UC(Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="ebc59-320">Microsoft UC (Unified Communications)</span></span>

- <span data-ttu-id="ebc59-321">Mitel MiContact Center for Lync(prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="ebc59-321">Mitel MiContact Center for Lync (prairieFyre)</span></span>

- <span data-ttu-id="ebc59-322">Oracle/Acme Packet Session Border Controller Video</span><span class="sxs-lookup"><span data-stu-id="ebc59-322">Oracle / Acme Packet Session Border Controller Video</span></span>

- <span data-ttu-id="ebc59-323">Oracle/Acme Packet Session Border Controller Voice</span><span class="sxs-lookup"><span data-stu-id="ebc59-323">Oracle / Acme Packet Session Border Controller Voice</span></span>

- <span data-ttu-id="ebc59-324">Singtel Mobile Voice</span><span class="sxs-lookup"><span data-stu-id="ebc59-324">Singtel Mobile Voice</span></span>

- <span data-ttu-id="ebc59-325">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="ebc59-325">SIPREC Video</span></span>

-  <span data-ttu-id="ebc59-326">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="ebc59-326">SIPREC Voice</span></span>

- <span data-ttu-id="ebc59-327">비즈니스용 Skype/Lync IM</span><span class="sxs-lookup"><span data-stu-id="ebc59-327">Skype for Business / Lync IM</span></span>

- <span data-ttu-id="ebc59-328">비즈니스용 Skype/Lync Video</span><span class="sxs-lookup"><span data-stu-id="ebc59-328">Skype for Business / Lync Video</span></span>

- <span data-ttu-id="ebc59-329">비즈니스용 Skype/Lync Voice</span><span class="sxs-lookup"><span data-stu-id="ebc59-329">Skype for Business / Lync Voice</span></span>

- <span data-ttu-id="ebc59-330">Speakerbus Voice</span><span class="sxs-lookup"><span data-stu-id="ebc59-330">Speakerbus Voice</span></span>

- <span data-ttu-id="ebc59-331">Standard SIP/H.323 Video</span><span class="sxs-lookup"><span data-stu-id="ebc59-331">Standard SIP/H.323 Video</span></span>

- <span data-ttu-id="ebc59-332">Standard SIP/H.323 Voice</span><span class="sxs-lookup"><span data-stu-id="ebc59-332">Standard SIP/H.323 Voice</span></span>

- <span data-ttu-id="ebc59-333">Truphone Voice</span><span class="sxs-lookup"><span data-stu-id="ebc59-333">Truphone Voice</span></span>

- <span data-ttu-id="ebc59-334">TwistedPair Radio</span><span class="sxs-lookup"><span data-stu-id="ebc59-334">TwistedPair Radio</span></span>

- <span data-ttu-id="ebc59-335">Windows 데스크톱 컴퓨터 화면</span><span class="sxs-lookup"><span data-stu-id="ebc59-335">Windows Desktop Computer Screen</span></span>

## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365"></a><span data-ttu-id="ebc59-336">2단계: 2단계: 2단계에서 타사 데이터 사서함 만들기 및 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ebc59-336">Step 2: Create and configure a third-party data mailbox in Microsoft 365</span></span>

<span data-ttu-id="ebc59-337">다음은 데이터 원본으로 데이터를 가져오기 위한 타사 데이터 사서함을 만들고 구성하는 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebc59-337">Here are the steps for creating and configuring a third-party data mailbox for importing data to Microsoft 365.</span></span> <span data-ttu-id="ebc59-338">앞서 설명한 것 처럼 파트너 커넥터에서 항목의 사용자 ID를 사용자 계정에 매핑할 수 없는 경우 항목이 이 사서함으로 가져오기됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-338">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to a user account.</span></span>

 <span data-ttu-id="ebc59-339">**다음 작업의 Microsoft 365 관리 센터**</span><span class="sxs-lookup"><span data-stu-id="ebc59-339">**Complete these tasks in the Microsoft 365 admin center**</span></span>

1. <span data-ttu-id="ebc59-340">사용자 계정을 만들고 계획 Exchange Online 라이선스를 할당합니다. 에 [사용자 추가를 Microsoft 365.](../admin/add-users/add-users.md)</span><span class="sxs-lookup"><span data-stu-id="ebc59-340">Create a user account and assign it an Exchange Online Plan 2 license; see [Add users to Microsoft 365](../admin/add-users/add-users.md).</span></span> <span data-ttu-id="ebc59-341">계획 2 라이선스는 사서함을 소송 자료 보관에 두거나 무제한 저장소 할당량인 보관 사서함을 사용하도록 설정하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-341">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>

2. <span data-ttu-id="ebc59-342">타사 데이터 사서함에 대한 사용자 계정을  Exchange 관리자 역할에 Microsoft 365. 에서 [관리자 역할 할당을 Microsoft 365.](../admin/add-users/assign-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="ebc59-342">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Microsoft 365; see [Assign admin roles in Microsoft 365](../admin/add-users/assign-admin-roles.md).</span></span>

    > [!TIP]
    > <span data-ttu-id="ebc59-p109">이 사용자 계정의 자격 증명을 기록해 둡니다. 4단계에서 설명한 것처럼 파트너에게 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-p109">Write down the credentials for this user account. You need to provide them to your partner, as described in Step 4.</span></span>

 <span data-ttu-id="ebc59-345">**Exchange 관리 센터에서 이러한 작업 완료**</span><span class="sxs-lookup"><span data-stu-id="ebc59-345">**Complete these tasks in the Exchange admin center**</span></span>

1. <span data-ttu-id="ebc59-346">조직의 주소 책 및 기타 주소 목록에서 타사 데이터 사서함을 숨기기 사용자 [사서함 관리를 참조합니다.](/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="ebc59-346">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes).</span></span> <span data-ttu-id="ebc59-347">또는 다음 PowerShell 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-347">Alternatively, you can run the following PowerShell command:</span></span>

    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="ebc59-348">관리자 **또는** 규정 준수 관리자가 타사 데스크톱 클라이언트에서 타사 데이터 사서함을 열 수 있도록 타사 데이터 Outlook 권한을 할당합니다. 받는 [사람에 대한 사용 권한 관리를 참조합니다.](https://go.microsoft.com/fwlink/p/?LinkId=692104)</span><span class="sxs-lookup"><span data-stu-id="ebc59-348">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>

3. <span data-ttu-id="ebc59-349">타사 데이터 사서함에 대해 다음 준수 관련 기능을 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebc59-349">Enable the following compliance-related features for the third-party data mailbox:</span></span>

    - <span data-ttu-id="ebc59-350">보관 사서함을 사용하도록 설정 보관 [사서함 사용 및](enable-archive-mailboxes.md) 무제한 보관 사용 [을 참조합니다.](enable-unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="ebc59-350">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="ebc59-351">이렇게 하면 타사 데이터 항목을 보관 사서함으로 이동하는 보관 정책을 설정하여 기본 사서함의 저장소 공간을 자유롭게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-351">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="ebc59-352">이렇게 하면 타사 데이터에 대한 무제한 저장소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-352">This provides you with unlimited storage for third-party data.</span></span>

    - <span data-ttu-id="ebc59-353">타사 데이터 사서함에 소송 보존을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-353">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="ebc59-354">보안 및 준수 센터에서 Microsoft 365 보존 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-354">You can also apply a Microsoft 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="ebc59-355">이 사서함을 보류하면 타사 데이터 항목이 보존되고(무기한 또는 지정된 기간 동안) 사서함에서 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-355">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="ebc59-356">다음 항목 중 하나를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ebc59-356">See one of the following topics:</span></span>

      - [<span data-ttu-id="ebc59-357">사서함을 소송 자료 보존으로 설정</span><span class="sxs-lookup"><span data-stu-id="ebc59-357">Place a mailbox on Litigation Hold</span></span>](./create-a-litigation-hold.md)

      - [<span data-ttu-id="ebc59-358">보존 정책 및 보존 레이블에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="ebc59-358">Learn about retention policies and retention labels</span></span>](retention.md)

    - <span data-ttu-id="ebc59-359">타사 데이터 사서함에 대한 소유자, 대리인 및 관리자 액세스에 대해 사서함 감사 로깅을 사용하도록 설정 사서함 [감사 사용 을 참조합니다.](enable-mailbox-auditing.md)</span><span class="sxs-lookup"><span data-stu-id="ebc59-359">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="ebc59-360">이렇게 하면 타사 데이터 사서함에 액세스할 수 있는 사용자가 수행한 모든 활동을 감사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-360">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="ebc59-361">3단계: 타사 데이터에 대한 사용자 사서함 구성</span><span class="sxs-lookup"><span data-stu-id="ebc59-361">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="ebc59-362">다음 단계는 타사 데이터를 지원하도록 사용자 사서함을 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-362">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="ebc59-363">Exchange 관리 센터 또는 해당 Windows PowerShell cmdlet을 사용하여 이러한 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-363">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>

1. <span data-ttu-id="ebc59-364">각 사용자에 대해 보관 사서함을 사용하도록 설정 보관 [사서함 사용 및](enable-archive-mailboxes.md) 무제한 보관 사용 [을 참조합니다.](enable-unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="ebc59-364">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>

2. <span data-ttu-id="ebc59-365">사용자 사서함에 소송 보존을 적용하거나 보존 Microsoft 365 적용합니다. 다음 항목 중 하나를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ebc59-365">Place user mailboxes on Litigation Hold or apply a Microsoft 365 retention policy; see one of the following topics:</span></span>

    - [<span data-ttu-id="ebc59-366">사서함을 소송 자료 보존으로 설정</span><span class="sxs-lookup"><span data-stu-id="ebc59-366">Place a mailbox on Litigation Hold</span></span>](./create-a-litigation-hold.md)

    - [<span data-ttu-id="ebc59-367">보존 정책 및 보존 레이블에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="ebc59-367">Learn about retention policies and retention labels</span></span>](retention.md)

    <span data-ttu-id="ebc59-368">앞서 언급한 것처럼 사서함을 보존하면 타사 데이터 원본의 항목을 보존하는 기간을 설정하거나 항목을 무기한 보존하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-368">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="ebc59-369">4단계: 파트너에게 정보 제공</span><span class="sxs-lookup"><span data-stu-id="ebc59-369">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="ebc59-370">마지막 단계는 파트너가 사용자 사서함 및 타사 데이터 사서함으로 데이터를 가져오도록 조직에 연결하도록 커넥터를 구성할 수 있도록 파트너에게 다음 정보를 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-370">The final step is to provide your partner with the following information so they can configure the connector to connect to your organization to import data to user mailboxes and to the third-party data mailbox.</span></span>

- <span data-ttu-id="ebc59-371">다음의 Azure 서비스에 연결하는 데 사용되는 끝점은 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebc59-371">The endpoint used to connect to the Azure service in Microsoft 365:</span></span>

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="ebc59-372">2단계에서 만든 타사 데이터 Microsoft 365 사서함의 로그인 자격 증명(사용자 ID 및 암호)입니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-372">The sign-in credentials (Microsoft 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="ebc59-373">이러한 자격 증명은 파트너 커넥터가 항목을 액세스하고 사용자 사서함 및 타사 데이터 사서함으로 가져올 수 있도록 하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-373">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>

## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="ebc59-374">5단계: 타사 데이터 커넥터를 등록합니다Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ebc59-374">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="ebc59-375">2018년 9월 30일부터 Microsoft 365 Azure 서비스는 Exchange Online 최신 인증을 사용하여 조직에 연결하여 데이터를 가져오는 타사 데이터 커넥터를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-375">Starting September 30, 2018, the Azure service in Microsoft 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your organization to import data.</span></span> <span data-ttu-id="ebc59-376">이러한 변경의 이유는 최신 인증이 Azure 서비스에 연결하기 위해 앞서 설명한 끝점을 사용하는 타사 커넥터에 대한 허용 목록을 기반으로 했던 현재 방법보다 더 많은 보안을 제공하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-376">The reason for this change is that modern authentication provides more security than the current method, which was based on an allow list for third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="ebc59-377">타사 데이터 커넥터가 새로운 최신 인증 방법을 사용하여 Microsoft 365 커넥터에 연결할 수 있도록 설정하려면 조직의 관리자가 커넥터를 해당 커넥터에 신뢰할 수 있는 서비스 응용 프로그램으로 등록하는 데 동의해야 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ebc59-377">To enable a third-party data connector to connect to Microsoft 365 using the new modern authentication method, an administrator in your organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="ebc59-378">이 수행은 커넥터가 조직의 데이터에 액세스할 수 있도록 허용하는 권한 요청을 수락하여 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ebc59-378">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="ebc59-379">이 요청을 수락하면 타사 데이터 커넥터가 엔터프라이즈 응용 프로그램으로 추가되어 서비스 Azure Active Directory 사용자로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-379">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="ebc59-380">동의 프로세스에 대한 자세한 내용은 테넌트 관리자 동의 [를 참조하세요.](/skype-sdk/trusted-application-api/docs/tenantadminconsent)</span><span class="sxs-lookup"><span data-stu-id="ebc59-380">For more information the consent process, see  [Tenant Admin Consent](/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="ebc59-381">커넥터 등록 요청을 액세스하고 수락하는 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-381">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="ebc59-382">이 [페이지로 이동하여](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) 전역 관리자의 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-382">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of a global administrator.</span></span>

   <span data-ttu-id="ebc59-383">다음 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-383">The following dialog box is displayed.</span></span> <span data-ttu-id="ebc59-384">캐터를 확장하여 커넥터에 할당할 사용 권한을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-384">You can expand the carets to review the permissions that will be assigned to the connector.</span></span>

   ![사용 권한 요청 대화 상자가 표시됩니다.](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. <span data-ttu-id="ebc59-386">**Accept(동의함)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-386">Click **Accept**.</span></span>

<span data-ttu-id="ebc59-387">요청을 수락하면 [Azure Portal이](https://portal.azure.com) 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-387">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="ebc59-388">조직의 응용 프로그램 목록을 보려면 응용 **프로그램 Azure Active Directory** Enterprise  >  **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ebc59-388">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="ebc59-389">타사 Microsoft 365 커넥터가 Enterprise **블레이드에 나열되어** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-389">The Microsoft 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebc59-390">2018년 9월 30일 이후에는 타사 데이터 커넥터를 조직에 등록하지 않은 경우 더 이상 타사 데이터를 조직의 사서함으로 가져오지 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ebc59-390">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="ebc59-391">참고 기존 타사 데이터 커넥터(2018년 9월 30일 전에 만든 커넥터)도 5단계의 절차를 수행하여 Azure Active Directory 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-391">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="ebc59-392">타사 데이터 커넥터에 대한 동의 해지</span><span class="sxs-lookup"><span data-stu-id="ebc59-392">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="ebc59-393">조직에서 타사 데이터 커넥터를 등록하기 위한 권한 요청에 동의하면 Azure Active Directory 해당 동의를 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-393">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="ebc59-394">그러나 커넥터에 대한 동의를 해지하면 타사 데이터 원본의 데이터를 더 이상 커넥터로 가져오지 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebc59-394">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Microsoft 365.</span></span>

<span data-ttu-id="ebc59-395">타사 데이터 커넥터에 대한 동의를 해지하려면 Azure Portal에서 Enterprise 응용 프로그램 블레이드를 사용하거나 Azure  Portal에서 [Remove-MsolServicePrincipal을](/powershell/module/msonline/remove-msolserviceprincipal) 사용하여 Azure Active Directory 서비스 계정을 삭제하여 응용 프로그램을 삭제할 수 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-395">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](/powershell/module/msonline/remove-msolserviceprincipal) in Microsoft 365 PowerShell.</span></span> <span data-ttu-id="ebc59-396">PowerShell에서 [Remove-AzureADServicePrincipal](/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet을 Azure Active Directory 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-396">You can also use the [Remove-AzureADServicePrincipal](/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>

## <a name="more-information"></a><span data-ttu-id="ebc59-397">추가 정보</span><span class="sxs-lookup"><span data-stu-id="ebc59-397">More information</span></span>

- <span data-ttu-id="ebc59-398">앞서 설명한 것처럼 타사 데이터 원본의 항목을 Exchange 사서함에 전자 메일 메시지로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-398">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="ebc59-399">파트너 커넥터는 파트너 API에 필요한 schema를 사용하여 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebc59-399">The partner connector imports the item using a schema required by the Microsoft 365 API.</span></span> <span data-ttu-id="ebc59-400">다음 표에서는 타사 데이터 원본 항목을 Exchange 사서함에 전자 메일 메시지로 가져온 후, 타사 데이터 원본 항목에 대한 메시지 속성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-400">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="ebc59-401">또한 이 표는 메시지 속성이 필수인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-401">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="ebc59-402">필수 속성은 채워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-402">Mandatory properties must be populated.</span></span> <span data-ttu-id="ebc59-403">필수 속성이 없는 항목은 해당 항목으로 가져오지 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebc59-403">If an item is missing a mandatory property, it won't be imported to Microsoft 365.</span></span> <span data-ttu-id="ebc59-404">가져오기 프로세스에서는 항목을 가져오지 않은 이유와 누락된 속성을 설명하는 오류 메시지가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-404">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span><br/><br/>

    |<span data-ttu-id="ebc59-405">**메시지 속성**</span><span class="sxs-lookup"><span data-stu-id="ebc59-405">**Message property**</span></span>|<span data-ttu-id="ebc59-406">**필수 여부**</span><span class="sxs-lookup"><span data-stu-id="ebc59-406">**Mandatory?**</span></span>|<span data-ttu-id="ebc59-407">**설명**</span><span class="sxs-lookup"><span data-stu-id="ebc59-407">**Description**</span></span>|<span data-ttu-id="ebc59-408">**예제 값**</span><span class="sxs-lookup"><span data-stu-id="ebc59-408">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ebc59-409">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="ebc59-409">**FROM**</span></span> <br/> |<span data-ttu-id="ebc59-410">예</span><span class="sxs-lookup"><span data-stu-id="ebc59-410">Yes</span></span>  <br/> |<span data-ttu-id="ebc59-411">타사 데이터 원본 항목을 처음 만들었거나 보낸 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-411">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="ebc59-412">파트너 커넥터는 원본 항목(예: Twitter 핸들)의 사용자 ID를 모든 참가자(FROM 및 TO 필드의 사용자)에 대한 사용자 계정에 매핑하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-412">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to a user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="ebc59-413">메시지 복사본을 모든 참가자의 사서함으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-413">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="ebc59-414">항목의 참가자 중 사용자 계정에 매핑할 수 없는 경우 항목은 해당 항목의 타사 보관 사서함으로 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebc59-414">If none of the participants from the item can be mapped to a user account, the item will be imported to the third-party archiving mailbox in Microsoft 365.</span></span>  <br/> <br/> <span data-ttu-id="ebc59-415">항목의 보낸 사람으로 식별된 참가자는 항목을 가져오는 조직에서 활성 사서함을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-415">The participant who's identified as the sender of the item must have an active mailbox in the organization that the item is being imported to.</span></span> <span data-ttu-id="ebc59-416">보낸 사람에게 활성 사서함이 없으면 다음과 같은 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-416">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="ebc59-417">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="ebc59-417">**TO**</span></span> <br/> |<span data-ttu-id="ebc59-418">예</span><span class="sxs-lookup"><span data-stu-id="ebc59-418">Yes</span></span>  <br/> |<span data-ttu-id="ebc59-419">데이터 원본의 항목을 받은 사람입니다(해당되는 경우).</span><span class="sxs-lookup"><span data-stu-id="ebc59-419">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="ebc59-420">**제목**</span><span class="sxs-lookup"><span data-stu-id="ebc59-420">**SUBJECT**</span></span> <br/> |<span data-ttu-id="ebc59-421">아니요</span><span class="sxs-lookup"><span data-stu-id="ebc59-421">No</span></span>  <br/> |<span data-ttu-id="ebc59-422">원본 항목의 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-422">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="ebc59-423">**DATE**</span><span class="sxs-lookup"><span data-stu-id="ebc59-423">**DATE**</span></span> <br/> |<span data-ttu-id="ebc59-424">예</span><span class="sxs-lookup"><span data-stu-id="ebc59-424">Yes</span></span>  <br/> |<span data-ttu-id="ebc59-425">항목을 처음 만들거나 고객 데이터 원본에 게시한 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-425">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="ebc59-426">예를 들어 Twitter 메시지가 트윗된 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-426">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="ebc59-427">**BODY**</span><span class="sxs-lookup"><span data-stu-id="ebc59-427">**BODY**</span></span> <br/> |<span data-ttu-id="ebc59-428">아니요</span><span class="sxs-lookup"><span data-stu-id="ebc59-428">No</span></span>  <br/> |<span data-ttu-id="ebc59-429">메시지 또는 게시물의 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-429">The contents of the message or post.</span></span> <span data-ttu-id="ebc59-430">일부 데이터 원본의 경우 이 속성의 콘텐츠는 **SUBJECT** 속성의 콘텐츠와 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-430">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="ebc59-431">가져오기 프로세스 중에 파트너 커넥터는 콘텐츠 원본에서 최대한 완전한 고화성을 유지하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-431">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="ebc59-432">가능한 경우 원본 항목의 본문에서 가져온 파일, 그래픽 또는 기타 콘텐츠가 이 속성에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-432">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="ebc59-433">그렇지 않은 경우 원본 항목의 콘텐츠가 **ATTACHMENT** 속성에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-433">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="ebc59-434">이 속성의 내용은 파트너 커넥터 및 원본 플랫폼의 기능에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-434">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="ebc59-435">**첨부 파일**</span><span class="sxs-lookup"><span data-stu-id="ebc59-435">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="ebc59-436">아니요</span><span class="sxs-lookup"><span data-stu-id="ebc59-436">No</span></span>  <br/> |<span data-ttu-id="ebc59-437">데이터 원본의 항목(예: Twitter의 트윗 또는 인스턴트 메시징 대화)에 첨부 파일이 첨부되거나 이미지가 포함된 경우 파트너 연결은 먼저 **BODY** 속성에 첨부 파일을 포함하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-437">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="ebc59-438">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span><span class="sxs-lookup"><span data-stu-id="ebc59-438">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="ebc59-439">첨부 파일의 다른 예로는 Facebook의 좋아요, 콘텐츠 원본의 메타데이터, 메시지 또는 게시물에 대한 응답이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-439">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="ebc59-440">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="ebc59-440">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="ebc59-441">예</span><span class="sxs-lookup"><span data-stu-id="ebc59-441">Yes</span></span>  <br/> | <span data-ttu-id="ebc59-442">파트너 커넥터가 만들어서 채우는 다중 값 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-442">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="ebc59-443">이 속성의 형식은  `IPM.NOTE.Source.Event` 입니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-443">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="ebc59-444">(이 속성은 로 시작해야  `IPM.NOTE` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-444">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="ebc59-445">이 형식은 메시지 클래스에 대한  `IPM.NOTE.X` 형식과 유사합니다.) 이 속성에는 다음 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-445">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="ebc59-446">`Source`: 타사 데이터 원본을 나타냅니다. 예: Twitter, Facebook 또는 BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="ebc59-446">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="ebc59-447">`Event`: 항목을 생성한 타사 데이터 원본에서 수행된 활동의 유형을 나타냅니다. 예를 들어 Twitter의 트윗 또는 Facebook의 게시물입니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-447">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="ebc59-448">이벤트는 데이터 원본과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-448">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="ebc59-449">이 속성의 한 가지 목적은 항목이 시작된 데이터 원본이나 이벤트의 유형에 따라 특정 항목을 필터링하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-449">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="ebc59-450">예를 들어 eDiscovery 검색에서 특정 사용자가 게시한 모든 트윗을 찾는 검색 쿼리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-450">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |

- <span data-ttu-id="ebc59-451">항목이 사서함에 있는 사서함으로 Microsoft 365 HTTP 응답의 일부로 고유 식별자가 호출자에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-451">When items are successfully imported to mailboxes in Microsoft 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="ebc59-452">라는 이 식별자는 파트너가 항목의 종단을 추적하기 위해 후속 문제 해결을 위해 사용할  `x-IngestionCorrelationID` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-452">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="ebc59-453">파트너는 이 정보를 수집하고 적절하게 기록해두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-453">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="ebc59-454">이 식별자를 나타내는 HTTP 응답의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-454">Here's an example of an HTTP response showing this identifier:</span></span>

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT
    ```

- <span data-ttu-id="ebc59-455">보안 및 준수 센터의 콘텐츠 검색 도구를 사용하여 타사 데이터 원본에서 사서함으로 가져온 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-455">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes from a third-party data source.</span></span> <span data-ttu-id="ebc59-456">이러한 가져온 항목을 구체적으로 검색하기 위해 콘텐츠 검색의 키워드 상자에 다음 메시지 속성-값 쌍을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-456">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>

  - <span data-ttu-id="ebc59-457">**`kind:externaldata`**: 이 속성-값 쌍을 사용하여 모든 타사 데이터 형식을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-457">**`kind:externaldata`**: Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="ebc59-458">예를 들어 타사 데이터 원본에서 가져온 항목을 검색하고 가져온 항목의 Subject 속성에 "contoso"라는 단어가 포함된 항목을 검색하기 위해 키워드 쿼리를  `kind:externaldata AND subject:contoso` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-458">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>

  - <span data-ttu-id="ebc59-459">**`itemclass:ipm.externaldata.<third-party data type>`**: 이 속성-값 쌍을 사용하여 지정한 형식의 타사 데이터만 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-459">**`itemclass:ipm.externaldata.<third-party data type>`**: Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="ebc59-460">예를 들어 Subject 속성에 단어 "contoso"가 포함된 Facebook 데이터만 검색하기 위해 키워드 쿼리를  `itemclass:ipm.externaldata.Facebook* AND subject:contoso` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebc59-460">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span>

  <span data-ttu-id="ebc59-461">속성에 대해 타사 데이터 형식에 사용할 값의 전체 목록은 `itemclass` Use Content Search to search [third-party data that was imported to Microsoft 365.](use-content-search-to-search-third-party-data-that-was-imported.md)</span><span class="sxs-lookup"><span data-stu-id="ebc59-461">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Microsoft 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span></span>

   <span data-ttu-id="ebc59-462">콘텐츠 검색 사용 및 키워드 검색 쿼리를 만드는 방법에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ebc59-462">For more information about using Content Search and creating keyword search queries, see:</span></span>

  - [<span data-ttu-id="ebc59-463">콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="ebc59-463">Content Search</span></span>](content-search.md)

  - [<span data-ttu-id="ebc59-464">콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건</span><span class="sxs-lookup"><span data-stu-id="ebc59-464">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)