---
title: 수신 차단된 보낸 사람 목록에서 자신을 제거합니다.
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 목록 제거 포털을 사용하여 Microsoft 365 수신이 차단된 보낸 사람 목록에서 자신을 제거하는 방법을 배우게 됩니다.
ms.openlocfilehash: 0c87d467db004a50502402b05eb0fa3283aa46c5
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614765"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="8355f-103">목록 해제 포털을 사용하여 수신 거부 목록에서 본인 제거</span><span class="sxs-lookup"><span data-stu-id="8355f-103">Use the delist portal to remove yourself from the blocked senders list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="8355f-104">해당 전자 메일 주소가 Microsoft 365에 있는 받는 사람에게 전자 메일을 보내려고 할 때 오류 메시지가 표시하나요?</span><span class="sxs-lookup"><span data-stu-id="8355f-104">Are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365?</span></span> <span data-ttu-id="8355f-105">오류 메시지가 수신되지 않는 것으로 생각될 경우 목록 제거 포털을 사용하여 차단된 보낸 사람 목록에서 자신을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8355f-105">If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the blocked senders list.</span></span>

## <a name="what-is-the-blocked-senders-list"></a><span data-ttu-id="8355f-106">수신이 차단된 보낸 사람 목록이란?</span><span class="sxs-lookup"><span data-stu-id="8355f-106">What is the blocked senders list?</span></span>

<span data-ttu-id="8355f-107">Microsoft는 수신 거부 목록을 사용하여 스팸, 스푸핑 및 피싱 공격으로부터 고객을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="8355f-107">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks.</span></span> <span data-ttu-id="8355f-108">메일 서버의 IP 주소, 즉 메일 서버가 인터넷에서 자체를 식별하는 데 사용하는 주소는 다양한 이유로 Microsoft 365에 잠재적인 위협으로 태그가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8355f-108">Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Microsoft 365 for one of a variety of reasons.</span></span> <span data-ttu-id="8355f-109">Microsoft 365가 목록에 IP 주소를 추가하면 데이터 센터를 통해 IP 주소와 모든 고객 간의 추가 통신이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="8355f-109">When Microsoft 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="8355f-110">다음과 같은 오류가 포함된 메일 메시지에 대한 응답이 수신되면 이 목록에 본인이 추가된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8355f-110">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="8355f-111">550 5.7.606-649 액세스 거부, 금지된 전송 IP [_IP 주소];_ 이 목록에서 제거를 요청하는 경우 <https://sender.office.com/> 방문하여 지침을 따르하세요.</span><span class="sxs-lookup"><span data-stu-id="8355f-111">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit <https://sender.office.com/> and follow the directions.</span></span> <span data-ttu-id="8355f-112">자세한 내용은 [Exchange Online의 전자 메일 배달되지 않은 보고서를 참조하세요.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)</span><span class="sxs-lookup"><span data-stu-id="8355f-112">For more information see [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="8355f-113">여기서  _IP address_ 는 메일 서버가 실행되는 컴퓨터의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8355f-113">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="8355f-114">목록 제거 포털을 사용하여 수신 차단된 보낸 사람 목록에서 자신을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="8355f-114">To use delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="8355f-115">웹 브라우저에서 <https://sender.office.com>으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8355f-115">In a web browser, go to <https://sender.office.com>.</span></span>

2. <span data-ttu-id="8355f-p104">페이지의 지시를 따릅니다. 오류 메시지가 전송된 전자 메일 주소와 오류 메시지에 지정된 IP 주소를 사용하고 있는지 확인합니다. 방문할 때마다 하나의 전자 메일 주소 및 하나의 IP 주소만 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8355f-p104">Follow the instructions on the page. Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message. You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="8355f-119">**전송** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8355f-119">Click **Submit**.</span></span>

    <span data-ttu-id="8355f-120">포털에서는 사용자가 제공한 전자 메일 주소로 전자 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8355f-120">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="8355f-121">The email will look like the following: ![ Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="8355f-121">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="8355f-122">목록 해제 포털을 사용하여 사용자에게 전송된 전자 메일의 확인 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8355f-122">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="8355f-123">그러면 목록 해제 포털로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="8355f-123">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="8355f-124">목록 해제 포털에서 **IP 목록 해제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8355f-124">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="8355f-125">IP 주소가 수신 차단된 보낸 사람 목록에서 제거되면 해당 IP 주소의 전자 메일 메시지가 Microsoft 365를 사용하는 받는 사람에게 배달됩니다.</span><span class="sxs-lookup"><span data-stu-id="8355f-125">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Microsoft 365.</span></span> <span data-ttu-id="8355f-126">따라서 해당 IP 주소에서 보낸 전자 메일이 악의적이지 않은지 확신해야 합니다. 그렇지 않으면 IP 주소가 다시 차단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8355f-126">So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8355f-127">최대 24시간이 걸릴 수 있습니다. 또는 제한이 제거되기 전에 결과가 크게 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8355f-127">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="8355f-128">[IP가 차단되지](create-safe-sender-lists-in-office-365.md) 않도록 EOP 및 [EOP의](outbound-spam-controls.md) 아웃바운드 스팸 보호에서 수신이 가능한 보낸 사람 목록 만들기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8355f-128">See [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in EOP](outbound-spam-controls.md) to prevent an IP from being blocked.</span></span>
