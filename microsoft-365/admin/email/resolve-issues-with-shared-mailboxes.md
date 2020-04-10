---
title: 공유 사서함의 문제 해결
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
description: 공유 사서함에서 문제가 발생 하는 경우 다음 솔루션을 사용해 보세요.
ms.openlocfilehash: 138bcee155652e84ab6ee16cf6a9acab310edde9
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210519"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="c9148-103">공유 사서함의 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c9148-103">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="c9148-104">공유 사서함을 만들거나 사용할 때 오류 메시지가 표시 되 면 가능한 해결 방법을 시도해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="c9148-104">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="c9148-105">공유 사서함을 만들 때 오류 발생</span><span class="sxs-lookup"><span data-stu-id="c9148-105">Error when creating shared mailboxes</span></span>
<span data-ttu-id="c9148-106"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="c9148-106"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="c9148-107">오류 메시지가 표시 되 면 " **\<name>"의 프록시 주소 또는 LegacyExchangeDN에서 프록시 주소\>"smtp: <공유 사서함 이름"을 이미 사용 하 고 있는 것입니다. 다른 프록시 주소를 선택**하 여 이미 사용 중인 공유 사서함의 이름을 지정 하 고 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9148-107">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="c9148-108">예를 들어 공유 사서함 이름을 info@domain1 및 info@domain2로 지정하려 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9148-108">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="c9148-109">이 작업은 다음 두 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9148-109">There are two ways to do this:</span></span>

  - <span data-ttu-id="c9148-110">Windows PowerShell을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9148-110">Use Windows PowerShell.</span></span> <span data-ttu-id="c9148-111">이 블로그 게시물에서 지침을 참조 하세요. [Office 365의 서로 다른 도메인에서 별칭이 같은 공유 사서함 만들기](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="c9148-111">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains in Office 365](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="c9148-112">두 번째 공유 사서함의 이름을 오류 발생과 다르게 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9148-112">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="c9148-113">그런 다음 관리 센터에서 공유 사서함의 이름을 원하는 대로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9148-113">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="c9148-114">공유 사서함을 사용 하는 경우 보내기 사용 권한 없음에 대 한 오류</span><span class="sxs-lookup"><span data-stu-id="c9148-114">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="c9148-115">공유 사서함을 만든 후 메시지를 보내려고 하면 다음 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9148-115">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="c9148-116">**이 메시지를 보낼 수 없습니다. 지정한 사용자를 대신 하 여 메시지를 보낼 수 있는 권한이 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="c9148-116">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="c9148-117">이 메시지는 Office 365에서 복제 대기 시간 문제가 발생 한 경우에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9148-117">This message appears when Office 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="c9148-118">새 공유 사서함에 대 한 정보 또는 추가 된 사용자에 대 한 정보가 모든 데이터 센터에 복제 되는 한 시간 내에 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9148-118">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="c9148-119">한 시간 동안 기다린 후 메시지를 다시 보내 봅니다.</span><span class="sxs-lookup"><span data-stu-id="c9148-119">Wait an hour and then try again to send a message.</span></span>

## <a name="related-articles"></a><span data-ttu-id="c9148-120">관련 문서</span><span class="sxs-lookup"><span data-stu-id="c9148-120">Related articles</span></span>

[<span data-ttu-id="c9148-121">공유 사서함 정보</span><span class="sxs-lookup"><span data-stu-id="c9148-121">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="c9148-122">공유 사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="c9148-122">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="c9148-123">공유 사서함 구성</span><span class="sxs-lookup"><span data-stu-id="c9148-123">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="c9148-124">사용자 사서함을 공유 사서함으로 변환</span><span class="sxs-lookup"><span data-stu-id="c9148-124">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="c9148-125">공유 사서함에서 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="c9148-125">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)


    

