---
title: SPF(Sender Policy Framework)가 스푸핑을 방지하는 방법
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/15/2016
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365에서 DNS의 SPF(Sender Policy Framework) TXT 레코드를 사용하여 대상 전자 메일 시스템이 사용자 지정 도메인에서 보낸 메시지를 신뢰하도록 하는 방법을 알아보습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 972f283f6138bafcebd877a19f0bfc429e0eed03
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071399"
---
# <a name="how-microsoft-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a><span data-ttu-id="5f6a6-103">Microsoft 365에서 SPF(Sender Policy Framework)를 사용하여 스푸핑을 방지하는 방법</span><span class="sxs-lookup"><span data-stu-id="5f6a6-103">How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5f6a6-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="5f6a6-104">**Applies to**</span></span>
- [<span data-ttu-id="5f6a6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5f6a6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5f6a6-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="5f6a6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5f6a6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f6a6-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

 <span data-ttu-id="5f6a6-108">**요약:** 이 문서에서는 Microsoft 365에서 DNS의 SPF(Sender Policy Framework) TXT 레코드를 사용하여 대상 전자 메일 시스템이 사용자 지정 도메인에서 보낸 메시지를 신뢰하도록 하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-108">**Summary:** This article describes how Microsoft 365 uses the Sender Policy Framework (SPF) TXT record in DNS to ensure that destination email systems trust messages sent from your custom domain.</span></span> <span data-ttu-id="5f6a6-109">이는 Microsoft 365에서 보낸 아웃바운드 메일에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-109">This applies to outbound mail sent from Microsoft 365.</span></span> <span data-ttu-id="5f6a6-110">Microsoft 365에서 Microsoft 365 내의 받는 사람에게 보낸 메시지는 항상 SPF를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-110">Messages sent from Microsoft 365 to a recipient within Microsoft 365 will always pass SPF.</span></span>

<span data-ttu-id="5f6a6-111">SPF TXT 레코드는 전자 메일 메시지가 전송되는 도메인 이름을 확인하여 스푸핑 및 피싱을 방지하는 데 도움이 되는 DNS 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-111">An SPF TXT record is a DNS record that helps prevent spoofing and phishing by verifying the domain name from which email messages are sent.</span></span> <span data-ttu-id="5f6a6-112">SPF는 보내는 도메인의 주장된 소유자에 대해 보낸 사람 IP 주소를 확인하여 전자 메일 메시지의 출처를 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-112">SPF validates the origin of email messages by verifying the IP address of the sender against the alleged owner of the sending domain.</span></span>

> [!NOTE]
> <span data-ttu-id="5f6a6-113">SPF 레코드 유형은 2014년 IETF(Internet Engineering Task Force)에서 더 이상 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-113">SPF record types were deprecated by the Internet Engineering Task Force (IETF) in 2014.</span></span> <span data-ttu-id="5f6a6-114">대신 DNS의 TXT 레코드를 사용하여 SPF 정보를 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-114">Instead, ensure that you use TXT records in DNS to publish your SPF information.</span></span> <span data-ttu-id="5f6a6-115">이 문서의 나머지부분에서는 명확성을 위해 SPF TXT 레코드를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-115">The rest of this article uses the term SPF TXT record for clarity.</span></span>

<span data-ttu-id="5f6a6-116">도메인 관리자는 DNS의 TXT 레코드에 SPF 정보를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-116">Domain administrators publish SPF information in TXT records in DNS.</span></span> <span data-ttu-id="5f6a6-117">SPF 정보는 권한이 부여된 아웃바운드 전자 메일 서버를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-117">The SPF information identifies authorized outbound email servers.</span></span> <span data-ttu-id="5f6a6-118">대상 전자 메일 시스템은 권한 있는 아웃바운드 전자 메일 서버에서 메시지를 보냈는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-118">Destination email systems verify that messages originate from authorized outbound email servers.</span></span> <span data-ttu-id="5f6a6-119">이미 SPF에 익숙하거나 간단한 배포가 있으며 Microsoft 365용 DNS의 SPF TXT 레코드에 포함할 것을 알아야 하는 경우 스푸핑을 방지하기 위해 [Microsoft 365에서 SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)설정으로 이동하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-119">If you are already familiar with SPF, or you have a simple deployment, and just need to know what to include in your SPF TXT record in DNS for Microsoft 365, you can go to [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="5f6a6-120">Microsoft 365에서 완전히 호스팅되는 배포가 없는 경우 또는 SPF 작동 방식 또는 Microsoft 365 SPF 문제 해결 방법에 대한 자세한 정보를 원할 경우 계속 읽어 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-120">If you do not have a deployment that is fully-hosted in Microsoft 365, or you want more information about how SPF works or how to troubleshoot SPF for Microsoft 365, keep reading.</span></span>

> [!NOTE]
> <span data-ttu-id="5f6a6-121">이전에는 SharePoint Online을 사용하는 경우 사용자 지정 도메인에 다른 SPF TXT 레코드를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-121">Previously, you had to add a different SPF TXT record to your custom domain if you also used SharePoint Online.</span></span> <span data-ttu-id="5f6a6-122">이 작업은 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-122">This is no longer required.</span></span> <span data-ttu-id="5f6a6-123">이렇게 변경하면 정크 메일 폴더에 SharePoint Online 알림 메시지가 표시될 위험이 줄어 듭니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-123">This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder.</span></span> <span data-ttu-id="5f6a6-124">즉시 변경할 필요는 없지만 "너무 많은 코드 업데이트" 오류가 발생하는 경우 스푸핑을 방지하기 위해 [Microsoft 365에서 SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)설정에 설명된 바와 같이 SPF TXT 레코드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-124">You do not need to make any changes immediately, but if you receive the "too many lookups" error, modify your SPF TXT record as described in [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span>

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-microsoft-365"></a><span data-ttu-id="5f6a6-125">Microsoft 365에서 SPF가 스푸핑 및 피싱을 방지하는 방법</span><span class="sxs-lookup"><span data-stu-id="5f6a6-125">How SPF works to prevent spoofing and phishing in Microsoft 365</span></span>
<span data-ttu-id="5f6a6-126"><a name="HowSPFWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6a6-126"><a name="HowSPFWorks"> </a></span></span>

<span data-ttu-id="5f6a6-127">SPF는 보낸 사람이 도메인을 대신하여 보낼 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-127">SPF determines whether or not a sender is permitted to send on behalf of a domain.</span></span> <span data-ttu-id="5f6a6-128">보낸 사람이 이를 허용하지 않는 경우, 즉 전자 메일이 받는 서버에서 SPF 확인에 실패하면 해당 서버에 구성된 스팸 정책에 따라 메시지로 할 작업을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-128">If the sender is not permitted to do so, that is, if the email fails the SPF check on the receiving server, the spam policy configured on that server determines what to do with the message.</span></span>

<span data-ttu-id="5f6a6-129">각 SPF TXT 레코드에는 SPF TXT 레코드로 선언, 도메인에서 메일을 보낼 수 있는 IP 주소 및 도메인을 대신하여 보낼 수 있는 외부 도메인 및 적용 규칙의 세 부분으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-129">Each SPF TXT record contains three parts: the declaration that it is an SPF TXT record, the IP addresses that are allowed to send mail from your domain and the external domains that can send on your domain's behalf, and an enforcement rule.</span></span> <span data-ttu-id="5f6a6-130">유효한 SPF TXT 레코드에 세 가지가 모두 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-130">You need all three in a valid SPF TXT record.</span></span> <span data-ttu-id="5f6a6-131">이 문서에서는 SPF TXT 레코드를 구성하는 방법을 설명하고 Microsoft 365에서 서비스 작업을 위한 모범 사례를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-131">This article describes how you form your SPF TXT record and provides best practices for working with the services in Microsoft 365.</span></span> <span data-ttu-id="5f6a6-132">DNS에 레코드를 게시하기 위해 도메인 등록 기관과 함께 작업하는 방법에 대한 링크도 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-132">Links to instructions on working with your domain registrar to publish your record to DNS are also provided.</span></span>

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a><span data-ttu-id="5f6a6-133">SPF 기본 사항: 사용자 지정 도메인에서 보낼 수 있는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="5f6a6-133">SPF basics: IP addresses allowed to send from your custom domain</span></span>
<span data-ttu-id="5f6a6-134"><a name="SPFBasicsIPaddresses"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6a6-134"><a name="SPFBasicsIPaddresses"> </a></span></span>

<span data-ttu-id="5f6a6-135">SPF 규칙에 대한 기본 구문을 살펴보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-135">Take a look at the basic syntax for an SPF rule:</span></span>

<span data-ttu-id="5f6a6-136">v=spf1 \<IP\>\<enforcement rule\></span><span class="sxs-lookup"><span data-stu-id="5f6a6-136">v=spf1 \<IP\> \<enforcement rule\></span></span>

<span data-ttu-id="5f6a6-137">예를 들어 다음 SPF 규칙이 다음과 같은 contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-137">For example, let's say the following SPF rule exists for contoso.com:</span></span>

<span data-ttu-id="5f6a6-138">v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\>\<enforcement rule\></span><span class="sxs-lookup"><span data-stu-id="5f6a6-138">v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\> \<enforcement rule\></span></span>

<span data-ttu-id="5f6a6-139">이 예에서 SPF 규칙은 받는 전자 메일 서버에서 다음 도메인에 대한 이러한 IP 주소의 메일만 수락할 수 contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-139">In this example, the SPF rule instructs the receiving email server to only accept mail from these IP addresses for the domain contoso.com:</span></span>

- <span data-ttu-id="5f6a6-140">IP 주소 #1</span><span class="sxs-lookup"><span data-stu-id="5f6a6-140">IP address #1</span></span>

- <span data-ttu-id="5f6a6-141">IP 주소 #2</span><span class="sxs-lookup"><span data-stu-id="5f6a6-141">IP address #2</span></span>

- <span data-ttu-id="5f6a6-142">IP 주소 #3</span><span class="sxs-lookup"><span data-stu-id="5f6a6-142">IP address #3</span></span>

<span data-ttu-id="5f6a6-143">이 SPF 규칙은 받는 전자 메일 서버에서 메시지가 contoso.com IP 주소 중 하나에서 온 것이 아닌 경우 받는 서버에서 메시지에 적용 규칙을 적용해야 한다고 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-143">This SPF rule tells the receiving email server that if a message comes from contoso.com, but not from one of these three IP addresses, the receiving server should apply the enforcement rule to the message.</span></span> <span data-ttu-id="5f6a6-144">적용 규칙은 일반적으로 다음 옵션 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-144">The enforcement rule is usually one of these options:</span></span>

- <span data-ttu-id="5f6a6-145">**하드 실패.**</span><span class="sxs-lookup"><span data-stu-id="5f6a6-145">**Hard fail.**</span></span> <span data-ttu-id="5f6a6-146">메시지 봉투에 '하드 실패'가 있는 메시지를 표시한 다음 이 유형의 메시지에 대해 받는 서버의 구성된 스팸 정책을 따르도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-146">Mark the message with 'hard fail' in the message envelope and then follow the receiving server's configured spam policy for this type of message.</span></span>

- <span data-ttu-id="5f6a6-147">**소프트 실패.**</span><span class="sxs-lookup"><span data-stu-id="5f6a6-147">**Soft fail.**</span></span> <span data-ttu-id="5f6a6-148">메시지 봉투에 'soft fail'으로 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-148">Mark the message with 'soft fail' in the message envelope.</span></span> <span data-ttu-id="5f6a6-149">일반적으로 전자 메일 서버는 이러한 메시지를 배달하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-149">Typically, email servers are configured to deliver these messages anyway.</span></span> <span data-ttu-id="5f6a6-150">대부분의 최종 사용자는 이 표시를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-150">Most end users do not see this mark.</span></span>

- <span data-ttu-id="5f6a6-151">**중립.**</span><span class="sxs-lookup"><span data-stu-id="5f6a6-151">**Neutral.**</span></span> <span data-ttu-id="5f6a6-152">아무 것도 하지 않습니다. 즉, 메시지 봉투를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-152">Do nothing, that is, do not mark the message envelope.</span></span> <span data-ttu-id="5f6a6-153">일반적으로 테스트 목적으로 예약되어 있으며 거의 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-153">This is usually reserved for testing purposes and is rarely used.</span></span>

<span data-ttu-id="5f6a6-154">다음 예제에서는 서로 다른 상황에서 SPF가 작동하는 방법을 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-154">The following examples show how SPF works in different situations.</span></span> <span data-ttu-id="5f6a6-155">이 예제에서는 contoso.com 보낸 사람이고 woodgrovebank.com 받는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-155">In these examples, contoso.com is the sender and woodgrovebank.com is the receiver.</span></span>

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a><span data-ttu-id="5f6a6-156">예제 1: 보낸 사람에서 받는 사람으로 직접 전송된 메시지의 전자 메일 인증</span><span class="sxs-lookup"><span data-stu-id="5f6a6-156">Example 1: Email authentication of a message sent directly from sender to receiver</span></span>
<span data-ttu-id="5f6a6-157"><a name="spfExample1"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6a6-157"><a name="spfExample1"> </a></span></span>

<span data-ttu-id="5f6a6-158">SPF는 보낸 사람에서 받는 사람으로의 경로가 직접적인 경우 가장 잘 작동합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-158">SPF works best when the path from sender to receiver is direct, for example:</span></span>

![서버 간에 직접 전자 메일이 전송될 때 SPF에서 전자 메일을 인증하는 방법을 보여주는 다이어그램입니다.](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

<span data-ttu-id="5f6a6-160">메시지를 woodgrovebank.com 경우 IP 주소가 #1 SPF TXT 레코드에 contoso.com 메시지가 SPF 검사를 통과하고 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-160">When woodgrovebank.com receives the message, if IP address #1 is in the SPF TXT record for contoso.com, the message passes the SPF check and is authenticated.</span></span>

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a><span data-ttu-id="5f6a6-161">예제 2: 스푸핑된 보낸 사람 주소가 SPF 검사에 실패</span><span class="sxs-lookup"><span data-stu-id="5f6a6-161">Example 2: Spoofed sender address fails the SPF check</span></span>
<span data-ttu-id="5f6a6-162"><a name="spfExample2"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6a6-162"><a name="spfExample2"> </a></span></span>

<span data-ttu-id="5f6a6-163">피싱 사용자가 다음을 통해 스푸핑하는 방법을 contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-163">Suppose a phisher finds a way to spoof contoso.com:</span></span>

![스푸핑된 서버에서 보낸 전자 메일을 SPF에서 인증하는 방법을 보여주는 다이어그램입니다.](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

<span data-ttu-id="5f6a6-165">IP 주소 #12 contoso.com의 SPF TXT 레코드에 있지 않은 경우 메시지가 SPF 검사에 실패하고 수신자가 이를 스팸으로 표시하기로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-165">Since IP address #12 is not in contoso.com's SPF TXT record, the message fails the SPF check and the receiver may choose to mark it as spam.</span></span>

### <a name="example-3-spf-and-forwarded-messages"></a><span data-ttu-id="5f6a6-166">예제 3: SPF 및 전달된 메시지</span><span class="sxs-lookup"><span data-stu-id="5f6a6-166">Example 3: SPF and forwarded messages</span></span>
<span data-ttu-id="5f6a6-167"><a name="spfExample3"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6a6-167"><a name="spfExample3"> </a></span></span>

<span data-ttu-id="5f6a6-168">SPF의 한 가지 단점은 전자 메일이 전달된 경우 작동하지 않는다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-168">One drawback of SPF is that it doesn't work when an email has been forwarded.</span></span> <span data-ttu-id="5f6a6-169">예를 들어 woodgrovebank.com 계정으로 모든 전자 메일을 보내기 위한 전달 outlook.com 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-169">For example, suppose the user at woodgrovebank.com has set up a forwarding rule to send all email to an outlook.com account:</span></span>

![메시지가 전달될 때 SPF에서 전자 메일을 인증할 수 없는 상황을 보여주는 다이어그램입니다.](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

<span data-ttu-id="5f6a6-171">메시지는 원래 woodgrovebank.com 때 SPF 검사를 통과했지만 ip outlook.com contoso.com의 SPF TXT 레코드에 #25 때문에 SPF 검사에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-171">The message originally passes the SPF check at woodgrovebank.com but it fails the SPF check at outlook.com because IP #25 is not in contoso.com's SPF TXT record.</span></span> <span data-ttu-id="5f6a6-172">Outlook.com 메시지가 스팸으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-172">Outlook.com might then mark the message as spam.</span></span> <span data-ttu-id="5f6a6-173">이 문제를 해결하려면 SPF를 DKIM 및 DMARC와 같은 다른 전자 메일 인증 방법과 함께 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-173">To work around this problem, use SPF in conjunction with other email authentication methods such as DKIM and DMARC.</span></span>

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a><span data-ttu-id="5f6a6-174">SPF 기본 사항: 도메인을 대신하여 메일을 보낼 수 있는 타사 도메인 포함</span><span class="sxs-lookup"><span data-stu-id="5f6a6-174">SPF basics: Including third-party domains that can send mail on behalf of your domain</span></span>
<span data-ttu-id="5f6a6-175"><a name="SPFBasicsIncludes"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6a6-175"><a name="SPFBasicsIncludes"> </a></span></span>

<span data-ttu-id="5f6a6-176">IP 주소 외에도 도메인을 보낸 사람으로 포함하도록 SPF TXT 레코드를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-176">In addition to IP addresses, you can also configure your SPF TXT record to include domains as senders.</span></span> <span data-ttu-id="5f6a6-177">이러한 명령문은 SPF TXT 레코드에 "include" 문으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-177">These are added to the SPF TXT record as "include" statements.</span></span> <span data-ttu-id="5f6a6-178">예를 들어 contoso.com 메일 서버가 소유하는 메일 서버의 모든 IP 주소를 contoso.net contoso.org 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-178">For example, contoso.com might want to include all of the IP addresses of the mail servers from contoso.net and contoso.org which it also owns.</span></span> <span data-ttu-id="5f6a6-179">이렇게 contoso.com 다음과 같은 SPF TXT 레코드를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-179">To do this, contoso.com publishes an SPF TXT record that looks like this:</span></span>

```text
v=spf1 include:contoso.net include:contoso.org -all
```

<span data-ttu-id="5f6a6-180">받는 서버에서 DNS에 이 레코드가 표시되어 있는 경우 DNS에 대한 SPF TXT 레코드에 대한 DNS contoso.net 수행한 다음 CONTOSO.ORG. 레코드 내에서 contoso.net 또는 contoso.org 포함 문을 찾으면 해당 문도 따라가게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-180">When the receiving server sees this record in DNS, it also performs a DNS lookup on the SPF TXT record for contoso.net and then for contoso.org. If it finds an additional include statement within the records for contoso.net or contoso.org, it will follow those too.</span></span> <span data-ttu-id="5f6a6-181">서비스 거부 공격을 방지하기 위해 단일 전자 메일 메시지에 대한 최대 DNS 쿼리 수는 10개입니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-181">In order to help prevent denial of service attacks, the maximum number of DNS lookups for a single email message is 10.</span></span> <span data-ttu-id="5f6a6-182">각 include 문은 추가 DNS 쿼리를 나타내는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-182">Each include statement represents an additional DNS lookup.</span></span> <span data-ttu-id="5f6a6-183">메시지가 10 제한을 초과하면 메시지가 SPF에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-183">If a message exceeds the 10 limit, the message fails SPF.</span></span> <span data-ttu-id="5f6a6-184">메시지가 이 제한에 도달하면 받는 서버가 구성된 방식에 따라 보낸 사람이 메시지가 "너무 많은 수의 응답"을 생성하거나 "메시지의 최대 홉 수가 초과했습니다."라는 메시지가 표시될 수 있습니다( 이 메시지는 쿼리 루프가 반복되고 DNS 시간 제한을 초과할 때 실행될 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="5f6a6-184">Once a message reaches this limit, depending on the way the receiving server is configured, the sender may get a message that says the message generated "too many lookups" or that the "maximum hop count for the message has been exceeded" (which can happen when the lookups loop and surpass the DNS timeout).</span></span> <span data-ttu-id="5f6a6-185">이를 방지하는 방법에 대한 팁은 [문제 해결: Microsoft 365의 SPF 모범 사례를 참조하세요.](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)</span><span class="sxs-lookup"><span data-stu-id="5f6a6-185">For tips on how to avoid this, see [Troubleshooting: Best practices for SPF in Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>

## <a name="requirements-for-your-spf-txt-record-and-microsoft-365"></a><span data-ttu-id="5f6a6-186">SPF TXT 레코드 및 Microsoft 365에 대한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f6a6-186">Requirements for your SPF TXT record and Microsoft 365</span></span>
<span data-ttu-id="5f6a6-187"><a name="SPFReqsinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6a6-187"><a name="SPFReqsinO365"> </a></span></span>

<span data-ttu-id="5f6a6-188">Microsoft 365를 설정할 때 메일을 설정한 경우 Microsoft 메시징 서버를 도메인의 합법적인 메일 원본으로 식별하는 SPF TXT 레코드를 이미 만들었다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-188">If you set up mail when you set up Microsoft 365, you already created an SPF TXT record that identifies the Microsoft messaging servers as a legitimate source of mail for your domain.</span></span> <span data-ttu-id="5f6a6-189">이 레코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-189">This record probably looks like this:</span></span>

```text
v=spf1 include:spf.protection.outlook.com -all
```

<span data-ttu-id="5f6a6-190">완전히 호스팅된 고객인 경우, 즉 아웃바운드 메일을 보내는 온-프레미스 메일 서버가 없는 경우 Office 365에 대해 게시해야 하는 유일한 SPF TXT 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-190">If you're a fully-hosted customer, that is, you have no on-premises mail servers that send outbound mail, this is the only SPF TXT record that you need to publish for Office 365.</span></span>

<span data-ttu-id="5f6a6-191">하이브리드 배포가 있는 경우(즉, 일부 사서함은 Microsoft 365에서 호스팅) 또는 EOP(Exchange Online Protection) 독립 실행형 고객인 경우(즉, 조직에서 EOP를 사용하여 프레미스 사서함을 보호) DNS의 SPF TXT 레코드에 각 프레미스 에지 메일 서버의 아웃바운드 IP 주소를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-191">If you have a hybrid deployment (that is, you have some mailboxes on-premises and some hosted in Microsoft 365), or if you're an Exchange Online Protection (EOP) standalone customer (that is, your organization uses EOP to protect your on-premises mailboxes), you should add the outbound IP address for each of your on-premises edge mail servers to the SPF TXT record in DNS.</span></span>

## <a name="form-your-spf-txt-record-for-microsoft-365"></a><span data-ttu-id="5f6a6-192">Microsoft 365에 대한 SPF TXT 레코드 작성</span><span class="sxs-lookup"><span data-stu-id="5f6a6-192">Form your SPF TXT record for Microsoft 365</span></span>
<span data-ttu-id="5f6a6-193"><a name="FormYourSPF"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6a6-193"><a name="FormYourSPF"> </a></span></span>

<span data-ttu-id="5f6a6-194">이 문서의 구문 정보를 사용하여 사용자 지정 도메인에 대한 SPF TXT 레코드를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-194">Use the syntax information in this article to form the SPF TXT record for your custom domain.</span></span> <span data-ttu-id="5f6a6-195">여기에 언급되지 않은 다른 구문 옵션이 있습니다. 이러한 옵션은 가장 일반적으로 사용되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-195">Although there are other syntax options that are not mentioned here, these are the most commonly used options.</span></span> <span data-ttu-id="5f6a6-196">레코드를 구성한 후에는 도메인 등록 기관에서 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-196">Once you have formed your record, you need to update the record at your domain registrar.</span></span>

<span data-ttu-id="5f6a6-197">Microsoft 365에 포함해야 하는 도메인에 대한 자세한 내용은 SPF에 필요한 외부 [DNS 레코드를 참조하세요.](../../enterprise/external-domain-name-system-records.md)</span><span class="sxs-lookup"><span data-stu-id="5f6a6-197">For information about the domains you will need to include for Microsoft 365, see [External DNS records required for SPF](../../enterprise/external-domain-name-system-records.md).</span></span> <span data-ttu-id="5f6a6-198">도메인 [등록](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) 기관에 대한 SPF(TXT) 레코드를 업데이트하기 위한 단계별 지침을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-198">Use the [step-by-step instructions](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) for updating SPF (TXT) records for your domain registrar.</span></span>

### <a name="spf-txt-record-syntax-for-microsoft-365"></a><span data-ttu-id="5f6a6-199">Microsoft 365용 SPF TXT 레코드 구문</span><span class="sxs-lookup"><span data-stu-id="5f6a6-199">SPF TXT record syntax for Microsoft 365</span></span>
<span data-ttu-id="5f6a6-200"><a name="SPFSyntaxO365"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6a6-200"><a name="SPFSyntaxO365"> </a></span></span>

<span data-ttu-id="5f6a6-201">Microsoft 365의 일반적인 SPF TXT 레코드에는 다음 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-201">A typical SPF TXT record for Microsoft 365 has the following syntax:</span></span>

```text
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

<span data-ttu-id="5f6a6-202">예시:</span><span class="sxs-lookup"><span data-stu-id="5f6a6-202">For example:</span></span>

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

<span data-ttu-id="5f6a6-203">여기서 각 부분이 나타내는 의미는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-203">where:</span></span>

- <span data-ttu-id="5f6a6-204">**v=spf1이** 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-204">**v=spf1** is required.</span></span> <span data-ttu-id="5f6a6-205">그러면 TXT 레코드가 SPF TXT 레코드로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-205">This defines the TXT record as an SPF TXT record.</span></span>

- <span data-ttu-id="5f6a6-206">**ip4는** IP 버전 4 주소를 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-206">**ip4** indicates that you are using IP version 4 addresses.</span></span> <span data-ttu-id="5f6a6-207">**ip6는** IP 버전 6 주소를 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-207">**ip6** indicates that you are using IP version 6 addresses.</span></span> <span data-ttu-id="5f6a6-208">IPv6 IP 주소를 사용하는 경우 이 문서의 예제에서 **ip4를** **ip6으로** 교체합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-208">If you are using IPv6 IP addresses, replace **ip4** with **ip6** in the examples in this article.</span></span> <span data-ttu-id="5f6a6-209">CIDR 표시를 사용하여 IP 주소 범위를 지정할 수도 있습니다(예: **ip4:192.168.0.1/26**).</span><span class="sxs-lookup"><span data-stu-id="5f6a6-209">You can also specify IP address ranges using CIDR notation, for example **ip4:192.168.0.1/26**.</span></span>

- <span data-ttu-id="5f6a6-210">_IP 주소는_ SPF TXT 레코드에 추가할 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-210">_IP address_ is the IP address that you want to add to the SPF TXT record.</span></span> <span data-ttu-id="5f6a6-211">일반적으로 이 주소는 조직에 대한 아웃바운드 메일 서버의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-211">Usually, this is the IP address of the outbound mail server for your organization.</span></span> <span data-ttu-id="5f6a6-212">여러 아웃바운드 메일 서버를 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-212">You can list multiple outbound mail servers.</span></span> <span data-ttu-id="5f6a6-213">자세한 내용은 예제: 여러 아웃바운드 사내 메일 서버의 SPF TXT 레코드 및 [Microsoft 365를 참조하세요.](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365)</span><span class="sxs-lookup"><span data-stu-id="5f6a6-213">For more information, see [Example: SPF TXT record for multiple outbound on-premises mail servers and Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).</span></span>

- <span data-ttu-id="5f6a6-214">_도메인 이름은_ 합법적인 보낸 사람으로 추가하려는 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-214">_domain name_ is the domain you want to add as a legitimate sender.</span></span> <span data-ttu-id="5f6a6-215">Microsoft 365에 포함해야 하는 도메인 이름 목록은 SPF에 필요한 외부 [DNS 레코드를 참조하세요.](../../enterprise/external-domain-name-system-records.md)</span><span class="sxs-lookup"><span data-stu-id="5f6a6-215">For a list of domain names you should include for Microsoft 365, see [External DNS records required for SPF](../../enterprise/external-domain-name-system-records.md).</span></span>

- <span data-ttu-id="5f6a6-216">적용 규칙은 일반적으로 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-216">Enforcement rule is usually one of the following:</span></span>

  - <span data-ttu-id="5f6a6-217">-모두</span><span class="sxs-lookup"><span data-stu-id="5f6a6-217">-all</span></span>

    <span data-ttu-id="5f6a6-218">하드 실패를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-218">Indicates hard fail.</span></span> <span data-ttu-id="5f6a6-219">도메인에 대해 권한이 부여된 모든 IP 주소를 알고 있는 경우 SPF TXT 레코드에 나열하고 -all(하드 실패) 한정자 를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-219">If you know all of the authorized IP addresses for your domain, list them in the SPF TXT record and use the -all (hard fail) qualifier.</span></span> <span data-ttu-id="5f6a6-220">또한 SPF만 사용하는 경우, 즉 DMARC 또는 DKIM을 사용하지 않는 경우 -all 한정자도 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-220">Also, if you are only using SPF, that is, you are not using DMARC or DKIM, you should use the -all qualifier.</span></span> <span data-ttu-id="5f6a6-221">항상 이 한정자만 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-221">We recommend that you use always this qualifier.</span></span>

  - <span data-ttu-id="5f6a6-222">~all</span><span class="sxs-lookup"><span data-stu-id="5f6a6-222">~all</span></span>

    <span data-ttu-id="5f6a6-223">소프트 실패를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-223">Indicates soft fail.</span></span> <span data-ttu-id="5f6a6-224">전체 IP 주소 목록이 있는지 확실하지 않은 경우 ~all(소프트 실패) 한정자도 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-224">If you're not sure that you have the complete list of IP addresses, then you should use the ~all (soft fail) qualifier.</span></span> <span data-ttu-id="5f6a6-225">또한 p=quarantine 또는 p=reject와 함께 DMARC를 사용하는 경우 ~all을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-225">Also, if you are using DMARC with p=quarantine or p=reject, then you can use ~all.</span></span> <span data-ttu-id="5f6a6-226">그렇지 않은 경우 -all을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-226">Otherwise, use -all.</span></span>

  - <span data-ttu-id="5f6a6-227">?all</span><span class="sxs-lookup"><span data-stu-id="5f6a6-227">?all</span></span>

    <span data-ttu-id="5f6a6-228">중립을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-228">Indicates neutral.</span></span> <span data-ttu-id="5f6a6-229">SPF를 테스트할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-229">This is used when testing SPF.</span></span> <span data-ttu-id="5f6a6-230">라이브 배포에서는 이 한정자 를 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-230">We do not recommend that you use this qualifier in your live deployment.</span></span>

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-microsoft-365"></a><span data-ttu-id="5f6a6-231">예: Microsoft 365에서 모든 메일을 보낼 때 사용할 SPF TXT 레코드</span><span class="sxs-lookup"><span data-stu-id="5f6a6-231">Example: SPF TXT record to use when all of your mail is sent by Microsoft 365</span></span>
<span data-ttu-id="5f6a6-232"><a name="ExampleSPFNoSP"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6a6-232"><a name="ExampleSPFNoSP"> </a></span></span>

<span data-ttu-id="5f6a6-233">모든 메일이 Microsoft 365에서 전송된 경우 SPF TXT 레코드에서 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-233">If all of your mail is sent by Microsoft 365, use this in your SPF TXT record:</span></span>

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-microsoft-365"></a><span data-ttu-id="5f6a6-234">예: 하나의 하이브리드 시나리오에 대한 SPF TXT 레코드와 하나의 Exchange Server Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f6a6-234">Example: SPF TXT record for a hybrid scenario with one on-premises Exchange Server and Microsoft 365</span></span>
<span data-ttu-id="5f6a6-235"><a name="ExampleSPFHybridOneExchangeServer"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6a6-235"><a name="ExampleSPFHybridOneExchangeServer"> </a></span></span>

<span data-ttu-id="5f6a6-236">하이브리드 환경에서는 EXCHANGE SERVER IP 주소가 192.168.0.1인 경우 SPF 적용 규칙을 하드 실패로 설정하기 위해 다음과 같이 SPF TXT 레코드를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-236">In a hybrid environment, if the IP address of your on-premises Exchange Server is 192.168.0.1, in order to set the SPF enforcement rule to hard fail, form the SPF TXT record as follows:</span></span>

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-microsoft-365"></a><span data-ttu-id="5f6a6-237">예: 여러 아웃바운드-프레미스 메일 서버 및 Microsoft 365에 대한 SPF TXT 레코드</span><span class="sxs-lookup"><span data-stu-id="5f6a6-237">Example: SPF TXT record for multiple outbound on-premises mail servers and Microsoft 365</span></span>
<span data-ttu-id="5f6a6-238"><a name="ExampleSPFMultipleMailServerO365"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6a6-238"><a name="ExampleSPFMultipleMailServerO365"> </a></span></span>

<span data-ttu-id="5f6a6-239">여러 아웃바운드 메일 서버가 있는 경우 SPF TXT 레코드에 각 메일 서버의 IP 주소를 포함하고 각 IP 주소를 공백과 "ip4:" 문으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-239">If you have multiple outbound mail servers, include the IP address for each mail server in the SPF TXT record and separate each IP address with a space followed by an "ip4:" statement.</span></span> <span data-ttu-id="5f6a6-240">예시:</span><span class="sxs-lookup"><span data-stu-id="5f6a6-240">For example:</span></span>

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-microsoft-365"></a><span data-ttu-id="5f6a6-241">다음 단계: Microsoft 365용 SPF 설정</span><span class="sxs-lookup"><span data-stu-id="5f6a6-241">Next steps: Set up SPF for Microsoft 365</span></span>
<span data-ttu-id="5f6a6-242"><a name="SPFNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6a6-242"><a name="SPFNextSteps"> </a></span></span>

<span data-ttu-id="5f6a6-243">SPF TXT 레코드를 공식화한 후 [Microsoft 365에서 SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md) 설정의 단계를 수행하여 스푸핑을 방지하여 도메인에 추가하는 것을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-243">Once you have formulated your SPF TXT record, follow the steps in [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) to add it to your domain.</span></span>

<span data-ttu-id="5f6a6-244">SPF는 스푸핑을 방지하도록 설계되어 있지만 SPF가 보호할 수 없는 스푸핑 기법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-244">Although SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="5f6a6-245">이러한 것을 방지하기 위해 SPF를 설정한 후 Microsoft 365에 대한 DKIM 및 DMARC도 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-245">In order to protect against these, once you have set up SPF, you should also configure DKIM and DMARC for Microsoft 365.</span></span> <span data-ttu-id="5f6a6-246">시작하려면 [DKIM을 사용하여 Microsoft 365의](use-dkim-to-validate-outbound-email.md)사용자 지정 도메인에서 보낸 아웃바운드 전자 메일의 유효성을 검사하기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-246">To get started, see [Use DKIM to validate outbound email sent from your custom domain in Microsoft 365](use-dkim-to-validate-outbound-email.md).</span></span> <span data-ttu-id="5f6a6-247">다음으로 [DMARC를 사용하여 Microsoft 365에서 전자 메일 유효성 검사](use-dmarc-to-validate-email.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-247">Next, see [Use DMARC to validate email in Microsoft 365](use-dmarc-to-validate-email.md).</span></span>

## <a name="troubleshooting-best-practices-for-spf-in-microsoft-365"></a><span data-ttu-id="5f6a6-248">문제 해결: Microsoft 365의 SPF 모범 사례</span><span class="sxs-lookup"><span data-stu-id="5f6a6-248">Troubleshooting: Best practices for SPF in Microsoft 365</span></span>
<span data-ttu-id="5f6a6-249"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6a6-249"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="5f6a6-250">사용자 지정 도메인에 대해 SPF TXT 레코드를 하나만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-250">You can only create one SPF TXT record for your custom domain.</span></span> <span data-ttu-id="5f6a6-251">레코드를 여러 개 만들면 라운드 로빈 상황이 발생하고 SPF가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-251">Creating multiple records causes a round robin situation and SPF will fail.</span></span> <span data-ttu-id="5f6a6-252">이 문제를 방지하기 위해 각 하위 구성에 대해 별도의 레코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-252">To avoid this, you can create separate records for each subdomain.</span></span> <span data-ttu-id="5f6a6-253">예를 들어 새 레코드에 대한 레코드를 contoso.com 레코드를 하나씩 bulkmail.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-253">For example, create one record for contoso.com and another record for bulkmail.contoso.com.</span></span>

<span data-ttu-id="5f6a6-254">전자 메일 메시지가 배달되기 전에 10개가 넘는 DNS 쿼리가 발생하는 경우 받는 메일 서버는 영구 오류(영구 오류)로 응답하며 SPF 검사에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-254">If an email message causes more than 10 DNS lookups before it is delivered, the receiving mail server will respond with a permanent error, also called a  _permerror_, and cause the message to fail the SPF check.</span></span> <span data-ttu-id="5f6a6-255">또한 받는 서버는 다음과 유사한 오류가 포함된 NDR(배달 못성 보고서)으로 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-255">The receiving server may also respond with a non-delivery report (NDR) that contains an error similar to these:</span></span>

- <span data-ttu-id="5f6a6-256">메시지가 홉 수를 초과합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-256">The message exceeded the hop count.</span></span>

- <span data-ttu-id="5f6a6-257">메시지에 너무 많은 보기가 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-257">The message required too many lookups.</span></span>

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-microsoft-365"></a><span data-ttu-id="5f6a6-258">Microsoft 365에서 타사 도메인을 사용할 때 "너무 많은 검색" 오류 방지</span><span class="sxs-lookup"><span data-stu-id="5f6a6-258">Avoiding the "too many lookups" error when you use third-party domains with Microsoft 365</span></span>
<span data-ttu-id="5f6a6-259"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6a6-259"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="5f6a6-260">타사 도메인에 대한 일부 SPF TXT 레코드는 수신 서버가 많은 수의 DNS 검색을 수행하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-260">Some SPF TXT records for third-party domains direct the receiving server to perform a large number of DNS lookups.</span></span> <span data-ttu-id="5f6a6-261">예를 들어 이 글을 쓸 때 레코드에 Salesforce.com include 문이 5개 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-261">For example, at the time of this writing, Salesforce.com contains 5 include statements in its record:</span></span>

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

<span data-ttu-id="5f6a6-262">이 오류를 방지하기 위해 예를 들어 대량 전자 메일을 보내는 모든 사람이 이 목적을 위해 특별히 하위omain을 사용해야 하는 정책을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-262">To avoid the error, you can implement a policy where anyone sending bulk email, for example, has to use a subdomain specifically for this purpose.</span></span> <span data-ttu-id="5f6a6-263">그런 다음 대량 전자 메일을 포함하는 하위 구성에 대해 다른 SPF TXT 레코드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-263">You then define a different SPF TXT record for the subdomain that includes the bulk email.</span></span>

 <span data-ttu-id="5f6a6-264">일부 경우에는 salesforce.com 예와 같이 SPF TXT 레코드의 도메인을 사용해야 하지만 다른 경우에는 타사에서 이러한 용도로 사용할 하위 도메인을 이미 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-264">In some cases, like the salesforce.com example, you have to use the domain in your SPF TXT record, but in other cases, the third-party may have already created a subdomain for you to use for this purpose.</span></span> <span data-ttu-id="5f6a6-265">예를 들어 exacttarget.com SPF TXT 레코드에 대해 사용해야 하는 하위omain을 만들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-265">For example, exacttarget.com has created a subdomain that you need to use for your SPF TXT record:</span></span>

```text
cust-spf.exacttarget.com
```

<span data-ttu-id="5f6a6-266">SPF TXT 레코드에 타사 도메인을 포함할 경우 10개까지의 검색 제한이 실행되지 않도록 타사에서 사용할 도메인 또는 하위 도메인을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-266">When you include third-party domains in your SPF TXT record, you need to confirm with the third-party which domain or subdomain to use in order to avoid running into the 10 lookup limit.</span></span>

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a><span data-ttu-id="5f6a6-267">현재 SPF TXT 레코드를 보고 필요한 조회 수를 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="5f6a6-267">How to view your current SPF TXT record and determine the number of lookups that it requires</span></span>
<span data-ttu-id="5f6a6-268"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6a6-268"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="5f6a6-269">nslookup을 사용하여 SPF TXT 레코드를 비롯한 DNS 레코드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-269">You can use nslookup to view your DNS records, including your SPF TXT record.</span></span> <span data-ttu-id="5f6a6-270">또는 원하는 경우 SPF TXT 레코드의 내용을 보는 데 사용할 수 있는 다양한 무료 온라인 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-270">Or, if you prefer, there are a number of free, online tools available that you can use to view the contents of your SPF TXT record.</span></span> <span data-ttu-id="5f6a6-271">SPF TXT 레코드를 보고 include 문 및 리디렉션 체인을 따라 레코드에 필요한 DNS 검색 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-271">By looking at your SPF TXT record and following the chain of include statements and redirects, you can determine how many DNS lookups the record requires.</span></span> <span data-ttu-id="5f6a6-272">일부 온라인 도구는 이러한 수치도 계산하고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-272">Some online tools will even count and display these lookups for you.</span></span> <span data-ttu-id="5f6a6-273">이 번호를 추적하면 조직에서 보낸 메시지가 수신 서버에서 영구적인 오류(영구 오류)를 트리거하지 못하게 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-273">Keeping track of this number will help prevent messages sent from your organization from triggering a permanent error, called a permerror, from the receiving server.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="5f6a6-274">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="5f6a6-274">For more information</span></span>
<span data-ttu-id="5f6a6-275"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6a6-275"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="5f6a6-276">SPF TXT 레코드를 추가하는 데 도움이 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="5f6a6-276">Need help adding the SPF TXT record?</span></span> <span data-ttu-id="5f6a6-277">Microsoft 365에서 사용자 지정 도메인과 함께 보낸 사람 정책 프레임워크를 사용하는 데 대한 자세한 내용은 모든 DNS 호스팅 공급자에서 [Microsoft 365용 DNS](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) 레코드 만들기 문서를 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-277">Read the article [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) for detailed information about usage of Sender Policy Framework with your custom domain in Microsoft 365.</span></span> <span data-ttu-id="5f6a6-278">[스팸 방지 메시지](anti-spam-message-headers.md) 헤더에는 SPF 검사에 Microsoft 365에서 사용하는 구문 및 헤더 필드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6a6-278">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for SPF checks.</span></span>
