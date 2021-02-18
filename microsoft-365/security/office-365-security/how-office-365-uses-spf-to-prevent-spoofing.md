---
title: SPF(Sender Policy Framework)가 스푸핑을 방지하는 방법
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/15/2016
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365에서 DNS의 SPF(Sender Policy Framework) TXT 레코드를 사용하여 대상 전자 메일 시스템이 사용자 지정 도메인에서 보낸 메시지를 신뢰하도록 하는 방법을 알아보습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: daf170339f4a218c404114f9c82b1d465779100d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286871"
---
# <a name="how-microsoft-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a>Microsoft 365에서 SPF(Sender Policy Framework)를 사용하여 스푸핑을 방지하는 방법

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

 **요약:** 이 문서에서는 Microsoft 365가 DNS의 SPF(Sender Policy Framework) TXT 레코드를 사용하여 대상 전자 메일 시스템이 사용자 지정 도메인에서 보낸 메시지를 신뢰하도록 하는 방법을 설명합니다. 이는 Microsoft 365에서 보낸 아웃바운드 메일에 적용됩니다. Microsoft 365에서 Microsoft 365 내의 받는 사람에게 보낸 메시지는 항상 SPF를 통과합니다.

SPF TXT 레코드는 전자 메일 메시지가 전송되는 도메인 이름을 확인하여 스푸핑 및 피싱을 방지하는 데 도움이 되는 DNS 레코드입니다. SPF는 보내는 도메인의 주장된 소유자에 대해 보낸 사람 IP 주소를 확인하여 전자 메일 메시지의 출처에 대한 유효성을 검사합니다.

> [!NOTE]
> SPF 레코드 유형은 2014년 IETF(Internet Engineering Task Force)에서 더 이상 사용이 불가능했습니다. 대신 DNS의 TXT 레코드를 사용하여 SPF 정보를 게시해야 합니다. 이 문서의 나머지에서는 명확성을 위해 SPF TXT 레코드를 사용했습니다.

도메인 관리자는 DNS의 TXT 레코드에 SPF 정보를 게시합니다. SPF 정보는 권한이 부여된 아웃바운드 전자 메일 서버를 식별합니다. 대상 전자 메일 시스템은 권한 있는 아웃바운드 전자 메일 서버에서 메시지를 보냈는지 확인합니다. 이미 SPF에 익숙하거나 간단한 배포가 있으며 Microsoft 365용 DNS의 SPF TXT 레코드에 포함할 것을 알아야 하는 경우 [Microsoft 365에서 SPF를](set-up-spf-in-office-365-to-help-prevent-spoofing.md)설정하여 스푸핑을 방지할 수 있습니다. Microsoft 365에서 완전히 호스팅되는 배포가 없는 경우 또는 SPF 작동 방식 또는 Microsoft 365 SPF 문제 해결 방법에 대한 자세한 정보를 원할 경우 계속 읽어 보아야 합니다.

> [!NOTE]
> 이전에는 SharePoint Online을 사용하는 경우 사용자 지정 도메인에 다른 SPF TXT 레코드를 추가해야 합니다. 이 작업은 더 이상 필요하지 않습니다. 이렇게 변경하면 정크 메일 폴더에 SharePoint Online 알림 메시지가 표시될 위험이 줄어 듭니다. 즉시 변경할 필요는 없지만 "너무 많은 코드 확인" 오류가 발생하는 경우 [Microsoft 365의 SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)설정에 설명된 바와 같이 SPF TXT 레코드를 수정하여 스푸핑을 방지합니다.

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-microsoft-365"></a>SpF가 Microsoft 365에서 스푸핑 및 피싱을 방지하는 방법
<a name="HowSPFWorks"> </a>

SPF는 보낸 사람이 도메인을 대신하여 보낼 수 있는지 여부를 지정합니다. 보낸 사람이 이를 허용하지 않는 경우, 즉 받는 서버에서 전자 메일이 SPF 확인에 실패하면 해당 서버에 구성된 스팸 정책에 따라 메시지로 할 작업을 결정하게 됩니다.

