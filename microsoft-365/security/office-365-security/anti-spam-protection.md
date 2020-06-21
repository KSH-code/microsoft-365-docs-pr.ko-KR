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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP (Exchange Online Protection)에서 스팸을 방지 하는 데 도움이 되는 스팸 방지 설정 및 필터에 대해 알아볼 수 있습니다.
ms.openlocfilehash: ce673a4bee64dfbc84f870f9cf4871e9ac32a71c
ms.sourcegitcommit: 89636f35b0194986f156302fc1bb96af25d4805b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44800110"
---
# <a name="anti-spam-protection-in-eop"></a>EOP의 스팸 방지 보호 기능

> [!NOTE]
> 이 항목은 관리자를 위한 것입니다. 최종 사용자 항목의 경우 [정크 메일 필터 개요](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) 및 [정크 메일 및 피싱에 대 한 자세한](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31)정보를 참조 하세요.

Exchange online 사서함이 없는 Microsoft 365 조직의 EOP (독립 실행형 Exchange Online Protection) 조직에 전자 메일 메시지가 EOP을 통해 스팸 (정크 메일) 로부터 자동으로 보호 됩니다.

Microsoft의 전자 메일 보안 로드맵에는 일치 하지 않는 제품 간 방법이 포함 됩니다. EOP 스팸 방지 및 피싱 방지 기술은 전자 메일 플랫폼에 적용 되어 사용자에 게 최신 스팸 방지 및 피싱 방지 도구와 네트워크 전체의 혁신을 제공 합니다. EOP의 목표는 정크 메일, 사기성 전자 메일 위협 (피싱) 및 맬웨어로부터 사용자를 감지 하 고 보호 하는 데 도움이 되는 포괄적이 고 사용 가능한 전자 메일 서비스를 제공 하는 것입니다.

전자 메일 사용이 증가 함에 따라 전자 메일 남용이 발생 합니다. 모니터링 되지 않는 정크 메일은 받은 편지함 및 네트워크를 clog 하 고 사용자 만족도에 영향을 줄 수 있으며 합법적인 전자 메일 통신의 효율성을 저하 합니다. Microsoft가 스팸 방지 기술에 계속 투자 하는 이유입니다. 간단히 말해서 정크 메일을 포함 하 고 필터링 하 여 시작 합니다.

## <a name="anti-spam-technologies-in-eop"></a>EOP의 스팸 방지 기술

정크 메일을 줄이기 위해 EOP에서는 독점 스팸 필터링 기술을 사용 하 여 합법적인 전자 메일에서 정크 메일을 식별 하 고 분리 하는 정크 메일 보호 기능을 포함 합니다. EOP 스팸 필터링은 알려진 스팸 및 피싱 위협과 소비자 플랫폼 Outlook.com의 사용자 의견을 알아냅니다. 정크 메일 분류 프로그램에서 EOP 사용자의 지속적인 피드백을 통해 EOP 기술을 지속적으로 교육 하 고 향상 시킬 수 있습니다.

EOP의 스팸 방지 설정은 다음과 같은 기술로 구성 됩니다.

- **연결 필터링**: Ip 허용 목록, Ip 차단 목록 및 *안전한 목록* (Microsoft에서 유지 관리 되는 신뢰할 수 있는 보낸 사람 목록)을 통해 인바운드 전자 메일 연결 초기에 양호 하 고 잘못 된 전자 메일 원본 서버를 식별 합니다. 이러한 설정은 연결 필터 정책에서 구성 합니다. 자세한 내용은 [연결 필터링 구성을](configure-the-connection-filter-policy.md)참고 하세요.

  > [!NOTE]
  > 스푸핑 인텔리전스는 연결 필터링을 사용 하 여 전자 메일 도메인을 위장 하는 보낸 사람 목록을 만들고 허용을 차단 합니다. 자세한 내용은 [Microsoft 365에서 스푸핑 인텔리전스에 대 한 자세한 내용을](learn-about-spoof-intelligence.md)참조 하세요.

