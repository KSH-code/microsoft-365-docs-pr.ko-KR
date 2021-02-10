---
title: 스팸 방지 보호 기능
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)에서 스팸을 방지하는 데 도움이 되는 스팸 방지 설정 및 필터에 대해 학습할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ae2c4f42d42c37f5b7a7df2b6c8306fd390b0af
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175862"
---
# <a name="anti-spam-protection-in-eop"></a>EOP의 스팸 방지 보호 기능

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 요금제 1 및 계획 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!NOTE]
> 이 항목은 관리자를 위한 것입니다. 최종 사용자 항목은 정크 메일 필터 개요 및 정크 메일 및 피싱에 [대해 자세히를 참조하세요.](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31) [](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)

Exchange Online 사서함이 없는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 전자 메일 메시지는 EOP에 의해 스팸(정크 메일)으로부터 자동으로 보호됩니다.

Microsoft의 전자 메일 보안 로드맵에는 제품 간 접근 방식이 수반됩니다. EOP 스팸 방지 및 피싱 방지 기술은 전자 메일 플랫폼에 적용하여 사용자에게 네트워크 전반에 걸쳐 최신 스팸 방지 및 피싱 방지 도구와 혁신 기능을 제공합니다. EOP의 목표는 정크 메일, 사기성 전자 메일 위협(피싱) 및 맬웨어로부터 사용자를 감지하고 보호하는 데 도움이 되는 포괄적이고 사용 가능한 전자 메일 서비스를 제공하는 것입니다.

전자 메일 사용이 증가하여 전자 메일 남용이 있습니다. 원치 않는 정크 메일은 받은 편지함 및 네트워크를 막고, 사용자 만족도에 영향을 미치며, 합법적인 전자 메일 통신의 효율성을 저해할 수 있습니다. 이러한 이유 때문에 Microsoft는 스팸 방지 기술에 계속 투자하고 있습니다. 간단히 말하면 정크 메일을 포함하고 필터링하는 것으로 시작합니다.

> [!TIP]
> 다음 스팸 방지 기술은 메시지 봉투(예: 보낸 사람 도메인 또는 메시지의 원본 IP 주소)를 기반으로 메시지를 허용하거나 차단하려는 경우 유용합니다. 페이로드를 기반으로 하는 메시지(예: 메시지의 URL 또는 첨부된 파일)를 허용하거나 차단하려면 [테넌트 허용/차단](tenant-allow-block-list.md)목록 포털을 사용해야 합니다.

## <a name="anti-spam-technologies-in-eop"></a>EOP의 스팸 방지 기술

정크 메일을 줄이기 위해 EOP에는 정크 메일을 식별하고 합법적인 전자 메일과 구분하기 위해 독점 스팸 필터링 기술을 사용하는 정크 메일 보호가 포함되어 있습니다. EOP 스팸 필터링은 알려진 스팸 및 피싱 위협과 소비자 플랫폼에서 사용자 피드백을 Outlook.com. 정크 메일 분류 프로그램에서 EOP 사용자의 지속적인 피드백을 통해 EOP 기술을 지속적으로 교육하고 개선할 수 있습니다.

EOP의 스팸 방지 설정은 다음 기술로 구성됩니다.

- **연결** 필터링: IP 허용 목록, IP 차단 목록 및 수신 허용 목록(Microsoft에서 유지 관리하는  신뢰할 수 있는 보낸 사람 목록)을 통해 인바운드 전자 메일 연결 초기에 양호하고 잘못된 전자 메일 원본 서버를 식별합니다. 연결 필터 정책에서 이러한 설정을 구성합니다. 연결 필터링 [구성에서 자세한 내용을 확인합니다.](configure-the-connection-filter-policy.md)

  > [!NOTE]
  > 스푸핑 인텔리전스에서는 연결 필터링을 사용하여 전자 메일 도메인을 스푸핑하는 보낸 사람 목록을 허용하고 차단합니다. 자세한 내용은 [Microsoft 365의](learn-about-spoof-intelligence.md)스푸핑 인텔리전스에 대한 자세한 내용을 참조하세요.

