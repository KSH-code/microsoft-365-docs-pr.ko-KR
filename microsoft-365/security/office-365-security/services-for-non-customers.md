---
title: 고객이 아닌 고객이 Microsoft 365로 메일을 보내는 서비스
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: 전자 메일 사용에 대한 사용자 신뢰를 유지하기 위해 Microsoft는 사용자를 보호하는 데 도움이 되는 다양한 정책 및 기술을 제공했습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3213cae1b04b3f1a1b861e8f2cfc698576013546
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206516"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a><span data-ttu-id="b6732-103">고객이 아닌 고객이 Microsoft 365로 메일을 보내는 서비스</span><span class="sxs-lookup"><span data-stu-id="b6732-103">Services for non-customers sending mail to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b6732-104">전자 메일 남용, 정크 메일 및 사기성 전자 메일(피싱)은 계속해서 전체 전자 메일 에코시스템에 부담을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-104">Email abuse, junk email, and fraudulent emails (phishing) continue to burden the entire email ecosystem.</span></span> <span data-ttu-id="b6732-105">전자 메일 사용에 대한 사용자 신뢰를 유지하기 위해 Microsoft는 사용자를 보호하기 위해 다양한 정책 및 기술을 적용했습니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-105">To help maintain user trust in the use of email, Microsoft has put various policies and technologies in place to help protect our users.</span></span> <span data-ttu-id="b6732-106">그러나 Microsoft는 합법적인 전자 메일이 부정적인 영향을 받지 않는 것으로 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-106">However, Microsoft understands that legitimate email should not be negatively affected.</span></span> <span data-ttu-id="b6732-107">따라서 보낸 사람이 보내는 신뢰도에 대해 사전 관리하여 Microsoft 365 사용자에게 전자 메일을 배달하는 기능을 개선하는 데 도움이 되는 서비스 제품군을 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-107">Therefore, we have established a suite of services to help senders improve their ability to deliver email to Microsoft 365 users by proactively managing their sending reputation.</span></span>

<span data-ttu-id="b6732-108">이 개요는 고객이 아니어도 조직에 제공하는 혜택에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-108">This overview provides information about benefits we provide to your organization even if you aren't a customer.</span></span>

## <a name="sender-solutions"></a><span data-ttu-id="b6732-109">보낸 사람 솔루션</span><span class="sxs-lookup"><span data-stu-id="b6732-109">Sender solutions</span></span>

****

