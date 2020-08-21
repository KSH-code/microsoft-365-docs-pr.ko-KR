---
title: EOP가 From 주소의 유효성을 검사하여 피싱을 방지하는 방법
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: 관리자는 EOP(Exchange Online Protection) 및 기능에 의해 수락 또는 거부되고 이러한 전자 메일 주소 유형에 Outlook.com 이러한 유형에 Outlook.com 이러한 유형에 대해 알아두고 못하시기 위해 이용할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c67cf5855f2b0a99cf8d03bb6d7ba8557329b300
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827424"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="02f6d-103">EOP가 From 주소의 유효성을 검사하여 피싱을 방지하는 방법</span><span class="sxs-lookup"><span data-stu-id="02f6d-103">How EOP validates the From address to prevent phishing</span></span>

<span data-ttu-id="02f6d-104">피싱 공격은 모든 전자 메일 조직의 끊임이 다른 위협입니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-104">Phishing attacks are a constant threat to any email organization.</span></span> <span data-ttu-id="02f6d-105">위임된(위의) [보낸 사람](anti-spoofing-protection.md)전자 메일 주소를 사용하는 방법 외에도 공격자는 인터넷 표준을 위반하는 보낸 사람 주소 값을 사용하는 경우가 자중있습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-105">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="02f6d-106">이러한 유형의 피싱을 방지하기 위해서는 이 항목에서 설명한 것과 같이 EOP(Exchange Online Protection) 및 Outlook.com 메시지에 RFC 호환 From 주소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-106">To help prevent this type of phishing, Exchange Online Protection (EOP) and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this topic.</span></span> <span data-ttu-id="02f6d-107">이 적용은 2017년 11월에 활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-107">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="02f6d-108">**참고:**</span><span class="sxs-lookup"><span data-stu-id="02f6d-108">**Notes**:</span></span>

- <span data-ttu-id="02f6d-109">이 항목에 설명된 바와 같이 보낸 사람 주소가 잘못된 조직에서 정기적으로 전자 메일을 받을 경우 이러한 조직이 최신 보안 표준을 따르도록 전자 메일 서버를 업데이트하도록 유도합니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-109">If you regularly receive email from organizations that have malformed From addresses as described in this topic, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="02f6d-110">관련 보낸 사람 필드(대신 보내기 및 메일 그룹에서 사용)는 이러한 요구 사항의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-110">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="02f6d-111">자세한 내용은 다음 블로그 게시물을 참조하세요. [전자 메일의 '보낸 사람'을 참조할 때는 어떤 의미가 있나요?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)</span><span class="sxs-lookup"><span data-stu-id="02f6d-111">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="02f6d-112">전자 메일 메시지 표준 개요</span><span class="sxs-lookup"><span data-stu-id="02f6d-112">An overview of email message standards</span></span>

<span data-ttu-id="02f6d-113">표준 SMTP 전자 메일 메시지는 메시지 *봉투와 메시지 내용으로* 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-113">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="02f6d-114">메시지 봉투에는 SMTP 서버 간에 메시지를 전송 및 배달하는 데 필요한 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-114">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="02f6d-115">메시지 내용에는 메시지 헤더 필드(사서함 헤더) 및 *메시지 본문이*들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-115">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="02f6d-116">메시지 봉투는 [RFC 5321에 설명되어](https://tools.ietf.org/html/rfc5321)있고 메시지 헤더는 [RFC 5322에 설명되어 있습니다.](https://tools.ietf.org/html/rfc5322)</span><span class="sxs-lookup"><span data-stu-id="02f6d-116">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="02f6d-117">메시지 봉투는 메시지 전송 프로세스에 의해 생성되며 실제로는 메시지의 일부가 아닌 실제 메시지 봉투를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-117">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="02f6d-118">이 `5321.MailFrom` **주소(메일 보낸 사람** 주소, P1 보낸 사람 또는 봉투 보낸 사람이라고도 함)는 메시지의 SMTP 전송에 사용되는 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-118">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="02f6d-119">이 전자 메일 주소는 일반적으로 메시지 헤더의 **Return-Path** 헤더 필드에 기록됩니다(보낸 사람이 서로 다른 반기 전자 메일 **주소를 지정할 수는** 있습니다).</span><span class="sxs-lookup"><span data-stu-id="02f6d-119">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="02f6d-120">보낸 사람 주소 또는 P2 보낸 사람이라고도 하는 보낸 사람 주소는 보낸 사람 헤더 필드의 전자 메일 주소이며, 전자 메일 클라이언트에 표시되는 보낸 `5322.From` 사람의 전자 메일 주소입니다. **From**</span><span class="sxs-lookup"><span data-stu-id="02f6d-120">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="02f6d-121">시작 주소는 이 항목의 요구 사항에 대해 중점적인 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-121">The From address is the focus of the requirements in this topic.</span></span>

