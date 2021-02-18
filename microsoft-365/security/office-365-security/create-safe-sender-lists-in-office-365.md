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
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)에서 인바운드 메시지를 허용하는 사용 가능한 옵션 및 기본 옵션에 대해 학습할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ddcd6240cfc80350920999f9fc1e8ea188834553
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289714"
---
# <a name="create-safe-sender-lists-in-eop"></a>EOP에서 수신 가능한 보낸 사람 목록 만들기

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online 사서함이 있는 Microsoft 365 고객 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 고객인 경우 EOP는 신뢰할 수 있는 보낸 사람으로부터 전자 메일을 받을 수 있는 여러 가지 방법을 제공합니다. 이러한 옵션에는 스팸 방지 정책의 Exchange 메일 흐름 규칙(전송 규칙), Outlook 수신 허용- 보낸 사람, IP 허용 목록(연결 필터링) 및 허용된 보낸 사람 목록 또는 허용된 도메인 목록이 포함됩니다. 이러한 옵션을 전체적으로 수신 수신이 가능한 보낸 사람 _목록으로 생각할 수 있습니다._

사용 가능한 수신 가능 보낸 사람 목록은 권장되는 목록부터 최소 권장 항목까지 순서대로 다음 목록에 설명되어 있습니다.

1. 메일 흐름 규칙
2. Outlook 수신이 안전한 보낸 사람
3. IP 허용 목록(연결 필터링)
4. 허용된 보낸 사람 목록 또는 허용된 도메인 목록(스팸 방지 정책)

메일 흐름 규칙을 사용하면 올바른 메시지만 허용할 수 있는 유연성을 확보할 수 있습니다. 스팸 방지 정책에서 허용된 보낸 사람 및 허용된 도메인 목록은 IP 허용 목록만큼 안전하지 않습니다. 보낸 사람 전자 메일 도메인은 쉽게 스푸핑됩니다. 그러나 IP 허용 목록은 해당 IP 주소에서  보낸 모든 도메인의 전자 메일이 스팸 필터링을 무시하기 때문에 위험을 제공합니다.

