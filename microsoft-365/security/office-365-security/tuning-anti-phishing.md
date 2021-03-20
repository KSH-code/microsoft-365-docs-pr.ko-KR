---
title: 피싱 방지 보호 기능 조정
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- MET150
description: 관리자는 Microsoft 365에서 피싱 메시지가 통과하는 이유와 방법을 파악하고 향후 더 많은 피싱 메시지를 방지하는 방법을 확인할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 84159ef08324ed0a895d84e6c9c19f429e227fa1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908141"
---
# <a name="tune-anti-phishing-protection"></a>피싱 방지 보호 기능 조정

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft 365에는 기본적으로 사용하도록 설정된 다양한 피싱 방지 기능이 제공되어도 일부 피싱 메시지는 여전히 사서함으로 전달될 수 있습니다. 이 항목에서는 피싱 메시지가 통과하는 이유와 실수로 더 나빠지지 않도록 Microsoft 365 조직의 피싱 방지 설정을 조정하기 위해 할 수 있는 작업을 _설명합니다._

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>첫 번째 사항: 손상된 계정을 처리하고 더 이상 피싱 메시지가 통과하지 못하게 차단하는지 확인

피싱 메시지의 결과로 받는 사람의 계정이 손상된 경우 Microsoft [365에서](responding-to-a-compromised-email-account.md)손상된 전자 메일 계정에 응답의 단계를 따릅니다.

구독에 Office 365용 Microsoft Defender가 포함되어 있는 경우 [Office 365 위협](office-365-ti.md) 인텔리전스를 사용하여 피싱 메시지를 받은 다른 사용자를 식별할 수 있습니다. 피싱 메시지를 차단하는 추가 옵션이 있습니다.

- [Office 365용 Microsoft Defender의 안전한 링크](set-up-atp-safe-links-policies.md)

- [Office 365용 Microsoft Defender의 안전한 첨부 파일](set-up-atp-safe-attachments-policies.md)

- [Microsoft Defender for Office 365의 피싱](configure-atp-anti-phishing-policies.md)방지 정책 . 정책의 고급 피싱  임계값을 **일시적으로 Standard에서** **적극적,** 보다 적극적 또는 가장 적극적인 으로 늘 수 **있습니다.**

Office 365용 Defender 기능이 켜져 있는지 확인

## <a name="report-the-phishing-message-to-microsoft"></a>Microsoft에 피싱 메시지 보고

피싱 메시지 보고는 Microsoft 365의 모든 고객을 보호하는 데 사용되는 필터를 조정하는 데 유용합니다. 자세한 내용은 Microsoft에 메시지 및 [파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)

## <a name="inspect-the-message-headers"></a>메시지 헤더 검사

피싱 메시지의 헤더를 검사하여 더 많은 피싱 메시지가 통과하지 못하게 방지하기 위해 직접 할 수 있는 일이 없는지 검사할 수 있습니다. 즉, 메시지 헤더를 검사하면 조직의 피싱 메시지를 허용한 설정을 식별하는 데 도움이 될 수 있습니다.

특히 메시지 헤더의 **X-Forefront-Antispam-Report** 헤더 필드에서 SFV(스팸 필터링 결과) 값에서 스팸 또는 피싱에 대해 건너뛴 필터링 표시를 검사해야 합니다. 필터링을 건너뛰는 메시지에는 의 항목이 있습니다. 즉, 서비스에서 확인한 스팸 또는 피싱 판정을 다시 정하여 설정 중 하나를 통해 이 메시지를 `SCL:-1` 허용합니다. 메시지 헤더와 사용 가능한 모든 스팸 방지 및 피싱 방지 메시지 헤더의 전체 목록을 다운로드하는 방법에 대한 자세한 내용은 [Microsoft 365의](anti-spam-message-headers.md)스팸 방지 메시지 헤더를 참조하세요.

## <a name="best-practices-to-stay-protected"></a>보호를 위한 모범 사례

- 월별 보안 점수를 [](../mtp/microsoft-secure-score.md) 실행하여 조직의 보안 설정을 평가합니다.

- 실수로 메시지에 대해 또는 통과가 허용되는 메시지의 경우 위협 탐색기 및 실시간 검색에서 해당 메시지를 검색하는 [것이 좋습니다.](threat-explorer.md) 보낸 사람, 받는 사람 또는 메시지 ID를 사용하여 검색할 수 있습니다. 메시지를 찾은 후 제목을 클릭하여 세부 정보로 이동하세요. 분리된 메시지의 경우 적절한 방법을 사용하여 다시 적용하는 데 사용할 수 있도록 "감지 기술"이 어떤지 찾아보아야 합니다. 허용된 메시지에 대해 메시지를 허용한 정책을 찾아 봐야 합니다.

