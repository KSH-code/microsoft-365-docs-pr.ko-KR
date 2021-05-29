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
description: 공유 사서함을 설정할 때 오류가 발생할 수 있습니다. 공유 사서함에 문제가 있는 경우 이러한 솔루션을 사용해 하세요.
ms.openlocfilehash: 89cdfbe29ab035b1eb6c3a0183629eef59d67477
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706133"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="67aa7-104">공유 사서함의 문제 해결</span><span class="sxs-lookup"><span data-stu-id="67aa7-104">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="67aa7-105">공유 사서함을 만들거나 사용할 때 오류 메시지가 표시될 경우 이러한 가능한 해결 방법을 시도해 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67aa7-105">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="67aa7-106">공유 사서함을 만들 때 오류 발생</span><span class="sxs-lookup"><span data-stu-id="67aa7-106">Error when creating shared mailboxes</span></span>
<span data-ttu-id="67aa7-107"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="67aa7-107"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="67aa7-108">오류 메시지가 표시될 경우 프록시 주소 "smtp:<공유 사서함 이름"이 이미 프록시 주소나 **\> "의 LegacyExchangeDN에서 \<name> 사용 중입니다. 다른 프록시 주소** 를 선택하세요. 즉, 공유 사서함에 이미 사용 중인 이름을 지정하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="67aa7-108">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="67aa7-109">예를 들어 공유 사서함 이름을 info@domain1 및 info@domain2로 지정하려 합니다.</span><span class="sxs-lookup"><span data-stu-id="67aa7-109">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="67aa7-110">이 작업을 수행하는 방법은 다음 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="67aa7-110">There are two ways to do this:</span></span>

  - <span data-ttu-id="67aa7-111">이 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67aa7-111">Use Windows PowerShell.</span></span> <span data-ttu-id="67aa7-112">자세한 내용은 다음 블로그 게시물을 참조하세요. [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="67aa7-112">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="67aa7-113">두 번째 공유 사서함의 이름을 시작과 다르게 지정하여 오류를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="67aa7-113">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="67aa7-114">그런 다음 관리 센터에서 공유 사서함의 이름을 원하는 것으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="67aa7-114">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="67aa7-115">공유 사서함을 사용할 때 보내기 권한이 없는 경우의 오류</span><span class="sxs-lookup"><span data-stu-id="67aa7-115">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="67aa7-116">공유 사서함을 만든 후 해당 사서함에서 메시지를 보내려고 시도하면 다음을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67aa7-116">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="67aa7-117">**이 메시지를 보낼 수 없습니다. 지정된 사용자를 대신하여 메시지를 보낼 수 있는 권한이 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="67aa7-117">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="67aa7-118">이 메시지는 Microsoft 365 대기 시간 문제가 발생하면 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="67aa7-118">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="67aa7-119">새 공유 사서함(또는 추가된 사용자)에 대한 정보가 모든 데이터 센터에 복제되는 경우 1시간 정도 지나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67aa7-119">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="67aa7-120">1시간을 기다렸다가 다시 시도하여 메시지를 보내려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="67aa7-120">Wait an hour and then try again to send a message.</span></span>

## <a name="related-content"></a><span data-ttu-id="67aa7-121">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="67aa7-121">Related content</span></span>

<span data-ttu-id="67aa7-122">[공유 사서함 정보](about-shared-mailboxes.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="67aa7-122">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="67aa7-123">[공유 사서함](create-a-shared-mailbox.md) 만들기(문서)</span><span class="sxs-lookup"><span data-stu-id="67aa7-123">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="67aa7-124">[공유 사서함 구성](configure-a-shared-mailbox.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="67aa7-124">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="67aa7-125">[사용자 사서함을 공유 사서함으로 변환](convert-user-mailbox-to-shared-mailbox.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="67aa7-125">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="67aa7-126">[공유 사서함에서 라이선스 제거](remove-license-from-shared-mailbox.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="67aa7-126">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>


    

