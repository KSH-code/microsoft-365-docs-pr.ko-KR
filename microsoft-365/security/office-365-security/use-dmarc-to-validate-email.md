---
title: DMARC를 사용하여 전자 메일의 유효성 검사
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 사용자의 조직에서 보낸 메시지의 유효성을 검사하기 위해 도메인 기반 메시지 인증, 보고 및 적합성(DMARC)을 구성하는 방법에 대해 알아봅니다.
ms.openlocfilehash: bcf1c0b3dc0a1a8dd8a679af815fbdc2173cabb7
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759859"
---
# <a name="use-dmarc-to-validate-email"></a><span data-ttu-id="4cbdf-103">DMARC를 사용하여 전자 메일의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="4cbdf-103">Use DMARC to validate email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="4cbdf-104">도메인 기반 메시지 인증, 보고 및 적합성 ([DMARC](https://dmarc.org))은 SPF (Sender Policy Framework) 및 DKIM (DomainKeys Identified Mail)과 함께 작동하여 메일 발신자를 인증하고 대상 전자 메일 시스템이 사용자의 도메인에서 보낸 메시지를 신뢰하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-104">Domain-based Message Authentication, Reporting, and Conformance ([DMARC](https://dmarc.org)) works with Sender Policy Framework (SPF) and DomainKeys Identified Mail (DKIM) to authenticate mail senders and ensure that destination email systems trust messages sent from your domain.</span></span> <span data-ttu-id="4cbdf-105">SPF 및 DKIM과 함께 DMARC를 구현하면 스푸핑 및 피싱 전자 메일에 대한 추가 보호 기능이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-105">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="4cbdf-106">DMARC는 수신 메일 시스템이 사용자의 도메인에서 보낸 SPF 또는 DKIM 확인에 실패한 메시지에 대해 수행할 작업을 결정하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-106">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span>

