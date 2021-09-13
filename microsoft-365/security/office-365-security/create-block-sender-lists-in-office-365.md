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
localization_priority: Normal
search.appverid:
- MET150s
description: 관리자는 EOP(인바운드 메시지)에서 인바운드 메시지를 차단하는 사용 가능한 옵션과 기본 Exchange Online Protection 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c844378a19ba7995cbd616f615e8a84994f9bf26
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59211775"
---
# <a name="create-blocked-sender-lists-in-eop"></a>EOP에서 차단된 보낸 사람 목록 만들기

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 사서함이 없는 Exchange Online 또는 EOP(독립 실행형 Exchange Online Protection) 조직에서 EOP는 Exchange Online 보낸 사람이 전자 메일을 차단하는 여러 가지 방법을 제공합니다. 이러한 옵션에는 Outlook 차단된 보낸 사람, 차단된 보낸 사람 목록 또는 스팸 방지 정책의 차단된 도메인 목록, Exchange 메일 흐름 규칙(전송 규칙) 및 IP 차단 목록(연결 필터링)이 포함됩니다. 전체적으로 이러한 옵션을 수신 차단된 보낸 사람 _목록으로 생각할 수 있습니다._

보낸 사람 차단의 가장 좋은 방법은 영향 범위에 따라 다릅니다. 단일 사용자의 경우 올바른 솔루션이 수신 Outlook 수 있습니다. 많은 사용자의 경우 다른 옵션 중 하나에 더 적합한 옵션 중 하나를 사용할 수 있습니다. 다음 옵션은 영향 범위와 범위 모두에 따라 순위가 지정됩니다. 목록은 좁아지지만 전체 권장 사항에 대한 *자세한* 내용을 읽습니다.

1. Outlook 수신 차단된 보낸 사람(각 사서함에 저장된 수신 차단된 보낸 사람 목록)

2. 차단된 보낸 사람 목록 또는 차단된 도메인 목록(스팸 방지 정책)

3. 메일 흐름 규칙

4. IP 차단 목록(연결 필터링)

> [!NOTE]
> 조직 전체 차단 설정을 사용하여 거짓 부정(스팸 누락)을 해결할 수 있는 반면, 분석을 위해 해당 메시지를 Microsoft에 제출해야 합니다. 차단 목록을 사용하여 거짓 부정을 관리하면 관리 오버헤드가 크게 증가합니다. 차단 목록을 사용하여 누락된 스팸을 반사하는 경우 [Report messages and files to Microsoft(Microsoft에](report-junk-email-messages-to-microsoft.md) 메시지 및 파일 보고) 항목을 준비된 상태로 유지해야 합니다.

