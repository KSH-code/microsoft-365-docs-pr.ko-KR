---
title: EOP에서 피싱을 방지 하기 위해 보낸 사람 주소 유효성을 검사 하는 방법
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
description: 관리자는 피싱 방지를 위해 EOP (Exchange Online Protection) 및 Outlook.com에서 수락 하거나 거부 하는 전자 메일 주소 유형에 대해 알아볼 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f16bb9b0af1ca5481437ef253c6d36dd519ff9e2
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209454"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>EOP에서 피싱을 방지 하기 위해 보낸 사람 주소 유효성을 검사 하는 방법

피싱 공격은 모든 전자 메일 조직에 대해 일정 한 위협이 됩니다. 공격자는 [가짜 (위조) 보낸 사람 전자 메일 주소](anti-spoofing-protection.md)를 사용 하는 것 외에도 발신자 주소에 인터넷 표준을 위반 하는 값을 사용 하는 경우가 많습니다. 이러한 유형의 피싱을 방지 하기 위해 EOP (Exchange Online Protection) 및 Outlook.com는이 항목에서 설명 하는 대로 RFC 규격인 From 주소를 포함 하도록 인바운드 메시지를 요청 합니다. 이 적용은 11 월 2017에서 사용 하도록 설정 되었습니다.

**참고**:

- 이 항목에서 설명 하는 주소에서 형식이 잘못 된 조직 으로부터 전자 메일을 정기적으로 수신 하는 경우 이러한 조직이 최신 보안 표준을 준수 하도록 전자 메일 서버를 업데이트 하도록 권장 합니다.

- "대신 보내기" 및 "메일 그룹에서 사용 하는" 관련 보낸 사람 "필드에는 이러한 요구 사항이 적용 되지 않습니다. 자세한 내용은 다음 블로그 게시물: [전자 메일의 ' 보낸 사람 '을 참조](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)하는 경우 무슨 의미 입니까?를 참조 하세요.

## <a name="an-overview-of-email-message-standards"></a>전자 메일 메시지 표준 개요

