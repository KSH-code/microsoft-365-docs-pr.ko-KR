---
title: '2단계: 설치를 Office 365 Microsoft Defender로 마이그레이션'
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
description: 타사 보호 서비스 또는 장치에서 Microsoft Defender로의 마이그레이션을 시작하는 단계를 Office 365 수행합니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 70ccdf6fe80a802bafec6617c19488af88040478
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60779188"
---
# <a name="migrate-to-microsoft-defender-for-office-365---phase-2-setup"></a>Microsoft Defender로 마이그레이션하여 Office 365 - 2단계: 설치

**적용 대상:**
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)

<br>

|[![1단계: 준비.](../../media/phase-diagrams/prepare.png)](migrate-to-defender-for-office-365-prepare.md) <br> [1 단계: 준비](migrate-to-defender-for-office-365-prepare.md)|![2단계: 설정.](../../media/phase-diagrams/setup.png) <br> 2 단계: 설정|[![3단계: 온보드.](../../media/phase-diagrams/onboard.png)](migrate-to-defender-for-office-365-onboard.md) <br> [3 단계: 온보딩](migrate-to-defender-for-office-365-onboard.md)|
|---|---|---|
||*여기 있습니다!*||

**2단계:** Microsoft **[Defender로의](migrate-to-defender-for-office-365.md#the-migration-process)** 마이그레이션 설정 Office 365! 이 마이그레이션 단계에는 다음 단계가 포함됩니다.

1. [파일럿 사용자를 위한 메일 그룹 만들기](#step-1-create-distribution-groups-for-pilot-users)
2. [사용자 메시지 보고를 위한 사용자 제출 구성](#step-2-configure-user-submission-for-user-message-reporting)
3. [SCL=-1 메일 흐름 규칙 유지 관리 또는 만들기](#step-3-maintain-or-create-the-scl-1-mail-flow-rule)
4. [커넥터에 대한 향상된 필터링 구성](#step-4-configure-enhanced-filtering-for-connectors)
5. [파일럿 보호 정책 만들기](#step-5-create-pilot-protection-policies)

## <a name="step-1-create-distribution-groups-for-pilot-users"></a>1단계: 파일럿 사용자를 위한 메일 그룹 만들기

메일 그룹은 마이그레이션의 Microsoft 365 측면에서 메일 그룹에 필요합니다.

- **SCL=-1** 메일 흐름 규칙에 대한 예외: 파일럿 사용자가 Office 365 보호를 위해 Defender의 모든 효과를 얻게 하려고 하여 들어오는 메시지를 Defender에서 검사해야 Office 365. 이 작업을 위해 서버의 적절한 메일 그룹에서 파일럿 사용자를 정의하고 Microsoft 365 이러한 그룹을 SCL=-1 메일 흐름 규칙에 대한 예외로 구성합니다.

  Onboard [2: (Optional) Exempt pilot users from filtering by your existing protection service에서](migrate-to-defender-for-office-365-onboard.md#step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service)설명한 바와 같이 기존 보호 서비스에서 이와 동일한 파일럿 사용자를 검사하지 못하게 해야 합니다. 기존 보호 서비스에서 필터링할 가능성을 없애고 Office 365 위해 Defender에 독점적으로 사용할 수 있는 것은 마이그레이션이 완료된 후 진행될 결과를 가장 잘 표현한 것입니다.

- Office 365 보호 기능에 대한 특정 **Defender** 테스트: 파일럿 사용자에게도 한 번만 모든 기능을 켜고 싶지는 않습니다. 파일럿 사용자에게 적용된 보호 기능에 대해 단계적 접근 방식을 사용하는 경우 문제 해결 및 조정이 훨씬 쉬워집니다. 이 방법을 염두에 두면 다음과 같은 메일 그룹이 권장됩니다.
  - **첨부 금고** 파일럿 그룹: 예: **MDOPilot \_ SafeAttachments**
  - 링크 금고 파일럿 **그룹:** 예: **MDOPilot \_ SafeLinks**
  - **표준 스팸 방지** 및 피싱 방지 정책 설정에 대한 파일럿 그룹: 예: **MDOPilot \_ SpamPhish \_ Standard**
  - **엄격한 스팸 방지** 및 피싱 방지 정책 설정에 대한 파일럿 그룹: 예: **MDOPilot \_ SpamPhish \_ Strict**

명확히 설명하기 위해 이 문서 전체에서 이러한 특정 그룹 이름을 사용하지만 자체 명명 규칙을 자유롭게 사용할 수 있습니다.

테스트를 시작할 준비가 되면 이러한 그룹을 [SCL=-1](#step-3-maintain-or-create-the-scl-1-mail-flow-rule)메일 흐름 규칙 에 예외로 추가합니다. Defender for Office 365 보호 기능에 대한 정책을 만들 때 이러한 그룹을 정책이 적용되는 사용자 정의 조건으로 사용할 수 있습니다.

**참고:**

- Standard 및 Strict 용어는 권장 보안 설정에서 [제공됩니다.](recommended-settings-for-eop-and-office365.md)이 설정은 미리 설정한 보안 정책에서도 [사용됩니다.](preset-security-policies.md) 이상적으로 표준 및 엄격한 미리 설정 보안 정책에서 파일럿 사용자를 정의할 것을 알려 주지만 이 작업을 할 수 없습니다. 이유 미리 설정한 보안 정책(특히 메시지에 대해 수행된 작업 또는 가장 보호 설정 조정)의 설정을 사용자 지정할 수 없습니다. 마이그레이션 테스트 중에 메시지에 대해 Office 365 Defender가 어떤 작업을 수행하고, 어떤 일이 일어나는지 확인하고, 정책 구성을 조정하여 이러한 결과를 허용하거나 방지할 수 있습니다.

  따라서 미리 설정한 보안 정책을 사용하는 대신 매우 유사하지만 경우에 따라 표준 및 엄격한 미리 설정 보안 정책의 설정과 다른 설정을 사용하여 사용자 지정 정책을 수동으로 만들 수 있습니다.

- Standard 또는 Strict 권장  값과 크게 다른 설정을 실험하려면 이러한 시나리오에서 파일럿 사용자에 대해 추가 및 특정 메일 그룹을 만들고 사용하는 것이 좋습니다. 구성 분석기를 사용하여 설정의 보안을 볼 수 있습니다. 자세한 내용은 [EOP의](configuration-analyzer-for-security-policies.md)보호 정책에 대한 구성 분석기 및 Microsoft Defender for Office 365.

  대부분의 조직에서 가장 좋은 방법은 권장되는 표준 설정과 밀접하게 부합하는 정책으로 시작하는 것입니다. 사용 가능한 시간 프레임에서 할 수 있는 만큼의 관찰 및 피드백을 제공한 후 나중에 보다 적극적인 설정으로 이동할 수 있습니다. 정크 메일 폴더와 정크 메일 폴더로의 배달을 가장하려면 사용자 지정이 필요할 수 있습니다.

  사용자 지정된 정책을 사용하는 경우 마이그레이션에 대한  권장 설정이 포함된 정책 앞에 적용해야 합니다. 사용자가 같은 유형의 여러 정책(예: 피싱 방지)에서 식별된 경우 해당 유형의 정책이 정책의 우선 순위 값에 따라 사용자에게 하나만 적용됩니다. 자세한 내용은 전자 메일 보호의 순서 및 [우선 순위를 참조하세요.](how-policies-and-protections-are-combined.md)

## <a name="step-2-configure-user-submission-for-user-message-reporting"></a>2단계: 사용자 메시지 보고를 위한 사용자 전송 구성

사용자가 마이그레이션을 위해 Defender에서 가짓 긍정 또는 거짓 Office 365 식별하는 능력은 마이그레이션의 중요한 부분입니다.

사용자가 악성 또는 Exchange Online 것으로 보고하는 메시지를 받기 위해 사서함을 지정할 수 있습니다. 자세한 내용은 [사용자가 보고한 메시지 설정을 참조하세요.](user-submission.md) 이 사서함은 사용자가 Microsoft에 제출한 메시지의 복사본을 받을 수 있습니다. 또는 사서함은 메시지를 Microsoft에 보고하지 않고 가로채 메시지를 가로채도 됩니다(보안 팀에서 수동으로 메시지를 분석하고 전송할 수 있습니다). 그러나 이 가로채기 방식에서는 서비스가 자동으로 조정하고 학습할 수 없습니다.

또한 파일럿의 모든 사용자에게 사용자 제출과 호환되는 지원되는 메시지 보고 Outlook 설치해야 합니다. 이러한 앱에는 다음이 포함됩니다.

- [보고서 메시지 추가 기능](enable-the-report-message-add-in.md)
- [피싱 보고 추가 기능](enable-the-report-phish-add-in.md)
- 여기에 설명된 바와 같이 지원되는 타사 보고 [도구](user-submission.md#third-party-reporting-tools)

이 단계의 중요성을 소중히 생각하지 않습니다. 사용자 제출의 데이터는 마이그레이션 전후에 양호하고 일관된 최종 사용자 환경을 확인하는 데 필요한 피드백 루프를 제공합니다. 이 피드백은 정보를 통해 정책 구성을 결정하고, 마이그레이션이 원활하게 진행된 관리에 데이터 백업 보고서를 제공하는 데 도움이 됩니다.

전체 조직의 경험에 의해 지원되는 데이터를 기반으로 하는 대신 두 개 이상의 마이그레이션으로 인해 단일 부정적인 사용자 환경을 기반으로 감정적인 추측이 일어 냈습니다. 또한 피싱 시뮬레이션을 실행한 경우 사용자의 피드백을 사용하여 조사가 필요할 수 있는 위험한 문제가 표시될 때 이를 알릴 수 있습니다.

## <a name="step-3-maintain-or-create-the-scl-1-mail-flow-rule"></a>3단계: SCL=-1 메일 흐름 규칙 유지 관리 또는 만들기

인바운드 전자 메일은 Microsoft 365 앞에 있는 다른 보호 서비스를 통해 라우팅되는 것이기 때문에 모든 받는 메일의 SCL(스팸 지수)을 -1(스팸 필터링 무시) 값으로 설정하는 메일 흐름 규칙(전송 규칙Exchange Online)이 이미 있을 가능성이 큼. 대부분의 타사 보호 서비스는 서비스를 사용하려는 Microsoft 365 SCL=-1 메일 흐름 규칙을 권장합니다.

Microsoft 필터링 스택(예: IP 허용 목록)을 다시 설정하는 다른 메커니즘을 사용하는 경우 타사 보호 서비스에서 모든 인바운드 인터넷 메일이 전송되는 한 SCL=-1 메일 흐름 규칙을 사용하는 것이 좋습니다Microsoft 365(인터넷에서 인터넷으로 직접 메일이 Microsoft 365). 

다음과 같은 이유로 마이그레이션 중에 SCL=-1 메일 흐름 규칙이 중요합니다.

- 위협 [탐색기를](email-security-in-microsoft-defender.md) 사용하여 기존 보호 서비스의  결과에 영향을 주지 않고 메시지에 대해 Microsoft 스택의 기능을 사용할 수 있습니다.
- SCL=-1 메일 흐름 규칙에 대한 예외를 구성하여 Microsoft 365 필터링 스택에 의해 보호되는 사용자도 점진적으로 조정할 수 있습니다. 단, 이 문서의 부분에서 권장하는 파일럿 메일 그룹의 구성원은 예외입니다.

  MX 레코드를 컷오버하기 전 또는 Microsoft 365 조직의 모든 받는 사람에 대해 Microsoft 365 보호 스택의 전체 보호를 설정하기 위해 이 규칙을 사용하지 않도록 설정하게 됩니다.

자세한 내용은 [Use mail flow rules to set the spam confidence level (SCL) in messages in Exchange Online.](https://docs.microsoft.comexchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)

**참고:**

- 인터넷 메일이 기존 보호 서비스를 통해 직접  Microsoft 365 통과하도록 허용하려면 SCL=-1 메일 흐름 규칙(스팸 필터링을 무시하는 메일)을 기존 보호 서비스를 통해서만 통과한 메일로 제한해야 합니다. 필터가 없는 인터넷 메일이 사용자 사서함의 사용자 사서함에 Microsoft 365.

  기존 보호 서비스에서 이미 검사한 메일을 올바르게 식별하려면 SCL=-1 메일 흐름 규칙에 조건을 추가할 수 있습니다. 예제:

  - **클라우드 기반 보호** 서비스의 경우: 조직에 고유한 헤더 및 헤더 값을 사용할 수 있습니다. 헤더가 있는 메시지는 헤더에서 Microsoft 365. 헤더가 없는 메시지는 헤더를 통해 Microsoft 365
  - **사내 보호** 서비스 또는 장치의 경우: 원본 IP 주소를 사용할 수 있습니다. 원본 IP 주소의 메시지는 원본 IP 주소에서 Microsoft 365. 원본 IP 주소에서 전송되지 않은 메시지는 원본 IP 주소에서 Microsoft 365.

- 메일이 필터링되는지 여부를 제어하기 위해 MX 레코드만 사용하여 제어하지 않습니다. 보낸 사람이 MX 레코드를 쉽게 무시하고 전자 메일을 해당 레코드로 직접 보낼 Microsoft 365.

## <a name="step-4-configure-enhanced-filtering-for-connectors"></a>4단계: 커넥터에 대한 향상된 필터링 구성

가장 먼저 기존 보호 [](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 서비스에서 커넥터로의 메일 흐름에 사용되는 커넥터에 대해 커넥터에 대한 향상된 필터링(목록 건너뛰기)을 Microsoft 365.  인바운드 메시지 보고서를 사용하여 [커넥터를](/exchange/monitoring/mail-flow-reports/mfr-inbound-messages-and-outbound-messages-reports) 식별할 수 있습니다.

인터넷 메시지가 실제로 보낸 위치를 확인하려면 Office 365 커넥터에 대한 향상된 필터링이 필요합니다. 커넥터에 대한 향상된 필터링은 Microsoft 필터링 스택(특히 스푸핑 인텔리전스)의 정확도와 [위협](threat-explorer.md) 탐색기 및 AIR(자동화된 조사 & [응답)의](automated-investigation-response-office.md)위반 후 기능을 크게 향상시킵니다. [](anti-spoofing-protection.md)

커넥터에 대해 향상된 필터링을 올바르게 사용하도록 설정하려면 인바운드 메일을 커넥터로 라우팅하는 모든 타사 서비스 및/또는 사내 전자 메일 시스템 호스트의 공용 **IP** \* \* **\* \*** 주소를 Microsoft 365.

커넥터에 대한 향상된 필터링이 작동하고 있는지 확인하기 위해 들어오는 메시지에 다음 헤더 중 하나 또는 둘 다가 포함되어 있는지 확인해야 합니다.

- `X-MS-Exchange-SkipListedInternetSender`
- `X-MS-Exchange-ExternalOriginalInternetSender`

## <a name="step-5-create-pilot-protection-policies"></a>5단계: 파일럿 보호 정책 만들기

프로덕션 정책을 만들면 모든 사용자에게 적용되지 않은 경우에도 위협 탐색기 같은 [](threat-explorer.md) 위반 후 기능을 테스트하고 보안 대응 팀의 프로세스에 Office 365 대한 Defender 통합을 테스트할 수 있습니다.

> [!IMPORTANT]
> 정책의 범위는 사용자, 그룹 또는 도메인으로 지정될 수 있습니다. 세 가지를 모두 일치하는 사용자만 정책의 범위에 포함하기에 한 정책에서 세 가지를 모두 혼합하지 않는 것이 좋습니다. 파일럿 정책의 경우 그룹 또는 사용자를 사용하는 것이 좋습니다. 프로덕션 정책의 경우 도메인을 사용하는 것이 좋습니다. 사용자의 기본 전자 메일  도메인만 사용자가 정책의 범위에 속하는지 여부를 확인하는 것이 매우 중요합니다. 따라서 사용자의 보조 도메인에 대한 MX 레코드를 전환하는 경우 기본 도메인도 정책에 적용해야 합니다.

### <a name="create-pilot-safe-attachments-policies"></a>파일럿 금고 첨부 파일 정책 만들기

[금고 첨부 파일은](safe-attachments.md) MX 레코드를 전환하기 전에 Office 365 사용하도록 설정하고 테스트하는 가장 쉬운 Defender 기능입니다. 금고 첨부 파일에는 다음과 같은 이점이 있습니다.

- 최소 구성.
- 가음성의 가능성이 매우 낮습니다.
- SCL=-1 메일 흐름 규칙의 영향을 받지 않는 항상 켜지며 영향을 받지 않는 맬웨어 방지 보호와 유사한 동작입니다.

파일럿 금고 대한 첨부 파일 정책을 만들 수 있습니다.

권장 설정은 [첨부 파일 정책 금고 권장을 참조하세요.](recommended-settings-for-eop-and-office365.md#safe-attachments-policy-settings) Standard 및 Strict 권장 사항은 동일합니다. 정책을 만들 내용은 [Set up 금고 Attachments policies을 참조합니다.](set-up-safe-attachments-policies.md) **그룹 MDOPilot \_ SafeAttachments를** 정책 조건(정책이 적용되는 사람)으로 사용해야 합니다.

> [!IMPORTANT]
> 현재 첨부 파일 정책의 기본 금고 없습니다. MX 레코드를 전환하기 전에 전체 조직을 보호하는 금고 첨부 파일 정책이 있는 것이 좋습니다.

### <a name="create-pilot-safe-links-policies"></a>파일럿 금고 링크 정책 만들기

> [!NOTE]
> 이미 래핑되거나 다시 써진 링크는 지원되지 않습니다. 현재 보호 서비스가 이미 전자 메일 메시지의 링크를 줄 바꿈하거나 다시 써 있는 경우 파일럿 사용자에 대해 이 기능을 해제해야 합니다. 이러한 문제가 발생하지 않도록 하는 한 가지 방법은 링크 정책에서 다른 서비스의 URL 도메인을 금고 것입니다.
>
> 금고 지원되는 Office 앱에 대한 링크 보호는 모든 사용이 허가된 사용자에게 적용되는 전역 설정입니다. 특정 사용자에 대해 설정하거나 전역으로 해제할 수 있습니다. 자세한 내용은 앱에 대한 금고 [링크 보호 구성을 Office 365 참조하세요.](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-microsoft-365-defender-portal)

파일럿 금고 대한 링크 정책을 만들 수 있습니다. 금고 링크에서 가음성에 대한 가능성도 매우 낮지만, 첨부 파일럿보다 적은 수의 파일럿 사용자에 대해 이 금고 고려해야 합니다. 이 기능은 사용자 환경에 영향을 미치기 때문에 사용자를 교육하는 계획을 고려해야 합니다.

권장 설정은 권장되는 링크 [금고 설정을 참조하세요.](recommended-settings-for-eop-and-office365.md#safe-links-settings) Standard 및 Strict 권장 사항은 동일합니다. 정책을 만들 내용은 [Set up 금고 Links policies을 참조하세요.](set-up-safe-links-policies.md) **그룹 MDOPilot \_ SafeLinks를** 정책 조건(정책이 적용되는 사람)으로 사용해야 합니다.

> [!IMPORTANT]
> 현재는 링크 정책의 기본 금고 없습니다. MX 레코드를 전환하기 전에 전체 조직을 보호하는 금고 링크 정책이 있는 것이 좋습니다.

### <a name="create-pilot-anti-spam-policies"></a>파일럿 스팸 방지 정책 만들기

파일럿 사용자에 대해 두 가지 스팸 방지 정책을 만들 수 있습니다.

- 표준 설정을 사용하는 정책입니다. **그룹 MDOPilot \_ SpamPhish \_ Standard를** 정책 조건(정책이 적용되는 사람)으로 사용
- Strict 설정을 사용하는 정책입니다. **MDOPilot \_ SpamPhish \_ Strict** 그룹을 정책 조건(정책이 적용되는 사람)으로 사용 이 정책의 우선 순위가 표준 설정인 정책보다 우선 순위가 높아야 합니다(낮은 수).

권장 표준 및 엄격한 설정은 권장 스팸 방지 정책 설정 [을 참조하세요.](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings) 정책을 만들 내용은 [Configure anti-spam policies을 참조합니다.](configure-your-spam-filter-policies.md)

### <a name="create-pilot-anti-phishing-policies"></a>파일럿 피싱 방지 정책 만들기

파일럿 사용자에 대해 다음 두 가지 피싱 방지 정책을 만들 수 있습니다.

- 아래 설명된 가장 검색 작업을 제외하고 표준 설정을 사용하는 정책입니다. **그룹 MDOPilot \_ SpamPhish \_ Standard를** 정책 조건(정책이 적용되는 사람)으로 사용
- 아래에 설명된 가장 검색 작업을 제외하고 Strict 설정을 사용하는 정책입니다. **MDOPilot \_ SpamPhish \_ Strict** 그룹을 정책 조건(정책이 적용되는 사람)으로 사용 이 정책의 우선 순위가 표준 설정인 정책보다 우선 순위가 높아야 합니다(낮은 수).

스푸핑 검색의 경우 권장되는 표준 작업은 메시지를 받는 사람의 정크 메일 폴더로 이동으로 이동으로, 권장되는 Strict 작업은 메시지 을 **Quarantine 입니다.** 스푸핑 인텔리전스 정보를 사용하여 결과를 관찰합니다. 다음 섹션에서는 Overrides에 대해 설명합니다. 자세한 내용은 [EOP의 스푸핑 인텔리전스 인사이트](learn-about-spoof-intelligence.md)를 참조하세요.

가장 검색의 경우 파일럿 정책에 대해 권장되는 표준 및 엄격한 작업을 무시합니다. 대신 다음 설정에  대해 작업을 적용하지 않습니다. 값을 사용합니다.

- **가장된 사용자로 메시지가 검색된 경우**
- **가장된 도메인으로 메시지가 검색된 경우**
- **사서함 인텔리전스에서 가장된 사용자를 검색하는 경우**

가장 정보를 사용하여 결과를 관찰합니다. 자세한 내용은 에 [대한 Defender의](impersonation-insight.md)가장 정보를 Office 365.

스푸핑 방지를 조정하고(허용 및 차단 조정) 각 가장 보호 작업을 켜서 메시지를 정크 메일 폴더(표준 또는 엄격한 권장 사항에 따라)에 따라 정크 메일 폴더로 검역하거나 이동합니다. 결과를 관찰하고 필요한 경우 설정을 조정할 수 있습니다.

자세한 내용은 아래 항목을 참조하세요.

- [스푸핑 방지 보호 기능](anti-spoofing-protection.md)
- [피싱 방지 정책의 가장 설정](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [에 대해 Defender에서](configure-mdo-anti-phishing-policies.md)피싱 방지 정책을 Office 365.

## <a name="next-step"></a>다음 단계

**축하합니다!** You have completed the **Setup** phase of your [migration to Microsoft Defender for Office 365!](migrate-to-defender-for-office-365.md#the-migration-process)

- [3단계: 온보더로 진행합니다.](migrate-to-defender-for-office-365-onboard.md)
