---
title: 피싱 방지 보호 기능 조정
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- MET150
description: 관리자는 Microsoft 365에서 피싱 메시지를 통해 얻은 이유와 방법을 파악 하 고, 향후 피싱 메시지를 더 많이 방지 하기 위해 수행 해야 하는 작업에 대해 알아봅니다.
ms.openlocfilehash: e933769b6bce9eb10765fb2b58025445432bed18
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845471"
---
# <a name="tune-anti-phishing-protection"></a>피싱 방지 보호 기능 조정

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Microsoft 365에는 기본적으로 사용 하도록 설정 된 다양 한 피싱 방지 기능이 포함 되어 있지만 일부 피싱 메시지가 여전히 사서함으로 이동할 수 있습니다. 이 항목에서는 피싱 메시지가 발생 한 이유를 파악 하기 위해 수행할 수 있는 작업과 _실수로 작업을 더 악화 하지 않고_ Microsoft 365 조 직에서 피싱 방지 설정을 조정 하기 위해 수행할 수 있는 작업에 대해 설명 합니다.

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>첫 번째 작업: 손상 된 계정을 처리 하 고 더 이상 피싱 메시지를 수신 하지 못하도록 차단 합니다.

피싱 메시지의 결과로 받는 사람의 계정이 손상 된 경우 [Microsoft 365에서 손상 된 전자 메일 계정에 응답 하](responding-to-a-compromised-email-account.md)는 단계를 따르세요.

구독에 Office 365 용 Microsoft Defender가 포함 되어 있는 경우 [office 365 위협 인텔리전스](office-365-ti.md) 를 사용 하 여 피싱 메시지도 받은 다른 사용자를 식별할 수 있습니다. 피싱 메시지를 차단 하는 추가 옵션은 다음과 같습니다.

- [Microsoft Defender for Office 365의 안전한 링크](set-up-atp-safe-links-policies.md)

- [Microsoft Defender for Office 365의 안전한 첨부 파일](set-up-atp-safe-attachments-policies.md)

- [Office 365 용 Microsoft Defender의 피싱 방지 정책](configure-atp-anti-phishing-policies.md) 정책의 **고급 피싱 임계값** 을 **표준** 에서 일시적 **으로, 적극적** **으로 또는** **적극적인** 로 높일 수 있습니다.

이러한 Defender for Office 365 기능이 켜져 있는지 확인 합니다.

## <a name="report-the-phishing-message-to-microsoft"></a>Microsoft에 피싱 메시지 보고

보고 피싱 메시지는 Microsoft 365의 모든 고객을 보호 하는 데 사용 되는 필터를 조정할 때 유용 합니다. 자세한 내용은 [Microsoft에 메시지 및 파일 보고서](report-junk-email-messages-to-microsoft.md)를 참조 하십시오.

## <a name="inspect-the-message-headers"></a>메시지 헤더를 검사 합니다.

피싱 메시지의 헤더를 검사 하 여 더 많은 피싱 메시지를 통해 들어오는 것을 방지 하기 위해 수행할 수 있는 작업이 있는지 확인할 수 있습니다. 즉 메시지 헤더를 검사 하면에서 피싱 메시지를 허용 하는 일을 담당 하는 조직의 설정을 식별 하는 데 도움이 될 수 있습니다.

특히 SFV (스팸 필터링 결과) 값에서 건너뛴 스팸 또는 피싱 필터링이 표시 되는 메시지 헤더에서 **스팸 방지-Report** 헤더 필드를 확인 해야 합니다. 필터링을 건너뛰지 않는 메시지에는 항목이 있는데 `SCL:-1` ,이는 설정 중 하나에서 서비스에 의해 결정 된 스팸 또는 피싱 verdicts를 재정의 하 여이 메시지를 허용 한다는 것을 의미 합니다. 사용 가능한 모든 스팸 방지 및 피싱 메시지 헤더의 전체 목록 및 메시지 헤더를 가져오는 방법에 대 한 자세한 내용은 [스팸 방지 메시지 헤더 (Microsoft 365)](anti-spam-message-headers.md)를 참조 하십시오.

## <a name="best-practices-to-stay-protected"></a>보호를 유지 하기 위한 모범 사례

- 매월 보안 [점수](../mtp/microsoft-secure-score.md) 를 실행 하 여 조직의 security 설정을 평가 합니다.

- 실수로 격리 되거나, 허용 되는 메시지에 대해 차단 되는 메시지의 경우 [위협 탐색기 및 실시간](threat-explorer.md)검색에서 해당 메시지를 찾는 것이 좋습니다. 보낸 사람, 받는 사람 또는 메시지 ID 별로 검색할 수 있습니다. 메시지를 찾은 후 주제를 클릭 하 여 세부 정보로 이동 합니다. 격리 된 메시지의 경우 적절 한 방법으로 재정의 하는 데 사용할 수 있도록 "검색 기술"이 있던 것을 확인 합니다. 허용 되는 메시지에 대해 메시지를 허용 하는 정책을 확인 합니다. 

