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
description: Exchange Online 사서함에 대해 무제한 보관 저장소를 제공 하는 자동 확장 보관에 대해 알아봅니다.
ms.openlocfilehash: f2d9e645badd98ea9a1d14dec22e291c8ad7de63
ms.sourcegitcommit: 416a4b87bfd7e5aff80194b59b2776f054aa8eb5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44534920"
---
# <a name="overview-of-unlimited-archiving"></a><span data-ttu-id="ebee9-103">무제한 보관 개요</span><span class="sxs-lookup"><span data-stu-id="ebee9-103">Overview of unlimited archiving</span></span>

<span data-ttu-id="ebee9-104">Office 365에서 보관 사서함은 사용자에 게 사서함 저장소 공간을 추가로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-104">In Office 365, archive mailboxes provide users with additional mailbox storage space.</span></span> <span data-ttu-id="ebee9-105">사용자의 보관 사서함을 사용 하도록 설정한 후에는 최대 100의 추가 저장소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-105">After a user's archive mailbox is enabled, up to 100 GB of additional storage is available.</span></span> <span data-ttu-id="ebee9-106">이전에 100 GB 저장소 할당량에 도달 하면 조직에서 Microsoft에 연락 하 여 보관 사서함에 대 한 추가 저장소 공간을 요청 해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-106">In the past, when the 100-GB storage quota was reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox.</span></span> <span data-ttu-id="ebee9-107">더 이상 이러한 경우는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-107">That's no longer the case.</span></span>

<span data-ttu-id="ebee9-108">Microsoft 365의 무제한 보관 기능 ( *자동 확장 보관*이라고 함)은 보관 사서함에 추가 저장소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-108">The unlimited archiving feature in Microsoft 365 (called *auto-expanding archiving*) provides additional storage in archive mailboxes.</span></span> <span data-ttu-id="ebee9-109">보관 사서함의 저장소 할당량에 도달 하면 Microsoft 365에서 자동으로 보관 함의 크기를 증가 시키며, 따라서 사용자에 게 사서함 저장소 공간이 부족 하지 않으며 관리자가 보관 사서함에 대해 추가 저장소를 요청할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-109">When the storage quota in the archive mailbox is reached, Microsoft 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>

