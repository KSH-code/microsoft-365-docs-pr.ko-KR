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
ms.openlocfilehash: b6b79957f84e660fe952f88dab18d8934937d875
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167530"
---
# <a name="how-microsoft-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a><span data-ttu-id="9b2c4-103">Microsoft 365에서 SPF(Sender Policy Framework)를 사용하여 스푸핑을 방지하는 방법</span><span class="sxs-lookup"><span data-stu-id="9b2c4-103">How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9b2c4-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="9b2c4-104">**Applies to**</span></span>
- [<span data-ttu-id="9b2c4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9b2c4-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="9b2c4-106">Microsoft Defender for Office 365 요금제 1 및 계획 2</span><span class="sxs-lookup"><span data-stu-id="9b2c4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="9b2c4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b2c4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

 <span data-ttu-id="9b2c4-108">**요약:** 이 문서에서는 Microsoft 365가 DNS의 SPF(Sender Policy Framework) TXT 레코드를 사용하여 대상 전자 메일 시스템이 사용자 지정 도메인에서 보낸 메시지를 신뢰하도록 하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-108">**Summary:** This article describes how Microsoft 365 uses the Sender Policy Framework (SPF) TXT record in DNS to ensure that destination email systems trust messages sent from your custom domain.</span></span> <span data-ttu-id="9b2c4-109">이는 Microsoft 365에서 보낸 아웃바운드 메일에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-109">This applies to outbound mail sent from Microsoft 365.</span></span> <span data-ttu-id="9b2c4-110">Microsoft 365에서 Microsoft 365 내의 받는 사람에게 보낸 메시지는 항상 SPF를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-110">Messages sent from Microsoft 365 to a recipient within Microsoft 365 will always pass SPF.</span></span>

<span data-ttu-id="9b2c4-111">SPF TXT 레코드는 전자 메일 메시지가 전송되는 도메인 이름을 확인하여 스푸핑 및 피싱을 방지하는 데 도움이 되는 DNS 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-111">An SPF TXT record is a DNS record that helps prevent spoofing and phishing by verifying the domain name from which email messages are sent.</span></span> <span data-ttu-id="9b2c4-112">SPF는 보내는 도메인의 주장된 소유자에 대해 보낸 사람 IP 주소를 확인하여 전자 메일 메시지의 출처에 대한 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-112">SPF validates the origin of email messages by verifying the IP address of the sender against the alleged owner of the sending domain.</span></span>

> [!NOTE]
> <span data-ttu-id="9b2c4-113">SPF 레코드 유형은 2014년 IETF(Internet Engineering Task Force)에서 더 이상 사용이 불가능했습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-113">SPF record types were deprecated by the Internet Engineering Task Force (IETF) in 2014.</span></span> <span data-ttu-id="9b2c4-114">대신 DNS의 TXT 레코드를 사용하여 SPF 정보를 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-114">Instead, ensure that you use TXT records in DNS to publish your SPF information.</span></span> <span data-ttu-id="9b2c4-115">이 문서의 나머지에서는 명확성을 위해 SPF TXT 레코드를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-115">The rest of this article uses the term SPF TXT record for clarity.</span></span>

<span data-ttu-id="9b2c4-116">도메인 관리자는 DNS의 TXT 레코드에 SPF 정보를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-116">Domain administrators publish SPF information in TXT records in DNS.</span></span> <span data-ttu-id="9b2c4-117">SPF 정보는 권한이 부여된 아웃바운드 전자 메일 서버를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-117">The SPF information identifies authorized outbound email servers.</span></span> <span data-ttu-id="9b2c4-118">대상 전자 메일 시스템은 권한 있는 아웃바운드 전자 메일 서버에서 메시지를 보냈는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-118">Destination email systems verify that messages originate from authorized outbound email servers.</span></span> <span data-ttu-id="9b2c4-119">이미 SPF에 익숙하거나 간단한 배포가 있으며 Microsoft 365용 DNS의 SPF TXT 레코드에 포함할 것을 알아야 하는 경우 [Microsoft 365에서 SPF를](set-up-spf-in-office-365-to-help-prevent-spoofing.md)설정하여 스푸핑을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-119">If you are already familiar with SPF, or you have a simple deployment, and just need to know what to include in your SPF TXT record in DNS for Microsoft 365, you can go to [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="9b2c4-120">Microsoft 365에서 완전히 호스팅되는 배포가 없는 경우 또는 SPF 작동 방식 또는 Microsoft 365 SPF 문제 해결 방법에 대한 자세한 정보를 원할 경우 계속 읽어 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-120">If you do not have a deployment that is fully-hosted in Microsoft 365, or you want more information about how SPF works or how to troubleshoot SPF for Microsoft 365, keep reading.</span></span>

> [!NOTE]
> <span data-ttu-id="9b2c4-121">이전에는 SharePoint Online을 사용하는 경우 사용자 지정 도메인에 다른 SPF TXT 레코드를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-121">Previously, you had to add a different SPF TXT record to your custom domain if you also used SharePoint Online.</span></span> <span data-ttu-id="9b2c4-122">이 작업은 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-122">This is no longer required.</span></span> <span data-ttu-id="9b2c4-123">이렇게 변경하면 정크 메일 폴더에 SharePoint Online 알림 메시지가 표시될 위험이 줄어 듭니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-123">This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder.</span></span> <span data-ttu-id="9b2c4-124">즉시 변경할 필요는 없지만 "너무 많은 코드 관리" 오류가 발생하는 경우 [Microsoft 365의 SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)설정에 설명된 바와 같이 SPF TXT 레코드를 수정하여 스푸핑을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-124">You do not need to make any changes immediately, but if you receive the "too many lookups" error, modify your SPF TXT record as described in [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span>

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-microsoft-365"></a><span data-ttu-id="9b2c4-125">SpF가 Microsoft 365에서 스푸핑 및 피싱을 방지하는 방법</span><span class="sxs-lookup"><span data-stu-id="9b2c4-125">How SPF works to prevent spoofing and phishing in Microsoft 365</span></span>
<span data-ttu-id="9b2c4-126"><a name="HowSPFWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="9b2c4-126"><a name="HowSPFWorks"> </a></span></span>

<span data-ttu-id="9b2c4-127">SPF는 보낸 사람이 도메인을 대신하여 보낼 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-127">SPF determines whether or not a sender is permitted to send on behalf of a domain.</span></span> <span data-ttu-id="9b2c4-128">보낸 사람이 이를 허용하지 않는 경우, 즉 받는 서버에서 전자 메일이 SPF 확인에 실패하면 해당 서버에 구성된 스팸 정책에 따라 메시지로 할 작업을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-128">If the sender is not permitted to do so, that is, if the email fails the SPF check on the receiving server, the spam policy configured on that server determines what to do with the message.</span></span>

<span data-ttu-id="9b2c4-129">각 SPF TXT 레코드에는 SPF TXT 레코드로 선언, 도메인 및 도메인 대신 보낼 수 있는 외부 도메인에서 메일을 보낼 수 있는 IP 주소, 적용 규칙의 세 부분으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-129">Each SPF TXT record contains three parts: the declaration that it is an SPF TXT record, the IP addresses that are allowed to send mail from your domain and the external domains that can send on your domain's behalf, and an enforcement rule.</span></span> <span data-ttu-id="9b2c4-130">유효한 SPF TXT 레코드에 세 가지가 모두 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-130">You need all three in a valid SPF TXT record.</span></span> <span data-ttu-id="9b2c4-131">이 문서에서는 SPF TXT 레코드를 구성하는 방법을 설명하고 Microsoft 365에서 서비스 사용에 대한 모범 사례를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-131">This article describes how you form your SPF TXT record and provides best practices for working with the services in Microsoft 365.</span></span> <span data-ttu-id="9b2c4-132">DNS에 레코드를 게시하기 위해 도메인 등록 기관과 함께 작업하는 방법에 대한 링크도 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-132">Links to instructions on working with your domain registrar to publish your record to DNS are also provided.</span></span>

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a><span data-ttu-id="9b2c4-133">SPF 기본 사항: 사용자 지정 도메인에서 보낼 수 있는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="9b2c4-133">SPF basics: IP addresses allowed to send from your custom domain</span></span>
<span data-ttu-id="9b2c4-134"><a name="SPFBasicsIPaddresses"> </a></span><span class="sxs-lookup"><span data-stu-id="9b2c4-134"><a name="SPFBasicsIPaddresses"> </a></span></span>

<span data-ttu-id="9b2c4-135">SPF 규칙의 기본 구문을 살펴보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-135">Take a look at the basic syntax for an SPF rule:</span></span>

<span data-ttu-id="9b2c4-136">v=spf1 \<IP\>\<enforcement rule\></span><span class="sxs-lookup"><span data-stu-id="9b2c4-136">v=spf1 \<IP\> \<enforcement rule\></span></span>

<span data-ttu-id="9b2c4-137">예를 들어 다음 SPF 규칙이 다음과 같은 CONTOSO.COM.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-137">For example, let's say the following SPF rule exists for contoso.com:</span></span>

<span data-ttu-id="9b2c4-138">v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\>\<enforcement rule\></span><span class="sxs-lookup"><span data-stu-id="9b2c4-138">v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\> \<enforcement rule\></span></span>

<span data-ttu-id="9b2c4-139">이 예에서 SPF 규칙은 받는 전자 메일 서버에서 다음 도메인에 대한 이러한 IP 주소의 메일만 수락할 수 contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-139">In this example, the SPF rule instructs the receiving email server to only accept mail from these IP addresses for the domain contoso.com:</span></span>

- <span data-ttu-id="9b2c4-140">IP 주소 #1</span><span class="sxs-lookup"><span data-stu-id="9b2c4-140">IP address #1</span></span>

- <span data-ttu-id="9b2c4-141">IP 주소 #2</span><span class="sxs-lookup"><span data-stu-id="9b2c4-141">IP address #2</span></span>

- <span data-ttu-id="9b2c4-142">IP 주소 #3</span><span class="sxs-lookup"><span data-stu-id="9b2c4-142">IP address #3</span></span>

<span data-ttu-id="9b2c4-143">이 SPF 규칙은 받는 전자 메일 서버에서 contoso.com IP 주소 중 하나에서 온 것이 아닌 경우 받는 서버에서 메시지에 적용 규칙을 적용해야 한다고 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-143">This SPF rule tells the receiving email server that if a message comes from contoso.com, but not from one of these three IP addresses, the receiving server should apply the enforcement rule to the message.</span></span> <span data-ttu-id="9b2c4-144">적용 규칙은 일반적으로 다음 옵션 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-144">The enforcement rule is usually one of these options:</span></span>

- <span data-ttu-id="9b2c4-145">**하드 실패.**</span><span class="sxs-lookup"><span data-stu-id="9b2c4-145">**Hard fail.**</span></span> <span data-ttu-id="9b2c4-146">메시지 봉투에 '하드 실패'로 표시한 다음 받는 서버의 구성된 스팸 정책을 이 유형의 메시지에 따르도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-146">Mark the message with 'hard fail' in the message envelope and then follow the receiving server's configured spam policy for this type of message.</span></span>

- <span data-ttu-id="9b2c4-147">**부드러운 오류가 발생했습니다.**</span><span class="sxs-lookup"><span data-stu-id="9b2c4-147">**Soft fail.**</span></span> <span data-ttu-id="9b2c4-148">메시지 봉투에 'soft fail'으로 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-148">Mark the message with 'soft fail' in the message envelope.</span></span> <span data-ttu-id="9b2c4-149">일반적으로 전자 메일 서버는 이러한 메시지를 배달하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-149">Typically, email servers are configured to deliver these messages anyway.</span></span> <span data-ttu-id="9b2c4-150">대부분의 최종 사용자는 이 표시를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-150">Most end users do not see this mark.</span></span>

- <span data-ttu-id="9b2c4-151">**중립**</span><span class="sxs-lookup"><span data-stu-id="9b2c4-151">**Neutral.**</span></span> <span data-ttu-id="9b2c4-152">아무 것도 하지 않습니다. 즉, 메시지 봉투를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-152">Do nothing, that is, do not mark the message envelope.</span></span> <span data-ttu-id="9b2c4-153">일반적으로 테스트 목적으로 예약되어 있으며 거의 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-153">This is usually reserved for testing purposes and is rarely used.</span></span>

<span data-ttu-id="9b2c4-154">다음 예제에서는 SPF가 서로 다른 상황에서 작동하는 방법을 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-154">The following examples show how SPF works in different situations.</span></span> <span data-ttu-id="9b2c4-155">이 예에서 contoso.com 보낸 사람이고 woodgrovebank.com 받는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-155">In these examples, contoso.com is the sender and woodgrovebank.com is the receiver.</span></span>

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a><span data-ttu-id="9b2c4-156">예제 1: 보낸 사람이 받는 사람으로 직접 보낸 메시지의 전자 메일 인증</span><span class="sxs-lookup"><span data-stu-id="9b2c4-156">Example 1: Email authentication of a message sent directly from sender to receiver</span></span>
<span data-ttu-id="9b2c4-157"><a name="spfExample1"> </a></span><span class="sxs-lookup"><span data-stu-id="9b2c4-157"><a name="spfExample1"> </a></span></span>

<span data-ttu-id="9b2c4-158">SPF는 보낸 사람에서 받는 사람으로의 경로가 직접적인 경우 가장 잘 작동합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-158">SPF works best when the path from sender to receiver is direct, for example:</span></span>

![서버 간에 직접 전자 메일이 전송될 때 SPF에서 전자 메일을 인증하는 방법을 보여주는 다이어그램입니다.](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

<span data-ttu-id="9b2c4-160">메시지가 woodgrovebank.com 경우 IP 주소가 #1 SPF TXT 레코드에 있는 경우 contoso.com SPF 확인을 통과하고 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-160">When woodgrovebank.com receives the message, if IP address #1 is in the SPF TXT record for contoso.com, the message passes the SPF check and is authenticated.</span></span>

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a><span data-ttu-id="9b2c4-161">예제 2: 스푸핑된 보낸 사람 주소가 SPF 검사에 실패</span><span class="sxs-lookup"><span data-stu-id="9b2c4-161">Example 2: Spoofed sender address fails the SPF check</span></span>
<span data-ttu-id="9b2c4-162"><a name="spfExample2"> </a></span><span class="sxs-lookup"><span data-stu-id="9b2c4-162"><a name="spfExample2"> </a></span></span>

<span data-ttu-id="9b2c4-163">피싱이 다음을 통해 스푸핑하는 방법을 contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-163">Suppose a phisher finds a way to spoof contoso.com:</span></span>

![스푸핑된 서버에서 보낸 전자 메일을 SPF에서 인증하는 방법을 보여주는 다이어그램입니다.](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

<span data-ttu-id="9b2c4-165">IP 주소 #12 contoso.com의 SPF TXT 레코드에 있지 않은 경우 메시지가 SPF 검사에 실패하고 수신자가 이를 스팸으로 표시하기로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-165">Since IP address #12 is not in contoso.com's SPF TXT record, the message fails the SPF check and the receiver may choose to mark it as spam.</span></span>

### <a name="example-3-spf-and-forwarded-messages"></a><span data-ttu-id="9b2c4-166">예제 3: SPF 및 전달된 메시지</span><span class="sxs-lookup"><span data-stu-id="9b2c4-166">Example 3: SPF and forwarded messages</span></span>
<span data-ttu-id="9b2c4-167"><a name="spfExample3"> </a></span><span class="sxs-lookup"><span data-stu-id="9b2c4-167"><a name="spfExample3"> </a></span></span>

<span data-ttu-id="9b2c4-168">SPF의 한 가지 단점은 전자 메일이 전달된 경우 작동하지 않는다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-168">One drawback of SPF is that it doesn't work when an email has been forwarded.</span></span> <span data-ttu-id="9b2c4-169">예를 들어 woodgrovebank.com 사용자가 모든 전자 메일을 전자 메일 계정으로 보내기 위한 전달 outlook.com 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-169">For example, suppose the user at woodgrovebank.com has set up a forwarding rule to send all email to an outlook.com account:</span></span>

![메시지가 전달될 때 SPF에서 전자 메일을 인증할 수 없는 상황을 보여주는 다이어그램입니다.](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

<span data-ttu-id="9b2c4-171">메시지는 원래 woodgrovebank.com 때 SPF 검사를 통과하지만 ip outlook.com contoso.com의 SPF TXT 레코드에 #25 때문에 SPF 검사에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-171">The message originally passes the SPF check at woodgrovebank.com but it fails the SPF check at outlook.com because IP #25 is not in contoso.com's SPF TXT record.</span></span> <span data-ttu-id="9b2c4-172">Outlook.com 메시지가 스팸으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-172">Outlook.com might then mark the message as spam.</span></span> <span data-ttu-id="9b2c4-173">이 문제를 해결하려면 SPF를 DKIM 및 DMARC와 같은 다른 전자 메일 인증 방법과 함께 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-173">To work around this problem, use SPF in conjunction with other email authentication methods such as DKIM and DMARC.</span></span>

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a><span data-ttu-id="9b2c4-174">SPF 기본 사항: 도메인을 대신하여 메일을 보낼 수 있는 타사 도메인 포함</span><span class="sxs-lookup"><span data-stu-id="9b2c4-174">SPF basics: Including third-party domains that can send mail on behalf of your domain</span></span>
<span data-ttu-id="9b2c4-175"><a name="SPFBasicsIncludes"> </a></span><span class="sxs-lookup"><span data-stu-id="9b2c4-175"><a name="SPFBasicsIncludes"> </a></span></span>

<span data-ttu-id="9b2c4-176">IP 주소 외에도 도메인을 보낸 사람으로 포함하도록 SPF TXT 레코드를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-176">In addition to IP addresses, you can also configure your SPF TXT record to include domains as senders.</span></span> <span data-ttu-id="9b2c4-177">이러한 명령문은 SPF TXT 레코드에 "include" 문으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-177">These are added to the SPF TXT record as "include" statements.</span></span> <span data-ttu-id="9b2c4-178">예를 들어 contoso.com 메일 서버의 IP 주소를 모두 포함해야 하는 경우 contoso.net 서버가 소유하는 contoso.org 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-178">For example, contoso.com might want to include all of the IP addresses of the mail servers from contoso.net and contoso.org which it also owns.</span></span> <span data-ttu-id="9b2c4-179">이를 위해 contoso.com 다음과 같은 SPF TXT 레코드를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-179">To do this, contoso.com publishes an SPF TXT record that looks like this:</span></span>

```text
v=spf1 include:contoso.net include:contoso.org -all
```

<span data-ttu-id="9b2c4-180">수신 서버에서 DNS에서 이 레코드를 볼 때 DNS에 대한 SPF TXT 레코드에 대한 DNS contoso.net 수행한 다음 해당 레코드에 대해 contoso.org. 레코드 내에서 contoso.net 또는 contoso.org 포함 문을 찾으면 해당 문도 따라가게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-180">When the receiving server sees this record in DNS, it also performs a DNS lookup on the SPF TXT record for contoso.net and then for contoso.org. If it finds an additional include statement within the records for contoso.net or contoso.org, it will follow those too.</span></span> <span data-ttu-id="9b2c4-181">서비스 거부 공격을 방지하기 위해 단일 전자 메일 메시지에 대한 최대 DNS 쿼리 수는 10개입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-181">In order to help prevent denial of service attacks, the maximum number of DNS lookups for a single email message is 10.</span></span> <span data-ttu-id="9b2c4-182">각 include 문은 추가 DNS 쿼리를 나타 내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-182">Each include statement represents an additional DNS lookup.</span></span> <span data-ttu-id="9b2c4-183">메시지가 10 제한을 초과하면 SPF에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-183">If a message exceeds the 10 limit, the message fails SPF.</span></span> <span data-ttu-id="9b2c4-184">메시지가 수신 서버가 구성된 방식에 따라 이 제한에 도달하면 보낸 사람이 메시지가 "너무 많은 수의 쿼리"를 생성하거나 "메시지의 최대 홉 수가 초과했습니다."라는 메시지가 표시될 수 있습니다( 이는 코드 관리 루프가 실행되고 DNS 시간 제한을 초과할 때 실행될 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="9b2c4-184">Once a message reaches this limit, depending on the way the receiving server is configured, the sender may get a message that says the message generated "too many lookups" or that the "maximum hop count for the message has been exceeded" (which can happen when the lookups loop and surpass the DNS timeout).</span></span> <span data-ttu-id="9b2c4-185">이러한 문제를 방지하는 방법에 대한 팁은 [문제 해결: Microsoft 365의 SPF](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)모범 사례를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-185">For tips on how to avoid this, see [Troubleshooting: Best practices for SPF in Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>

## <a name="requirements-for-your-spf-txt-record-and-microsoft-365"></a><span data-ttu-id="9b2c4-186">SPF TXT 레코드 및 Microsoft 365에 대한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b2c4-186">Requirements for your SPF TXT record and Microsoft 365</span></span>
<span data-ttu-id="9b2c4-187"><a name="SPFReqsinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="9b2c4-187"><a name="SPFReqsinO365"> </a></span></span>

<span data-ttu-id="9b2c4-188">Microsoft 365를 설정할 때 메일을 설정한 경우 Microsoft 메시징 서버를 도메인의 합법적인 메일 원본으로 식별하는 SPF TXT 레코드를 이미 만들었다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-188">If you set up mail when you set up Microsoft 365, you already created an SPF TXT record that identifies the Microsoft messaging servers as a legitimate source of mail for your domain.</span></span> <span data-ttu-id="9b2c4-189">이 레코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-189">This record probably looks like this:</span></span>

```text
v=spf1 include:spf.protection.outlook.com -all
```

<span data-ttu-id="9b2c4-190">완전히 호스팅된 고객인 경우, 즉 아웃바운드 메일을 보내는 온-프레미스 메일 서버가 없는 경우 Office 365에 대해 게시해야 하는 유일한 SPF TXT 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-190">If you're a fully-hosted customer, that is, you have no on-premises mail servers that send outbound mail, this is the only SPF TXT record that you need to publish for Office 365.</span></span>

<span data-ttu-id="9b2c4-191">하이브리드 배포가 있는 경우(즉, 일부 사서함은 Microsoft 365에 호스트되어 있으며 일부 사서함은 Microsoft 365에서 호스팅) 또는 EOP(Exchange Online Protection) 독립 실행형 고객인 경우(즉, 조직에서 EOP를 사용하여 프레미스 사서함을 보호하는 경우) 각온-프레미스 에지 메일 서버의 아웃바운드 IP 주소를 DNS의 SPF TXT 레코드에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-191">If you have a hybrid deployment (that is, you have some mailboxes on-premises and some hosted in Microsoft 365), or if you're an Exchange Online Protection (EOP) standalone customer (that is, your organization uses EOP to protect your on-premises mailboxes), you should add the outbound IP address for each of your on-premises edge mail servers to the SPF TXT record in DNS.</span></span>

## <a name="form-your-spf-txt-record-for-microsoft-365"></a><span data-ttu-id="9b2c4-192">Microsoft 365에 대한 SPF TXT 레코드 작성</span><span class="sxs-lookup"><span data-stu-id="9b2c4-192">Form your SPF TXT record for Microsoft 365</span></span>
<span data-ttu-id="9b2c4-193"><a name="FormYourSPF"> </a></span><span class="sxs-lookup"><span data-stu-id="9b2c4-193"><a name="FormYourSPF"> </a></span></span>

<span data-ttu-id="9b2c4-194">이 문서의 구문 정보를 사용하여 사용자 지정 도메인에 대한 SPF TXT 레코드를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-194">Use the syntax information in this article to form the SPF TXT record for your custom domain.</span></span> <span data-ttu-id="9b2c4-195">여기에 언급되지 않은 다른 구문 옵션이 있습니다. 이러한 옵션은 가장 일반적으로 사용되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-195">Although there are other syntax options that are not mentioned here, these are the most commonly used options.</span></span> <span data-ttu-id="9b2c4-196">레코드를 구성한 후에는 도메인 등록 기관에서 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-196">Once you have formed your record, you need to update the record at your domain registrar.</span></span>

<span data-ttu-id="9b2c4-197">Microsoft 365에 포함해야 하는 도메인에 대한 자세한 내용은 SPF에 필요한 외부 [DNS 레코드를 참조하세요.](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)</span><span class="sxs-lookup"><span data-stu-id="9b2c4-197">For information about the domains you will need to include for Microsoft 365, see [External DNS records required for SPF](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="9b2c4-198">도메인 [등록](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) 기관에 대한 SPF(TXT) 레코드를 업데이트하는 단계별 지침을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-198">Use the [step-by-step instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) for updating SPF (TXT) records for your domain registrar.</span></span>

### <a name="spf-txt-record-syntax-for-microsoft-365"></a><span data-ttu-id="9b2c4-199">Microsoft 365용 SPF TXT 레코드 구문</span><span class="sxs-lookup"><span data-stu-id="9b2c4-199">SPF TXT record syntax for Microsoft 365</span></span>
<span data-ttu-id="9b2c4-200"><a name="SPFSyntaxO365"> </a></span><span class="sxs-lookup"><span data-stu-id="9b2c4-200"><a name="SPFSyntaxO365"> </a></span></span>

<span data-ttu-id="9b2c4-201">Microsoft 365의 일반적인 SPF TXT 레코드에는 다음 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-201">A typical SPF TXT record for Microsoft 365 has the following syntax:</span></span>

```text
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

<span data-ttu-id="9b2c4-202">예:</span><span class="sxs-lookup"><span data-stu-id="9b2c4-202">For example:</span></span>

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

<span data-ttu-id="9b2c4-203">여기서 각 부분이 나타내는 의미는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-203">where:</span></span>

- <span data-ttu-id="9b2c4-204">**v=spf1이** 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-204">**v=spf1** is required.</span></span> <span data-ttu-id="9b2c4-205">이렇게 하여 TXT 레코드를 SPF TXT 레코드로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-205">This defines the TXT record as an SPF TXT record.</span></span>

- <span data-ttu-id="9b2c4-206">**ip4는** IP 버전 4 주소를 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-206">**ip4** indicates that you are using IP version 4 addresses.</span></span> <span data-ttu-id="9b2c4-207">**ip6은** IP 버전 6 주소를 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-207">**ip6** indicates that you are using IP version 6 addresses.</span></span> <span data-ttu-id="9b2c4-208">IPv6 IP 주소를 사용하는 경우 이 문서의 예제에서 **ip4를** **ip6으로** 바하십시오.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-208">If you are using IPv6 IP addresses, replace **ip4** with **ip6** in the examples in this article.</span></span> <span data-ttu-id="9b2c4-209">CIDR 표시를 사용하여 IP 주소 범위를 지정할 수도 있습니다(예: **ip4:192.168.0.1/26).**</span><span class="sxs-lookup"><span data-stu-id="9b2c4-209">You can also specify IP address ranges using CIDR notation, for example **ip4:192.168.0.1/26**.</span></span>

- <span data-ttu-id="9b2c4-210">_IP 주소는_ SPF TXT 레코드에 추가할 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-210">_IP address_ is the IP address that you want to add to the SPF TXT record.</span></span> <span data-ttu-id="9b2c4-211">일반적으로 이 주소는 조직에 대한 아웃바운드 메일 서버의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-211">Usually, this is the IP address of the outbound mail server for your organization.</span></span> <span data-ttu-id="9b2c4-212">여러 아웃바운드 메일 서버를 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-212">You can list multiple outbound mail servers.</span></span> <span data-ttu-id="9b2c4-213">자세한 내용은 예제: 여러 아웃바운드 아웃바운드 메일 서버 및 [Microsoft 365에 대한 SPF TXT](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365)레코드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-213">For more information, see [Example: SPF TXT record for multiple outbound on-premises mail servers and Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).</span></span>

- <span data-ttu-id="9b2c4-214">_도메인 이름은_ 합법적인 보낸 사람으로 추가하려는 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-214">_domain name_ is the domain you want to add as a legitimate sender.</span></span> <span data-ttu-id="9b2c4-215">Microsoft 365에 포함해야 하는 도메인 이름 목록은 [SPF에 필요한 외부 DNS 레코드를 참조하세요.](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)</span><span class="sxs-lookup"><span data-stu-id="9b2c4-215">For a list of domain names you should include for Microsoft 365, see [External DNS records required for SPF](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span>

- <span data-ttu-id="9b2c4-216">적용 규칙은 일반적으로 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-216">Enforcement rule is usually one of the following:</span></span>

  - <span data-ttu-id="9b2c4-217">-모두</span><span class="sxs-lookup"><span data-stu-id="9b2c4-217">-all</span></span>

    <span data-ttu-id="9b2c4-218">하드 실패를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-218">Indicates hard fail.</span></span> <span data-ttu-id="9b2c4-219">도메인에 대해 권한이 부여된 모든 IP 주소를 알고 있는 경우 SPF TXT 레코드에 나열하고 -all(하드 실패) 한정자(하드 실패)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-219">If you know all of the authorized IP addresses for your domain, list them in the SPF TXT record and use the -all (hard fail) qualifier.</span></span> <span data-ttu-id="9b2c4-220">또한 SPF만 사용하는 경우, 즉 DMARC 또는 DKIM을 사용하지 않는 경우 -all 한정자도 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-220">Also, if you are only using SPF, that is, you are not using DMARC or DKIM, you should use the -all qualifier.</span></span> <span data-ttu-id="9b2c4-221">항상 이 한정자만 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-221">We recommend that you use always this qualifier.</span></span>

  - <span data-ttu-id="9b2c4-222">~all</span><span class="sxs-lookup"><span data-stu-id="9b2c4-222">~all</span></span>

    <span data-ttu-id="9b2c4-223">소프트 실패를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-223">Indicates soft fail.</span></span> <span data-ttu-id="9b2c4-224">전체 IP 주소 목록이 있는지 확실하지 않은 경우 ~all(소프트 실패) 한정자(소프트 실패)를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-224">If you're not sure that you have the complete list of IP addresses, then you should use the ~all (soft fail) qualifier.</span></span> <span data-ttu-id="9b2c4-225">또한 p=quarantine 또는 p=reject와 함께 DMARC를 사용하는 경우 ~all을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-225">Also, if you are using DMARC with p=quarantine or p=reject, then you can use ~all.</span></span> <span data-ttu-id="9b2c4-226">그렇지 않은 경우 -all을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-226">Otherwise, use -all.</span></span>

  - <span data-ttu-id="9b2c4-227">?all</span><span class="sxs-lookup"><span data-stu-id="9b2c4-227">?all</span></span>

    <span data-ttu-id="9b2c4-228">중립을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-228">Indicates neutral.</span></span> <span data-ttu-id="9b2c4-229">SPF를 테스트할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-229">This is used when testing SPF.</span></span> <span data-ttu-id="9b2c4-230">라이브 배포에서는 이 한정자만 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-230">We do not recommend that you use this qualifier in your live deployment.</span></span>

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-microsoft-365"></a><span data-ttu-id="9b2c4-231">예: Microsoft 365에서 모든 메일을 보낼 때 사용할 SPF TXT 레코드</span><span class="sxs-lookup"><span data-stu-id="9b2c4-231">Example: SPF TXT record to use when all of your mail is sent by Microsoft 365</span></span>
<span data-ttu-id="9b2c4-232"><a name="ExampleSPFNoSP"> </a></span><span class="sxs-lookup"><span data-stu-id="9b2c4-232"><a name="ExampleSPFNoSP"> </a></span></span>

<span data-ttu-id="9b2c4-233">모든 메일이 Microsoft 365에서 전송된 경우 SPF TXT 레코드에서 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-233">If all of your mail is sent by Microsoft 365, use this in your SPF TXT record:</span></span>

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-microsoft-365"></a><span data-ttu-id="9b2c4-234">예: 하나의 하이브리드 시나리오에 대한 SPF TXT 레코드(하나의 Exchange Server 및 Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="9b2c4-234">Example: SPF TXT record for a hybrid scenario with one on-premises Exchange Server and Microsoft 365</span></span>
<span data-ttu-id="9b2c4-235"><a name="ExampleSPFHybridOneExchangeServer"> </a></span><span class="sxs-lookup"><span data-stu-id="9b2c4-235"><a name="ExampleSPFHybridOneExchangeServer"> </a></span></span>

<span data-ttu-id="9b2c4-236">하이브리드 환경에서는 Exchange Server 192.168.0.1의 IP 주소가 192.168.0.1인 경우 SPF 적용 규칙을 하드 실패로 설정하기 위해 SPF TXT 레코드를 다음과 같이 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-236">In a hybrid environment, if the IP address of your on-premises Exchange Server is 192.168.0.1, in order to set the SPF enforcement rule to hard fail, form the SPF TXT record as follows:</span></span>

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-microsoft-365"></a><span data-ttu-id="9b2c4-237">예: 여러 아웃바운드 아웃바운드 메일 서버 및 Microsoft 365에 대한 SPF TXT 레코드</span><span class="sxs-lookup"><span data-stu-id="9b2c4-237">Example: SPF TXT record for multiple outbound on-premises mail servers and Microsoft 365</span></span>
<span data-ttu-id="9b2c4-238"><a name="ExampleSPFMultipleMailServerO365"> </a></span><span class="sxs-lookup"><span data-stu-id="9b2c4-238"><a name="ExampleSPFMultipleMailServerO365"> </a></span></span>

<span data-ttu-id="9b2c4-239">여러 아웃바운드 메일 서버가 있는 경우 SPF TXT 레코드에 각 메일 서버의 IP 주소를 포함하고 각 IP 주소를 공백과 "ip4:" 문으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-239">If you have multiple outbound mail servers, include the IP address for each mail server in the SPF TXT record and separate each IP address with a space followed by an "ip4:" statement.</span></span> <span data-ttu-id="9b2c4-240">예:</span><span class="sxs-lookup"><span data-stu-id="9b2c4-240">For example:</span></span>

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-microsoft-365"></a><span data-ttu-id="9b2c4-241">다음 단계: Microsoft 365에 대한 SPF 설정</span><span class="sxs-lookup"><span data-stu-id="9b2c4-241">Next steps: Set up SPF for Microsoft 365</span></span>
<span data-ttu-id="9b2c4-242"><a name="SPFNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="9b2c4-242"><a name="SPFNextSteps"> </a></span></span>

<span data-ttu-id="9b2c4-243">SPF TXT 레코드를 공식화한 후 [Microsoft 365에서 SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md) 설정 단계에 따라 도메인에 추가하는 스푸핑을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-243">Once you have formulated your SPF TXT record, follow the steps in [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) to add it to your domain.</span></span>

<span data-ttu-id="9b2c4-244">SPF는 스푸핑을 방지하도록 설계되어 있지만 SPF가 보호할 수 없는 스푸핑 기법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-244">Although SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="9b2c4-245">이러한 것을 방지하기 위해 SPF를 설정한 후 Microsoft 365에 대해 DKIM 및 DMARC도 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-245">In order to protect against these, once you have set up SPF, you should also configure DKIM and DMARC for Microsoft 365.</span></span> <span data-ttu-id="9b2c4-246">시작하려면 [DKIM을 사용하여 Microsoft 365의](use-dkim-to-validate-outbound-email.md)사용자 지정 도메인에서 보낸 아웃바운드 전자 메일의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-246">To get started, see [Use DKIM to validate outbound email sent from your custom domain in Microsoft 365](use-dkim-to-validate-outbound-email.md).</span></span> <span data-ttu-id="9b2c4-247">다음으로 [DMARC를 사용하여 Microsoft 365에서 전자 메일 유효성 검사](use-dmarc-to-validate-email.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-247">Next, see [Use DMARC to validate email in Microsoft 365](use-dmarc-to-validate-email.md).</span></span>

## <a name="troubleshooting-best-practices-for-spf-in-microsoft-365"></a><span data-ttu-id="9b2c4-248">문제 해결: Microsoft 365의 SPF 모범 사례</span><span class="sxs-lookup"><span data-stu-id="9b2c4-248">Troubleshooting: Best practices for SPF in Microsoft 365</span></span>
<span data-ttu-id="9b2c4-249"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="9b2c4-249"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="9b2c4-250">사용자 지정 도메인에 대해 SPF TXT 레코드를 하나만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-250">You can only create one SPF TXT record for your custom domain.</span></span> <span data-ttu-id="9b2c4-251">여러 레코드를 만들면 라운드 로빈 상황이 발생하고 SPF가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-251">Creating multiple records causes a round robin situation and SPF will fail.</span></span> <span data-ttu-id="9b2c4-252">이를 방지하기 위해 각 하위 구성에 대해 별도의 레코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-252">To avoid this, you can create separate records for each subdomain.</span></span> <span data-ttu-id="9b2c4-253">예를 들어 레코드의 레코드를 하나씩 contoso.com 레코드를 하나씩 bulkmail.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-253">For example, create one record for contoso.com and another record for bulkmail.contoso.com.</span></span>

<span data-ttu-id="9b2c4-254">전자 메일 메시지가 배달되기 전에 10개가 넘는 DNS 쿼리가 발생하는 경우 받는 메일 서버는 영구적인 오류(영구적 오류)로 응답하고 메시지가 SPF 확인에 실패하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-254">If an email message causes more than 10 DNS lookups before it is delivered, the receiving mail server will respond with a permanent error, also called a  _permerror_, and cause the message to fail the SPF check.</span></span> <span data-ttu-id="9b2c4-255">또한 수신 서버는 다음 오류와 유사한 오류가 포함된 배달 못지 않은 보고서(NDR)로 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-255">The receiving server may also respond with a non-delivery report (NDR) that contains an error similar to these:</span></span>

- <span data-ttu-id="9b2c4-256">메시지가 홉 수를 초과합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-256">The message exceeded the hop count.</span></span>

- <span data-ttu-id="9b2c4-257">메시지에 너무 많은 수의 확인이 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-257">The message required too many lookups.</span></span>

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-microsoft-365"></a><span data-ttu-id="9b2c4-258">Microsoft 365에서 타사 도메인을 사용할 때 "너무 많은 코드 검색" 오류 방지</span><span class="sxs-lookup"><span data-stu-id="9b2c4-258">Avoiding the "too many lookups" error when you use third-party domains with Microsoft 365</span></span>
<span data-ttu-id="9b2c4-259"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="9b2c4-259"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="9b2c4-260">타사 도메인에 대한 일부 SPF TXT 레코드는 수신 서버가 많은 수의 DNS 검색을 수행하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-260">Some SPF TXT records for third-party domains direct the receiving server to perform a large number of DNS lookups.</span></span> <span data-ttu-id="9b2c4-261">예를 들어 이 쓰기 시에는 Salesforce.com 포함 문 5개가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-261">For example, at the time of this writing, Salesforce.com contains 5 include statements in its record:</span></span>

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

<span data-ttu-id="9b2c4-262">이 오류를 방지하기 위해 대량 전자 메일을 보내는 모든 사람이 이 목적을 위해 특별히 하위omain을 사용해야 하는 정책을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-262">To avoid the error, you can implement a policy where anyone sending bulk email, for example, has to use a subdomain specifically for this purpose.</span></span> <span data-ttu-id="9b2c4-263">그런 다음 대량 전자 메일을 포함하는 하위 구성에 대해 다른 SPF TXT 레코드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-263">You then define a different SPF TXT record for the subdomain that includes the bulk email.</span></span>

 <span data-ttu-id="9b2c4-264">경우에 따라 salesforce.com 예와 같이 SPF TXT 레코드에 도메인을 사용해야 하지만 다른 경우에는 타사에서 이러한 용도로 사용할 하위 도메인을 이미 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-264">In some cases, like the salesforce.com example, you have to use the domain in your SPF TXT record, but in other cases, the third-party may have already created a subdomain for you to use for this purpose.</span></span> <span data-ttu-id="9b2c4-265">예를 들어 exacttarget.com SPF TXT 레코드에 사용할 하위omain을 만들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-265">For example, exacttarget.com has created a subdomain that you need to use for your SPF TXT record:</span></span>

```text
cust-spf.exacttarget.com
```

<span data-ttu-id="9b2c4-266">SPF TXT 레코드에 타사 도메인을 포함하면 10개까지의 검색 제한이 실행되지 않도록 타사에서 사용할 도메인 또는 하위 도메인을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-266">When you include third-party domains in your SPF TXT record, you need to confirm with the third-party which domain or subdomain to use in order to avoid running into the 10 lookup limit.</span></span>

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a><span data-ttu-id="9b2c4-267">현재 SPF TXT 레코드를 보고 필요한 조회 수를 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="9b2c4-267">How to view your current SPF TXT record and determine the number of lookups that it requires</span></span>
<span data-ttu-id="9b2c4-268"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="9b2c4-268"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="9b2c4-269">nslookup을 사용하여 SPF TXT 레코드를 비롯한 DNS 레코드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-269">You can use nslookup to view your DNS records, including your SPF TXT record.</span></span> <span data-ttu-id="9b2c4-270">또는 원하는 경우 SPF TXT 레코드의 콘텐츠를 보는 데 사용할 수 있는 다양한 무료 온라인 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-270">Or, if you prefer, there are a number of free, online tools available that you can use to view the contents of your SPF TXT record.</span></span> <span data-ttu-id="9b2c4-271">SPF TXT 레코드를 보고 include 문 및 리디렉션 체인을 따라 레코드에 필요한 DNS 검색 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-271">By looking at your SPF TXT record and following the chain of include statements and redirects, you can determine how many DNS lookups the record requires.</span></span> <span data-ttu-id="9b2c4-272">일부 온라인 도구는 이러한 수치도 계산하고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-272">Some online tools will even count and display these lookups for you.</span></span> <span data-ttu-id="9b2c4-273">이 번호를 추적하면 조직에서 보낸 메시지가 수신 서버에서 영구적인 오류(영구적 오류)를 트리거하지 못하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-273">Keeping track of this number will help prevent messages sent from your organization from triggering a permanent error, called a permerror, from the receiving server.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="9b2c4-274">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="9b2c4-274">For more information</span></span>
<span data-ttu-id="9b2c4-275"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="9b2c4-275"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="9b2c4-276">SPF TXT 레코드를 추가하는 데 도움이 필요하세요?</span><span class="sxs-lookup"><span data-stu-id="9b2c4-276">Need help adding the SPF TXT record?</span></span> <span data-ttu-id="9b2c4-277">Microsoft 365의 사용자 지정 도메인과 함께 보낸 사람 정책 프레임워크 사용에 대한 자세한 내용은 모든 DNS 호스팅 공급자에서 [Microsoft 365용 DNS](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) 레코드 만들기 문서를 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-277">Read the article [Create DNS records at any DNS hosting provider for Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) for detailed information about usage of Sender Policy Framework with your custom domain in Microsoft 365.</span></span> <span data-ttu-id="9b2c4-278">[스팸 방지 메시지](anti-spam-message-headers.md) 헤더에는 Microsoft 365 SPF 검사에 사용되는 구문과 헤더 필드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c4-278">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for SPF checks.</span></span>


