---
title: 기본적으로 보안은 Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 06/28/2021
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: EOP(보안 기본 설정)에 대해 Exchange Online Protection 자세히 알아보시다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c737647202e82af0fc217c0eadb3e2573d13a9b1
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59219795"
---
# <a name="secure-by-default-in-office-365"></a>기본적으로 보안은 Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

"기본적으로 보안"은 가장 안전한 기본 설정을 정의하는 데 사용되는 용어입니다.

그러나 보안은 생산성과 균형을 조정해야 합니다. 여기에는 다음과 같은 분산이 포함됩니다.

- **사용 가능성:** 설정 생산성을 높이지 못합니다.
- **위험:** 보안이 중요한 활동을 차단할 수 있습니다.
- **레거시 설정:** 새 최신 설정이 개선된 경우에도 비즈니스상의 이유로 이전 제품 및 기능에 대한 일부 구성을 유지 관리해야 할 수 있습니다.

Microsoft 365 사서함이 있는 Exchange Online EOP(Exchange Online Protection 보호됩니다. 이 보호에는 다음이 포함됩니다.

- 의심되는 맬웨어가 있는 전자 메일은 자동으로 고지되고 받는 사람에게 알림이 전송됩니다. [EOP에서 맬웨어 방지 정책 구성을 참조합니다.](configure-anti-malware-policies.md)
- 높은 신뢰도 피싱으로 식별된 전자 메일은 스팸 방지 정책 조치에 따라 처리됩니다. [EOP에서 스팸 방지 정책 구성을 참조합니다.](configure-your-spam-filter-policies.md)

EOP에 대한 자세한 내용은 Exchange Online Protection [개요를 참조하세요.](exchange-online-protection-overview.md)

Microsoft는 기본적으로 고객의 보안을 유지하기를 원하기 때문에 일부 테넌트는 맬웨어 또는 높은 신뢰도 피싱에 적용되지 않습니다. 이러한 오버라이드에는 다음이 포함됩니다.

- 허용된 보낸 사람 목록 또는 허용된 도메인 목록(스팸 방지 정책)
- Outlook 금고 보낸 사람
- IP 허용 목록(연결 필터링)

이러한 오버라이드에 대한 자세한 내용은 안전한 보낸 사람 목록 만들기 [에서 찾을 수 있습니다.](create-safe-sender-lists-in-office-365.md)

> [!NOTE]
> EOP 스팸 방지  정책에서 높은 지수의 피싱 전자 메일 판정에 대한 정크 메일 폴더로 메시지 이동 작업은 더는 사용되지 않습니다.  높은 신뢰도의 피싱 메시지에 대해 이 작업을 사용하는 스팸 방지 정책은 메시지 를 **Quarantine message 로 변환합니다.** 높은 **신뢰도의** 피싱 메시지에 대한 전자 메일 주소로 메시지 리디렉션 작업은 영향을 받지 않습니다.

기본적으로 보안은 켜거나 끄는 설정이 아니며, 필터링이 기본적으로 작동하여 잠재적으로 위험하거나 원치 않는 메시지를 사서함 밖으로 유지하는 방식입니다. 맬웨어 및 높은 신뢰도의 피싱 메시지는 차단해야 합니다. 관리자만 맬웨어 또는 높은 신뢰도 피싱으로 보호된 메시지를 관리할 수 있으며, Microsoft에 가음성 보고도 할 수 있습니다. 자세한 내용은 EOP에서 관리자로 [quarantined messages and files를 참조하세요.](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>이 작업을 수행하고 있는 이유에 대한 자세한 내용은

기본적으로 보안이 유지되는 경우: 구성된 예외로 메시지가 배달될 수 있는 경우에도 악의적인 메시지를 알고 있는 경우 메시지에 대해 동일한 작업을 수행하게 됩니다. 이는 항상 맬웨어에 사용한 방법과 동일하며, 이제는 높은 신뢰도의 피싱 메시지로 동일한 동작을 확장하고 있습니다.

이 데이터는 사용자가 정크 메일 폴더와 Quarantine의 메시지에서 악의적인 링크를 클릭할 가능성이 30배 더 높을 수 있습니다. 또한 이 데이터는 높은 신뢰도의 피싱 메시지에 대한 가음성 비율(양호한 메시지)이 매우 낮고 관리자가 관리자 제출을 통해 가짓 긍정을 해결할 수 있다는 것입니다.

또한 스팸 방지 정책 및 금고 도메인 목록의 허용된 보낸 사람 및 허용된 도메인 목록이 Outlook 너무 광범위하여 양호한 것보다 더 많은 손상을 일으키는 것으로 확인되었습니다.

또 다른 방법으로 말해서, 보안 서비스로, 사용자가 손상되지 않도록 사용자를 대신하여 행동하고 있습니다.

## <a name="exceptions"></a>예외

> [!NOTE]
> 2021년 8월에는 기본적으로 보안이 메일 흐름 규칙(전송 Exchange)으로 확장됩니다. 메일 흐름 규칙을 사용하여 타사 피싱 시뮬레이션 또는 필터되지 않은 배달을 보안 작업 사서함으로 허용하는 경우 결국 이러한 [](configure-advanced-delivery.md) 규칙을 제거하고 기능을 사용할 수 있는 경우 고급 배달 정책을 사용하여 _전환해야 합니다._

높은 신뢰도의 피싱 메시지가 필터링을 무시할 수 있는 유일한 무시는 메일 흐름 규칙입니다. 메일 흐름 규칙을 사용하여 필터링을 무시하는 경우 메일 흐름 규칙을 사용하여 [메시지에서 SCL 설정을 참조합니다.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)

다음과 같은 시나리오에서만 오버라이드를 사용하는 것이 좋습니다.

- 피싱 시뮬레이션: 시뮬레이션된 공격은 실제 공격이 조직에 영향을 미치기 전에 취약한 사용자를 식별하는 데 도움이 될 수 있습니다.
- 보안/SecOps 사서함: 보안 팀에서 필터되지 않은 메시지를 받는 데 사용하는 전용 사서함(좋음 및 불량) Teams 검토하여 악성 콘텐츠가 포함되어 있는지 검토할 수 있습니다.
- 타사 필터: 도메인의 MX 레코드가 기본 설정을 지정하지 않는 경우 기본적으로 보안이 적용되지 Office 365.
- 가양성: 관리자 제출을 통해 Microsoft에서 여전히 분석하고 있는 특정 메시지를 일시적으로 [허용할 수 있습니다.](admin-submission.md) 모든 재지정과 함께 임시로 지정하는 것이 좋습니다.
