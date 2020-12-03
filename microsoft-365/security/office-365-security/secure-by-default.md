---
title: Office 365에서 기본적으로 보안
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: EOP (Exchange Online Protection)의 보안 강화 설정에 대 한 자세한 정보
ms.openlocfilehash: 54000d351463ba90751f1f27638fb52847cf05ce
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558517"
---
# <a name="secure-by-default-in-office-365"></a>Office 365에서 기본적으로 보안

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

"기본적으로 보안"은 최대한 안전한 기본 설정을 정의 하는 데 사용 되는 용어입니다.

그러나 보안을 생산성과 균형 있게 조정 해야 합니다. 여기에는 다음과 같은 분산이 포함 될 수 있습니다.

- **유용성**: 설정이 사용자 생산성을 유지 하는 방식으로 제공 되어서는 안 됩니다.
- **위험**: 보안은 중요 한 작업을 차단할 수 있습니다.
- **레거시 설정**: 이전 제품 및 기능에 대 한 일부 구성은 새로운 최신 설정이 향상 되더라도 비즈니스 상의 이유로 유지 관리 해야 할 수 있습니다.

Exchange Online 사서함이 있는 Microsoft 365 조직은 EOP (Exchange Online Protection)를 통해 보호 됩니다. 이 보호에는 다음이 포함 됩니다.

- 의심 스러운 맬웨어가 있는 전자 메일은 자동으로 격리 되 고 받는 사람에 게 알림이 제공 됩니다. [EOP에서 맬웨어 방지 정책 구성을](configure-anti-malware-policies.md)참조 하세요.
- 높은 신뢰도의 피싱 메일로 확인 된 전자 메일은 스팸 방지 정책 작업에 따라 처리 됩니다. [EOP에서 스팸 방지 정책 구성을](configure-your-spam-filter-policies.md)참조 하세요.

Microsoft는 고객의 보안을 기본적으로 유지 하려고 하기 때문에 맬웨어 또는 높은 신뢰 피싱에 대해 일부 테 넌 트 재정의가 적용 되지 않습니다. 이러한 재정의에는 다음이 포함 됩니다.

- 허용 된 보낸 사람 목록 또는 허용 된 도메인 목록 (스팸 방지 정책)
- Outlook 수신 허용-보낸 사람
- IP 허용 목록 (연결 필터링)

이러한 재정의에 대 한 자세한 내용은 [수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)에서 찾을 수 있습니다.

보안은 기본적으로 설정 하거나 해제할 수 있는 설정이 아니며, 필터링이 사용자의 위험 또는 원치 않는 메시지를 사서함 외부로 보호 하기 위해 상자에서 작동 하는 방식입니다. 맬웨어 및 높은 신뢰도 피싱 메시지를 격리 해야 합니다. 관리자만이 맬웨어 또는 높은 신뢰도 피싱 메일로 격리 된 메시지를 관리할 수 있으며 여기에서 가양성을 Microsoft에 보고할 수도 있습니다. 자세한 내용은 [격리 된 메시지 및 파일을 관리자 권한으로 EOP에서 관리](manage-quarantined-messages-and-files.md) 를 참조 하세요.

## <a name="more-on-why-were-doing-this"></a>이 작업을 수행 하는 이유에 대 한 자세한 내용을 알아봅니다.

기본적으로 안전 하다 고 생각 하는 것은 현재 위치에 있더라도 메시지를 악의적으로 알고 있는 경우에도 메시지에 대해 동일한 작업을 수행 하는 것입니다. 이 방법은 맬웨어에 사용한 것과 동일한 방식으로, 이제 높은 신뢰도 피싱 메시지에 대해 이와 동일한 동작을 확장 하는 것입니다. 이 데이터는 신뢰도가 높은 피싱 메시지에 대 한 가양성 비율이 매우 낮은 것을 나타내며 관리자는 관리자 제출을 통해 가양성을 해결할 수 있습니다. 또한이 데이터는 스팸 방지 정책 및 Outlook의 수신 허용-보낸 사람 목록과 허용 되는 도메인 목록이 너무 광범위 하 여 더 많은 피해를 야기 한다는 것을 나타냅니다.

또 다른 방법으로, 보안 서비스의 역할을 하는 것 이므로 사용자가 공격에 노출 되는 것을 방지할 수 있습니다. 또한 기본적으로 보안은 스팸 방지 정책에서 높은 신뢰도 피싱 메시지에 사용할 수 있는 옵션의 전체 인수 아닙니다. 격리를 권장 하지만, 항상 사용할 수 있는 다른 작업은 여전히 사용할 수 있습니다 (정크 메일 폴더로 이동 하거나 전자 메일 주소로 리디렉션).

## <a name="exceptions"></a>예외

높은 신뢰도 피싱 메시지는 Exchange 메일 흐름 규칙 (전송 규칙이 라고도 함)은 필터링을 우회 하도록 허용 하는 유일한 재정의입니다. 메일 흐름 규칙을 사용 하 여 필터링을 우회 하려면 [메일 흐름 규칙을 사용 하 여 메시지에 SCL을 설정](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)합니다 .를 참조 하십시오.

다음과 같은 시나리오에서는 재정의를 사용 하는 것이 좋습니다.

- 피싱 시뮬레이션: 시뮬레이션 된 공격은 실제 공격이 조직에 영향을 미치는 경우 취약 한 사용자를 식별 하는 데 도움이 될 수 있습니다.
- Security/SecOps 사서함: 보안 팀에서 필터링 되지 않은 메시지를 가져오는 데 사용 하는 전용 사서함입니다 (정상 및 불량). 그런 다음 팀이 악성 콘텐츠가 포함 되어 있는지 검토할 수 있습니다.
- 타사 필터: 타사 필터는 메일 필터링을 관리 하기 때문에 일부 타사 공급 업체는 EOP (SCL =-1)를 해제 하는 것이 좋습니다. Office 365 용 Defender에는 EOP as EOP이 필요 하므로이 기능을 해제 하는 것은 권장 되지 않습니다. 대신 [커넥터에 대 한 향상 된 필터링](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)을 설정 하는 것이 좋습니다.
- 가양성: [관리자 제출을 통해](admin-submission.md)여전히 Microsoft가 분석 중인 특정 메시지를 일시적으로 허용 하려는 경우가 있습니다. 모든 재정의와 마찬가지로 임시적으로 사용 하는 것이 좋습니다.
