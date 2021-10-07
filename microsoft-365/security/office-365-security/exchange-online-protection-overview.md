---
title: Exchange Online Protection(EOP) 개요
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: EOP(Exchange Online Protection)가 독립 실행형 및 하이브리드 환경에서 어떻게 프레미스 전자 메일 조직을 보호할 수 있도록 하는지 알아보십시오.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0fa4aa1d724ad13b3c43f84a0c6d2a7e8002983f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60174366"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection 개요

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection(EOP)는 스팸, 맬웨어 및 기타 전자 메일 위협으로부터 조직을 보호하는 클라우드 기반 필터링 서비스입니다. EOP는 사서함이 있는 모든 Microsoft 365 조직에 Exchange Online 포함됩니다.

> [!NOTE]
> EOP는 자체적으로만 사용할 수 있으며, 하이브리드 환경에서는 사서함을 보호할 수 있으며, 하이브리드 환경에서도 EOP를 통해 사서함을 보호할 Exchange 있습니다. 자세한 내용은 독립 실행형 을 [Exchange Online Protection.](/exchange/standalone-eop/standalone-eop)

EOP 보안 기능을 설정하는 단계 및 Microsoft Defender for Office 365 추가된 보안에 대한 비교는 위협으로부터 [보호를 참조하세요.](protect-against-threats.md) EOP 기능에 대한 권장 설정은 EOP 및 보안용 [Microsoft Defender에](recommended-settings-for-eop-and-office365.md)대한 권장 Office 365 있습니다.

이 문서의 나머지에서는 EOP의 작동 방식과 EOP에서 사용할 수 있는 기능에 대해 설명합니다.

## <a name="how-eop-works"></a>EOP의 작동 방식

EOP가 받는 전자 메일을 처리하는 방법을 확인하면 EOP의 작동 방식을 이해하는 데 도움이 됩니다.

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="정크 메일 또는 정크 메일 또는 최종 사용자 메일 배달에 대한 판결이 나기 전에 EOP, 연결, 맬웨어 방지, 메일 흐름 규칙 슬래시 정책 필터링 및 콘텐츠 필터링을 통해 전달되는 인터넷 또는 고객 피드백의 그래픽입니다.":::

1. 들어오는 메시지가 EOP에 들어오면 처음에는 연결 필터링을 통과하여 보낸 사람 신뢰도를 확인합니다. 대부분의 스팸은 이 시점에서 중지된 후 EOP에서 거부됩니다. 자세한 내용은 [연결 필터링 구성](configure-the-connection-filter-policy.md)을 참조하십시오.

2. 그런 다음 메시지에서 맬웨어를 검사합니다. 메시지 또는 첨부 파일에서 맬웨어가 발견된 경우 해당 메시지는 검사로 배달됩니다. 기본적으로 관리자만 맬웨어로 차단된 메시지를 보고 상호 작용할 수 있습니다. 그러나 관리자는 정책을 만들고 [](quarantine-policies.md) 사용하여 사용자가 검사된 메시지에 대해 할 수 있는 작업을 지정할 수 있습니다. 맬웨어 보호에 대한 자세한 내용은 [EOP의 맬웨어 방지 보호를 참조합니다.](anti-malware-protection.md)

3. 메시지는 정책 필터링을 통해 계속됩니다. 여기서 메시지는 앞서 만든 모든 메일 흐름 규칙(전송 규칙)에 대해 평가됩니다. 예를 들어 규칙은 특정 보낸 사람으로부터 메시지가 도착할 때 관리자에게 알림을 보낼 수 있습니다.

   서비스 라이선스가 있는 Exchange Enterprise 조직의 경우 EOP의 [DLP(데이터](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) 손실 방지) 검사도 이 시점에 발생됩니다.

