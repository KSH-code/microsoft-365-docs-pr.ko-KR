---
title: SPF (Sender Policy Framework)에서 스푸핑을 방지 하는 방법
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/15/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365에서 DNS의 SPF (Sender Policy Framework) TXT 레코드를 사용 하 여 대상 전자 메일 시스템이 사용자 지정 도메인에서 보낸 메시지를 신뢰 하는지 확인 하는 방법을 알아봅니다.
ms.openlocfilehash: a86087f510dca328bb5b56af6fd4802f1f42a454
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587487"
---
# <a name="how-microsoft-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a><span data-ttu-id="89410-103">Microsoft 365에서 SPF(Sender Policy Framework)를 사용하여 스푸핑을 방지하는 방법</span><span class="sxs-lookup"><span data-stu-id="89410-103">How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>

 <span data-ttu-id="89410-104">**요약:** 이 문서에서는 Microsoft 365에서 DNS의 SPF (Sender Policy Framework) TXT 레코드를 사용 하 여 대상 전자 메일 시스템이 사용자 지정 도메인에서 보낸 메시지를 신뢰 하는지 확인 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-104">**Summary:** This article describes how Microsoft 365 uses the Sender Policy Framework (SPF) TXT record in DNS to ensure that destination email systems trust messages sent from your custom domain.</span></span> <span data-ttu-id="89410-105">이는 Microsoft 365에서 보내는 아웃 바운드 메일에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89410-105">This applies to outbound mail sent from Microsoft 365.</span></span> <span data-ttu-id="89410-106">Microsoft 365에서 Microsoft 365 내의 받는 사람에 게 전송 되는 메시지는 항상 SPF를 통과 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-106">Messages sent from Microsoft 365 to a recipient within Microsoft 365 will always pass SPF.</span></span>

<span data-ttu-id="89410-107">SPF TXT 레코드는 전자 메일 메시지를 보낸 도메인 이름을 확인 하 여 스푸핑 및 피싱을 방지 하는 데 도움이 되는 DNS 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="89410-107">An SPF TXT record is a DNS record that helps prevent spoofing and phishing by verifying the domain name from which email messages are sent.</span></span> <span data-ttu-id="89410-108">SPF는 보내는 도메인의와 대조 소유자에 대해 보낸 사람의 IP 주소를 확인 하 여 전자 메일 메시지의 출처를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-108">SPF validates the origin of email messages by verifying the IP address of the sender against the alleged owner of the sending domain.</span></span>

> [!NOTE]
> <span data-ttu-id="89410-109">SPF 레코드 유형은 2014의 IETF (인터넷 엔지니어링 작업)에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-109">SPF record types were deprecated by the Internet Engineering Task Force (IETF) in 2014.</span></span> <span data-ttu-id="89410-110">대신 DNS에서 TXT 레코드를 사용 하 여 SPF 정보를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-110">Instead, ensure that you use TXT records in DNS to publish your SPF information.</span></span> <span data-ttu-id="89410-111">이 문서의 나머지 부분에서는 명확성을 위해 SPF TXT 레코드 용어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-111">The rest of this article uses the term SPF TXT record for clarity.</span></span>