- 스푸핑된 메일에는 Defender for Office 365의 피싱로 태그가 지정 됩니다. 때로는 스푸핑이 심각 하지 않으며 사용자가 격리 하지 않을 수도 있습니다. 사용자에 게 미치는 영향을 최소화 하기 위해, 주기적으로 [스푸핑 인텔리전스 보고서](learn-about-spoof-intelligence.md)를 검토 합니다. 필요한 재정의를 검토 하 고 수행한 후에는 사용자의 정크 메일 폴더로 배달 하지 않고 의심 스러운 메시지를 **격리** 하도록 [스푸핑 인텔리전스를 구성](set-up-anti-phishing-policies.md#spoof-settings) 하는 것을 확신할 수 있습니다.

- 가장 (도메인 또는 사용자)에 대해 위의 단계를 반복할 수 있습니다. 가장 보고서는 **Threat Management** \> **Dashboard** \> **Insights** 에서 찾을 수 있습니다.

- [위협 방지 상태 보고서](view-reports-for-atp.md#threat-protection-status-report)를 주기적으로 검토 합니다.

- 일부 고객은 스팸 방지 정책의 보낸 사람 허용 또는 허용 도메인 목록에 자신의 도메인을 추가 하 여 피싱 메시지를 통과 하도록 할 수 있습니다. 이 구성에서는 일부 합법적인 메시지를 허용 하지만, 일반적으로 스팸 및/또는 피싱 필터에 의해 차단 되는 악성 메시지도 허용 됩니다. 도메인을 허용 하는 대신 근본적인 문제를 해결 해야 합니다.

  도메인의 보낸 사람을 포함 하는 Microsoft 365 (가양성)에 의해 차단 되는 합법적인 메시지를 처리 하는 가장 좋은 방법은 _모든_ 전자 메일 도메인의 DNS에서 SPF, DKIM 및 DMARC 레코드를 완전히 및 완전히 구성 하는 것입니다.

  - SPF 레코드에 도메인의 보낸 사람에 대 한 _모든_ 전자 메일 원본이 식별 되는지 확인 합니다 (타사 서비스를 잊지 마십시오.).

  - \-무단 보낸 사람이이를 수행 하도록 구성 된 전자 메일 시스템에 의해 거부 되도록 하려면 하드 실패 (모두)를 사용 합니다. [스푸핑 인텔리전스](learn-about-spoof-intelligence.md) 를 사용 하면 SPF 레코드에 권한이 부여 된 타사 보낸 사람을 포함할 수 있도록 도메인을 사용 중인 보낸 사람을 식별 하는 데 도움이 됩니다.

  구성 지침에 대해서는 다음을 참조 하세요.
  
  - [스푸핑을 방지할 수 있도록 SPF 설정](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [DKIM을 사용하여 사용자 지정 도메인에서 전송한 아웃바운드 전자 메일의 유효성 검사](use-dkim-to-validate-outbound-email.md)

  - [DMARC를 사용하여 전자 메일의 유효성 검사](use-dmarc-to-validate-email.md)

- 가능한 경우에는 항상 도메인에 대 한 전자 메일을 Microsoft 365로 직접 배달 하는 것이 좋습니다. 즉, Microsoft 365 도메인의 MX 레코드를 Microsoft 365로 가리킵니다. EOP (Exchange Online Protection)은 메일이 Microsoft 365로 직접 배달 될 때 클라우드 사용자에 게 최상의 보호를 제공할 수 있습니다. EOP 앞에 타사 전자 메일 바이러스 예방 시스템을 사용 해야 하는 경우에는 커넥터에 대 한 고급 필터링을 사용 합니다. 자세한 내용은 [Exchange Online의 커넥터에 대 한 향상 된 필터링](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)을 참조 하십시오.

- 사용자가 Microsoft에 [메시지를 보고](enable-the-report-message-add-in.md) 하 여 시스템을 훈련 시킬 수 있도록 해야 합니다. 관리자는 [관리자 전송](admin-submission.md) 기능도 함께 활용 해야 합니다.

- MFA (multi-factor authentication)는 손상 된 계정을 방지 하는 좋은 방법입니다. 모든 사용자에 대해 MFA를 사용 하도록 설정 하는 것이 좋습니다. 단계적 접근 방식에서는 모든 사용자에 대해 MFA를 사용 하도록 설정 하기 전에 가장 중요 한 사용자 (관리자, 임원 등)에 대해 MFA를 사용 하도록 설정 하는 것부터 시작 합니다. 자세한 내용은 [다단계 인증 설정을](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)참조 하십시오.

- 외부 받는 사람에 게 규칙을 전달 하는 경우 공격자가 데이터를 추출 하는 경우가 많습니다. [Microsoft 보안 점수](../mtp/microsoft-secure-score.md) 에서 **사서함 전달 규칙 검토** 정보를 사용 하 여 외부의 받는 사람에 대 한 전달 규칙을 찾아이를 방지할 수도 있습니다. 자세한 내용은 [보안 점수를 사용한 클라이언트 외부 전달 규칙 완화](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)를 참조 하세요.
