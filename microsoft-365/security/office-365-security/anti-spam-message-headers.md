---
title: 스팸 방지 메시지 헤더
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
description: 관리자는 메시지와 메시지 처리 방법에 대한 정보를 제공하기 위해 Exchange Online Protection에서 메시지에 추가하는 헤더 필드에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d63d173b90ffd868cfbeac212f2c9d5a6ee125c6
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208225"
---
# <a name="anti-spam-message-headers-in-microsoft-365"></a>Microsoft 365의 스팸 방지 메시지 헤더

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직의 경우, EOP에서 **X-Forefront-Antispam-Report** 헤더를 검색하여 각 인바운드 전자 메일 메시지에 삽입합니다. 관리자는 이 헤더의 필드를 통해 메시지 및 메시지 처리 방법에 대한 정보를 확인할 수 있습니다. **X-Microsoft-Antispam** 헤더의 필드는 대량 메일 및 피싱에 대한 추가 정보를 제공합니다. 이러한 두 헤더 외에도, Exchange Online Protection은 **Authentication-results** 헤더에서 처리하는 각 메시지의 전자 메일 인증 결과를 삽입합니다.

다양한 전자 메일 클라이언트에서 전자 메일 메시지 헤더를 보는 방법에 대한 자세한 내용은 [Outlook에서 인터넷 메시지 헤더 보기](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)를 참조하세요.

