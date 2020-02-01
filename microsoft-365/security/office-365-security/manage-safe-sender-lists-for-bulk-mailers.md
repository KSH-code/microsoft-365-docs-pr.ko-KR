---
title: 대량 메일에 대해 수신 허용 - 보낸 사람 목록 관리
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: '안전한 보낸 사람 목록을 사용 하려는 경우에는 EOP (Exchange Online Protection) 및 Outlook 처리가 서로 다르게 처리 된다는 사실을 알아야 합니다. 이 서비스는 rfc 5321 보낸 사람 주소와 RFC 5322.from 주소의을 검사 하 여 수신 허용-보낸 사람 및 도메인을 고려 하 고, Outlook에서는 RFC 5322.from 주소의 주소를 사용자의 수신 허용-발신자 목록에 추가 합니다. (참고: 서비스는 차단 된 보낸 사람 주소 및 도메인에 대 한 5321 주소와 5322.from 주소의 from address)를 모두 검사 합니다.'
ms.openlocfilehash: aaede7cab2e640603c20804f4015e19f61b6c2f3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598945"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a><span data-ttu-id="a81c0-105">대량 메일에 대해 수신 허용 - 보낸 사람 목록 관리</span><span class="sxs-lookup"><span data-stu-id="a81c0-105">Manage safe sender lists for bulk mailers</span></span>

<span data-ttu-id="a81c0-106">안전한 보낸 사람 목록을 사용 하려는 경우에는 EOP (Exchange Online Protection) 및 Outlook 처리가 서로 다르게 처리 된다는 사실을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a81c0-106">If you want to use safe sender lists, you should know that Exchange Online Protection (EOP) and Outlook handle processing differently.</span></span> <span data-ttu-id="a81c0-107">Office 365 서비스는 주소와 `RFC 5321.MailFrom` `RFC 5322.From` 주소를 검사 하 여 수신 허용-보낸 사람 및 도메인을 사용 하므로 `RFC 5322.From` Outlook에서 사용자의 수신 허용-보낸 사람 목록에 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a81c0-107">The Office 365 service respects safe senders and domains by inspecting the `RFC 5321.MailFrom` address and the `RFC 5322.From` address, while Outlook adds the `RFC 5322.From` address to a user's safe sender list.</span></span> <span data-ttu-id="a81c0-108">(참고: 서비스가 차단 된 보낸 사람 `5321.MailFrom` 및 도메인 `5322.From` 에 대 한 주소와 주소를 모두 검사 합니다.)</span><span class="sxs-lookup"><span data-stu-id="a81c0-108">(Note: The service inspects both the `5321.MailFrom` address and `5322.From` address for blocked senders and domains.)</span></span>

<span data-ttu-id="a81c0-109">`RFC 5321.MailFrom address`이 주소는 `SMTP MAIL FROM` SPF 검사를 수행 하는 데 사용 되는 전자 메일 주소이 고, 메일을 배달할 수 없는 경우 반송 메시지가 배달 되는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="a81c0-109">The `SMTP MAIL FROM` address, otherwise known as the `RFC 5321.MailFrom address`, is the email address that's used to perform SPF checks, and if the mail can't be delivered, the path to which the bounced message is delivered.</span></span> <span data-ttu-id="a81c0-110">이 전자 메일 주소는 보낸 사람이 다른 `Return-Path` `Return-Path` 주소를 지정할 수 있지만 메시지 헤더의에 기본적으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a81c0-110">It's this email address that is placed into the `Return-Path` in the message headers by default, though it's possible for the sender to designate a different `Return-Path` address.</span></span>

<span data-ttu-id="a81c0-111">주소 라는 메시지 헤더의 `From:` 주소는 Outlook과 같은 메일 클라이언트에 표시 되는 전자 메일 주소입니다. `RFC 5322.From`</span><span class="sxs-lookup"><span data-stu-id="a81c0-111">The `From:` address in the message headers, otherwise known as the `RFC 5322.From` address, is the email address that is displayed in the mail client such as Outlook.</span></span>

<span data-ttu-id="a81c0-112">많은 시간과 `5321.MailFrom` `5322.From` 주소가 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="a81c0-112">Much of the time, the `5321.MailFrom` and `5322.From` addresses are the same.</span></span> <span data-ttu-id="a81c0-113">이는 사용자 간 통신에 일반적으로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a81c0-113">This is typical for person-to-person communication.</span></span> <span data-ttu-id="a81c0-114">그러나 다른 사람을 대신 하 여 전자 메일을 보내는 경우에는 주소가 서로 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81c0-114">However, when email is sent on behalf of someone else, the addresses are frequently different.</span></span> <span data-ttu-id="a81c0-115">일반적으로 대량 전자 메일 메시지에서 가장 자주 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a81c0-115">This usually happens most often for bulk email messages.</span></span>

<span data-ttu-id="a81c0-116">예를 들어 파란색 Yonder Airlines가 손 정 란 여행사를 고용 하 여 전자 메일 광고를 보내도록 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a81c0-116">For example, suppose that Blue Yonder Airlines has hired Margie's Travel to send out its email advertising.</span></span> <span data-ttu-id="a81c0-117">그런 다음 보낸 사람 blueyonder@news.blueyonderairlines.com에서 받은 편지함에 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="a81c0-117">You then get a message in your inbox from sender blueyonder@news.blueyonderairlines.com.</span></span> <span data-ttu-id="a81c0-118">이 예제의 특징은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a81c0-118">In this example:</span></span>

- <span data-ttu-id="a81c0-119">주소 `5321.MailFrom` 는 blueyonder.airlines@margiestravel.com입니다.</span><span class="sxs-lookup"><span data-stu-id="a81c0-119">The `5321.MailFrom` address is blueyonder.airlines@margiestravel.com.</span></span>

- <span data-ttu-id="a81c0-120">주소 `5322.From` 는 blueyonder@news.blueyonderairlines.com, 즉 Outlook에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81c0-120">The `5322.From` address is blueyonder@news.blueyonderairlines.com, which is what you'll see in Outlook.</span></span>

<span data-ttu-id="a81c0-121">이 메시지가 필터링 되지 않도록 하려면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81c0-121">To prevent this message from being filtered, you can:</span></span>

- <span data-ttu-id="a81c0-122">**사용자**: Outlook에서 수신 허용 `RFC 5322.From` -보낸 사람으로 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a81c0-122">**As a user**: Add the `RFC 5322.From` address as a Safe Sender in Outlook.</span></span>

- <span data-ttu-id="a81c0-123">**관리자**: [메일 흐름 규칙](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) (전송 규칙이 라고도 함)을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a81c0-123">**As an admin**: Set up a [mail flow rule](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) (also known as a transport rule).</span></span>