- **스팸 필터링 (콘텐츠 필터링)**: EOP은 스팸 필터링 verdicts **스팸**, **높은 신뢰도 스팸**, **대량 전자 메일**, **피싱 메일** 및 **높은 신뢰도 피싱 전자 메일** 을 사용 하 여 메시지를 분류 합니다. 이러한 verdicts에 따라 수행할 작업을 구성 하 고, 전달 되지 않고 격리 된 메시지에 대 한 최종 사용자 알림 옵션을 구성할 수 있습니다. 자세한 내용은 [Microsoft 365에서 스팸 방지 정책 구성을](configure-your-spam-filter-policies.md)참조 하세요.

  > [!NOTE]
  > 기본적으로 스팸 필터링은 스팸으로 표시 된 메시지를 받는 사람의 정크 메일 폴더로 보내도록 구성 됩니다. 그러나 EOP가 온-프레미스 Exchange 사서함을 보호 하는 하이브리드 환경에서는 메시지에 추가 되는 EOP 스팸 헤더를 인식할 수 있도록 온-프레미스 Exchange 조직에서 두 개의 메일 흐름 규칙 (전송 규칙이 라고도 함)을 구성 해야 합니다. 자세한 내용은 [하이브리드 환경에서 스팸을 정크 메일 폴더로 배달하도록 독립 실행형 EOP 구성하기](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)를 참조하세요.

- **아웃 바운드 스팸 필터링**: EOP 또한 사용자가 아웃 바운드 메시지 콘텐츠 또는 아웃 바운드 메시지 제한을 초과 하 여 스팸 메일을 보내지 않도록 확인 합니다. 자세한 내용은 [Microsoft 365에서 아웃 바운드 스팸 필터링 구성을](configure-the-outbound-spam-policy.md)참조 하세요.

- **스푸핑 인텔리전스**: 자세한 내용은 [Microsoft 365에서 스푸핑 인텔리전스에 대 한 자세한](learn-about-spoof-intelligence.md)정보를 참조 하세요.

## <a name="manage-errors-in-spam-filtering"></a>스팸 필터링의 오류 관리

좋은 메시지를 스팸으로 식별 하거나 (가양성이 라고도 함) 스팸을 받은 편지 함으로 배달할 수 있습니다. 다음 섹션에 나와 있는 제안을 사용 하 여 발생 한 상황을 확인 하 고 그에 해당 하지 않는 문제를 방지할 수 있습니다.

다음은 두 시나리오에 적용 되는 몇 가지 최상의 방법입니다.

- 스팸으로 잘못 분류 메시지를 항상 Microsoft에 제출 합니다. 자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.

- **스팸 방지 메시지 헤더를 검사**합니다. 이러한 값은 메시지가 스팸으로 표시 된 이유와 스팸 필터링을 건너뛴 이유를 알려줍니다. 자세한 내용은 [스팸 방지 메시지 헤더](anti-spam-message-headers.md)를 참조하세요.

- **Microsoft 365에 대 한 MX 레코드 가리키기**: EOP에서 최상의 보호를 제공 하려면 먼저 전자 메일을 Microsoft 365로 배달 하는 것이 좋습니다. 자세한 내용은 [dns 호스팅 공급자에서 Microsoft 365에 대 한 dns 레코드 만들기](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)를 참조 하십시오.

  MX 레코드가 다른 위치 (예: 타사 스팸 방지 솔루션 또는 어플라이언스)를 가리키는 경우에는 EOP가 정확한 스팸 필터링을 제공 하기가 어렵습니다. 이 시나리오에서는 커넥터 ( _건너뛰기 목록_)에 대 한 향상 된 필터링을 구성 해야 합니다. 자세한 내용은 [Exchange Online의 커넥터에 대 한 향상 된 필터링](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)을 참조 하십시오.

