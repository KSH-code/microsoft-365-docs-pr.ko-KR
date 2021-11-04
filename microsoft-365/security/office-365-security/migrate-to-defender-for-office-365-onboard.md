---
title: '3단계: 온보딩을 Office 365 Microsoft Defender로 마이그레이션'
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: migrationguides
description: 타사 보호 서비스 또는 장치에서 Microsoft Defender로 마이그레이션하기 위한 단계를 Office 365 완료합니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a218aa1e86bd696079bb2c77b630bcf870bc0c25
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60779191"
---
# <a name="migrate-to-microsoft-defender-for-office-365---phase-3-onboard"></a>Microsoft Defender로 마이그레이션 Office 365 - 3단계: 온보딩

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)

<br>

|[![1단계: 준비.](../../media/phase-diagrams/prepare.png)](migrate-to-defender-for-office-365-prepare.md) <br> [1 단계: 준비](migrate-to-defender-for-office-365-prepare.md)|[![2단계: 설정.](../../media/phase-diagrams/setup.png)](migrate-to-defender-for-office-365-setup.md) <br> [2 단계: 설정](migrate-to-defender-for-office-365-setup.md)|![3단계: 온보드.](../../media/phase-diagrams/onboard.png) <br> 3 단계: 온보딩|
|---|---|---|
|||*여기 있습니다!*|

