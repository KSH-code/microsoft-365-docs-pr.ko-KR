---
title: Microsoft 365로 전송한 문제 해결 메일
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 전자 메일을 받은 편지함으로 보내는 문제에 대한 문제 해결 Microsoft 365 & 모범 사례를 Microsoft 365 제공합니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1e51173e589bac06fb4ca1ba92657137e77ade92
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60203810"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a>Microsoft 365로 전송한 문제 해결 메일

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)

이 문서에서는 전자 메일을 받은 편지함으로 보내려고 할 때 문제가 있는 보낸 사람에 대한 문제 해결 정보를 Microsoft 365 모범 사례를 제공합니다.

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a>IP 및 도메인의 전송 신뢰도 관리 중입니까?

EOP 필터링 기술은 다른 Microsoft 제품(예: Microsoft 365 및 기타 Microsoft 제품)에 대해 스팸 방지 보호 기능을 Exchange Server. 또한 SPF, DKIM 및 DMARC를 활용합니다. 전자 메일을 보내는 도메인이 스푸핑 및 피싱 문제를 해결할 수 있도록 하는 전자 메일 인증 기술입니다. EOP 필터링은 보내는 IP, 도메인, 인증, 목록 정확도, 불만 비율, 콘텐츠 등 다양한 요소의 영향을 미치게 됩니다. 이 중 보낸 사람 신뢰도와 전자 메일을 배달할 수 있는 능력의 주된 요인 중 하나는 정크 메일 불만 비율입니다.

## <a name="are-you-sending-email-from-new-ip-addresses"></a>새 IP 주소에서 전자 메일을 보내나요?

이전에 전자 메일을 보내는 데 사용되지 않은 IP 주소는 일반적으로 시스템에 구축된 신뢰도에 없습니다. 따라서 새 IP의 전자 메일에 배달 문제가 있을 가능성이 더 높습니다. IP가 스팸을 보내지 않는 신뢰도로 구축된 경우 EOP는 일반적으로 더 나은 전자 메일 배달 환경을 허용합니다.

기존 SPF 레코드에 따라 인증된 도메인에 대해 추가되는 새 IP는 일반적으로 도메인의 보내는 신뢰도 중 일부를 상속할 때의 추가 이점을 경험합니다. 도메인의 전송 평판이 좋은 경우 새 IP가 빠른 램프 시간을 경험할 수 있습니다. 새 IP는 볼륨, 목록 정확도 및 정크 메일 불만 비율에 따라 몇 주 이내에 완전히 증가할 것으로 예상할 수 있습니다.

## <a name="confirm-that-your-dns-is-set-up-correctly"></a>DNS가 올바르게 설정되어 있는지 확인

메일 라우팅에 필요한 MX 레코드를 포함하여 DNS 레코드를 만들고 유지 관리하는 방법에 대한 지침은 DNS 호스팅 공급자에 문의해야 합니다.

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a>라우팅할 수 없는 IP로 자신을 보급하지 않도록 합니다.

역방향 DNS 쿼리에 실패한 보낸 사람이 보낸 전자 메일을 수락하지 않을 수 있습니다. 경우에 따라 합법적인 보낸 사람이 EOP에 대한 연결을 열려고 할 때 인터넷에 라우팅할 수 없는 IP로 잘못 보급하는 경우도 있습니다. 개인(라우팅할 수 없는) 네트워킹에 예약된 IP 주소는 다음과 같습니다.

- 192.168.0.0/16(또는 192.168.0.0 - 192.168.255.255)
- 10.0.0.0/8(또는 10.0.0.0 - 10.255.255.255)
- 172.16.0.0/11(또는 172.16.0.0 - 172.31.255.255)

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a>사용자의 사용자에게 전자 메일을 보낼 때 NDR(배달되지 않은 보고서)을 Office 365

일부 배달 문제는 Microsoft에서 보낸 사람 IP 주소가 차단되거나 사용자 계정이 이전 스팸 활동으로 인해 금지된 보낸 사람으로 식별된 결과입니다. NDR을 오류로 수신했다고 생각되면 먼저 NDR 메시지의 지침을 따라 문제를 해결합니다.

