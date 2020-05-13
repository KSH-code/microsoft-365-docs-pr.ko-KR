---
title: 스팸 방지 보호 FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP (Exchange Online Protection)의 스팸 방지 보호 기능에 대 한 질문과 대답을 볼 수 있습니다.
ms.openlocfilehash: 69d9e72e3be53f0ddd5bc5771493564f364bef54
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209646"
---
# <a name="anti-spam-protection-faq"></a>스팸 방지 보호 FAQ

이 항목에서는 exchange online 사서함이 없는 Microsoft 365 조 직의 사서함과 EOP (독립 실행형 Exchange Online Protection) 조직에 대 한 맬웨어 방지 보호 기능에 대 한 질문과 대답을 제공 합니다.

격리에 대한 질문과 대답은 [격리 FAQ](quarantine-faq.md)를 참조하세요.

맬웨어 방지 보호 기능에 대 한 질문과 대답은 [맬웨어 방지 보호 FAQ](anti-malware-protection-faq-eop.md)를 참조 하세요.

스푸핑 방지 보호에 대 한 질문과 대답은 스푸핑 방지 [보호 FAQ](anti-spoofing-protection-faq.md)를 참조 하세요.

## <a name="by-default-what-happens-to-a-spam-detected-message"></a>스팸으로 검색된 메시지에 대해 기본적으로 수행되는 작업은 무엇입니까?

**인바운드 메시지의 경우:** 대부분의 스팸은 원본 전자 메일 서버의 IP 주소를 기반으로 하는 연결 필터링을 통해 삭제 됩니다. 스팸 방지 정책 (스팸 필터 정책 또는 콘텐츠 필터 정책이 라고도 함)은 메시지를 조사 하 여 스팸, 대량 또는 피싱으로 분류 합니다. 기본적으로 스팸으로 분류 된 메시지는 받는 사람의 정크 메일 폴더로 배달 되며, 피싱로 분류 된 메시지는 격리 됩니다. 모든 받는 사람에 게 적용 되는 기본 스팸 방지 정책을 수정 하거나, 특정 사용자 그룹에 대 한 보다 엄격한 설정으로 사용자 지정 스팸 방지 정책을 만들 수 있습니다 (예: 임원에 전송 된 스팸 격리 가능). 자세한 내용은 [스팸 방지 정책 구성](configure-your-spam-filter-policies.md) 및 [권장 되는 스팸 방지 정책 설정을](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)참조 하십시오.

> [!IMPORTANT]
> EOP가 온-프레미스 사서함을 보호 하는 하이브리드 배포에서는 메시지에 추가 되는 EOP 스팸 필터링 헤더를 검색 하도록 온-프레미스 Exchange 조직에서 두 가지 Exchange 메일 흐름 규칙 (전송 규칙이 라고도 함)을 구성 해야 합니다. 자세한 내용은 [하이브리드 환경에서 스팸을 정크 메일 폴더로 배달하도록 독립 실행형 EOP 구성하기](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)를 참조하세요.

 **아웃 바운드 메시지의 경우:** 메시지가 [위험성이 높은 배달 풀](high-risk-delivery-pool-for-outbound-messages.md) 을 통해 라우팅되고 있거나 배달 못 함 보고서 (NDR 또는 바운스 메시지로 알려짐)에서 보낸 사람에 게 반환 됩니다. 아웃 바운드 스팸 방지에 대 한 자세한 내용은 [아웃 바운드 스팸 제어](outbound-spam-controls.md)를 참조 하십시오.

## <a name="whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a>스팸이 0 일에 해당 하는 것은 무엇 이며, 서비스에서 처리 하는 방법은 무엇 인가요?

0 일의 스팸 변형은 첫 번째 세대 이며, 이전에는 캡처되지 않거나 분석 되지 않은 스팸의 변종 이며, 스팸 방지 필터에는 아직 해당 정보를 검색 하는 데 사용할 수 있는 정보가 없습니다. 스팸 분석가에 의해 0 일 동안의 스팸 샘플이 캡처 및 분석 된 후 스팸 분류 조건을 충족 하는 경우이를 검색 하기 위해 스팸 방지 필터를 업데이트 했으며 더 이상 "0 일"로 간주 되지 않습니다.

**참고:** 서비스를 개선 하는 데 도움이 되도록 0 일 동안의 스팸 변종 메시지를 받은 경우에는 [보고서 메시지 및 파일](report-junk-email-messages-to-microsoft.md)에 설명 된 방법 중 하나를 microsoft에 제출 하십시오.

## <a name="do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a>스팸 방지 보호 기능을 제공하도록 서비스를 구성해야 합니까?