반면에 수신 허용 - 보낸 사람 목록을 사용하여 특정 원본의 전자 메일을 항상 허용하는 몇 가지 _옵션도 있습니다._ 자세한 내용은 [수신 허용 - 보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조하세요.

## <a name="email-message-basics"></a>전자 메일 메시지 기본

표준 SMTP 전자 메일 메시지는 메시지 봉투와 메시지 콘텐츠로 구성됩니다.  메시지 봉투에는 SMTP 서버 간에 메시지를 전송하고 배달하는 데 필요한 정보가 포함되어 있습니다. 메시지 콘텐츠에는 메시지 헤더 필드(총체적으로 메시지 *헤더)와* 메시지 본문이 포함되어 있습니다. 메시지 봉투는 RFC 5321에 설명되어 있으며 메시지 헤더는 RFC 5322에 설명되어 있습니다. 받는 사람은 메시지 전송 프로세스에 의해 생성되어 실제로 메시지의 일부가 아니기 때문에 실제 메시지 봉투를 볼 수 없습니다.

- 주소(MAIL FROM 주소, P1 보낸 사람 또는 봉투 보낸 사람)는 메시지의 SMTP 전송에 사용되는 전자 메일 `5321.MailFrom` 주소입니다.  이 전자 메일 주소는 일반적으로 메시지 헤더의 **반환 경로** 헤더 필드에 기록됩니다(보낸 사람이 다른  반환 경로 전자 메일 주소를 지정하는 것은 가능). 메시지를 배달할 수 없는 경우 배달 못 한 보고서(NDR 또는 반송 메시지라고도 알려)의 받는 사람입니다.

- 보낸 사람(보낸 사람 주소 또는 P2 보낸 사람)은 보낸 사람 헤더 필드의 전자 메일 주소로, 전자 메일 클라이언트에 표시되는 보낸 사람 전자 메일 `5322.From` 주소입니다.  

자주 및 `5321.MailFrom` `5322.From` 주소는 동일합니다(개인 간 통신). 그러나 다른 사람을 대신하여 전자 메일을 보낼 경우 주소가 다를 수 있습니다.

EOP의 스팸 방지 정책에서 차단된 보낸 사람 목록 및 차단된 도메인 목록은 및 주소를 `5321.MailFrom` 모두 `5322.From` 검사합니다. Outlook 수신이 차단된 보낸 사람만 주소를 `5322.From` 사용 합니다.

## <a name="use-outlook-blocked-senders"></a>수신 Outlook 보낸 사람 사용

소수의 사용자만 원치 않는 전자 메일을 받은 경우 사용자 또는 관리자는 사서함의 수신 차단된 보낸 사람 목록에 보낸 사람 전자 메일 주소를 추가할 수 있습니다. 자세한 내용은 [사서함의 정크](configure-junk-email-settings-on-exo-mailboxes.md)메일 설정 Exchange Online 참조하세요.

사용자의 수신이 차단된 보낸 사람 목록으로 인해 메시지가 차단된 경우 **X-Forefront-Antispam-Report** 헤더 필드에는 값이 를 포함하게 `SFV:BLK` 됩니다.

> [!NOTE]
> 원치 않는 메시지가 수신 가능하고 인식할 수 있는 원본의 뉴스레터인 경우 사용자가 메시지를 받지 못하도록 하는 또 다른 옵션으로 전자 메일 구독을 중지할 수 있습니다.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>차단된 보낸 사람 목록 또는 차단된 도메인 목록 사용

여러 사용자가 영향을 받는 경우 범위가 더 넓어지기 때문에 다음으로는 스팸 방지 정책의 차단된 보낸 사람 목록 또는 차단된 도메인 목록이 있습니다. 목록에 있는 보낸 사람이 보낸 메시지는 높은 지수 스팸으로 표시되어 있으며 높은  지수 스팸 필터 판정에 대해 구성한 작업이 메시지에 대해 수행됩니다. 자세한 내용은 [안티스팸 정책 구성](configure-your-spam-filter-policies.md)을(를) 참조합니다.

이러한 목록의 최대 제한은 약 1,000개 항목입니다.

## <a name="use-mail-flow-rules"></a>메일 흐름 규칙 사용

특정 사용자 또는 전체 조직에 전송된 메시지를 차단해야 하는 경우 메일 흐름 규칙을 사용할 수 있습니다. 메일 흐름 규칙은 원치 않는 메시지에서 키워드 또는 기타 속성을 검색할 수 있기 때문에 보낸 사람 목록 또는 차단된 보낸 사람 도메인 목록을 차단하는 것보다 더 유연합니다.

메시지를 식별하는 데 사용하는 조건 또는 예외에 관계없이 메시지의 SCL(스팸 지수)을 9로 설정하여 메시지를 높은 지수 스팸으로 표시하도록 작업을 **구성합니다.** 자세한 내용은 메일 흐름 규칙을 사용하여 [메시지에서 SCL 설정을 참조하세요.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)

> [!IMPORTANT]
> 너무 적극적인 규칙을 쉽게  만들 수 있으므로 매우 구체적인 조건을 사용하여 차단하려는 메시지만 식별하는 것이 중요합니다. 또한 규칙에 대한 감사를 사용하도록 설정하고 규칙 결과를 테스트하여 모든 것이 예상대로 작동하는지 확인해야 합니다.

## <a name="use-the-ip-block-list"></a>IP 차단 목록 사용

다른 옵션 중 하나를 사용하여 보낸 사람 차단을 사용할  수 없는 경우 연결 필터 정책에서 IP 차단 목록을 사용하는 것이 좋습니다. 자세한 내용은 [Configure the connection filter policy](configure-the-connection-filter-policy.md)를 참조하십시오. 차단된 IP 수를 최소한으로 유지하는 것이 중요하기 때문에 전체 IP 주소 범위를 차단하지 않는 것이 *좋습니다.*

특히 *소비자* 서비스(예: outlook.com) 또는 공유 인프라에 속하는 IP 주소 범위를 추가하지 말고 정기적인 유지 관리의 일부로 차단된 IP 주소 목록을 검토해야 합니다.
