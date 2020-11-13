---
title: 비 고객을 위한 Microsoft 365 메일을 보내는 서비스
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: 전자 메일을 사용할 때 사용자의 신뢰를 유지 하기 위해 Microsoft는 사용자를 보호 하기 위한 다양 한 정책 및 기술을 배치 했습니다.
ms.openlocfilehash: 478f94d2ed1a03253168486d48fb2b2df57a6a5e
ms.sourcegitcommit: 9546708a5506fdbadbfe2500cbf1bd1aeaec6fcb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49021028"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a><span data-ttu-id="f32e1-103">비 고객을 위한 Microsoft 365 메일을 보내는 서비스</span><span class="sxs-lookup"><span data-stu-id="f32e1-103">Services for non-customers sending mail to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f32e1-104">전자 메일 남용, 정크 메일 및 사기성 전자 메일 (피싱)은 전체 전자 메일 에코에 부담을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-104">Email abuse, junk email, and fraudulent emails (phishing) continue to burden the entire email ecosystem.</span></span> <span data-ttu-id="f32e1-105">전자 메일을 사용할 때 사용자의 신뢰를 유지 하기 위해 Microsoft는 사용자를 보호 하기 위한 다양 한 정책과 기술을 마련 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-105">To help maintain user trust in the use of email, Microsoft has put various policies and technologies in place to help protect our users.</span></span> <span data-ttu-id="f32e1-106">그러나 Microsoft는 합법적인 전자 메일이 부정적인 영향을 받지 않도록 인식 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-106">However, Microsoft understands that legitimate email should not be negatively affected.</span></span> <span data-ttu-id="f32e1-107">따라서 전송 신뢰도를 사전에 관리 하 여 보낸 사람이 Microsoft 365 사용자에 게 전자 메일을 배달 하는 기능을 개선 하는 데 도움이 되는 서비스 모음을 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-107">Therefore, we have established a suite of services to help senders improve their ability to deliver email to Microsoft 365 users by proactively managing their sending reputation.</span></span>

<span data-ttu-id="f32e1-108">이 개요에서는 고객이 아닌 경우에도 조직에 제공 하는 혜택에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-108">This overview provides information about benefits we provide to your organization even if you aren't a customer.</span></span>

## <a name="sender-solutions"></a><span data-ttu-id="f32e1-109">보낸 사람 솔루션</span><span class="sxs-lookup"><span data-stu-id="f32e1-109">Sender solutions</span></span>

****

