---
title: 스푸핑을 방지할 수 있도록 SPF 설정
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365에서 사용자 지정 도메인과 함께 SPF(Sender Policy Framework)를 사용할 수 있도록 DNS(도메인 이름 서비스) 레코드를 업데이트하는 방법을 알아봅니다.
ms.openlocfilehash: ce8a982b875632ad58b34ae240c02b507c4656fe
ms.sourcegitcommit: 9546708a5506fdbadbfe2500cbf1bd1aeaec6fcb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49021064"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a>스푸핑을 방지할 수 있도록 SPF 설정

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

 **요약:** 이 문서에서는 Office 365에서 사용자 지정 도메인과 함께 SPF (Sender Policy Framework)를 사용할 수 있도록 DNS (Domain Name Service) 레코드를 업데이트하는 방법에 대해 설명합니다. SPF를 사용하여 사용자 지정 도메인에서 전송한 아웃바운드 전자 메일의 유효성 검사

사용자 지정 도메인을 사용하려면 Office 365에서는 스푸핑을 방지하는 데 도움이 되도록 SPF (Sender Policy Framework) TXT 레코드를 사용자 DNS 레코드에 추가해야 합니다. SPF는 사용자를 대신하여 메일을 보낼 수 있는 메일 서버를 식별합니다. 기본적으로 SPF는 DKIM, DMARC 및 Office 365에서 지원하는 기타 기술과 함께 스푸핑 및 피싱을 방지합니다. SPF는 사용자 지정 도메인을 대신하여 메일을 보낼 수 있는 메일 서버를 식별하기 위해 DNS에서 사용하는 TXT 레코드에 추가됩니다. 받는 사람의 메일 시스템은 SPF TXT 레코드를 참조하여 사용자 지정 도메인의 메시지가 인증된 메시징 서버에서 온 것인지 여부를 확인합니다.

예를 들어 사용자 지정 도메인 contoso.com이 Office 365를 사용한다고 가정합니다. Office 365 메시징 서버를 사용자 도메인의 정상적인 메일 서버로 나열하는 SPF TXT 레코드를 추가합니다. 수신 메시징 서버가 joe@contoso.com으로부터 메시지를 받으면 서버는 contoso.com의 SPF TXT 레코드를 조회하여 메시지가 유효한지 확인합니다. 수신 서버에서 SPF 레코드에 나열된 Office 365 메시징 서버 이외의 서버에서 받은 메시지를 발견하는 경우 수신 메일 서버에서 메시지를 스팸으로 거부하도록 선택할 수 있습니다.

또한 사용자 지정 도메인에 SPF TXT 레코드가 없는 경우 일부 수신 서버에서 메시지를 완전히 거부할 수 있습니다. 이는 수신 서버에서 메시지가 인증된 메시징 서버에서 온 것인지 확인할 수 없기 때문입니다.

사용자가 Office 365용 메일을 이미 설정한 경우 SPF TXT 레코드로 Microsoft 메시징 서버를 DNS에 이미 포함 시켰습니다. 그러나 DNS에서 SPF TXT 레코드를 업데이트해야 하는 경우가 있습니다. 예:

- 이전에는 SharePoint Online을 사용하는 경우 다른 SPF TXT 레코드를 사용자 지정 도메인에 추가해야 했습니다. 이 작업은 더 이상 필요하지 않습니다. 이렇게 변경하면 정크 메일 폴더에 SharePoint Online 알림 메시지가 표시될 위험이 줄어 듭니다. 조회 제한 10개에 도달하여 "조회 제한 초과" 및 "너무 많은 홉"과 같은 오류가 발생하는 경우 SPF TXT 레코드를 업데이트하세요.

- Office 365 및 Exchange 온-프레미스의 하이브리드 환경이 있는 경우

- DKIM 및 DMARC (권장)를 설정하려고합니다.

## <a name="updating-your-spf-txt-record-for-office-365"></a>Office 365용 SPF TXT 레코드를 업데이트합니다.

DNS에서 TXT 레코드를 업데이트하기 전에 먼저 정보를 수집하고 레코드 형식을 결정해야 합니다. 이렇게 하면 DNS 오류가 발생하지 않습니다. 지원되는 SPF 구문에 대한 자세한 내용과 고급 예제를 보려면 [SPF가 Office 365에서 스푸핑 및 피싱을 방지하는 방법](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)을 참조하세요.

다음 정보를 수집합니다.

- 사용자 정의 도메인의 현재 SPF TXT 레코드. 지침은 [Office 365 DNS 레코드를 만드는 데 필요한 정보 수집](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records)을 참조하세요.

- 모든 온-프레미스 메시징 서버의 외부 IP 주소. 예를 들어, **131.107.2.200**.

- SPF TXT 레코드에 포함해야하는 모든 제3자 도메인에 사용할 도메인 이름. 일부 대량 메일 공급자는 고객에게 사용할 하위 도메인을 설정했습니다. 예를 들어, MailChimp 회사는 **servers.mcsv.net** 을 설정했습니다.

- SPF TXT 레코드에 사용할 시행 규칙을 결정합니다. **-all** 을 권장합니다. 다른 구문 옵션에 대한 자세한 내용은 [Office 365용 SPF TXT 레코드 구문](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365)을 참조하세요.

### <a name="to-add-or-update-your-spf-txt-record"></a>SPF TXT 레코드를 추가하거나 업데이트하려면

