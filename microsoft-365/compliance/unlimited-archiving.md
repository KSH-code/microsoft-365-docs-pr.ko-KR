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
description: 사서함에 무제한 보관 저장소를 제공하는 자동 확장 보관에 Exchange Online 대해 자세히 알아보습니다.
ms.openlocfilehash: d61d3649ed65a93298928cced21180bbeca6aa95
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476269"
---
# <a name="overview-of-unlimited-archiving"></a><span data-ttu-id="00f35-103">무제한 보관 개요</span><span class="sxs-lookup"><span data-stu-id="00f35-103">Overview of unlimited archiving</span></span>

<span data-ttu-id="00f35-104">이 Office 365 보관 사서함은 사용자에게 추가 사서함 저장소 공간을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-104">In Office 365, archive mailboxes provide users with additional mailbox storage space.</span></span> <span data-ttu-id="00f35-105">사용자의 보관 사서함을 사용하도록 설정한 후 최대 100GB의 추가 저장소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-105">After a user's archive mailbox is enabled, up to 100 GB of additional storage is available.</span></span> <span data-ttu-id="00f35-106">과거에는 100GB 저장소 할당량에 도달할 때 조직에서 보관 사서함에 대한 추가 저장소 공간을 요청하기 위해 Microsoft에 문의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-106">In the past, when the 100-GB storage quota was reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox.</span></span> <span data-ttu-id="00f35-107">더 이상 그럴 수가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="00f35-107">That's no longer the case.</span></span>

<span data-ttu-id="00f35-108">보관 사서함의 무제한 보관 Microsoft 365(자동 확장 보관)는 보관 사서함에 추가 저장소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-108">The unlimited archiving feature in Microsoft 365 (called *auto-expanding archiving*) provides additional storage in archive mailboxes.</span></span> <span data-ttu-id="00f35-109">보관 사서함의 저장소 할당량에 도달하면 Microsoft 365 자동으로 보관함 크기가 증가합니다. 즉, 사용자는 사서함 저장소 공간을 모두 사용할 수 있으며 관리자는 보관 사서함에 대한 추가 저장소를 요청할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-109">When the storage quota in the archive mailbox is reached, Microsoft 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>

