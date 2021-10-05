---
title: DMARC를 사용하여 전자 메일, 설정 단계의 유효성 검사
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/10/2021
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 사용자의 조직에서 보낸 메시지의 유효성을 검사하기 위해 도메인 기반 메시지 인증, 보고 및 적합성(DMARC)을 구성하는 방법에 대해 알아봅니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 68a3f9bc2b7752ee59c040ebaca54e58008479e9
ms.sourcegitcommit: d1eb1c26609146ff5a59b2a1b005dd7ac43ae64e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/05/2021
ms.locfileid: "60099749"
---
# <a name="use-dmarc-to-validate-email"></a>DMARC를 사용하여 전자 메일의 유효성 검사

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

도메인 기반 메시지 인증, 보고 및 적합성 ([DMARC](https://dmarc.org))은 SPF (Sender Policy Framework) 및 DKIM (DomainKeys Identified Mail)과 함께 작동하여 메일 발신자를 인증하고 대상 전자 메일 시스템이 사용자의 도메인에서 보낸 메시지를 신뢰하도록 합니다. SPF 및 DKIM과 함께 DMARC를 구현하면 스푸핑 및 피싱 전자 메일에 대한 추가 보호 기능이 제공됩니다. DMARC는 수신 메일 시스템이 사용자의 도메인에서 보낸 SPF 또는 DKIM 확인에 실패한 메시지에 대해 수행할 작업을 결정하는 데 도움을 줍니다.

> [!TIP]
> [MISA(Microsoft 지능형 보안 연합)](https://www.microsoft.com/misapartnercatalog) 카탈로그를 방문하여 Microsoft 365에 대해 DMARC 보고를 제공하는 타사 공급 업체를 확인하세요.

## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-microsoft-365"></a>SPF와 DMARC는 Microsoft 365에서 전자 메일을 보호하기 위해 어떻게 함께 작동하나요?

 전자 메일 메시지에는 여러 작성자, 발신자 또는 주소가 포함될 수 있습니다. 이러한 주소는 다양한 목적으로 사용할 수 있습니다. 예를 들어 다음 주소를 살펴보겠습니다.

- **"Mail From" 주소**: 발신자를 식별하고 배달 못 함 알림과 같은 메시지의 배달에 문제가 발생할 경우 반송 알림을 보낼 위치를 지정합니다. 전자 메일 메시지의 봉투 부분에 표시되며 일반적으로 전자 메일 응용 프로그램에는 표시되지 않습니다. 5321.MailFrom 주소 또는 역-경로 주소라고도 합니다.

- **"From" 주소**: 메일 응용 프로그램에서 발신자 주소로 표시되는 주소입니다. 이 주소는 전자 메일의 작성자를 식별합니다. 즉, 메시지 작성을 담당하는 개인 또는 시스템의 사서함입니다. 이를 5322.From이라고도 합니다.

SPF는 DNS TXT 레코드를 사용하여 지정된 도메인에 대해 인증된 전송 IP 주소 목록을 제공합니다. 일반적으로 SPF 검사는 5321.MailFrom 주소에 대해서만 수행됩니다. 즉, SPF를 단독으로 사용하는 경우 5322.From 주소가 인증되지 않습니다. 이를 통해 SPF 검사를 통과했지만 스푸핑된 5322.From 발신자 주소를 가지고 있는 메시지를 사용자가 받을 수 있게 되는 시나리오가 가능합니다. 예를 들어 다음 SMTP 내용을 살펴봅니다.

```console
S: Helo woodgrovebank.com
S: Mail from: phish@phishing.contoso.com
S: Rcpt to: astobes@tailspintoys.com
S: data
S: To: "Andrew Stobes" <astobes@tailspintoys.com>
S: From: "Woodgrove Bank Security" <security@woodgrovebank.com>
S: Subject: Woodgrove Bank - Action required
S:
S: Greetings User,
S:
S: We need to verify your banking details.
S: Please click the following link to verify that we have the right information for your account.
S:
S: https://short.url/woodgrovebank/updateaccount/12-121.aspx
S:
S: Thank you,
S: Woodgrove Bank
S: .
```

이 내용에서 발신자 주소는 다음과 같습니다.

- Mail from 주소 (5321.MailFrom): phish@phishing.contoso.com

- From 주소 (5322.From): security@woodgrovebank.com

SPF를 구성한 경우 수신 서버는 Mail from 주소인 phish@phishing.contoso.com에 대해 검사를 수행합니다. 메시지가 도메인 phishing.contoso.com의 유효한 출처에서 온 경우 SPF 검사를 통과합니다. 전자 메일 클라이언트는 From 주소만 표시하므로 사용자에게 이 메시지는 security@woodgrovebank.com에서 온 것으로 보입니다. SPF 단독으로는 woodgrovebank.com의 유효성이 인증되지 않았습니다.

DMARC를 사용하는 경우 수신 서버는 From 주소에 대해서도 확인합니다. 위의 예제에서 woodgrovebank.com에 대한 DMARC TXT 레코드가 있는 경우 From 주소의 검사는 실패합니다.

## <a name="what-is-a-dmarc-txt-record"></a>DMARC TXT 레코드란 무엇인가요?

SPF의 DNS 레코드와 마찬가지로 DMARC의 레코드는 스푸핑 및 피싱을 방지하는 데 도움이 되는 DNS 텍스트 (TXT) 레코드입니다. DMARC TXT 레코드를 DNS에 게시합니다. DMARC TXT 레코드는 전자 메일을 보내는 도메인의 알려진 소유자와 대조하여 전자 메일 작성자의 IP 주소를 확인함으로써 전자 메일 메시지의 출처에 대한 유효성을 검사합니다. DMARC TXT 레코드는 인증된 아웃바운드 전자 메일 서버를 식별합니다. 그런 다음 대상 전자 메일 시스템은 수신한 메시지가 인증된 아웃바운드 전자 메일 서버에서 보낸 것인지 확인할 수 있습니다.

Microsoft의 DMARC TXT 레코드는 다음과 같습니다.

```console
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1"
```

Microsoft는 자사의 DMARC 보고서를 타사인 [Agari](https://agari.com)에게 보냅니다. Agari는 DMARC 보고서를 수집하고 분석합니다. [MISA 카탈로그](https://www.microsoft.com/misapartnercatalog)에 방문하여 Microsoft 365에 대해 DMARC 보고를 제공하는 타사 공급 업체를 확인하세요.

## <a name="set-up-dmarc-for-inbound-mail"></a>인바운드 메일에 대해 DMARC 설정

Microsoft 365에서 받는 메일에 대해 DMARC를 설정하지 않아도 됩니다. Microsoft가 사용자를 위해 모든 것을 담당합니다. DMARC 검사를 통과하지 못한 메일에 대해 알아보려면 [Microsoft 365에서 DMARC에 실패한 인바운드 전자 메일을 처리하는 방법](#how-microsoft-365-handles-inbound-email-that-fails-dmarc)을 참조하세요.

## <a name="set-up-dmarc-for-outbound-mail-from-microsoft-365"></a>Microsoft 365에서 아웃바운드 메일에 대해 DMARC 설정

Microsoft 365를 사용하지만 사용자 지정 도메인을 사용하지 않는 경우(즉, onmicrosoft.com을 사용하는 경우), 사용자 조직의 DMARC를 구성하거나 구현하기 위해 다른 작업을 수행할 필요가 없습니다. SPF는 이미 설정되어 있으며 Microsoft 365는 보내는 메일에 대해 DKIM 서명을 자동으로 생성합니다. 이 서명에 대한 자세한 내용은 [DKIM 및 Microsoft 365의 기본 동작](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)을 참조하세요.

 사용자 지정 도메인이 있거나 Microsoft 365 외에 온-프레미스 Exchange 서버를 사용하는 경우 아웃바운드 메일에 대해 DMARC를 수동으로 구현해야 합니다. 사용자 지정 도메인에 대한 DMARC 구현에는 다음 단계가 포함됩니다.

- [1단계: 사용자 도메인의 유효한 메일 출처 식별](#step-1-identify-valid-sources-of-mail-for-your-domain)

- [2단계: 사용자 도메인에 대한 SPF 설정하기](#step-2-set-up-spf-for-your-domain)

- [3단계: 사용자 지정 도메인에 대한 DKIM 설정하기](#step-3-set-up-dkim-for-your-custom-domain)

- [4단계: 사용자 도메인에 대한 DMARC TXT 레코드 형성하기](#step-4-form-the-dmarc-txt-record-for-your-domain)

### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a>1단계: 사용자 도메인의 유효한 메일 출처 식별

이미 SPF를 설정한 경우 이 작업은 이미 진행한 것입니다. 그러나 DMARC의 경우 추가 고려 사항이 있습니다. 사용자 도메인의 메일 출처를 식별할 때 두 가지 질문에 답해야 합니다.

- 내 도메인에서 메시지를 보내는 IP 주소는 무엇인가요?

- 나를 대신하여 제3자가 보낸 메일의 경우 5321.MailFrom과 5322.From 도메인이 일치하나요?

### <a name="step-2-set-up-spf-for-your-domain"></a>2단계: 사용자 도메인에 대한 SPF 설정하기

이제 유효한 모든 발신자 목록이 있으므로 [스푸핑을 방지할 수 있도록 SPF 설정하기](set-up-spf-in-office-365-to-help-prevent-spoofing.md) 단계를 수행할 수 있습니다.

예를 들어 contoso.com이 Exchange Online에서 메일을 보낸다고 가정하면, IP 주소가 192.168.0.1인 온-프레미스 Exchange 서버와 IP 주소가 192.168.100.100인 웹 응용 프로그램의 경우 SPF TXT 레코드는 다음과 같습니다.

```console
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

모범 실무로서 SPF TXT 레코드에 제3자 발신자에 대한 고려를 해야합니다.

### <a name="step-3-set-up-dkim-for-your-custom-domain"></a>3단계: 사용자 지정 도메인에 대한 DKIM 설정하기

SPF 설정을 마쳤으면 DKIM을 설정해야 합니다. DKIM을 사용하면 메시지 머리글에 있는 전자 메일 메시지에 디지털 서명을 첨부할 수 있습니다. DKIM을 설정하지 않고 대신 Microsoft 365에서 도메인의 기본 DKIM 구성을 사용하도록 허용하는 경우 DMARC가 실패할 수 있습니다. 이는 기본 DKIM 구성은 사용자 지정 도메인이 아닌 초기 onmicrosoft.com 도메인을 5322.From 주소로 사용하기 때문입니다. 이렇게 하면 사용자 도메인에서 보낸 모든 전자 메일의 5321.MailFrom과 5322.From 주소가 일치하지 않습니다.

사용자를 대신하여 메일을 발송하는 제3자 발신자가 있고 발신한 메일이 5321.MailFrom 및 5322.From 주소와 일치하지 않으면 해당 이메일에 대해 DMARC가 실패합니다. 이를 방지하려면 해당 제3자 발신자와 함께 사용자 도메인에 DKIM을 설정해야 합니다. 이를 통해 Microsoft 365는 이 제3자 서비스의 전자 메일을 인증할 수 있습니다. 그러나 이는 또한 Yahoo, Gmail 및 Comcast와 같은 곳에서 메일을 수신할 때 제3자가 보낸 전자 메일이 마치 사용자가 보낸 전자 메일로 확인하도록 할 수 있습니다. 이 기능은 고객의 사서함 위치에 관계없이 고객이 사용자 도메인에 대한 신뢰를 구축할 수 있게 해주며 동시에 Microsoft 365는 사용자 도메인의 인증 확인을 통과하기 때문에 스푸핑으로 인해 메시지를 스팸으로 표시하지 않는 이점이 있습니다.

사용자 도메인을 스푸핑할 수 있도록 제3자 발신자에 대해 DKIM을 설정하는 방법을 포함하여 도메인에 DKIM을 설정하는 방법에 대한 지침은 [DKIM을 사용하여 사용자 지정 도메인에서 전송한 아웃바운드 전자 메일의 유효성을 검사](use-dkim-to-validate-outbound-email.md)를 참조하세요.

### <a name="step-4-form-the-dmarc-txt-record-for-your-domain"></a>4단계: 사용자 도메인에 대한 DMARC TXT 레코드 형성

여기에 언급되지 않은 다른 구문 옵션도 있지만 이 옵션이 Microsoft 365에 가장 일반적으로 사용됩니다. 사용자 도메인의 DMARC TXT 레코드를 다음 형식으로 구성합니다.

```console
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; p=policy; pct=100"
```

여기서 각 부분이 나타내는 의미는 다음과 같습니다.

- *도메인* 은 사용자가 보호할 도메인입니다. 기본적으로 레코드는 도메인 및 모든 하위 도메인의 메일을 보호합니다. 예를 들어 \_dmarc.contoso.com을 지정하면 DMARC는 housewares.contoso.com 또는 plumbing.contoso.com과 같은 도메인 및 모든 하위 도메인에서 메일을 보호합니다.

- *TTL* 은 항상 1시간과 같아야 합니다. TTL에 사용되는 단위 (시간 (1시간), 분 (60분) 또는 초 (3,600초))는 도메인의 등록 기관에 따라 다릅니다.

- *pct = 100* 은 이 규칙을 전자 메일의 100%에 사용해야 함을 나타냅니다.

- *정책* 은 DMARC가 실패하는 경우 수신 서버에서 어떤 정책을 따를 것인지를 지정합니다. 정책을 없음, 격리 또는 거부로 설정할 수 있습니다.

사용할 옵션에 대한 자세한 내용은 [Microsoft 365에서 DMARC를 구현하기 위한 모범 사례](#best-practices-for-implementing-dmarc-in-microsoft-365)의 개념을 숙지하세요.

예제:

- 정책을 없음으로 설정

    ```console
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- 정책을 격리로 설정

    ```console
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- 정책을 거부로 설정

    ```console
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

레코드를 구성한 후에는 도메인 등록 기관에서 레코드를 업데이트해야 합니다.

## <a name="dmarc-mail-public-preview-feature"></a>DMARC 메일(공개 미리 보기 기능)
> [!CAUTION]
> 매일 메일을 보내지 않을 수 있으며 공개 미리 보기 중에 보고서 자체가 변경될 수 있습니다.  DMARC 집계 보고서 전자 메일은 소비자 계정(예: hotmail.com, outlook.com 또는 live.com 계정)에서 예상할 수 있습니다.

이 DMARC TXT 레코드 **_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1"** 예제에서, 이 경우에는 타사인 Agari가 처리한 *rua* 주소를 확인할 수 있습니다. 이 주소는 분석을 위해 '집계 피드백'을 보내는 데 사용되며 보고서를 생성하는 데 사용됩니다.

> [!TIP]
> [MISA 카탈로그](https://www.microsoft.com/misapartnercatalog)에 방문하여 Microsoft 365에 대해 DMARC 보고를 제공하는 타사 공급 업체를 확인하세요. DMARC 'rua' 주소에 대한 자세한 내용은 [ IETF.org의 '도메인 기반 메시지 인증, 보고 및 적합성(DMARC)'](https://datatracker.ietf.org/doc/html/rfc7489)을 참조하세요.

## <a name="best-practices-for-implementing-dmarc-in-microsoft-365"></a>Microsoft 365에서 DMARC를 구현하기 위한 모범 사례

나머지 메일 흐름에 영향을 주지 않고 DMARC를 점진적으로 구현할 수 있습니다. 이 단계를 따르는 롤아웃 계획을 만들고 구현합니다. 아래 단계를 진행하기 전에 먼저 하위 도메인, 다른 하위 도메인을 차례로 수행하고, 마지막으로 사용자 조직의 최상위 도메인을 수행합니다.

1. DMARC 구현의 영향 모니터링

    DMARC 수신자가 해당 도메인을 사용하여 볼 수 있는 메시지에 대한 통계를 사용자에게 보내도록 요청하는 하위 도메인 또는 도메인에 대한 간단한 모니터링 모드 레코드를 사용하여 시작합니다. 모니터링 모드 레코드는 정책이 none (p=none)으로 설정된 DMARC TXT 레코드입니다. 많은 회사에서는 더욱 제한적인 DMARC 정책을 게시했을 때 손실이 발생할 수 있는 이메일 양을 정확히 알 수 없기 때문에 p=none으로 DMARC TXT 레코드를 게시합니다.

    메시징 인프라에서 SPF 또는 DKIM을 구현하기 전에도 이 작업을 수행할 수 있습니다. 그러나 SPF 및 DKIM을 구현할 때까지는 DMARC를 사용하여 메일을 효과적으로 격리하거나 거부할 수 없습니다. SPF 및 DKIM을 도입하면서 DMARC를 통해 생성된 보고서에는 이러한 검사를 통과한 메시지 수와 출처를 제공하고 그렇지 않은 메시지에 대해서도 이를 제공합니다. 이를 통해 다루어지는 정상/비정상적인 트래픽의 양을 쉽게 파악하고 이에 따른 문제를 해결할 수 있습니다. 또한 얼마나 많은 사기성 메시지가 전송되는지, 어디로부터 전송되는지 확인할 수 있습니다.

2. DMARC 실패한 메일을 외부 메일 시스템에서 격리하도록 요청

    정상적인 트래픽의 전부 또는 대부분이 SPF 및 DKIM에 의해 보호된다는 것을 믿고 DMARC 구현이 미치는 영향을 이해하고 있는 경우에는 격리 정책을 구현할 수 있습니다. 격리 정책은 정책이 격리 (p=quarantine)으로 설정된 DMARC TXT 레코드입니다. 이렇게 하면 DMARC 수신자에게 DMARC 검사에 실패한 사용자 도메인의 메시지를 사용자 고객의 받은 편지함 대신 스팸 폴더의 로컬과 같은 곳에 메시지를 넣도록 요청합니다.

3. 외부 메일 시스템이 DMARC에 실패한 메시지를 허용하지 않도록 요청

    마지막 단계는 거부 정책을 구현하는 것입니다. 거부 정책은 정책이 거부 (p=reject)로 설정된 DMARC TXT 레코드입니다. 이렇게 하면 DMARC 수신자에게 DMARC 검사에 실패한 메시지를 수락하지 않도록 요청합니다.

4. 하위 도메인에 대해 DMARC를 설정하는 방법은 무엇입니까?

   DMARC는 정책을 DNS에 TXT 레코드로 게시하여 구현되며 계층적입니다(예: contoso.com에 대해 게시된 정책은 하위 도메인에 대해 명시적으로 다른 정책이 정의되지 않는 한 sub.domain.contonos.com에 적용됩니다). 이 기능은 조직에서 상위 DMARC 레코드를 더 적은 수로 지정하여 더 넓은 범위를 제공할 수 있기 때문에 유용합니다. 하위 도메인이 최상위 도메인의 DMARC 레코드를 상속하지 않도록 하려면 주의해야 합니다.

   또한 하위 도메인이 전자 메일을 보내지 않아야 할 때 `sp=reject` 값을 추가하여 DMARC에 와일드카드 유형 정책을 추가할 수 있습니다. 예를 들면 다음과 같습니다.

   ```text
   _dmarc.contoso.com. TXT "v=DMARC1; p=reject; sp=reject; ruf=mailto:authfail@contoso.com; rua=mailto:aggrep@contoso.com"
   ```

## <a name="how-microsoft-365-handles-outbound-email-that-fails-dmarc"></a>Microsoft 365가 DMARC에 실패한 아웃바운드 전자 메일을 처리하는 방법

메시지가 Microsoft 365에서 아웃바운드되고 DMARC에 실패하고 정책을 p=quarantne 또는 p=reject로 설정한 경우 메시지는 [아웃바운드 메시지용 높은 위험 배달 풀](high-risk-delivery-pool-for-outbound-messages.md)로 라우팅됩니다. 아웃바운드 전자 메일에 대한 재정의는 없습니다.

DMARC 거부 정책(p=reject)을 게시하면 서비스를 통해 아웃바운드 메시지를 릴레이할 때 메시지가 사용자 도메인에 대해 SPF 또는 DKIM을 통과할 수 없으므로 Microsoft 365의 다른 고객이 사용자 도메인을 스푸핑할 수 없습니다. 그러나 DMARC 거부 정책을 게시했지만 Microsoft 365를 통해 모든 전자 메일을 인증하지 않았다면 일부 전자 메일이 인바운드 전자 메일에 대한 스팸으로 표시되거나(위에 설명된 것처럼) SPF를 게시하지 않고 서비스를 통해 아웃바운드 릴레이하려고 시도하면 거부됩니다. 예를 들어, DMARC TXT 레코드를 형성할 때 사용자 도메인을 대신하여 메일을 보내는 서버 및 앱의 일부 IP 주소를 포함하지 않은 경우에 발생합니다.

## <a name="how-microsoft-365-handles-inbound-email-that-fails-dmarc"></a>Microsoft 365가 DMARC에 실패한 인바운드 전자 메일을 처리하는 방법

발신 서버의 DMARC 정책이 `p=reject`이면 [EOP](exchange-online-protection-overview.md)(Exchange Online 방지)는 메시지를 거부하는 대신 스푸핑으로 표시합니다. 즉, 인바운드 전자 메일의 경우 Microsoft 365는 `p=reject` 및 `p=quarantine`을 동일한 방식으로 처리합니다. 관리자는 [피싱 방지 정책](set-up-anti-phishing-policies.md)에서 스푸핑으로 분류된 메시지에 대해 수행할 작업을 정의할 수 있습니다.

일부 정상적인 전자 메일이 DMARC 검사에 실패할 수 있으므로 Microsoft 365는 이와 같이 구성됩니다. 예를 들어, 메일 그룹에 전송된 메시지가 모든 목록 참가자에게 릴레이되는 경우 DMARC 검사에 실패할 수 있습니다. Microsoft 365에서 이러한 메시지를 거부하는 경우 사용자가 정상적인 전자 메일을 잃을 수 있으며 이를 되찾을 방법이 없습니다. 대신 이러한 메시지는 여전히 DMARC 검사에 실패하지만 스팸으로 표시되고 거부되지는 않습니다. 원하는 경우 사용자는 다음 방법을 통해 받은 편지함에서 이러한 메시지를 계속 받을 수 있습니다.

- 사용자가 전자 메일 클라이언트를 사용하여 개별적으로 수신 허용 - 보낸 사람을 추가합니다.

- 관리자는 [스푸핑 인텔리전스 인사이트](learn-about-spoof-intelligence.md) 또는 [테넌트 허용/차단 목록](tenant-allow-block-list.md)을 사용하여 스푸핑된 발신자의 메시지를 허용할 수 있습니다.

- 관리자는 특정 보낸 사람의 메시지를 허용하는 모든 사용자에 대해 Exchange 메일 흐름 규칙 (전송 규칙이라고도 함)을 만듭니다.

자세한 내용은 [수신 허용 - 보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조하세요.

## <a name="how-microsoft-365-utilizes-authenticated-received-chain-arc"></a>Microsoft 365가 ARC(Authenticated Received Chain)를 활용하는 방법

이제 Microsoft 365에서 호스팅되는 모든 사서함에는 메시지 배달 기능과 스푸핑 방지 기능이 향상되는 ARC의 이점을 갖게 됩니다. ARC는 원래 서버에서 받는 사람 사서함으로 전자 메일이 라우팅될 때 모든 참여 중개자, 홉의 전자 메일 인증 결과를 보존합니다. ARC 이전에는 전달 규칙이나 자동 서명을 비롯한 전자 메일 라우팅의 중개자가 수행한 수정으로 전자 메일이 받는 사람의 사서함에 도달했을 때 DMARC 오류가 발생할 수 있었습니다. ARC를 사용하여 인증 결과에 대한 암호화를 보존하면 Microsoft 365에서 전자 메일을 보낸 사람의 신뢰성을 확인할 수 있습니다.

Microsoft 365는 현재 ARC를 사용하여 Microsoft가 ARC Sealer인 경우 인증 결과를 확인하지만, 향후 타사 ARC Sealer에 대한 지원을 추가할 계획입니다.

## <a name="troubleshooting-your-dmarc-implementation"></a>DMARC 구현 문제 해결

EOP가 첫 번째 항목이 아닌 사용자 도메인의 MX 레코드를 구성한 경우 사용자 도메인에 대해 DMARC 검사 실패가 발생하지 않습니다.

사용자가 고객이고 도메인의 기본 MX 레코드가 EOP를 가리키지 않는 경우에는 DMARC의 이점을 얻을 수 없습니다. 예를 들어 MX 레코드를 온-프레미스 메일 서버로 지정한 다음 커넥터를 사용하여 전자 메일을 EOP로 경로 지정하는 경우에는 DMARC가 작동하지 않습니다. 이 시나리오에서 수신 도메인은 사용자의 허용된 도메인 중 하나이고 EOP는 기본 MX가 아닙니다. 예를 들어 contoso.com이 MX를 자체적으로 가리키고 EOP를 보조 MX 레코드로 사용한다고 가정하면 contoso.com의 MX 레코드는 다음과 같습니다.

```console
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

모든 또는 대부분의 전자 메일은 기본 MX인 mail.contoso.com으로 먼저 경로 지정된 다음, 메일은 EOP로 경로 지정됩니다. 경우에 따라 EOP를 MX 레코드로 전혀 나열하지 않고 단순히 커넥터를 연결하여 전자 메일을 경로 지정할 수도 있습니다. DMARC 유효성 검사를 수행하기 위해 EOP가 첫 번째 항목일 필요는 없습니다. 모든 온-프레미스/비O365 서버가 DMARC 검사를 수행할 것이라고 확신할 수 없기 때문에 이는 유효성 검사만을 보장합니다.  DMARC TXT 레코드를 설정할 때 DMARC는 고객의 도메인 (서버가 아님)에 대해 수행될 수 있지만, 실제로 수행을 적용하는 것은 수신 서버에 달려 있습니다.  수신 서버로 EOP를 설정하면 EOP가 DMARC 검사를 수행합니다.

:::image type="content" source="../../media/Tp_DMARCTroublehoot.png" alt-text="DMARC에 대한 문제 해결 그래픽, Daniel Mande 제공" lightbox="../../media/Tp_DMARCTroublehoot.png":::

## <a name="for-more-information"></a>자세한 내용

DMARC에 대한 자세한 정보가 필요하신가요? 다음 리소스가 도움이 될 수 있습니다.

- [스팸 방지 메시지 헤더](anti-spam-message-headers.md)에는 Microsoft 365에서 DMARC 검사에 사용하는 구문 및 헤더 필드가 포함됩니다.

- M<sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group)의 [DMARC 교육 시리즈](https://www.m3aawg.org/activities/training/dmarc-training-series)를 이용하세요.

- [dmarcian](https://space.dmarcian.com/deployment/)의 검사 목록을 사용하세요.

- [DMARC.org](https://dmarc.org)의 출처로 바로 이동합니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365에서 SPF(Sender Policy Framework)를 사용하여 스푸핑을 방지하는 방법](how-office-365-uses-spf-to-prevent-spoofing.md)

[**스푸핑을 방지할 수 있도록 Microsoft 365에서 SPF 설정하기**](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

[**DKIM을 사용하여 Microsoft 365의 사용자 지정 도메인에서 전송한 아웃바운드 전자 메일의 유효성 검사**](use-dkim-to-validate-outbound-email.md)
