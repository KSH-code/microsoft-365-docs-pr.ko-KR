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
ms.localizationpriority: medium
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: 관리자는 피싱 방지를 위해 EOP(Exchange Online Protection 또는 Outlook.com)에서 수락 또는 거부하는 전자 메일 주소 유형에 대해 Outlook 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 412b6eb7045051c21a88c8b4b2ba5e80a06832dd
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60199432"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>EOP에서 피싱을 방지하기 위해 시작 주소의 유효성을 검사하는 방법

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

피싱 공격은 모든 전자 메일 조직에 대한 지속적인 위협입니다. [스푸핑된(위조된)](anti-spoofing-protection.md)보낸 사람 전자 메일 주소를 사용하는 것 외에도 공격자는 보낸 사람 주소에서 인터넷 표준을 위반하는 값을 자주 사용합니다. 이러한 유형의 피싱을 방지하려면 이제 EOP(Exchange Online Protection) 및 Outlook.com에 이 문서에 설명된 RFC 규격 보낸사용자 주소를 포함해야 합니다. 이 적용은 2017년 11월에 사용하도록 설정되어 있습니다.

**참고**:

- 이 문서에 설명된 바와 같이 주소가 올드 메일이 올 수 없는 조직으로부터 전자 메일을 정기적으로 받는 경우 이러한 조직은 최신 보안 표준을 준수하도록 전자 메일 서버를 업데이트하도록 권장합니다.

- 관련 보낸 사람 필드(대신 보내기 및 메일 보내기 목록에서 사용)는 이러한 요구 사항의 영향을 받지 않습니다. 자세한 내용은 다음 블로그 게시물을 [참조하세요. 전자 메일의 '보낸 사람'을](/archive/blogs/tzink/what-do-we-mean-when-we-refer-to-the-sender-of-an-email)참조하는 경우 무엇을 의미하나요? 를 참조하세요.

## <a name="an-overview-of-email-message-standards"></a>전자 메일 메시지 표준 개요