**3단계:** Microsoft **[Defender로의](migrate-to-defender-for-office-365.md#the-migration-process)** 마이그레이션 온보딩을 Office 365! 이 마이그레이션 단계에는 다음 단계가 포함됩니다.

1. [보안 및 보안 Teams](#step-1-begin-onboarding-security-teams)
2. [(선택 사항) 기존 보호 서비스의 파일럿 사용자 필터링 제외](#step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service)
3. [스푸핑 인텔리전스 조정](#step-3-tune-spoof-intelligence)
4. [가장 보호 및 사서함 인텔리전스 조정](#step-4-tune-impersonation-protection-and-mailbox-intelligence)
5. [사용자 제출의 데이터를 사용하여 측정 및 조정](#step-5-use-data-from-user-submissions-to-measure-and-adjust)
6. [(선택 사항) 파일럿에 사용자 추가 및 추가](#step-6-optional-add-more-users-to-your-pilot-and-iterate)
7. [모든 Microsoft 365 보호를 확장하고 SCL=-1 메일 흐름 규칙을 해제합니다.](#step-7-extend-microsoft-365-protection-to-all-users-and-turn-off-the-scl-1-mail-flow-rule)
8. [MX 레코드 전환](#step-8-switch-your-mx-records)

## <a name="step-1-begin-onboarding-security-teams"></a>1단계: 보안 관리 온보더링 Teams

조직에 보안 대응 팀이 있는 경우 이제 티켓 시스템을 포함하여 Office 365 프로세스에 Microsoft Defender를 통합하기 시작할 시간입니다. 이 항목은 전체 항목 자체에 해당하지만 간과하기도 합니다. 보안 대응 팀을 조기 구성하면 MX 레코드를 전환할 때 조직에서 위협을 대응할 준비가 되도록 할 수 있습니다. 인시던트 대응을 잘 갖추어 다음 작업을 처리해야 합니다.

- 새 도구를 알아보고 기존 흐름에 통합합니다. 예제:
  - 분리된 메시지의 관리자 관리가 중요합니다. 자세한 내용은 [관리자로 quarantined messages and files를 참조하세요.](manage-quarantined-messages-and-files.md)
  - 메시지 추적을 사용하면 메시지가 메시지에 들어오거나 메시지에서 나갈 때 어떤 일이 Microsoft 365. 자세한 내용은 의 최신 Exchange 관리 센터의 메시지 [추적을 Exchange Online.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)
- 조직에 들어와 있을 수 있는 위험을 식별합니다.
- 조직 [프로세스에 대한 알림을](../../compliance/alert-policies.md) 조정하고 사용자 지정합니다.
- 인시던트 큐를 관리하고 잠재적인 위험을 수정합니다.

조직에서 Office 365 계획 2용 Microsoft Defender를 구입한 경우 위협 탐색기, 고급 헌팅 및 인시던트와 같은 기능을 익히고 사용을 시작해야 합니다. 관련 교육은 을(를) <https://aka.ms/mdoninja> 참조합니다.

보안 응답 팀이 필터되지 않은 메시지를 수집하고 분석하는 경우 이러한 필터되지 않은 메시지를 받도록 SecOps 사서함을 구성할 수 있습니다. 자세한 내용은 고급 배달 [정책에서 SecOps 사서함 구성을 참조하세요.](configure-advanced-delivery.md#use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy)

### <a name="siemsoar"></a>SIEM/SOAR

SIEM/SOAR과 통합하는 데 대한 자세한 내용은 다음 문서를 참조하세요.

- [Microsoft 365 Defender API 개요](/microsoft-365/security/defender/api-overview)
- [스트리밍 API](/microsoft-365/security/defender/streaming-api)
- [고급 헌팅 API](/microsoft-365/security/defender/api-advanced-hunting)
- [인시던트 API](/microsoft-365/security/defender/api-incident)

조직에 보안 대응 팀이나 기존 프로세스 흐름이 없는 경우 이번에는 조직의 Defender에서 기본적인 헌팅 및 응답 기능을 익숙해지며 Office 365. 자세한 내용은 위협 조사 및 [응답을 참조하세요.](office-365-ti.md)

### <a name="rbac-roles"></a>RBAC 역할

Office 365 Defender의 사용 권한은 RBAC(역할 기반 액세스 제어)를 기반으로 하며 Microsoft 365 Defender 포털의 [사용 권한에 설명되어 있습니다.](permissions-microsoft-365-security-center.md) 다음은 유의해야 할 중요한 사항입니다.

- Azure AD 역할은 해당 역할의 **모든** 워크로드에 대한 권한을 Microsoft 365. 예를 들어 Azure Portal의 보안 관리자에 사용자를 추가하면 모든 곳에서 보안 관리자 권한이 부여됩니다.
- & 포털의 전자 메일 Microsoft 365 Defender 공동 작업 역할은 Microsoft 365 Defender Portal, Microsoft 365 규정 준수 센터 및 이전 보안 & 규정 준수 센터에 대한 권한을 부여합니다. 예를 들어 Microsoft 365 Defender 포털에서 보안 관리자에 사용자를 추가하는 경우 보안  관리자 액세스 권한은 Microsoft 365 Defender 포털, Microsoft 365 규정 준수 센터 및 보안 & 준수 센터에서만 액세스할 수 있습니다.
- Microsoft 365 Defender 포털의 많은 기능은 Exchange Online PowerShell cmdlet을 기반으로 하므로 Exchange Online(특히 해당 역할 그룹에 액세스하려면 기술적으로 역할 그룹)의 역할 그룹 구성원 자격이 Exchange Online PowerShell cmdlet)
- Microsoft 365 Defender 포털에는 Azure AD 역할과 동등한 역할이 없는 전자 메일 & 공동 작업 역할이 있으며 보안 작업에 중요합니다(예: 미리 보기 역할 및 검색 및 제거 역할).

일반적으로 보안 담당자의 일부만 사용자 사서함에서 직접 메시지를 다운로드할 수 있는 추가 권한만 필요합니다. 이렇게 하려면 기본적으로 보안 읽기 권한자에 없는 추가 권한이 필요합니다.

## <a name="step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service"></a>2단계: (선택 사항) 기존 보호 서비스의 파일럿 사용자 필터링 제외

이 단계가 필요하지는 않은 경우 기존 보호 서비스에서 필터링을 무시할 파일럿 사용자를 구성하는 것을 고려해야 합니다. 이 작업을 수행하면 Defender가 Office 365  사용자에 대한 모든 필터링 및 보호 의무를 처리할 수 있습니다. 기존 보호 서비스에서 파일럿 사용자를 제외하지 않는 경우 defender for Office 365 다른 서비스의 누락(이미 필터링된 메시지 필터링)만 효과적으로 작동하게 됩니다.

> [!NOTE]
> 현재 보호 서비스에서 링크 래핑을 제공하지만 링크 기능을 파일럿하려는 경우 이 금고 필요합니다. 링크의 이중 래핑은 지원되지 않습니다.

## <a name="step-3-tune-spoof-intelligence"></a>3단계: 스푸핑 인텔리전스 조정

[스푸핑](learn-about-spoof-intelligence.md) 인텔리전스 정보를 확인하여 스푸핑으로 허용되거나 차단되는 정보를 확인하고 스푸핑에 대한 시스템 판정을 다시 설정해야 하는지 여부를 판단합니다. 업무상 중요한 전자 메일의 일부 원본이 DNS(SPF, DKIM 및 DMARC)의 전자 메일 인증 레코드를 잘못 구성한 경우 기존 보호 서비스에서 재지정을 사용하여 도메인 문제를 마스킹하고 있을 수 있습니다.

스푸핑 인텔리전스에서는 DNS에서 적절한 전자 메일 인증 레코드가 없는 도메인에서 전자 메일을 발송할 수 있지만 적절한 스푸핑과 잘못된 스푸핑을 구분하는 데 도움이 필요한 경우도 있습니다. 다음과 같은 유형의 메시지 원본에 초점을 맞추고 있습니다.

- 커넥터에 대한 향상된 필터링에 정의된 IP 주소 범위 외부에 있는 메시지 [원본입니다.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)
- 메시지 수가 가장 많은 메시지 원본입니다.
- 조직에 가장 큰 영향을 미치는 메시지 원본입니다.

스푸핑 인텔리전스에서는 사용자 제출을 구성한 후 자체적으로 조정하기 때문에 완벽한 구성이 필요하지 않습니다.

## <a name="step-4-tune-impersonation-protection-and-mailbox-intelligence"></a>4단계: 가장 보호 및 사서함 인텔리전스 조정

수행 모드 적용 안 에서 가장 보호의 결과를  관찰할 충분한 시간이 있는 경우 피싱 방지 정책에서 각 가장 보호 작업을 개별적으로 켜면 됩니다.

- 사용자 가장 보호: **표준** 및 엄격한 메시지 모두에 대해 메시지를 검역합니다.
- 도메인 가장 **보호:** 표준 및 엄격한 메시지 모두에 대해 메시지를 검역합니다.
- 사서함 인텔리전스 보호: 표준에 대한 받는 사람의 정크 메일 **폴더로 메시지** 이동 **Strict에 대한 메시지를 Quarantine** the message.

메시지에 대해 행동하지 않고 가장 보호 결과를 모니터링하는 기간이 길수록 식별해야 할 데이터가 수록 요구될 수 있는 허용 또는 차단이 더 많이 필요합니다. 관찰 및 조정을 허용할 만큼 충분히 중요한 각 보호를 켜는 사이에 지연을 사용하는 것이 있습니다.

> [!NOTE]
> 이러한 보호에 대한 빈번하고 지속적인 모니터링 및 조정이 중요합니다. 가짓 긍정이 의심되는 경우 원인을 조사하고 필요한 검색 기능에 한해 필요한 경우만 다시 를 사용하세요.

### <a name="tune-mailbox-intelligence"></a>사서함 인텔리전스 조정

사서함 인텔리전스가 가장 시도로 확인된 [](impersonation-insight.md)메시지에 대해 아무 작업도 수행하지 않고도 파일럿 사용자의 전자 메일 보내기 및 수신 패턴을 학습하고 있습니다. 외부 사용자가 파일럿 사용자 한 명과 연락하는 경우 해당 외부 사용자의 메시지는 사서함 인텔리전스를 통해 가장 시도로 식별되지 않습니다(따라서 가음성 감소).

준비가 되면 다음 단계를 수행하여 사서함 인텔리전스가 가장 시도로 검색된 메시지에 대한 작업을 수행하도록 허용합니다.

- 표준 보호 설정이 있는 피싱 방지 정책에서 사서함  인텔리전스에서 가장된 사용자를 검색하여 받는 사람의 정크 메일 폴더로 메시지 이동 값을 변경합니다. 

- 엄격한 보호 설정이 있는 피싱 방지 정책에서 사서함  인텔리전스가 사용자를 검색하고 가장하는 경우의 값을 메시지 를 **Quarantine으로 변경합니다.**

정책을 수정하려면 [Configure anti-phishing policies in Defender for Office 365.](configure-mdo-anti-phishing-policies.md)

결과를 관찰하고 조정한 후 다음 섹션으로 진행하여 사용자 가장에 의해 검색된 메시지를 검역합니다.

### <a name="tune-user-impersonation-protection"></a>사용자 가장 보호 조정

표준 및 엄격한 설정을 기반으로 하는 두 가지 피싱 방지  정책에서 가장된 사용자로 메시지가 검색된 경우의 값을 변경하여 메시지를 **검역합니다.**

가장 [정보를](impersonation-insight.md) 확인하여 사용자 가장 시도로 차단되는 것을 확인할 수 있습니다.

정책을 수정하려면 [Configure anti-phishing policies in Defender for Office 365.](configure-mdo-anti-phishing-policies.md)

결과를 관찰하고 조정한 후 다음 섹션으로 진행하여 도메인 가장에서 검색된 메시지를 검역합니다.

### <a name="tune-domain-impersonation-protection"></a>도메인 가장 보호 조정

표준 및 엄격한 설정을 기반으로 하는 두 가지 피싱 방지  정책에서 가장된 도메인으로 메시지가 검색된 경우의 값을 변경하여 메시지를 **검역합니다.**

가장 [정보를](impersonation-insight.md) 확인하여 도메인 가장 시도로 차단되는 것을 확인할 수 있습니다.

정책을 수정하려면 [Configure anti-phishing policies in Defender for Office 365.](configure-mdo-anti-phishing-policies.md)

결과를 관찰하고 필요한 경우 조정합니다.

## <a name="step-5-use-data-from-user-submissions-to-measure-and-adjust"></a>5단계: 사용자 제출의 데이터를 사용하여 측정 및 조정

파일럿 사용자가 가짓 긍정 및 거짓 부정을 보고하면 메시지는 파일럿 포털의 제출 [페이지에 Microsoft 365 Defender 표시됩니다.](admin-submission.md) 분석을 위해 Microsoft에 잘못 확인된 메시지를 보고하고 정보를 사용하여 필요한 경우 파일럿 경찰의 설정 및 예외를 조정할 수 있습니다.

다음 기능을 사용하여 Defender for Office 365.

- [격리](manage-quarantined-messages-and-files.md)
- [위협 탐색기](email-security-in-microsoft-defender.md)
- [전자 메일 보안 보고서](view-email-security-reports.md)
- [Defender for Office 365 보고서](view-reports-for-mdo.md)
- [메일 흐름 인사이트](/exchange/monitoring/mail-flow-insights/mail-flow-insights)
- [메일 흐름 보고서](/exchange/monitoring/mail-flow-reports/mail-flow-reports)

조직에서 사용자 보고서에 타사 서비스를 사용하는 경우 해당 데이터를 피드백 루프에 통합할 수 있습니다.

## <a name="step-6-optional-add-more-users-to-your-pilot-and-iterate"></a>6단계: (선택 사항) 파일럿에 사용자를 더 추가하고

문제를 찾아 해결할 때 파일럿 그룹에 사용자를 더 추가할 수 있으며, 그에 따라 새 파일럿 사용자가 기존 보호 서비스에서 검사하지 못하도록 적절하게 제외할 수 있습니다. 지금 테스트할수록 나중에 처리해야 하는 사용자 문제도 줄어듭습니다. 이 "워터파일" 접근 방식을 사용하면 조직의 더 많은 부분에 대해 조정할 수 있으며 보안 팀이 새 도구 및 프로세스에 적응할 시간을 제공합니다.

- Microsoft 365 정책에 의해 높은 신뢰도의 피싱 메시지가 허용되는 경우 경고가 생성됩니다. 이러한 메시지를 식별하기 위해 다음 옵션을 사용할 수 있습니다.
  - 위협 방지 상태 [보고서의 을(를)](view-email-security-reports.md#threat-protection-status-report)
  - 위협 탐색기에서 필터링하여 메시지를 식별합니다.
  - 고급 헌팅에서 필터링하여 메시지를 식별합니다.

  관리자 제출을 통해 가능한 한 일찍 Microsoft에 가짓 긍정을 보고하려면 테넌트 [허용/차단](tenant-allow-block-list.md) 목록 기능을 사용하여 이러한 가짓 긍정에 대해 안전한 다시 설정을 구성합니다.

- 불필요한 재지정을 검사하는 것이 좋습니다. 즉, 메시지에 제공한 Microsoft 365 판정을 살펴 봐야 합니다. Microsoft365에서 올바른 판정을 렌더링한 경우 다시 설정의 필요성이 크게 줄거나 제거됩니다.

## <a name="step-7-extend-microsoft-365-protection-to-all-users-and-turn-off-the-scl-1-mail-flow-rule"></a>7단계: Microsoft 365 보호를 모든 사용자로 확장하고 SCL=-1 메일 흐름 규칙을 해제합니다.

MX 레코드를 전환하여 MX 레코드를 전환할 준비가 된 경우 이 섹션의 Microsoft 365.

1. 파일럿 정책을 전체 조직으로 확장합니다. 기본적으로 이 작업을 하는 방법에는 여러 가지가 있습니다.
   - 미리 [설정한 보안 정책을](preset-security-policies.md) 사용하여 표준 보호 프로필과 Strict protection 프로필(모든 사용자가 적용된지 확인)으로 사용자를 나누는 방법을 제공합니다. 미리 설정한 보안 정책은 만든 사용자 지정 정책 또는 기본 정책 앞에 적용됩니다. 개별 파일럿 정책을 삭제하지 않고 해제할 수 있습니다.

     보안 정책을 미리 설정해야 하는 단점은 보안 정책을 만든 후 많은 중요한 설정을 변경할 수 없습니다.

   - 파일럿 중에 만들어 조정한 정책의 범위를 변경하여 모든 사용자(예: 모든 도메인의 모든 받는 사람)를 포함합니다. 동일한 유형의 여러 정책(예: 피싱 방지 정책)이 동일한 사용자(개별적으로, 그룹 구성원 또는 전자 메일 도메인)에 적용되는 경우 우선 순위가 가장 높은 정책 설정(가장 낮은 우선 순위 번호)만 적용되고 해당 유형의 정책에 대한 처리가 중지됩니다.

2. SCL=-1 메일 흐름 규칙을 끄면 됩니다(삭제하지 않고 해제할 수 있습니다).

3. 이전 변경 내용이 적용되었는지, 모든 사용자에 대해 Office 365 사용할 수 있는지 확인합니다. 이 시점에서 Office 365 Defender for Office 365 모든 받는 사람에 대한 메일에 대해 작업을 할 수 있지만 해당 메일은 기존 보호 서비스에 의해 이미 검색되었습니다.

대규모 데이터 기록 및 조정을 위해 이 단계에서 일시 중지할 수 있습니다.

## <a name="step-8-switch-your-mx-records"></a>8단계: MX 레코드 전환

> [!NOTE]
>
> - 도메인의 MX 레코드를 전환할 때 변경 내용이 인터넷에 전파될 때 최대 48시간이 걸릴 수 있습니다.
>
> - 더 빠른 응답과 가능한 롤백(필요한 경우)을 사용하려면 DNS 레코드의 TTL 값을 낮추는 것이 좋습니다. 전환이 완료 및 확인된 후 원래 TTL 값으로 되전할 수 있습니다.
>
> - 덜 자주 사용되는 도메인 변경부터 고려해야 합니다. 더 큰 도메인으로 이동하기 전에 일시 중지하고 모니터링할 수 있습니다. 그러나 이렇게 한다고 경우에도 보조 SMTP 도메인은 정책 응용 프로그램 이전에 기본 도메인으로 확인될 수 있기 때문에 모든 사용자 및 도메인이 정책에 적용될 수 있도록 해야 합니다.
>   
> - 단일 도메인에 대한 여러 MX 레코드가 기술적으로 작동하므로 이 문서의 모든 지침을 따랐을 경우 분할 라우팅을 사용할 수 있습니다. 특히, 정책이 모든 사용자에게 적용되고, SCL=-1 메일 흐름 규칙이 설치 [3단계: SCL=-1](migrate-to-defender-for-office-365-setup.md#step-3-maintain-or-create-the-scl-1-mail-flow-rule)메일 흐름 규칙 유지 관리 또는 만들기에 설명된 바와 같이 기존 보호 서비스를 통과하는 메일에만 적용해야 합니다. 그러나 이 구성에서는 문제 해결이 훨씬 더 어렵게 만드는 동작이 도입되어, 특히 장시간의 경우 일반적으로 권장되지 않습니다.
>
> - MX 레코드를 전환하기 전에 보호 서비스의 인바운드 커넥터에서 다음 설정이 사용되지 않는지 Microsoft 365. 일반적으로 커넥터에는 다음 설정 중 하나 이상이 구성됩니다.
>
>   - 이 도메인 *이름(RestrictDomainsToCertificate)과* 일치하는지 파트너가 인증하는 **데 Office 365** 인증서의 주체 이름을 요구합니다.
>   - **전자 메일 메시지가** 이 IP 주소 범위 내에서 전송되지 않은 경우 거부(RestrictDomainsToIPAddresses)
>
>   커넥터 유형이 **Partner인** 경우 이러한 설정 중 하나를 켜면 MX 레코드를 전환한 후 도메인으로의 모든 메일 배달이 실패합니다. 계속하기 전에 이러한 설정을 사용하지 않도록 설정해야 합니다. 커넥터가 하이브리드에 사용되는 사내 커넥터인 경우, 사내 커넥터를 수정할 필요가 없습니다. 그러나 파트너 커넥터의 유무를 확인할 **수** 있습니다.
>   
> - 현재 메일 게이트웨이에서 받는 사람 유효성 검사도 제공하는 경우 도메인이 [](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) 2013에서 권한이 있는 도메인으로 구성되어 있는지 Microsoft 365. 이렇게 하면 불필요한 반송 메시지를 방지할 수 있습니다.

준비가 되면 도메인의 MX 레코드를 전환합니다. 모든 도메인을 한에 마이그레이션할 수 있습니다. 또는 덜 자주 사용하는 도메인을 먼저 마이그레이션한 다음 나중에 나머지 도메인을 마이그레이션할 수 있습니다.

어떤 시점에서든 자유롭게 일시 중지하고 평가할 수 있습니다. 그러나 SCL=-1 메일 흐름 규칙을 해제하면 사용자에게 가짓 긍정을 검사하는 두 가지 환경이 서로 다를 수 있습니다. 일관된 단일 환경을 더 빨리 제공할 수 있을 때 누락된 메시지 문제를 해결해야 하는 사용자와 지원 센터 팀이 더 기까워지기만 하면 됩니다.

## <a name="next-steps"></a>다음 단계

축하합니다! You have completed your [migration to Microsoft Defender for Office 365!](migrate-to-defender-for-office-365.md#the-migration-process) 이 마이그레이션 가이드의 단계를 수행한 후 처음 며칠 동안 메일이 메일로 직접 배달되는 Microsoft 365 훨씬 매끄러워야 합니다.

이제 사용자에 대한 Defender의 정상적인 작동 및 유지 Office 365. 파일럿 중에 경험한 문제와 비슷하지만 더 큰 규모로 문제를 모니터링하고 감시합니다. 스푸핑 인텔리전스 [](impersonation-insight.md) [인사이트와](learn-about-spoof-intelligence.md) 가장 인사이트가 가장 유용하지만 다음 활동을 정기적으로 만드는 것이 고려됩니다.

- 사용자 제출, 특히 사용자가 보고한 [피싱 메시지를 검토합니다.](/microsoft-365/security/office-365-security/automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- 위협 방지 상태 보고서에서 재지정을 [검토합니다.](view-email-security-reports.md#threat-protection-status-report)
- 고급 [헌팅](/microsoft-365/security/defender/advanced-hunting-example.md) 쿼리를 사용하여 조정 기회 및 위험한 메시지를 검색합니다.