<span data-ttu-id="ebee9-110">자동 확장 보관을 설정 하는 단계별 지침은 [Enable 무제한 보관 사용](enable-unlimited-archiving.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebee9-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ebee9-111">자동 확장 보관 기능은 공유 사서함도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-111">Auto-expanding archiving also supports shared mailboxes.</span></span> <span data-ttu-id="ebee9-112">공유 사서함에 대 한 보관 함을 사용 하도록 설정 하려면 exchange online 계획 2 라이선스 또는 교환 라이선스가 있는 exchange online 계획 1 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-112">To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>

## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="ebee9-113">자동 확장 보관의 작동 방식</span><span class="sxs-lookup"><span data-stu-id="ebee9-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="ebee9-114">앞에서 설명한 것 처럼 사용자의 보관 사서함을 사용 하도록 설정 하면 추가 사서함 저장소 공간이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-114">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled.</span></span> <span data-ttu-id="ebee9-115">자동 확장 보관을 사용 하도록 설정 하면 Microsoft 365에서 보관 사서함의 크기를 주기적으로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-115">When auto-expanding archiving is enabled, Microsoft 365 periodically checks the size of the archive mailbox.</span></span> <span data-ttu-id="ebee9-116">보관 사서함의 저장 제한 시간에 근접 하면 Microsoft 365에서 자동으로 보관에 대 한 추가 저장소 공간을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-116">When an archive mailbox gets close to its storage limit, Microsoft 365 automatically creates additional storage space for the archive.</span></span> <span data-ttu-id="ebee9-117">사용자가이 추가 저장 공간을 초과 하는 경우 Microsoft 365에서는 사용자의 보관 사서함에 저장 공간을 더 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-117">If the user runs out of this additional storage space, Microsoft 365 adds more storage space to the user's archive.</span></span> <span data-ttu-id="ebee9-118">이 프로세스가 자동으로 수행 되므로 관리자가 추가 보관 저장소를 요청 하거나 자동 확장 보관을 관리할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-118">This process happens automatically, which means administrators don't have to request additional archive storage or manage auto-expanding archiving.</span></span>

<span data-ttu-id="ebee9-119">프로세스에 대 한 간략 한 개요는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-119">Here's a quick overview of the process.</span></span>

![자동 확장 보관 프로세스 개요](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. <span data-ttu-id="ebee9-121">사용자 사서함 또는 공유 사서함에 대해 보관을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-121">Archiving is enabled for a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="ebee9-122">100 GB의 저장소 공간이 있는 보관 사서함이 만들어지고 보관 사서함에 대 한 경고 할당량이 90 g b로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-122">An archive mailbox with 100 GB of storage space is created, and the warning quota for the archive mailbox is set to 90 GB.</span></span>

2. <span data-ttu-id="ebee9-123">관리자가 사서함에 대해 자동 확장 보관을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-123">An administrator enables auto-expanding archiving for the mailbox.</span></span> <span data-ttu-id="ebee9-124">복구 가능한 항목 폴더를 포함 하는 보관 사서함이 90에 도달 하면 자동 확장 보관 함으로 변환 되 고 Microsoft 365에서 보관 함에 저장 공간을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-124">When the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Microsoft 365 adds storage space to the archive.</span></span> <span data-ttu-id="ebee9-125">추가 저장 공간을 프로 비전 하는 데 최대 30 일이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-125">It can take up to 30 days for the additional storage space to be provisioned.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ebee9-126">사서함을 보류 하거나 보존 정책에 할당 하면 자동 확장 보관을 사용 하는 경우 보관 사서함의 저장소 할당량이 110 GB로 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-126">If a mailbox is placed on hold or assigned to a retention policy, the storage quota for the archive mailbox is increased to 110 GB when auto-expanding archiving is enabled.</span></span> <span data-ttu-id="ebee9-127">마찬가지로 보관 경고 할당량이 100 GB로 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-127">Similarly, the archive warning quota is increased to 100 GB.</span></span>

3. <span data-ttu-id="ebee9-128">Microsoft 365는 필요한 경우 저장 공간을 자동으로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-128">Microsoft 365 automatically adds more storage space when necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebee9-129">자동 확장 보관은 하루에 1GB를 초과 하지 않는 성장률을 갖는 개별 사용자 (또는 공유 사서함)에 사용 되는 사서함에 대해서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-129">Auto-expanding archive is only supported for mailboxes used for individual users (or shared mailboxes) with a growth rate that doesn't exceed 1 GB per day.</span></span> <span data-ttu-id="ebee9-130">사용자의 보관 사서함은 해당 사용자만을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-130">A user's archive mailbox is intended for just that user.</span></span> <span data-ttu-id="ebee9-131">저널링, 전송 규칙 또는 자동 전달 규칙을 사용 하 여 보관 사서함에 메시지를 복사할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-131">Using journaling, transport rules, or auto-forwarding rules to copy messages to an archive mailbox is not permitted.</span></span> <span data-ttu-id="ebee9-132">Microsoft는 사용자의 보관 사서함이 다른 사용자의 보관 데이터를 저장 하는 데 사용 되거나 부적절 하 게 사용 되는 경우를 제외 하 고 무제한 보관을 거부할 수 있는 권한을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-132">Microsoft reserves the right to deny unlimited archiving in instances where a user's archive mailbox is used to store archive data for other users or in other cases of the inappropriate use.</span></span>

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="ebee9-133">추가 보관 저장소 공간으로 이동 하는 것은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="ebee9-133">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="ebee9-134">자동 확장 보관 저장소를 효율적으로 사용 하기 위해 폴더가 이동 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-134">To make efficient use of auto-expanding archive storage, folders may get moved.</span></span> <span data-ttu-id="ebee9-135">Microsoft 365에서는 추가 저장소가 보관 사서함에 추가 될 때 이동할 폴더를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-135">Microsoft 365 determines which folders get moved when additional storage is added to the archive.</span></span> <span data-ttu-id="ebee9-136">폴더를 이동 하면 하나 이상의 하위 폴더가 자동으로 만들어지고 원본 폴더의 항목이 이러한 폴더에 배포 되어 이동 프로세스를 촉진 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-136">Sometimes when a folder is moved, one or more subfolders are automatically created and items from the original folder are distributed to these folders to facilitate the moving process.</span></span> <span data-ttu-id="ebee9-137">Outlook에서 폴더 목록의 보관 부분을 볼 때 이러한 하위 폴더는 원래 폴더 아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-137">When viewing the archive portion of the folder list in Outlook, these subfolders are displayed under the original folder.</span></span>  <span data-ttu-id="ebee9-138">Microsoft 365에서 이러한 하위 폴더의 이름을 지정 하는 데 사용 하는 명명 규칙은 \*\* \<folder name\> _yyyy (mmm dd, yyyy h_mm)로 작성\*\*됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-138">The naming convention that Microsoft 365 uses to name these subfolders is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span>

- <span data-ttu-id="ebee9-139">**yyyy** 는 폴더에서 메시지가 수신 된 연도입니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-139">**yyyy** is the year the messages in the folder were received.</span></span>

- <span data-ttu-id="ebee9-140">**mmm dd, yyyy h_m** 는 사용자의 표준 시간대 및 Outlook 국가별 설정에 따라 하위 폴더가 Office 365에서 만들어진 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-140">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span>

<span data-ttu-id="ebee9-141">다음 스크린샷에서는 메시지가 자동 확장 된 보관 함으로 이동 되기 전과 후의 폴더 목록을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-141">The following screenshots show a folder list before and after messages are moved to an auto-expanded archive.</span></span>

 <span data-ttu-id="ebee9-142">**추가 저장소가 추가 되기 전에**</span><span class="sxs-lookup"><span data-stu-id="ebee9-142">**Before additional storage is added**</span></span>

![자동 확장 보관이 프로 비전 되기 전 보관 사서함의 폴더 목록](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 <span data-ttu-id="ebee9-144">**추가 저장소가 추가 된 후**</span><span class="sxs-lookup"><span data-stu-id="ebee9-144">**After additional storage is added**</span></span>

![자동 확장 보관이 프로 비전 된 후 보관 사서함의 폴더 목록](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> <span data-ttu-id="ebee9-146">앞에서 설명한 것 처럼 Microsoft 365는 항목을 하위 폴더로 이동 하 고 위에 설명 된 명명 규칙을 사용 하 여 해당 사용자의 이름을 보조 아카이브로 콘텐츠를 분산 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-146">As previously described, Microsoft 365 moves items to subfolders (and names them using the naming convention described above) to help distribute content to an auxiliary archive.</span></span> <span data-ttu-id="ebee9-147">하지만 하위 폴더로 항목을 이동 하는 경우는 항상 해당 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-147">But moving items to subfolders may not always be the case.</span></span> <span data-ttu-id="ebee9-148">전체 폴더가 보조 아카이브로 이동 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-148">Sometimes an entire folder may be moved to an auxiliary archive.</span></span> <span data-ttu-id="ebee9-149">이 경우 폴더의 원래 이름은 그대로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-149">In this case, the folder will retain its original name.</span></span>  <span data-ttu-id="ebee9-150">Outlook의 폴더 목록에서 폴더가 보조 보관 함으로 이동 되었음을 명확 하 게 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-150">It won't be apparent in the folder list in Outlook that the folder was moved to an auxiliary archive.</span></span>

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="ebee9-151">자동 확장 보관 함의 항목에 액세스 하기 위한 Outlook 요구 사항</span><span class="sxs-lookup"><span data-stu-id="ebee9-151">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="ebee9-152">자동 확장 보관 사서함에 저장 된 메시지에 액세스 하려면 사용자는 다음 Outlook 클라이언트 중 하나를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-152">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>

- <span data-ttu-id="ebee9-153">Windows 용 outlook 2016 또는 Outlook 2019</span><span class="sxs-lookup"><span data-stu-id="ebee9-153">Outlook 2016 or Outlook 2019 for Windows</span></span>

- <span data-ttu-id="ebee9-154">웹용 Outlook</span><span class="sxs-lookup"><span data-stu-id="ebee9-154">Outlook on the web</span></span>

- <span data-ttu-id="ebee9-155">Mac 용 outlook 2016 또는 Outlook 2019</span><span class="sxs-lookup"><span data-stu-id="ebee9-155">Outlook 2016 or Outlook 2019 for Mac</span></span>

<span data-ttu-id="ebee9-156">다음은 Outlook 또는 웹용 Outlook을 사용 하 여 자동 확장 보관 함에 저장 된 메시지에 액세스 하는 경우 고려해 야 할 몇 가지 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-156">Here are some things to consider when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>

- <span data-ttu-id="ebee9-157">자동 확장 된 저장 영역으로 이동 된 폴더를 포함 하 여 보관 사서함의 모든 편지함에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-157">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>

- <span data-ttu-id="ebee9-158">자동 확장 보관용 검색은 16.0.12716.10000 build for 참가자의 Outlook 데스크톱 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-158">Search for auto-expanded archiving is only available in Outlook Desktop as of Insiders build 16.0.12716.10000.</span></span> <span data-ttu-id="ebee9-159">웹에 대 한 Outlook에서 검색을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-159">Search is available in Outlook for the web.</span></span> <span data-ttu-id="ebee9-160">온라인 보관 함과 마찬가지로, 폴더 자체를 검색 해야만 추가 저장소 영역으로 이동한 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-160">Similar to Online Archive, you can search for items that were moved to an additional storage area only by searching the folder itself.</span></span> <span data-ttu-id="ebee9-161">즉, 검색 범위로 **현재 폴더** 옵션을 선택 하려면 폴더 목록에서 보관 폴더를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-161">This means that you have to select the archive folder in the folder list to select the **Current Folder** option as the search scope.</span></span> <span data-ttu-id="ebee9-162">마찬가지로 자동 확장 된 저장소 영역의 폴더에 하위 폴더가 있는 경우 각 하위 폴더를 개별적으로 검색 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-162">Similarly, if a folder in an auto-expanded storage area contains subfolders, you have to search each subfolder separately.</span></span>

- <span data-ttu-id="ebee9-163">자동 확장 보관 함에서 Outlook 및 웹용 Outlook의 항목 수가 정확 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-163">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web) in an auto-expanded archive might not be accurate.</span></span>

- <span data-ttu-id="ebee9-164">자동 확장 된 저장 영역을 가리키는 하위 폴더의 항목을 삭제할 수는 있지만 해당 폴더 자체를 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-164">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span>

- <span data-ttu-id="ebee9-165">지운 편지함 복구 기능을 사용 하 여 자동 확장 된 저장소 영역에서 삭제 된 항목을 복구할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-165">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>

## <a name="auto-expanding-archiving-and-other-compliance-features"></a><span data-ttu-id="ebee9-166">보관 및 기타 규정 준수 기능 자동 확장</span><span class="sxs-lookup"><span data-stu-id="ebee9-166">Auto-expanding archiving and other compliance features</span></span>

<span data-ttu-id="ebee9-167">이 섹션에서는 자동 확장 보관과 기타 준수 및 데이터 거 버 넌 스 기능 간의 기능에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-167">This section explains the functionality between auto-expanding archiving and other compliance and data governance features.</span></span>

- <span data-ttu-id="ebee9-168">**eDiscovery:** 콘텐츠 검색 또는 원본 위치 eDiscovery와 같은 eDiscovery 도구를 사용 하면 자동 확장 보관 함의 추가 저장소 영역도 검색 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-168">**eDiscovery:** When you use an eDiscovery tool, such as Content Search or In-Place eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>

- <span data-ttu-id="ebee9-169">**보존:** 보안 및 준수 센터에서 Exchange Online 또는 eDiscovery 사례 보류와 보존 정책에 대 한 소송 보존 등의 도구를 사용 하 여 사서함을 보존 하면 자동 확장 보관 함에 있는 콘텐츠도 보존 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-169">**Retention:** When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery case holds and retention policies in the security and compliance center, content located in an auto-expanded archive is also placed on hold.</span></span>

- <span data-ttu-id="ebee9-170">**MRM (메시징 레코드 관리):** Exchange Online에서 MRM 삭제 정책을 사용 하 여 만료 된 사서함 항목을 영구적으로 삭제 하는 경우에는 자동 확장 보관 함에 있는 만료 됨 항목도 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-170">**Messaging records management (MRM):** If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>

- <span data-ttu-id="ebee9-171">**서비스 가져오기:** Office 365 가져오기 서비스를 사용 하 여 PST 파일을 사용자의 자동 확장 아카이브로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-171">**Import service:** You can use the Office 365 Import service to import PST files to a user's auto-expanded archive.</span></span> <span data-ttu-id="ebee9-172">PST 파일에서 사용자의 보관 사서함으로의 데이터를 최대 100 GB까지 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebee9-172">You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span>

## <a name="more-information"></a><span data-ttu-id="ebee9-173">추가 정보</span><span class="sxs-lookup"><span data-stu-id="ebee9-173">More information</span></span>

<span data-ttu-id="ebee9-174">자동 확장 보관에 대 한 자세한 기술 정보는 [Microsoft 365: 자동 확장 보관 함 FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebee9-174">For more technical details about auto-expanding archiving, see [Microsoft 365: Auto-Expanding Archives FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).</span></span>