- **전자 메일 인증 사용**: 전자 메일 도메인을 소유 하 고 있는 경우 DNS를 사용 하 여 해당 도메인의 보낸 사람 으로부터 메시지가 유효한 지 확인할 수 있습니다. EOP에서 스팸 및 원치 않는 스푸핑 문제를 방지 하려면 다음과 같은 전자 메일 인증 방법을 모두 사용 합니다.

  - **SPF**: 보낸 사람 정책 프레임 워크는 보내는 도메인의 소유자에 대해 메시지의 원본 IP 주소를 확인 합니다. SPF에 대 한 간략 한 소개 및 빠르게 구성 하려면 SPF를 설정 하 여 [스푸핑을 방지](set-up-spf-in-office-365-to-help-prevent-spoofing.md)합니다 .를 참조 하세요. Microsoft 365에서 SPF를 사용하는 방법이나 문제 해결 또는 비표준 배포(예: 하이브리드 배포)에 대한 자세한 내용은 [Microsoft 365에서 SPF(Sender Policy Framework)를 사용하여 스푸핑을 차단하는 방법](how-office-365-uses-spf-to-prevent-spoofing.md)을 참조하세요.

  - **Dkim**: Domainkeys 확인 메일 도메인에서 보낸 메시지의 메시지 헤더에 디지털 서명을 추가 합니다. 자세한 내용은 [Microsoft 365에서 DKIM을 사용 하 여 사용자 지정 도메인에서 보낸 아웃 바운드 전자 메일의 유효성 검사를](use-dkim-to-validate-outbound-email.md)참조 하세요.

  - **DMARC**: 도메인 기반 메시지 인증, 보고 및 적합성은 대상 전자 메일 시스템에서 SPF 또는 dkim 검사가 실패 한 메시지에 대해 수행할 작업을 결정 하 고 전자 메일 파트너에 게 다른 수준의 신뢰를 제공 하는 데 도움이 됩니다. 자세한 내용은 [Microsoft 365에서 DMARC을 사용 하 여 전자 메일의 유효성 검사를](use-dmarc-to-validate-email.md)참조 하십시오.

- **대량 전자 메일 설정 확인**: 스팸 방지 정책에 구성 하는 BCL (대량 준수 수준) 임계값에 따라 대량 전자 메일 ( _회색 메일이_라고도 함)이 스팸으로 표시 되는지 여부가 결정 됩니다. 기본적으로 설정 되는 PowerShell 전용 _MarkAsSpamBulkMail_ 결과에도 기여 합니다. 자세한 내용은 [Microsoft 365에서 스팸 방지 정책 구성을](configure-your-spam-filter-policies.md)참조 하세요.

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>받은 편지함에 스팸 배달 방지

