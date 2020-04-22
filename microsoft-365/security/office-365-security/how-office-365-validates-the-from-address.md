---
title: Microsoft 365에서 보낸 사람 주소의 유효성을 검사 하 여 피싱을 방지 하는 방법
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Microsoft 365의 인바운드 메시지에 대 한 전자 메일 주소에서의 요구 사항에 대 한 lear 11 월 2017 현재까지 서비스에서 스푸핑을 방지 하는 데 도움이 되는 주소에서 RFC 규격이 필요 합니다.
ms.openlocfilehash: 876ede087b37c381b9e9b557268057122e0987c0
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633981"
---
# <a name="how-microsoft-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="add29-104">Microsoft 365에서 보낸 사람 주소의 유효성을 검사 하 여 피싱을 방지 하는 방법</span><span class="sxs-lookup"><span data-stu-id="add29-104">How Microsoft 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="add29-105">Microsoft 365 전자 메일 계정에는 많은 수의 피싱 공격이 수신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="add29-105">Microsoft 365 email accounts receive an increasingly large number of phishing attacks.</span></span> <span data-ttu-id="add29-106">공격자는 [가짜 (위조) 보낸 사람 전자 메일 주소](anti-spoofing-protection.md)를 사용 하는 것 외에도 발신자 주소에 인터넷 표준을 위반 하는 값을 사용 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-106">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="add29-107">이러한 유형의 피싱을 방지 하기 위해 Microsoft 365 및 Outlook.com에는이 항목에 설명 된 대로 RFC 규격 From 주소를 포함 하기 위한 인바운드 메시지가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="add29-107">To help prevent this type of phishing, Microsoft 365 and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this topic.</span></span> <span data-ttu-id="add29-108">이 적용은 11 월 2017에서 사용 하도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-108">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="add29-109">**참고:**</span><span class="sxs-lookup"><span data-stu-id="add29-109">**Notes**:</span></span>

- <span data-ttu-id="add29-110">이 항목에서 설명 하는 주소에서 형식이 잘못 된 조직 으로부터 전자 메일을 정기적으로 수신 하는 경우 이러한 조직이 최신 보안 표준을 준수 하도록 전자 메일 서버를 업데이트 하도록 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="add29-110">If you regularly receive email from organizations that have malformed From addresses as described in this topic, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="add29-111">"대신 보내기" 및 "메일 그룹에서 사용 하는" 관련 보낸 사람 "필드에는 이러한 요구 사항이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-111">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="add29-112">자세한 내용은 다음 블로그 게시물: [전자 메일의 ' 보낸 사람 '을 참조](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)하는 경우 무슨 의미 입니까?를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="add29-112">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="add29-113">전자 메일 메시지 표준 개요</span><span class="sxs-lookup"><span data-stu-id="add29-113">An overview of email message standards</span></span>

<span data-ttu-id="add29-114">표준 SMTP 전자 메일 메시지는 *메시지 봉투* 와 메시지 콘텐츠로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="add29-114">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="add29-115">메시지 봉투에는 SMTP 서버 간에 메시지를 전송 및 배달 하는 데 필요한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-115">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="add29-116">메시지 콘텐츠에는 메시지 헤더 필드 (통칭 *메시지 헤더*) 및 메시지 본문이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="add29-116">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="add29-117">메시지 봉투는 [rfc 5321](https://tools.ietf.org/html/rfc5321)에 설명 되어 있고 메시지 헤더는 [rfc 5322](https://tools.ietf.org/html/rfc5322)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-117">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="add29-118">실제 메시지 봉투는 메시지 전송 프로세스에 의해 생성 되며 실제로는 메시지의 일부가 아니기 때문에 받는 사람에 게는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-118">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="add29-119">`5321.MailFrom` 주소 ( **메일** 보낸 사람 주소, P1 sender 또는 envelope sender)는 메시지의 SMTP 전송에 사용 되는 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="add29-119">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="add29-120">이 전자 메일 주소는 일반적으로 메시지 헤더의 **반환 경로** 헤더 필드에 기록 됩니다 (보낸 사람이 다른 **반환 경로** 전자 메일 주소를 지정할 수 있지만).</span><span class="sxs-lookup"><span data-stu-id="add29-120">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="add29-121">보낸 사람 주소 또는 P2 보낸 사람이 라고도 하는 전자 메일 주소는 보낸 사람의 전자 메일 주소 이며 전자 메일 클라이언트에 표시 됩니다. **From** `5322.From`</span><span class="sxs-lookup"><span data-stu-id="add29-121">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="add29-122">보낸 사람 주소는이 항목의 요구 사항에 중점을 둔 것입니다.</span><span class="sxs-lookup"><span data-stu-id="add29-122">The From address is the focus of the requirements in this topic.</span></span>