표준 SMTP 전자 메일 메시지는 *메시지 봉투* 와 메시지 콘텐츠로 구성 됩니다. 메시지 봉투에는 SMTP 서버 간에 메시지를 전송 및 배달 하는 데 필요한 정보가 포함 되어 있습니다. 메시지 콘텐츠에는 메시지 헤더 필드 (통칭 *메시지 헤더*) 및 메시지 본문이 포함 됩니다. 메시지 봉투는 [rfc 5321](https://tools.ietf.org/html/rfc5321)에 설명 되어 있고 메시지 헤더는 [rfc 5322](https://tools.ietf.org/html/rfc5322)에 설명 되어 있습니다. 실제 메시지 봉투는 메시지 전송 프로세스에 의해 생성 되며 실제로는 메시지의 일부가 아니기 때문에 받는 사람에 게는 표시 되지 않습니다.

- `5321.MailFrom`주소 ( **메일** 보낸 사람 주소, P1 sender 또는 envelope sender)는 메시지의 SMTP 전송에 사용 되는 전자 메일 주소입니다. 이 전자 메일 주소는 일반적으로 메시지 헤더의 **반환 경로** 헤더 필드에 기록 됩니다 (보낸 사람이 다른 **반환 경로** 전자 메일 주소를 지정할 수 있지만).

- 보낸 `5322.From` 사람 주소 또는 P2 보낸 사람이 라고도 하는 전자 메일 주소 **는 보낸 사람의** 전자 메일 주소 이며 전자 메일 클라이언트에 표시 됩니다. 보낸 사람 주소는이 항목의 요구 사항에 중점을 둔 것입니다.

보낸 사람 주소는 몇 가지 Rfc (예: RFC 5322, 3.4, 3.4.1 및 [RFC 3696](https://tools.ietf.org/html/rfc3696))에서 자세히 정의 됩니다. 주소 지정에는 다양 한 변형이 있으며 유효한 것으로 간주 되는 것으로 생각 됩니다. 이를 단순하게 유지 하려면 다음 형식과 정의를 권장 합니다.

`From: "Display Name" <EmailAddress>`

- **표시 이름**: 전자 메일 주소의 소유자를 설명 하는 선택적 구문입니다.

  - 표시 되는 대로 항상 display name을 큰따옴표 (")로 묶는 것이 좋습니다. 표시 이름에 쉼표가 포함 되어 있으면 RFC 5322 당 큰따옴표를 큰따옴표로 묶어야 _합니다_ .
  - 보낸 사람 주소에 표시 이름이 포함 되어 있는 경우 EmailAddress 값은 표시 된 대로 꺾쇠 괄호 (< >)로 묶어야 합니다.
  - 표시 이름과 전자 메일 주소 사이에 공백을 삽입 하는 것이 좋습니다.

- **EmailAddress**: 전자 메일 주소는 다음 형식을 사용 합니다 `local-part@domain` .

  - **local part**: 주소와 연결 된 사서함을 식별 하는 문자열입니다. 이 값은 도메인 내에서 고유 합니다. 사서함 소유자의 사용자 이름 또는 GUID가 사용 되는 경우가 많습니다.
  - **도메인**: 전자 메일 주소의 로컬 부분으로 식별 되는 사서함을 호스트 하는 전자 메일 서버의 FQDN (정규화 된 도메인 이름)입니다.

  다음은 EmailAddress 값에 대 한 몇 가지 추가 고려 사항입니다.

  - 전자 메일 주소 하나만
  - 꺾쇠 괄호는 공백으로 구분 하지 않는 것이 좋습니다.
  - 전자 메일 주소 뒤에 추가 텍스트를 포함 하지 않습니다.

## <a name="examples-of-valid-and-invalid-from-addresses"></a>유효 및 잘못 된 주소의 예

다음은 유효한 전자 메일 주소입니다.

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >`꺾쇠 괄호와 전자 메일 주소 사이에는 공백이 있으므로 권장 되지 않습니다.

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>`표시 이름이 큰따옴표로 묶여 있지 않으므로 권장 하지 않습니다.

다음의 보낸 사람 전자 메일 주소가 잘못 되었습니다.

- **보낸 사람 주소**: 일부 자동 메시지에는 보낸 사람 주소가 포함 되지 않습니다. 더 이상 Microsoft 365 또는 Outlook.com에서 보낸 사람 주소가 없는 메시지를 받은 경우 서비스는 다음의 기본값을에서 메시지를 제공 하는 주소를 지정 합니다 .로 추가 했습니다.

  `From: <>`

  이제는 보낸 사람 주소가 비어 있는 메시지가 더 이상 수락 되지 않습니다.

- `From: Microsoft 365 sender@contoso.com`표시 이름은 제공 되지만 전자 메일 주소는 꺾쇠 괄호로 묶여 있지 않습니다.

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)`(전자 메일 주소 다음에 오는 텍스트)

- `From: Sender, Example <sender.example@contoso.com>`(표시 이름에는 쉼표가 포함 되어 있지만 큰따옴표로 묶지 않습니다.)

- `From: "Microsoft 365 <sender@contoso.com>"`전체 값이 큰따옴표로 잘못 묶여 있습니다.

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com`표시 이름은 제공 되지만 전자 메일 주소는 꺾쇠 괄호로 묶여 있지 않습니다.

- `From: Microsoft 365<sender@contoso.com>`(표시 이름 및 왼쪽 꺽쇠 괄호 사이에 공백 없음)

- `From: "Microsoft 365"<sender@contoso.com>`닫는 큰따옴표와 왼쪽 꺽쇠 괄호 사이에는 공백이 없어야 합니다.

## <a name="suppress-auto-replies-to-your-custom-domain"></a>사용자 지정 도메인에 대 한 자동 회신을 표시 하지 않습니다.

자동 회신을 표시 하지 않으려면이 값을 사용할 수 없습니다 `From: <>` . 대신 사용자 지정 도메인에 대해 null MX 레코드를 설정 해야 합니다. 응답 서버가 메시지를 보낼 수 있는 게시 된 주소가 없기 때문에 자동 회신 (및 모든 응답)은 자연스럽 게 표시 되지 않습니다.

- 전자 메일을 받을 수 없는 전자 메일 도메인을 선택 합니다. 예를 들어 주 도메인이 contoso.com 인 경우 noreply.contoso.com을 선택할 수 있습니다.

- 이 도메인에 대 한 null MX 레코드는 단일 기간으로 구성 됩니다.

예시:

```text
noreply.contoso.com IN MX .
```

MX 레코드를 설정 하는 방법에 대 한 자세한 내용은 [dns 호스팅 공급자에서 Microsoft 365에 대 한 dns 레코드 만들기](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)를 참조 하십시오.

Null MX를 게시 하는 방법에 대 한 자세한 내용은 [RFC 7505](https://tools.ietf.org/html/rfc7505)을 참조 하십시오.

## <a name="override-from-address-enforcement"></a>주소 적용에서 무시

인바운드 전자 메일에 대해 From 주소 요구 사항을 무시 하려면 [Microsoft 365에서 수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)에 설명 된 대로 IP Allow List (연결 필터링) 또는 메일 흐름 규칙 (전송 규칙이 라고도 함)을 사용할 수 있습니다.

Microsoft 365에서 보내는 아웃 바운드 전자 메일에 대 한 보낸 사람 주소 요구 사항을 재정의할 수는 없습니다. 또한 Outlook.com에서는 지원을 통해 모든 종류의 재정의를 허용 하지 않습니다.

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Microsoft 365에서 cybercrimes을 방지 하 고 보호 하는 기타 방법

피싱, 스팸, 데이터 위반 및 기타 위협 으로부터 조직을 강화 하는 방법에 대 한 자세한 내용은 [Top 10 방법으로 Microsoft 365 for business 요금제](../../admin/security-and-compliance/secure-your-business-data.md)를 참조 하세요.