> [!IMPORTANT]
>
> - 수신이 가능한  보낸 사람 목록을 사용하여 스팸 필터링에 대해 적용한 예외를 면밀하게 모니터링해야 합니다.
>
> - 수신 가능 보낸 사람 목록을 사용하여 가음성(양호한 전자 메일로 표시)을 지원할 수 있는 반면, 수신 가능하면 안전한 보낸 사람 목록을 임시 솔루션으로 사용하는 것을 고려해야 합니다. 스팸 필터링에 대한 예외로 조직이 스푸핑 및 기타 공격을 하게 될 수 있기 때문에 수신이 가능한 보낸 사람 목록을 사용하여 가짓 긍정을 관리하는 것은 권장되지 않습니다. 수신이 가능한 보낸 사람 목록을 사용하여 가짓 긍정을 관리하는 경우 신세를 들이고 항목 보고서 메시지 및 파일을 [Microsoft에](report-junk-email-messages-to-microsoft.md) 준비된 것으로 유지해야 합니다.
>
> - 도메인에서 비인식 전자 메일(스푸핑 방지 보호 무시)을 보내지만 스팸 방지 및 맬웨어 방지 검사를 무시하지 못하도록 허용하려면 [AllowedToSpoof](walkthrough-spoof-intelligence-insight.md) 수신 허용 - 보낸 사람 목록에 추가하면 됩니다.
>
> - EOP 및 Outlook에서는 서로 다른 메시지 속성을 검사하여 메시지 보낸 사람 확인 자세한 내용은 이 [](#considerations-for-bulk-email) 문서 부분의 대량 전자 메일에 대한 고려 사항 섹션을 참조하세요.

반면에 차단된 보낸 사람 목록을 사용하여 특정 원본의 전자 메일을 차단하는 몇 가지 _옵션도 있습니다._ 자세한 내용은 [EOP에서 차단할 보낸 사람 목록 만들기](create-block-sender-lists-in-office-365.md)를 참조하세요.

## <a name="recommended-use-mail-flow-rules"></a>(권장) 메일 흐름 규칙 사용

Exchange Online 및 독립 실행형 EOP의 메일 흐름 규칙에서는 조건 및 예외를 사용하여 메시지를 식별하고 해당 메시지에 대해 수행할 작업을 지정합니다. 자세한 내용은 Exchange Online의 메일 흐름 [규칙(전송 규칙)을 참조하세요.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

다음 예에서는 스팸 필터링을 건너뛰기 위해 contoso.com 전자 메일이 필요하다고 가정합니다. 이렇게하려면 다음 설정을 구성합니다.

1. **조건:** **보낸 사람 도메인이** \> **contoso.com.** \>

2. 다음 설정 중 하나를 구성합니다.

   - **메일 흐름 규칙 조건:** 메시지 헤더에는 다음 단어 헤더  \>  \> **이름**: `Authentication-Results` \> **헤더 값**: `dmarc=pass` 또는 `dmarc=bestguesspass` .

     이 조건은 보내는 전자 메일 도메인의 전자 메일 인증 상태를 확인하여 보내는 도메인이 스푸핑되지 않는지 검사합니다. 전자 메일 인증에 대한 자세한 내용은 [SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)및 [DMARC를 참조하세요.](use-dmarc-to-validate-email.md)

   - **IP 허용 목록:** 연결 필터 정책에서 원본 IP 주소 또는 주소 범위를 지정합니다.

     보내는 도메인에서 전자 메일 인증을 사용하지 않는 경우 이 설정을 사용하세요. IP 허용 목록의 원본 IP 주소에 대한 경우 최대한 제한적으로 설정해야 합니다. IP 주소 범위가 /24 이하인 것이 좋습니다(적을 좋음). 소비자 서비스(예: outlook.com) 또는 공유 인프라에 속하는 IP 주소 범위를 사용하지 않습니다.

   > [!IMPORTANT]
   >
   > - 스팸 필터링을 건너뛰기 위한 조건으로 보낸 사람 도메인만 사용하여 메일 흐름 규칙을 구성하지 않습니다.  이렇게 하면  공격자가 보내는 도메인을 스푸핑(또는 전체 전자 메일 주소 가장)하고, 모든 스팸 필터링을 건너뛰고, 메시지가 받는 사람의 받은 편지함으로 도착하도록 보낸 사람 인증 검사를 건너뛸 가능성이 크게 증가합니다.
   >
   > - 소유한 도메인(허용 도메인) 또는 인기 있는 도메인(예: microsoft.com)을 메일 흐름 규칙의 조건으로 사용하지 않습니다. 이렇게 하면 공격자가 필터링되는 전자 메일을 보낼 수 있는 기회가 만들어지기 때문에 높은 위험으로 간주됩니다.
   >
   > - NAT(Network Address Translation) 게이트웨이 뒤에 있는 IP 주소를 허용하는 경우 IP 허용 목록의 범위를 알기 위해 NAT 풀에 포함되는 서버를 알아야 합니다. IP 주소 및 NAT 참가자는 변경할 수 있습니다. 표준 유지 관리 절차의 일부로 IP 허용 목록 항목을 정기적으로 검사해야 합니다.

3. **선택적 조건:**

   - **보낸 사람** \> **내부/외부** \> **조직 외부:** 이 조건은 암시적이지만 올바르게 구성되지 않을 수 있는 전자 메일 서버를 고려하는 데 이 조건을 사용하는 것이 좋습니다.

   - **제목 또는 본문** \> **제목 또는 본문에 다음 단어 포함** \> : 제목 줄이나 메시지 본문의 키워드 또는 구로 메시지를 추가로 제한할 수 있는 경우 해당 단어를 \<keywords\> 조건으로 사용할 수 있습니다.

4. **작업:** 규칙에서 다음 두 작업을 모두 구성합니다.

   a. **메시지 속성 수정** \> **SCL(스팸 지수)** \> 설정 **스팸 필터링을 무시합니다.**

   b. **메시지 속성 수정** \> **메시지 헤더 설정**: **메시지 헤더를** \<CustomHeaderName\> **값으로 설정** \<CustomHeaderValue\>

      예를 들면 `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`와 같습니다. 규칙에 도메인이 두 개 이상 있는 경우 헤더 텍스트를 적절하게 사용자 지정할 수 있습니다.

      메일 흐름 규칙으로 인해 메시지가 스팸 필터링을 건너뛰면 값 값이 `SFV:SKN` **X-Forefront-Antispam-Report** 헤더에 스탬프 처리됩니다. 메시지가 IP 허용 목록에 있는 원본에서 보낸 경우 값도 `IPV:CAL` 추가됩니다. 이러한 값은 문제 해결에 도움이 될 수 있습니다.

![스팸 필터링을 무시하기 위한 EAC의 메일 흐름 규칙 설정](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>Outlook 수신이 안전한 보낸 사람 사용

> [!CAUTION]
> 이 방법을 사용하면 공격자가 받은 편지함으로 전자 메일을 배달하여 다른 방법으로 필터링될 위험이 높습니다. 그러나 사용자의 안전한 보낸 사람 또는 안전한 도메인 목록은 맬웨어 또는 높은 신뢰도의 피싱 메시지가 필터링되는 것을 방지하지 않습니다.

사용자 또는 관리자는 조직 설정 대신 사서함의 수신 허용 - 보낸 사람 목록에 보낸 사람 전자 메일 주소를 추가할 수 있습니다. 자세한 내용은 [Office 365에서 Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md)사서함의 정크 메일 설정 구성을 참조하세요. 보낸 사람이 필터링 스택의 일부를 무시하기 때문에 대부분의 상황에서는 바람직하지 않습니다. 보낸 사람이 신뢰하는 경우도 보낸 사람이 손상된 후 악의적인 콘텐츠를 보낼 수 있습니다. 필터에서 모든 메시지를 확인한 다음 필터에 문제가 있는 경우 [Microsoft에](report-junk-email-messages-to-microsoft.md) 가짓 긍정/부정을 보고하는 데 필요한 작업을 필터에 적용하는 것이 가장 최선입니다. 필터링 스택을 무시하면 [ZAP가 방해됩니다.](zero-hour-auto-purge.md)

사용자의 수신-보낸 사람 목록으로 인해 메시지가 스팸 필터링을 건너뛰면 **X-Forefront-Antispam-Report** 헤더 필드에 스팸, 스푸핑 및 피싱에 대한 필터링이 무시된 `SFV:SFE` 것입니다.

## <a name="use-the-ip-allow-list"></a>IP 허용 목록 사용

앞서 설명한 메일 흐름 규칙을 사용할 수 없는 경우 다음으로는 연결 필터 정책의 IP 허용 목록에 원본 전자 메일 서버 또는 서버를 추가하는 것이 가장 좋습니다. 자세한 내용은 EOP에서 연결 필터링 [구성을 참조합니다.](configure-the-connection-filter-policy.md)

**참고:**

- 허용되는 IP 주소 수를 최소로 유지하는 것이 중요하기 때문에 가능하면 전체 IP 주소 범위를 사용하지 않도록 합니다.

- 소비자 서비스(예: outlook.com) 또는 공유 인프라에 속하는 IP 주소 범위를 사용하지 않습니다.

- IP 허용 목록의 항목을 정기적으로 검토하고 더 이상 필요 없는 항목을 제거합니다.

> [!CAUTION]
> 메일 흐름 규칙과 같은 추가 확인이 없는 경우 IP 허용 목록의 원본에서 보낸 전자 메일은 스팸 필터링 및 보낸 사람 인증(SPF, DKIM, DMARC) 검사를 건너뜁습니다. 이렇게 하면 공격자가 받은 편지함으로 전자 메일을 배달할 위험이 높아지며 그렇지 않으면 필터링됩니다. 그러나 IP 허용 목록은 맬웨어 또는 높은 신뢰도의 피싱 메시지가 필터링되는 것을 방지하지 않습니다.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>허용된 보낸 사람 목록 또는 허용된 도메인 목록 사용

가장 바람직한 옵션은 스팸 방지 정책에서 허용된 보낸 사람 목록 또는 허용된 도메인 목록을 사용하는 것입니다. 보낸 사람이 모든  스팸, 스푸핑 및 피싱 보호 및 보낸 사람 인증(SPF, DKIM, DMARC)을 무시하기 때문에 가능하면 이 옵션을 피해야 합니다. 이 방법은 임시 테스트에만 사용하는 것이 가장 좋습니다. 자세한 단계는 [EOP의](configure-your-spam-filter-policies.md) 스팸 방지 정책 구성 항목에서 찾을 수 있습니다.

이러한 목록에 대한 최대 제한은 약 1,000개 항목입니다. 그러나 포털에 30개 항목만 입력할 수 있습니다. PowerShell을 사용하여 30개 이상의 항목을 추가해야 합니다.

> [!CAUTION]
>
> - 이 방법을 사용하면 공격자가 받은 편지함으로 전자 메일을 배달하여 다른 방법으로 필터링될 위험이 높습니다. 그러나 허용된 보낸 사람 또는 허용된 도메인 목록은 맬웨어 또는 높은 신뢰도의 피싱 맬웨어가 필터링되는 것을 방지하지 않습니다.
>
> - 소유한 도메인(허용 도메인) 또는 인기 있는 도메인(예: microsoft.com)을 허용 도메인 목록에 사용하지 않습니다.

## <a name="considerations-for-bulk-email"></a>대량 전자 메일에 대한 고려 사항

표준 SMTP 전자 메일 메시지는 메시지 봉투와 메시지 콘텐츠로 구성됩니다.  메시지 봉투에는 SMTP 서버 간에 메시지를 전송하고 배달하는 데 필요한 정보가 포함되어 있습니다. 메시지 콘텐츠에는 메시지 헤더 필드(총체적으로 메시지 *헤더)와* 메시지 본문이 포함되어 있습니다. 메시지 봉투는 RFC 5321에 설명되어 있으며 메시지 헤더는 RFC 5322에 설명되어 있습니다. 받는 사람은 메시지 전송 프로세스에 의해 생성되어 실제로 메시지의 일부가 아니기 때문에 실제 메시지 봉투를 볼 수 없습니다.

- MAIL FROM 주소, P1 보낸 사람 또는 봉투 보낸 사람라고도 하는 주소는 메시지의 SMTP 전송에 사용되는 전자 메일 `5321.MailFrom` 주소입니다.  이 전자 메일 주소는  일반적으로 메시지 헤더의 반환 경로 헤더 필드에 기록됩니다(보낸 사람이 다른  반환 경로 전자 메일 주소를 지정하는 것은 가능). 메시지를 배달할 수 없는 경우 배달 못 한 보고서(NDR 또는 반송 메시지라고도 합니다)의 받는 사람입니다.

- 보낸 사람(보낸 사람 주소 또는 P2 보낸 사람)은 보낸 사람 헤더 필드의 전자 메일 주소로, 전자 메일 클라이언트에 표시되는 보낸 사람 전자 메일 `5322.From` 주소입니다.  

주소와 주소가 `5321.MailFrom` `5322.From` 같을 때가 잦습니다(사용자 간 통신). 그러나 다른 사람을 대신하여 전자 메일을 보낼 경우 주소가 다를 수 있습니다. 이 문제는 대량 전자 메일 메시지에 대해 가장 자주 발생합니다.

예를 들어 Blue Yonder Airlines에서 Margie's Travel을 고용하여 전자 메일 광고를 보낸 경우를 가정해 보겠습니다. 받은 편지함에서 받는 메시지의 속성은 다음과 같습니다.

- 주소가 `5321.MailFrom` blueyonder.airlines@margiestravel.com.

- 주소는 blueyonder@news.blueyonderairlines.com Outlook에 `5322.From` 표시됩니다.

EOP의 스팸 방지 정책의 수신 허용 - 보낸 사람 목록 및 수신 허용 - 도메인 목록은 주소만 검사합니다. 이는 주소를 사용하는 Outlook 수신 허용 - 보낸 사람과 `5322.From` `5322.From` 유사합니다.

이 메시지가 필터링되지 않도록 방지하기 위해 다음 단계를 수행하면 됩니다.

- Outlook blueyonder@news.blueyonderairlines.com 보낸 사람으로 `5322.From` 주소(주소)를 추가합니다.

- [메일 흐름 규칙은](#recommended-use-mail-flow-rules) 주소, blueyonder@news.blueyonderairlines.com(주소, blueyonder.airlines@margiestravel.com 또는 둘 다)에서 메시지를 `5322.From` blueyonder.airlines@margiestravel.com `5321.MailFrom` 조건과 함께 사용하세요.

자세한 내용은 [EOP에서 수신이 가능한 보낸 사람 목록 만들기를 참조하세요.](create-safe-sender-lists-in-office-365.md)