> [!TIP]
> 메시지 헤더의 내용을 복사하여 [메시지 분석기](https://testconnectivity.microsoft.com/?tabid=mha) 도구에 붙여 넣을 수 있습니다. 이 도구는 헤더를 구문 분석하여 더 판독하기 쉬운 형식으로 삽입합니다.

## <a name="x-forefront-antispam-report-message-header-fields"></a>X-Forefront-Antispam-Report 메시지 헤더 필드

메시지 헤더 정보에 액세스한 후 **X-X-Forefront-Antispam-Report**를 검색하여 이 필드를 찾습니다. 이 헤더의 다른 필드는 Microsoft 스팸 방지 팀에서 진단용으로만 사용합니다.

|||
|---|---|
|**헤더 필드**|**설명**|
|ARC|ARC 프로토콜에는 다음과 같은 헤더가 있습니다. <ul><li>AAR: DMARC의 인증 결과 헤더의 내용을 기록합니다.</li><li>AMS: 이 헤더는 메시지 암호화 서명을 포함합니다.</li><li>AS: 메시지 헤더의 암호화 서명을 포함합니다. 이 헤더에는 체인 유효성 검사의 결과를 **none**, **pass** 또는 **fail**로 포함하는 "cv ="라는 체인 유효성 검사 태그가 포함되어 있습니다.</li></ul>|
|CAT:|메시지에 적용 되는 보호 정책의 범주: <ul><li>BULK: 대량</li><li>DIMP: 도메인 가장</li><li>GIMP: 사서함 인텔리전스</li><li>HPHSH 또는 HPHISH: 신뢰도가 높은 피싱 </li><li>HSPM: 높은 정확도의 스팸</li><li>MALW: 맬웨어</li><li>PHSH: 피싱</li><li>SPM: 스팸</li><li>SPOOF: 스푸핑</li><li>UIMP: 사용자 가장</li></ul><br/>인바운드 메시지는 여러 유형의 보호 및 다중 검색 검사에 의해 플래그가 지정될 수 있습니다. 정책의 우선 순위가 다르기 때문에 우선 순위가 가장 높은 정책이 먼저 적용됩니다. 자세한 내용을 알고 싶다면 [전자 메일에 여러 보호 방법과 검색 검사가 실행될 때 어떤 정책이 적용되는지](how-policies-and-protections-are-combined.md)를 확인합니다.|
|CIP: \[IP 주소\]|연결할 IP 주소. IP 허용 목록 또는 IP 차단 목록에 이 IP 주소를 사용할 수 있습니다. 자세한 내용은 [연결 필터링 구성](configure-the-connection-filter-policy.md)을 참조하십시오.|
|CTRY|연결 IP 주소(원래 메시지를 보낸 IP 주소와 다를 수도 있음)를 통해 확인되는 원본 국가입니다.|
|H:\[helostring\]|연결 전자 메일 서버의 HELO 또는 EHLO 문자열입니다.|
|IPV:CAL|원본 IP 주소가 IP 허용 목록에 있기 때문에 메시지가 스팸 필터링을 건너뛰었습니다. 자세한 내용은 [연결 필터링 구성](configure-the-connection-filter-policy.md)을 참조하십시오.|
|IPV:NLI|IP 주소가 IP 신뢰도 목록에 포함되지 않았습니다.|
|LANG|국가 코드로 지정된 메시지 작성 언어입니다. 예를 들어 ru_RU는 러시아어입니다.|
|PTR:\[ReverseDNS\]|원본 IP 주소의 PTR 레코드 (역 DNS 조회라고도 함).|
|SCL|메시지의 SCL(스팸 지수)입니다. 값이 높을수록 메시지가 스팸일 가능성이 더 높습니다. 자세한 내용은 [SCL(스팸 지수)](spam-confidence-levels.md)을 참조하세요.|
|SFTY|메시지가 피싱 메일로 확인되었으므로 다음 값 중 하나로 표시됩니다. <ul><li>9.1: 기본값. 메시지에 피싱 URL이 포함되어 있거나, 다른 피싱 콘텐츠가 포함되어 있을 수도 있고, Microsoft 365에 메시지를 릴레이하기 전에 Exchange Server의 온-프레미스 버전과 같은 다른 메일 필터에 의해 피싱으로 표시되어 있을 수 있습니다.</li><li>[9.11: 조직 내 또는 자체 스푸핑](anti-spoofing-protection.md#different-types-of-spoofing) 메시지가 보낸 사람 헤더에 있는 보낸 사람의 전자 메일 도메인이 수신 도메인과 동일하거나, 수신 도메인에 적합하거나, 수신 도메인과 동일한 조직의 일부인지에 대한 스푸핑 방지 확인에 실패했습니다. 조직 내 스푸핑에 대한 안전 정보가 메시지에 추가됩니다.</li><li>9.19: 도메인 가장. 발신 도메인이 ATP 피싱 방지 정책에 지정된 보호된 도메인(수신자 조직 또는 사용자 지정 도메인이 소유한 도메인)을 가장하려고 합니다. 도메인 가장을 위한 안전 정보가 메시지에 추가됩니다(안전 정보가 ATP 피싱 방지 정책에서 활성화된 경우).</li><li>9.20: 사용자 가장. 발신 사용자가 수신자 조직의 사용자 또는 ATP 피싱 방지 정책에 지정된 보호된 사용자를 가장하려고 합니다. 사용자 가장을 위한 안전 정보가 메시지에 추가됩니다(안전 정보가 ATP 피싱 방지 정책에서 활성화된 경우).</li><li>9.21: [도메인 간 스푸핑](anti-spoofing-protection.md#different-types-of-spoofing). 스푸핑 방지 실패 메시지는 발신인 헤더의 발신인 이메일 도메인이 인증되지 않은 외부 도메인인지 확인합니다. [CompAuth](#authentication-results-message-header-fields-used-by-microsoft-email-authentication))와 함께 사용합니다.</li><li>9.22: 9.21과 동일하며, 다른 사항은 사용자에게 재정의된 [수신 허용 - 보낸 사람]이 있다는 점입니다.</li><li>9.23: 9.22와 동일하며, 다른 사항은 조직에 재정의된 허용된 보낸 사람 또는 도메인이 있다는 점입니다.</li><li>9.24: 9.23과 동일하며, 다른 사항은 사용자에게 재정의된 Exchange 메일 흐름 규칙(전송 규칙이라고도 함)이 있다는 점입니다.</li></ul>|
|SFV:BLK|사용자의 Outlook 수신 거부(사용자의 수신 거부 목록)에 있는 주소에서 보낸 메시지이므로 필터링을 건너뛰었으며 메시지가 차단되었습니다.<br/></br> 관리자가 사용자의 수신 거부 목록을 관리하는 방법에 대한 자세한 내용은 [Exchange Online 사서함의 정크 메일 설정 구성](configure-junk-email-settings-on-exo-mailboxes.md)을 참조하세요.|
|SFV:NSPM|스팸 필터링이 메시지를 스팸이 아닌 것으로 표시하고 메시지를 지정된 받는 사람에게 보냈습니다.|
|SFV:SFE|사용자의 Outlook 수신 허용(사용자의 수신 허용 - 보낸 사람 목록)에 있는 주소에서 보낸 메시지이므로 필터링을 건너뛰었으며 메시지를 통과시켰습니다.<br/></br> 관리자가 사용자의 수신 허용 - 보낸 사람 목록을 관리하는 방법에 대한 자세한 내용은 [Exchange Online 사서함의 정크 메일 설정 구성](configure-junk-email-settings-on-exo-mailboxes.md)을 참조하세요.|
|SFV:SKA|메시지가 스팸 방지 정책에서 허용되는 보낸 사람 목록 또는 허용되는 도메인 목록의 항목과 일치하기 때문에 스팸 필터링을 건너뛰고 받은 편지함으로 배달되었습니다. 자세한 내용은 [스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.|
|SFV: SKB|메시지가 스팸 방지 정책에 있는 수신 거부 목록이나 차단된 도메인 목록의 항목과 일치하기 때문에 메시지를 스팸으로 표시했습니다. 자세한 내용은 [스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.|
|SFV:SKI|SFV:SKN과 마찬가지로 다른 이유 때문에 메시지가 스팸 필터링을 건너뛰었습니다(예: 테넌트 내의 조직 내 전자 메일).|
|SFV:SKN|스팸 필터링을 사용하여 메시지를 배달하기 전에 메시지를 스팸이 아닌 것으로 표시했습니다(예: 메시지가 메일 흐름 규칙에 따라 SCL-1 또는 **스팸 필터링 우회**로 표시됨).|
|SFV:SKQ|메시지가 격리에서 해제되었으며 받는 사람에게 전송되었습니다.|
|SFV:SKS|스팸 필터링으로 메시지를 처리하기 전에 메시지를 스팸으로 표시했습니다(예: 메시지가 메일 흐름 규칙에 따라 SCL 5~9로 표시됨).|
|SFV:SPM|메시지가 스팸 필터링에 의해 스팸으로 표시되었습니다.|
|SRV:BULK|메시지가 스팸 필터링 및 BCL(대량 불만 수준) 임계값에 의해 벌크 메일로 식별되었습니다. _MarkAsSpamBulkMail_ 매개 변수가 `On`인 경우(기본적으로 켜져 있음) 벌크 메일 메시지는 높은 정확도의 스팸(SCL 9)으로 표시됩니다. 자세한 내용은 [스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.|
|X-CustomSpam: \[ASFOption\]|메시지가 ASF(고급 스팸 필터) 설정과 일치합니다. 각 ASF 설정의 X-헤더 값을 보려면 [ASF(고급 스팸 필터) 설정](advanced-spam-filtering-asf-options.md)을 참조하세요.|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>X-Microsoft-Antispam 메시지 헤더 필드

다음 표에서는 **X-Microsoft-Antispam** 메시지 헤더의 유용한 필드에 대해 설명합니다. 이 헤더의 다른 필드는 Microsoft 스팸 방지 팀에서 진단용으로만 사용합니다.

|||
|---|---|
|**헤더 필드**|**설명**|
|BCL|메시지의 BCL(대량 불만 수준)입니다. BCL이 높다는 것은 벌크 메일 메시지(_회색 메일_이라고도 함)가 불만을 야기할 가능성이 높다는 것을 의미합니다(그러므로 스팸일 가능성이 높음). 자세한 내용은 [BCL(대량 불만 수준)](bulk-complaint-level-values.md)을 참조하세요.|
|

## <a name="authentication-results-message-header"></a>Authentication-Results 메시지 헤더

전자 메일 서버에서 전자 메일 메시지를 수신 하는 경우 SPF, DKIM 및 DMARC에 대한 검사 결과는 **Authentication-results** 메시지 헤더의 Microsoft 365를 통해 기록되거나 스탬프 처리됩니다.

### <a name="check-stamp-syntax-and-examples"></a>검사 스탬프 구문 및 예제

다음 구문 예제에서는 Microsoft 365가 메일 서버에서 수신할 때 전자 메일 인증 확인을 실행하는 각 전자 메일의 메시지 헤더에 적용 되는 "스탬프"라는 텍스트 부분을 보여줍니다. 스탬프가 **Authentication-Results** 헤더에 추가됩니다.

#### <a name="syntax-spf-check-stamp"></a>구문: SPF 체크 스탬프

SPF의 경우, 다음 구문이 적용됩니다.

```text
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

##### <a name="examples-spf-check-stamp"></a>예: SPF 체크 스탬프

```text
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
```

#### <a name="syntax-dkim-check-stamp"></a>구문: DKIM 체크 스탬프

DKIM의 경우, 다음 구문이 적용됩니다.

```text
dkim=<pass|fail (reason)|none> header.d=<domain>
```

##### <a name="examples-dkim-check-stamp"></a>예: DKIM 체크 스탬프

```text
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

#### <a name="syntax-dmarc-check-stamp"></a>구문: DMARC 체크 스탬프

DMARC의 경우, 다음 구문이 적용됩니다.

```text
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

##### <a name="examples-dmarc-check-stamp"></a>예: DMARC 체크 스탬프

```text
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-microsoft-email-authentication"></a>Microsoft 전자 메일 인증에서 사용하는 Authentication-results 메시지 헤더 필드

이 표에서는 각 전자 메일 인증 확인에 대한 필드와 가능한 값에 대해 설명합니다.

|||
|---|---|
|**헤더 필드**|**설명**|
|조치|DMARC 검사 결과에 따라 스팸 필터에서 수행하는 작업을 표시합니다. 예시: <ul><li>**oreject** 또는 **o.reject**: 재정의에 대한 거부를 나타냅니다. 이 경우, Microsoft 365에서는 p=reject 정책을 사용하는 DMARC TXT 레코드의 도메인으로부터 DMARC 검사에 실패하는 메시지를 수신할 때 이 작업을 사용합니다.  메시지를 삭제하거나 거부하는 대신, Microsoft 365에서는 해당 메시지를 스팸으로 표시합니다. Microsoft 365를 이런 방식으로 구성하는 방법에 대한 자세한 내용은 [Microsoft 365에서 DMARC에 실패한 인바운드 전자 메일을 처리하는 방법](use-dmarc-to-validate-email.md#how-microsoft-365-handles-inbound-email-that-fails-dmarc)을 참조하세요.</li><li>**pct.quarantine**: DMARC를 통과하지 못하는 메시지 중 100% 미만의 백분율이 전달됨을 나타냅니다. 즉, 메시지가 DMARC에 실패하고 정책이 격리로 설정되어 있지만, pct 필드는 100%로 설정되지 않았고, 지정된 도메인의 정책에 따라, 시스템에서 DMARC 작업을 적용하지 않도록 임의로 결정했음을 의미합니다.</li><li>**pct.reject**: DMARC를 통과하지 못하는 메시지 중 100% 미만의 백분율이 전달됨을 나타냅니다. 즉, 메시지가 DMARC에 실패하고 정책이 거부로 설정되어 있지만, pct 필드는 100%로 설정되지 않았고, 지정된 도메인의 정책에 따라, 시스템에서 DMARC 작업을 적용하지 않도록 임의로 결정했음을 나타냅니다.</li><li>**permerror**: DMARC 평가 중에 영구적 오류(예: DNS에서 잘못된 형식의 DMARC TXT 레코드 발생)가 발생했습니다. 이 메시지를 다시 보내도 결과가 달라지지 않을 수 있습니다. 대신, 이 문제를 해결하기 위해 도메인 소유자에게 문의해야 합니다.</li><li>**temperror**: DMARC 평가 중에 일시적인 오류가 발생했습니다. 전자 메일을 제대로 처리할 수 있도록 보낸 사람이 메시지를 나중에 다시 보내도록 요청할 수 있습니다.</li></ul>|
|compauth|복합 인증 결과 Microsoft 365에서 SPF, DKIM, DMARC 또는 메시지의 기타 부분과 같은 다양한 유형의 인증을 결합하여 메시지의 인증 여부를 확인하는 데 사용됩니다. 평가 기준으로 보낸 사람: 도메인을 사용합니다.|
|dkim|메시지의 DKIM 검사 결과를 설명합니다. 가능한 값은 다음과 같습니다. <ul><li>**통과**: 통과한 메시지의 DKIM 검사를 나타냅니다.</li><li>**실패(원인)**: 실패한 메시지의 DKIM 검사와 오류를 나타냅니다. 예를 들어, 메시지에 서명이 없거나 서명이 확인되지 않은 경우입니다.</li><li>**없음**: 메시지에 서명이 없음을 나타냅니다. 이는 도메인에 DKIM 레코드가 있거나 DKIM 레코드가 결과에 대해 평가되지 않음을 의미하지 않으며, 이 메시지에 서명이 없음을 나타냅니다.</li></ul>|
|dmarc|메시지에 대한 DMARC 검사 결과를 설명합니다. 가능한 값은 다음과 같습니다. <ul><li>**통과**: 메시지에 대한 DMARC 에 통과했음을 나타냅니다.</li><li>**실패**: 메시지에 대한 DMARC 검사에 실패했음을 나타냅니다.</li><li>**bestguesspass**: 도메인의 DMARC TXT 레코드가 없음을 나타내며, 이미 존재하는 경우에는 해당 메시지에 대한 DMARC 검사를 통과했음을 나타냅니다. 이는 `5321.MailFrom` 주소(메일 보낸 사람 주소, P1 보낸 사람 또는 봉투 보낸 사람이라고도 함)의 도메인이 `5322.From` 주소(보낸 사람 주소 또는 P2 보낸 사람이라고도 함)의 도메인과 일치하기 때문입니다.</li><li>**없음**: DNS에 송신 도메인에 대한 DMARC TXT 레코드가 존재하지 않음을 나타냅니다.|
|머리글. d|해당하는 경우, DKIM 서명에서 식별된 도메인입니다. 이는 공개 키에 대해 쿼리된 도메인입니다.|
|header.from|전자 메일 메시지 헤더에 있는 `5322.From` 주소(보낸 사람 주소 또는 P2 보낸 사람이라고도 함)의 도메인입니다. 받는 사람은 전자 메일 클라이언트에서 보낸 사람 주소를 봅니다.|
|이유|복합 인증을 통과 또는 실패한 이유입니다. 값은 3 자리 코드입니다. 예시: <ul><li>**000**: 메시지가 인증에 명시적으로 실패했습니다(`compauth=fail`). 예를 들어, 메시지가 격리 또는 거부 조치와 함께 DMARC 실패를 수신한 경우입니다.</li><li>**001**: 메시지가 인증에 암시적으로 실패했습니다(`compauth=fail`). 이는 보내는 도메인에 전자 메일 인증 레코드가 게시되지 않았거나 인증 레코드가 경우에는 실패 정책이 약함(SPF soft fail 또는 중립, `p=none`인 DMARC 정책)을 의미합니다.</li><li>**002**: 보낸 사람/도메인 쌍에 대해 스푸핑된 전자 메일을 보내는 것을 명시적으로 금지하는 정책을 가지고 있음을 의미합니다. 이 설정은 관리자가 수동으로 설정합니다.</li><li>**010**: 메시지가 거부 또는 격리 작업과 함께 DMARC에서 실패했음을 의미하며 전송 도메인은 조직에서 허용하는 도메인 중 하나입니다(이는 자체 대 자체 또는 내부 조직, 스푸핑의 일부).</li><li>**1xx** 또는 **7xx**: 메시지가 인증을 통과했습니다(`compauth=pass`). 마지막 두 자리는 Microsoft 365에서 사용하는 내부 코드입니다.</li><li>**2xx**: 메시지가 암시적 인증을 소프트 패스했습니다(`compauth=softpass`). 마지막 두 자리는 Microsoft 365에서 사용하는 내부 코드입니다.</li><li>**3xx**: 복합 인증에 대해 메시지를 확인하지 않았습니다(`compauth=none`).</li><li>**4xx** 또는 **9xx**: 메시지에서 복합 인증을 바이패스했습니다(`compauth=none`). 마지막 두 자리는 Microsoft 365에서 사용하는 내부 코드입니다.</li><li>**6xx**: 메시지가 암시적 전자 메일 인증에 실패했고 전송 도메인은 조직에서 허용하는 도메인 중 하나입니다(이는 자체 대 자체 또는 내부 조직, 스푸핑의 일부).</li></ul>|
|smtp.mailfrom|`5321.MailFrom` 주소(메일 보낸 사람 주소, P1 보낸 사람 또는 봉투 보낸 사람이라고도 함)의 도메인입니다. 배달 못 함 보고서(NDR 또는 반송 메시지라고도 함)에 사용되는 전자 메일 주소입니다.|
|spf|메시지에 대한 SPF 검사 결과를 설명합니다. 가능한 값은 다음과 같습니다. <ul><li>**통과(IP 주소)**: 전달된 메시지에 대한 SPF 검사를 나타내고 보낸 사람의 IP 주소를 포함합니다. 클라이언트는 보낸 사람의 도메인을 대신하여 전자 메일을 보내거나 릴레이할 수 있습니다.</li><li>**실패(IP 주소)**: 메시지에 대한 SPF 검사가 실패했음을 나타내고 보낸 사람의 IP 주소를 포함합니다. 이를 종종 _하드 실패_라고 합니다.</li><li>**소프트 실패(원인)**: SPF 레코드에서 호스트가 보낼 수 없는 것으로 지정되었지만 전환 중임을 나타냅니다.</li><li>**중립**: SPF 레코드에 IP 주소가 인증되었는지 여부를 어설션하지 않음을 명시적으로 지정되었음을 나타냅니다.</li><li>**없음**: 도메인에 SPF 레코드가 없거나 SPF 레코드에서 결과를 평가하지 않음을 나타냅니다.</li><li>**temperror**: 예를 들어 DNS 오류와 같은 일시적인 오류가 발생했음을 나타냅니다. 나중에 다시 시도하면 관리자 조치 없이도 성공할 수 있습니다.</li><li>**permerror**: 영구적인 오류가 발생했음을 나타냅니다. 예를 들어 도메인에 형식이 잘못된 SPF 레코드가 있을 때 발생합니다.</li></ul>|
|
