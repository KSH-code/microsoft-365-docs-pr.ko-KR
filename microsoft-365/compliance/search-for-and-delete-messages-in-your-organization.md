---
title: 조직의 전자 메일 메시지 검색 및 삭제하기
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: 보안 및 준수 센터의 검색 및 삭제하기 기능을 사용하여 조직의 모든 사서함에서 전자 메일 메시지를 검색하고 삭제할 수 있습니다.
ms.openlocfilehash: b7bb1008120df8efefc983d526d90e8397b3a89e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924238"
---
# <a name="search-for-and-delete-email-messages"></a><span data-ttu-id="f3f81-103">전자 메일 메시지 검색 및 삭제</span><span class="sxs-lookup"><span data-stu-id="f3f81-103">Search for and delete email messages</span></span>

<span data-ttu-id="f3f81-104">**이 문서는 관리자를 위해 작성되었습니다. 사서함에서 삭제할 항목을 찾으려고 하나요? [빠른 검색을 사용하여 메시지 또는 항목 찾기](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)** 를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3f81-104">**This article is for administrators. Are you trying to find items in your mailbox that you want to delete? See [Find a message or item with Instant Search](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**.</span></span>

<span data-ttu-id="f3f81-105">콘텐츠 검색 기능을 사용하여 조직의 모든 사서함에서 전자 메일 메시지를 검색하고 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-105">You can use the Content Search feature to search for and delete an email message from all mailboxes in your organization.</span></span> <span data-ttu-id="f3f81-106">이렇게 하면 잠재적으로 유해하거나 위험성이 높은 전자 메일을 찾아서 제거하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-106">This can help you find and remove potentially harmful or high-risk email, such as:</span></span>

- <span data-ttu-id="f3f81-107">위험한 첨부 파일 또는 바이러스를 포함하는 메시지</span><span class="sxs-lookup"><span data-stu-id="f3f81-107">Messages that contain dangerous attachments or viruses</span></span>

- <span data-ttu-id="f3f81-108">피싱 메시지</span><span class="sxs-lookup"><span data-stu-id="f3f81-108">Phishing messages</span></span>

- <span data-ttu-id="f3f81-109">중요한 데이터가 포함된 메시지</span><span class="sxs-lookup"><span data-stu-id="f3f81-109">Messages that contain sensitive data</span></span>

> [!CAUTION]
> <span data-ttu-id="f3f81-110">검색 및 삭제는 필요한 권한이 할당된 누구든지 조직의 사서함에서 전자 메일 메시지를 삭제할 수 있도록 하는 강력한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-110">Search and purge is a powerful feature that allows anyone that is assigned the necessary permissions to delete email messages from mailboxes in your organization.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f3f81-111">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="f3f81-111">Before you begin</span></span>