각 SPF TXT 레코드에는 SPF TXT 레코드로 선언, 도메인 및 도메인 대신 보낼 수 있는 외부 도메인에서 메일을 보낼 수 있는 IP 주소, 적용 규칙의 세 부분으로 구성됩니다. 유효한 SPF TXT 레코드에 세 가지가 모두 필요합니다. 이 문서에서는 SPF TXT 레코드를 구성하는 방법을 설명하고 Microsoft 365에서 서비스 사용에 대한 모범 사례를 제공합니다. DNS에 레코드를 게시하기 위해 도메인 등록 기관과 함께 작업하는 방법에 대한 링크도 제공됩니다.

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a>SPF 기본 사항: 사용자 지정 도메인에서 보낼 수 있는 IP 주소
<a name="SPFBasicsIPaddresses"> </a>

SPF 규칙의 기본 구문을 살펴보아야 합니다.

v=spf1 \<IP\>\<enforcement rule\>

예를 들어 다음 SPF 규칙이 다음과 같은 CONTOSO.COM.

v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\>\<enforcement rule\>

이 예에서 SPF 규칙은 받는 전자 메일 서버에서 다음 도메인에 대한 이러한 IP 주소의 메일만 수락할 수 contoso.com.

- IP 주소 #1

- IP 주소 #2

- IP 주소 #3

이 SPF 규칙은 받는 전자 메일 서버에서 메시지가 contoso.com IP 주소 중 하나에서 온 것이 아닌 경우 받는 서버에서 메시지에 적용 규칙을 적용해야 한다고 알 수 있습니다. 적용 규칙은 일반적으로 다음 옵션 중 하나입니다.

- **하드 실패.** 메시지 봉투에 '하드 실패'로 메시지를 표시한 다음 받는 서버의 구성된 스팸 정책을 이 유형의 메시지에 따르도록 합니다.

- **부드러운 오류가 발생했습니다.** 메시지 봉투에 'soft fail'으로 메시지를 표시합니다. 일반적으로 전자 메일 서버는 이러한 메시지를 배달하도록 구성됩니다. 대부분의 최종 사용자는 이 표시를 볼 수 없습니다.

- **중립** 아무 것도 하지 않습니다. 즉, 메시지 봉투를 표시하지 않습니다. 일반적으로 테스트 목적으로 예약되어 있으며 거의 사용되지 않습니다.

다음 예제에서는 SPF가 서로 다른 상황에서 작동하는 방법을 보여 제공합니다. 이 예에서 contoso.com 보낸 사람이고 woodgrovebank.com 받는 사람입니다.

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a>예제 1: 보낸 사람이 받는 사람으로 직접 보낸 메시지의 전자 메일 인증
<a name="spfExample1"> </a>

SPF는 보낸 사람에서 받는 사람으로의 경로가 직접적인 경우 가장 잘 작동합니다. 예를 들면 다음과 같습니다.