<span data-ttu-id="add29-123">보낸 사람 주소는 몇 가지 Rfc (예: RFC 5322, 3.4, 3.4.1 및 [RFC 3696](https://tools.ietf.org/html/rfc3696))에서 자세히 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="add29-123">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="add29-124">주소 지정에는 다양 한 변형이 있으며 유효한 것으로 간주 되는 것으로 생각 됩니다.</span><span class="sxs-lookup"><span data-stu-id="add29-124">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="add29-125">이를 단순하게 유지 하려면 다음 형식과 정의를 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="add29-125">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="add29-126">**표시 이름**: 전자 메일 주소의 소유자를 설명 하는 선택적 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="add29-126">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="add29-127">표시 되는 대로 항상 display name을 큰따옴표 (")로 묶는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-127">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="add29-128">표시 이름에 쉼표가 포함 되어 있으면 RFC 5322 당 큰따옴표를 큰따옴표로 묶어야 _합니다_ .</span><span class="sxs-lookup"><span data-stu-id="add29-128">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="add29-129">보낸 사람 주소에 표시 이름이 포함 되어 있는 경우 EmailAddress 값은 표시 된 대로 꺾쇠 괄호 (< >)로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="add29-129">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="add29-130">표시 이름과 전자 메일 주소 사이에 공백을 삽입 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-130">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="add29-131">**EmailAddress**: 전자 메일 주소는 다음 형식을 `local-part@domain`사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="add29-131">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="add29-132">**local part**: 주소와 연결 된 사서함을 식별 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="add29-132">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="add29-133">이 값은 도메인 내에서 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="add29-133">This value is unique within the domain.</span></span> <span data-ttu-id="add29-134">사서함 소유자의 사용자 이름 또는 GUID가 사용 되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-134">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="add29-135">**도메인**: 전자 메일 주소의 로컬 부분으로 식별 되는 사서함을 호스트 하는 전자 메일 서버의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="add29-135">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="add29-136">다음은 EmailAddress 값에 대 한 몇 가지 추가 고려 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="add29-136">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="add29-137">전자 메일 주소 하나만</span><span class="sxs-lookup"><span data-stu-id="add29-137">Only one email address.</span></span>
  - <span data-ttu-id="add29-138">꺾쇠 괄호는 공백으로 구분 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-138">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="add29-139">전자 메일 주소 뒤에 추가 텍스트를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-139">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="add29-140">유효 및 잘못 된 주소의 예</span><span class="sxs-lookup"><span data-stu-id="add29-140">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="add29-141">다음은 유효한 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="add29-141">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="add29-142">`From: < sender@contoso.com >`꺾쇠 괄호와 전자 메일 주소 사이에는 공백이 있으므로 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-142">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="add29-143">`From: Microsoft 365 <sender@contoso.com>`표시 이름이 큰따옴표로 묶여 있지 않으므로 권장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-143">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="add29-144">다음의 보낸 사람 전자 메일 주소가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-144">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="add29-145">**보낸 사람 주소**: 일부 자동 메시지에는 보낸 사람 주소가 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-145">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="add29-146">더 이상 Microsoft 365 또는 Outlook.com에서 보낸 사람 주소가 없는 메시지를 받은 경우 서비스는 다음의 기본값을에서 메시지를 제공 하는 주소를 지정 합니다 .로 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-146">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="add29-147">이제는 보낸 사람 주소가 비어 있는 메시지가 더 이상 수락 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-147">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="add29-148">`From: Microsoft 365 sender@contoso.com`표시 이름은 제공 되지만 전자 메일 주소는 꺾쇠 괄호로 묶여 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-148">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="add29-149">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)`(전자 메일 주소 다음에 오는 텍스트)</span><span class="sxs-lookup"><span data-stu-id="add29-149">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="add29-150">`From: Sender, Example <sender.example@contoso.com>`(표시 이름에는 쉼표가 포함 되어 있지만 큰따옴표로 묶지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="add29-150">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="add29-151">`From: "Microsoft 365 <sender@contoso.com>"`전체 값이 큰따옴표로 잘못 묶여 있습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-151">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="add29-152">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com`표시 이름은 제공 되지만 전자 메일 주소는 꺾쇠 괄호로 묶여 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-152">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="add29-153">`From: Microsoft 365<sender@contoso.com>`(표시 이름 및 왼쪽 꺽쇠 괄호 사이에 공백 없음)</span><span class="sxs-lookup"><span data-stu-id="add29-153">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="add29-154">`From: "Microsoft 365"<sender@contoso.com>`닫는 큰따옴표와 왼쪽 꺽쇠 괄호 사이에는 공백이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="add29-154">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="add29-155">사용자 지정 도메인에 대 한 자동 회신을 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-155">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="add29-156">자동 회신을 표시 하지 `From: <>` 않으려면이 값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-156">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="add29-157">대신 사용자 지정 도메인에 대해 null MX 레코드를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="add29-157">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="add29-158">응답 서버가 메시지를 보낼 수 있는 게시 된 주소가 없기 때문에 자동 회신 (및 모든 응답)은 자연스럽 게 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-158">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="add29-159">전자 메일을 받을 수 없는 전자 메일 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="add29-159">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="add29-160">예를 들어 주 도메인이 contoso.com 인 경우 noreply.contoso.com을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-160">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="add29-161">이 도메인에 대 한 null MX 레코드는 단일 기간으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="add29-161">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="add29-162">예시:</span><span class="sxs-lookup"><span data-stu-id="add29-162">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="add29-163">MX 레코드를 설정 하는 방법에 대 한 자세한 내용은 [dns 호스팅 공급자에서 Microsoft 365에 대 한 dns 레코드 만들기](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="add29-163">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="add29-164">Null MX를 게시 하는 방법에 대 한 자세한 내용은 [RFC 7505](https://tools.ietf.org/html/rfc7505)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="add29-164">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="add29-165">주소 적용에서 무시</span><span class="sxs-lookup"><span data-stu-id="add29-165">Override From address enforcement</span></span>

<span data-ttu-id="add29-166">인바운드 전자 메일에 대해 From 주소 요구 사항을 무시 하려면 [Microsoft 365에서 수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)에 설명 된 대로 IP Allow List (연결 필터링) 또는 메일 흐름 규칙 (전송 규칙이 라고도 함)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-166">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="add29-167">Microsoft 365에서 보내는 아웃 바운드 전자 메일에 대 한 보낸 사람 주소 요구 사항을 재정의할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-167">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="add29-168">또한 Outlook.com에서는 지원을 통해 모든 종류의 재정의를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="add29-168">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="add29-169">Microsoft 365에서 cybercrimes을 방지 하 고 보호 하는 기타 방법</span><span class="sxs-lookup"><span data-stu-id="add29-169">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="add29-170">피싱, 스팸, 데이터 위반 및 기타 위협 으로부터 조직을 강화 하는 방법에 대 한 자세한 내용은 [Top 10 방법으로 Microsoft 365 for business 요금제](../../admin/security-and-compliance/secure-your-business-data.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="add29-170">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>