표준 SMTP 전자 메일 메시지는 메시지 봉투와 메시지 콘텐츠로 구성됩니다.  메시지 봉투에는 SMTP 서버 간에 메시지를 전송하고 배달하는 데 필요한 정보가 포함되어 있습니다. 메시지 콘텐츠에는 메시지 헤더 필드(총체적으로 메시지 *헤더)와* 메시지 본문이 포함되어 있습니다. 메시지 봉투는 [RFC 5321에](https://tools.ietf.org/html/rfc5321)설명되어 있으며 메시지 헤더는 [RFC 5322에 설명되어 있습니다.](https://tools.ietf.org/html/rfc5322) 받는 사람은 메시지 전송 프로세스에 의해 생성되어 실제로 메시지의 일부가 아니기 때문에 실제 메시지 봉투를 볼 수 없습니다.

- 주소(MAIL FROM 주소, P1 보낸 사람 또는 봉투 보낸 사람)는 메시지의 SMTP 전송에 사용되는 전자 메일 `5321.MailFrom` 주소입니다.  이 전자 메일 주소는 일반적으로 메시지 헤더의 **반환 경로** 헤더 필드에 기록됩니다(보낸 사람이 다른  반환 경로 전자 메일 주소를 지정하는 것은 가능).

- 보낸 사람(보낸 사람 주소 또는 P2 보낸 사람)은 보낸 사람 헤더 필드의 전자 메일 주소로, 전자 메일 클라이언트에 표시되는 보낸 사람 전자 메일 `5322.From` 주소입니다.  From 주소는 이 문서의 요구 사항에 초점을 맞추고 있습니다.

From 주소는 여러 RFC(예: RFC 5322 섹션 3.2.3, 3.4 및 3.4.1 및 [RFC 3696)에서](https://tools.ietf.org/html/rfc3696)자세히 정의됩니다. 주소에 많은 변형이 있으며 유효하거나 잘못된 것으로 간주되는 것이 있습니다. 간단하게 유지를 위해 다음과 같은 형식과 정의를 사용하는 것이 좋습니다.

`From: "Display Name" <EmailAddress>`

- **표시 이름:** 전자 메일 주소의 소유자를 설명하는 선택적 구입니다.

  - 표시 이름은 항상 표시된 두 배의 인용 부호(")로 묶는 것이 좋습니다. 표시 이름에 콤보가  포함되어 있는 경우 RFC 5322당 문자열을 큰 인용 부호로 묶아야 합니다.
  - From 주소에 표시 이름이 포함된 경우 EmailAddress 값은 표시된 < > 괄호로 묶아야 합니다.
  - 표시 이름과 전자 메일 주소 사이에 공백을 삽입하는 것이 좋습니다.

- **EmailAddress**: 전자 메일 주소에는 형식이 사용 `local-part@domain` 됩니다.

  - **local-part**: 주소와 연결된 사서함을 식별하는 문자열입니다. 이 값은 도메인 내에서 고유합니다. 사서함 소유자의 사용자 이름 또는 GUID가 사용되는 경우가 종종 있습니다.
  - **domain**: 전자 메일 주소의 로컬 부분으로 식별된 사서함을 호스트하는 전자 메일 서버의 FQDN(정식 도메인 이름)입니다.

  다음은 EmailAddress 값에 대한 몇 가지 추가 고려 사항입니다.

  - 전자 메일 주소가 하나만 있습니다.
  - 괄호는 공백으로 구분하지 않는 것이 좋습니다.
  - 전자 메일 주소 다음에 추가 텍스트를 포함하지 않습니다.

## <a name="examples-of-valid-and-invalid-from-addresses"></a>유효하고 유효하지 않은 From 주소의 예

다음의 전자 메일 주소가 유효합니다.

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` 괄호와 전자 메일 주소 사이에 공백이 있기 때문에 권장되지 않습니다.

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` 표시 이름은 이중 인용 부호로 묶이지 않는 것이 틀리기 때문에 권장되지 않습니다.

다음 전자 메일 주소가 잘못되었습니다.

- **보낸사서** 주소 없음: 일부 자동화된 메시지에는 보낸사서 주소가 없습니다. 과거에는 Microsoft 365 또는 Outlook.com에서 보낸사용자 주소 없이 메시지를 수신하면 서비스에서 다음과 같은 기본 보낸사용자: 주소를 추가하여 메시지를 배달할 수 있습니다.

  `From: <>`

  이제 보낸 주소가 비어 있는 메시지는 더 이상 수락되지 않습니다.

- `From: Microsoft 365 sender@contoso.com` 표시 이름이 있지만 전자 메일 주소는 괄호로 묶이지 않습니다.

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (전자 메일 주소 뒤의 텍스트)

- `From: Sender, Example <sender.example@contoso.com>` 표시 이름에는 콤보가 포함되어 있지만 인용 부호가 묶이지 않습니다.

- `From: "Microsoft 365 <sender@contoso.com>"` 전체 값이 2차원 인용 부호로 잘못 묶입니다.

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` 표시 이름이 있지만 전자 메일 주소는 괄호로 묶이지 않습니다.

- `From: Microsoft 365<sender@contoso.com>` 표시 이름과 왼쪽 괄호 사이의 공백이 없습니다.

- `From: "Microsoft 365"<sender@contoso.com>` 닫는 이중 인용 부호와 왼쪽 괄호 사이의 공백이 없는 경우

## <a name="suppress-auto-replies-to-your-custom-domain"></a>사용자 지정 도메인에 대한 자동 응답을 표시하지 않습니다.

이 값을 사용하여 자동 응답을 `From: <>` 표시하지 않습니다. 대신 사용자 지정 도메인에 대해 null MX 레코드를 설정해야 합니다. 응답 서버가 메시지를 보낼 수 있는 게시된 주소가 아니기 때문에 자동 답장과 모든 응답은 자연히 표시되지 않습니다.

- 전자 메일을 받을 수 없는 전자 메일 도메인을 선택하세요. 예를 들어 기본 도메인이 contoso.com 경우 기본 도메인을 noreply.contoso.com.

- 이 도메인에 대한 null MX 레코드는 단일 기간으로 구성됩니다.

예제:

```text
noreply.contoso.com IN MX .
```

MX 레코드를 설정하는 데 대한 자세한 내용은 [Dns](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)호스팅 공급자에서 DNS 레코드 만들기를 Microsoft 365.

null MX를 게시하는 자세한 내용은 [RFC 7505를 참조하세요.](https://tools.ietf.org/html/rfc7505)

## <a name="override-from-address-enforcement"></a>주소 적용에서 오버라이드

인바운드 전자 메일의 보낸 사람 주소 요구 사항을 무시하기 위해 Microsoft 365. [](create-safe-sender-lists-in-office-365.md)

전자 메일에서 보내는 아웃바운드 전자 메일의 보낸 사람 주소 요구 사항은 Microsoft 365. 또한 Outlook.com은 지원을 통해서도 어떠한 종류의 다시도 허용하지 않습니다.

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>사이버 범죄를 방지하고 보호하는 다른 Microsoft 365

피싱, 스팸, 데이터 위반 및 기타 위협으로부터 조직을 강화하는 방법에 대한 자세한 내용은 비즈니스 계획에 대한 보안 Microsoft 365 [방법을 참조하세요.](../../admin/security-and-compliance/secure-your-business-data.md)