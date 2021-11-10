---
title: 스팸 방지 메시지 헤더
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: high
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 관리자는 EOP(Exchange Online Protection)에 의해 메시지에 추가되는 헤더 필드에 대해 알아볼 수 있습니다. 이러한 헤더 필드는 메시지 및 처리 방법에 대한 정보를 제공합니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8eaf567e4cbceae66a5acd1fa1a45565f15a4804
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2021
ms.locfileid: "60884004"
---
# <a name="anti-spam-message-headers-in-microsoft-365"></a>Microsoft 365의 스팸 방지 메시지 헤더

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

모든 Microsoft 365 조직에서 EOP(Exchange Online Protection)는 들어오는 모든 메시지에 대해 스팸, 멀웨어 및 기타 위협을 검색합니다. 이러한 검색 결과는 메시지의 다음 헤더 필드에 추가됩니다.

- **X-Forefront-Antispam-Report**: 메시지에 대한 정보와 메시지 처리 방법에 대한 정보를 포함합니다.

- **X-Microsoft-Antispam**: 대량 메일 및 피싱에 대한 추가 정보가 포함되어 있습니다.

- **인증-결과**: SPF, DKIM 및 DMARC(전자 메일 인증) 결과에 대한 정보가 포함되어 있습니다.

이 문서에서는 이러한 헤더 필드에서 사용할 수 있는 항목에 대해 설명합니다.

다양한 전자 메일 클라이언트에서 전자 메일 메시지 헤더를 보는 방법에 대한 자세한 내용은 [Outlook에서 인터넷 메시지 헤더 보기](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)를 참조하세요.

