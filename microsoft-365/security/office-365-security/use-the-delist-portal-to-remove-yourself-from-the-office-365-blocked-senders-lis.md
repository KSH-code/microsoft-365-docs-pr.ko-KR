---
title: 수신 거부 목록에서 본인 제거
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
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 목록 해제 포털을 사용 하 여 Microsoft 365 수신 거부 목록에서 자신을 제거 하는 방법에 대해 설명 합니다.
ms.openlocfilehash: 2d9dbba12740e62305e1bcfd193175659be34026
ms.sourcegitcommit: 9ea67fd2e02af760d4fb62e3d09c93b446173f9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2020
ms.locfileid: "44739235"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="5eb4b-103">목록 해제 포털을 사용하여 수신 거부 목록에서 본인 제거</span><span class="sxs-lookup"><span data-stu-id="5eb4b-103">Use the delist portal to remove yourself from the blocked senders list</span></span>

<span data-ttu-id="5eb4b-104">전자 메일 주소가 Microsoft 365에 있는 받는 사람에 게 전자 메일을 보내려고 할 때 오류 메시지가 발생 하나요?</span><span class="sxs-lookup"><span data-stu-id="5eb4b-104">Are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365?</span></span> <span data-ttu-id="5eb4b-105">오류 메시지가 나타나지 않는다고 생각 되 면 목록 해제 포털을 사용 하 여 수신 거부 목록에서 본인을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eb4b-105">If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the blocked senders list.</span></span>

## <a name="what-is-the-blocked-senders-list"></a><span data-ttu-id="5eb4b-106">수신 거부 목록 이란?</span><span class="sxs-lookup"><span data-stu-id="5eb4b-106">What is the blocked senders list?</span></span>

<span data-ttu-id="5eb4b-107">Microsoft는 수신 거부 목록을 사용하여 스팸, 스푸핑 및 피싱 공격으로부터 고객을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="5eb4b-107">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks.</span></span> <span data-ttu-id="5eb4b-108">메일 서버의 IP 주소, 즉 메일 서버가 인터넷에서 자신을 식별 하는 데 사용 하는 주소에는 다양 한 이유로 Microsoft 365의 잠재적 위협에 대 한 태그가 지정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eb4b-108">Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Microsoft 365 for one of a variety of reasons.</span></span> <span data-ttu-id="5eb4b-109">Microsoft 365이 목록에 IP 주소를 추가 하면 데이터 센터를 통해 IP 주소와 고객 간의 모든 추가 통신을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eb4b-109">When Microsoft 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="5eb4b-110">다음과 같은 오류가 포함된 메일 메시지에 대한 응답이 수신되면 이 목록에 본인이 추가된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5eb4b-110">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="5eb4b-111">550 5.7.606-649 액세스 거부, 금지 된 보낸 IP [_ip 주소_]; 이 목록에서 제거를 요청 하려면을 방문 https://sender.office.com/ 하 여 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="5eb4b-111">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit https://sender.office.com/ and follow the directions.</span></span> <span data-ttu-id="5eb4b-112">자세한 내용은 [Exchange Online의 전자 메일 배달 못 함 보고서](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5eb4b-112">For more information see [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="5eb4b-113">여기서  _IP address_는 메일 서버가 실행되는 컴퓨터의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="5eb4b-113">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="5eb4b-114">목록 해제 포털을 사용 하 여 수신 거부 목록에서 본인을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="5eb4b-114">To use delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="5eb4b-115">웹 브라우저에서 [https://sender.office.com](https://sender.office.com)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5eb4b-115">In a web browser, go to [https://sender.office.com](https://sender.office.com).</span></span>

2. <span data-ttu-id="5eb4b-116">Follow the instructions on the page.</span><span class="sxs-lookup"><span data-stu-id="5eb4b-116">Follow the instructions on the page.</span></span> <span data-ttu-id="5eb4b-117">Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message.</span><span class="sxs-lookup"><span data-stu-id="5eb4b-117">Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message.</span></span> <span data-ttu-id="5eb4b-118">You can only enter one email address and one IP address per visit.</span><span class="sxs-lookup"><span data-stu-id="5eb4b-118">You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="5eb4b-119">**전송**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5eb4b-119">Click **Submit**.</span></span>

    <span data-ttu-id="5eb4b-120">포털에서는 사용자가 제공한 전자 메일 주소로 전자 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="5eb4b-120">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="5eb4b-121">전자 메일은 다음과 같이 표시 됩니다. ![ 목록 해제 포털을 통해 요청을 제출할 때 받는 전자 메일의 스크린샷](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="5eb4b-121">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="5eb4b-122">목록 해제 포털을 사용하여 사용자에게 전송된 전자 메일의 확인 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5eb4b-122">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="5eb4b-123">그러면 목록 해제 포털로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="5eb4b-123">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="5eb4b-124">목록 해제 포털에서 **IP 목록 해제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5eb4b-124">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="5eb4b-125">차단 된 보낸 사람 목록에서 IP 주소를 제거한 후에는 해당 IP 주소에서 보낸 전자 메일 메시지가 Microsoft 365을 사용 하는 받는 사람에 게 배달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5eb4b-125">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Microsoft 365.</span></span> <span data-ttu-id="5eb4b-126">따라서 해당 IP 주소에서 보낸 전자 메일은 악성이 되거나 악성 메일이 아닐 수도 있습니다. 그렇지 않으면 IP 주소가 다시 차단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eb4b-126">So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5eb4b-127">제한이 제거 되기 전에 최대 24 시간이 걸릴 수도 있고 결과가 크게 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eb4b-127">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="5eb4b-128">IP가 차단 되지 않도록 하려면 EOP 및 [EOP의 아웃 바운드 스팸 방지](outbound-spam-controls.md) [에서 수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5eb4b-128">See [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in EOP](outbound-spam-controls.md) to prevent an IP from being blocked.</span></span>