<span data-ttu-id="00f35-110">자동 확장 보관을 켜는 단계별 지침은 무제한 보관 사용 [을 참조하세요.](enable-unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="00f35-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>

> [!NOTE]
> <span data-ttu-id="00f35-111">자동 확장 보관 기능은 공유 사서함도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-111">Auto-expanding archiving also supports shared mailboxes.</span></span> <span data-ttu-id="00f35-112">공유 사서함에 대해 보관을 사용하도록 설정하려면 Exchange Online 계획 2 라이선스 또는 Exchange Online 라이선스가 있는 Exchange Online Archiving 계획 1 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-112">To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>

## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="00f35-113">자동 확장 보관의 작동 방식</span><span class="sxs-lookup"><span data-stu-id="00f35-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="00f35-114">앞서 설명한 것 처럼 사용자의 보관 사서함을 사용하도록 설정하면 추가 사서함 저장소 공간이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-114">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled.</span></span> <span data-ttu-id="00f35-115">자동 확장 보관을 사용하도록 설정하면 Microsoft 365 사서함의 크기를 정기적으로 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-115">When auto-expanding archiving is enabled, Microsoft 365 periodically checks the size of the archive mailbox.</span></span> <span data-ttu-id="00f35-116">보관 사서함이 저장소 제한에 가까워지면 보관 Microsoft 365 추가 저장소 공간을 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-116">When an archive mailbox gets close to its storage limit, Microsoft 365 automatically creates additional storage space for the archive.</span></span> <span data-ttu-id="00f35-117">사용자가 이러한 추가 저장소 공간을 사용할 수 Microsoft 365 저장소 공간을 더 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-117">If the user runs out of this additional storage space, Microsoft 365 adds more storage space to the user's archive.</span></span> <span data-ttu-id="00f35-118">이 프로세스는 자동으로 수행됩니다. 즉, 관리자가 추가 보관 저장소를 요청하거나 자동 확장 보관을 관리할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-118">This process happens automatically, which means administrators don't have to request additional archive storage or manage auto-expanding archiving.</span></span>

<span data-ttu-id="00f35-119">다음은 프로세스에 대한 간략한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-119">Here's a quick overview of the process.</span></span>

![자동 확장 보관 프로세스 개요](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. <span data-ttu-id="00f35-121">사용자 사서함 또는 공유 사서함에 대해 보관을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-121">Archiving is enabled for a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="00f35-122">저장소 공간이 100GB인 보관 사서함이 만들어지며 보관 사서함에 대한 경고 할당량은 90GB로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-122">An archive mailbox with 100 GB of storage space is created, and the warning quota for the archive mailbox is set to 90 GB.</span></span>

2. <span data-ttu-id="00f35-123">관리자는 사서함에 대해 자동 확장 보관을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-123">An administrator enables auto-expanding archiving for the mailbox.</span></span> <span data-ttu-id="00f35-124">보관 사서함(복구 가능한 항목 폴더 포함)이 90GB에 도달하면 자동 확장 보관함으로 변환되고 Microsoft 365 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-124">When the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Microsoft 365 adds storage space to the archive.</span></span> <span data-ttu-id="00f35-125">추가 저장소 공간을 프로비전하는 데 최대 30일이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-125">It can take up to 30 days for the additional storage space to be provisioned.</span></span>

   > [!NOTE]
   > <span data-ttu-id="00f35-126">사서함이 보류 중이거나 보존 정책에 할당된 경우 자동 확장 보관을 사용하도록 설정하면 보관 사서함의 저장소 할당량은 110GB로 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-126">If a mailbox is placed on hold or assigned to a retention policy, the storage quota for the archive mailbox is increased to 110 GB when auto-expanding archiving is enabled.</span></span> <span data-ttu-id="00f35-127">마찬가지로 보관 경고 할당량은 100GB로 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-127">Similarly, the archive warning quota is increased to 100 GB.</span></span>

3. <span data-ttu-id="00f35-128">Microsoft 365 경우 저장소 공간이 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-128">Microsoft 365 automatically adds more storage space when necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00f35-129">자동 확장 보관은 하루 1GB를 초과하지 않는 증가 속도의 개별 사용자(또는 공유 사서함)에 사용되는 사서함에만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-129">Auto-expanding archive is only supported for mailboxes used for individual users (or shared mailboxes) with a growth rate that doesn't exceed 1 GB per day.</span></span> <span data-ttu-id="00f35-130">사용자의 보관 사서함은 해당 사용자만을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-130">A user's archive mailbox is intended for just that user.</span></span> <span data-ttu-id="00f35-131">저널링, 전송 규칙 또는 자동 전달 규칙을 사용하여 메시지를 보관 사서함에 복사할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-131">Using journaling, transport rules, or auto-forwarding rules to copy messages to an archive mailbox is not permitted.</span></span> <span data-ttu-id="00f35-132">Microsoft는 사용자의 보관 사서함이 다른 사용자의 보관 데이터를 저장하는 데 사용되는 경우 또는 부적절한 사용의 다른 경우에 무제한 보관을 거부할 수 있는 권리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-132">Microsoft reserves the right to deny unlimited archiving in instances where a user's archive mailbox is used to store archive data for other users or in other cases of the inappropriate use.</span></span>

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="00f35-133">추가 보관 저장소 공간으로 이동하는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="00f35-133">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="00f35-134">자동 확장 보관 저장소를 효율적으로 사용하기 위해 폴더가 이동될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-134">To make efficient use of auto-expanding archive storage, folders may get moved.</span></span> <span data-ttu-id="00f35-135">Microsoft 365 저장소가 추가될 때 이동되는 폴더를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-135">Microsoft 365 determines which folders get moved when additional storage is added to the archive.</span></span> <span data-ttu-id="00f35-136">폴더를 이동할 때 하나 이상의 하위 폴더가 자동으로 만들어지며 원본 폴더의 항목이 이러한 폴더에 배포되어 이동 프로세스를 용이하게 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-136">Sometimes when a folder is moved, one or more subfolders are automatically created and items from the original folder are distributed to these folders to facilitate the moving process.</span></span> <span data-ttu-id="00f35-137">폴더 목록의 보관 부분을 볼 Outlook 이러한 하위 폴더는 원래 폴더 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-137">When viewing the archive portion of the folder list in Outlook, these subfolders are displayed under the original folder.</span></span>  <span data-ttu-id="00f35-138">이러한 하위 Microsoft 365 이름을 지정하는 데 사용하는 명명 규칙은 **\<folder name\> _yyyy(mmm dd, yyyy h_mm)입니다.** 여기서</span><span class="sxs-lookup"><span data-stu-id="00f35-138">The naming convention that Microsoft 365 uses to name these subfolders is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span>

- <span data-ttu-id="00f35-139">**yyyy는** 폴더의 메시지를 받은 연도입니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-139">**yyyy** is the year the messages in the folder were received.</span></span>

- <span data-ttu-id="00f35-140">**mmm dd, yyyyy** h_m 는 Office 365 UTC 형식의 하위폴더를 만든 날짜와 시간으로, Outlook.</span><span class="sxs-lookup"><span data-stu-id="00f35-140">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span>

<span data-ttu-id="00f35-141">다음 스크린샷은 메시지가 자동 확장 보관함으로 이동되기 전과 후에 폴더 목록을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="00f35-141">The following screenshots show a folder list before and after messages are moved to an auto-expanded archive.</span></span>

 <span data-ttu-id="00f35-142">**추가 저장소가 추가되기 전에**</span><span class="sxs-lookup"><span data-stu-id="00f35-142">**Before additional storage is added**</span></span>

![자동 확장 보관이 프로비전되기 전 보관 사서함의 폴더 목록](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 <span data-ttu-id="00f35-144">**추가 저장소 추가 후**</span><span class="sxs-lookup"><span data-stu-id="00f35-144">**After additional storage is added**</span></span>

![자동 확장 보관함이 프로비전된 후 보관 사서함의 폴더 목록](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> <span data-ttu-id="00f35-146">앞서 Microsoft 365 항목을 하위폴더로 이동하고 위에 설명된 명명 규칙을 사용하여 이름을 변경하여 보조 보관함으로 콘텐츠를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-146">As previously described, Microsoft 365 moves items to subfolders (and names them using the naming convention described above) to help distribute content to an auxiliary archive.</span></span> <span data-ttu-id="00f35-147">그러나 항목을 하위폴더로 이동하는 경우도 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-147">But moving items to subfolders may not always be the case.</span></span> <span data-ttu-id="00f35-148">경우에 따라 전체 폴더가 보조 보관함으로 이동될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-148">Sometimes an entire folder may be moved to an auxiliary archive.</span></span> <span data-ttu-id="00f35-149">이 경우 폴더는 원래 이름을 그대로 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-149">In this case, the folder will retain its original name.</span></span>  <span data-ttu-id="00f35-150">폴더가 보조 보관함으로 Outlook 폴더 목록에는 분명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-150">It won't be apparent in the folder list in Outlook that the folder was moved to an auxiliary archive.</span></span>

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="00f35-151">Outlook 확장된 보관함의 항목에 액세스하기 위한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="00f35-151">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="00f35-152">자동 확장 보관 파일에 저장된 메시지에 액세스하기 위해 사용자는 다음 클라이언트 중 하나를 Outlook 합니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-152">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>

- <span data-ttu-id="00f35-153">Outlook 2016 Outlook 또는 Windows</span><span class="sxs-lookup"><span data-stu-id="00f35-153">Outlook 2016 or Outlook 2019 for Windows</span></span>

- <span data-ttu-id="00f35-154">웹용 Outlook</span><span class="sxs-lookup"><span data-stu-id="00f35-154">Outlook on the web</span></span>

- <span data-ttu-id="00f35-155">Outlook 2016 또는 Outlook 2019 for Mac</span><span class="sxs-lookup"><span data-stu-id="00f35-155">Outlook 2016 or Outlook 2019 for Mac</span></span>

<span data-ttu-id="00f35-156">다음은 자동 확장 보관 파일에 저장된 메시지에 액세스하기 위해 웹 Outlook Outlook 때 고려해야 할 몇 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-156">Here are some things to consider when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>

- <span data-ttu-id="00f35-157">자동 확장 저장소 영역으로 이동된 폴더를 포함하여 보관 사서함의 모든 폴더에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-157">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>

- <span data-ttu-id="00f35-158">자동 확장 보관 검색은 OWA(웹용 Outlook 검색)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-158">Search for auto-expanded archiving is available in Outlook for the web (OWA).</span></span> <span data-ttu-id="00f35-159">온라인 보관과 마찬가지로 추가 저장소 영역으로 이동된 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-159">Similar to Online Archive, you can search for items that were moved to an additional storage area.</span></span> <span data-ttu-id="00f35-160">OWA에서 보관함이 검색 범위로 선택되어 있는 경우 모든 보관함(자동 확장된 보관함 포함)과 해당 하위폴더가 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-160">When archive is selected as the search scope in OWA, all archives (including auto-expanded archives) and their corresponding subfolders will be searched.</span></span>

- <span data-ttu-id="00f35-161">자동 확장 보관 검색은 현재 채널의 Outlook 데스크톱(미리 보기)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-161">Auto-expanded archive search is available in Outlook Desktop in Current Channel (Preview).</span></span> <span data-ttu-id="00f35-162">이 미리 보기 내에서 현재 사서함 범위를 사용할 수 있어 자동 확장된 보관 파일을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-162">Within this preview, the Current Mailbox scope is available, thus allowing you to search the auto-expanded archive.</span></span> <span data-ttu-id="00f35-163">이 기능 및 기타 Microsoft Search 지원 기능에 대한 자세한 내용은 Microsoft Search에 연결된 Outlook Windows Microsoft Search를 활용하는 [Exchange Online 참조하세요.](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045)</span><span class="sxs-lookup"><span data-stu-id="00f35-163">For more information about this and other Microsoft Search support features, see [How Outlook for Windows connected to Exchange Online utilizes Microsoft Search](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045).</span></span> 

- <span data-ttu-id="00f35-164">자동 확장된 Outlook 및 읽기/읽지 않은 항목 수(웹에서 Outlook Outlook 항목 수)가 정확하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-164">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web) in an auto-expanded archive might not be accurate.</span></span>

- <span data-ttu-id="00f35-165">자동 확장 저장소 영역을 지정하는 하위 폴더의 항목을 삭제할 수 있지만 폴더 자체는 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-165">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span>

- <span data-ttu-id="00f35-166">지우기 항목 복구 기능을 사용하여 자동 확장된 저장소 영역에서 삭제된 항목을 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-166">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>

## <a name="auto-expanding-archiving-and-other-compliance-features"></a><span data-ttu-id="00f35-167">자동 확장 보관 및 기타 규정 준수 기능</span><span class="sxs-lookup"><span data-stu-id="00f35-167">Auto-expanding archiving and other compliance features</span></span>

<span data-ttu-id="00f35-168">이 섹션에서는 자동 확장 보관과 기타 규정 준수 및 데이터 거버넌스 기능 간의 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-168">This section explains the functionality between auto-expanding archiving and other compliance and data governance features.</span></span>

- <span data-ttu-id="00f35-169">**eDiscovery:** 콘텐츠 검색 또는 eDiscovery와 같은 eDiscovery 도구를 In-Place 자동 확장 보관함의 추가 저장소 영역도 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-169">**eDiscovery:** When you use an eDiscovery tool, such as Content Search or In-Place eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>

- <span data-ttu-id="00f35-170">**보존:** 보안 및 규정 준수 센터의 Exchange Online 또는 eDiscovery 사례 보류 및 보존 정책과 같은 도구를 사용하여 사서함을 보류하면 자동 확장된 보관함에 있는 콘텐츠도 보류됩니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-170">**Retention:** When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery case holds and retention policies in the security and compliance center, content located in an auto-expanded archive is also placed on hold.</span></span>

- <span data-ttu-id="00f35-171">**MRM(메시징 레코드 관리):** 사서함에서 MRM 삭제 정책을 Exchange Online 만료된 사서함 항목을 영구적으로 삭제하면 자동 확장 보관함에 있는 만료된 항목도 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-171">**Messaging records management (MRM):** If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>

- <span data-ttu-id="00f35-172">**서비스 가져오기:** 가져오기 Office 365 사용하여 PST 파일을 사용자의 자동 확장 보관함으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-172">**Import service:** You can use the Office 365 Import service to import PST files to a user's auto-expanded archive.</span></span> <span data-ttu-id="00f35-173">PST 파일에서 사용자의 보관 사서함으로 최대 100GB의 데이터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00f35-173">You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span>

## <a name="more-information"></a><span data-ttu-id="00f35-174">추가 정보</span><span class="sxs-lookup"><span data-stu-id="00f35-174">More information</span></span>

<span data-ttu-id="00f35-175">자동 확장 보관에 대한 자세한 기술 정보는 Microsoft 365: 자동 확장 [보관함 FAQ를 참조합니다.](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784)</span><span class="sxs-lookup"><span data-stu-id="00f35-175">For more technical details about auto-expanding archiving, see [Microsoft 365: Auto-Expanding Archives FAQ](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784).</span></span>
