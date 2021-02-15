---
title: 무제한 보관 개요
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: Exchange Online 사서함에 무제한 보관 저장소를 제공하는 자동 확장 보관에 대해 자세히 알아보습니다.
ms.openlocfilehash: 9692ba27c64f41ac584bb4008a8b860daab031f5
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029434"
---
# <a name="overview-of-unlimited-archiving"></a><span data-ttu-id="920ab-103">무제한 보관 개요</span><span class="sxs-lookup"><span data-stu-id="920ab-103">Overview of unlimited archiving</span></span>

<span data-ttu-id="920ab-104">Office 365에서 보관 사서함은 사용자에게 추가 사서함 저장소 공간을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-104">In Office 365, archive mailboxes provide users with additional mailbox storage space.</span></span> <span data-ttu-id="920ab-105">사용자의 보관 사서함을 사용하도록 설정하면 최대 100GB의 추가 저장소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-105">After a user's archive mailbox is enabled, up to 100 GB of additional storage is available.</span></span> <span data-ttu-id="920ab-106">과거에는 100GB 저장소 할당량에 도달할 때 조직에서 보관 사서함에 대한 추가 저장소 공간을 요청하기 위해 Microsoft에 문의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-106">In the past, when the 100-GB storage quota was reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox.</span></span> <span data-ttu-id="920ab-107">더 이상 그럴 수가 없는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-107">That's no longer the case.</span></span>

<span data-ttu-id="920ab-108">Microsoft 365의 무제한 보관 기능(자동 확장 보관이라고도함)은 보관 사서함에 추가 저장소를 제공합니다. </span><span class="sxs-lookup"><span data-stu-id="920ab-108">The unlimited archiving feature in Microsoft 365 (called *auto-expanding archiving*) provides additional storage in archive mailboxes.</span></span> <span data-ttu-id="920ab-109">보관 사서함의 저장소 할당량에 도달하면 Microsoft 365에서 자동으로 보관함 크기가 증가합니다. 즉, 사용자는 사서함 저장소 공간을 모두 사용할 수 있으며 관리자가 보관 사서함에 대한 추가 저장소를 요청할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-109">When the storage quota in the archive mailbox is reached, Microsoft 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>