서비스에 등록 하 고 도메인을 추가 하 고 나면 스팸 필터링이 자동으로 사용 하도록 설정 됩니다. 기본적으로 스팸 필터링은 혼합 환경의 독립 실행형 EOP 독립 실행형 고객에 대해 앞에서 설명한 예외를 제외 하 고는 추가 구성 없이도 사용자를 보호할 수 있도록 조정 됩니다. 관리자는 기본 스팸 필터링 설정을 조직의 요구에 가장 잘 맞게 편집할 수 있습니다. 세분성을 높이기 위해 조직의 지정 된 사용자, 그룹 또는 도메인에 적용 되는 스팸 방지 정책 및 아웃 바운드 스팸 방지 정책을 만들 수도 있습니다. 사용자 지정 정책은 항상 기본 정책보다 우선하지만 사용자 지정 정책의 우선 순위(즉, 실행 순서)를 변경할 수 있습니다.

자세한 내용은 다음 항목을 참조하세요.

[EOP 및 Office 365 ATP 보안에 대 한 권장 설정](recommended-settings-for-eop-and-office365-atp.md)

[EOP에서 연결 필터링 구성](configure-the-connection-filter-policy.md)

[EOP에서 스팸 방지 정책 구성](configure-your-spam-filter-policies.md)

[아웃바운드 스팸 정책 구성](configure-the-outbound-spam-policy.md)

## <a name="if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a>스팸 방지 정책을 변경하는 경우 저장한 변경 내용이 적용될 때까지 시간이 얼마나 걸립니까?

변경 내용이 적용되기까지 최대 1시간 정도 걸릴 수 있습니다.

## <a name="is-bulk-email-filtering-automatically-enabled"></a>대량 전자 메일 필터링은 자동으로 사용하도록 설정됩니까?

예. 대량 전자 메일에 대 한 자세한 내용은 [정크 메일과 대량 전자 메일의 차이점](what-s-the-difference-between-junk-email-and-bulk-email.md)을 참조 하세요.

## <a name="does-the-service-provide-url-filtering"></a>서비스에서 URL 필터링 기능을 제공합니까?

예, 서비스에 메시지 내의 url을 확인 하는 URL 필터가 있습니다. 알려진 스팸 또는 악성 콘텐츠와 관련 된 Url이 검색 되 면 메시지가 스팸으로 표시 됩니다.

## <a name="how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a>서비스를 사용하는 고객이 거짓 부정(스팸) 및 가양성(스팸 아님) 메시지를 Microsoft로 보내려면 어떻게 해야 합니까?

스팸 및 스팸이 아닌 메시지는 분석을 위해 여러 가지 방법으로 Microsoft에 제출할 수 있습니다. 자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.

## <a name="can-i-get-spam-reports"></a>스팸 보고서를 확인할 수 있습니까?

예를 들어 Microsoft 365 관리 센터에서 스팸 검색 보고서를 받을 수 있습니다. 이 보고서는 스팸 볼륨을 고유한 메시지의 수로 표시 합니다. 보고에 대한 자세한 내용은 다음 링크를 참조하십시오.