- **스팸 필터링(콘텐츠 필터링)**: EOP는 스팸 필터링 판정 **스팸,** **높은** 지수 **스팸,**  대량 전자 **메일,** 피싱 전자 메일 및 높은 신뢰도 피싱 전자 메일을 사용하여 메시지를 분류합니다. 이러한 판정에 따라 수행할 작업을 구성할 수 있으며, 배달되지 않고 메일이 전송된 메시지에 대해 최종 사용자 알림 옵션을 구성할 수 있습니다. 자세한 내용은 [Microsoft 365에서](configure-your-spam-filter-policies.md)스팸 방지 정책 구성을 참조하세요.

  > [!NOTE]
  > 기본적으로 스팸 필터링은 스팸으로 표시된 메시지를 받는 사람의 정크 메일 폴더로 보내도록 구성됩니다. 그러나 EOP가 전자 메일 흐름 사서함을 보호하는 하이브리드 환경에서는 메시지에 추가된 EOP 스팸 헤더를 인식하도록 두 개의 메일 흐름 규칙(전송 규칙)을 구성해야 합니다. 자세한 내용은 [하이브리드 환경에서 스팸을 정크 메일 폴더로 배달하도록 독립 실행형 EOP 구성하기](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)를 참조하세요.

- **아웃바운드** 스팸 필터링: 또한 EOP는 사용자가 아웃바운드 메시지 콘텐츠에서 또는 아웃바운드 메시지 제한을 초과하여 스팸을 보내지 않는지 검사합니다. 자세한 내용은 [Microsoft 365에서](configure-the-outbound-spam-policy.md)아웃바운드 스팸 필터링 구성을 참조하세요.

- **스푸핑 인텔리전스**: 자세한 내용은 [Microsoft 365의](learn-about-spoof-intelligence.md)스푸핑 인텔리전스에 대한 자세한 내용을 참조하세요.

## <a name="manage-errors-in-spam-filtering"></a>스팸 필터링에서 오류 관리

좋은 메시지를 스팸으로 식별하거나(가음성으로도 알려지거나) 스팸이 받은 편지함으로 배달될 수 있습니다. 다음 섹션의 제안을 사용하여 발생된 문제를 찾고 향후 이러한 문제를 방지할 수 있습니다.

두 시나리오에 적용되는 몇 가지 모범 사례는 다음과 같습니다.

- 잘못 된 메시지를 Microsoft에 항상 제출 합니다. 자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.

- **스팸 방지** 메시지 헤더 검사: 이러한 값은 메시지가 스팸으로 표시된 이유 또는 스팸 필터링을 건너뛴 이유를 알 수 있습니다. 자세한 내용은 [스팸 방지 메시지 헤더](anti-spam-message-headers.md)를 참조하세요.