4. 이 메시지는 유해한 메시지가 스팸, 높은 지수의 스팸, 피싱, 높은 신뢰도 피싱 또는 대량(스팸 방지 정책) 또는 스푸핑(피싱 방지 정책의 스푸핑 설정)으로 식별되는 콘텐츠 필터링(스팸 방지 및 스푸핑 방지)을 통과합니다. 필터링 판정(예: 정크 메일 폴더로 이동 등)과 사용자가 검사 정책을 사용하여 분리된 메시지에 대해 할 수 있는 작업을 기반으로 메시지에 대해 수행하도록 작업을 구성할 수 [있습니다.](quarantine-policies.md) 자세한 내용은 [스팸](configure-your-spam-filter-policies.md) 방지 정책 구성 및 EOP에서 피싱 방지 정책 [구성을 참조하세요.](configure-anti-phishing-policies-eop.md)

이러한 모든 보호 계층을 성공적으로 전달하는 메시지는 받는 사람에게 배달됩니다.

자세한 내용은 전자 메일 보호의 순서 및 [우선 순위를 참조하세요.](how-policies-and-protections-are-combined.md)

### <a name="eop-datacenters"></a>EOP 데이터 센터

EOP는 최고 수준의 사용 가능성을 제공하도록 설계된 전 세계 데이터 센터 네트워크에서 실행됩니다. 예를 들어 데이터 센터를 사용할 수 없더라도 서비스 중단 없이 전자 메일 메시지가 다른 데이터 센터에 자동으로 라우팅됩니다. 각 데이터 센터의 서버는 사용자 대신 메시지를 수락하여 조직과 인터넷을 분리하는 계층을 제공함으로써 서버에 대한 부하를 줄입니다. 이처럼 가용성이 뛰어난 네트워크를 통해 Microsoft는 전자 메일이 제때에 조직으로 배달되도록 할 수 있습니다.

EOP는 특정 지역 내에서만 데이터 센터 간 부하 분산을 수행합니다. 단일 지역에서 프로비전되는 경우에는 해당 영역에 대한 메일 라우팅을 사용하여 모든 메시지가 처리됩니다. 다음 목록에는 EOP 데이터 센터에 대한 영역 메일 라우팅의 작동 방식이 나와 있습니다.

- EMEA(유럽, 중동 및 아프리카)에서는 모든 Exchange Online 사서함이 EMEA 데이터 센터에 있으며 모든 메시지가 EOP 필터링용으로 EMEA 데이터 센터를 통해 라우팅됩니다.
- APAC(Asia-Pacific)에서 모든 Exchange Online 사서함은 APAC 데이터 센터에 있으며 메시지는 현재 EOP 필터링을 위해 APAC 데이터 센터를 통해 라우팅됩니다.
- 미국에서는 서비스가 다음 위치에 배포됩니다.
  - 남미: Exchange Online 사서함은 브라질과 칠레의 데이터 센터에 있습니다. 모든 메시지는 EOP 필터링을 위해 로컬 데이터 센터를 통해 라우팅됩니다. Quarantined messages are stored in the datacenter where the tenant is located.
  - 캐나다: Exchange Online 사서함은 캐나다의 데이터 센터에 있습니다. 모든 메시지는 EOP 필터링을 위해 로컬 데이터 센터를 통해 라우팅됩니다. Quarantined messages are stored in the datacenter where the tenant is located.
  - 미국: Exchange Online 사서함은 미국 데이터 센터에 있습니다. 모든 메시지는 EOP 필터링을 위해 로컬 데이터 센터를 통해 라우팅됩니다. Quarantined messages are stored in the datacenter where the tenant is located.
- GCC(정부 커뮤니티 클라우드)의 경우에는 모든 Exchange Online 사서함이 미국 데이터 센터에 있으며 모든 메시지는 EOP 필터링용으로 미국 데이터 센터를 통해 라우팅됩니다.

### <a name="eop-features"></a>EOP 기능

이 섹션에서는 EOP에서 사용할 수 있는 주요 기능에 대한 간략한 개요를 제공합니다.