- 스푸핑된 메일은 Office 365용 Defender에서 피싱으로 태그가 지정됩니다. 경우에 따라 스푸핑이 양성일 수 있으며 사용자가 이를 무단으로 두지 않는 경우도 있습니다. 사용자에게 미치는 영향을 최소화하기 위해 스푸핑 인텔리전스 보고서를 정기적으로 [검토합니다.](learn-about-spoof-intelligence.md) 검토하고 필요한 모든 재지정을 한 후 의심스러운 [](set-up-anti-phishing-policies.md#spoof-settings) 메시지를 사용자의 정크  메일 폴더로 배달하는 대신 이를 검지하도록 스푸핑 인텔리전스를 구성할 수 있습니다.

- 가장(도메인 또는 사용자)에 대해 위의 단계를 반복할 수 있습니다. 가장 보고서는 **위협** 관리 대시보드 \>  \> **인사이트 아래에 있습니다.**

- 위협 방지 상태 보고서를 [정기적으로 검토합니다.](view-reports-for-atp.md#threat-protection-status-report)

- 일부 고객은 보낸 사람 또는 허용 도메인 목록에 스팸 방지 정책에 자신의 도메인을 넣어 피싱 메시지를 허용합니다. 이 구성에서는 합법적인 일부 메시지를 통과할 수 있도록 허용하기는 하지만 일반적으로 스팸 및/또는 피싱 필터에 의해 차단되는 악의적인 메시지도 허용합니다. 도메인을 허용하는 대신, 문제를 해결해야 합니다.

  도메인의 보낸 사람이 포함되는 Microsoft 365(가음성)에서 차단되는 합법적인 메시지를 처리하려면 모든 전자 메일 도메인에 대해 DNS에서 SPF,  DKIM 및 DMARC 레코드를 완전히 구성하는 것이 가장 좋습니다.

  - SPF 레코드가 도메인의  보낸 사람에 대한 모든 전자 메일 원본을 식별하는지 확인해야 합니다(타사 서비스를 잊지 마세요!).

  - 하드 실패(모두)를 사용하여 권한이 없는 보낸 사람이 거부되도록 구성된 전자 메일 시스템에서 \- 거부되도록 합니다. 스푸핑 [인텔리전스를](learn-about-spoof-intelligence.md) 사용하여 도메인을 사용하는 보낸 사람 식별을 지원하여 SPF 레코드에 인증된 타사 보낸 사람이 포함될 수 있습니다.

  구성 지침은 다음을 참조하세요.

  - [스푸핑을 방지할 수 있도록 SPF 설정](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [DKIM을 사용하여 사용자 지정 도메인에서 전송한 아웃바운드 전자 메일의 유효성 검사](use-dkim-to-validate-outbound-email.md)

  - [DMARC를 사용하여 전자 메일의 유효성 검사](use-dmarc-to-validate-email.md)

- 가능하면 도메인의 전자 메일을 Microsoft 365로 직접 전달하는 것이 좋습니다. 즉, Microsoft 365 도메인의 MX 레코드를 Microsoft 365를 지정합니다. EOP(Exchange Online Protection)는 메일이 Microsoft 365로 직접 배달될 때 클라우드 사용자에게 최상의 보호를 제공할 수 있습니다. EOP 앞에 타사 전자 메일방지 시스템을 사용하려면 커넥터에 대한 향상된 필터링을 사용하세요. 자세한 내용은 Exchange Online에서 커넥터에 대한 [향상된 필터링을 참조하세요.](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- 사용자는 보고서 [](enable-the-report-message-add-in.md) 메시지 추가 기능 또는 [](enable-the-report-phish-add-in.md) 피싱 보고 추가 기능을 사용하여 Microsoft에 메시지를 보고해야 합니다. 이 추가 기능을 통해 시스템을 학습할 수 있습니다. 관리자는 관리 제출 [기능도 활용해야](admin-submission.md) 합니다.

- MFA(다단계 인증)는 손상된 계정을 방지하는 좋은 방법입니다. 모든 사용자에 대해 MFA를 사용하도록 설정하는 것을 강력히 고려해야 합니다. 단계적 접근 방법의 경우 모든 사용자에 대해 MFA를 사용하도록 설정하기 전에 가장 중요한 사용자(관리자, 임원 등)에 대해 MFA를 사용하도록 설정하는 것부터 시작하세요. 자세한 내용은 [다단계 인증 설정 을 참조하세요.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)

- 외부 받는 사람에게 전달 규칙은 종종 공격자가 데이터를 추출하는 데 사용됩니다. [Microsoft](../mtp/microsoft-secure-score.md) **보안 점수의** 사서함 전달 규칙 검토 정보를 사용하여 외부 받는 사람에게 전달 규칙을 찾아서 차단할 수도 있습니다. 자세한 내용은 보안 점수를 사용하여 클라이언트 [외부 전달 규칙 완화를 참조하세요.](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)