- MX 레코드를 **Microsoft 365로** 설정: EOP가 최상의 보호를 제공하기 위해서는 항상 Microsoft 365로 전자 메일을 전달하는 것이 좋습니다. 자세한 내용은 모든 DNS 호스팅 [공급자에서 Microsoft 365용 DNS 레코드 만들기를 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)

  MX 레코드가 다른 위치(예: 타사 스팸 방지 솔루션 또는 어플라이언스)를 포인트로 하는 경우 EOP에서 정확한 스팸 필터링을 제공하기가 어렵습니다. 이 시나리오에서는 커넥터에 대해 향상된 필터링을 구성해야 합니다(목록 건너뛰기라고도 _합니다)._ 자세한 내용은 Exchange Online의 커넥터에 대한 향상된 [필터링을 참조하세요.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- **전자 메일 인증** 사용: 전자 메일 도메인을 소유하고 있는 경우 DNS를 사용하여 해당 도메인의 보낸 사람이 보낸 메시지가 합법적인지 확인할 수 있습니다. EOP에서 스팸 및 원치 않는 스푸핑을 방지할 수 있도록 다음 전자 메일 인증 방법을 모두 사용하세요.

  - **SPF**: 보낸 사람 정책 프레임워크는 보내는 도메인의 소유자와 메시지의 원본 IP 주소를 검증합니다. SPF를 빠르게 소개하고 빠르게 구성하는 방법을 얻었다면 스푸핑을 방지할 수 있도록 SPF 설정을 [참조합니다.](set-up-spf-in-office-365-to-help-prevent-spoofing.md) Microsoft 365에서 SPF를 사용하는 방법이나 문제 해결 또는 비표준 배포(예: 하이브리드 배포)에 대한 자세한 내용은 [Microsoft 365에서 SPF(Sender Policy Framework)를 사용하여 스푸핑을 차단하는 방법](how-office-365-uses-spf-to-prevent-spoofing.md)을 참조하세요.

  - **DKIM**: DomainKeys Identified Mail은 도메인에서 보낸 메시지의 메시지 헤더에 디지털 서명을 추가합니다. 자세한 내용은 [DKIM을 사용하여 Microsoft 365의](use-dkim-to-validate-outbound-email.md)사용자 지정 도메인에서 보낸 아웃바운드 전자 메일의 유효성을 검사합니다.

  - **DMARC**: 도메인 기반 메시지 인증, 보고 및 적합성은 대상 전자 메일 시스템에서 SPF 또는 DKIM 확인에 실패한 메시지에 대해 할 작업을 결정하고 전자 메일 파트너에게 다른 수준의 신뢰를 제공합니다. 자세한 내용은 [DMARC를 사용하여 Microsoft 365에서](use-dmarc-to-validate-email.md)전자 메일의 유효성을 검사합니다.

- **대량 전자** 메일 설정 확인: 스팸 방지 정책에서 구성하는 BCL(대량 규격 수준) 임계값에 따라 대량 전자 메일(회색 메일)이 스팸으로 표시되어 있는지 여부가 결정됩니다.  기본적으로 설정되어 있는 PowerShell 전용 _설정인 MarkAsSpamBulkMail도_ 결과에 영향을 미치게 됩니다. 자세한 내용은 [Microsoft 365에서](configure-your-spam-filter-policies.md)스팸 방지 정책 구성을 참조하세요.

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>받은 편지함으로 스팸 배달 방지

- **조직 설정** 확인: 메시지가 스팸 필터링을 건너뛸 수 있도록 허용하는 설정(예: 스팸 방지 정책에서 허용된 도메인 목록에 도메인을 추가하는 경우)을 확인합니다. 권장 설정은 EOP 및 [Office 365용 Microsoft Defender](recommended-settings-for-eop-and-office365-atp.md) 보안에 대한 권장 설정과 수신이 가능한 보낸 사람 목록 [만들기를 참조하세요.](create-safe-sender-lists-in-office-365.md)

- **사용자의** 사서함에서 정크 메일 규칙이 사용하도록 설정되어 있는지 확인합니다. 이 규칙은 기본적으로 사용하도록 설정되지만 사용하지 않도록 설정된 경우 정크 메일 폴더로 표시된 메시지를 정크 메일 폴더로 이동할 수 없습니다. 자세한 내용은 [Microsoft 365의 Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md)사서함에 대한 정크 메일 설정 구성을 참조하세요.

- **사용 가능한 수신 차단된 보낸** 사람 목록 사용: 자세한 내용은 차단된 보낸 [사람 목록 만들기를 참조하세요.](create-block-sender-lists-in-office-365.md)

- **대량 전자 메일 구독 취소** 사용자가 등록한 메시지(뉴스레터, 제품 공지 등)에 해당하고 해당 출처의 구독 취소 링크가 포함된 경우 구독을 취소하도록 요청하는 것이 됩니다.

- 독립 실행형 **EOP: EOP** 스팸 필터링 판정에 대한 메일 흐름 규칙 만들기: EOP가온-프레미스 Exchange 사서함을 보호하는 독립 실행형 EOP 환경에서는 정크 메일 규칙이 메시지를 정크 메일 폴더로 이동할 수 있도록 EOP 스팸 필터링 판정을 변환하도록 메일 흐름 규칙(전송 규칙)을 구성해야 합니다. 자세한 내용은 [하이브리드 환경에서 스팸을 정크 메일 폴더로 배달하도록 독립 실행형 EOP 구성하기](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)를 참조하세요.

### <a name="prevent-good-email-from-being-identified-as-spam"></a>좋은 전자 메일이 스팸으로 식별되지 않도록 방지

다음은 가긍성 방지를 위해 취할 수 있는 몇 가지 단계입니다.

- **사용자의 Outlook 정크 메일 필터 설정을 확인합니다.**

  - **Outlook 정크** 메일 필터가 사용하지 않도록 설정되어 있는지 확인: Outlook 정크 메일 필터가 **기본값인 자동** 필터링 없음으로 설정되어 있는 경우 Outlook에서는 스팸으로 분류하지 않습니다.  낮음 또는 높음으로 설정하면 Outlook 정크 메일 필터는 자체 SmartScreen 필터 기술을 사용하여 스팸을 식별하고 정크 메일 폴더로 이동하여 가긍정을 얻을 수 있습니다.  Microsoft는 2016년 11월 Exchange 및 Outlook에서 SmartScreen 필터에 대한 스팸 정의 업데이트 생성을 중지했습니다. 기존 SmartScreen 스팸 정의는 적용된 것이지만 시간이 지날 때 효율성이 저하될 수 있습니다.

  - **Outlook '수신** 가능 목록만' 설정이 사용되지 않도록 설정되어 있는지 확인합니다. 이 설정을 사용하도록 설정하면 사용자의 수신 가능 보낸 사람 목록 또는 수신 가능 받는 사람 목록에 있는 보낸 사람의 메시지만 받은 편지함으로 배달됩니다. 다른 모든 사람이 전송한 전자 메일은 자동으로 정크 메일 폴더로 이동됩니다.

  이러한 설정에 대한 자세한 내용은 [Microsoft 365의 Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md)사서함에서 정크 메일 설정 구성을 참조하세요.

- **사용 가능한 수신 가능 보낸** 사람 목록 사용: 자세한 내용은 수신 가능 보낸 사람 목록 [만들기를 참조하세요.](create-safe-sender-lists-in-office-365.md)

- **사용자가** Exchange Online 서비스 설명의 수신 및 [](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) 전송 제한에 설명된 전송 및 수신 제한 내에 있는지를 확인할 수 있습니다.

- **독립 실행형 EOP:** 디렉터리 동기화 사용: 독립 실행형 EOP를 사용하여온-프레미스 Exchange 조직을 보호하는 경우 디렉터리 동기화를 사용하여 사용자 설정을 서비스와 동기화해야 합니다. 이렇게 하면 EOP에서 수신 허용-보낸 사람 목록을 유지할 수 있습니다. 자세한 내용은 [메일 사용자 관리를 위한 디렉토리 동기화 사용을](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users) 참고하세요.

## <a name="anti-spam-legislation"></a>스팸 방지 입법

Microsoft는 새로운 기술 및 자율 규제를 개발하려면 효과적인 정부 정책 및 법률 프레임워크를 지원해야 합니다. 전 세계 스팸 확산은 상업용 전자 메일을 규제하기 위해 수많은 입법 기관을 급증하고 있습니다. 이제 많은 국가에서 스팸 방지법이 제정되었습니다. 미국에는 스팸을 규정하는 연방법과 주법이 둘 다 있으며 이러한 보완적인 접근 방식은 합법적인 전자 상거래가 번성할 수 있도록 하면서 스팸을 자르는 데 도움이 됩니다. CAN-SPAM Act는 사기성 및 사기성 전자 메일 메시지를 차단하는 데 사용할 수 있는 도구를 확장합니다.
