---
title: 안전한 보낸 사람 목록 만들기
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
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)에서 인바운드 메시지를 허용하는 사용 가능한 옵션 및 기본 설정 옵션을 알게 됩니다.
ms.openlocfilehash: f182027b153ee73e33131b39066e512c9303fcbd
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827114"
---
# <a name="create-safe-sender-lists-in-eop"></a>EOP에서 안전한 보낸 사람 목록 만들기

Exchange Online 사서함이 있는 Microsoft 365 고객 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 고객인 경우, EOP를 통해 사용자가 신뢰할 수 있는 보낸 사람의 전자 메일을 받게 됩니다. 이러한 옵션에는 Exchange 메일 흐름 규칙(전송 규칙이라고도 함), Outlook 수신 허용 - 보낸 사람, IP 허용 목록(연결 필터링) 및 스팸 방지 정책의 허용된 보낸 사람 목록 또는 허용된 도메인 목록이 포함됩니다. 이러한 옵션을 안전한 보낸 사람 목록으로 _합리적으로 생각할 수 있습니다._

사용 가능한 수신 허용 - 보낸 사람 목록은 대부분 권장부터 가장 적은 권장 순서순서로 설명되어 있습니다.

1. 메일 흐름 규칙
2. Outlook 수신 허용 - 보낸 사람
3. IP 허용 목록(연결 필터링)
4. 허용된 보낸 사람 목록 또는 허용된 도메인 목록(스팸 방지 정책)

메일 흐름 규칙을 통해 적합한 메시지만 허용하도록 유연하게 지정할 수 있습니다. 스팸 방지 정책에서 허용되는 보낸 사람 및 허용 도메인 목록은 보낸 사람의 전자 메일 도메인이 쉽게 스푸핑되므로 이를 IP 허용 목록으로 안전하지 않습니다. 그러나 IP 허용 목록에서도 해당 IP 주소에서 _any_ 전송된 도메인의 전자 메일은 스팸 필터링을 무시하기 때문에 위험이 발생합니다.