<span data-ttu-id="89410-112">도메인 관리자는 DNS의 TXT 레코드에 SPF 정보를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-112">Domain administrators publish SPF information in TXT records in DNS.</span></span> <span data-ttu-id="89410-113">SPF 정보는 권한 있는 아웃 바운드 전자 메일 서버를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-113">The SPF information identifies authorized outbound email servers.</span></span> <span data-ttu-id="89410-114">대상 전자 메일 시스템은 권한 있는 아웃바운드 전자 메일 서버에서 메시지를 보냈는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-114">Destination email systems verify that messages originate from authorized outbound email servers.</span></span> <span data-ttu-id="89410-115">SPF에 이미 익숙한 경우 또는 간단한 배포를 수행 하 고 Microsoft 365 용 DNS에서 SPF TXT 레코드에 포함할 사항을 확인 해야 하는 경우에는 [스푸핑을 방지 하기 위해 microsoft 365에서 spf를 설정할](set-up-spf-in-office-365-to-help-prevent-spoofing.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-115">If you are already familiar with SPF, or you have a simple deployment, and just need to know what to include in your SPF TXT record in DNS for Microsoft 365, you can go to [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="89410-116">Microsoft 365에서 완전히 호스트 되는 배포가 없거나 SPF 작동 방식에 대 한 자세한 정보나 Microsoft 365의 SPF 문제를 해결 하는 방법에 대 한 자세한 내용은 계속 읽어 보십시오.</span><span class="sxs-lookup"><span data-stu-id="89410-116">If you do not have a deployment that is fully-hosted in Microsoft 365, or you want more information about how SPF works or how to troubleshoot SPF for Microsoft 365, keep reading.</span></span>

> [!NOTE]
> <span data-ttu-id="89410-117">이전에는 SharePoint Online도 함께 사용 하는 경우 다른 SPF TXT 레코드를 사용자 지정 도메인에 추가 해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-117">Previously, you had to add a different SPF TXT record to your custom domain if you also used SharePoint Online.</span></span> <span data-ttu-id="89410-118">이 작업은 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-118">This is no longer required.</span></span> <span data-ttu-id="89410-119">이렇게 변경하면 정크 메일 폴더에 SharePoint Online 알림 메시지가 표시될 위험이 줄어 듭니다.</span><span class="sxs-lookup"><span data-stu-id="89410-119">This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder.</span></span> <span data-ttu-id="89410-120">즉시 변경 작업을 수행할 필요가 없지만 "너무 많은 조회" 오류가 표시 되는 경우 [스푸핑을 방지 하기 위해 Microsoft 365의 Spf 설정](set-up-spf-in-office-365-to-help-prevent-spoofing.md)에 설명 된 대로 spf TXT 레코드를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-120">You do not need to make any changes immediately, but if you receive the "too many lookups" error, modify your SPF TXT record as described in [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span>

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-microsoft-365"></a><span data-ttu-id="89410-121">SPF의 작동 방식 Microsoft 365에서 스푸핑 및 피싱 방지</span><span class="sxs-lookup"><span data-stu-id="89410-121">How SPF works to prevent spoofing and phishing in Microsoft 365</span></span>
<span data-ttu-id="89410-122"><a name="HowSPFWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="89410-122"><a name="HowSPFWorks"> </a></span></span>

<span data-ttu-id="89410-123">SPF는 보낸 사람이 도메인을 대신 하 여 메일을 보낼 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-123">SPF determines whether or not a sender is permitted to send on behalf of a domain.</span></span> <span data-ttu-id="89410-124">보낸 사람이이 작업을 수행할 수 없는 경우 즉, 전자 메일이 받는 서버에서 SPF 확인을 통과 하지 못하는 경우 해당 서버에 구성 된 스팸 정책에 따라 메시지와 관련 하 여 수행 해야 하는 작업이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89410-124">If the sender is not permitted to do so, that is, if the email fails the SPF check on the receiving server, the spam policy configured on that server determines what to do with the message.</span></span>

<span data-ttu-id="89410-125">각 SPF TXT 레코드에는 해당 레코드가 SPF TXT 레코드이 고 도메인에서 메일을 보낼 수 있는 IP 주소, 도메인 대신 메시지를 보내도록 허용 되는 외부 도메인 및 적용 규칙 이라는 세 개의 부분이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-125">Each SPF TXT record contains three parts: the declaration that it is an SPF TXT record, the IP addresses that are allowed to send mail from your domain and the external domains that can send on your domain's behalf, and an enforcement rule.</span></span> <span data-ttu-id="89410-126">유효한 SPF TXT 레코드에서는 3 개가 모두 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-126">You need all three in a valid SPF TXT record.</span></span> <span data-ttu-id="89410-127">이 문서에서는 SPF TXT 레코드를 작성 하는 방법에 대해 설명 하 고 Microsoft 365에서 서비스 작업을 수행 하기 위한 모범 사례를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-127">This article describes how you form your SPF TXT record and provides best practices for working with the services in Microsoft 365.</span></span> <span data-ttu-id="89410-128">도메인 등록자를 사용 하 여 레코드를 DNS에 게시 하는 방법에 대 한 지침에 대 한 링크도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89410-128">Links to instructions on working with your domain registrar to publish your record to DNS are also provided.</span></span>

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a><span data-ttu-id="89410-129">SPF 기본 사항: 사용자 지정 도메인에서 보낼 수 있는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="89410-129">SPF basics: IP addresses allowed to send from your custom domain</span></span>
<span data-ttu-id="89410-130"><a name="SPFBasicsIPaddresses"> </a></span><span class="sxs-lookup"><span data-stu-id="89410-130"><a name="SPFBasicsIPaddresses"> </a></span></span>

<span data-ttu-id="89410-131">SPF 규칙에 대 한 기본 구문을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-131">Take a look at the basic syntax for an SPF rule:</span></span>

<span data-ttu-id="89410-132">v = spf1 \<IP\>\<enforcement rule\></span><span class="sxs-lookup"><span data-stu-id="89410-132">v=spf1 \<IP\> \<enforcement rule\></span></span>

<span data-ttu-id="89410-133">예를 들어 contoso.com에 대 한 다음과 같은 SPF 규칙이 있다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-133">For example, let's say the following SPF rule exists for contoso.com:</span></span>

<span data-ttu-id="89410-134">v = spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\>\<enforcement rule\></span><span class="sxs-lookup"><span data-stu-id="89410-134">v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\> \<enforcement rule\></span></span>

<span data-ttu-id="89410-135">이 예에서 SPF 규칙은 받는 전자 메일 서버에 contoso.com 도메인에 대 한 이러한 IP 주소 로부터의 메일만 수락 하도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-135">In this example, the SPF rule instructs the receiving email server to only accept mail from these IP addresses for the domain contoso.com:</span></span>

- <span data-ttu-id="89410-136">IP 주소 #1</span><span class="sxs-lookup"><span data-stu-id="89410-136">IP address #1</span></span>

- <span data-ttu-id="89410-137">IP 주소 #2</span><span class="sxs-lookup"><span data-stu-id="89410-137">IP address #2</span></span>

- <span data-ttu-id="89410-138">IP 주소 #3</span><span class="sxs-lookup"><span data-stu-id="89410-138">IP address #3</span></span>

<span data-ttu-id="89410-139">이 SPF 규칙은 받는 전자 메일 서버에 게 메시지를 보내는 경우, 즉 이러한 세 가지 IP 주소 중 하나에서 보낸 메시지가 아닌 경우 받는 서버에서 메시지에 적용 규칙을 contoso.com 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-139">This SPF rule tells the receiving email server that if a message comes from contoso.com, but not from one of these three IP addresses, the receiving server should apply the enforcement rule to the message.</span></span> <span data-ttu-id="89410-140">적용 규칙은 일반적으로 다음 옵션 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="89410-140">The enforcement rule is usually one of these options:</span></span>

- <span data-ttu-id="89410-141">**하드 디스크에 오류가 발생 했습니다.**</span><span class="sxs-lookup"><span data-stu-id="89410-141">**Hard fail.**</span></span> <span data-ttu-id="89410-142">메시지 봉투에 메시지를 ' hard fail '로 표시 한 다음이 유형의 메시지에 대해 받는 서버의 구성 된 스팸 정책을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="89410-142">Mark the message with 'hard fail' in the message envelope and then follow the receiving server's configured spam policy for this type of message.</span></span>

- <span data-ttu-id="89410-143">**소프트 오류가 발생 합니다.**</span><span class="sxs-lookup"><span data-stu-id="89410-143">**Soft fail.**</span></span> <span data-ttu-id="89410-144">메시지 봉투에 ' 소프트 실패 ' 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-144">Mark the message with 'soft fail' in the message envelope.</span></span> <span data-ttu-id="89410-145">일반적으로 전자 메일 서버는 이러한 메시지를 배달 하도록 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89410-145">Typically, email servers are configured to deliver these messages anyway.</span></span> <span data-ttu-id="89410-146">대부분의 최종 사용자에 게는이 표시가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-146">Most end users do not see this mark.</span></span>

- <span data-ttu-id="89410-147">**우세.**</span><span class="sxs-lookup"><span data-stu-id="89410-147">**Neutral.**</span></span> <span data-ttu-id="89410-148">아무 작업도 하지 않고 메시지 봉투를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-148">Do nothing, that is, do not mark the message envelope.</span></span> <span data-ttu-id="89410-149">이 작업은 일반적으로 테스트 목적으로 예약 되어 있으며 거의 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-149">This is usually reserved for testing purposes and is rarely used.</span></span>

<span data-ttu-id="89410-150">다음 예에서는 여러 상황에서 SPF가 작동 하는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89410-150">The following examples show how SPF works in different situations.</span></span> <span data-ttu-id="89410-151">이 예에서는 contoso.com가 보낸 사람 및 woodgrovebank.com가 수신자입니다.</span><span class="sxs-lookup"><span data-stu-id="89410-151">In these examples, contoso.com is the sender and woodgrovebank.com is the receiver.</span></span>

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a><span data-ttu-id="89410-152">예 1: 보낸 사람이 받는 사람에 게 직접 전송 되는 메시지의 전자 메일 인증</span><span class="sxs-lookup"><span data-stu-id="89410-152">Example 1: Email authentication of a message sent directly from sender to receiver</span></span>
<span data-ttu-id="89410-153"><a name="spfExample1"> </a></span><span class="sxs-lookup"><span data-stu-id="89410-153"><a name="spfExample1"> </a></span></span>

<span data-ttu-id="89410-154">SPF는 보낸 사람에서 받는 사람으로의 경로가 direct와 같은 경우에 가장 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-154">SPF works best when the path from sender to receiver is direct, for example:</span></span>

![서버 간에 직접 전자 메일이 전송될 때 SPF에서 전자 메일을 인증하는 방법을 보여주는 다이어그램입니다.](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

<span data-ttu-id="89410-156">Woodgrovebank.com에서 메시지를 수신 하는 경우 IP 주소 #1 contoso.com의 SPF TXT 레코드에 있는 경우 메시지가 SPF 확인을 통과 하 고 인증 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89410-156">When woodgrovebank.com receives the message, if IP address #1 is in the SPF TXT record for contoso.com, the message passes the SPF check and is authenticated.</span></span>

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a><span data-ttu-id="89410-157">예 2: 스푸핑된 보낸 사람 주소가 SPF 확인에 실패 함</span><span class="sxs-lookup"><span data-stu-id="89410-157">Example 2: Spoofed sender address fails the SPF check</span></span>
<span data-ttu-id="89410-158"><a name="spfExample2"> </a></span><span class="sxs-lookup"><span data-stu-id="89410-158"><a name="spfExample2"> </a></span></span>

<span data-ttu-id="89410-159">Phisher에서 contoso.com을 스푸핑할 수 있는 방법을 찾는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-159">Suppose a phisher finds a way to spoof contoso.com:</span></span>

![스푸핑된 서버에서 보낸 전자 메일을 SPF에서 인증하는 방법을 보여주는 다이어그램입니다.](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

<span data-ttu-id="89410-161">IP 주소 #12는 contoso의 SPF TXT 레코드에 없으므로 메시지가 SPF 검사를 통과 하지 못하고 수신자가 해당 메시지를 스팸으로 표시 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-161">Since IP address #12 is not in contoso.com's SPF TXT record, the message fails the SPF check and the receiver may choose to mark it as spam.</span></span>

### <a name="example-3-spf-and-forwarded-messages"></a><span data-ttu-id="89410-162">예제 3: SPF 및 전달 메시지</span><span class="sxs-lookup"><span data-stu-id="89410-162">Example 3: SPF and forwarded messages</span></span>
<span data-ttu-id="89410-163"><a name="spfExample3"> </a></span><span class="sxs-lookup"><span data-stu-id="89410-163"><a name="spfExample3"> </a></span></span>

<span data-ttu-id="89410-164">SPF의 한 가지 단점은 전자 메일이 전달 된 경우에도 작동 하지 않는다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="89410-164">One drawback of SPF is that it doesn't work when an email has been forwarded.</span></span> <span data-ttu-id="89410-165">예를 들어 woodgrovebank.com의 사용자가 모든 전자 메일을 outlook.com 계정으로 보내도록 전달 규칙을 설정 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-165">For example, suppose the user at woodgrovebank.com has set up a forwarding rule to send all email to an outlook.com account:</span></span>

![메시지가 전달될 때 SPF에서 전자 메일을 인증할 수 없는 상황을 보여주는 다이어그램입니다.](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

<span data-ttu-id="89410-167">이 메시지는 원래 woodgrovebank.com에서 SPF 검사를 통과 했지만, IP #25이 contoso의 SPF TXT 레코드에 없기 때문에 outlook.com에서 SPF 검사에 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-167">The message originally passes the SPF check at woodgrovebank.com but it fails the SPF check at outlook.com because IP #25 is not in contoso.com's SPF TXT record.</span></span> <span data-ttu-id="89410-168">그러면 Outlook.com에서 메시지를 스팸으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-168">Outlook.com might then mark the message as spam.</span></span> <span data-ttu-id="89410-169">이 문제를 해결 하려면 SPF를 DKIM 및 DMARC 같은 다른 전자 메일 인증 방법과 함께 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-169">To work around this problem, use SPF in conjunction with other email authentication methods such as DKIM and DMARC.</span></span>

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a><span data-ttu-id="89410-170">SPF 기본 사항: 도메인을 대신 하 여 메일을 보낼 수 있는 타사 도메인을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-170">SPF basics: Including third-party domains that can send mail on behalf of your domain</span></span>
<span data-ttu-id="89410-171"><a name="SPFBasicsIncludes"> </a></span><span class="sxs-lookup"><span data-stu-id="89410-171"><a name="SPFBasicsIncludes"> </a></span></span>

<span data-ttu-id="89410-172">IP 주소 외에 도메인을 보낸 사람으로 포함 하도록 SPF TXT 레코드를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-172">In addition to IP addresses, you can also configure your SPF TXT record to include domains as senders.</span></span> <span data-ttu-id="89410-173">이러한 기능은 SPF TXT 레코드에 "include" 문으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89410-173">These are added to the SPF TXT record as "include" statements.</span></span> <span data-ttu-id="89410-174">예를 들어 contoso.com는 contoso.net 및 contoso.org에서 메일 서버의 모든 IP 주소를 포함 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-174">For example, contoso.com might want to include all of the IP addresses of the mail servers from contoso.net and contoso.org which it also owns.</span></span> <span data-ttu-id="89410-175">이 작업을 수행 하기 위해 contoso.com에서는 다음과 같은 SPF TXT 레코드를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-175">To do this, contoso.com publishes an SPF TXT record that looks like this:</span></span>

```text
v=spf1 include:contoso.net include:contoso.org -all
```

<span data-ttu-id="89410-176">받는 서버가 DNS에서이 레코드를 볼 때 contoso.net의 SPF TXT 레코드에 대 한 DNS 조회를 수행한 다음 contoso.org 용으로도이를 수행 합니다. Contoso.net 또는 contoso.org에 대 한 레코드 내에 추가 포함 문을 찾으면이를 팔 로우 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-176">When the receiving server sees this record in DNS, it also performs a DNS lookup on the SPF TXT record for contoso.net and then for contoso.org. If it finds an additional include statement within the records for contoso.net or contoso.org, it will follow those too.</span></span> <span data-ttu-id="89410-177">서비스 거부 공격을 방지 하기 위해 단일 전자 메일 메시지에 대 한 최대 DNS 조회 수는 10 개입니다.</span><span class="sxs-lookup"><span data-stu-id="89410-177">In order to help prevent denial of service attacks, the maximum number of DNS lookups for a single email message is 10.</span></span> <span data-ttu-id="89410-178">각 포함 문은 추가 DNS 조회를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89410-178">Each include statement represents an additional DNS lookup.</span></span> <span data-ttu-id="89410-179">메시지가 10 개 제한을 초과 하면 메시지가 SPF에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-179">If a message exceeds the 10 limit, the message fails SPF.</span></span> <span data-ttu-id="89410-180">메시지가이 제한에 도달 하면 받는 서버가 구성 된 방식에 따라 보낸 사람에 게 "너무 많은 조회"가 생성 되었거나 "메시지의 최대 홉 수가 초과 되었습니다." 라는 메시지가 표시 될 수 있습니다 (조회 루프가 surpass DNS 시간 초과로 인해 발생할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="89410-180">Once a message reaches this limit, depending on the way the receiving server is configured, the sender may get a message that says the message generated "too many lookups" or that the "maximum hop count for the message has been exceeded" (which can happen when the lookups loop and surpass the DNS timeout).</span></span> <span data-ttu-id="89410-181">이를 방지 하는 방법에 대 한 팁은 [문제 해결: Microsoft 365에서 SPF에 대 한 모범 사례](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89410-181">For tips on how to avoid this, see [Troubleshooting: Best practices for SPF in Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>

## <a name="requirements-for-your-spf-txt-record-and-microsoft-365"></a><span data-ttu-id="89410-182">SPF TXT 레코드 및 Microsoft 365에 대 한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="89410-182">Requirements for your SPF TXT record and Microsoft 365</span></span>
<span data-ttu-id="89410-183"><a name="SPFReqsinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="89410-183"><a name="SPFReqsinO365"> </a></span></span>

<span data-ttu-id="89410-184">Microsoft 365을 설정할 때 메일을 설정 하는 경우 Microsoft 메시징 서버를 도메인에 대 한 합법적인 메일 원본으로 식별 하는 SPF TXT 레코드를 이미 만든 것입니다.</span><span class="sxs-lookup"><span data-stu-id="89410-184">If you set up mail when you set up Microsoft 365, you already created an SPF TXT record that identifies the Microsoft messaging servers as a legitimate source of mail for your domain.</span></span> <span data-ttu-id="89410-185">이 레코드는 다음과 같이 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-185">This record probably looks like this:</span></span>

```text
v=spf1 include:spf.protection.outlook.com -all
```

<span data-ttu-id="89410-186">완전히 호스트 된 고객 인 경우 아웃 바운드 메일을 전송 하는 온-프레미스 메일 서버가 없으면 Office 365에 대해 게시 해야 하는 유일한 SPF TXT 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="89410-186">If you're a fully-hosted customer, that is, you have no on-premises mail servers that send outbound mail, this is the only SPF TXT record that you need to publish for Office 365.</span></span>

<span data-ttu-id="89410-187">하이브리드 배포를 보유 하는 경우 온-프레미스에 있는 일부 사서함이 있고 Microsoft 365에서 호스트 되는 EOP (Exchange Online Protection) 독립 실행형 고객 인 경우 (즉, 조직에서 EOP를 사용 하 여 온-프레미스 사서함을 보호 하는 경우) 각 온-프레미스에 지 메일 서버에 대 한 아웃 바운드 IP 주소를 DNS의 SPF TXT 레코드에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-187">If you have a hybrid deployment (that is, you have some mailboxes on-premises and some hosted in Microsoft 365), or if you're an Exchange Online Protection (EOP) standalone customer (that is, your organization uses EOP to protect your on-premises mailboxes), you should add the outbound IP address for each of your on-premises edge mail servers to the SPF TXT record in DNS.</span></span>

## <a name="form-your-spf-txt-record-for-microsoft-365"></a><span data-ttu-id="89410-188">Microsoft 365에 대 한 SPF TXT 레코드를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-188">Form your SPF TXT record for Microsoft 365</span></span>
<span data-ttu-id="89410-189"><a name="FormYourSPF"> </a></span><span class="sxs-lookup"><span data-stu-id="89410-189"><a name="FormYourSPF"> </a></span></span>

<span data-ttu-id="89410-190">이 문서의 구문 정보를 사용 하 여 사용자 지정 도메인에 대 한 SPF TXT 레코드를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-190">Use the syntax information in this article to form the SPF TXT record for your custom domain.</span></span> <span data-ttu-id="89410-191">여기에 나와 있지 않은 다른 구문 옵션도 있지만 가장 일반적으로 사용 되는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-191">Although there are other syntax options that are not mentioned here, these are the most commonly used options.</span></span> <span data-ttu-id="89410-192">레코드를 구성한 후에는 도메인 등록 기관에서 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-192">Once you have formed your record, you need to update the record at your domain registrar.</span></span>

<span data-ttu-id="89410-193">Microsoft 365에 대해 포함 해야 하는 도메인에 대 한 자세한 내용은 [SPF에 필요한 외부 DNS 레코드](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89410-193">For information about the domains you will need to include for Microsoft 365, see [External DNS records required for SPF](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="89410-194">도메인 등록 기관에 대 한 SPF (TXT) 레코드를 업데이트 하는 단계별 [지침](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) 을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-194">Use the [step-by-step instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) for updating SPF (TXT) records for your domain registrar.</span></span>

### <a name="spf-txt-record-syntax-for-microsoft-365"></a><span data-ttu-id="89410-195">Microsoft 365에 대 한 SPF TXT 레코드 구문</span><span class="sxs-lookup"><span data-stu-id="89410-195">SPF TXT record syntax for Microsoft 365</span></span>
<span data-ttu-id="89410-196"><a name="SPFSyntaxO365"> </a></span><span class="sxs-lookup"><span data-stu-id="89410-196"><a name="SPFSyntaxO365"> </a></span></span>

<span data-ttu-id="89410-197">Microsoft 365의 일반적인 SPF TXT 레코드는 다음 구문을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-197">A typical SPF TXT record for Microsoft 365 has the following syntax:</span></span>

```text
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

<span data-ttu-id="89410-198">예시:</span><span class="sxs-lookup"><span data-stu-id="89410-198">For example:</span></span>

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

<span data-ttu-id="89410-199">여기서 각 부분이 나타내는 의미는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-199">where:</span></span>

- <span data-ttu-id="89410-200">**v = spf1** 가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-200">**v=spf1** is required.</span></span> <span data-ttu-id="89410-201">TXT 레코드를 SPF TXT 레코드로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-201">This defines the TXT record as an SPF TXT record.</span></span>

- <span data-ttu-id="89410-202">**ip4** 는 IP 버전 4 주소를 사용 중임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89410-202">**ip4** indicates that you are using IP version 4 addresses.</span></span> <span data-ttu-id="89410-203">**ip6** 는 IP 버전 6 주소를 사용 중임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89410-203">**ip6** indicates that you are using IP version 6 addresses.</span></span> <span data-ttu-id="89410-204">IPv6 IP 주소를 사용 하는 경우이 문서의 예제에서 **ip4** with **ip6** 를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-204">If you are using IPv6 IP addresses, replace **ip4** with **ip6** in the examples in this article.</span></span> <span data-ttu-id="89410-205">또한 **ip4:192.168.0.1/26**과 같이 CIDR 표기법을 사용 하 여 IP 주소 범위를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-205">You can also specify IP address ranges using CIDR notation, for example **ip4:192.168.0.1/26**.</span></span>

- <span data-ttu-id="89410-206">_Ip 주소_ 는 SPF TXT 레코드에 추가 하려는 ip 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="89410-206">_IP address_ is the IP address that you want to add to the SPF TXT record.</span></span> <span data-ttu-id="89410-207">일반적으로 조직에 대 한 아웃 바운드 메일 서버의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="89410-207">Usually, this is the IP address of the outbound mail server for your organization.</span></span> <span data-ttu-id="89410-208">여러 아웃 바운드 메일 서버를 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-208">You can list multiple outbound mail servers.</span></span> <span data-ttu-id="89410-209">자세한 내용은 [예: SPF TXT record for a outbound 온-프레미스 메일 서버 및 Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89410-209">For more information, see [Example: SPF TXT record for multiple outbound on-premises mail servers and Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).</span></span>

- <span data-ttu-id="89410-210">_도메인 이름은_ 합법적인 보낸 사람으로 추가 하려는 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="89410-210">_domain name_ is the domain you want to add as a legitimate sender.</span></span> <span data-ttu-id="89410-211">Microsoft 365에 대해 포함 해야 하는 도메인 이름 목록은 [SPF에 필요한 외부 DNS 레코드](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89410-211">For a list of domain names you should include for Microsoft 365, see [External DNS records required for SPF](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span></span>

- <span data-ttu-id="89410-212">적용 규칙은 일반적으로 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="89410-212">Enforcement rule is usually one of the following:</span></span>

  - <span data-ttu-id="89410-213">-모두</span><span class="sxs-lookup"><span data-stu-id="89410-213">-all</span></span>

    <span data-ttu-id="89410-214">하드 실패를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89410-214">Indicates hard fail.</span></span> <span data-ttu-id="89410-215">도메인에 대해 모든 권한이 부여 된 IP 주소를 알고 있는 경우 SPF TXT 레코드에이를 나열 하 고-all (hard fail) 한정자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-215">If you know all of the authorized IP addresses for your domain, list them in the SPF TXT record and use the -all (hard fail) qualifier.</span></span> <span data-ttu-id="89410-216">또한 SPF만 사용 하는 경우, 즉 DMARC 또는 DKIM을 사용 하지 않는 경우에는-all 한정자를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-216">Also, if you are only using SPF, that is, you are not using DMARC or DKIM, you should use the -all qualifier.</span></span> <span data-ttu-id="89410-217">항상이 한정자를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-217">We recommend that you use always this qualifier.</span></span>

  - <span data-ttu-id="89410-218">~ all</span><span class="sxs-lookup"><span data-stu-id="89410-218">~all</span></span>

    <span data-ttu-id="89410-219">소프트 장애를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89410-219">Indicates soft fail.</span></span> <span data-ttu-id="89410-220">전체 IP 주소 목록이 있는지 잘 모를 경우 ~ all (소프트 오류) 한정자를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-220">If you're not sure that you have the complete list of IP addresses, then you should use the ~all (soft fail) qualifier.</span></span> <span data-ttu-id="89410-221">또한 p = 격리 또는 p = 거부와 함께 DMARC을 사용 하는 경우 ~ all을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-221">Also, if you are using DMARC with p=quarantine or p=reject, then you can use ~all.</span></span> <span data-ttu-id="89410-222">그렇지 않으면-all을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-222">Otherwise, use -all.</span></span>

  - <span data-ttu-id="89410-223">? all</span><span class="sxs-lookup"><span data-stu-id="89410-223">?all</span></span>

    <span data-ttu-id="89410-224">중립을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89410-224">Indicates neutral.</span></span> <span data-ttu-id="89410-225">이는 SPF을 테스트할 때 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89410-225">This is used when testing SPF.</span></span> <span data-ttu-id="89410-226">실제 배포에서는이 한정자를 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-226">We do not recommend that you use this qualifier in your live deployment.</span></span>

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-microsoft-365"></a><span data-ttu-id="89410-227">예: Microsoft 365에서 모든 메일을 보낼 때 사용할 SPF TXT 레코드</span><span class="sxs-lookup"><span data-stu-id="89410-227">Example: SPF TXT record to use when all of your mail is sent by Microsoft 365</span></span>
<span data-ttu-id="89410-228"><a name="ExampleSPFNoSP"> </a></span><span class="sxs-lookup"><span data-stu-id="89410-228"><a name="ExampleSPFNoSP"> </a></span></span>

<span data-ttu-id="89410-229">Microsoft 365에서 모든 메일을 보낸 경우 SPF TXT 레코드에서 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-229">If all of your mail is sent by Microsoft 365, use this in your SPF TXT record:</span></span>

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-microsoft-365"></a><span data-ttu-id="89410-230">예: 단일 온-프레미스 Exchange Server 및 Microsoft 365을 사용 하는 하이브리드 시나리오에 대 한 SPF TXT 레코드</span><span class="sxs-lookup"><span data-stu-id="89410-230">Example: SPF TXT record for a hybrid scenario with one on-premises Exchange Server and Microsoft 365</span></span>
<span data-ttu-id="89410-231"><a name="ExampleSPFHybridOneExchangeServer"> </a></span><span class="sxs-lookup"><span data-stu-id="89410-231"><a name="ExampleSPFHybridOneExchangeServer"> </a></span></span>

<span data-ttu-id="89410-232">하이브리드 환경에서 온-프레미스 Exchange 서버의 IP 주소가 192.168.0.1 이면 SPF 적용 규칙을 하드 실패로 설정 하기 위해 SPF TXT 레코드를 다음과 같이 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-232">In a hybrid environment, if the IP address of your on-premises Exchange Server is 192.168.0.1, in order to set the SPF enforcement rule to hard fail, form the SPF TXT record as follows:</span></span>

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-microsoft-365"></a><span data-ttu-id="89410-233">예: 여러 아웃 바운드 온-프레미스 메일 서버 및 Microsoft 365에 대 한 SPF TXT 레코드</span><span class="sxs-lookup"><span data-stu-id="89410-233">Example: SPF TXT record for multiple outbound on-premises mail servers and Microsoft 365</span></span>
<span data-ttu-id="89410-234"><a name="ExampleSPFMultipleMailServerO365"> </a></span><span class="sxs-lookup"><span data-stu-id="89410-234"><a name="ExampleSPFMultipleMailServerO365"> </a></span></span>

<span data-ttu-id="89410-235">아웃 바운드 메일 서버가 여러 개인 경우에는 각 메일 서버의 IP 주소를 SPF TXT 레코드에 포함 하 고 각 IP 주소를 공백으로 구분 하 고 "ip4:" 문을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-235">If you have multiple outbound mail servers, include the IP address for each mail server in the SPF TXT record and separate each IP address with a space followed by an "ip4:" statement.</span></span> <span data-ttu-id="89410-236">예시:</span><span class="sxs-lookup"><span data-stu-id="89410-236">For example:</span></span>

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-microsoft-365"></a><span data-ttu-id="89410-237">다음 단계: Microsoft 365에 대 한 SPF 설정</span><span class="sxs-lookup"><span data-stu-id="89410-237">Next steps: Set up SPF for Microsoft 365</span></span>
<span data-ttu-id="89410-238"><a name="SPFNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="89410-238"><a name="SPFNextSteps"> </a></span></span>

<span data-ttu-id="89410-239">SPF TXT 레코드를 만든 후에는 [Microsoft 365에서 Set UP SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md) 의 단계를 수행 하 여 스푸핑이 도메인에 추가 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-239">Once you have formulated your SPF TXT record, follow the steps in [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) to add it to your domain.</span></span>

<span data-ttu-id="89410-240">SPF는 스푸핑을 방지 하는 데 도움이 되지만 SPF에서 보호할 수 없는 스푸핑 기법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-240">Although SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="89410-241">이를 방지 하기 위해 SPF를 설정한 후에는 Microsoft 365에 대해 DKIM 및 DMARC도 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-241">In order to protect against these, once you have set up SPF, you should also configure DKIM and DMARC for Microsoft 365.</span></span> <span data-ttu-id="89410-242">시작 하려면 [DKIM을 사용 하 여 Microsoft 365에서 사용자 지정 도메인에서 보낸 아웃 바운드 전자 메일의 유효성 검사](use-dkim-to-validate-outbound-email.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89410-242">To get started, see [Use DKIM to validate outbound email sent from your custom domain in Microsoft 365](use-dkim-to-validate-outbound-email.md).</span></span> <span data-ttu-id="89410-243">다음으로 [DMARC를 사용하여 Microsoft 365에서 전자 메일 유효성 검사](use-dmarc-to-validate-email.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89410-243">Next, see [Use DMARC to validate email in Microsoft 365](use-dmarc-to-validate-email.md).</span></span>

## <a name="troubleshooting-best-practices-for-spf-in-microsoft-365"></a><span data-ttu-id="89410-244">문제 해결: Microsoft 365의 SPF에 대 한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="89410-244">Troubleshooting: Best practices for SPF in Microsoft 365</span></span>
<span data-ttu-id="89410-245"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="89410-245"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="89410-246">사용자 지정 도메인에 대해 SPF TXT 레코드를 하나만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-246">You can only create one SPF TXT record for your custom domain.</span></span> <span data-ttu-id="89410-247">여러 레코드를 만들면 라운드 로빈 상황이 발생 하 고 SPF가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-247">Creating multiple records causes a round robin situation and SPF will fail.</span></span> <span data-ttu-id="89410-248">이를 방지 하기 위해 각 하위 도메인에 대해 별도의 레코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-248">To avoid this, you can create separate records for each subdomain.</span></span> <span data-ttu-id="89410-249">예를 들어 contoso.com에 대 한 레코드 하나 및 bulkmail.contoso.com에 대 한 다른 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="89410-249">For example, create one record for contoso.com and another record for bulkmail.contoso.com.</span></span>

<span data-ttu-id="89410-250">전자 메일 메시지가 배달 되기 전에 10 개 보다 많은 DNS 조회가 발생 하는 경우 받는 메일 서버는 _permerror_라고도 하는 영구 오류로 응답 하 고 메시지에 SPF 확인이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-250">If an email message causes more than 10 DNS lookups before it is delivered, the receiving mail server will respond with a permanent error, also called a  _permerror_, and cause the message to fail the SPF check.</span></span> <span data-ttu-id="89410-251">받는 서버는 다음과 같은 오류가 포함 된 배달 못 함 보고서 (NDR)와 함께 응답할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-251">The receiving server may also respond with a non-delivery report (NDR) that contains an error similar to these:</span></span>

- <span data-ttu-id="89410-252">메시지가 홉 수를 초과 했습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-252">The message exceeded the hop count.</span></span>

- <span data-ttu-id="89410-253">메시지에 너무 많은 조회가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-253">The message required too many lookups.</span></span>

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-microsoft-365"></a><span data-ttu-id="89410-254">Microsoft 365에서 타사 도메인을 사용 하는 경우 "너무 많은 조회" 오류가 발생 하지 않음</span><span class="sxs-lookup"><span data-stu-id="89410-254">Avoiding the "too many lookups" error when you use third-party domains with Microsoft 365</span></span>
<span data-ttu-id="89410-255"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="89410-255"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="89410-256">타사 도메인에 대 한 일부 SPF TXT 레코드는 받는 서버가 연결 하 여 많은 수의 DNS 조회를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-256">Some SPF TXT records for third-party domains direct the receiving server to perform a large number of DNS lookups.</span></span> <span data-ttu-id="89410-257">예를 들어이 문서를 작성 하는 시점에 Salesforce.com에는 레코드에 5 개의 include 문이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-257">For example, at the time of this writing, Salesforce.com contains 5 include statements in its record:</span></span>

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

<span data-ttu-id="89410-258">이 오류가 발생 하지 않도록 하려면 예를 들어 대량 전자 메일을 보내는 모든 사람이이 용도로만 하위 도메인을 사용 해야 하는 정책을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-258">To avoid the error, you can implement a policy where anyone sending bulk email, for example, has to use a subdomain specifically for this purpose.</span></span> <span data-ttu-id="89410-259">그런 다음 대량 전자 메일이 포함 된 하위 도메인에 대해 다른 SPF TXT 레코드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-259">You then define a different SPF TXT record for the subdomain that includes the bulk email.</span></span>

 <span data-ttu-id="89410-260">Salesforce.com 예제와 같이 SPF TXT 레코드에서 도메인을 사용 해야 하는 경우도 있지만 타사에서이 목적으로 사용할 하위 도메인을 이미 만들었을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-260">In some cases, like the salesforce.com example, you have to use the domain in your SPF TXT record, but in other cases, the third-party may have already created a subdomain for you to use for this purpose.</span></span> <span data-ttu-id="89410-261">예를 들어 exacttarget.com은 SPF TXT 레코드에 사용 해야 하는 하위 도메인을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-261">For example, exacttarget.com has created a subdomain that you need to use for your SPF TXT record:</span></span>

```text
cust-spf.exacttarget.com
```

<span data-ttu-id="89410-262">SPF TXT 레코드에 타사 도메인을 포함 하는 경우에는 10 개의 조회 제한으로 실행 되지 않도록 하기 위해 사용 하는 도메인 또는 하위 도메인이 있는 타사에 대 한 확인을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-262">When you include third-party domains in your SPF TXT record, you need to confirm with the third-party which domain or subdomain to use in order to avoid running into the 10 lookup limit.</span></span>

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a><span data-ttu-id="89410-263">현재 SPF TXT 레코드를 확인 하 고 필요한 조회 수를 결정 하는 방법</span><span class="sxs-lookup"><span data-stu-id="89410-263">How to view your current SPF TXT record and determine the number of lookups that it requires</span></span>
<span data-ttu-id="89410-264"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="89410-264"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="89410-265">Nslookup을 사용 하 여 SPF TXT 레코드를 비롯 한 DNS 레코드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-265">You can use nslookup to view your DNS records, including your SPF TXT record.</span></span> <span data-ttu-id="89410-266">또는 원하는 경우 SPF TXT 레코드의 콘텐츠를 보는 데 사용할 수 있는 무료 온라인 도구가 많이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-266">Or, if you prefer, there are a number of free, online tools available that you can use to view the contents of your SPF TXT record.</span></span> <span data-ttu-id="89410-267">SPF TXT 레코드를 확인 하 고 포함 문 및 리디렉션 체인을 따라 레코드에 필요한 DNS 조회 수를 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-267">By looking at your SPF TXT record and following the chain of include statements and redirects, you can determine how many DNS lookups the record requires.</span></span> <span data-ttu-id="89410-268">일부 온라인 도구는 이러한 조회 수를 계산 하 여 표시 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="89410-268">Some online tools will even count and display these lookups for you.</span></span> <span data-ttu-id="89410-269">이 번호를 추적 하면 조직에서 보내는 메시지가 받는 서버에서 permerror 라는 영구 오류를 발생 시 가지 못하도록 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-269">Keeping track of this number will help prevent messages sent from your organization from triggering a permanent error, called a permerror, from the receiving server.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="89410-270">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="89410-270">For more information</span></span>
<span data-ttu-id="89410-271"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="89410-271"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="89410-272">SPF TXT 레코드를 추가 하는 데 도움이 필요 하세요?</span><span class="sxs-lookup"><span data-stu-id="89410-272">Need help adding the SPF TXT record?</span></span> <span data-ttu-id="89410-273">Microsoft 365에서 사용자 지정 도메인을 사용 하 여 보낸 사람 정책 프레임 워크를 사용 하는 방법에 대 한 자세한 내용은 [microsoft 365 용 dns 호스팅 공급자에서 dns 레코드 만들기](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89410-273">Read the article [Create DNS records at any DNS hosting provider for Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) for detailed information about usage of Sender Policy Framework with your custom domain in Microsoft 365.</span></span> <span data-ttu-id="89410-274">[스팸 방지 메시지 헤더](anti-spam-message-headers.md) 에는 SPF 확인을 위해 Microsoft 365에서 사용 하는 구문 및 헤더 필드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89410-274">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for SPF checks.</span></span>