![서버 간에 직접 전자 메일이 전송될 때 SPF에서 전자 메일을 인증하는 방법을 보여주는 다이어그램입니다.](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

메시지가 woodgrovebank.com 경우 IP 주소가 #1 SPF TXT 레코드에 있는 경우 contoso.com SPF 확인을 통과하고 인증됩니다.

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a>예제 2: 스푸핑된 보낸 사람 주소가 SPF 검사에 실패
<a name="spfExample2"> </a>

피싱이 다음을 통해 스푸핑하는 방법을 contoso.com.

![스푸핑된 서버에서 보낸 전자 메일을 SPF에서 인증하는 방법을 보여주는 다이어그램입니다.](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

IP 주소 #12 contoso.com의 SPF TXT 레코드에 있지 않은 경우 메시지가 SPF 검사에 실패하고 수신자가 이를 스팸으로 표시하기로 선택할 수 있습니다.

### <a name="example-3-spf-and-forwarded-messages"></a>예제 3: SPF 및 전달된 메시지
<a name="spfExample3"> </a>

SPF의 한 가지 단점은 전자 메일이 전달된 경우 작동하지 않는다는 것입니다. 예를 들어 woodgrovebank.com 사용자가 모든 전자 메일을 전자 메일 계정으로 보내기 위한 전달 outlook.com 가정해 보겠습니다.

![메시지가 전달될 때 SPF에서 전자 메일을 인증할 수 없는 상황을 보여주는 다이어그램입니다.](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

메시지는 원래 woodgrovebank.com 때 SPF 확인을 통과하지만 ip outlook.com contoso.com의 SPF TXT 레코드에 #25 때문에 SPF 검사에 실패합니다. Outlook.com 메시지가 스팸으로 표시될 수 있습니다. 이 문제를 해결하려면 SPF를 DKIM 및 DMARC와 같은 다른 전자 메일 인증 방법과 함께 사용하세요.

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a>SPF 기본 사항: 도메인을 대신하여 메일을 보낼 수 있는 타사 도메인 포함
<a name="SPFBasicsIncludes"> </a>

IP 주소 외에도 도메인을 보낸 사람으로 포함하도록 SPF TXT 레코드를 구성할 수도 있습니다. 이러한 명령문은 SPF TXT 레코드에 "include" 문으로 추가됩니다. 예를 들어 contoso.com 메일 서버의 IP 주소를 모두 포함해야 하는 경우 contoso.net 서버가 소유하는 contoso.org 수 있습니다. 이를 위해 contoso.com 다음과 같은 SPF TXT 레코드를 게시합니다.

```text
v=spf1 include:contoso.net include:contoso.org -all
```

수신 서버에서 DNS에서 이 레코드를 볼 때 DNS에 대한 SPF TXT 레코드에 대한 DNS contoso.net 수행한 다음 해당 레코드에 대해 contoso.org. 레코드 내에서 contoso.net 또는 contoso.org 포함 문을 찾으면 해당 문도 따라야 합니다. 서비스 거부 공격을 방지하기 위해 단일 전자 메일 메시지에 대한 최대 DNS 쿼리 수는 10개입니다. 각 include 문은 추가 DNS 쿼리를 나타 내는 것입니다. 메시지가 10개 제한을 초과하면 SPF에 실패합니다. 메시지가 수신 서버가 구성된 방식에 따라 이 제한에 도달하면 보낸 사람이 메시지가 "너무 많은 수의 쿼리"를 생성하거나 "메시지의 최대 홉 수가 초과했습니다."라는 메시지가 표시될 수 있습니다( 이는 코드 관리 루프가 실행되고 DNS 시간 제한을 초과할 때 실행될 수 있습니다). 이러한 문제를 방지하는 방법에 대한 팁은 [문제 해결: Microsoft 365의 SPF](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)모범 사례를 참조하세요.

## <a name="requirements-for-your-spf-txt-record-and-microsoft-365"></a>SPF TXT 레코드 및 Microsoft 365에 대한 요구 사항
<a name="SPFReqsinO365"> </a>

Microsoft 365를 설정할 때 메일을 설정한 경우 Microsoft 메시징 서버를 도메인의 합법적인 메일 원본으로 식별하는 SPF TXT 레코드를 이미 만들었다는 것입니다. 이 레코드는 다음과 같습니다.

```text
v=spf1 include:spf.protection.outlook.com -all
```

완전히 호스팅된 고객인 경우, 즉 아웃바운드 메일을 보내는 온-프레미스 메일 서버가 없는 경우 Office 365에 대해 게시해야 하는 유일한 SPF TXT 레코드입니다.

하이브리드 배포가 있는 경우(즉, 일부 사서함은 Microsoft 365에 호스트되어 있으며 일부 사서함은 Microsoft 365에서 호스팅) 또는 EOP(Exchange Online Protection) 독립 실행형 고객인 경우(즉, 조직에서 EOP를 사용하여 프레미스 사서함을 보호하는 경우) 각온-프레미스 에지 메일 서버의 아웃바운드 IP 주소를 DNS의 SPF TXT 레코드에 추가해야 합니다.

## <a name="form-your-spf-txt-record-for-microsoft-365"></a>Microsoft 365에 대한 SPF TXT 레코드 작성
<a name="FormYourSPF"> </a>

이 문서의 구문 정보를 사용하여 사용자 지정 도메인에 대한 SPF TXT 레코드를 구성합니다. 여기에 언급되지 않은 다른 구문 옵션이 있습니다. 이러한 옵션은 가장 일반적으로 사용되는 옵션입니다. 레코드를 구성한 후에는 도메인 등록 기관에서 레코드를 업데이트해야 합니다.

Microsoft 365에 포함해야 하는 도메인에 대한 자세한 내용은 SPF에 필요한 외부 [DNS 레코드를 참조하세요.](../../enterprise/external-domain-name-system-records.md) 도메인 등록 [기관에](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) 대한 SPF(TXT) 레코드를 업데이트하는 단계별 지침을 사용하세요.

### <a name="spf-txt-record-syntax-for-microsoft-365"></a>Microsoft 365용 SPF TXT 레코드 구문
<a name="SPFSyntaxO365"> </a>

Microsoft 365의 일반적인 SPF TXT 레코드에는 다음 구문이 있습니다.

```text
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

예시:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

여기서 각 부분이 나타내는 의미는 다음과 같습니다.

- **v=spf1이** 필요합니다. 이렇게 하여 TXT 레코드를 SPF TXT 레코드로 정의합니다.

- **ip4는** IP 버전 4 주소를 사용 중입니다. **ip6은** IP 버전 6 주소를 사용 중입니다. IPv6 IP 주소를 사용하는 경우 이 문서의 예제에서 **ip4를** **ip6으로** 바하십시오. CIDR 표시를 사용하여 IP 주소 범위를 지정할 수도 있습니다(예: **ip4:192.168.0.1/26).**

- _IP 주소는_ SPF TXT 레코드에 추가할 IP 주소입니다. 일반적으로 이 주소는 조직에 대한 아웃바운드 메일 서버의 IP 주소입니다. 여러 아웃바운드 메일 서버를 나열할 수 있습니다. 자세한 내용은 예제: 여러 아웃바운드 아웃바운드 메일 서버 및 [Microsoft 365에 대한 SPF TXT](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365)레코드를 참조하세요.

- _도메인 이름은_ 합법적인 보낸 사람으로 추가하려는 도메인입니다. Microsoft 365에 포함해야 하는 도메인 이름 목록은 [SPF에 필요한 외부 DNS 레코드를 참조하세요.](../../enterprise/external-domain-name-system-records.md)

- 적용 규칙은 일반적으로 다음 중 하나입니다.

  - -모두

    하드 실패를 나타냅니다. 도메인에 대해 권한이 부여된 모든 IP 주소를 알고 있는 경우 SPF TXT 레코드에 나열하고 -all(하드 실패) 한정자(하드 실패)를 사용합니다. 또한 SPF만 사용하는 경우, 즉 DMARC 또는 DKIM을 사용하지 않는 경우 -all 한정자도 사용해야 합니다. 항상 이 한정자만 사용하는 것이 좋습니다.

  - ~all

    소프트 실패를 나타냅니다. 전체 IP 주소 목록이 있는지 확실하지 않은 경우 ~all(소프트 실패) 한정자(소프트 실패)를 사용해야 합니다. 또한 p=quarantine 또는 p=reject와 함께 DMARC를 사용하는 경우 ~all을 사용할 수 있습니다. 그렇지 않은 경우 -all을 사용 합니다.

  - ?all

    중립을 나타냅니다. SPF를 테스트할 때 사용됩니다. 라이브 배포에서는 이 한정자만 사용하지 않는 것이 좋습니다.

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-microsoft-365"></a>예: Microsoft 365에서 모든 메일을 보낼 때 사용할 SPF TXT 레코드
<a name="ExampleSPFNoSP"> </a>

모든 메일이 Microsoft 365에서 전송된 경우 SPF TXT 레코드에서 다음을 사용 합니다.

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-microsoft-365"></a>예: 하나의 하이브리드 시나리오에 대한 SPF TXT 레코드(하나의 Exchange Server 및 Microsoft 365)
<a name="ExampleSPFHybridOneExchangeServer"> </a>

하이브리드 환경에서는 Exchange Server 192.168.0.1의 IP 주소가 192.168.0.1인 경우 SPF 적용 규칙을 하드 실패로 설정하기 위해 SPF TXT 레코드를 다음과 같이 구성합니다.

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-microsoft-365"></a>예: 여러 아웃바운드 아웃바운드 메일 서버 및 Microsoft 365에 대한 SPF TXT 레코드
<a name="ExampleSPFMultipleMailServerO365"> </a>

여러 아웃바운드 메일 서버가 있는 경우 SPF TXT 레코드에 각 메일 서버의 IP 주소를 포함하고 각 IP 주소를 공백과 "ip4:" 문으로 구분합니다. 예시:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-microsoft-365"></a>다음 단계: Microsoft 365용 SPF 설정
<a name="SPFNextSteps"> </a>

SPF TXT 레코드를 공식화한 후 [Microsoft 365에서 SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md) 설정 단계에 따라 도메인에 추가하는 스푸핑을 방지합니다.

SPF는 스푸핑을 방지하도록 설계되어 있지만 SPF가 보호할 수 없는 스푸핑 기법이 있습니다. 이러한 것을 방지하기 위해 SPF를 설정한 후 Microsoft 365에 대해 DKIM 및 DMARC도 구성해야 합니다. 시작하려면 [DKIM을 사용하여 Microsoft 365의](use-dkim-to-validate-outbound-email.md)사용자 지정 도메인에서 보낸 아웃바운드 전자 메일의 유효성을 검사합니다. 다음으로 [DMARC를 사용하여 Microsoft 365에서 전자 메일 유효성 검사](use-dmarc-to-validate-email.md)를 참조하세요.

## <a name="troubleshooting-best-practices-for-spf-in-microsoft-365"></a>문제 해결: Microsoft 365의 SPF 모범 사례
<a name="SPFTroubleshoot"> </a>

사용자 지정 도메인에 대해 SPF TXT 레코드를 하나만 만들 수 있습니다. 여러 레코드를 만들면 라운드 로빈 상황이 발생하고 SPF가 실패합니다. 이를 방지하기 위해 각 하위 구성에 대해 별도의 레코드를 만들 수 있습니다. 예를 들어 레코드의 레코드를 하나씩 contoso.com 레코드를 하나씩 bulkmail.contoso.com.

전자 메일 메시지가 배달되기 전에 10개가 넘는 DNS 쿼리가 발생하는 경우 받는 메일 서버는 영구적인 오류(영구적 오류)로 응답하고 메시지가 SPF 확인에 실패하게 합니다. 또한 수신 서버는 다음 오류와 유사한 오류가 포함된 배달 못지 않은 보고서(NDR)로 응답할 수 있습니다.

- 메시지가 홉 수를 초과합니다.

- 메시지에 너무 많은 확인이 필요했습니다.

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-microsoft-365"></a>Microsoft 365에서 타사 도메인을 사용할 때 "너무 많은 코드 검색" 오류 방지
<a name="SPFTroubleshoot"> </a>

타사 도메인에 대한 일부 SPF TXT 레코드는 수신 서버가 많은 수의 DNS 검색을 수행하게 합니다. 예를 들어 이 쓰기를 할 때 Salesforce.com 포함 문 5개가 포함됩니다.

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

오류를 방지하기 위해 대량 전자 메일을 보내는 모든 사람이 이 목적을 위해 특별히 하위omain을 사용해야 하는 정책을 구현할 수 있습니다. 그런 다음 대량 전자 메일을 포함하는 하위 구성에 대해 다른 SPF TXT 레코드를 정의합니다.

 경우에 따라 salesforce.com 예와 같이 SPF TXT 레코드에 도메인을 사용해야 하지만 다른 경우에는 타사에서 이러한 용도로 사용할 하위 도메인을 이미 만들 수 있습니다. 예를 들어 exacttarget.com SPF TXT 레코드에 대해 사용해야 하는 하위Omain을 만들면 다음과 같습니다.

```text
cust-spf.exacttarget.com
```

SPF TXT 레코드에 타사 도메인을 포함하면 10개까지의 검색 제한이 실행되지 않도록 타사에서 사용할 도메인 또는 하위 도메인을 확인해야 합니다.

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a>현재 SPF TXT 레코드를 보고 필요한 조회 수를 확인하는 방법
<a name="SPFTroubleshoot"> </a>

nslookup을 사용하여 SPF TXT 레코드를 비롯한 DNS 레코드를 볼 수 있습니다. 또는 원하는 경우 SPF TXT 레코드의 콘텐츠를 보는 데 사용할 수 있는 다양한 무료 온라인 도구가 있습니다. SPF TXT 레코드를 보고 include 문 및 리디렉션 체인을 따라 레코드에 필요한 DNS 검색 수를 확인할 수 있습니다. 일부 온라인 도구는 이러한 수치도 계산하여 표시합니다. 이 번호를 추적하면 조직에서 보낸 메시지가 수신 서버에서 영구적인 오류(영구적 오류)를 트리거하지 못하게 하는 데 도움이 됩니다.

## <a name="for-more-information"></a>자세한 내용
<a name="SPFTroubleshoot"> </a>

SPF TXT 레코드 추가에 도움이 필요하세요? Microsoft 365의 사용자 지정 도메인과 함께 보낸 사람 정책 프레임워크 사용에 대한 자세한 내용은 모든 DNS 호스팅 공급자에서 [Microsoft 365용 DNS](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) 레코드 만들기 문서를 읽어 읽습니다. [스팸 방지 메시지](anti-spam-message-headers.md) 헤더에는 Microsoft 365 SPF 검사에 사용되는 구문과 헤더 필드가 포함되어 있습니다.
