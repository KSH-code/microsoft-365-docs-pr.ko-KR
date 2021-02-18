---
title: EOP 기능
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: 다음 표에는 EOP(Exchange 온라인 보호) 호스팅 전자 메일 필터링 서비스에서 사용할 수 있는 기능 목록이 나와 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7dbdf30df0659565d775bfba2cf968ac56f6a4ac
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286852"
---
# <a name="eop-features"></a>EOP 기능

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
-  [Exchange Online Protection 독립 실행형](exchange-online-protection-overview.md)

다음 표에는 EOP(Exchange 온라인 보호) 호스팅 전자 메일 필터링 서비스에서 사용할 수 있는 기능 목록이 나와 있습니다.

> [!TIP]
> 비즈니스용 [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) 로드맵은 예정된 새 기능에 대한 정보를 찾는 데 좋은 리소스입니다. 여러 EOP 구독 계획에서 사용할 수 있는 기능에 대한 폭넓은 정보는 [Exchange 온라인 보호 서비스 설명](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)에서 확인할 수 있습니다.

****

|기능|설명|
|---|---|
|**스팸 방지 보호 기능**||
|인바운드 스팸 검색|자세한 내용은 [Microsoft 365의](anti-spam-protection.md)스팸 방지 보호 기능을 참조하세요. <p> EOP로 온-프레미스 Exchange 사서함을 보호하는 독립 실행형 EOP 환경에서는 EOP 스팸 필터링 결과를 변환하여 정크 메일 규칙에 따라 메시지를 정크 메일 폴더로 이동하기 위해 온-프레미스 Exchange에서 메일 흐름 규칙(전송 규칙이라고도 함)을 구성해야 합니다. 자세한 내용은 하이브리드 환경의 정크 메일 폴더에 스팸을 배달하도록 독립 실행형 [EOP 구성을 참조하세요.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)|
|아웃바운드 스팸 검색|아웃바운드 메일을 보내는 데 서비스를 사용하는 경우 아웃바운드 스팸 방지 보호가 항상 사용하도록 설정됩니다. 자세한 내용은 아웃바운드 스팸 [보호를 참조하세요.](outbound-spam-controls.md)|
|후방산 보호|자세한 내용은 후방산자 및 [EOP를 참조하세요.](backscatter-messages-and-eop.md)|
|대량 메일 필터링|EOP는 BCL(대량 불만 임계값)을 사용하여 대량 전자 메일 메시지를 스팸으로 표시합니다. 자세한 내용은 다음 항목을 참조하세요. <p> [정크 이메일과 대량 이메일의 차이점이 무엇인가요?](what-s-the-difference-between-junk-email-and-bulk-email.md) <p> [EOP의 BCL(대량 불만 수준)](bulk-complaint-level-values.md) <p> [스팸 방지 정책 구성](configure-your-spam-filter-policies.md)|
|악성 URL 차단 목록|EOP에서는 메시지 내에서 알려진 악성 링크를 검색하는 데 도움이 되는 여러 URL 차단 목록을 사용합니다.|
|피싱 방지 보호 기능|EOP에는 750,000개의 알려진 스팸 발송자 도메인이 포함되어 있습니다.|
|스푸핑 방지 보호 기능|자세한 내용은 스푸핑 방지 보호 [기능을 참조하세요.](anti-spoofing-protection.md)|
|**스팸 관리**||
|수신이 안전한 보낸 사람 및 수신이 차단된 보낸 사람 구성|자세한 내용은 [수신이](create-safe-sender-lists-in-office-365.md) 가능한 보낸 사람 목록 만들기 및 수신 차단된 보낸 [사람 목록 만들기를 참조하세요.](create-block-sender-lists-in-office-365.md)|
|사용자 지정 스팸 방지 정책 만들기|세분성을 강화하기 위해 사용자 지정 스팸 방지 정책을 만들어 조직의 지정된 사용자, 그룹 또는 도메인에 적용할 수 있습니다. 사용자 지정 정책은 항상 기본 정책보다 우선하지만 사용자 지정 정책의 우선 순위(즉, 실행 순서)를 변경할 수 있습니다. 자세한 내용은 [스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.|
|스팸 필터링 메시지에 대한 작업 구성|예를 들어 콘텐츠가 필터링된 메시지를 삭제하거나 이러한 메시지를 격리 또는 정크 메일 폴더로 보낼 수 있습니다. 자세한 내용은 [스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.|
|다국어 스팸 필터링|특정 언어로 작성되거나 특정 국가나 지역에서 보낸 메시지를 필터링하도록 스팸 방지 필터링을 구성할 수 있습니다. 자세한 내용은 [스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.|
|Outlook 또는 웹용 Outlook(이전의 웹용 Outlook)을 통해 스팸 Outlook Web App|관리자 및 최종 사용자가 안전한 보낸 사람 목록 및 차단된 보낸 사람 목록을 만들 수 있습니다. 자세한 내용은 [Outlook의 정크 메일 설정에 대해 참조하세요.](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook) <p> EOP를 사용하여프레미스 사서함을 보호하는 경우 디렉터리 동기화를 사용하여 이러한 설정이 서비스에 동기화되도록 합니다. 디렉터리 동기화 설정에 대한 자세한 내용은 [EOP에서 메일 사용자 관리](manage-mail-users-in-eop.md)에서 "디렉터리 동기화를 사용하여 메일 사용자 관리"를 참조하세요.|
|Microsoft에 가짓 긍정 및 거짓 부정을 보고합니다.|자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.|
|최종 사용자 스팸 격리 알림|자세한 내용은 [최종](use-spam-notifications-to-release-and-report-quarantined-messages.md) 사용자 스팸 알림 및 최종 사용자 스팸 알림 [구성을 참조하세요.](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)|
|메시지를 확인, 찾기 및 관리합니다.|자세한 내용은 EOP에서 관리자로, 또는 사용자로 [Quarantined Messages](manage-quarantined-messages-and-files.md) 및 Files를 찾아서 릴리스하는 방법을 [참조하세요.](find-and-release-quarantined-messages-as-a-user.md)|
|스팸으로 차단된 메시지 헤더 보기|메시지 헤더를 확인한 후 메시지 헤더 분석기에서 헤더 텍스트를 복사하여 [](https://mha.azurewebsites.net/) 붙여넣어 메시지에 어떤 일이 일어나는지 찾을 수도 있습니다.|
|**맬웨어 방지 보호 기능**||
|여러 엔진 맬웨어 방지 보호|여러 맬웨어 방지 엔진을 사용하여 자동으로 고객을 항상 보호할 수 있습니다.|
|맬웨어 필터링을 사용하지 않도록 설정하는 능력|맬웨어 필터링을 사용하지 않도록 설정할 수 없습니다. Microsoft는 모든 고객에게 일관되고 엄격한 수준의 보호 기능을 제공하는 것이 이메일 메시징 환경을 보호하는 데 필요한 심층 방어 전략의 중요한 부분이라고 생각합니다. 따라서 모든 고객에 대해 맬웨어 필터링이 자동으로 사용하도록 설정됩니다.|
|메시지 본문 및 첨부 파일에 대한 맬웨어 검사|이 서비스는 메시지 본문 및 모든 메시지 첨부 파일의 활성 페이로드에서 맬웨어를 검사합니다.|
|기본 또는 사용자 지정 맬웨어 경고 알림|보낸 사람 또는 관리자에게 알림 메시지를 보낼 수 있습니다. 자세한 내용은 맬웨어 [방지 정책 구성을 참조하십시오.](configure-anti-malware-policies.md)|
|받는 사람 알림|메시지를 자동으로 검지하거나 메시지를 잠가 표준 또는 사용자 지정 텍스트가 포함된 단일 텍스트 파일로 대체된 모든 첨부 파일로 배달합니다. 자세한 내용은 맬웨어 [방지 정책 구성을 참조하십시오.](configure-anti-malware-policies.md)|
|일반 첨부 파일 필터링|항상 맬웨어로 생각되는 파일 형식 목록을 사용하도록 설정하고 사용자 지정할 수 있습니다. 자세한 내용은 [EOP의 맬웨어 방지 보호 기능을 참조하세요.](anti-malware-protection.md)|
|스파이웨어 방지 보호 기능|맬웨어 방지 보호는 바이러스 백신 및 스파이웨어 방지를 포괄합니다.|
|사용자 지정 맬웨어 필터 정책 만들기|세분성을 높이기 위해 사용자 지정 맬웨어 필터 정책을 만들어서 조직의 지정된 사용자, 그룹 또는 도메인에 적용할 수 있습니다. 사용자 지정 정책은 항상 기본 정책보다 우선하지만 사용자 지정 정책의 우선 순위(즉, 실행 순서)를 변경할 수 있습니다. 자세한 내용은 맬웨어 [방지 정책 구성을 참조하십시오.](configure-anti-malware-policies.md)|
|**메일 라우팅 및 커넥터**||
|조건부 메일 라우팅|자세한 내용은 [시나리오: Exchange Online에서 조건부 메일 라우팅](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing)을 참조하세요.|
|편의적 또는 강제 TLS|커넥터에서 기회적 또는 강제 TLS를 사용할 수 있습니다. 기회적 TLS는 TLS 연결을 시도하지만 TLS 연결이 실패한 경우 SMTP 연결을 사용 합니다. TLS 강제 적용은 TLS 연결을 적용합니다. 즉, TLS 연결이 실패하면 메시지가 거부됩니다. TLS, 보안 및 커넥터에 대한 자세한 내용은 [Set up connectors for secure mail flow with a partner organization](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)을 참조하세요.|
|국가별 라우팅(메일 흐름이 특정 지역으로 제한)|자세한 내용은 [Exchange Online Protection 개요](exchange-online-protection-overview.md)에서 "EOP 데이터 센터" 섹션을 참조하세요.|
|SMTP 연결 검사기 도구|이 도구를 사용하여 메일 흐름을 테스트하는 데 대한 자세한 내용은 [Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)커넥터의 유효성을 검사하여 메일 흐름 테스트를 참조하세요.|
|하위 도메인 일치|허용 도메인의 하위 도메인과의 메일 흐름을 설정하는 데 대한 자세한 내용은 [EOP의 메일 흐름을 참조하세요.](mail-flow-in-eop.md)|
|**메일 흐름 규칙**||
|정책 기반 필터링 및 작업|사용자 지정 정책은 Exchange 메일 흐름 규칙(전송 규칙)을 기반으로 합니다. 도메인, 키워드, 파일 이름, 파일 형식, 제목 줄, 메시지 본문, 보낸 사람, 받는 사람, 헤더 및 IP 주소별로 필터링할 수 있습니다. 자세한 내용은 Exchange Online Protection의 메일 흐름 [규칙(전송 규칙)을 참조하세요.](mail-flow-rules-transport-rules-0.md)|
|텍스트 패턴을 기준으로 필터링|메일 흐름 규칙은 배열 또는 정규식을 사용하여 텍스트를 일치할 수 있습니다. 또한 하나의 문자열 또는 문자열 배열을 사용하여 주소, 제목, 본문 또는 첨부 파일 이름과 같은 여러 메시지 속성을 일치시킬 수 있습니다. 자세한 내용은 Exchange Online Protection의 메일 흐름 [규칙(전송 규칙)을 참조하세요.](mail-flow-rules-transport-rules-0.md)|
|사용자 지정 사전|메일 흐름 규칙에는 긴 텍스트 및 키워드 목록이 포함되어 사용자 지정 사전과 동일한 기능을 제공합니다.|
|도메인별 정책 규칙|보낸 사람 또는 받는 사람 도메인 이름, IP 주소 범위, 주소 키워드 또는 패턴, 그룹 구성원 자격 및 기타 조건과 일치하도록 메일 흐름 규칙의 범위를 사용자 지정할 수 있습니다.|
|첨부 파일 검색|첨부 파일의 파일 이름, 확장명 및 내용을 검색하도록 규칙을 만들 수 있습니다.|
|보낸 사람에게 정책 규칙 알림 보내기|메시지를 거부하고 설명이 있는 메시지 거부 또는 확장 상태 코드 작업이 있는 메시지 거부를 통해  보낸에게 배달되지  않는 보고서(NDR 또는 반송 메시지라고도 알려지기)를 보낼 수 있습니다. 자세한 내용은 [Exchange Online의 메일 흐름 규칙 작업을 참조하세요.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)|
|메시지 리디렉션 또는 복사|메일 흐름 규칙은 리디렉션하고,Cc 또는 Bcc로 받는 사람을 추가하고, 받는 사람 및 기타 옵션을 추가할 수 있습니다. 자세한 내용은 [Exchange Online의 메일 흐름 규칙 작업을 참조하세요.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)|
|여러 규칙에서 규칙 우선 순위 조정|Exchange 관리 센터를 사용하여 규칙이 처리되는 순서를 변경할 수 있습니다.|
|메시지를 필터링한 다음 메시지의 라우팅 또는 특성을 변경합니다.|다양한 조건에 따라 메시지를 필터링한 다음 각 메시지에 일련의 동작을 적용할 수 있습니다. 자세한 내용은 Exchange Online Protection의 메일 흐름 [규칙(전송 규칙)을 참조하세요.](mail-flow-rules-transport-rules-0.md)|
|규칙에 따라 메시지의 SCL(스팸 지수)을 변경합니다.|전송 중인 메시지를 검사하고 선택한 기준에 따라 스팸 지수를 할당할 수 있습니다. 자세한 내용은 메일 흐름 규칙을 사용하여 메시지의 [SCL(스팸 지수)을 설정하세요.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)|
|메시지 첨부 파일 검사|첨부 파일의 내용 또는 첨부된 파일의 특성을 조사하고 발견된 항목에 따라 수행할 작업을 정의할 수 있습니다. 자세한 내용은 메일 흐름 규칙을 사용하여 Exchange Online의 메시지 첨부 파일을 [검사하는 방법을 참조하세요.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)|
|**관리**||
|웹 기반 관리|관리자는 60개 언어로 지원되는 EAC(Exchange 관리 센터)에서 서비스를 관리할 수 있습니다. 자세한 내용은 독립 실행형 [EOP의 Exchange 관리 센터를 참조하세요.](exchange-admin-center-in-exchange-online-protection-eop.md)|
|디렉터리 동기화|디렉터리 동기화는 Azure Active Directory 동기화 도구를 통해 사용할 수 있습니다. 자세한 내용은 [EOP에서 메일 사용자 관리](manage-mail-users-in-eop.md)에서 "디렉터리 동기화를 사용하여 메일 사용자 관리" 섹션을 참조하세요.  |
|DBEB(디렉터리 기반 Edge 차단)|DBEB 기능을 통해 서비스 네트워크 주변에서 잘못된 받는 사람에 대한 메시지를 거부할 수 있습니다. DBEB를 사용하면 관리자가 메일 사용이 가능한 받는 사람을 Microsoft 365에 추가하고 Microsoft 365에 없는 전자 메일 주소로 전송된 모든 메시지를 차단할 수 있습니다. DBEB 구성에 대한 자세한 내용은 디렉터리 기반 Edge 차단을 사용하여 잘못된 받는 사람에게 보낸 메시지를 [거부합니다.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|
|PowerShell|전체 EOP 기능은 독립 실행형 EOP PowerShell에서 사용할 수 있습니다. 자세한 내용은 [Exchange Online Protection PowerShell을 참조하세요.](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell)|
|**보고 및 로깅**||
|Message trace|관리자는 서비스를 통과할 때 전자 메일 메시지를 팔로우할 수 있습니다. 서비스에서 대상 전자 메일 메시지를 수신, 거부, 지연 또는 배달할지 여부를 결정할 수 있습니다. 이를 통해 사용자의 질문에 효율적으로 답변하고, 메일 흐름 문제를 해결하고, 정책 변경의 유효성을 검사하고, 기술 지원에 도움을 요청해야 하는 필요성을 해결할 수 있습니다. 자세한 내용은 [보안 및 준수 센터 메시지 추적](message-trace-scc.md)을 참조하세요.|
|웹 기반 보고서|보안 및 준수 센터의 메일 보호 & 데이터를 제공합니다. 예를 들어 검색되는 스팸 및 맬웨어의 수 또는 메일 흐름 규칙이 일치되는 정도를 모니터링할 수 있습니다. 이러한 대화형 보고서를 사용하여 최대 90일 이전의 요약 데이터에 대한 시각적 보고서를 빠르게 보고 개별 메시지의 세부 정보를 드릴다운할 수 있습니다. 자세한 내용은 메일 보호 보고서를 사용하여 맬웨어, 스팸 및 규칙 검색에 대한 [데이터를 볼 수 있습니다.](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports)|
|감사 로깅|EOP 관리에 관리자 역할 그룹 보고서 및 관리자 감사 로그를 사용할 수 있습니다. 자세한 내용은 [EOP의 감사 보고서](auditing-reports-in-eop.md)를 참조하세요.  |
|**SLA(서비스 수준 계약) 및 지원**||
|스팸 유효성 SLA|\> 99%|
|가양성 비율 SLA|\< 1:250,000|
|바이러스 검색 및 차단 SLA|알려진 바이러스의 100%|
|월별 작동 시간 SLA|99.999%|
|연중 무휴 24시간 전화 및 웹 기술 지원|EOP 도움말 및 지원 옵션에 대한 자세한 내용은 [EOP에 대한 도움말 및 지원](help-and-support-for-eop.md)을 참조하세요.|
|**기타 기능**||
|지역 중복 글로벌 서버 네트워크|EOP는 최상의 가용성을 제공하도록 설계된 데이터 센터의 전 세계 네트워크에서 실행됩니다. 자세한 내용은 [Exchange Online Protection 개요](exchange-online-protection-overview.md)에서 "EOP 데이터 센터" 섹션을 참조하세요.  |
|온-프레미스 서버가 메일을 수락할 수 없는 경우 메시지 큐 대기|지연 메시지는 하루 동안 큐에 남아 있습니다. 메시지 다시 시도는 받는 사람의 메일 시스템에서 다시 수신된 오류를 기반으로 합니다. 평균적으로 5분마다 메시지가 다시 시도됩니다. 자세한 내용은 [EOP 대기, 지연 및 반송 메시지 FAQ](eop-queued-deferred-and-bounced-messages-faq.md)를 참조하세요.|
|추가 서비스로 사용할 수 있는 Office 365 메시지 암호화|자세한 내용은 [Office 365의 암호화](../../compliance/encryption.md)를 참조하세요.|
|