> [!IMPORTANT]
>
> - 수신 허용 - 보낸 사람 목록을 사용하여 *스팸 필터링에* 대한 예외를 면밀히 모니터링해야 합니다.
>
> - 수신 허용 - 보낸 사람 목록을 사용하여 가양성(스팸으로 표시가 좋은 전자 메일)과 관련해 도와주기 는 하지만 수신 허용되는 수신 허용 - 보낸 사람 목록을 임시 솔루션으로 사용하는 것이 좋습니다. 이 솔루션은 가능한 경우 피해야 하는 임시 솔루션입니다. 스팸 필터링의 예외는 조직을 스푸핑하거나 기타 공격에 노출할 수 있기 때문에 수신 허용 - 보낸 사람 목록을 사용하여 가양성을 관리하는 것이 좋습니다. 수신 허용 - 보낸 사람 목록을 사용하여 가양성을 관리하는 경우 취력을 받고 항목을 Microsoft에 보고하는 작업을 [준비해야](report-junk-email-messages-to-microsoft.md) 합니다.
>
> - 도메인에서 인증되지 않은 이메일(스푸핑 방지 보호 바이패스)을 보내도록 허용하지만 스팸 방지 및 맬웨어 방지 검사를 무시하지 않도록 하려면 [AllowedToSpoof 수신 허용 -](walkthrough-spoof-intelligence-insight.md) 보낸 사람 목록에 추가하면 됩니다.
>
> - EOP 및 Outlook에서는 다양한 메시지 속성을 검사하여 메시지 보낸 사람을 확인합니다. 자세한 내용은 이 항목의 [뒷부분에 있는 대량 전자 메일의 고려 사항을](#considerations-for-bulk-email) 참조하세요.

이와 비해 차단된 보낸 사람 목록을 사용하여 특정 원본의 전자 메일을 차단할 수 있는 _몇 가지 옵션도 있습니다._ 자세한 내용은 [EOP에서 차단할 보낸 사람 목록 만들기](create-block-sender-lists-in-office-365.md)를 참조하세요.

## <a name="recommended-use-mail-flow-rules"></a>(권장) 메일 흐름 규칙 사용

Exchange Online 및 독립 실행형 EOP의 메일 흐름 규칙은 조건 및 예외를 사용하여 메시지와 해당 메시지에 대해 수행할 작업을 지정합니다. 자세한 내용은 [Exchange Online에서 메일 흐름 규칙(전송 규칙)을 참조하세요.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

다음 예에서는 스팸 필터링을 건너뛰기 위해 전자 contoso.com 있다고 가정합니다. 이렇게 하려면 다음 설정을 구성합니다.

1. **조건:** **보낸 사람** \> **도메인이 구성 contoso.com.** \>

2. 다음 설정 중 하나를 구성합니다.

   - **메일 흐름 규칙 조건:** **메시지 헤더에** \> **다음 단어 헤더 이름:** \> **헤더 값:** `Authentication-Results` \> **또는 .가 포함됩니다.** `dmarc=pass` `dmarc=bestguesspass`

     이 조건은 보내는 전자 메일 도메인의 보낸 사람 인증 상태를 확인하여 보내는 도메인이 스푸핑되지 않았는지 확인합니다. 전자 메일 인증에 대한 자세한 내용은 [SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)및 [DMARC를 참조하세요.](use-dmarc-to-validate-email.md)

   - **IP 허용 목록:** 연결 필터 정책에서 원본 IP 주소 또는 주소 범위를 지정합니다.
  
     보내는 도메인에 인증이 없는 경우 이 설정을 사용합니다. IP 허용 목록의 원본 IP 주소에 포함될 경우 최대한 제한적입니다. IP 주소 범위 /24 이하를 사용하는 것이 좋습니다(더 적습니다). 소비자 서비스에 속한 IP 주소 범위(예: outlook.com, 또는 공유 인프라 사용 안 됨)를 사용하지 않습니다.

   > [!IMPORTANT]
   >
   > - 메일 흐름 규칙만 을 스팸 필터링을 *건너뛰는* 조건으로 구성하지 않도록 합니다. 이렇게 하면 *공격자가 송신* 도메인을 스푸핑하거나 전체 전자 메일 주소를 가장할 가능성이 크게 높아지고, 모든 스팸 필터링을 건너뛰고, 보낸 사람 인증 검사는 건너뛰므로 받는 사람의 받은 편지함에 메시지가 도배됩니다.
   >
   > - 메일 흐름 규칙의 조건으로 소유하고 소유한 도메인 또는 인기 도메인(예: microsoft.com)을 사용하지 않도록 합니다. 이렇게 하면 공격자가 전자 메일을 보낼 수 있어 필터링할 수 있기 때문에 위험도가 높은 것으로 간주됩니다.
   >
   > - NAT(Network Address Translation) 게이트웨이 뒤에 있는 IP 주소를 허용하는 경우 IP 허용 목록의 범위를 알기 위해 NAT 풀에 포함된 서버를 알아야 합니다. IP 주소 및 NAT 참가자가 변경할 수 있습니다. 표준 유지 관리 절차의 일부로 IP 허용 목록 항목을 정기적으로 확인해야 합니다.

3. **선택적 조건:**

   - **보낸 사람** \> **내부/외부입니다.** \> **조직 외부:** 이 상태는 암시적이지만 올바르게 구성되지 않을 수 있는 온-프레미스 전자 메일 서버에 대해 해당 규칙을 사용해도 됩니다.

   - **제목 또는 본문** \> **제목 또는 본문에 다음 단어 포함** \> : 제목 줄이나 메시지 본문에서 키워드나 구별로 메시지를 추가로 제한할 수 있는 경우 \<keywords\> 해당 단어를 조건으로 사용할 수 있습니다.

4. **동작:** 규칙에서 다음과 같은 작업을 모두 구성합니다.

   a. **메시지 속성 수정** \> **SCL(스팸 지수) 설정** \> **스팸 필터링을 무시합니다.**

   b. **메시지 머리글** \> **입력하는 단어 포함** \> **헤더 이름:** \<CustomHeaderName\> **헤더 값**: \<CustomHeaderValue\> .

      예를 들면 `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`와 같습니다. 규칙에 도메인이 두 개 이상 있는 경우 헤더 텍스트를 적절한 지(적절하게 사용자 지정)할 수 있습니다.

      메일 흐름 규칙으로 인해 메시지가 스팸 필터링을 건너뛰면 `SFV:SKN` 값은 **X-Forefront-Antispam-Report 헤더에 스탬프 처리됩니다.** 메시지가 IP 허용 목록에 있는 원본에서 온 경우 이 값도 `IPV:CAL` 추가됩니다. 이 값은 문제 해결에 도움이 될 수 있습니다.

![스팸 필터링을 무시하도록 EAC의 메일 흐름 규칙 설정](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>Outlook 수신 허용 - 보낸 사람 사용

사용자나 관리자는 조직 설정 대신 사서함의 수신 허용 - 보낸 사람 목록에 보낸 사람 전자 메일 주소를 추가할 수 있습니다. 자세한 내용은 [Office 365에서 Exchange Online 사서함에 대한 정크 메일 설정 구성을 참조하세요.](configure-junk-email-settings-on-exo-mailboxes.md) 보낸 사람이 필터링 스택의 일부를 무시하기 때문에 대부분의 경우에는 이 방법이 바되지 않습니다. 보낸 사람을 신뢰하지만 보낸 사람이 여전히 위반될 수 있고 악의적인 콘텐츠를 보낼 수 있습니다. 필터가 잘못된 경우 필터에서 모든 메시지를 확인하는 데 필요한 작업을 수행한 후 [잘못된 내용/수신성을 Microsoft에](report-junk-email-messages-to-microsoft.md) 보고하는 것이 가장 좋습니다. 필터링 스택을 무시하면 [ZAP가 간주합니다.](zero-hour-auto-purge.md)

사용자의 수신 허용 - 보낸 사람 목록으로 인해 메시지가 스팸 필터링을 건너뛰면 **X-Forefront-Antispam-Report** 헤더 필드에 해당 `SFV:SFE` 값을 포함하여 스팸, 스푸핑 및 피싱 필터링이 무시되었습니다.

## <a name="use-the-ip-allow-list"></a>IP 허용 목록 사용

앞에서 설명한 것과 같이 메일 흐름 규칙을 사용할 수 있는 경우 다음 가장 좋은 방법은 연결 필터 정책에서 원본 전자 메일 서버를 IP 허용 목록에 추가하는 것입니다. 자세한 내용은 [EOP에서 연결 필터링 구성을 참조하십시오.](configure-the-connection-filter-policy.md)

**참고:**

- 허용된 IP 주소 의 개수를 최소로 유지해야 하므로 가능한 경우 전체 IP 주소 범위를 사용하지 않도록 합니다.

- 소비자 서비스에 속한 IP 주소 범위(예: outlook.com, 또는 공유 인프라 사용 안 됨)를 사용하지 않습니다.

- IP 허용 목록의 항목을 정기적으로 검토하고 더 이상 필요 없는 항목을 제거합니다.

> [!CAUTION]
> 메일 흐름 규칙처럼 추가 로고를 확인하지 않으면 IP 허용 목록의 소스에서 보낸 전자 메일은 스팸 필터링 및 보낸 사람 인증(SPF, DKIM, DMARC) 확인을 건너뜁니다. 이렇게 하면 공격자가 받은 편지함에게 전자 메일을 전송하여 그렇지 않으면 필터링할 위험이 높아지게 됩니다.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>허용된 보낸 사람 목록 또는 허용된 도메인 목록 사용

스팸 방지 정책에서 허용된 보낸 사람 목록 또는 허용도메인 목록을 사용하는 것이 가장 바선될 수 있는 옵션입니다. 보낸 사람이 모든 스팸, *스푸핑* 및 피싱 보호와 보낸 사람 인증(SPF, DKIM, DMARC)을 바이패스하므로 가능한 경우에는 이 옵션을 사용하지 않아야 합니다. 이 방법은 임시 테스트에만 사용하는 것이 가장 좋습니다. 자세한 단계는 EOP 항목의 스팸 [방지 정책 구성에서 찾을 수](configure-your-spam-filter-policies.md) 있습니다.

이러한 목록에 대한 최대 제한은 약 1000개 항목입니다. 하지만 포털에 30개 항목만 입력할 수 있습니다. 30개 항목을 더 추가하려면 PowerShell을 사용해야 합니다.

> [!CAUTION]
>
> - 이 방법을 사용하면 공격자가 받은 편지함에게 전자 메일을 제대로 배달할 때 위험이 높아지고, 그렇지 않으면 필터링될 수 있습니다.
>
> - 허용 도메인 목록에 사용자가 소유하고 있는 도메인(허용 도메인이라고도 함) 또는 인기 도메인(예microsoft.com을 사용하지 않도록 합니다.

## <a name="considerations-for-bulk-email"></a>대량 전자 메일에 대한 고려 사항

표준 SMTP 전자 메일 메시지는 메시지 *봉투와 메시지 내용으로* 구성됩니다. 메시지 봉투에는 SMTP 서버 간에 메시지를 전송 및 배달하는 데 필요한 정보가 있습니다. 메시지 내용에는 메시지 헤더 필드(사서함 헤더) 및 *메시지 본문이*들어 있습니다. 메시지 봉투는 RFC 5321에 설명되어 있고 메시지 헤더는 RFC 5322에 설명되어 있습니다. 메시지 봉투는 메시지 전송 프로세스에 의해 생성되며 실제로는 메시지의 일부가 아닌 실제 메시지 봉투를 볼 수 없습니다.

- 이 `5321.MailFrom` **주소(메일 보낸 사람** 주소, P1 보낸 사람 또는 봉투 보낸 사람이라고도 함)는 메시지의 SMTP 전송에 사용되는 전자 메일 주소입니다. 이 전자 메일 주소는 일반적으로 메시지 헤더의 **Return-Path** 헤더 필드에 기록됩니다(보낸 사람이 서로 다른 반기 전자 메일 **주소를 지정할 수는** 있습니다). 메시지를 배달할 수 없는 경우 배달 못 함 보고서(NDR 또는 반송 메시지라고도 함)를 받는 사람입니다.

- 보낸 `5322.From` 사람 주소 또는 P2 **보낸** 사람이라고도 하는 보낸 사람 주소는 **보낸** 사람 헤더 필드의 전자 메일 주소이며, 전자 메일 클라이언트에 표시되는 보낸 사람의 전자 메일 주소입니다.

대칭적으로, `5321.MailFrom` 주소가 `5322.From` 동일합니다(개인 간 통신). 그러나 다른 사용자를 대신하여 전자 메일을 보낼 때는 해당 주소가 서로 다를 수 있습니다. 이 문제는 대량 전자 메일 메시지에 대해 가장 자주 발생합니다.

예를 들어 Blue Yonder Airlines에서 이메일 광고를 보내는 Margie's Travel이 수량으로 표시된다고 가정합니다. 받은 편지함에 받는 메시지에는 다음 속성이 포함됩니다.

- 주소는 `5321.MailFrom` blueyonder.airlines@margiestravel.com.

- 이 `5322.From` 주소는 blueyonder@news.blueyonderairlines.com Outlook에 표시된 것과 같은 정보가 필요합니다.

EOP의 스팸 방지 정책에 포함된 수신 허용 - 보낸 사람 목록 및 안전한 도메인 목록은 주소만 `5322.From` 검사합니다. 이 옵션은 주소를 사용하는 Outlook 수신 허용 - 보낸 사람 목록과 유사합니다. `5322.From`

이 메시지를 필터링하지 못하도록 하려면 다음 단계를 수행합니다.

- 메시지 `5322.From` blueyonder@news.blueyonderairlines.com(주소)를 Outlook 수신 허용 - 보낸 사람으로 추가합니다.

- [메일 흐름 규칙은](#recommended-use-mail-flow-rules) 조건과 함께 사용합니다blueyonder@news.blueyonderairlines.com 주소, 메시지 blueyonder@news.blueyonderairlines.com(와일드리아트) 또는 둘 `5322.From` blueyonder.airlines@margiestravel.com `5321.MailFrom` 다인 메시지를 찾습니다.

자세한 내용은 [EOP에서 수신 허용 - 보낸 사람 목록 만들기를 참조하세요.](create-safe-sender-lists-in-office-365.md)
