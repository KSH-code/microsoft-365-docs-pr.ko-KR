---
title: EOP에서 피싱을 방지하기 위해 시작 주소의 유효성을 검사하는 방법
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: 관리자는 EOP(Exchange Online Protection)에서 수락 또는 거부하는 전자 메일 주소 유형에 대해 알아보고 피싱을 방지하기 위해 Outlook.com 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e7c2cbec49082fbded857dde13f73516fd3e0fd5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167518"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="949c5-103">EOP에서 피싱을 방지하기 위해 시작 주소의 유효성을 검사하는 방법</span><span class="sxs-lookup"><span data-stu-id="949c5-103">How EOP validates the From address to prevent phishing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="949c5-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="949c5-104">**Applies to**</span></span>
- [<span data-ttu-id="949c5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="949c5-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="949c5-106">Microsoft Defender for Office 365 요금제 1 및 계획 2</span><span class="sxs-lookup"><span data-stu-id="949c5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="949c5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="949c5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="949c5-108">피싱 공격은 모든 전자 메일 조직에 지속적으로 위협됩니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-108">Phishing attacks are a constant threat to any email organization.</span></span> <span data-ttu-id="949c5-109">공격자는 스푸핑된(위조된) 보낸 사람 전자 메일 주소를 사용하는 것 외에도 보낸 사람 주소의 값을 사용하여 인터넷 표준을 위반하는 경우가 종종 있습니다. [](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="949c5-109">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="949c5-110">이러한 유형의 피싱을 방지하기 위해 EOP(Exchange Online Protection) 및 Outlook.com 이 문서에 설명된 RFC 규격 보낸사서 주소를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-110">To help prevent this type of phishing, Exchange Online Protection (EOP) and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this article.</span></span> <span data-ttu-id="949c5-111">이 적용은 2017년 11월에 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-111">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="949c5-112">**참고**:</span><span class="sxs-lookup"><span data-stu-id="949c5-112">**Notes**:</span></span>

- <span data-ttu-id="949c5-113">이 문서에 설명된 바와 같이 주소가 올지 의문이 있는 조직으로부터 전자 메일을 정기적으로 받는 경우 이러한 조직에서 최신 보안 표준을 준수하도록 전자 메일 서버를 업데이트하도록 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-113">If you regularly receive email from organizations that have malformed From addresses as described in this article, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="949c5-114">관련 보낸 사람 필드(대신 보내기 및 메일링 목록에서 사용)는 이러한 요구 사항의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-114">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="949c5-115">자세한 내용은 다음 블로그 게시물을 [참조하세요. 전자 메일의 '보낸 사람'을](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)참조하는 경우 무엇을 의미하나요?</span><span class="sxs-lookup"><span data-stu-id="949c5-115">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="949c5-116">전자 메일 메시지 표준 개요</span><span class="sxs-lookup"><span data-stu-id="949c5-116">An overview of email message standards</span></span>

<span data-ttu-id="949c5-117">표준 SMTP 전자 메일 메시지는 메시지 봉투와 메시지 콘텐츠로 구성됩니다. </span><span class="sxs-lookup"><span data-stu-id="949c5-117">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="949c5-118">메시지 봉투에는 SMTP 서버 간에 메시지를 전송하고 배달하는 데 필요한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-118">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="949c5-119">메시지 콘텐츠에는 메시지 헤더 필드(총체적으로 메시지 *헤더)와* 메시지 본문이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-119">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="949c5-120">메시지 봉투는 [RFC 5321에](https://tools.ietf.org/html/rfc5321)설명되어 있으며 메시지 헤더는 [RFC 5322에 설명되어 있습니다.](https://tools.ietf.org/html/rfc5322)</span><span class="sxs-lookup"><span data-stu-id="949c5-120">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="949c5-121">받는 사람은 메시지 전송 프로세스에 의해 생성되어 실제로 메시지의 일부가 아니기 때문에 실제 메시지 봉투를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-121">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="949c5-122">MAIL FROM 주소, P1 보낸 사람 또는 봉투 보낸 사람라고도 하는 주소는 메시지의 SMTP 전송에 사용되는 전자 메일 `5321.MailFrom` 주소입니다. </span><span class="sxs-lookup"><span data-stu-id="949c5-122">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="949c5-123">이 전자 메일 주소는  일반적으로 메시지 헤더의 반환 경로 헤더 필드에 기록됩니다(보낸 사람이 다른  반환 경로 전자 메일 주소를 지정하는 것은 가능).</span><span class="sxs-lookup"><span data-stu-id="949c5-123">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="949c5-124">보낸 사람(보낸 사람 주소 또는 P2 보낸 사람)은 보낸 사람 헤더 필드의 전자 메일 주소로, 전자 메일 클라이언트에 표시되는 보낸 사람 전자 메일 `5322.From` 주소입니다. </span><span class="sxs-lookup"><span data-stu-id="949c5-124">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="949c5-125">From 주소는 이 문서의 요구 사항에 초점을 맞추고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-125">The From address is the focus of the requirements in this article.</span></span>

<span data-ttu-id="949c5-126">From 주소는 여러 RFC(예: RFC 5322 섹션 3.2.3, 3.4 및 3.4.1 및 [RFC 3696)에서](https://tools.ietf.org/html/rfc3696)자세히 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-126">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="949c5-127">주소에 많은 변형이 있으며 유효하거나 잘못된 것으로 간주되는 것이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-127">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="949c5-128">간단하게 유지를 위해 다음과 같은 형식과 정의를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-128">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="949c5-129">**표시 이름**: 전자 메일 주소의 소유자를 설명하는 선택적 구입니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-129">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="949c5-130">표시 이름은 항상 표시된 것 같이 이중 인용 부호(")로 묶는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-130">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="949c5-131">표시 이름에 COMMA가  포함되어 있는 경우 RFC 5322당 문자열을 큰 인용 부호로 묶아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-131">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="949c5-132">From 주소에 표시 이름이 포함되어 있는 경우 EmailAddress 값은 표시된 < > 괄호로 묶아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-132">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="949c5-133">표시 이름과 전자 메일 주소 사이에 공백을 삽입하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-133">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="949c5-134">**EmailAddress**: 전자 메일 주소에 다음 형식이 `local-part@domain` 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-134">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="949c5-135">**local-part**: 주소와 연결된 사서함을 식별하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-135">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="949c5-136">이 값은 도메인 내에서 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-136">This value is unique within the domain.</span></span> <span data-ttu-id="949c5-137">사서함 소유자의 사용자 이름 또는 GUID가 사용되는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-137">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="949c5-138">**domain**: 전자 메일 주소의 로컬 부분으로 식별된 사서함을 호스트하는 전자 메일 서버의 FQDN(FQDN)입니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-138">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="949c5-139">다음은 EmailAddress 값에 대한 몇 가지 추가 고려 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-139">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="949c5-140">전자 메일 주소는 하나만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-140">Only one email address.</span></span>
  - <span data-ttu-id="949c5-141">괄호는 공백으로 구분하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-141">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="949c5-142">전자 메일 주소 다음에 추가 텍스트를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-142">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="949c5-143">유효하고 유효하지 않은 From 주소의 예</span><span class="sxs-lookup"><span data-stu-id="949c5-143">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="949c5-144">다음 전자 메일 주소가 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-144">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="949c5-145">`From: < sender@contoso.com >` 괄호와 전자 메일 주소 사이에 공백이 있기 때문에 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-145">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="949c5-146">`From: Microsoft 365 <sender@contoso.com>` 표시 이름은 이중 인용 부호로 묶이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-146">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="949c5-147">다음 전자 메일 주소가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-147">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="949c5-148">**No From address**: Some automated messages don't include a From address.</span><span class="sxs-lookup"><span data-stu-id="949c5-148">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="949c5-149">과거에는 Microsoft 365 또는 Outlook.com 보낸사용자 주소 없이 메시지를 받았을 때 서비스에서 다음과 같은 기본 보낸사용자: 주소를 추가하여 메시지를 배달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-149">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="949c5-150">이제 보낸 주소가 비어 있는 메시지는 더 이상 수락되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-150">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="949c5-151">`From: Microsoft 365 sender@contoso.com` 표시 이름이 있지만 전자 메일 주소는 앵글 괄호로 묶이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-151">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="949c5-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (전자 메일 주소 다음에 있는 텍스트)</span><span class="sxs-lookup"><span data-stu-id="949c5-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="949c5-153">`From: Sender, Example <sender.example@contoso.com>` 표시 이름에는 COMMA(콤보)가 포함되어 있지만 인용 부호가 묶이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-153">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="949c5-154">`From: "Microsoft 365 <sender@contoso.com>"` 전체 값이 2차원 인용 부호로 잘못 묶입니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-154">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="949c5-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` 표시 이름이 있지만 전자 메일 주소는 앵글 괄호로 묶이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="949c5-156">`From: Microsoft 365<sender@contoso.com>` 표시 이름과 왼쪽 괄호 사이에 공백이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-156">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="949c5-157">`From: "Microsoft 365"<sender@contoso.com>` 닫는 이중 인용 부호와 왼쪽 괄호 사이의 공백이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="949c5-157">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="949c5-158">사용자 지정 도메인에 대한 자동 응답 표시 안</span><span class="sxs-lookup"><span data-stu-id="949c5-158">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="949c5-159">이 값을 사용하여 자동 응답을 `From: <>` 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-159">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="949c5-160">대신 사용자 지정 도메인에 대해 null MX 레코드를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-160">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="949c5-161">응답 서버가 메시지를 보낼 수 있는 게시된 주소가 아니기 때문에 자동 응답(및 모든 답장)은 자연스럽게 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-161">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="949c5-162">전자 메일을 받을 수 없는 전자 메일 도메인을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="949c5-162">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="949c5-163">예를 들어 기본 도메인이 contoso.com 경우 기본 도메인을 noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="949c5-163">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="949c5-164">이 도메인에 대한 null MX 레코드는 단일 기간으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-164">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="949c5-165">예:</span><span class="sxs-lookup"><span data-stu-id="949c5-165">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="949c5-166">MX 레코드 설정에 대한 자세한 내용은 모든 DNS 호스팅 공급자에서 [Microsoft 365용 DNS 레코드 만들기를 참조하세요.](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="949c5-166">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="949c5-167">null MX를 게시하는 자세한 내용은 [RFC 7505를 참조하세요.](https://tools.ietf.org/html/rfc7505)</span><span class="sxs-lookup"><span data-stu-id="949c5-167">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="949c5-168">주소 적용에서 적용을 드리우기</span><span class="sxs-lookup"><span data-stu-id="949c5-168">Override From address enforcement</span></span>

<span data-ttu-id="949c5-169">인바운드 전자 메일의 보낸 사람 주소 요구 사항을 무시하기 위해 [Microsoft 365에서](create-safe-sender-lists-in-office-365.md)수신 허용 - 보낸 사람 목록 만들기에 설명된 IP 허용 목록(연결 필터링) 또는 메일 흐름 규칙(전송 규칙)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-169">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="949c5-170">Microsoft 365에서 보내는 아웃바운드 전자 메일의 보낸 사람 주소 요구 사항은 다시 정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-170">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="949c5-171">또한 Outlook.com 경우에도 어떠한 종류의 다시도 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="949c5-171">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="949c5-172">Microsoft 365에서 사이버 범죄를 방지하고 보호하는 다른 방법</span><span class="sxs-lookup"><span data-stu-id="949c5-172">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="949c5-173">피싱, 스팸, 데이터 위반 및 기타 위협으로부터 조직을 강화하는 방법에 대한 자세한 내용은 [비즈니스용 Microsoft 365](../../admin/security-and-compliance/secure-your-business-data.md)계획을 보호하는 10가지 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="949c5-173">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>