Exchange Online 고객: [Exchange online의 모니터링, 보고 및 메시지 추적](https://docs.microsoft.com/exchange/monitoring/monitoring)

독립 실행형 EOP 고객: [Exchange Online Protection의 보고 및 메시지 추적](reporting-and-message-trace-in-exchange-online-protection.md)

## <a name="someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a>다른 사용자가 메시지를 보냈지만 찾을 수 없습니다. 이는 스팸으로 검색 된 것으로 의심 됩니다. 를 확인 하는 데 사용할 수 있는 도구가 있나요?

예, 메시지 추적 도구를 사용 하면 전자 메일 메시지가 서비스를 통과 하는 대로 진행 되는 상황을 확인할 수 있습니다. 메시지 추적 도구를 사용 하 여 메시지가 스팸으로 표시 된 이유를 확인 하는 방법에 대 한 자세한 내용은 [메시지가 스팸으로 표시 되었습니까?](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam) 를 참조 하세요.

## <a name="will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a>사용자가 아웃 바운드 스팸을 보낼 때 서비스 제한 (속도 제한)은 내 메일 입니까?

특정 시간대 (예: 시간당)에서 서비스를 통해 사용자가 보낸 메일의 절반 이상이 EOP에 의해 스팸으로 확인 되 면 사용자는 메시지를 보낼 수 없게 됩니다. 대부분의 경우 아웃 바운드 메시지가 스팸으로 확인 되 면이 메시지는 높은 위험 배달 풀을 통해 라우팅되며, 일반 아웃 바운드 IP 풀이 차단 목록에 추가 될 가능성을 줄입니다.

보낸 사람이 아웃바운드 스팸을 보낼 수 없도록 차단된 경우 지정된 전자 메일 주소로 알림을 보낼 수 있습니다. 이 설정에 대 한 자세한 내용은 [아웃 바운드 스팸 정책 구성을](configure-the-outbound-spam-policy.md)참조 하십시오.

## <a name="can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a>타사 스팸 방지 및 맬웨어 방지 공급자와 Exchange Online을 함께 사용할 수 있습니까?

예. Microsoft에 대 한 MX 레코드를 가리키는 것이 좋지만 Microsoft가 아닌 다른 사람에 게 전자 메일을 라우팅하는 합법적인 비즈니스 이유가 있다는 것을 알게 되었습니다.

- **Inbound**: 타사 공급자를 가리키도록 MX 레코드를 변경한 다음 추가 처리를 위해 메시지를 EOP로 리디렉션합니다. 자세한 내용은 [Exchange Online의 커넥터에 대 한 향상 된 필터링](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)을 참조 하십시오.

- **Outbound**: Microsoft 365에서 대상 타사 공급자로의 스마트 호스트 라우팅을 구성 합니다.

## <a name="does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a>Microsoft에 피싱 메일로부터 자기 자신을 보호할 수 있는 방법에 대한 설명서가 있습니까?

예. 자세한 내용은 [인터넷에서 개인 정보 보호](https://support.microsoft.com/help/4091455) 를 참조 하세요.

## <a name="are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a>스팸 및 맬웨어 메시지의 경우 보낸 사람을 조사하거나 법 집행 기관으로 전송됩니까?

서비스는 스팸 및 맬웨어 감지 및 제거에 중점을 둔 반면, 특히 위험 하거나 스팸을 손상 하거나 캠페인을 공격 하 고 perpetrators를 추진 하는 경우가 있습니다. 이는 발신자의 botnet을 차단 하 고, 스팸 발송자가 서비스를 사용 하는 경우 (아웃 바운드 전자 메일을 보내는 데 사용 하는 경우), 범죄 법정에 대 한 정보를 법률 집행 기관에 전달 하는 법적 및 디지털 범죄를 이용 하는 것을 포함 합니다.

## <a name="what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a>메일 배달을 보장할 수 있는 가장 좋은 아웃바운드 메일 보내기 방법은 무엇입니까?

아래에 나와 있는 지침이 아웃바운드 전자 메일 메시지를 보내는 모범 사례입니다.

- **원본 전자 메일 도메인이 DNS에서 확인 해야 합니다.**

  예를 들어 보낸 사람이 user@fabrikam 되는 경우 도메인 fabrikam은 IP 주소 192.0.43.10 확인 합니다.
  
  보내는 도메인의 A 레코드와 MX 레코드가 DNS에 없으면 서비스에서는 메시지 내용이 스팸인지 여부에 관계없이 위험성이 높은 배달 풀을 통하여 해당 메시지를 라우팅합니다. 위험성이 높은 배달 풀에 대 한 자세한 내용은 [아웃 바운드 메시지에 대 한 위험성이 높은 배달 풀](high-risk-delivery-pool-for-outbound-messages.md)을 참조 하십시오.

- **아웃 바운드 메일 eserver에는 역방향 DNS (PTR) 항목이 있어야 합니다.**

  예를 들어 전자 메일 원본 IP 주소가 192.0.43.10 인 경우 역방향 DNS 항목은 `43-10.any.icann.org` 입니다. '

- **HELO/EHLO 및 MAIL FROM 명령은 일관성이 있어야 하며 IP 주소가 아닌 도메인 이름 형식으로 지정해야 합니다.**

  HELO/EHLO 명령은 보내는 IP 주소의 역방향 DNS와 일치하도록 구성해야 합니다. 그래야 메시지 헤더의 여러 부분에서 도메인이 동일하게 유지됩니다.

- **DNS에서 적절한 SPF 레코드를 설정해야 합니다.**

  SPF 레코드는 도메인에서 전송된 메일이 실제로 해당 도메인에서 보낸 것이며 스푸핑되지 않았음을 검사하는 메커니즘입니다. SPF 레코드에 대한 자세한 내용은 다음 링크를 참조하십시오.

  [스푸핑을 방지할 수 있도록 SPF 설정](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  [도메인 FAQ](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

- **DKIM으로 전자 메일에 서명을 하는 경우 낮은 수준의 정규화로 서명합니다.**

  보낸 사람은 DKIM(Domain Keys Identified Mail)을 사용하여 메시지에 서명을 하고 서비스를 통해 아웃바운드 메일을 보내려는 경우 낮은 수준의 헤더 정규화 알고리즘을 사용하여 서명해야 합니다. 엄격한 헤더 정규화를 사용하여 서명을 하면 메시지가 서비스를 통과할 때 서명이 무효화될 수 있습니다.

- **도메인 소유자는 WHOIS 데이터베이스에 정확한 정보를 포함해야 합니다.**

  이렇게 하면 고정된 모회사, 담당자 및 이름 서버를 입력함으로써 도메인 소유자 및 소유자에게 연락하는 방법을 파악할 수 있습니다.

- **대량 메일러의 경우 보낸 사람: 이름이 메시지를 보내는 사람을 반영해야 하며 메시지의 제목 줄은 메시지 내용에 대한 간략한 요약을 포함해야 합니다.**

  메시지 본문에는 제공 사항, 서비스 또는 제품이 명확하게 표시되어 있어야 합니다. 예를 들어 보낸 사람이 Contoso라는 회사를 위해 대량의 메일을 보내는 경우 전자 메일의 보낸 사람 및 제목은 다음과 같아야 합니다.

  > 보낸 사람: marketing@contoso.com <br/> 제목: 업데이트된 크리스마스 시즌용 신규 카탈로그!

  다음은 대량 메일임을 충분히 설명하지 않으므로 부적합한 메일의 예입니다.

  > 보낸 사람: user@hotmail.com <br/> 제목: 카탈로그

- **뉴스레터 형식의 메시지를 많은 수의 받는 사람에게 대량 메일로 보내는 경우에는 메시지 아래쪽에 구독을 취소할 수 있는 수단이 있어야 합니다.**

  다음과 같은 구독 취소 옵션을 포함해야 합니다.

  > 이 메시지는 sender@fabrikam.com에서 example.@contoso.com으로 전송된 것입니다. 프로필/전자 메일 주소 업데이트 | **Safeunsubscribe 취소** 를 사용한 빠른 제거 &trade; | 개인 정보 보호 정책

- **대량 전자 메일을 보내는 경우에는 이중 옵트인(opt in)을 통해 목록을 확보해야 합니다. 이중 옵트인(opt in)은 대량 메일러에 대한 업계 모범 사례입니다.**

  이중 옵트인(opt in)은 사용자가 마케팅 메일을 신청할 때 두 가지 작업을 수행하도록 요구하는 방식입니다.

  1. 먼저, 사용자는 이전에는 선택하지 않았던 확인란을 클릭하여 마케팅 업체의 서비스 또는 전자 메일 메시지를 계속 받도록 옵트인(opt in)합니다.

  2. 다음으로, 사용자가 입력한 전자 메일 주소로 마케팅 업체가 확인 전자 메일을 보내 사용자가 일정 시간 이내에 링크를 클릭하여 확인을 완료하도록 요청합니다.

  이중 옵트인(opt in)을 사용하는 경우 대량 전자 메일 보낸 사람의 신뢰도가 높아집니다.

- **대량 전자 메일 보낸 사람은 책임질 수 있는 명확한 콘텐츠를 작성해야 합니다.**

  1. 받는 사람이 보낸 사람을 주소록에 추가하도록 요청하는 장문의 메시지에서는 해당 작업을 수행해도 배달이 보장되지는 않음을 명확하게 설명해야 합니다.

  2. 메시지 본문에 리디렉션을 구성하는 경우에는 일관성 있는 링크 스타일을 사용합니다.

  3. 큰 이미지나 첨부 파일, 또는 이미지로만 구성된 메시지를 보내지 않습니다.

  4. 추적 픽셀(웹 버그 또는 탐지 장치)을 사용할 때는 공개 개인 정보 또는 P3P 설정에서 그러한 항목이 있음을 명기합니다.

- **아웃 바운드 바운스 메시지의 형식을 지정 합니다.**

  배달 상태 알림 메시지 (배달 못 함 보고서, Ndr 또는 바운스 메시지)를 생성할 때 보낸 사람은 [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt)에 지정 된 바운스 형식을 따라야 합니다.

- **존재하지 않는 사용자의 반송된 전자 메일 주소를 제거합니다.**

  전자 메일 주소가 더 이상 사용되지 않음을 나타내는 NDR을 받으면 존재하지 않는 전자 메일 별칭을 목록에서 제거합니다. 전자 메일 주소는 시간이 지남에 따라 변경되며, 주소를 삭제하는 사용자도 있습니다.

- **Hotmail의 SNDS(Smart Network Data Services) 프로그램을 사용합니다.**

  Hotmail에서는 최종 사용자가 전송한 불만 사항을 보낸 사람이 확인할 수 있도록 하는 Smart Network Data Services라는 프로그램을 사용합니다. SNDS는 Hotmail에 대한 배달 문제 해결을 위한 기본 포털입니다.