- **조직 설정 확인**: 스팸 방지 정책에서 허용 되는 도메인 목록에 자체 도메인을 추가 하는 경우와 같이 메시지가 스팸 필터링을 건너뛰는 것을 허용 하는 설정을 검토 합니다. 권장 설정에 대 한 자세한 내용은 [EOP And Office 365 ATP security의 권장 설정](recommended-settings-for-eop-and-office365-atp.md) 및 [수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조 하세요.

- **정크 메일 규칙이 사용자 사서함에서 사용 하도록 설정 되어 있는지 확인**하세요. 기본적으로 사용 하도록 설정 되어 있지만 사용 하지 않도록 설정 되어 있으면 정크 메일로 표시 된 메시지를 정크 메일 폴더로 이동할 수 없습니다. 자세한 내용은 [Microsoft 365에서 Exchange Online 사서함의 정크 메일 설정 구성을](configure-junk-email-settings-on-exo-mailboxes.md)참조 하세요.

- **사용할 수 있는 차단 된 보낸 사람 목록 사용**: 자세한 내용은 [수신 거부 목록 만들기](create-block-sender-lists-in-office-365.md)를 참조 하세요.

- **대량 전자 메일 구독 취소** 사용자가 등록 한 메시지 (뉴스레터, 제품 공지 사항 등)가 있고 믿을 수 있는 출처의 구독 취소 링크를 포함 하는 경우 간단히 구독을 취소할 것을 요청 하는 것이 좋습니다.

- **독립 실행형 EOP: 온-프레미스 exchange에서 EOP 스팸 필터링 verdicts에 대 한 메일 흐름 규칙 만들기**: EOP 온-프레미스 exchange 사서함을 보호 하는 독립 실행형 EOP 환경에서는 온-프레미스 exchange의 메일 흐름 규칙 (전송 규칙이 라고도 함)을 구성 하 여 정크 메일 규칙에서 메시지를 정크 메일 폴더로 이동할 수 있도록 해야 합니다. 자세한 내용은 [하이브리드 환경에서 스팸을 정크 메일 폴더로 배달하도록 독립 실행형 EOP 구성하기](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)를 참조하세요.

### <a name="prevent-good-email-from-being-identified-as-spam"></a>전자 메일이 스팸으로 식별 되지 않도록 방지

가양성을 방지 하기 위해 수행할 수 있는 몇 가지 단계는 다음과 같습니다.

- **사용자의 Outlook 정크 메일 필터 설정을 확인 합니다**.

  - **Outlook 정크 메일 필터가 사용 하지 않도록 설정 되어 있는지 확인**: Outlook 정크 메일 필터를 기본값인 **자동 필터링**이 해제 되지 않으면 outlook에서 massages를 스팸으로 분류 하지 않습니다.  **낮음** 또는 **높음으로**설정 된 경우 Outlook 정크 메일 필터는 자체 SmartScreen 필터 기술을 사용 하 여 스팸을 식별 하 고 정크 메일 폴더로 이동 하므로 가양성을 가져올 수 있습니다. Microsoft는 Exchange 및 11 월 2016의 Outlook에서 SmartScreen 필터에 대 한 스팸 정의 업데이트 생성을 중지 했습니다. 기존 SmartScreen 스팸 정의는 그대로 남아 있지만 해당 효율성은 시간이 지남에 따라 저하 될 수 있습니다.

  - **Outlook ' 안전한 목록만 ' 설정이 사용 하지 않도록 설정 되어 있는지 확인**:이 설정을 사용 하도록 설정 하면 사용자의 수신 허용-보낸 사람 목록 또는 수신 허용-받는 사람 목록에 있는 보낸 사람의 메시지만 받은 편지 함으로 배달 됩니다. 다른 사용자의 전자 메일은 자동으로 정크 메일 폴더로 이동 됩니다.

  이러한 설정에 대 한 자세한 내용은 [Microsoft 365에서 Exchange Online 사서함의 정크 메일 설정 구성을](configure-junk-email-settings-on-exo-mailboxes.md)참조 하십시오.

- **사용할 수 있는 수신 허용-보낸 사람 목록을 사용**합니다. 자세한 내용은 [수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조 하십시오.

- Exchange Online 서비스 설명의 [수신 및 전송 제한](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) 에 설명 된 대로, **사용자가 보내기 및 받기 제한 내에 있는지 확인** 합니다.

- **독립 실행형 EOP: 디렉터리 동기화 사용**: 독립 실행형 EOP을 사용 하 여 온-프레미스 Exchange 조직을 보호 하는 경우 디렉터리 동기화를 사용 하 여 사용자 설정을 서비스와 동기화 해야 합니다. 이렇게 하면 EOP에서 수신 허용-보낸 사람 목록을 유지할 수 있습니다. 자세한 내용은 [메일 사용자 관리를 위한 디렉토리 동기화 사용을](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users) 참고하세요.

## <a name="anti-spam-legislation"></a>스팸 방지 법규

Microsoft에서는 새로운 기술 및 자체 규정을 개발 하는 데 효과적인 정부 정책 및 올바른 프레임 워크를 지원 해야 한다고 생각 합니다. 전 세계의 스팸 확산에는 상업용 전자 메일을 규제 하기 위해 수많은 기관 본문 spurred 있습니다. 이제 대부분의 국가에서는 스팸 방지 법이 마련 되었습니다. 미국에는 스팸이 관리 되는 연방 및 지방 법률이 있으며, 이러한 보완 방식은 합법적인 전자 상거래를 프로 스퍼로 설정 하는 동안 스팸을 curtail 하는 데 도움이 됩니다. CAN-스팸 Act는 curbing 사기 및 사기성 전자 메일 메시지에 사용할 수 있는 도구를 확장 합니다.
