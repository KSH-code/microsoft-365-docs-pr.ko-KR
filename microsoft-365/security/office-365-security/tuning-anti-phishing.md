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
search.appverid:
- MET150
description: 관리자는 Microsoft 365에서 피싱 메시지가 어떻게 통과되는지, 이후에 피싱 메일을 방지하기 위해 수행해야 할 일을 확인하는 방법에 대해 알아보세요.
ms.openlocfilehash: b0fbb29489cece6d708811c5c8d8d60450938f0c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825212"
---
# <a name="tune-anti-phishing-protection"></a>피싱 방지 보호 기능 조정

Microsoft 365에는 기본적으로 사용하도록 설정되어 있는 다양한 피싱 방지 기능이 제공되지만 일부 피싱 메시지가 여전히 사서함에 전달될 수 있습니다. 이 항목에서는 피싱 메시지가 통과된 이유를 검색하기 위해 수행할 수 있는 작업과 단계적 적이하지 않고 Microsoft 365 조직에서 피싱 방지 설정을 조정하기 위해 수행할 수 있는 작업에 대해 _설명합니다._

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>먼저, 모든 위임된 계정을 처리하고 더 이상 피싱 메시지가 통과하지 못하도록 차단해야 합니다.

피싱 메일로 인해 받는 사람의 계정이 손상된 경우, Microsoft 365에서 손상된 전자 메일 계정에 [응답의 단계를 따릅니다.](responding-to-a-compromised-email-account.md)

구독에 ATP(Advanced Threat Protection)가 포함된 경우 [Office 365 위협](office-365-ti.md) 인텔리전스를 사용하여 피싱 메시지도 도입한 다른 사용자를 식별할 수 있습니다. 피싱 메시지를 차단하는 추가 옵션이 있습니다.

- [ATP 안전한 링크](set-up-atp-safe-links-policies.md)

- [ATP 안전한 첨부 파일](set-up-atp-safe-attachments-policies.md)

- [Microsoft 365의 ATP 피싱 방지 정책.](configure-atp-anti-phishing-policies.md) 정책의 고급 피싱 임계값을 **Advanced phishing thresholds** **표준에서** 적도적, 보다 적법한 **Aggressive** **값**또는 가장 적정으로 **높일 수 있습니다.**

이러한 ATP 기능이 켜져 있는지 확인합니다.

## <a name="report-the-phishing-message-to-microsoft"></a>Microsoft에 피싱 메시지 보고

보고 피싱 메시지는 Microsoft 365에서 모든 고객을 보호하는 데 사용되는 필터를 미치는 데 유용합니다. 지침은 Microsoft에 보고 [메시지와 파일을 참조하세요.](report-junk-email-messages-to-microsoft.md)

## <a name="inspect-the-message-headers"></a>메시지 헤더 검사

피싱 메시지의 머리글을 검사하여 더 많은 피싱 메일의 전송을 방지하기 위해 자신이 수행할 수 있는 작업이 있는지 확인할 수 있습니다. 즉, 메시지 헤더를 검사하면 조직에서 피싱 메시지를 허용하는 모든 설정을 확인하는 데 도움이 됩니다.

특히, 메시지 헤더의 **X-Forefront-Antispam-Report** 헤더 필드에서 SFV(스팸 필터링 결과)의 건너뛰는 스팸 또는 피싱 필터링의 표시가 있는지를 확인해야 합니다. 필터링을 건너뛰는 메시지는 항목을 가진 있습니다. 즉, 서비스에서 결정한 스팸 또는 피싱 결과를 다시 정의하여 이 메시지가 전송된 설정 중 `SCL:-1` 하나가 있습니다. 메시지 헤더를 가져오는 방법 및 사용 가능한 모든 스팸 방지 및 피싱 메시지 헤더의 전체 목록을 보려면 Microsoft 365에서 스팸 방지 메시지 [헤더를 참조하세요.](anti-spam-message-headers.md)

## <a name="best-practices-to-stay-protected"></a>보호된 개인을 지확인하기 위한 모범 사례

- 매월 보안 점수를 [실행하면](../mtp/microsoft-secure-score.md) 조직의 보안 설정을 평가합니다.

- 실수로 끝나거나 보내도록 허용된 메시지에 대해 발생하는 메시지의 경우에는 위협 탐색기 및 실시간 탐지에서 [해당 메시지를 검색하는 것이 좋습니다.](threat-explorer.md) 보낸 사람, 받는 사람 또는 메시지 ID로 검색할 수 있습니다. 메시지를 찾은 후에 제목을 클릭하 고 세부 정보로 이동합니다. 격리된 메시지는 적절한 방법으로 재정의할 수 있도록 "검색 기술"이 무엇에 대한 검색 기술을 확인합니다. 허용된 메시지는 메시지를 허용한 정책을 확인합니다. 