- <span data-ttu-id="f3f81-112">콘텐츠 검색을 만들고 실행하려면 **eDiscovery 관리자** 역할 그룹의 구성원이거나 **준수 검색** 관리 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-112">To create and run a Content Search, you have to be a member of the **eDiscovery Manager** role group or be assigned the **Compliance Search** management role.</span></span> <span data-ttu-id="f3f81-113">메시지를 삭제하려면 **조직 관리** 역할 그룹의 구성원이거나 **검색 및 삭제** 관리 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-113">To delete messages, you have to be a member of the **Organization Management** role group or be assigned the **Search And Purge** management role.</span></span> <span data-ttu-id="f3f81-114">역할 그룹에 사용자를 추가하는 방법에 대한 자세한 내용은 [보안 및 준수 센터의 eDiscovery 권한 부여](assign-ediscovery-permissions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3f81-114">For information about adding users to a role group, see [Assign eDiscovery permissions in the Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="f3f81-115">메시지를 삭제하려면 보안 및 준수 센터 PowerShell을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-115">You have to use Security & Compliance Center PowerShell to delete messages.</span></span> <span data-ttu-id="f3f81-116">연결하는 방법에 대한 자세한 내용은 [2단계](#step-2-connect-to-security--compliance-center-powershell)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3f81-116">See [Step 2](#step-2-connect-to-security--compliance-center-powershell) for instructions about how to connect.</span></span>

- <span data-ttu-id="f3f81-117">사서함마다 한 번에 최대 10개의 항목을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-117">A maximum of 10 items per mailbox can be removed at one time.</span></span> <span data-ttu-id="f3f81-118">메시지를 검색하고 제거하는 기능은 인시던트 응답 도구로 고안되었으므로 이러한 제한은 사서함에서 메시지가 빠르게 제거되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-118">Because the capability to search for and remove messages is intended to be an incident-response tool, this limit helps ensure that messages are quickly removed from mailboxes.</span></span> <span data-ttu-id="f3f81-119">이 기능은 사용자 사서함을 정리하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-119">This feature isn't intended to clean up user mailboxes.</span></span>

- <span data-ttu-id="f3f81-120">콘텐츠 검색에서 검색 및 삭제 작업을 사용하여 항목을 삭제할 수 있는 최대 사서함 수는 50,000개입니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-120">The maximum number of mailboxes in a content search that you can use to delete items by doing a search and purge action is 50,000.</span></span> <span data-ttu-id="f3f81-121">[1단계](#step-1-create-a-content-search-to-find-the-message-to-delete)에서 만든 검색에 50,000개를 초과하는 사서함이 있는 경우 3단계에서 만드는 삭제 작업이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-121">If the search (that you create in [Step 1](#step-1-create-a-content-search-to-find-the-message-to-delete)) searches more than 50,000 mailboxes, the purge action (that you create in Step 3) will fail.</span></span> <span data-ttu-id="f3f81-122">일반적으로 단일 검색에서 50,000개 이상의 편지함을 검색하는 작업은 조직의 모든 편지함을 포함하도록 검색을 구성할 때 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-122">Searching more than 50,000 mailbox in a single search might typically happen when you configure the search to include all mailboxes in your organization.</span></span> <span data-ttu-id="f3f81-123">이 제한은 50,000개 미만의 사서함에 검색 쿼리와 일치하는 항목이 포함된 경우에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-123">This restriction still applies even when less than 50,000 mailboxes contain items that match the search query.</span></span> <span data-ttu-id="f3f81-124">50,000개 이상의 사서함에서 검색 권한 필터를 사용하여 항목을 검색하고 제거하는 방법에 대한 지침은 [자세한 정보](#more-information) 색션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3f81-124">See the [More information](#more-information) section for guidance about using search permissions filters to search for and purge items from more than 50,000 mailboxes.</span></span>

- <span data-ttu-id="f3f81-125">이 문서의 절차는 Exchange Online 사서함 및 공용 폴더에서 항목을 삭제하는 데에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-125">The procedure in this article can only be used to delete items in Exchange Online mailboxes and public folders.</span></span> <span data-ttu-id="f3f81-126">SharePoint 또는 비즈니스용 OneDrive 사이트에서 콘텐츠를 삭제하는 데에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-126">You can't use it to delete content from SharePoint or OneDrive for Business sites.</span></span>

- <span data-ttu-id="f3f81-127">Advanced eDiscovery 사례에서 검토 집합의 전자 메일 항목은 이 문서의 절차를 사용하여 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-127">Email items in a review set in an Advanced eDiscovery case can't be deleted by using the procedures in this article.</span></span> <span data-ttu-id="f3f81-128">검토 집합의 항목이 실제 서비스가 아닌 Azure Storage 위치에 저장되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-128">That's because items in a review set are stored in an Azure Storage location, and not in the live service.</span></span> <span data-ttu-id="f3f81-129">즉, 1단계에서 만든 콘텐츠 검색에서 이를 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-129">This means they won't be returned by the content search that you create in Step 1.</span></span> <span data-ttu-id="f3f81-130">검토 집합의 항목을 삭제하려면 검토 집합이 포함된 Advanced eDiscovery 사례를 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-130">To delete items in a review set, you have to delete the Advanced eDiscovery case that contains the review set.</span></span> <span data-ttu-id="f3f81-131">자세한 내용은 [Advanced eDiscovery 사례 닫기 또는 삭제하기](close-or-delete-case.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3f81-131">For more information, see [Close or delete an Advanced eDiscovery case](close-or-delete-case.md).</span></span>

## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a><span data-ttu-id="f3f81-132">1단계: 삭제할 메시지를 찾는 콘텐츠 검색 만들기</span><span class="sxs-lookup"><span data-stu-id="f3f81-132">Step 1: Create a Content Search to find the message to delete</span></span>

<span data-ttu-id="f3f81-133">첫 번째 단계는 조직의 사서함에서 제거하려는 메시지를 찾는 콘텐츠 검색을 만들어 실행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-133">The first step is to create and run a Content Search to find the message that you want to remove from mailboxes in your organization.</span></span> <span data-ttu-id="f3f81-134">보안 및 준수 센터를 사용하거나 **New-ComplianceSearch** 및 **Start-ComplianceSearch** cmdlet을 실행하여 검색을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-134">You can create the search by using the Security & Compliance Center or by running the **New-ComplianceSearch** and **Start-ComplianceSearch** cmdlets.</span></span> <span data-ttu-id="f3f81-135">이 검색의 쿼리와 일치하는 메시지는 [3단계](#step-3-delete-the-message)에서 **New-ComplianceSearchAction -Purge** 명령을 실행하여 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-135">The messages that match the query for this search will be deleted by running the **New-ComplianceSearchAction -Purge** command in [Step 3](#step-3-delete-the-message).</span></span> <span data-ttu-id="f3f81-136">콘텐츠 검색을 만들고 검색 쿼리를 구성하는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3f81-136">For information about creating a Content Search and configuring search queries, see the following topics:</span></span>

- [<span data-ttu-id="f3f81-137">Office 365의 콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="f3f81-137">Content Search in Office 365</span></span>](content-search.md)

- [<span data-ttu-id="f3f81-138">콘텐츠 검색에 대한 키워드 쿼리</span><span class="sxs-lookup"><span data-stu-id="f3f81-138">Keyword queries for Content Search</span></span>](keyword-queries-and-search-conditions.md)

- [<span data-ttu-id="f3f81-139">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="f3f81-139">New-ComplianceSearch</span></span>](/powershell/module/exchange/New-ComplianceSearch)

- [<span data-ttu-id="f3f81-140">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="f3f81-140">Start-ComplianceSearch</span></span>](/powershell/module/exchange/Start-ComplianceSearch)

> [!NOTE]
> <span data-ttu-id="f3f81-141">이 단계에서 만드는 콘텐츠 검색에서 검색되는 콘텐츠 위치에는 SharePoint 또는 비즈니스용 OneDrive 사이트가 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-141">The content locations that are searched in the Content Search that you create in this step can't include SharePoint or OneDrive for Business sites.</span></span> <span data-ttu-id="f3f81-142">전자 메일 메시지에 사용되는 콘텐츠 검색에는 사서함 및 공용 폴더만 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-142">You can include only mailboxes and public folders in a Content Search that will be used to email messages.</span></span> <span data-ttu-id="f3f81-143">콘텐츠 검색에 사이트가 포함되는 경우 **New-ComplianceSearchAction** cmdlet을 실행할 때 3단계에서 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-143">If the Content Search includes sites, you'll receive an error in Step 3 when you run the **New-ComplianceSearchAction** cmdlet.</span></span>

### <a name="tips-for-finding-messages-to-remove"></a><span data-ttu-id="f3f81-144">제거할 메시지를 찾기 위한 팁</span><span class="sxs-lookup"><span data-stu-id="f3f81-144">Tips for finding messages to remove</span></span>

<span data-ttu-id="f3f81-p110">검색 쿼리의 목적은 검색의 결과 범위를 제거할 메시지로만 좁히는 것입니다. 다음 팁을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3f81-p110">The goal of the search query is to narrow the results of the search to only the message or messages that you want to remove. Here are some tips:</span></span>

- <span data-ttu-id="f3f81-147">메시지의 제목 줄에 사용된 정확한 텍스트나 구를 알고 있으면 검색 쿼리에 **Subject** 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-147">If you know the exact text or phrase used in the subject line of the message, use the **Subject** property in the search query.</span></span>

- <span data-ttu-id="f3f81-148">메시지의 정확한 날짜(또는 날짜 범위)를 알고 있으면 검색 쿼리에 **Received** 속성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-148">If you know that exact date (or date range) of the message, include the **Received** property in the search query.</span></span>

- <span data-ttu-id="f3f81-149">메시지를 보낸 사람을 알고 있으면 검색 쿼리에 **From** 속성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-149">If you know who sent the message, include the **From** property in the search query.</span></span>

- <span data-ttu-id="f3f81-150">검색 결과를 미리 확인하여 콘텐츠 검색이 삭제하려는 메시지만 반환하는지 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-150">Preview the search results to verify that the search returned only the message (or messages) that you want to delete.</span></span>

- <span data-ttu-id="f3f81-151">검색 예상 통계(보안 및 준수 센터의 검색 세부 정보 창에 표시되거나 [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch) cmdlet을 사용할 경우에 표시)를 사용하여 결과의 총 개수를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-151">Use the search estimate statistics (displayed in the details pane of the search in the Security & Compliance Center or by using the [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch) cmdlet) to get a count of the total number of results.</span></span>

<span data-ttu-id="f3f81-152">다음은 의심스러운 전자 메일 메시지를 찾는 쿼리의 두 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-152">Here are two examples of queries to find suspicious email messages.</span></span>

- <span data-ttu-id="f3f81-153">이 쿼리는 2016년 4월 13일과 2016년 4월 14일 사이에 사용자가 받은 메시지 중에서 제목 줄에 "action" 및 "required"가 포함된 메시지를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-153">This query returns messages that were received by users between April 13, 2016 and April 14, 2016 and that contain the words "action" and "required" in the subject line.</span></span>

  ```powershell
  (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
  ```

- <span data-ttu-id="f3f81-154">이 쿼리는 chatsuwloginsset12345@outlook.com에서 보낸 메시지 중에서 제목 줄에 "Update your account information"이 포함된 메시지를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-154">This query returns messages that were sent by chatsuwloginsset12345@outlook.com and that contain the exact phrase "Update your account information" in the subject line.</span></span>

  ```powershell
  (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
  ```

<span data-ttu-id="f3f81-155">다음은 사용할 쿼리를 만들고 **New-ComplianceSearch** 및 **Start-ComplianceSearch** cmdlet을 실행하여 검색을 시작하고 조직의 모든 사서함을 검색하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-155">Here's an example of using a query to create and start a search by running the **New-ComplianceSearch** and **Start-ComplianceSearch** cmdlets to search all mailboxes in the organization:</span></span>

```powershell
$Search=New-ComplianceSearch -Name "Remove Phishing Message" -ExchangeLocation All -ContentMatchQuery '(Received:4/13/2016..4/14/2016) AND (Subject:"Action required")'
Start-ComplianceSearch -Identity $Search.Identity
```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="f3f81-156">2단계: 보안 및 준수 센터 PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="f3f81-156">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="f3f81-157">다음 단계에서는 조직의 보안 및 준수 센터 PowerShell에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-157">The next step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="f3f81-158">단계별 지침은 [보안 및 준수 센터 PowerShell에 연결하기](/powershell/exchange/connect-to-scc-powershell)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3f81-158">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

<span data-ttu-id="f3f81-159">보안 및 준수 센터 PowerShell에 연결한 후 이전 단계에서 준비한 **New-ComplianceSearch** 및 **Start-ComplianceSearch** cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-159">After you've connected to Security & Compliance Center PowerShell, run the **New-ComplianceSearch** and **Start-ComplianceSearch** cmdlets that you prepared in the previous step.</span></span>

## <a name="step-3-delete-the-message"></a><span data-ttu-id="f3f81-160">3단계: 메시지 삭제</span><span class="sxs-lookup"><span data-stu-id="f3f81-160">Step 3: Delete the message</span></span>

<span data-ttu-id="f3f81-161">제거하려면 메시지를 반환하는 콘텐츠 검색을 만들고 구체화한 다음 보안 및 준수 센터 PowerShell에 연결되면 마지막으로 **New-ComplianceSearchAction** cmdlet을 실행하여 메시지를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-161">After you've created and refined a Content Search to return the message that you want to remove and are connected to Security & Compliance Center PowerShell, the final step is to run the **New-ComplianceSearchAction** cmdlet to delete the message.</span></span> <span data-ttu-id="f3f81-162">메시지를 일시 또는 영구 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-162">You can soft- or hard-delete the message.</span></span> <span data-ttu-id="f3f81-163">일시 삭제된 메시지는 사용자의 복구 가능한 항목 폴더로 이동하고 삭제된 항목 보존 기간이 만료될 때까지 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-163">A soft-deleted message is moved to a user's Recoverable Items folder and retained until the deleted item retention period expires.</span></span> <span data-ttu-id="f3f81-164">영구 삭제된 메시지는 사서함에서 영구 제거 표시되고 관리되는 폴더 도우미에서 다음에 사서함을 처리할 때 영구적으로 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-164">Hard-deleted messages are marked for permanent removal from the mailbox and will be permanently removed the next time the mailbox is processed by the Managed Folder Assistant.</span></span> <span data-ttu-id="f3f81-165">사서함에 대해 단일 항목 복구를 사용하는 경우 삭제된 항목 보존 기간이 만료되면 영구 삭제된 항목은 영구히 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-165">If single item recovery is enabled for the mailbox, hard-deleted items will be permanently removed after the deleted item retention period expires.</span></span> <span data-ttu-id="f3f81-166">사서함이 보류 중인 경우 항목에 대한 보존 기간이 만료되거나 사서함에서 보류가 제거될 때까지 삭제된 메시지가 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-166">If a mailbox is placed on hold, deleted messages are preserved until the hold duration for the item expires or until the hold is removed from the mailbox.</span></span>

<span data-ttu-id="f3f81-167">다음 예에서 명령은 “피싱 메시지 제거”라는 콘텐츠 검색에 의해 반환된 검색 결과를 일시 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-167">In the following example, the command soft-deletes the search results returned by a Content Search named "Remove Phishing Message".</span></span>

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

<span data-ttu-id="f3f81-168">"피싱 메시지 제거" 콘텐츠 검색에서 반환되는 항목을 영구 삭제하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-168">To hard-delete the items returned by the "Remove Phishing Message" content search, you would run this command:</span></span>

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

<span data-ttu-id="f3f81-169">이전 명령을 실행하여 메시지를 일시 삭제하거나 영구 삭제하는 경우 *SearchName* 매개 변수에 지정된 검색은 1단계에서 만든 콘텐츠 검색입니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-169">When you run the previous command to soft- or hard-delete messages, the search specified by the  *SearchName*  parameter is the Content Search that you created in Step 1.</span></span>

<span data-ttu-id="f3f81-170">자세한 내용은 [New-ComplianceSearchAction](/powershell/module/exchange/New-ComplianceSearchAction)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3f81-170">For more information, see [New-ComplianceSearchAction](/powershell/module/exchange/New-ComplianceSearchAction).</span></span>

## <a name="more-information"></a><span data-ttu-id="f3f81-171">추가 정보</span><span class="sxs-lookup"><span data-stu-id="f3f81-171">More information</span></span>

- <span data-ttu-id="f3f81-172">**검색 및 삭제 작업에 대한 상태를 어떻게 가져오나요?**</span><span class="sxs-lookup"><span data-stu-id="f3f81-172">**How do you get status on the search and remove operation?**</span></span>

  <span data-ttu-id="f3f81-173">삭제 작업에 대한 상태를 가져오려면 **Get-ComplianceSearchAction** 을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-173">Run the **Get-ComplianceSearchAction** to get the status on the delete operation.</span></span> <span data-ttu-id="f3f81-174">**New-ComplianceSearchAction** cmdlet을 실행할 때 생성되는 개체의 이름은 다음 형식을 사용하여 지정됩니다. `<name of Content Search>_Purge`.</span><span class="sxs-lookup"><span data-stu-id="f3f81-174">The object that is created when you run the **New-ComplianceSearchAction** cmdlet is named using this format:  `<name of Content Search>_Purge`.</span></span>

- <span data-ttu-id="f3f81-175">**메시지를 삭제하면 어떻게 되나요?**</span><span class="sxs-lookup"><span data-stu-id="f3f81-175">**What happens after you delete a message?**</span></span>

  <span data-ttu-id="f3f81-176">`New-ComplianceSearchAction -Purge -PurgeType HardDelete` 명령을 사용하여 삭제한 메시지는 제거 폴더로 이동되고 사용자가 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-176">A message that's deleted with the  `New-ComplianceSearchAction -Purge -PurgeType HardDelete` command is moved to the Purges folder and can't be accessed by the user.</span></span> <span data-ttu-id="f3f81-177">사서함에서 단일 항목 복구를 사용하는 경우 메시지는 제거 폴더로 이동된 후 삭제된 항목 보존 기간 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-177">After the message is moved to the Purges folder, the message is retained for the duration of the deleted item retention period if single item recovery is enabled for the mailbox.</span></span> <span data-ttu-id="f3f81-178">Microsoft 365에서는 새 사서함을 만들 때 단일 항목 복구가 기본적으로 사용됩니다. 삭제된 항목 보존 기간이 만료되면 메시지는 영구 삭제로 표시되고 관리되는 폴더 도우미에서 다음에 사서함을 처리할 때 Microsoft 365에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-178">(In Microsoft 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Microsoft 365 the next time the mailbox is processed by the Managed Folder assistant.</span></span>

  <span data-ttu-id="f3f81-179">`New-ComplianceSearchAction -Purge -PurgeType SoftDelete` 명령을 사용하는 경우 사용자의 복구 가능한 항목 폴더에서 삭제 폴더로 메시지가 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-179">If you use the `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` command, messages are moved to the Deletions folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="f3f81-180">메시지는 Microsoft 365에서 바로 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-180">It isn't immediately purged from Microsoft 365.</span></span> <span data-ttu-id="f3f81-181">사용자는 사서함에 구성된 삭제된 항목 보존 기간에 따라 일정 기간 동안 삭제된 항목 폴더에서 메시지를 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-181">The user can recover messages in the Deleted Items folder for the duration based on the deleted item retention period configured for the mailbox.</span></span> <span data-ttu-id="f3f81-182">이 보존 기간이 만료되거나 만료되기 전에 사용자가 메시지를 제거하면 메시지는 제거 폴더로 이동되고 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-182">After this retention period expires (or if user purges the message before it expires), the message is moved to the Purges folder and can no longer be accessed by the user.</span></span> <span data-ttu-id="f3f81-183">사서함에서 단일 항목 복구를 사용하는 경우 제거 폴더의 메시지는 사서함에 대해 구성된 삭제된 항목 보존 기간에 따라 일정 기간 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-183">Once in the Purges folder, the message is retained for the duration based on the deleted item retention period configured for the mailbox if single items recovery is enabled for the mailbox.</span></span> <span data-ttu-id="f3f81-184">Microsoft 365에서는 새 사서함을 만들 때 단일 항목 복구가 기본적으로 사용됩니다. 삭제된 항목 보존 기간이 만료되면 메시지는 영구 삭제로 표시되고 관리되는 폴더 도우미에서 다음에 사서함을 처리할 때 Microsoft 365에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-184">(In Microsoft 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Microsoft 365 the next time that the mailbox is processed by the Managed Folder assistant.</span></span>

- <span data-ttu-id="f3f81-185">**50,000개를 초과하는 사서함에서 메시지를 삭제해야 하는 경우 어떻게 되나요?**</span><span class="sxs-lookup"><span data-stu-id="f3f81-185">**What if you have to delete a message from more than 50,000 mailboxes?**</span></span>

  <span data-ttu-id="f3f81-186">앞서 설명한 대로 최대 50,000개의 사서함에서 검색 및 삭제 작업을 수행할 수 있습니다(50,000개 미만의 항목에 검색 쿼리와 일치하는 항목이 포함된 경우에도 마찬가지입니다.)</span><span class="sxs-lookup"><span data-stu-id="f3f81-186">As previously stated, you can perform a search and purge operation on a maximum of 50,000 mailboxes (even if less than 50,000 contain items that match the search query).</span></span> <span data-ttu-id="f3f81-187">50,000개를 초과하는 사서함에서 검색 및 삭제 작업을 수행해야 하는 경우 검색되는 사서함 수를 50,000개 이하로 줄여주는 임시 검색 권한 필터를 만들어 보세요.</span><span class="sxs-lookup"><span data-stu-id="f3f81-187">If you have to do a search and purge operation on more than 50,000 mailboxes, consider creating temporary search permissions filters that reduce the number of mailboxes that would be searched to less than 50,000 mailboxes.</span></span> <span data-ttu-id="f3f81-188">예를 들어 여러 부서, 주 또는 국가에 조직의 사서함이 포함되어 있는 경우 이러한 사서함 속성 중 하나를 기반으로 사서함 검색 권한 필터를 만들어 조직의 사서함 하위 집합을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-188">For example, if your organization contains mailboxes in different departments, states, or countries, you can create a mailbox search permissions filter based on one of those mailbox properties to search a subset of mailboxes in your organization.</span></span> <span data-ttu-id="f3f81-189">검색 사용 권한 필터를 만든 후 1단계에서 설명한 대로 검색을 만든 후 3단계에서 설명한 대로 메시지를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-189">After you create the search permissions filter, you would create the search (described in Step 1) and then delete the message (described in Step 3).</span></span> <span data-ttu-id="f3f81-190">그런 다음 필터를 편집하여 다른 사서함 집합에서 메시지를 검색한 후 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-190">Then you can edit the filter to search for and purge messages in a different set of mailboxes.</span></span> <span data-ttu-id="f3f81-191">검색 권한 필터를 만드는 방법에 대한 자세한 내용은 [콘텐츠 검색에 대한 권한 필터링 구성](permissions-filtering-for-content-search.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3f81-191">For more information about creating search permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>

- <span data-ttu-id="f3f81-192">**검색 결과에 포함된 인덱싱되지 않은 항목이 삭제되나요?**</span><span class="sxs-lookup"><span data-stu-id="f3f81-192">**Will unindexed items included in the search results be deleted?**</span></span>

  <span data-ttu-id="f3f81-193">아니요. \`New-ComplianceSearchAction -Purge 명령은 인덱싱되지 않은 항목을 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-193">No, the  \`New-ComplianceSearchAction -Purge command doesn't delete unindexed items.</span></span>

- <span data-ttu-id="f3f81-194">**원본 위치 유지 또는 소송 보존에 포함되거나 Microsoft 365 보존 정책에 할당된 사서함에서 메시지를 삭제하면 어떻게 되나요?**</span><span class="sxs-lookup"><span data-stu-id="f3f81-194">**What happens if a message is deleted from a mailbox that has been placed on In-Place Hold or Litigation Hold or is assigned to an Microsoft 365 retention policy?**</span></span>

  <span data-ttu-id="f3f81-195">메시지가 삭제되고 제거 폴더로 이동된 후 보존 기간이 만료될 때까지 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-195">After the message is purged and moved to the Purges folder, the message is retained until the hold duration expires.</span></span> <span data-ttu-id="f3f81-196">보존 기간에 제한이 없는 경우 보류를 제거하거나 보존 기간을 변경할 때까지 항목이 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-196">If the hold duration is unlimited, then items are retained until the hold is removed or the hold duration is changed.</span></span>

- <span data-ttu-id="f3f81-197">**다양한 보안 및 준수 센터 역할 그룹 간에 검색 및 제거 워크플로가 분리되어 있는 이유**</span><span class="sxs-lookup"><span data-stu-id="f3f81-197">**Why is the search and remove workflow divided among different security and compliance center role groups?**</span></span>

  <span data-ttu-id="f3f81-198">앞서 설명한 것처럼 사서함을 검색하려면 eDiscovery 관리자 역할 그룹의 구성원이거나 준수 검색 관리 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-198">As previously explained, a person has to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role to search mailboxes.</span></span> <span data-ttu-id="f3f81-199">메시지를 삭제하려면 조직 관리 역할 그룹의 구성원이거나 검색 및 제거 관리 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-199">To delete messages, a person has to be a member of the Organization Management role group or be assigned the Search And Purge management role.</span></span> <span data-ttu-id="f3f81-200">이렇게 하면 조직에서 사서함을 검색할 수 있는 사람과 메시지를 삭제할 수 있는 사람을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f81-200">This makes it possible to control who can search mailboxes in the organization and who can delete messages.</span></span>