1. 다음 표에서는 SPF 구문을 잘 알고 있어야 합니다.

   ****

   |요소|만약 다음을 사용 중이라면...|고객에게 일반적인가요?|이 항목을 추가하세요...|
   |---|---|---|---|
   |1|모든 전자 메일 시스템 (필수)|공통. 이 값으로 시작하는 모든 SPF TXT 레코드|`v=spf1`|
   |2|Exchange Online|공통|`include:spf.protection.outlook.com`|
   |3|Exchange Online 전용|공통이 아님|`ip4:23.103.224.0/19 ip4:206.191.224.0/19 ip4:40.103.0.0/16 include:spf.protection.outlook.com`|
   |4|Office 365 독일, Microsoft Cloud 독일 전용|공통이 아님|`include:spf.protection.outlook.de`|
   |5|제3자 전자 메일 시스템|공통이 아님|`include:<domain_name>`  <br/> 3자 전자 메일 시스템의 도메인이 \<domain_name\>인 경우.|
   |6|온-프레미스 메일 시스템 예를 들어 Exchange Online Protection 및 다른 메일 시스템|공통이 아님|추가 메일 시스템마다 다음 중 하나를 사용합니다. <br> `ip4:<IP_address>` <br/> `ip6:<IP_address>` <br/> `include:<domain_name>` <br/> 사용자의 도메인을 대신하여 메일을 보내는 다른 전자 메일의 IP 주소와 도메인이 \<IP_address\> 및 \<domain_name\>인 경우. |
   |7|모든 전자 메일 시스템 (필수)|공통. 이 값으로 끝나는 모든 SPF TXT 레코드|`<enforcement rule>` <br/> 다음 여러 값 중 하나일 수 있습니다. ``-모두`를 사용하는 것이 좋습니다.|
   |

2. 아직 이 작업을 수행하지 않은 경우 다음 표의 구문을 사용하여 SPF TXT 레코드를 구성합니다.

   예를 들어, Office 365에서 완전히 호스팅되는 즉, 온-프레미스 메일 서버가 없는 경우, SPF TXT 레코드에는 1, 2 및 7행이 포함되며 다음과 같이 나타납니다.

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   이것이 가장 일반적인 SPF TXT 레코드입니다. 이 레코드는 사용자의 Microsoft 데이터 센터가 미국, 유럽 (독일 포함) 또는 다른 위치에 있는지 여부에 관계없이 모든 사람에게 적용됩니다.

   그러나 Microsoft Cloud 독일의 일부인 Office 365 Germany를 구매한 경우 2행 대신 4행의 include 문을 사용해야 합니다. 예를 들어, Office 365 Germany에서 완전히 호스팅되는 즉, 온-프레미스 메일 서버가 없는 경우, SPF TXT 레코드에는 1, 4 및 7행이 포함되며 다음과 같이 나타납니다.

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   사용자가 이미 Office 365에 배포되어 있고 사용자 지정 도메인에 대한 SPF TXT 레코드를 설정했고 Office 365 Germany로 마이그레이션하는 경우에는 SPF TXT 레코드를 업데이트해야 합니다. 이렇게 하려면 `include:spf.protection.outlook.com` 를 `include:spf.protection.outlook.de`로 변경합니다.

3. SPF TXT 레코드를 구성한 후에는 DNS에서 레코드를 업데이트해야 합니다. 도메인에 대해 하나의 SPF TXT 레코드만 가질 수 있습니다. SPF TXT 레코드가 존재하는 경우 새 레코드를 추가하는 대신 기존 레코드를 업데이트해야 합니다. [Office 365용 DNS 레코드 만들기](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)로 이동한 다음 DNS 호스트에 대한 링크를 클릭합니다.

4. 사용자의 SPF TXT 레코드를 테스트 합니다.

## <a name="how-to-handle-subdomains"></a>하위 도메인을 어떻게 처리합니까?

하위 도메인은 최상위 도메인의 SPF 레코드를 상속하지 않으므로 각 하위 도메인에 대해 별도의 레코드를 만들어야 합니다.

모든 도메인 및 하위 도메인에 대해 추가 와일드카드 SPF 레코드(`*.`)가 있어야 공격자가 존재하지 않는 하위 도메인에서 보낸다고 주장하는 전자 메일을 보낼 수 없습니다. 예를 들어,

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="more-information-about-spf"></a>SPF에 대한 자세한 정보

지원되는 SPF 구문, 스푸핑, 문제 해결 및 Office 365에서 SPF를 지원하는 방법에 대한 자세한 내용과 고급 예제를 보려면 [SPF가 Office 365에서 스푸핑 및 피싱을 방지하는 방법](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)을 참조하세요.

## <a name="next-steps-after-you-set-up-spf-for-office-365"></a>다음 단계: Office 365에 대한 SPF를 설정한 후

SPF TXT 레코드에 문제가 있나요? [문제 해결: Office 365의 SPF에 대한 모범 사례](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)를 읽으세요.

 SPF는 스푸핑 차단을 돕지만 SPF가 방어할 수 없는 스푸핑 기술이 있습니다. 이 같은 기술을 차단하려면 SPF를 설치한 후에 Office 365의 DKIM 및 DMARC도 구성해야 합니다. 시작하려면 [DKIM을 사용하여 Office 365의 사용자 지정 도메인에서 보낸 아웃바운드 전자 메일의 유효성 검사](use-dkim-to-validate-outbound-email.md)를 참조하세요. 다음으로 [DMARC를 사용하여 Office 365에서 전자 메일 유효성 검사](use-dmarc-to-validate-email.md)를 참조하세요.