받은 오류에 대한 자세한 내용은 전자 메일 배달되지 않은 보고서의 오류 코드 목록을 [Exchange Online.](/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

 예를 들어 다음 NDR을 받으면 보내는 IP 주소가 Microsoft에 의해 차단된 것입니다.

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

이 목록에서 제거를 요청하려면 목록 제거 포털을 사용하여 수신 차단된 보낸 사람 목록에서 자신을 [제거할 수 있습니다.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a>받는 사람의 정크 메일 폴더에 있는 내 전자 메일

EOP에서 메시지가 스팸으로 잘못 식별된 경우 받는 사람과 함께 이 가짓 긍정 메시지를 Microsoft 스팸 분석 팀에 제출하여 메시지를 평가하고 분석할 수 있습니다. 자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a>내 IP 주소의 트래픽이 EOP에 의해 스로틀됩니다.

EOP에서 IP 주소가 EOP에 의해 스로틀되고 있는 것을 나타내는 NDR을 받는 경우 다음을 예로 들 수 있습니다.

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

IP 주소에서 의심스러운 활동이 검색되어 추가 평가가 진행되는 동안 일시적으로 제한되어 NDR을 수신했습니다. 평가를 통해 의혹이 제거될 경우 이 제한이 곧 해제됩니다.

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a>I can't receive email from senders in Microsoft 365

 사용자로부터 메시지를 받으기 위해 네트워크에서 EOP가 데이터 센터에서 사용하는 IP 주소로부터의 연결을 허용하는지 확인합니다. 자세한 내용은 IP [주소 Exchange Online Protection 참조하세요.](../../enterprise/urls-and-ip-address-ranges.md)

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a>사용자에 대한 대량 전자 메일 Microsoft 365 모범 사례

전자 메일이 안전하고 Microsoft 365 방식으로 도착하는지 확인하려는 경우 이 섹션의 팁을 따르세요.

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a>보낸 사람 이름에 메시지를 보내는 사람이 반영되도록 합니다.

제목은 메시지의 내용을 간략하게 요약한 것이고 메시지 본문은 제품, 서비스 또는 제품의 대상을 명확하고 간결하게 나타내야 합니다. 예제:

정확함:

> From: marketing@shoppershandbag.com <br> 제목: 성탄절에 대한 카탈로그가 업데이트되었습니다!

정확하지 않음:

> From: someone@outlook.com <br> 제목: 카탈로그

사람들이 사용자와 수행하고 있는 작업을 보다 쉽게 알 수 있도록 함으로써 대부분의 스팸 필터를 통해 전달하는 데 어려움을 덜 수 있습니다.

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a>캠페인 전자 메일에 구독 취소 옵션 항상 포함

마케팅 전자 메일( 특히 뉴스레터)에는 항상 향후 전자 메일의 구독을 해지하는 방법이 포함되어야 합니다. 예제:

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

일부 보낸 사람은 받는 사람이 제목에 "구독 취소"가 포함된 특정 별칭으로 전자 메일을 보내야 하여 이 옵션을 포함합니다. 이 예제는 위의 한 번 클릭 예제보다는 바람직하지 않습니다. 받는 사람이 메일을 보내야 하도록 선택한 경우 링크를 클릭할 때 필요한 모든 필드가 미리 채워지는지 확인 합니다.

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a>마케팅 전자 메일 또는 뉴스레터 등록에 이중 옵트인 옵션 사용

회사에서 제품 또는 서비스에 액세스하기 위해 사용자에게 연락처 정보를 등록하도록 요구하거나 권장하는 경우 이 업계 모범 사례를 권장합니다. 일부 회사에서는 등록 프로세스 중에 마케팅 전자 메일 또는 전자 뉴스레터에 사용자를 자동으로 등록하는 것이 관행이지만 이는 전자 메일 필터링 세계에서 의심스러우는 마케팅 사례로 간주됩니다.

등록 프로세스 중에 "예, 뉴스레터 보내기" 또는 "예, 특별 혜택 보내기" 확인란이 기본적으로 선택되어 있는 경우, 주의를 기울이지 않는 사용자는 원치 않는 마케팅 전자 메일 또는 뉴스레터에 의도치 않은 등록할 수 있습니다.

 대신 이중 옵트인 옵션을 사용하는 것이 좋습니다. 즉, 마케팅 전자 메일 또는 뉴스레터의 확인란은 기본적으로 선택되지 않습니다. 또한 등록 양식이 제출되면 사용자가 마케팅 전자 메일을 받을지 확인할 수 있는 URL이 있는 확인 전자 메일이 사용자에게 전송됩니다.

 이렇게 하면 마케팅 전자 메일을 받으 원하는 사용자만 전자 메일에 등록하여 의심이 많은 전자 메일 마케팅 사례를 보내는 회사를 지우는 데 도움이 됩니다.

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a>전자 메일 메시지 콘텐츠가 투명하고 추적 가능하도록 보장

전자 메일이 전송되는 방식만큼 중요한 것은 포함된 콘텐츠입니다. 전자 메일 콘텐츠를 만들 때 다음과 같은 모범 사례를 사용하여 전자 메일에 전자 메일 필터링 서비스에 의해 플래그가 지정되지 않도록 합니다.

- 전자 메일 메시지에서 받는 사람이 주소장에 보낸 사람을 추가하게 요청하는 경우 이러한 작업은 배달 보장이 아 없다고 명확하게 설명해야 합니다.

- 메시지 본문에 포함된 리디렉션은 유사하고 일관적일 수 있으며 여러 개가 아니며 다양해야 합니다. 이 컨텍스트의 리디렉션은 링크 및 문서와 같이 메시지에서 멀어진 모든 것입니다. 광고 또는 구독 취소 링크가 많거나 프로필 링크 업데이트가 있는 경우 모두 동일한 도메인을 지정해야 합니다. 예제:

  맞습니다(모든 도메인이 동일).

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  올바르지 않습니다(모든 도메인이 다를 수 있습니다).

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- 큰 이미지 및 첨부 파일이 있는 콘텐츠나 이미지로만 구성된 메시지는 피합니다.

- 공개 개인 정보 또는 P3P 설정은 추적 픽셀(웹 버그 또는 비콘)의 존재를 명확하게 표시해야 합니다.

### <a name="remove-incorrect-email-aliases-from-your-databases"></a>데이터베이스에서 잘못된 전자 메일 별칭 제거

반송을 만드는 데이터베이스의 전자 메일 별칭은 불필요하며 아웃바운드 전자 메일은 전자 메일 필터링 서비스로 추가적으로 관리해야 할 위험에 노출됩니다. 전자 메일 데이터베이스를 최신으로 유지해야 합니다.