<span data-ttu-id="920ab-110">자동 확장 보관을 켜는 단계별 지침은 무제한 보관 사용을 [참조하세요.](enable-unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="920ab-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>

> [!NOTE]
> <span data-ttu-id="920ab-111">자동 확장 보관 기능은 공유 사서함도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-111">Auto-expanding archiving also supports shared mailboxes.</span></span> <span data-ttu-id="920ab-112">공유 사서함에 대해 보관 사서함을 사용하도록 설정하려면 Exchange Online 계획 2 라이선스 또는 Exchange Online 계획 1 라이선스와 Exchange Online Archiving 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-112">To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>

## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="920ab-113">자동 확장 보관의 작동 방식</span><span class="sxs-lookup"><span data-stu-id="920ab-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="920ab-114">앞서 설명한처럼 사용자의 보관 사서함을 사용하도록 설정하면 추가 사서함 저장소 공간이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-114">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled.</span></span> <span data-ttu-id="920ab-115">자동 확장 보관을 사용하도록 설정하면 Microsoft 365는 보관 사서함의 크기를 주기적으로 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-115">When auto-expanding archiving is enabled, Microsoft 365 periodically checks the size of the archive mailbox.</span></span> <span data-ttu-id="920ab-116">보관 사서함이 저장 용량 제한에 가까워지면 Microsoft 365는 보관 사서함에 대한 추가 저장소 공간을 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-116">When an archive mailbox gets close to its storage limit, Microsoft 365 automatically creates additional storage space for the archive.</span></span> <span data-ttu-id="920ab-117">사용자가 이 추가 저장소 공간을 사용할 수 있는 경우 Microsoft 365는 사용자의 보관에 더 많은 저장 공간을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-117">If the user runs out of this additional storage space, Microsoft 365 adds more storage space to the user's archive.</span></span> <span data-ttu-id="920ab-118">이 프로세스는 자동으로 수행됩니다. 즉, 관리자가 추가 보관 저장소를 요청하거나 자동 확장 보관을 관리할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-118">This process happens automatically, which means administrators don't have to request additional archive storage or manage auto-expanding archiving.</span></span>

<span data-ttu-id="920ab-119">다음은 프로세스에 대한 간략한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-119">Here's a quick overview of the process.</span></span>

![자동 확장 보관 프로세스 개요](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. <span data-ttu-id="920ab-121">사용자 사서함 또는 공유 사서함에 대해 보관을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-121">Archiving is enabled for a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="920ab-122">저장소 공간이 100GB인 보관 사서함이 만들어지며 보관 사서함에 대한 경고 할당량은 90GB로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-122">An archive mailbox with 100 GB of storage space is created, and the warning quota for the archive mailbox is set to 90 GB.</span></span>

2. <span data-ttu-id="920ab-123">관리자가 사서함에 대해 자동 확장 보관을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-123">An administrator enables auto-expanding archiving for the mailbox.</span></span> <span data-ttu-id="920ab-124">복구 가능한 항목 폴더를 포함한 보관 사서함이 90GB에 도달하면 자동 확장 보관함으로 변환되고 Microsoft 365는 보관함에 저장 공간을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-124">When the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Microsoft 365 adds storage space to the archive.</span></span> <span data-ttu-id="920ab-125">추가 저장소 공간을 프로비전하는 데 최대 30일이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-125">It can take up to 30 days for the additional storage space to be provisioned.</span></span>

   > [!NOTE]
   > <span data-ttu-id="920ab-126">사서함이 보류 중이거나 보존 정책에 할당된 경우 자동 확장 보관을 사용하도록 설정하면 보관 사서함의 저장소 할당량은 110GB로 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-126">If a mailbox is placed on hold or assigned to a retention policy, the storage quota for the archive mailbox is increased to 110 GB when auto-expanding archiving is enabled.</span></span> <span data-ttu-id="920ab-127">마찬가지로 보관 경고 할당량도 100GB로 늘어났습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-127">Similarly, the archive warning quota is increased to 100 GB.</span></span>

3. <span data-ttu-id="920ab-128">Microsoft 365는 필요한 경우 자동으로 더 많은 저장 공간을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-128">Microsoft 365 automatically adds more storage space when necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="920ab-129">자동 확장 보관은 하루당 1GB를 초과하지 않는 증가율의 개별 사용자(또는 공유 사서함)에 사용되는 사서함에만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-129">Auto-expanding archive is only supported for mailboxes used for individual users (or shared mailboxes) with a growth rate that doesn't exceed 1 GB per day.</span></span> <span data-ttu-id="920ab-130">사용자의 보관 사서함은 해당 사용자만을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-130">A user's archive mailbox is intended for just that user.</span></span> <span data-ttu-id="920ab-131">저널링, 전송 규칙 또는 자동 전달 규칙을 사용하여 메시지를 보관 사서함으로 복사할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-131">Using journaling, transport rules, or auto-forwarding rules to copy messages to an archive mailbox is not permitted.</span></span> <span data-ttu-id="920ab-132">Microsoft는 사용자의 보관 사서함이 다른 사용자의 보관 데이터를 저장하는 데 사용되는 경우 또는 부적절한 사용의 경우 무제한 보관을 거부할 권리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-132">Microsoft reserves the right to deny unlimited archiving in instances where a user's archive mailbox is used to store archive data for other users or in other cases of the inappropriate use.</span></span>

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="920ab-133">추가 보관 저장소 공간으로 이동하는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="920ab-133">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="920ab-134">자동 확장 보관 저장소를 효율적으로 사용하기 위해 폴더가 이동될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-134">To make efficient use of auto-expanding archive storage, folders may get moved.</span></span> <span data-ttu-id="920ab-135">Microsoft 365는 보관에 추가 저장소가 추가될 때 이동되는 폴더를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-135">Microsoft 365 determines which folders get moved when additional storage is added to the archive.</span></span> <span data-ttu-id="920ab-136">폴더를 이동할 때 하나 이상의 하위 폴더가 자동으로 만들어지며 원본 폴더의 항목이 이동 프로세스를 용이하게 하기 위해 이러한 폴더에 배포되는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-136">Sometimes when a folder is moved, one or more subfolders are automatically created and items from the original folder are distributed to these folders to facilitate the moving process.</span></span> <span data-ttu-id="920ab-137">Outlook에서 폴더 목록의 보관 부분을 볼 때 이러한 하위 폴더는 원래 폴더 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-137">When viewing the archive portion of the folder list in Outlook, these subfolders are displayed under the original folder.</span></span>  <span data-ttu-id="920ab-138">Microsoft 365에서 이러한 하위폴더의 이름을 지정하는 데 사용하는 명명 규칙은 **\<folder name\> _yyyy(mmm dd, yyyy** h_mm에서 생성)입니다. 여기서:</span><span class="sxs-lookup"><span data-stu-id="920ab-138">The naming convention that Microsoft 365 uses to name these subfolders is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span>

- <span data-ttu-id="920ab-139">**yyyy는** 폴더의 메시지를 받은 연도입니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-139">**yyyy** is the year the messages in the folder were received.</span></span>

- <span data-ttu-id="920ab-140">**mmm dd, yyyy h_m** 는 사용자의 표준 시간대 및 Outlook의 국가별 설정에 따라 Office 365에서 하위폴더를 만든 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-140">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span>

<span data-ttu-id="920ab-141">다음 스크린샷은 메시지가 자동 확장 보관함으로 이동되기 전과 후에 폴더 목록을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="920ab-141">The following screenshots show a folder list before and after messages are moved to an auto-expanded archive.</span></span>

 <span data-ttu-id="920ab-142">**추가 저장소가 추가되기 전에**</span><span class="sxs-lookup"><span data-stu-id="920ab-142">**Before additional storage is added**</span></span>

![자동 확장 보관이 프로비전되기 전 보관 사서함의 폴더 목록](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 <span data-ttu-id="920ab-144">**추가 저장소 추가 후**</span><span class="sxs-lookup"><span data-stu-id="920ab-144">**After additional storage is added**</span></span>

![자동 확장 보관함이 프로비전된 후 보관 사서함의 폴더 목록](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> <span data-ttu-id="920ab-146">앞서 설명한 대로 Microsoft 365는 보조 보관함으로 콘텐츠를 배포할 수 있도록 항목을 하위폴더로 이동하고 위에서 설명한 명명 규칙을 사용하여 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-146">As previously described, Microsoft 365 moves items to subfolders (and names them using the naming convention described above) to help distribute content to an auxiliary archive.</span></span> <span data-ttu-id="920ab-147">그러나 항목을 하위폴더로 이동하는 것은 항상 해당되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-147">But moving items to subfolders may not always be the case.</span></span> <span data-ttu-id="920ab-148">경우에 따라 전체 폴더가 보조 보관함으로 이동될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-148">Sometimes an entire folder may be moved to an auxiliary archive.</span></span> <span data-ttu-id="920ab-149">이 경우 폴더는 원래 이름을 그대로 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-149">In this case, the folder will retain its original name.</span></span>  <span data-ttu-id="920ab-150">Outlook의 폴더 목록에서 폴더가 보조 보관함으로 이동된 것이 분명하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-150">It won't be apparent in the folder list in Outlook that the folder was moved to an auxiliary archive.</span></span>

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="920ab-151">자동 확장 보관함의 항목에 액세스하기 위한 Outlook 요구 사항</span><span class="sxs-lookup"><span data-stu-id="920ab-151">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="920ab-152">자동 확장 보관 파일에 저장된 메시지에 액세스하기 위해 사용자는 다음 Outlook 클라이언트 중 하나를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-152">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>

- <span data-ttu-id="920ab-153">Windows용 Outlook 2016 또는 Outlook 2019</span><span class="sxs-lookup"><span data-stu-id="920ab-153">Outlook 2016 or Outlook 2019 for Windows</span></span>

- <span data-ttu-id="920ab-154">웹용 Outlook</span><span class="sxs-lookup"><span data-stu-id="920ab-154">Outlook on the web</span></span>

- <span data-ttu-id="920ab-155">Outlook 2016 또는 Outlook 2019 for Mac</span><span class="sxs-lookup"><span data-stu-id="920ab-155">Outlook 2016 or Outlook 2019 for Mac</span></span>

<span data-ttu-id="920ab-156">다음은 Outlook 또는 웹용 Outlook을 사용하여 자동 확장 보관 파일에 저장된 메시지에 액세스할 때 고려해야 할 몇 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-156">Here are some things to consider when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>

- <span data-ttu-id="920ab-157">자동 확장 저장소 영역으로 이동된 폴더를 포함하여 보관 사서함의 모든 폴더에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-157">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>

- <span data-ttu-id="920ab-158">자동 확장 보관 검색은 웹용 Outlook에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-158">Search for auto-expanded archiving is available in Outlook for the web.</span></span> <span data-ttu-id="920ab-159">온라인 보관과 마찬가지로 현재 폴더 자체만 검색하여 추가 저장 영역으로 이동된 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-159">Similar to Online Archive, you can search for items that were moved to an additional storage area only by searching the current folder itself.</span></span> <span data-ttu-id="920ab-160">즉, 폴더 목록에서 보관 폴더를 선택한 다음 단일 폴더를 검색 범위로 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-160">This means that you must select the archive folder in the folder list, and then select a single folder as your search scope.</span></span> <span data-ttu-id="920ab-161">마찬가지로 자동 확장 저장소 영역의 폴더에 하위 폴더가 포함되어 있는 경우 각 하위 폴더를 개별적으로 검색해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-161">Similarly, if a folder in an auto-expanded storage area contains subfolders, you must search each subfolder separately.</span></span>
- <span data-ttu-id="920ab-162">자동 확장 보관 검색은 현재 채널의 Outlook 데스크톱(미리 보기)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-162">Auto-expanded archive search is available in Outlook Desktop in Current Channel (Preview).</span></span> <span data-ttu-id="920ab-163">이 미리 보기 내에서 현재 사서함 범위를 사용할 수 있어 자동 확장된 보관 사서함을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-163">Within this preview, the Current Mailbox scope is available, thus allowing you to search the auto-expanded archive.</span></span> <span data-ttu-id="920ab-164">이 기능과 기타 Microsoft Search 지원 기능에 대한 자세한 내용은 Exchange Online에 연결된 [Windows용 Outlook에서 Microsoft Search를](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045)활용하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="920ab-164">For more information about this and other Microsoft Search support features, see [How Outlook for Windows connected to Exchange Online utilizes Microsoft Search](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045).</span></span> 

- <span data-ttu-id="920ab-165">자동 확장된 보관함의 Outlook 및 읽기/읽지 않은 항목 수(Outlook 및 웹용 Outlook)의 항목 수가 정확하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-165">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web) in an auto-expanded archive might not be accurate.</span></span>

- <span data-ttu-id="920ab-166">자동 확장 저장소 영역을 지정하는 하위 폴더의 항목을 삭제할 수 있지만 폴더 자체는 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-166">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span>

- <span data-ttu-id="920ab-167">지우기 항목 복구 기능을 사용하여 자동 확장된 저장소 영역에서 삭제된 항목을 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-167">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>

## <a name="auto-expanding-archiving-and-other-compliance-features"></a><span data-ttu-id="920ab-168">자동 확장 보관 및 기타 규정 준수 기능</span><span class="sxs-lookup"><span data-stu-id="920ab-168">Auto-expanding archiving and other compliance features</span></span>

<span data-ttu-id="920ab-169">이 섹션에서는 자동 확장 보관과 기타 규정 준수 및 데이터 거버넌스 기능 간의 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-169">This section explains the functionality between auto-expanding archiving and other compliance and data governance features.</span></span>

- <span data-ttu-id="920ab-170">**eDiscovery:** 콘텐츠 검색 또는 In-Place eDiscovery와 같은 eDiscovery 도구를 사용하는 경우 자동 확장 보관함의 추가 저장소 영역도 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-170">**eDiscovery:** When you use an eDiscovery tool, such as Content Search or In-Place eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>

- <span data-ttu-id="920ab-171">**보존:** Exchange Online의 소송 보존 또는 eDiscovery 사례 보류 및 보안 및 준수 센터의 보존 정책과 같은 도구를 사용하여 사서함을 보류할 경우 자동 확장된 보관함에 있는 콘텐츠도 보류됩니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-171">**Retention:** When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery case holds and retention policies in the security and compliance center, content located in an auto-expanded archive is also placed on hold.</span></span>

- <span data-ttu-id="920ab-172">**MRM(메시징 레코드 관리):** Exchange Online에서 MRM 삭제 정책을 사용하여 만료된 사서함 항목을 영구적으로 삭제하는 경우 자동 확장 보관함에 있는 만료된 항목도 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-172">**Messaging records management (MRM):** If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>

- <span data-ttu-id="920ab-173">**가져오기 서비스:** Office 365 가져오기 서비스를 사용하여 PST 파일을 사용자의 자동 확장 보관함으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-173">**Import service:** You can use the Office 365 Import service to import PST files to a user's auto-expanded archive.</span></span> <span data-ttu-id="920ab-174">PST 파일에서 사용자의 보관 사서함으로 최대 100GB의 데이터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-174">You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span>

## <a name="more-information"></a><span data-ttu-id="920ab-175">추가 정보</span><span class="sxs-lookup"><span data-stu-id="920ab-175">More information</span></span>

<span data-ttu-id="920ab-176">자동 확장 보관에 대한 자세한 기술 정보는 [Microsoft 365:](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784)자동 확장 보관함 FAQ를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="920ab-176">For more technical details about auto-expanding archiving, see [Microsoft 365: Auto-Expanding Archives FAQ](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784).</span></span>
