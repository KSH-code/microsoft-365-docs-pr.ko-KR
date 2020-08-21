---
title: 차단할 보낸 사람 목록 만들기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: 관리자는 EOP(Exchange Online Protection)에서 인바운드 메시지를 차단하는 사용 가능한 옵션 및 기본 설정 옵션을 알고 있을 수 있습니다.
ms.openlocfilehash: 9b676f96ccdff8be1fa49841a9e0ce44bb59964c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827316"
---
# <a name="create-blocked-sender-lists-in-eop"></a>EOP에서 차단된 보낸 사람 목록 만들기

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 EOP는 관계없는 보낸 사람으로부터 전자 메일을 차단하는 여러 가지 방법을 제공합니다. 이러한 옵션에는 Outlook 수신 거부, 수신 거부 목록 또는 차단된 도메인 목록이 스팸 방지 정책의 목록, Exchange 메일 흐름 규칙(전송 규칙이라고도 함) 및 IP 차단 목록(연결 필터링)이 포함됩니다. 이러한 옵션은 집합적으로 차단된 보낸 사람 _목록으로 간주할 수 있습니다._

보낸 사람을 차단하는 가장 좋은 방법은 영향 범위에 따라 다릅니다. 단일 사용자의 경우 올바른 솔루션은 Outlook 수신 거부일 수 있습니다. 많은 사용자의 경우 다른 옵션 중 하나가 더 적절합니다. 다음 옵션은 영향 범위와 설명을 모두 통해 순위가 지정됩니다. 목록은 좁은 범위에서 광범위하지만, *전체 권장 사항에 대한 자세한* 사항을 읽습니다.

1. Outlook 수신 거부(각 사서함에 저장되어 있는 수신 거부 목록)

2. 수신 거부 목록 또는 차단된 도메인 목록(스팸 방지 정책)

3. 메일 흐름 규칙

4. IP 차단 목록(연결 필터링)

> [!NOTE]
> 조직 전체의 블록 설정을 사용하여 거짓 부정(스팸 부정)을 처리할 수 있고, 분석을 위해 Microsoft에 해당 메시지를 전송해야 합니다. 차단 목록을 사용하여 가양성을 관리하면 관리 오버헤드가 크게 증가합니다. 차단 목록을 사용하여 누락된 스팸을 조사할 경우 항목을 [Microsoft에](report-junk-email-messages-to-microsoft.md) 보고하는 것이 준비되어 있습니다.