- 스푸핑된 메일은 ATP에서 피싱 태그가 지정됩니다. 간간 스푸핑이 야간하며 사용자가 스푸핑을 분할하고 자주 사용하지 않는 경우가 있습니다. 사용자에게 미치는 영향을 최소화하려면 스푸핑 [인텔리전스 보고서를 주기적으로 검토하십시오.](learn-about-spoof-intelligence.md) 필요한 재정의를 검토하고 만든 후에는 사용자의 정크 메일 [configure spoof intelligence](set-up-anti-phishing-policies.md#spoof-settings) 폴더로 전달하는 대신 **Quarantine** 스푸핑 인텔리전스를 격리된 메시지에 구성할 수 있습니다.

- 위의 단계를 가장 단계(도메인 또는 사용자)로 반복할 수 있습니다. 가장 보고서는 위협 관리 **대시보드** \> **정보에서** \> **찾을 수 있습니다.**

- 위협 방지 상태 보고서를 [주기적으로 검토합니다.](view-reports-for-atp.md#threat-protection-status-report)

- 일부 고객은 고유의 도메인을 허용 보낸 사람 또는 허용 목록을 스팸 방지 정책에 포함하여 피싱 메시지를 우회하도록 허용합니다. 이 구성에서는 일부 적법한 메시지를 허용하지만 스팸 및/또는 피싱 필터에 의해 일반적으로 차단되는 악의적인 메시지도 허용합니다. 도메인을 허용하는 대신 기본 문제를 해결해야 합니다.

  도메인의 보낸 사람이 격리하는 합법적인 메시지(가양성)를 다루는 가장 좋은 방법은 모든 이메일 도메인에 대해 DNS에서 SPF, DKIM 및 DMARC 레코드를 완전히 구성하고 _완전히_ 구성하는 것입니다.

  - SPF 레코드가 도메인에 있는 보낸 _사람의 모든_ 전자 메일 원본을 식별하는지 확인합니다(타사 서비스 를 받아오지 마세요!).

  - 영구 실패(모두)를 사용하여 권한 없는 보낸 사람을 적절하지 않은 보낸 사람이 적절해 두도록 구성된 전자 \- 메일 시스템에서 거부되도록 합니다. 스푸핑 [인텔리전스를](learn-about-spoof-intelligence.md) 사용하여 권한이 부여된 타사 발신자를 SPF 레코드에 포함할 수 있습니다.

  구성 지침은 다음을 참조하세요.
  
  - [스푸핑을 방지할 수 있도록 SPF 설정](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [DKIM을 사용하여 사용자 지정 도메인에서 전송한 아웃바운드 전자 메일의 유효성 검사](use-dkim-to-validate-outbound-email.md)

  - [DMARC를 사용하여 전자 메일의 유효성 검사](use-dmarc-to-validate-email.md)

- 가능한 경우 도메인의 전자 메일을 Microsoft 365에 직접 배달하는 것이 좋습니다. 즉, Microsoft 365 도메인의 MX 레코드를 Microsoft 365로 가리키도록 합니다. EOP(Exchange Online Protection)는 메일이 Microsoft 365로 직접 배달될 때 클라우드 사용자에게 최상의 보호가 제공됩니다. EOP 앞에 타사 전자 메일 방역 시스템을 해야 하는 경우 커넥터에 대한 향상된 필터링을 사용합니다. 자세한 내용은 [Exchange Online에서 커넥터에 대한 향상된 필터링을 참조하세요.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- 사용자는 [시스템을 교육할](enable-the-report-message-add-in.md) 수 있는 Microsoft로 메시지를 보고해야 합니다. 관리자도 관리자 제출 기능을 [활용해야](admin-submission.md) 합니다.

- 다단계 인증(MFA)은 계정 이문제를 방지하기 위한 좋은 방법입니다. 모든 사용자에 대해 MFA를 사용하도록 설정하는 것이 좋습니다. 단계별 접근 방식의 경우 모든 사용자에 대해 MFA를 사용하기 전에 가장 중요한 사용자(관리자, 임원 등)에 대해 MFA를 사용하도록 설정합니다. 관련 지침은 다단계 [인증 설정을 참조하세요.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)

- 외부 받는 사람에게 전달 규칙은 대다가 공격자가 데이터를 추출하는 데 사용됩니다. Microsoft 보안 **점수의 사서함 전달 규칙** 정보 [검토를 사용하여 외부](../mtp/microsoft-secure-score.md) 받는 사람에게 전달 규칙을 검색하거나 방지합니다. 자세한 내용은 보안 [점수를 사용하여 클라이언트 외부 전달 규칙 완화를 참조하십시오.](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)