|<span data-ttu-id="b6732-110">서비스</span><span class="sxs-lookup"><span data-stu-id="b6732-110">Service</span></span>|<span data-ttu-id="b6732-111">이점</span><span class="sxs-lookup"><span data-stu-id="b6732-111">Benefits</span></span>|
|---|---|
|<span data-ttu-id="b6732-112">이 온라인 도움말 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="b6732-112">This online help content</span></span>|<span data-ttu-id="b6732-113">다음을 제공:</span><span class="sxs-lookup"><span data-stu-id="b6732-113">Provides:</span></span> <ul><li><span data-ttu-id="b6732-114">EOP 사용자에게 통신 전달과 관련된 질문의 시작 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-114">A starting point for any questions related to delivering communications to EOP users.</span></span></li><li><span data-ttu-id="b6732-115">정책 및 요구 사항을 포함하는 간단한 온라인 가이드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-115">Includes a simple online guide with our policies and requirements.</span></span></li><li><span data-ttu-id="b6732-116">Microsoft에서 사용하는 정크 메일 필터 및 인증 기술에 대한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-116">An overview of the junk email filters and authentication technologies employed by Microsoft.</span></span></li><ul>|
|[<span data-ttu-id="b6732-117">Microsoft 지원</span><span class="sxs-lookup"><span data-stu-id="b6732-117">Microsoft support</span></span>](#microsoft-support)|<span data-ttu-id="b6732-118">배달 문제에 대한 자가 도움말 및 에스컬레이터 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-118">Provides self-help and escalation support for delivery issues.</span></span>|
|[<span data-ttu-id="b6732-119">스팸 방지 IP 목록 목록 포털</span><span class="sxs-lookup"><span data-stu-id="b6732-119">Anti-Spam IP Delist Portal</span></span>](#anti-spam-ip-delist-portal)|<span data-ttu-id="b6732-120">IP 목록 목록 목록 요청을 제출하기 위한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-120">A tool to submit IP delist request.</span></span> <span data-ttu-id="b6732-121">이 요청을 제출하기 전에 해당 IP에서 시작된 추가 메일이 악의적이지 않은지 확인해야 하는 것은 보낸 사람 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-121">Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.</span></span>|
|[<span data-ttu-id="b6732-122">Exchange Online에서 시작된 정크 메일에 대한 남용 및 스팸 보고</span><span class="sxs-lookup"><span data-stu-id="b6732-122">Abuse and spam reporting for junk email originating from Exchange Online</span></span>](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|<span data-ttu-id="b6732-123">스팸 및 기타 원치 않는 메일이 Exchange Online에서 전송되지 않도록 하여 인터넷과 메일 시스템이 지루해지지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-123">Keeps spam and other unwanted mail from being sent from Exchange Online and cluttering up the internet and your mail system.</span></span>|
|

## <a name="microsoft-support"></a><span data-ttu-id="b6732-124">Microsoft 지원</span><span class="sxs-lookup"><span data-stu-id="b6732-124">Microsoft support</span></span>

<span data-ttu-id="b6732-125">Microsoft는 Microsoft 365 받는 사람에게 메일을 보내는 데 문제가 있는 사용자에 대한 몇 가지 지원 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-125">Microsoft offers several support options for people having trouble sending mail to Microsoft 365 recipients.</span></span> <span data-ttu-id="b6732-126">다음의 작업을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-126">We recommend that you:</span></span>

- <span data-ttu-id="b6732-127">수신한 모든 배달 못 한 보고서의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-127">Follow the instructions in any non-delivery report you receive.</span></span>

- <span data-ttu-id="b6732-128">[Office 365로](troubleshooting-mail-sent-to-office-365.md)보낸 메일 문제 해결에서 고객이 아닌 고객이 발생하는 가장 일반적인 문제를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-128">Check out the most common problems that non-customers encounter in [Troubleshooting mail sent to Office 365](troubleshooting-mail-sent-to-office-365.md).</span></span>

- <span data-ttu-id="b6732-129">Microsoft [365](https://sender.office.com) 목록 제거 포털을 사용하여 IP가 차단된 보낸 사람 목록에서 제거된 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-129">Use the [Microsoft 365 delist portal](https://sender.office.com) to submit a request to have your IP removed from the blocked sender's list.</span></span>

- <span data-ttu-id="b6732-130">Microsoft [커뮤니티 포럼 을 읽어 읽습니다.](https://community.office365.com/f/)</span><span class="sxs-lookup"><span data-stu-id="b6732-130">Read the [Microsoft community forums](https://community.office365.com/f/).</span></span>

- <span data-ttu-id="b6732-131">다른 방법을 사용하여 전자 메일을 보내려고 하는 고객에게 연락하여 Microsoft 지원에 문의하여 고객 대신 지원 티켓을 열게 요청하세요.</span><span class="sxs-lookup"><span data-stu-id="b6732-131">Contact the customer you're trying to email using another method and ask them to contact Microsoft Support and open a support ticket on your behalf.</span></span> <span data-ttu-id="b6732-132">경우에 따라 법적 이유로 Microsoft 지원에서 차단되는 IP 공간을 소유한 보낸 사람과 직접 통신해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-132">In some cases, for legal reasons, Microsoft Support must communicate directly with the sender who owns the IP space that is being blocked.</span></span> <span data-ttu-id="b6732-133">그러나 비 고객은 일반적으로 지원 티켓을 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-133">However, non-customers typically can't open support tickets.</span></span>

  <span data-ttu-id="b6732-134">Office 365에 대한 Microsoft 기술 지원에 대한 자세한 내용은 지원을 [참조하세요.](/office365/servicedescriptions/office-365-platform-service-description/support)</span><span class="sxs-lookup"><span data-stu-id="b6732-134">For more information about Microsoft Technical support for Office 365, see [Support](/office365/servicedescriptions/office-365-platform-service-description/support).</span></span>

## <a name="anti-spam-ip-delist-portal"></a><span data-ttu-id="b6732-135">스팸 방지 IP 목록 목록 포털</span><span class="sxs-lookup"><span data-stu-id="b6732-135">Anti-Spam IP Delist Portal</span></span>

<span data-ttu-id="b6732-136">Microsoft 365 수신이 차단된 보낸 사람 목록에서 자신을 제거하는 데 사용할 수 있는 셀프 서비스 포털입니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-136">This is a self-service portal you can use to remove yourself from the Microsoft 365 blocked senders list.</span></span> <span data-ttu-id="b6732-137">Microsoft 365에 있는 전자 메일 주소가 Microsoft 365에 있는 받는 사람에게 전자 메일을 보내려고 할 때 오류 메시지가 표시될 경우 이 포털을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="b6732-137">Use this portal if you are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365 and you don't think you should be.</span></span> <span data-ttu-id="b6732-138">자세한 내용은 [목록 해제 포털을 사용하여 수신 거부 목록에서 자신 제거](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6732-138">For more information, see [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a><span data-ttu-id="b6732-139">Exchange Online에서 시작된 정크 메일에 대한 남용 및 스팸 보고</span><span class="sxs-lookup"><span data-stu-id="b6732-139">Abuse and spam reporting for junk email originating from Exchange Online</span></span>

<span data-ttu-id="b6732-140">경우에 따라 Microsoft365는 사용 약관 및 정책을 위반하여 제3자에서 정크 메일을 보내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-140">Sometimes Microsoft365 is used by third parties to send junk email, in violation of our terms of use and policy.</span></span> <span data-ttu-id="b6732-141">Office 365에서 정크 메일을 받으면 이러한 메시지를 Microsoft에 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6732-141">If you receive any junk email from Office 365, you can report these messages to Microsoft.</span></span> <span data-ttu-id="b6732-142">자세한 내용은 Microsoft에 메시지 및 [파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="b6732-142">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>