> [!TIP]
> 메시지 헤더의 내용을 복사하여 [메시지 헤더 분석기](https://mha.azurewebsites.net/) 도구에 붙여 넣을 수 있습니다. 이 도구는 헤더를 구문 분석하여 더 판독하기 쉬운 형식으로 삽입합니다.

## <a name="x-forefront-antispam-report-message-header-fields"></a>X-Forefront-Antispam-Report 메시지 헤더 필드

메시지 헤더 정보를 받은 후 **X-Forefront-Antispam-Report** 헤더를 찾습니다. 이 헤더에는 세미콜론(;)으로 구분된 필드 및 값 쌍이 여러 개 있습니다. 예시:

`...CTRY:;LANG:hr;SCL:1;SRV:;IPV:NLI;SFV:NSPM;PTR:;CAT:NONE;SFTY:;...`

개별 필드 및 값에 대해 설명이 다음 표에 설명되어 있습니다.

> [!NOTE]
> **X-Forefront-Antispam-Report** 헤더에는 다양한 필드 및 값이 포함되어 있습니다. 표에 설명되어 있지 않은 필드는 Microsoft 스팸 방지 팀에서 진단용으로만 사용합니다.

****

|필드|설명|
|---|---|
|`ARC`|`ARC` 프로토콜에는 다음 필드가 있습니다. <ul><li>`AAR`: DMARC에서 **인증-결과** 헤더의 내용을 기록합니다.</li><li>`AMS`: 메시지의 암호화 서명을 포함합니다.</li><li>`AS`: 메시지 헤더의 암호화 서명을 포함합니다. 이 필드에는 `"cv="`이라는 체인 유효성 검사 태그가 포함되어 있습니다. 여기에는 **해당 없음**, **통과** 또는 **실패** 로 체인 유효성 검사 결과가 포함됩니다.</li></ul>|
|`CAT:`|메시지에 적용 되는 보호 정책의 범주: <ul><li>`BULK`: 대량</li><li>`DIMP`: 도메인 명의 도용</li><li>`GIMP`: [사서함 인텔리전스 기반 가장](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>`HPHSH` 또는 `HPHISH`: 높은 신뢰도의 피싱</li><li>`HSPM`: 신뢰도가 높은 스팸</li><li>`MALW`: 악성 코드</li><li>`PHSH`: 피싱</li><li>`SPM`: 스팸</li><li>`SPOOF`: 스푸핑</li><li>`UIMP` : 사용자 가장</li><li>`AMP` : 맬웨어 방지</li><li>`SAP` : 안전한 첨부 파일</li><li>`OSPM` : 발신 스팸</li></ul> <p> 인바운드 메시지는 여러 유형의 보호 및 다중 검색 검사에 의해 플래그가 지정될 수 있습니다. 정책의 우선 순위가 다르기 때문에 우선 순위가 가장 높은 정책이 먼저 적용됩니다. 자세한 내용을 알고 싶다면 [전자 메일에 여러 보호 방법과 검색 검사가 실행될 때 어떤 정책이 적용되는지](how-policies-and-protections-are-combined.md)를 확인합니다.|
|`CIP:[IP address]`|연결할 IP 주소. IP 허용 목록 또는 IP 차단 목록에 이 IP 주소를 사용할 수 있습니다. 자세한 내용은 [연결 필터링 구성](configure-the-connection-filter-policy.md)을 참조하십시오.|
|`CTRY`|연결 IP 주소(원래 메시지를 보낸 IP 주소와 다를 수도 있음)를 통해 확인되는 원본 국가입니다.|
|`H:[helostring]`|연결 전자 메일 서버의 HELO 또는 EHLO 문자열입니다.|
|`IPV:CAL`|원본 IP 주소가 IP 허용 목록에 있기 때문에 메시지가 스팸 필터링을 건너뛰었습니다. 자세한 내용은 [연결 필터링 구성](configure-the-connection-filter-policy.md)을 참조하세요.|
|`IPV:NLI`|IP 주소가 IP 신뢰도 목록에서 발견되지 않았습니다.|
|`LANG`|국가 코드로 지정된 메시지 작성 언어입니다(예를 들어 ru_RU는 러시아어입니다).|
|`PTR:[ReverseDNS]`|원본 IP 주소의 PTR 레코드 (역 DNS 조회라고도 함).|
|`SCL`|메시지의 SCL(스팸 지수)입니다. 값이 높을수록 메시지가 스팸일 가능성이 더 높습니다. 자세한 내용은 [SCL(스팸 지수)](spam-confidence-levels.md)을 참조하세요.|
|`SFTY`|메시지가 피싱 메일로 확인되었으므로 다음 값 중 하나로 표시됩니다. <ul><li>9.19: 도메인 가장. 보내는 도메인이 [보호된 도메인을 사용자 도용](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)하려고 시도하고 있습니다. 도메인 가장에 대한 안전 팁이 메시지에 추가됩니다(사용 가능한 경우).</li><li>9.20: 사용자 가장. 발신 사용자가 수신자 조직의 사용자 또는 Office 365용 Microsoft Defender의 [피싱 방지 정책에 지정된 보호된 사용자](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)를 가장하려고 합니다. 사용자 가장에 대한 안전 팁이 메시지에 추가됩니다(사용 가능한 경우).</li></ul>|
|`SFV:BLK`|사용자의 차단된 보낸 사람 목록에 있는 주소에서 보낸 메시지이므로 필터링을 건너뛰고 메시지를 차단했습니다. <p> 관리자가 사용자의 차단된 보낸 사람 목록을 관리하는 방법에 대한 자세한 내용은 [Exchange Online 사서함](configure-junk-email-settings-on-exo-mailboxes.md)에서 정크 전자 메일 설정 구성을 참조하시기 바랍니다.|
|`SFV:NSPM`|스팸 필터링은 메시지를 비스팸으로 표시했으며 메시지가 원하는 수신자에게 전송되었습니다.|
|`SFV:SFE`|필터를 건너뛰고 사용자의 안전 보낸 사람 목록에 있는 주소에서 보낸 메시지이므로 이 메시지가 허용되었습니다. <p> 관리자가 사용자의 안전한 보낸 사람 목록을 관리하는 방법에 대한 자세한 내용은 [Exchange Online 사서함](configure-junk-email-settings-on-exo-mailboxes.md)에서 정크 전자 메일 설정 구성을 참조하시기 바랍니다.|
|`SFV:SKA`|보낸 사람이 안티스팸 정책의 허용된 보낸 사람 목록 또는 허용된 도메인 목록에 있으므로 스팸 필터링을 건너뛰고 받은 편지함으로 배달되었습니다. 자세한 내용은 [스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.|
|`SFV:SKB`|메시지는 차단된 보낸 사람 목록 또는 안티스팸 정책의 차단된 도메인 목록의 보낸 사람과 일치하기 때문에 스팸으로 표시되었습니다. 자세한 내용은 [스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.|
|`SFV:SKI`|SFV와 유사합니다.SKN, 메시지는 다른 이유로 스팸 필터링을 건너뛰었습니다(예: 테넌트 내의 조직 내 전자 메일).|
|`SFV:SKN`|스팸 필터링을 사용하여 메시지를 배달하기 전에 메시지를 스팸이 아닌 것으로 표시했습니다(예: 메시지가 메일 흐름 규칙에 따라 SCL-1 또는 **스팸 필터링 우회** 로 표시됨).|
|`SFV:SKQ`|메시지가 검역소에서 릴리스되어 원하는 수신자에게 전송되었습니다.|
|`SFV:SKS`|스팸 필터링으로 메시지를 처리하기 전에 메시지를 스팸으로 표시했습니다(예: 메시지가 메일 흐름 규칙에 따라 SCL 5~9로 표시됨).|
|`SFV:SPM`|메시지가 스팸 필터링에 의해 스팸으로 표시되었습니다.|
|`SRV:BULK`|메시지가 스팸 필터링 및 BCL(대량 불만 수준) 임계값에 의해 벌크 메일로 식별되었습니다. _MarkAsSpamBulkMail_ 매개 변수가 `On`인 경우(기본적으로 켜져 있음) 벌크 메일 메시지는 스팸(SCL 6)으로 표시됩니다. 자세한 내용은 [스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.|
|`X-CustomSpam: [ASFOption]`|메시지가 ASF(고급 스팸 필터) 설정과 일치합니다. 각 ASF 설정의 X-헤더 값을 보려면 [ASF(고급 스팸 필터) 설정](advanced-spam-filtering-asf-options.md)을 참조하세요.|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>X-Microsoft-Antispam 메시지 헤더 필드

다음 표에서는 **X-Microsoft-Antispam** 메시지 헤더의 유용한 필드에 대해 설명합니다. 이 헤더의 다른 필드는 Microsoft 스팸 방지 팀에서 진단용으로만 사용합니다.

****

|필드|설명|
|---|---|
|`BCL`|메시지의 BCL(대량 불만 수준)입니다. BCL이 높을수록 대량 메일 메시지가 불만을 발생시킬 가능성이 높으므로 스팸일 가능성이 더 높습니다. 자세한 내용은 [BCL(대량 불만 수준)](bulk-complaint-level-values.md)을 참조하세요.|
|

## <a name="authentication-results-message-header"></a>Authentication-Results 메시지 헤더

SPF, DKIM 및 DMARC에 대한 전자 메일 인증 확인 결과는 인바운드 메시지의 **인증-결과** 메시지 헤더에 기록(스탬프됨)됩니다.

다음 목록에서는 각 전자 메일 인증 확인 유형에 대해 **인증-결과** 헤더에 추가된 텍스트를 설명합니다.

- SPF는 다음 구문을 사용합니다.

  ```text
  spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
  ```

  예를 들어 다음과 같습니다.

  ```text
  spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
  spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
  ```

- DKIM은 다음 구문을 사용합니다.

  ```text
  dkim=<pass|fail (reason)|none> header.d=<domain>
  ```

  예를 들어 다음과 같습니다.

  ```text
  dkim=pass (signature was verified) header.d=contoso.com
  dkim=fail (body hash did not verify) header.d=contoso.com
  ```

- DMARC는 다음 구문을 사용합니다.

  ```text
  dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
  ```

  예를 들어 다음과 같습니다.

  ```text
  dmarc=pass action=none header.from=contoso.com
  dmarc=bestguesspass action=none header.from=contoso.com
  dmarc=fail action=none header.from=contoso.com
  dmarc=fail action=oreject header.from=contoso.com
  ```

### <a name="authentication-results-message-header-fields"></a>인증확인 - 메시지 헤더 필드를 생성합니다.

다음 표에서는 각 전자 메일 인증 검사에 대한 필드 및 가능한 값에 대해 설명합니다.

****

|필드|설명|
|---|---|
|`action`|DMARC 검사 결과에 따라 스팸 필터에서 수행하는 작업을 표시합니다. 예를 들면 다음과 같습니다.<ul><li>**oreject** 또는 **o.reject**: 재정의에 대한 거부를 나타냅니다. 이 경우, Microsoft 365에서는 p=reject 정책을 사용하는 DMARC TXT 레코드의 도메인으로부터 DMARC 검사에 실패하는 메시지를 수신할 때 이 작업을 사용합니다.  메시지를 삭제하거나 거부하는 대신, Microsoft 365에서는 해당 메시지를 스팸으로 표시합니다. Microsoft 365를 이런 방식으로 구성하는 방법에 대한 자세한 내용은 [Microsoft 365에서 DMARC에 실패한 인바운드 전자 메일을 처리하는 방법](use-dmarc-to-validate-email.md#how-microsoft-365-handles-inbound-email-that-fails-dmarc)을 참조하세요.</li><li>**pct.quarantine**: DMARC를 통과하지 못하는 메시지 중 100% 미만의 백분율이 전달됨을 나타냅니다. 즉, 메시지가 DMARC에 실패하고 정책이 격리로 설정되어 있지만, pct 필드는 100%로 설정되지 않았고, 지정된 도메인의 정책에 따라, 시스템에서 DMARC 작업을 적용하지 않도록 임의로 결정했음을 의미합니다.</li><li>**pct.reject**: DMARC를 통과하지 못하는 메시지 중 100% 미만의 백분율이 전달됨을 나타냅니다. 즉, 메시지가 DMARC에 실패하고 정책이 거부로 설정되어 있지만, pct 필드는 100%로 설정되지 않았고, 지정된 도메인의 정책에 따라, 시스템에서 DMARC 작업을 적용하지 않도록 임의로 결정했음을 나타냅니다.</li><li>**permerror**: DMARC 평가 중에 영구적 오류(예: DNS에서 잘못된 형식의 DMARC TXT 레코드 발생)가 발생했습니다. 이 메시지를 다시 보내도 결과가 달라지지 않을 수 있습니다. 대신, 이 문제를 해결하기 위해 도메인 소유자에게 문의해야 합니다.</li><li>**temperror**: DMARC 평가 중에 일시적인 오류가 발생했습니다. 전자 메일을 제대로 처리할 수 있도록 보낸 사람이 메시지를 나중에 다시 보내도록 요청할 수 있습니다.</li></ul>|
|`compauth`|복합 인증 결과입니다. Microsoft 365에서 SPF, DKIM, DMARC 또는 메시지의 기타 부분과 같은 다양한 유형의 인증을 결합하여 메시지의 인증 여부를 확인하는 데 사용됩니다. 평가 기준으로 보낸 사람: 도메인을 사용합니다.|
|`dkim`|메시지의 DKIM 검사 결과를 설명합니다. 가능한 값은 다음과 같습니다. <ul><li>**통과**: 통과한 메시지의 DKIM 검사를 나타냅니다.</li><li>**실패(원인)**: 실패한 메시지의 DKIM 검사와 오류를 나타냅니다. 예를 들어, 메시지에 서명이 없거나 서명이 확인되지 않은 경우입니다.</li><li>**없음**: 메시지에 서명이 없음을 나타냅니다. 이는 도메인에 DKIM 레코드가 있거나 DKIM 레코드가 결과에 대해 평가되지 않음을 의미하지 않으며, 이 메시지에 서명이 없음을 나타냅니다.</li></ul>|
|`dmarc`|메시지의 MARC 검사 결과를 설명합니다. 가능한 값은 다음과 같습니다. <ul><li>**통과**: 메시지에 대한 DMARC 에 통과했음을 나타냅니다.</li><li>**실패**: 메시지에 대한 DMARC 검사에 실패했음을 나타냅니다.</li><li>**bestguesspass**: 도메인의 DMARC TXT 레코드가 없음을 나타내며, 이미 존재하는 경우에는 해당 메시지에 대한 DMARC 검사를 통과했음을 나타냅니다.</li><li>**없음**: DNS에 송신 도메인에 대한 DMARC TXT 레코드가 존재하지 않음을 나타냅니다.|
|`header.d`|해당하는 경우, DKIM 서명에서 식별된 도메인입니다. 이는 공개 키에 대해 쿼리된 도메인입니다.|
|`header.from`|전자 메일 메시지 헤더에 있는 `5322.From` 주소(보낸 사람 주소 또는 P2 보낸 사람이라고도 함)의 도메인입니다. 받는 사람은 전자 메일 클라이언트에서 보낸 사람 주소를 봅니다.|
|`reason`|복합 인증을 통과 또는 실패한 이유입니다. 값은 3 자리 코드입니다. 예시: <ul><li>**000**: 메시지가 인증에 명시적으로 실패했습니다(`compauth=fail`). 예를 들어, 메시지가 격리 또는 거부 조치와 함께 DMARC 실패를 수신한 경우입니다.</li><li>**001**: 메시지가 인증에 암시적으로 실패했습니다(`compauth=fail`). 이는 보내는 도메인에 전자 메일 인증 레코드가 게시되지 않았거나 인증 레코드가 경우에는 실패 정책이 약함(SPF 일시적인 실패 또는 중립, `p=none`인 DMARC 정책)을 의미합니다.</li><li>**002**: 보낸 사람/도메인 쌍에 대해 스푸핑된 전자 메일을 보내는 것을 명시적으로 금지하는 정책을 가지고 있음을 의미합니다. 이 설정은 관리자가 수동으로 설정합니다.</li><li>**010**: 메시지가 거부 또는 격리 작업과 함께 DMARC에서 실패했음을 의미하며 전송 도메인은 조직에서 허용하는 도메인 중 하나입니다(이는 자체 대 자체 또는 내부 조직, 스푸핑의 일부).</li><li>**1xx** 또는 **7xx**: 메시지가 인증을 통과했습니다(`compauth=pass`). 마지막 두 자리는 Microsoft 365에서 사용하는 내부 코드입니다.</li><li>**2xx**: 메시지가 암시적 인증을 소프트 패스했습니다(`compauth=softpass`). 마지막 두 자리는 Microsoft 365에서 사용하는 내부 코드입니다.</li><li>**3xx**: 복합 인증에 대해 메시지를 확인하지 않았습니다(`compauth=none`).</li><li>**4xx** 또는 **9xx**: 메시지에서 복합 인증을 바이패스했습니다(`compauth=none`). 마지막 두 자리는 Microsoft 365에서 사용하는 내부 코드입니다.</li><li>**6xx**: 메시지가 암시적 전자 메일 인증에 실패했고 전송 도메인은 조직에서 허용하는 도메인 중 하나입니다(이는 자체 대 자체 또는 내부 조직, 스푸핑의 일부).</li></ul>|
|`smtp.mailfrom`|`5321.MailFrom` 주소(메일 보낸 사람 주소, P1 보낸 사람 또는 봉투 보낸 사람이라고도 함)의 도메인입니다. 배달 못 함 보고서(NDR 또는 반송 메시지라고도 함)에 사용되는 전자 메일 주소입니다.|
|`spf`|메시지에 대한 SPF 검사 결과를 설명합니다. 가능한 값은 다음과 같습니다. <ul><li>`pass (IP address)`: 전달된 메시지에 대한 SPF 검사에는 보낸 사람의 IP 주소가 포함됩니다. 클라이언트는 보낸 사람의 도메인을 대신하여 전자 메일을 보내거나 릴레이할 수 있습니다.</li><li>`fail (IP address)`: 메시지에 대한 SPF 검사가 실패했으며 보낸 사람의 IP 주소를 포함합니다. 이를 종종 _하드 실패_ 라고 합니다.</li><li>`softfail (reason)`: SPF 레코드에서 호스트가 전송이 허용되지 않는 것으로 지정되었지만 전환 중입니다.</li><li>`neutral`: SPF 레코드에는 IP 주소의 전송 권한이 있는지 여부를 주장하지 않는다는 내용이 명시되어 있습니다.</li><li>`none`: 도메인에 SPF 레코드가 없거나 SPF 레코드가 결과로 평가되지 않습니다.</li><li>`temperror`: 일시적인 오류가 발생했습니다. 예를 들어 DNS 오류입니다. 나중에 동일한 검사가 성공할 수 있습니다.</li><li>`permerror`: 영구 오류가 발생했습니다. 예를 들어, 도메인에 잘못된 형식의 SPF 레코드가 있습니다.</li></ul>|
|