이와 비해 수신 허용 - 보낸 사람 목록을 사용하여 특정 소스에서 보내는 전자 메일을 항상 허용하는 몇 _가지 옵션도 있습니다._ 자세한 내용은 [수신 허용 - 보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조하세요.

## <a name="email-message-basics"></a>전자 메일 메시지 기본 사항

표준 SMTP 전자 메일 메시지는 메시지 *봉투와 메시지 내용으로* 구성됩니다. 메시지 봉투에는 SMTP 서버 간에 메시지를 전송 및 배달하는 데 필요한 정보가 있습니다. 메시지 내용에는 메시지 헤더 필드(사서함 헤더) 및 *메시지 본문이*들어 있습니다. 메시지 봉투는 RFC 5321에 설명되어 있고 메시지 헤더는 RFC 5322에 설명되어 있습니다. 메시지 봉투는 메시지 전송 프로세스에 의해 생성되며 실제로는 메시지의 일부가 아닌 실제 메시지 봉투를 볼 수 없습니다.

- 이 `5321.MailFrom` **주소(메일 보낸 사람** 주소, P1 보낸 사람 또는 봉투 보낸 사람이라고도 함)는 메시지의 SMTP 전송에 사용되는 전자 메일 주소입니다. 이 전자 메일 주소는 일반적으로 메시지 헤더의 **Return-Path** 헤더 필드에 기록됩니다(보낸 사람이 서로 다른 반기 전자 메일 **주소를 지정할 수는** 있습니다). 메시지를 배달할 수 없는 경우 배달 못 함 보고서(NDR 또는 반송 메시지라고도 함)를 받는 사람입니다.

- 보낸 `5322.From` 사람 주소 또는 P2 **보낸** 사람이라고도 하는 보낸 사람 주소는 **보낸** 사람 헤더 필드의 전자 메일 주소이며, 전자 메일 클라이언트에 표시되는 보낸 사람의 전자 메일 주소입니다.

대칭적으로, `5321.MailFrom` 주소가 `5322.From` 동일합니다(개인 간 통신). 그러나 다른 사용자를 대신하여 전자 메일을 보낼 때는 해당 주소가 서로 다를 수 있습니다.

EOP에서 스팸 방지 정책의 수신 거부 목록과 차단된 도메인 목록이 모두 및 주소를 `5321.MailFrom` `5322.From` 검사합니다. Outlook 수신 거부는 주소만 `5322.From` 사용합니다.

## <a name="use-outlook-blocked-senders"></a>Outlook 수신 거부 사용

소수의 사용자만 사용자의 일본에서 사용자의 사서함을 수신하는 경우 사용자나 관리자는 사서함의 수신 거부 목록에 보낸 사람 전자 메일 주소를 추가할 수 있습니다. 자세한 내용은 [Exchange Online 사서함에 대해 정크 메일 설정 구성을 참조하세요.](configure-junk-email-settings-on-exo-mailboxes.md)

사용자의 수신 거부 목록으로 인해 메시지가 성공적으로 차단된 경우 **X-Forefront-Antispam-Report 헤더** 필드에는 이 값이 포함됩니다. `SFV:BLK`

> [!NOTE]
> 필요하지 않은 메시지가 평질이 있고 인식 가능한 원본의 뉴스레터인 경우 사용자가 메시지를 받지 못하도록 하는 추가 옵션이 전자 메일에서 구독 해제됩니다.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>차단할 보낸 사람 목록 또는 차단할 도메인 목록 사용

여러 사용자에게 영향을 받는 경우 스팸 방지 정책에서 그 다음 최상의 방법으로 보낸 사람 목록 또는 차단된 도메인 목록이 차단됩니다. 목록에 있는 보낸 사람이 보낸 메시지는 **스팸으로**표시되며, 메시지에서 **Spam** 사용자가 구성한 작업을 수행합니다. 자세한 내용은 [스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

이러한 목록에 대한 최대 제한은 약 1000개 항목입니다.

## <a name="use-mail-flow-rules"></a>메일 흐름 규칙 사용

특정 사용자에게 보내지거나 전체 조직에서 전송되는 메시지를 차단해야 하는 경우 메일 흐름 규칙을 사용할 수 있습니다. 메일 흐름 규칙은 원치 않는 메시지에서 키워드 또는 기타 속성을 찾을 수 있기 때문에 보낸 사람 목록 또는 수신 거부 도메인 목록보다 훨씬 더 유연합니다.

메시지를 식별하는 데 사용하는 조건이나 예외에 관계없이 메시지의 SCL(스팸 지수)을 9로 설정하도록 작업을 구성하여 메시지의 **신뢰도를 높게 표시합니다.** 자세한 내용은 메일 흐름 [규칙을 사용하여 SCL 설정을 메시지에 시행합니다.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

> [!IMPORTANT]
> 과도하게 액세스하는 규칙을 *만들기가* 매우 어우중요하므로 매우 구체적인 조건을 사용하여 차단할 메시지만 식별하는 것이 중요합니다. 또한 규칙에 대한 감사를 사용하도록 설정하고 규칙 결과를 테스트하여 모든 작업이 예상대로 작동하는지 확인해야 합니다.

## <a name="use-the-ip-block-list"></a>IP 차단 목록 사용

다른 옵션 중 하나를 사용하여 보낸 사람을 차단할 수 없는 *경우에는 연결* 필터 정책에서 IP 차단 목록만 사용해야 합니다. 자세한 내용은 [Configure the connection filter policy](configure-the-connection-filter-policy.md)를 참조하십시오. 차단된 IP 의 개수를 최소한으로 유지해야 하므로 전체 IP 주소 범위를 차단하지 않는 *것이* 좋습니다.

사용자 서비스에 *속한* IP 주소 범위(예: outlook.com) 또는 공유 인프라를 추가하는 일이 원치 않는 한 주의해야 하며, 일반 유지 관리의 일부로 차단된 IP 주소 목록을 검토해야 합니다.