|<span data-ttu-id="f32e1-110">서비스</span><span class="sxs-lookup"><span data-stu-id="f32e1-110">Service</span></span>|<span data-ttu-id="f32e1-111">이점</span><span class="sxs-lookup"><span data-stu-id="f32e1-111">Benefits</span></span>|
|---|---|
|<span data-ttu-id="f32e1-112">온라인 도움말 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="f32e1-112">This online help content</span></span>|<span data-ttu-id="f32e1-113">단계별로</span><span class="sxs-lookup"><span data-stu-id="f32e1-113">Provides:</span></span> <ul><li><span data-ttu-id="f32e1-114">EOP 사용자에 게 통신을 제공 하는 것과 관련 된 질문에 대 한 시작 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-114">A starting point for any questions related to delivering communications to EOP users.</span></span></li><li><span data-ttu-id="f32e1-115">여기에는 정책과 요구 사항이 포함 된 간단한 온라인 가이드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-115">Includes a simple online guide with our policies and requirements.</span></span></li><li><span data-ttu-id="f32e1-116">Microsoft에서 채택 하 고 있는 정크 메일 필터 및 인증 기술에 대 한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-116">An overview of the junk email filters and authentication technologies employed by Microsoft.</span></span></li><ul>|
|[<span data-ttu-id="f32e1-117">Microsoft 지원</span><span class="sxs-lookup"><span data-stu-id="f32e1-117">Microsoft support</span></span>](#microsoft-support)|<span data-ttu-id="f32e1-118">배달 문제에 대 한 자가 진단 및 에스컬레이션 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-118">Provides self-help and escalation support for delivery issues.</span></span>|
|[<span data-ttu-id="f32e1-119">스팸 방지 IP 목록 포털</span><span class="sxs-lookup"><span data-stu-id="f32e1-119">Anti-Spam IP Delist Portal</span></span>](#anti-spam-ip-delist-portal)|<span data-ttu-id="f32e1-120">IP 목록 요청을 제출 하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-120">A tool to submit IP delist request.</span></span> <span data-ttu-id="f32e1-121">이 요청을 제출 하기 전에 해당 IP가 보낸 모든 메일이 악의적이 든 악의적인 지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-121">Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.</span></span>|
|[<span data-ttu-id="f32e1-122">Exchange Online에서 보내는 정크 메일에 대 한 불건전 및 스팸 보고</span><span class="sxs-lookup"><span data-stu-id="f32e1-122">Abuse and spam reporting for junk email originating from Exchange Online</span></span>](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|<span data-ttu-id="f32e1-123">스팸 및 기타 원치 않는 메일이 Exchange Online에서 전송 되 고 인터넷 및 메일 시스템을 복잡 하 게 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-123">Keeps spam and other unwanted mail from being sent from Exchange Online and cluttering up the internet and your mail system.</span></span>|
|

## <a name="microsoft-support"></a><span data-ttu-id="f32e1-124">Microsoft 지원</span><span class="sxs-lookup"><span data-stu-id="f32e1-124">Microsoft support</span></span>

<span data-ttu-id="f32e1-125">Microsoft는 Microsoft 365 받는 사람에 게 메일을 보낼 수 없는 사용자를 위한 몇 가지 지원 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-125">Microsoft offers several support options for people having trouble sending mail to Microsoft 365 recipients.</span></span> <span data-ttu-id="f32e1-126">다음의 작업을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-126">We recommend that you:</span></span>

- <span data-ttu-id="f32e1-127">수신 하는 배달 못 함 보고서 (들)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-127">Follow the instructions in any non-delivery report you receive.</span></span>

- <span data-ttu-id="f32e1-128">[Office 365로 전송 되는 메일 문제 해결](troubleshooting-mail-sent-to-office-365.md)에서 고객이 직면 하 게 되는 가장 일반적인 문제를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-128">Check out the most common problems that non-customers encounter in [Troubleshooting mail sent to Office 365](troubleshooting-mail-sent-to-office-365.md).</span></span>

- <span data-ttu-id="f32e1-129">[Microsoft 365 목록 해제 포털](https://sender.office.com) 을 사용 하 여 수신 거부 목록에서 IP를 제거 하는 요청을 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-129">Use the [Microsoft 365 delist portal](https://sender.office.com) to submit a request to have your IP removed from the blocked sender's list.</span></span>

- <span data-ttu-id="f32e1-130">[Microsoft 커뮤니티 포럼](https://community.office365.com/f/)을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-130">Read the [Microsoft community forums](https://community.office365.com/f/).</span></span>

- <span data-ttu-id="f32e1-131">다른 방법을 사용 하 여 전자 메일을 보내려고 하는 고객에 게 문의 하 여 사용자에 게 Microsoft 지원에 문의 하 여 지원 티켓을 열도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-131">Contact the customer you're trying to email using another method and ask them to contact Microsoft Support and open a support ticket on your behalf.</span></span> <span data-ttu-id="f32e1-132">법적 이유가 있는 경우 Microsoft Support는 차단 되는 IP 공간을 소유한 보낸 사람과 직접 통신 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-132">In some cases, for legal reasons, Microsoft Support must communicate directly with the sender who owns the IP space that is being blocked.</span></span> <span data-ttu-id="f32e1-133">그러나 일반적으로 고객은 지원 티켓을 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-133">However, non-customers typically can't open support tickets.</span></span>

  <span data-ttu-id="f32e1-134">Office 365에 대 한 Microsoft 기술 지원에 대 한 자세한 내용은 [지원](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support)항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f32e1-134">For more information about Microsoft Technical support for Office 365, see [Support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support).</span></span>

## <a name="anti-spam-ip-delist-portal"></a><span data-ttu-id="f32e1-135">스팸 방지 IP 목록 포털</span><span class="sxs-lookup"><span data-stu-id="f32e1-135">Anti-Spam IP Delist Portal</span></span>

<span data-ttu-id="f32e1-136">이는 Microsoft 365 수신 거부 목록에서 자신을 제거 하는 데 사용할 수 있는 셀프 서비스 포털입니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-136">This is a self-service portal you can use to remove yourself from the Microsoft 365 blocked senders list.</span></span> <span data-ttu-id="f32e1-137">전자 메일 주소가 Microsoft 365에 있는 받는 사람에 게 전자 메일을 보내려고 할 때 오류 메시지가 표시 되는 경우에는이 포털을 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f32e1-137">Use this portal if you are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365 and you don't think you should be.</span></span> <span data-ttu-id="f32e1-138">자세한 내용은 [목록 해제 포털을 사용하여 수신 거부 목록에서 자신 제거](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f32e1-138">For more information, see [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a><span data-ttu-id="f32e1-139">Exchange Online에서 보내는 정크 메일에 대 한 불건전 및 스팸 보고</span><span class="sxs-lookup"><span data-stu-id="f32e1-139">Abuse and spam reporting for junk email originating from Exchange Online</span></span>

<span data-ttu-id="f32e1-140">제 3 자가 사용 약관을 위반 하 여 정크 메일을 보내는 경우도 가끔 Microsoft365.</span><span class="sxs-lookup"><span data-stu-id="f32e1-140">Sometimes Microsoft365 is used by third parties to send junk email, in violation of our terms of use and policy.</span></span> <span data-ttu-id="f32e1-141">Office 365에서 정크 메일을 받으면 이러한 메시지를 Microsoft에 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f32e1-141">If you receive any junk email from Office 365, you can report these messages to Microsoft.</span></span> <span data-ttu-id="f32e1-142">자세한 내용은 [Microsoft에 메시지 및 파일 보고서](report-junk-email-messages-to-microsoft.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f32e1-142">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>