<span data-ttu-id="02f6d-122">From 주소는 여러 RFC(예: RFC 5322 섹션 3.2.3, 3.4, 3.4.1 및 [RFC 3696)에 자세히 정의되어 있습니다.](https://tools.ietf.org/html/rfc3696)</span><span class="sxs-lookup"><span data-stu-id="02f6d-122">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="02f6d-123">주소 지정과 유효하지 않은 것으로 간주되는 점은 많습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-123">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="02f6d-124">단순히 유지하려면 다음과 같은 형식 및 정의를 고려하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-124">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="02f6d-125">**표시 이름:** 전자 메일 주소 소유자를 설명하는 선택적 구입니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-125">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="02f6d-126">표시 이름을 항상 큰따옴표(")로 묶는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-126">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="02f6d-127">표시 이름에 쉼표가 포함되어 _must_ 있는 경우 RFC 5322별 큰따옴표로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-127">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="02f6d-128">From 주소에 표시 이름이 포함된 경우 EmailAddress 값은 표시된 바와 같이 각도(< >)로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-128">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="02f6d-129">표시 이름과 전자 메일 주소 사이에 공백을 삽입하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-129">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="02f6d-130">**EmailAddress**: The email address uses the format `local-part@domain` :</span><span class="sxs-lookup"><span data-stu-id="02f6d-130">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="02f6d-131">**로컬 부분:** 주소와 연결된 사서함을 식별하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-131">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="02f6d-132">이 값은 도메인 내에서 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-132">This value is unique within the domain.</span></span> <span data-ttu-id="02f6d-133">사서함 소유자의 사용자 이름 또는 GUID가 사용되는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-133">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="02f6d-134">**domain:** 전자 메일 주소의 로컬 부분으로 식별되는 사서함을 호스트하는 전자 메일 서버의 FQDN(정규화된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-134">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="02f6d-135">다음은 EmailAddress 값을 사용하기 위한 추가 고려 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-135">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="02f6d-136">하나의 전자 메일 주소</span><span class="sxs-lookup"><span data-stu-id="02f6d-136">Only one email address.</span></span>
  - <span data-ttu-id="02f6d-137">따라서 각괄러스를 공백과 구분하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-137">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="02f6d-138">전자 메일 주소 뒤에 추가 텍스트를 포함하지 마합니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-138">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="02f6d-139">유효한 보낸 사람 주소 및 잘못된 보낸 사람 주소의 예</span><span class="sxs-lookup"><span data-stu-id="02f6d-139">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="02f6d-140">유효한 보낸 사람 전자 메일 주소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-140">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="02f6d-141">`From: < sender@contoso.com >` 각괄괄로 이메일 주소 사이에 공백이 있기 때문에 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-141">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="02f6d-142">`From: Microsoft 365 <sender@contoso.com>` 표시 이름이 큰따옴표로 묶지 않았기 때문에 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-142">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="02f6d-143">다음의 보낸 사람 전자 메일 주소는 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-143">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="02f6d-144">**보낸 사람 주소**없음: 일부 자동화된 메시지에는 보낸 사람 주소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-144">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="02f6d-145">과면에 Microsoft 365 또는 Outlook.com 보낸 사람 주소가 없는 메시지를 받은 경우 서비스는 메시지 배달 가능하도록 만들기 위해 다음과 같은 기본 보낸 사람: 주소를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-145">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="02f6d-146">이제 보낸 사람 주소가 비어 있는 메시지는 더 이상 수락되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-146">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="02f6d-147">`From: Microsoft 365 sender@contoso.com` 표시 이름이 있지만 전자 메일 주소는 Angle 괄옴표로 묶지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-147">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="02f6d-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (전자 메일 주소 다음에 오는 텍스트)</span><span class="sxs-lookup"><span data-stu-id="02f6d-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="02f6d-149">`From: Sender, Example <sender.example@contoso.com>` 표시 이름은 쉼표를 포함하지만 큰따옴표로 묶지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-149">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="02f6d-150">`From: "Microsoft 365 <sender@contoso.com>"` (전체 값이 큰따옴표로 묶여 있지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="02f6d-150">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="02f6d-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` 표시 이름이 있지만 전자 메일 주소는 Angle 괄옴표로 묶지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="02f6d-152">`From: Microsoft 365<sender@contoso.com>` 표시 이름과 왼쪽 각도 대괄이동</span><span class="sxs-lookup"><span data-stu-id="02f6d-152">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="02f6d-153">`From: "Microsoft 365"<sender@contoso.com>` 닫는 큰따옴표와 왼쪽 각도 사이에는 공백을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-153">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="02f6d-154">사용자 지정 도메인으로 자동 회신을 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-154">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="02f6d-155">이 값을 사용하여 자동 `From: <>` 회신을 표시하지 않을 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-155">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="02f6d-156">대신 사용자 지정 도메인에 대해 null MX 레코드를 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-156">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="02f6d-157">응답 서버에서 메시지를 보낼 수 있는 게시된 주소가 없기 때문에 자동 회신(및 모든 회신)은 자연스러운 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-157">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="02f6d-158">전자 메일을 받을 수 되지 않는 전자 메일 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-158">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="02f6d-159">예를 들어 기본 도메인이 마이그레이션된 contoso.com 도메인을 선택할 noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="02f6d-159">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="02f6d-160">이 도메인에 대한 Null MX 레코드는 단일 기간으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-160">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="02f6d-161">예제:</span><span class="sxs-lookup"><span data-stu-id="02f6d-161">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="02f6d-162">MX 레코드 설정에 대한 자세한 내용은 DNS 호스팅 [공급자에서 Microsoft 365용 DNS 레코드 만들기를 참조하세요.](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="02f6d-162">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="02f6d-163">Null MX를 게시하는 방법에 대한 자세한 내용은 [RFC 7505를 참조하세요.](https://tools.ietf.org/html/rfc7505)</span><span class="sxs-lookup"><span data-stu-id="02f6d-163">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="02f6d-164">주소 적용 재정의</span><span class="sxs-lookup"><span data-stu-id="02f6d-164">Override From address enforcement</span></span>

<span data-ttu-id="02f6d-165">인바운드 전자 메일에 대한 보낸 사람 주소 요구 사항을 무시하려면 [Microsoft 365에서 안전한](create-safe-sender-lists-in-office-365.md)보낸 사람 목록 만들기에 설명된 IP 허용 목록(연결 필터링) 또는 메일 흐름 규칙(전송 규칙이라고도 함)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-165">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="02f6d-166">Microsoft 365에서 보내는 아웃바운드 전자 메일에 대한 보낸 사람 주소 요구 사항은 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-166">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="02f6d-167">또한 Outlook.com 지원을 통해 어떤 종류의 재정의도 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02f6d-167">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="02f6d-168">Microsoft 365에서 암호화를 방지하고 보호하는 기타 방법</span><span class="sxs-lookup"><span data-stu-id="02f6d-168">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="02f6d-169">피싱, 스팸, 데이터 침해 및 기타 위협으로부터 조직을 강화하는 방법에 대한 자세한 내용은 [비즈니스용 Microsoft 365 요금제의 보안을 강화할 수 있는 상위 10가지 방법을 참조하세요.](../../admin/security-and-compliance/secure-your-business-data.md)</span><span class="sxs-lookup"><span data-stu-id="02f6d-169">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>
