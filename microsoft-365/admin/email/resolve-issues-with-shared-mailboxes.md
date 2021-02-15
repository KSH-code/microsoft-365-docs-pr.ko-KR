---
title: 공유 사서함의 문제 해결
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: 공유 사서함에 문제가 있는 경우 이러한 해결 방법을 시도해 보아야 합니다.
ms.openlocfilehash: ba62db76edff6e4ab3d738ed0af8db2a40c18394
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926489"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="ed4aa-103">공유 사서함의 문제 해결</span><span class="sxs-lookup"><span data-stu-id="ed4aa-103">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="ed4aa-104">공유 사서함을 만들거나 사용할 때 오류 메시지가 표시될 경우 이러한 해결 방법을 시도해 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed4aa-104">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="ed4aa-105">공유 사서함을 만들 때 오류</span><span class="sxs-lookup"><span data-stu-id="ed4aa-105">Error when creating shared mailboxes</span></span>
<span data-ttu-id="ed4aa-106"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="ed4aa-106"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="ed4aa-107">오류 메시지가 표시될 경우 프록시 주소 "smtp:<공유 사서함 이름"이 프록시 주소 또는 **\> ""의 LegacyExchangeDN에서 이미 사용 \<name> 중입니다. 다른 프록시 주소를 선택하세요.** 즉, 공유 사서함에 이미 사용 중인 이름을 지정하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed4aa-107">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="ed4aa-108">예를 들어 공유 사서함 이름을 info@domain1 및 info@domain2로 지정하려 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed4aa-108">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="ed4aa-109">이 작업은 다음 두 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4aa-109">There are two ways to do this:</span></span>

  - <span data-ttu-id="ed4aa-110">이 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed4aa-110">Use Windows PowerShell.</span></span> <span data-ttu-id="ed4aa-111">지침은 다음 블로그 게시물을 참조하세요. 다른 도메인에서 동일한 별칭을 사용하여 공유 사서함 [만들기](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="ed4aa-111">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="ed4aa-112">두 번째 공유 사서함의 이름을 시작과 다르게 지정하여 오류를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="ed4aa-112">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="ed4aa-113">그런 다음 관리 센터에서 공유 사서함의 이름을 원하는 것으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ed4aa-113">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="ed4aa-114">공유 사서함을 사용할 때 보내기 권한이 없는 경우의 오류</span><span class="sxs-lookup"><span data-stu-id="ed4aa-114">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="ed4aa-115">공유 사서함을 만든 다음 해당 사서함에서 메시지를 보내려고 시도하면 다음 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4aa-115">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="ed4aa-116">**이 메시지를 보낼 수 없습니다. 지정된 사용자를 대신하여 메시지를 보낼 수 있는 권한이 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="ed4aa-116">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="ed4aa-117">이 메시지는 Microsoft 365에서 복제 대기 시간 문제가 발생하는 경우 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed4aa-117">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="ed4aa-118">새 공유 사서함(또는 추가된 사용자)에 대한 정보가 모든 데이터 센터에 복제될 때 1시간 정도 지나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4aa-118">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="ed4aa-119">1시간을 기다렸다가 메시지를 다시 보내려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="ed4aa-119">Wait an hour and then try again to send a message.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ed4aa-120">관련 문서</span><span class="sxs-lookup"><span data-stu-id="ed4aa-120">Related articles</span></span>

[<span data-ttu-id="ed4aa-121">공유 사서함 정보</span><span class="sxs-lookup"><span data-stu-id="ed4aa-121">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="ed4aa-122">공유 사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="ed4aa-122">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="ed4aa-123">공유 사서함 구성</span><span class="sxs-lookup"><span data-stu-id="ed4aa-123">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="ed4aa-124">사용자 사서함을 공유 사서함으로 변환</span><span class="sxs-lookup"><span data-stu-id="ed4aa-124">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="ed4aa-125">공유 사서함에서 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="ed4aa-125">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)


    