> [!TIP]
> <span data-ttu-id="4cbdf-107">[MISA(Microsoft 지능형 보안 연합)](https://www.microsoft.com/misapartnercatalog) 카탈로그를 방문하여 Microsoft 365에 대해 DMARC 보고를 제공하는 타사 공급 업체를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-107">Visit the [Microsoft Intelligent Security Association (MISA)](https://www.microsoft.com/misapartnercatalog) catalog to view third-party vendors offering DMARC reporting for Microsoft 365.</span></span>

## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-microsoft-365"></a><span data-ttu-id="4cbdf-108">SPF와 DMARC는 Microsoft 365에서 전자 메일을 보호하기 위해 어떻게 함께 작동하나요?</span><span class="sxs-lookup"><span data-stu-id="4cbdf-108">How do SPF and DMARC work together to protect email in Microsoft 365?</span></span>

 <span data-ttu-id="4cbdf-109">전자 메일 메시지에는 여러 작성자, 발신자 또는 주소가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-109">An email message may contain multiple originator or sender addresses.</span></span> <span data-ttu-id="4cbdf-110">이러한 주소는 다양한 목적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-110">These addresses are used for different purposes.</span></span> <span data-ttu-id="4cbdf-111">예를 들어 다음 주소를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-111">For example, consider these addresses:</span></span>

- <span data-ttu-id="4cbdf-112">**"Mail From" 주소**: 발신자를 식별하고 배달 못 함 알림과 같은 메시지의 배달에 문제가 발생할 경우 반송 알림을 보낼 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-112">**"Mail From" address**: Identifies the sender and specifies where to send return notices if any problems occur with the delivery of the message, such as non-delivery notices.</span></span> <span data-ttu-id="4cbdf-113">전자 메일 메시지의 봉투 부분에 표시되며 일반적으로 전자 메일 응용 프로그램에는 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-113">This appears in the envelope portion of an email message and is not usually displayed by your email application.</span></span> <span data-ttu-id="4cbdf-114">5321.MailFrom 주소 또는 역-경로 주소라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-114">This is sometimes called the 5321.MailFrom address or the reverse-path address.</span></span>

- <span data-ttu-id="4cbdf-115">**"From" 주소**: 메일 응용 프로그램에서 발신자 주소로 표시되는 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-115">**"From" address**: The address displayed as the From address by your mail application.</span></span> <span data-ttu-id="4cbdf-116">이 주소는 전자 메일의 작성자를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-116">This address identifies the author of the email.</span></span> <span data-ttu-id="4cbdf-117">즉, 메시지 작성을 담당하는 개인 또는 시스템의 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-117">That is, the mailbox of the person or system responsible for writing the message.</span></span> <span data-ttu-id="4cbdf-118">이를 5322.From이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-118">This is sometimes called the 5322.From address.</span></span>

<span data-ttu-id="4cbdf-119">SPF는 DNS TXT 레코드를 사용하여 지정된 도메인에 대해 인증된 전송 IP 주소 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-119">SPF uses a DNS TXT record to provide a list of authorized sending IP addresses for a given domain.</span></span> <span data-ttu-id="4cbdf-120">일반적으로 SPF 검사는 5321.MailFrom 주소에 대해서만 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-120">Normally, SPF checks are only performed against the 5321.MailFrom address.</span></span> <span data-ttu-id="4cbdf-121">즉, SPF를 단독으로 사용하는 경우 5322.From 주소가 인증되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-121">This means that the 5322.From address is not authenticated when you use SPF by itself.</span></span> <span data-ttu-id="4cbdf-122">이를 통해 SPF 검사를 통과했지만 스푸핑된 5322.From 발신자 주소를 가지고 있는 메시지를 사용자가 받을 수 있게 되는 시나리오가 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-122">This allows for a scenario where a user can receive a message which passes an SPF check but has a spoofed 5322.From sender address.</span></span> <span data-ttu-id="4cbdf-123">예를 들어 다음 SMTP 내용을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-123">For example, consider this SMTP transcript:</span></span>

```console
S: Helo woodgrovebank.com
S: Mail from: phish@phishing.contoso.com
S: Rcpt to: astobes@tailspintoys.com
S: data
S: To: "Andrew Stobes" <astobes@tailspintoys.com>
S: From: "Woodgrove Bank Security" <security@woodgrovebank.com>
S: Subject: Woodgrove Bank - Action required
S:
S: Greetings User,
S:
S: We need to verify your banking details.
S: Please click the following link to verify that we have the right information for your account.
S:
S: https://short.url/woodgrovebank/updateaccount/12-121.aspx
S:
S: Thank you,
S: Woodgrove Bank
S: .
```

<span data-ttu-id="4cbdf-124">이 내용에서 발신자 주소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-124">In this transcript, the sender addresses are as follows:</span></span>

- <span data-ttu-id="4cbdf-125">Mail from 주소 (5321.MailFrom): phish@phishing.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4cbdf-125">Mail from address (5321.MailFrom): phish@phishing.contoso.com</span></span>

- <span data-ttu-id="4cbdf-126">From 주소 (5322.From): security@woodgrovebank.com</span><span class="sxs-lookup"><span data-stu-id="4cbdf-126">From address (5322.From): security@woodgrovebank.com</span></span>

<span data-ttu-id="4cbdf-127">SPF를 구성한 경우 수신 서버는 Mail from 주소인 phish@phishing.contoso.com에 대해 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-127">If you configured SPF, then the receiving server performs a check against the Mail from address phish@phishing.contoso.com.</span></span> <span data-ttu-id="4cbdf-128">메시지가 도메인 phishing.contoso.com의 유효한 출처에서 온 경우 SPF 검사를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-128">If the message came from a valid source for the domain phishing.contoso.com then the SPF check passes.</span></span> <span data-ttu-id="4cbdf-129">전자 메일 클라이언트는 From 주소만 표시하므로 사용자에게 이 메시지는 security@woodgrovebank.com에서 온 것으로 보입니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-129">Since the email client only displays the From address, the user sees that this message came from security@woodgrovebank.com.</span></span> <span data-ttu-id="4cbdf-130">SPF 단독으로는 woodgrovebank.com의 유효성이 인증되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-130">With SPF alone, the validity of woodgrovebank.com was never authenticated.</span></span>

<span data-ttu-id="4cbdf-131">DMARC를 사용하는 경우 수신 서버는 From 주소에 대해서도 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-131">When you use DMARC, the receiving server also performs a check against the From address.</span></span> <span data-ttu-id="4cbdf-132">위의 예제에서 woodgrovebank.com에 대한 DMARC TXT 레코드가 있는 경우 From 주소의 검사는 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-132">In the example above, if there is a DMARC TXT record in place for woodgrovebank.com, then the check against the From address fails.</span></span>

## <a name="what-is-a-dmarc-txt-record"></a><span data-ttu-id="4cbdf-133">DMARC TXT 레코드란 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="4cbdf-133">What is a DMARC TXT record?</span></span>

<span data-ttu-id="4cbdf-134">SPF의 DNS 레코드와 마찬가지로 DMARC의 레코드는 스푸핑 및 피싱을 방지하는 데 도움이 되는 DNS 텍스트 (TXT) 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-134">Like the DNS records for SPF, the record for DMARC is a DNS text (TXT) record that helps prevent spoofing and phishing.</span></span> <span data-ttu-id="4cbdf-135">DMARC TXT 레코드를 DNS에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-135">You publish DMARC TXT records in DNS.</span></span> <span data-ttu-id="4cbdf-136">DMARC TXT 레코드는 전자 메일을 보내는 도메인의 알려진 소유자와 대조하여 전자 메일 작성자의 IP 주소를 확인함으로써 전자 메일 메시지의 출처에 대한 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-136">DMARC TXT records validate the origin of email messages by verifying the IP address of an email's author against the alleged owner of the sending domain.</span></span> <span data-ttu-id="4cbdf-137">DMARC TXT 레코드는 인증된 아웃바운드 전자 메일 서버를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-137">The DMARC TXT record identifies authorized outbound email servers.</span></span> <span data-ttu-id="4cbdf-138">그런 다음 대상 전자 메일 시스템은 수신한 메시지가 인증된 아웃바운드 전자 메일 서버에서 보낸 것인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-138">Destination email systems can then verify that messages they receive originate from authorized outbound email servers.</span></span>

<span data-ttu-id="4cbdf-139">Microsoft의 DMARC TXT 레코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-139">Microsoft's DMARC TXT record looks something like this:</span></span>

```console
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1"
```

<span data-ttu-id="4cbdf-140">Microsoft는 자사의 DMARC 보고서를 타사인 [Agari](https://agari.com)에게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-140">Microsoft sends its DMARC reports to [Agari](https://agari.com), a third party.</span></span> <span data-ttu-id="4cbdf-141">Agari는 DMARC 보고서를 수집하고 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-141">Agari collects and analyzes DMARC reports.</span></span> <span data-ttu-id="4cbdf-142">[MISA 카탈로그](https://www.microsoft.com/misapartnercatalog)에 방문하여 Microsoft 365에 대해 DMARC 보고를 제공하는 타사 공급 업체를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-142">Please visit the [MISA catalog](https://www.microsoft.com/misapartnercatalog) to view more third-party vendors offering DMARC reporting for Microsoft 365.</span></span>

## <a name="implement-dmarc-for-inbound-mail"></a><span data-ttu-id="4cbdf-143">인바운드 메일에 대한 DMARC 구현</span><span class="sxs-lookup"><span data-stu-id="4cbdf-143">Implement DMARC for inbound mail</span></span>

<span data-ttu-id="4cbdf-144">Microsoft 365에서 받는 메일에 대해 DMARC를 설정하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-144">You don't have to do a thing to set up DMARC for mail that you receive in Microsoft 365.</span></span> <span data-ttu-id="4cbdf-145">Microsoft가 사용자를 위해 모든 것을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-145">We've taken care of everything for you.</span></span> <span data-ttu-id="4cbdf-146">DMARC 검사를 통과하지 못한 메일에 대해 알아보려면 [Microsoft 365에서 DMARC에 실패한 인바운드 전자 메일을 처리하는 방법](#how-microsoft-365-handles-inbound-email-that-fails-dmarc)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-146">If you want to learn what happens to mail that fails to pass our DMARC checks, see [How Microsoft 365 handles inbound email that fails DMARC](#how-microsoft-365-handles-inbound-email-that-fails-dmarc).</span></span>

## <a name="implement-dmarc-for-outbound-mail-from-microsoft-365"></a><span data-ttu-id="4cbdf-147">Microsoft 365의 아웃바운드 메일에 대한 DMARC 구현</span><span class="sxs-lookup"><span data-stu-id="4cbdf-147">Implement DMARC for outbound mail from Microsoft 365</span></span>

<span data-ttu-id="4cbdf-148">Microsoft 365를 사용하지만 사용자 지정 도메인을 사용하지 않는 경우(즉, onmicrosoft.com을 사용하는 경우), 사용자 조직의 DMARC를 구성하거나 구현하기 위해 다른 작업을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-148">If you use Microsoft 365 but you aren't using a custom domain, that is, you use onmicrosoft.com, you don't need to do anything else to configure or implement DMARC for your organization.</span></span> <span data-ttu-id="4cbdf-149">SPF는 이미 설정되어 있으며 Microsoft 365는 보내는 메일에 대해 DKIM 서명을 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-149">SPF is already set up for you and Microsoft 365 automatically generates a DKIM signature for your outgoing mail.</span></span> <span data-ttu-id="4cbdf-150">이 서명에 대한 자세한 내용은 [DKIM 및 Microsoft 365의 기본 동작](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-150">For more information about this signature, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>

 <span data-ttu-id="4cbdf-151">사용자 지정 도메인이 있거나 Microsoft 365 외에 온-프레미스 Exchange 서버를 사용하는 경우 아웃바운드 메일에 대해 DMARC를 수동으로 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-151">If you have a custom domain or you are using on-premises Exchange servers in addition to Microsoft 365, you need to manually implement DMARC for your outbound mail.</span></span> <span data-ttu-id="4cbdf-152">사용자 정의 도메인에 DMARC를 구현하는 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-152">Implementing DMARC for your custom domain includes these steps:</span></span>

- [<span data-ttu-id="4cbdf-153">1단계: 사용자 도메인의 유효한 메일 출처 식별</span><span class="sxs-lookup"><span data-stu-id="4cbdf-153">Step 1: Identify valid sources of mail for your domain</span></span>](#step-1-identify-valid-sources-of-mail-for-your-domain)

- [<span data-ttu-id="4cbdf-154">2단계: 사용자 도메인에 대한 SPF 설정하기</span><span class="sxs-lookup"><span data-stu-id="4cbdf-154">Step 2: Set up SPF for your domain</span></span>](#step-2-set-up-spf-for-your-domain)

- [<span data-ttu-id="4cbdf-155">3단계: 사용자 지정 도메인에 대한 DKIM 설정하기</span><span class="sxs-lookup"><span data-stu-id="4cbdf-155">Step 3: Set up DKIM for your custom domain</span></span>](#step-3-set-up-dkim-for-your-custom-domain)

- [<span data-ttu-id="4cbdf-156">4단계: 사용자 도메인에 대한 DMARC TXT 레코드 형성하기</span><span class="sxs-lookup"><span data-stu-id="4cbdf-156">Step 4: Form the DMARC TXT record for your domain</span></span>](#step-4-form-the-dmarc-txt-record-for-your-domain)

### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a><span data-ttu-id="4cbdf-157">1단계: 사용자 도메인의 유효한 메일 출처 식별</span><span class="sxs-lookup"><span data-stu-id="4cbdf-157">Step 1: Identify valid sources of mail for your domain</span></span>

<span data-ttu-id="4cbdf-158">이미 SPF를 설정한 경우 이 작업은 이미 진행한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-158">If you have already set up SPF then you have already gone through this exercise.</span></span> <span data-ttu-id="4cbdf-159">그러나 DMARC의 경우 추가 고려 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-159">However, for DMARC, there are additional considerations.</span></span> <span data-ttu-id="4cbdf-160">사용자 도메인의 메일 출처를 식별할 때 두 가지 질문에 답해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-160">When identifying sources of mail for your domain there are two questions you need to answer:</span></span>

- <span data-ttu-id="4cbdf-161">내 도메인에서 메시지를 보내는 IP 주소는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="4cbdf-161">What IP addresses send messages from my domain?</span></span>

- <span data-ttu-id="4cbdf-162">나를 대신하여 제3자가 보낸 메일의 경우 5321.MailFrom과 5322.From 도메인이 일치하나요?</span><span class="sxs-lookup"><span data-stu-id="4cbdf-162">For mail sent from third parties on my behalf, will the 5321.MailFrom and 5322.From domains match?</span></span>

### <a name="step-2-set-up-spf-for-your-domain"></a><span data-ttu-id="4cbdf-163">2단계: 사용자 도메인에 대한 SPF 설정하기</span><span class="sxs-lookup"><span data-stu-id="4cbdf-163">Step 2: Set up SPF for your domain</span></span>

<span data-ttu-id="4cbdf-164">이제 유효한 모든 발신자 목록이 있으므로 [스푸핑을 방지할 수 있도록 SPF 설정하기](set-up-spf-in-office-365-to-help-prevent-spoofing.md) 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-164">Now that you have a list of all your valid senders you can follow the steps to [Set up SPF to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span>

<span data-ttu-id="4cbdf-165">예를 들어 contoso.com이 Exchange Online에서 메일을 보낸다고 가정하면, IP 주소가 192.168.0.1인 온-프레미스 Exchange 서버와 IP 주소가 192.168.100.100인 웹 응용 프로그램의 경우 SPF TXT 레코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-165">For example, assuming contoso.com sends mail from Exchange Online, an on-premises Exchange server whose IP address is 192.168.0.1, and a web application whose IP address is 192.168.100.100, the SPF TXT record would look like this:</span></span>

```console
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

<span data-ttu-id="4cbdf-166">모범 실무로서 SPF TXT 레코드에 제3자 발신자에 대한 고려를 해야합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-166">As a best practice, ensure that your SPF TXT record takes into account third-party senders.</span></span>

### <a name="step-3-set-up-dkim-for-your-custom-domain"></a><span data-ttu-id="4cbdf-167">3단계: 사용자 지정 도메인에 대한 DKIM 설정하기</span><span class="sxs-lookup"><span data-stu-id="4cbdf-167">Step 3: Set up DKIM for your custom domain</span></span>

<span data-ttu-id="4cbdf-168">SPF 설정을 마쳤으면 DKIM을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-168">Once you have set up SPF, you need to set up DKIM.</span></span> <span data-ttu-id="4cbdf-169">DKIM을 사용하면 메시지 머리글에 있는 전자 메일 메시지에 디지털 서명을 첨부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-169">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="4cbdf-170">DKIM을 설정하지 않고 대신 Microsoft 365에서 도메인의 기본 DKIM 구성을 사용하도록 허용하는 경우 DMARC가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-170">If you do not set up DKIM and instead allow Microsoft 365 to use the default DKIM configuration for your domain, DMARC may fail.</span></span> <span data-ttu-id="4cbdf-171">이는 기본 DKIM 구성은 사용자 지정 도메인이 아닌 초기 onmicrosoft.com 도메인을 5322.From 주소로 사용하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-171">This is because the default DKIM configuration uses your initial onmicrosoft.com domain as the 5322.From address, not your custom domain.</span></span> <span data-ttu-id="4cbdf-172">이렇게 하면 사용자 도메인에서 보낸 모든 전자 메일의 5321.MailFrom과 5322.From 주소가 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-172">This forces a mismatch between the 5321.MailFrom and the 5322.From addresses in all email sent from your domain.</span></span>

<span data-ttu-id="4cbdf-173">사용자를 대신하여 메일을 발송하는 제3자 발신자가 있고 발신한 메일이 5321.MailFrom 및 5322.From 주소와 일치하지 않으면 해당 이메일에 대해 DMARC가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-173">If you have third-party senders that send mail on your behalf and the mail they send has mismatched 5321.MailFrom and 5322.From addresses, DMARC will fail for that email.</span></span> <span data-ttu-id="4cbdf-174">이를 방지하려면 해당 제3자 발신자와 함께 사용자 도메인에 DKIM을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-174">To avoid this, you need to set up DKIM for your domain specifically with that third-party sender.</span></span> <span data-ttu-id="4cbdf-175">이를 통해 Microsoft 365는 이 제3자 서비스의 전자 메일을 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-175">This allows Microsoft 365 to authenticate email from this 3rd-party service.</span></span> <span data-ttu-id="4cbdf-176">그러나 이는 또한 Yahoo, Gmail 및 Comcast와 같은 곳에서 메일을 수신할 때 제3자가 보낸 전자 메일이 마치 사용자가 보낸 전자 메일로 확인하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-176">However, it also allows others, for example, Yahoo, Gmail, and Comcast, to verify email sent to them by the third-party as if it was email sent by you.</span></span> <span data-ttu-id="4cbdf-177">이 기능은 고객의 사서함 위치에 관계없이 고객이 사용자 도메인에 대한 신뢰를 구축할 수 있게 해주며 동시에 Microsoft 365는 사용자 도메인의 인증 확인을 통과하기 때문에 스푸핑으로 인해 메시지를 스팸으로 표시하지 않는 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-177">This is beneficial because it allows your customers to build trust with your domain no matter where their mailbox is located, and at the same time Microsoft 365 won't mark a message as spam due to spoofing because it passes authentication checks for your domain.</span></span>

<span data-ttu-id="4cbdf-178">사용자 도메인을 스푸핑할 수 있도록 제3자 발신자에 대해 DKIM을 설정하는 방법을 포함하여 도메인에 DKIM을 설정하는 방법에 대한 지침은 [DKIM을 사용하여 사용자 지정 도메인에서 전송한 아웃바운드 전자 메일의 유효성을 검사](use-dkim-to-validate-outbound-email.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-178">For instructions on setting up DKIM for your domain, including how to set up DKIM for third-party senders so they can spoof your domain, see [Use DKIM to validate outbound email sent from your custom domain](use-dkim-to-validate-outbound-email.md).</span></span>

### <a name="step-4-form-the-dmarc-txt-record-for-your-domain"></a><span data-ttu-id="4cbdf-179">4단계: 사용자 도메인에 대한 DMARC TXT 레코드 형성</span><span class="sxs-lookup"><span data-stu-id="4cbdf-179">Step 4: Form the DMARC TXT record for your domain</span></span>

<span data-ttu-id="4cbdf-180">여기에 언급되지 않은 다른 구문 옵션도 있지만 이 옵션이 Microsoft 365에 가장 일반적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-180">Although there are other syntax options that are not mentioned here, these are the most commonly used options for Microsoft 365.</span></span> <span data-ttu-id="4cbdf-181">사용자 도메인의 DMARC TXT 레코드를 다음 형식으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-181">Form the DMARC TXT record for your domain in the format:</span></span>

```console
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; p=policy; pct=100"
```

<span data-ttu-id="4cbdf-182">여기서 각 부분이 나타내는 의미는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-182">where:</span></span>

- <span data-ttu-id="4cbdf-183">*도메인* 은 사용자가 보호할 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-183">*domain* is the domain you want to protect.</span></span> <span data-ttu-id="4cbdf-184">기본적으로 레코드는 도메인 및 모든 하위 도메인의 메일을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-184">By default, the record protects mail from the domain and all subdomains.</span></span> <span data-ttu-id="4cbdf-185">예를 들어 \_dmarc.contoso.com을 지정하면 DMARC는 housewares.contoso.com 또는 plumbing.contoso.com과 같은 도메인 및 모든 하위 도메인에서 메일을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-185">For example, if you specify \_dmarc.contoso.com, then DMARC protects mail from the domain and all subdomains, such as housewares.contoso.com or plumbing.contoso.com.</span></span>

- <span data-ttu-id="4cbdf-186">*TTL* 은 항상 1시간에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-186">*TTL* should always be the equivalent of one hour.</span></span> <span data-ttu-id="4cbdf-187">TTL에 사용되는 단위 (시간 (1시간), 분 (60분) 또는 초 (3,600초))는 도메인의 등록 기관에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-187">The unit used for TTL, either hours (1 hour), minutes (60 minutes), or seconds (3600 seconds), will vary depending on the registrar for your domain.</span></span>

- <span data-ttu-id="4cbdf-188">*pct = 100* 은 이 규칙을 전자 메일의 100%에 사용해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-188">*pct=100* indicates that this rule should be used for 100% of email.</span></span>

- <span data-ttu-id="4cbdf-189">*정책* 은 DMARC가 실패하는 경우 수신 서버에서 어떤 정책을 따를 것인지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-189">*policy* specifies what policy you want the receiving server to follow if DMARC fails.</span></span> <span data-ttu-id="4cbdf-190">정책을 없음, 격리 또는 거부로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-190">You can set the policy to none, quarantine, or reject.</span></span>

<span data-ttu-id="4cbdf-191">사용할 옵션에 대한 자세한 내용은 [Microsoft 365에서 DMARC를 구현하기 위한 모범 사례](#best-practices-for-implementing-dmarc-in-microsoft-365)의 개념을 숙지하세요.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-191">For information about which options to use, become familiar with the concepts in [Best practices for implementing DMARC in Microsoft 365](#best-practices-for-implementing-dmarc-in-microsoft-365).</span></span>

<span data-ttu-id="4cbdf-192">예제:</span><span class="sxs-lookup"><span data-stu-id="4cbdf-192">Examples:</span></span>

- <span data-ttu-id="4cbdf-193">정책을 없음으로 설정</span><span class="sxs-lookup"><span data-stu-id="4cbdf-193">Policy set to none</span></span>

    ```console
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- <span data-ttu-id="4cbdf-194">정책을 격리로 설정</span><span class="sxs-lookup"><span data-stu-id="4cbdf-194">Policy set to quarantine</span></span>

    ```console
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- <span data-ttu-id="4cbdf-195">정책을 거부로 설정</span><span class="sxs-lookup"><span data-stu-id="4cbdf-195">Policy set to reject</span></span>

    ```console
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

<span data-ttu-id="4cbdf-196">레코드를 구성한 후에는 도메인 등록 기관에서 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-196">Once you have formed your record, you need to update the record at your domain registrar.</span></span> <span data-ttu-id="4cbdf-197">Microsoft 365의 DNS 레코드에 DMARC TXT 레코드를 추가하는 방법에 대한 지침은 [DNS 레코드를 관리할 때 Microsoft 365용 DNS 레코드 만들기](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-197">For instructions on adding the DMARC TXT record to your DNS records for Microsoft 365, see [Create DNS records for Microsoft 365 when you manage your DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

## <a name="best-practices-for-implementing-dmarc-in-microsoft-365"></a><span data-ttu-id="4cbdf-198">Microsoft 365에서 DMARC를 구현하기 위한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="4cbdf-198">Best practices for implementing DMARC in Microsoft 365</span></span>

<span data-ttu-id="4cbdf-199">나머지 메일 흐름에 영향을 주지 않고 DMARC를 점진적으로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-199">You can implement DMARC gradually without impacting the rest of your mail flow.</span></span> <span data-ttu-id="4cbdf-200">이 단계를 따르는 롤아웃 계획을 만들고 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-200">Create and implement a roll-out plan that follows these steps.</span></span> <span data-ttu-id="4cbdf-201">아래 단계를 진행하기 전에 먼저 하위 도메인, 다른 하위 도메인을 차례로 수행하고, 마지막으로 사용자 조직의 최상위 도메인을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-201">Do each of these steps first with a sub-domain, then other sub-domains, and finally with the top-level domain in your organization before moving on to the next step.</span></span>

1. <span data-ttu-id="4cbdf-202">DMARC 구현의 영향 모니터링</span><span class="sxs-lookup"><span data-stu-id="4cbdf-202">Monitor the impact of implementing DMARC</span></span>

    <span data-ttu-id="4cbdf-203">DMARC 수신자가 해당 도메인을 사용하여 볼 수 있는 메시지에 대한 통계를 사용자에게 보내도록 요청하는 하위 도메인 또는 도메인에 대한 간단한 모니터링 모드 레코드를 사용하여 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-203">Start with a simple monitoring-mode record for a sub-domain or domain that requests that DMARC receivers send you statistics about messages that they see using that domain.</span></span> <span data-ttu-id="4cbdf-204">모니터링 모드 레코드는 정책이 none (p=none)으로 설정된 DMARC TXT 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-204">A monitoring-mode record is a DMARC TXT record that has its policy set to none (p=none).</span></span> <span data-ttu-id="4cbdf-205">많은 회사에서는 더욱 제한적인 DMARC 정책을 게시했을 때 손실이 발생할 수 있는 이메일 양을 정확히 알 수 없기 때문에 p=none으로 DMARC TXT 레코드를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-205">Many companies publish a DMARC TXT record with p=none because they are unsure about how much email they may lose by publishing a more restrictive DMARC policy.</span></span>

    <span data-ttu-id="4cbdf-206">메시징 인프라에서 SPF 또는 DKIM을 구현하기 전에도 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-206">You can do this even before you've implemented SPF or DKIM in your messaging infrastructure.</span></span> <span data-ttu-id="4cbdf-207">그러나 SPF 및 DKIM을 구현할 때까지는 DMARC를 사용하여 메일을 효과적으로 격리하거나 거부할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-207">However, you won't be able to effectively quarantine or reject mail by using DMARC until you also implement SPF and DKIM.</span></span> <span data-ttu-id="4cbdf-208">SPF 및 DKIM을 도입하면서 DMARC를 통해 생성된 보고서에는 이러한 검사를 통과한 메시지 수와 출처를 제공하고 그렇지 않은 메시지에 대해서도 이를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-208">As you introduce SPF and DKIM, the reports generated through DMARC will provide the numbers and sources of messages that pass these checks, and those that don't.</span></span> <span data-ttu-id="4cbdf-209">이를 통해 다루어지는 정상/비정상적인 트래픽의 양을 쉽게 파악하고 이에 따른 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-209">You can easily see how much of your legitimate traffic is or isn't covered by them, and troubleshoot any problems.</span></span> <span data-ttu-id="4cbdf-210">또한 얼마나 많은 사기성 메시지가 전송되는지, 어디로부터 전송되는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-210">You'll also begin to see how many fraudulent messages are being sent, and from where.</span></span>

2. <span data-ttu-id="4cbdf-211">DMARC 실패한 메일을 외부 메일 시스템에서 격리하도록 요청</span><span class="sxs-lookup"><span data-stu-id="4cbdf-211">Request that external mail systems quarantine mail that fails DMARC</span></span>

    <span data-ttu-id="4cbdf-212">정상적인 트래픽의 전부 또는 대부분이 SPF 및 DKIM에 의해 보호된다는 것을 믿고 DMARC 구현이 미치는 영향을 이해하고 있는 경우에는 격리 정책을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-212">When you believe that all or most of your legitimate traffic is protected by SPF and DKIM, and you understand the impact of implementing DMARC, you can implement a quarantine policy.</span></span> <span data-ttu-id="4cbdf-213">격리 정책은 정책이 격리 (p=quarantine)으로 설정된 DMARC TXT 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-213">A quarantine policy is a DMARC TXT record that has its policy set to quarantine (p=quarantine).</span></span> <span data-ttu-id="4cbdf-214">이렇게 하면 DMARC 수신자에게 DMARC 검사에 실패한 사용자 도메인의 메시지를 사용자 고객의 받은 편지함 대신 스팸 폴더의 로컬과 같은 곳에 메시지를 넣도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-214">By doing this, you are asking DMARC receivers to put messages from your domain that fail DMARC into the local equivalent of a spam folder instead of your customers' inboxes.</span></span>

3. <span data-ttu-id="4cbdf-215">외부 메일 시스템이 DMARC에 실패한 메시지를 허용하지 않도록 요청</span><span class="sxs-lookup"><span data-stu-id="4cbdf-215">Request that external mail systems not accept messages that fail DMARC</span></span>

    <span data-ttu-id="4cbdf-216">마지막 단계는 거부 정책을 구현하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-216">The final step is implementing a reject policy.</span></span> <span data-ttu-id="4cbdf-217">거부 정책은 정책이 거부 (p=reject)로 설정된 DMARC TXT 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-217">A reject policy is a DMARC TXT record that has its policy set to reject (p=reject).</span></span> <span data-ttu-id="4cbdf-218">이렇게 하면 DMARC 수신자에게 DMARC 검사에 실패한 메시지를 수락하지 않도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-218">When you do this, you're asking DMARC receivers not to accept messages that fail the DMARC checks.</span></span>

4. <span data-ttu-id="4cbdf-219">하위 도메인에 대해 DMARC를 설정하는 방법은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="4cbdf-219">How to set up DMARC for subdomain?</span></span>

   <span data-ttu-id="4cbdf-220">DMARC는 정책을 DNS에 TXT 레코드로 게시하여 구현되며 계층적입니다(예: contoso.com에 대해 게시된 정책은 하위 도메인에 대해 명시적으로 다른 정책이 정의되지 않는 한 sub.domain.contonos.com에 적용됩니다).</span><span class="sxs-lookup"><span data-stu-id="4cbdf-220">DMARC is implemented by publishing a policy as a TXT record in DNS and is hierarchical (e.g. a policy published for contoso.com will apply to sub.domain.contonos.com unless a different policy is explicitly defined for the subdomain).</span></span> <span data-ttu-id="4cbdf-221">이 기능은 조직에서 상위 DMARC 레코드를 더 적은 수로 지정하여 더 넓은 범위를 제공할 수 있기 때문에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-221">This is useful as organizations may be able to specify a smaller number of high-level DMARC records for wider coverage.</span></span> <span data-ttu-id="4cbdf-222">하위 도메인이 최상위 도메인의 DMARC 레코드를 상속하지 않도록 하려면 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-222">Care should be taken to configure explicit subdomain DMARC records where you do not want the subdomains to inherit the top-level domain's DMARC record.</span></span>

   <span data-ttu-id="4cbdf-223">또한 하위 도메인이 전자 메일을 보내지 않아야 할 때 `sp=reject` 값을 추가하여 DMARC에 와일드카드 유형 정책을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-223">Also, you can add a wildcard-type policy for DMARC when subdomains shouldn't be sending email, by adding the `sp=reject` value.</span></span> <span data-ttu-id="4cbdf-224">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="4cbdf-224">For example:</span></span>

   ```text
   _dmarc.contoso.com. TXT "v=DMARC1; p=reject; sp=reject; ruf=mailto:authfail@contoso.com; rua=mailto:aggrep@contoso.com"
   ```

## <a name="how-microsoft-365-handles-outbound-email-that-fails-dmarc"></a><span data-ttu-id="4cbdf-225">Microsoft 365가 DMARC에 실패한 아웃바운드 전자 메일을 처리하는 방법</span><span class="sxs-lookup"><span data-stu-id="4cbdf-225">How Microsoft 365 handles outbound email that fails DMARC</span></span>

<span data-ttu-id="4cbdf-226">메시지가 Microsoft 365에서 아웃바운드되고 DMARC에 실패하고 정책을 p=quarantne 또는 p=reject로 설정한 경우 메시지는 [아웃바운드 메시지용 높은 위험 배달 풀](high-risk-delivery-pool-for-outbound-messages.md)로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-226">If a message is outbound from Microsoft 365 and fails DMARC, and you have set the policy to p=quarantine or p=reject, the message is routed through the [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span> <span data-ttu-id="4cbdf-227">아웃바운드 전자 메일에 대한 오버라이드는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-227">There is no override for outbound email.</span></span>

<span data-ttu-id="4cbdf-228">DMARC 거부 정책(p=reject)을 게시하면 서비스를 통해 아웃바운드 메시지를 릴레이할 때 메시지가 사용자 도메인에 대해 SPF 또는 DKIM을 통과할 수 없으므로 Microsoft 365의 다른 고객이 사용자 도메인을 스푸핑할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-228">If you publish a DMARC reject policy (p=reject), no other customer in Microsoft 365 can spoof your domain because messages will not be able to pass SPF or DKIM for your domain when relaying a message outbound through the service.</span></span> <span data-ttu-id="4cbdf-229">그러나 DMARC 거부 정책을 게시했지만 Microsoft 365를 통해 모든 전자 메일을 인증하지 않았다면 일부 전자 메일이 인바운드 전자 메일에 대한 스팸으로 표시되거나(위에 설명된 것처럼) SPF를 게시하지 않고 서비스를 통해 아웃바운드 릴레이하려고 시도하면 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-229">However, if you do publish a DMARC reject policy but don't have all of your email authenticated through Microsoft 365, some of it may be marked as spam for inbound email (as described above), or it will be rejected if you do not publish SPF and try to relay it outbound through the service.</span></span> <span data-ttu-id="4cbdf-230">예를 들어, DMARC TXT 레코드를 형성할 때 사용자 도메인을 대신하여 메일을 보내는 서버 및 앱의 일부 IP 주소를 포함하지 않은 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-230">This happens, for example, if you forget to include some of the IP addresses for servers and apps that send mail on behalf of your domain when you form your DMARC TXT record.</span></span>

## <a name="how-microsoft-365-handles-inbound-email-that-fails-dmarc"></a><span data-ttu-id="4cbdf-231">Microsoft 365가 DMARC에 실패한 인바운드 전자 메일을 처리하는 방법</span><span class="sxs-lookup"><span data-stu-id="4cbdf-231">How Microsoft 365 handles inbound email that fails DMARC</span></span>

<span data-ttu-id="4cbdf-232">발신 서버의 DMARC 정책이 `p=reject`이면 [EOP](exchange-online-protection-overview.md)(Exchange Online 방지)는 메시지를 거부하는 대신 스푸핑으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-232">If the DMARC policy of the sending server is `p=reject`, [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) marks the message as spoof instead of rejecting it.</span></span> <span data-ttu-id="4cbdf-233">즉, 인바운드 전자 메일의 경우 Microsoft 365는 `p=reject` 및 `p=quarantine`을 동일한 방식으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-233">In other words, for inbound email, Microsoft 365 treats `p=reject` and `p=quarantine` the same way.</span></span> <span data-ttu-id="4cbdf-234">관리자는 [피싱 방지 정책](set-up-anti-phishing-policies.md)에서 스푸핑으로 분류된 메시지에 대해 수행할 작업을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-234">Admins can define the action to take on messages classified as spoof within the [anti-phishing policy](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="4cbdf-235">일부 정상적인 전자 메일이 DMARC 검사에 실패할 수 있으므로 Microsoft 365는 이와 같이 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-235">Microsoft 365 is configured like this because some legitimate email may fail DMARC.</span></span> <span data-ttu-id="4cbdf-236">예를 들어, 메일 그룹에 전송된 메시지가 모든 목록 참가자에게 릴레이되는 경우 DMARC 검사에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-236">For example, a message might fail DMARC if it is sent to a mailing list that then relays the message to all list participants.</span></span> <span data-ttu-id="4cbdf-237">Microsoft 365에서 이러한 메시지를 거부하는 경우 사용자가 정상적인 전자 메일을 잃을 수 있으며 이를 되찾을 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-237">If Microsoft 365 rejected these messages, people could lose legitimate email and have no way to retrieve it.</span></span> <span data-ttu-id="4cbdf-238">대신 이러한 메시지는 여전히 DMARC 검사에 실패하지만 스팸으로 표시되고 거부되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-238">Instead, these messages will still fail DMARC but they will be marked as spam and not rejected.</span></span> <span data-ttu-id="4cbdf-239">원하는 경우 사용자는 다음 방법을 통해 받은 편지함에서 이러한 메시지를 계속 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-239">If desired, users can still get these messages in their inbox through these methods:</span></span>

- <span data-ttu-id="4cbdf-240">사용자가 전자 메일 클라이언트를 사용하여 개별적으로 수신 허용 - 보낸 사람을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-240">Users add safe senders individually by using their email client.</span></span>

- <span data-ttu-id="4cbdf-241">관리자는 스푸핑을 허용하도록 [스푸핑 인텔리전스](learn-about-spoof-intelligence.md) 보고를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-241">Administrators can update the [Spoof Intelligence](learn-about-spoof-intelligence.md) reporting to allow the spoof.</span></span>

- <span data-ttu-id="4cbdf-242">관리자는 특정 보낸 사람의 메시지를 허용하는 모든 사용자에 대해 Exchange 메일 흐름 규칙 (전송 규칙이라고도 함)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-242">Administrators create an Exchange mail flow rule (also known as a transport rule) for all users that allows messages for those particular senders.</span></span>

<span data-ttu-id="4cbdf-243">자세한 내용은 [수신 허용 - 보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-243">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="how-microsoft-365-utilizes-authenticated-received-chain-arc"></a><span data-ttu-id="4cbdf-244">Microsoft 365가 ARC(Authenticated Received Chain)를 활용하는 방법</span><span class="sxs-lookup"><span data-stu-id="4cbdf-244">How Microsoft 365 utilizes Authenticated Received Chain (ARC)</span></span>

<span data-ttu-id="4cbdf-245">이제 Microsoft 365에서 호스팅되는 모든 사서함에는 메시지 배달 기능과 스푸핑 방지 기능이 향상되는 ARC의 이점을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-245">All hosted mailboxes in Microsoft 365 will now gain the benefit of ARC with improved deliverability of messages and enhanced anti-spoofing protection.</span></span> <span data-ttu-id="4cbdf-246">ARC는 원래 서버에서 받는 사람 사서함으로 전자 메일이 라우팅될 때 모든 참여 중개자, 홉의 전자 메일 인증 결과를 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-246">ARC preserves the email authentication results from all participating intermediaries, or hops, when an email is routed from the originating server to the recipient mailbox.</span></span> <span data-ttu-id="4cbdf-247">ARC 이전에는 전달 규칙이나 자동 서명을 비롯한 전자 메일 라우팅의 중개자가 수행한 수정으로 전자 메일이 받는 사람의 사서함에 도달했을 때 DMARC 오류가 발생할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-247">Before ARC, modifications performed by intermediaries in email routing, like forwarding rules or automatic signatures, could cause DMARC failures by the time the email reached the recipient mailbox.</span></span> <span data-ttu-id="4cbdf-248">ARC를 사용하여 인증 결과에 대한 암호화를 보존하면 Microsoft 365에서 전자 메일을 보낸 사람의 신뢰성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-248">With ARC, the cryptographic preservation of the authentication results allows Microsoft 365 to verify the authenticity of an email's sender.</span></span>

<span data-ttu-id="4cbdf-249">Microsoft 365는 현재 ARC를 사용하여 Microsoft가 ARC Sealer인 경우 인증 결과를 확인하지만, 향후 타사 ARC Sealer에 대한 지원을 추가할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-249">Microsoft 365 currently utilizes ARC to verify authentication results when Microsoft is the ARC Sealer, but plan to add support for third-party ARC sealers in the future.</span></span>

## <a name="troubleshooting-your-dmarc-implementation"></a><span data-ttu-id="4cbdf-250">DMARC 구현 문제 해결</span><span class="sxs-lookup"><span data-stu-id="4cbdf-250">Troubleshooting your DMARC implementation</span></span>

<span data-ttu-id="4cbdf-251">EOP가 첫 번째 항목이 아닌 사용자 도메인의 MX 레코드를 구성한 경우 사용자 도메인에 대해 DMARC 검사 실패가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-251">If you have configured your domain's MX records where EOP is not the first entry, DMARC failures will not be enforced for your domain.</span></span>

<span data-ttu-id="4cbdf-252">사용자가 고객이고 도메인의 기본 MX 레코드가 EOP를 가리키지 않는 경우에는 DMARC의 이점을 얻을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-252">If you're a customer, and your domain's primary MX record does not point to EOP, you will not get the benefits of DMARC.</span></span> <span data-ttu-id="4cbdf-253">예를 들어 MX 레코드를 온-프레미스 메일 서버로 지정한 다음 커넥터를 사용하여 전자 메일을 EOP로 경로 지정하는 경우에는 DMARC가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-253">For example, DMARC won't work if you point the MX record to your on-premises mail server and then route email to EOP by using a connector.</span></span> <span data-ttu-id="4cbdf-254">이 시나리오에서 수신 도메인은 사용자의 허용된 도메인 중 하나이고 EOP는 기본 MX가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-254">In this scenario, the receiving domain is one of your Accepted-Domains but EOP is not the primary MX.</span></span> <span data-ttu-id="4cbdf-255">예를 들어 contoso.com이 MX를 자체적으로 가리키고 EOP를 보조 MX 레코드로 사용한다고 가정하면 contoso.com의 MX 레코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-255">For example, suppose contoso.com points its MX at itself and uses EOP as a secondary MX record, contoso.com's MX record looks like the following:</span></span>

```console
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

<span data-ttu-id="4cbdf-256">모든 또는 대부분의 전자 메일은 기본 MX인 mail.contoso.com으로 먼저 경로 지정된 다음, 메일은 EOP로 경로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-256">All, or most, email will first be routed to mail.contoso.com since it's the primary MX, and then mail will get routed to EOP.</span></span> <span data-ttu-id="4cbdf-257">경우에 따라 EOP를 MX 레코드로 전혀 나열하지 않고 단순히 커넥터를 연결하여 전자 메일을 경로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-257">In some cases, you might not even list EOP as an MX record at all and simply hook up connectors to route your email.</span></span> <span data-ttu-id="4cbdf-258">DMARC 유효성 검사를 수행하기 위해 EOP가 첫 번째 항목일 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-258">EOP does not have to be the first entry for DMARC validation to be done.</span></span> <span data-ttu-id="4cbdf-259">모든 온-프레미스/비O365 서버가 DMARC 검사를 수행할 것이라고 확신할 수 없기 때문에 이는 유효성 검사만을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-259">It just ensures the validation, as we cannot be certain that all on-premise/non-O365 servers will do DMARC checks.</span></span>  <span data-ttu-id="4cbdf-260">DMARC TXT 레코드를 설정할 때 DMARC는 고객의 도메인 (서버가 아님)에 대해 수행될 수 있지만, 실제로 수행을 적용하는 것은 수신 서버에 달려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-260">DMARC is eligible to be enforced for a customer's domain (not server) when you set up the DMARC TXT record, but it is up to the receiving server to actually do the enforcement.</span></span>  <span data-ttu-id="4cbdf-261">수신 서버로 EOP를 설정하면 EOP가 DMARC 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-261">If you set up EOP as the receiving server, then EOP does the DMARC enforcement.</span></span>

![DMARC에 대한 문제 해결 그래픽, Daniel Mande 제공](../../media/Tp_DMARCTroublehoot.png)

## <a name="for-more-information"></a><span data-ttu-id="4cbdf-263">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="4cbdf-263">For more information</span></span>

<span data-ttu-id="4cbdf-264">DMARC에 대한 자세한 정보가 필요하신가요?</span><span class="sxs-lookup"><span data-stu-id="4cbdf-264">Want more information about DMARC?</span></span> <span data-ttu-id="4cbdf-265">다음 리소스가 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-265">These resources can help.</span></span>

- <span data-ttu-id="4cbdf-266">[스팸 방지 메시지 헤더](anti-spam-message-headers.md)에는 Microsoft 365에서 DMARC 검사에 사용하는 구문 및 헤더 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-266">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for DMARC checks.</span></span>

- <span data-ttu-id="4cbdf-267">M<sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group)의 [DMARC 교육 시리즈](https://www.m3aawg.org/activities/training/dmarc-training-series)를 이용하세요.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-267">Take the [DMARC Training Series](https://www.m3aawg.org/activities/training/dmarc-training-series) from M<sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group).</span></span>

- <span data-ttu-id="4cbdf-268">[dmarcian](https://space.dmarcian.com/deployment/)의 검사 목록을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-268">Use the checklist at [dmarcian](https://space.dmarcian.com/deployment/).</span></span>

- <span data-ttu-id="4cbdf-269">[DMARC.org](https://dmarc.org)의 출처로 바로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-269">Go directly to the source at [DMARC.org](https://dmarc.org).</span></span>

## <a name="see-also"></a><span data-ttu-id="4cbdf-270">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4cbdf-270">See also</span></span>

[<span data-ttu-id="4cbdf-271">Microsoft 365에서 SPF(Sender Policy Framework)를 사용하여 스푸핑을 방지하는 방법</span><span class="sxs-lookup"><span data-stu-id="4cbdf-271">How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)

[<span data-ttu-id="4cbdf-272">스푸핑을 방지할 수 있도록 Microsoft 365에서 SPF 설정하기</span><span class="sxs-lookup"><span data-stu-id="4cbdf-272">Set up SPF in Microsoft 365 to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

[<span data-ttu-id="4cbdf-273">DKIM을 사용하여 Microsoft 365의 사용자 지정 도메인에서 전송한 아웃바운드 전자 메일의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="4cbdf-273">Use DKIM to validate outbound email sent from your custom domain in Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md)