모든 EOP 구독 계획의 요구 사항, 중요한 제한 및 기능 가용성에 대한 자세한 내용은 Exchange Online Protection [서비스 설명을 참조하세요.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

**참고**:

- EOP에서는 메시지 내에서 알려진 악성 링크를 검색하는 데 도움이 되는 여러 URL 차단 목록을 사용합니다.
- EOP는 스팸을 보내는 것으로 알려진 방대한 도메인 목록을 사용 합니다.
- EOP는 여러 맬웨어 방지 엔진을 사용하여 고객을 자동으로 보호합니다.
- EOP는 메시지 본문의 활성 페이로드와 모든 메시지 첨부 파일에서 맬웨어를 검사합니다.
- 보호 정책에 대한 권장 값은 보안에 대한 EOP 및 [Microsoft Defender에 대한 권장 Office 365 참조하세요.](recommended-settings-for-eop-and-office365.md)
- 보호 정책을 구성하는 빠른 지침은 [위협으로부터 보호를 참조하세요.](protect-against-threats.md)

<br>

****
|기능|설명|
|---|---|
|**보호**||
|맬웨어 방지|[EOP의 맬웨어 방지 보호 기능](anti-malware-protection.md) <p> [맬웨어 방지 보호 FAQ](anti-malware-protection-faq-eop.yml) <p> [EOP에서 맬웨어 방지 정책 구성](configure-anti-malware-policies.md)|
|인바운드 스팸 방지|[EOP의 스팸 방지 보호 기능](anti-spam-protection.md) <p> [스팸 방지 및 보호 FAQ](anti-spam-protection-faq.yml) <p> [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)|
|아웃바운드 스팸 방지|[EOP의 아웃바운드 스팸 보호](outbound-spam-controls.md) <p> [EOP에서 아웃바운드 스팸 필터링 구성](configure-the-outbound-spam-policy.md) <p> [전자 메일에서 자동 외부 전자 메일 전달 Microsoft 365](external-email-forwarding.md)|
|연결 필터링|[연결 필터링 구성](configure-the-connection-filter-policy.md)|
|피싱 방지|[2016년 8월의 피싱 Microsoft 365](set-up-anti-phishing-policies.md) <p> [EOP에서 스팸 방지 정책 구성](configure-anti-phishing-policies-eop.md)|
|스푸핑 방지 보호 기능|[EOP의 스푸핑 인텔리전스 정보](learn-about-spoof-intelligence.md) <p> [테넌트 허용/차단 목록 관리](tenant-allow-block-list.md)|
|배달된 맬웨어, 스팸 및 피싱 메시지에 대한 ZAP(제로 아워 자동 제거)|[Exchange Online](zero-hour-auto-purge.md)|
|보안 정책 미리조정|[EOP 및 Microsoft Defender for Office 365](preset-security-policies.md) <p> [EOP 및 Microsoft Defender for Office 365](configuration-analyzer-for-security-policies.md)|
|테넌트 허용/차단 목록|[테넌트 허용/차단 목록 관리](tenant-allow-block-list.md)|
|메시지 보낸 사람에 대한 차단 목록|[EOP에서 차단된 보낸 사람 목록 만들기](create-block-sender-lists-in-office-365.md)|
|메시지 보낸 사람에 대한 목록 허용|[EOP에서 수신 가능한 보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)|
|DBEB(디렉터리 기반 Edge 차단)|[디렉터리 기반 Edge 차단을 사용하여 잘못된 받는 사람에게 전송된 메시지 거부](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|
|**Quarantine and submissions**||
|관리자 제출|[관리자 제출을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 Microsoft에 제출](admin-submission.md)|
|사용자 제출(사용자 지정 사서함)|[사용자 제출 정책](user-submission.md)|
|Quarantine - admins|[EOP에서 관리자 권한으로 격리된 메시지 및 파일 관리하기](manage-quarantined-messages-and-files.md) <p> [Quarantined messages FAQ](quarantine-faq.yml) <p> [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md) <p> [Microsoft 365의 스팸 방지 메시지 헤더](anti-spam-message-headers.md) <p> 의 메시지 헤더 분석기를 사용하여 분리된 메시지의 메시지 [헤더를 분석할 수 있습니다.](https://mha.azurewebsites.net/)|
|Quarantine - 최종 사용자|[EOP에서 사용자 권한으로 격리된 메시지 찾기 및 해제하기](find-and-release-quarantined-messages-as-a-user.md) <p> [검란 알림을 사용하여 검란된 메시지 릴리스 및 보고](use-spam-notifications-to-release-and-report-quarantined-messages.md) <p> [격리 정책](quarantine-policies.md)|
|**메일 흐름**||
|메일 흐름 규칙|[메일 흐름 규칙(전송 규칙) Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) <p> [Exchange Online의 메일 흐름 규칙 조건 및 예외(조건자)](/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions) <p> [Exchange Online의 메일 흐름 규칙 작업](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions) <p> [Exchange Online에서 메일 흐름 규칙 관리](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) <p> [흐름 규칙 절차 Exchange Online 메일](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-procedures)|
|허용 도메인|[Exchange Online에서 허용 도메인 관리](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)|
|커넥터|[2013에서 커넥터를 사용하여 메일 흐름 Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)|
|커넥터에 대한 향상된 필터링|[서버의 커넥터에 대한 Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)|
|**모니터링**||
|메시지 추적|[메시지 추적](message-trace-scc.md) <p> [Exchange 센터의 메시지 추적](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)|
|전자 메일 & 공동 작업 보고서|[전자 메일 보안 보고서 보기](view-email-security-reports.md)|
|메일 흐름 보고서|[메일 흐름 보고서 보기](view-mail-flow-reports.md) <p> [Exchange 관리 센터의 메일 흐름 보고서](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|메일 흐름 인사이트|[메일 흐름 인사이트](mail-flow-insights-v2.md) <p> [Exchange 관리 센터의 메일 흐름 정보](/exchange/monitoring/mail-flow-insights/mail-flow-insights)|
|감사 보고서|[Exchange 관리 센터의 감사 보고서](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)|
|알림 정책|[알림 정책](../../compliance/alert-policies.md)|
|**SLA(서비스 수준 계약) 및 지원**||
|스팸 유효성 SLA|\> 99%|
|가양성 비율 SLA|\< 1:250,000|
|바이러스 검색 및 차단 SLA|알려진 바이러스의 100%|
|월별 작동 시간 SLA|99.999%|
|연중 무휴 24시간 전화 및 웹 기술 지원|[EOP에 대한 도움말 및 지원.](help-and-support-for-eop.md)|
|**기타 기능**||
|지역 중복 글로벌 서버 네트워크|EOP는 최상의 가용성을 제공하도록 설계된 데이터 센터의 전 세계 네트워크에서 실행됩니다. 자세한 내용은 이 문서 앞부분의 [EOP 데이터](#eop-datacenters) 센터 섹션을 참조하세요.|
|온-프레미스 서버가 메일을 수락할 수 없는 경우 메시지 큐 대기|지연 메시지는 하루 동안 큐에 남아 있습니다. 메시지 다시 시도는 받는 사람의 메일 시스템에서 다시 수신된 오류를 기반으로 합니다. 평균적으로 5분마다 메시지가 다시 시도됩니다. 자세한 내용은 [EOP 대기, 지연 및 반송 메시지 FAQ](eop-queued-deferred-and-bounced-messages-faq.yml)를 참조하세요.|
|Office 365 메시지 암호화 추가 기능으로 사용할 수 있는 기능|자세한 내용은 [Office 365의 암호화](../../compliance/encryption.md)를 참조하세요.|
|||
