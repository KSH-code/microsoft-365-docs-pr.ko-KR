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
ms.openlocfilehash: d4345134e98ae204f73dfb51a0abf5136590a24c
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126664"
---
# <a name="secure-by-default-in-office-365"></a>Office 365에서 기본적으로 보안

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

"기본적으로 보안"은 최대한 안전한 기본 설정을 정의 하는 데 사용 되는 용어입니다.

그러나 보안을 생산성과 균형 있게 조정 해야 합니다. 여기에는 다음과 같은 분산이 포함 될 수 있습니다.

- 유용성: 설정이 사용자 생산성을 유지 하는 방식으로 제공 되어서는 안 됩니다.
- 위험: 보안은 중요 한 작업을 차단할 수 있습니다.
- 레거시 설정: 이전 제품 및 기능에 대 한 일부 구성은 새로운 최신 설정이 향상 되더라도 비즈니스 상의 이유로 유지 관리 해야 할 수 있습니다.

Exchange Online 사서함이 있는 Microsoft 365 조직은 EOP (Exchange Online Protection)를 통해 보호 됩니다. 이 보호에는 다음이 포함 됩니다.

1. 의심 스러운 맬웨어가 있는 전자 메일은 자동으로 격리 되 고 받는 사람에 게 알림이 제공 됩니다. [EOP에서 맬웨어 방지 정책 구성을](configure-anti-malware-policies.md)참조 하세요.
1. "높은 신뢰도"로 식별 된 피싱 전자 메일은 스팸 방지 정책 작업에 따라 처리 됩니다. [EOP에서 스팸 방지 정책 구성을](configure-your-spam-filter-policies.md)참조 하세요.

Microsoft는 고객에 게 기본적으로 보안을 유지 하려고 하기 때문에 일부 테 넌 트 재정의는 맬웨어 또는 높은 신뢰도 피싱 적용 되지 않습니다. 이러한 재정의에는 다음이 포함 됩니다.

- 허용 된 보낸 사람 목록 또는 허용 된 도메인 목록 (스팸 방지 정책)
- Outlook 수신 허용-보낸 사람
- IP 허용 목록 (연결 필터링)

이러한 재정의에 대 한 자세한 내용은 [수신 허용-보낸 사람 목록 만들기](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365)에서 찾을 수 있습니다.

기본적으로 보안은 설정 또는 해제할 수 있는 설정이 아니며, 필터링이 상자에서 작동 하 여 위험할 수도 있고 원치 않는 메시지를 사서함에서 제외 하는 방법을 제공 합니다. 맬웨어 및 높은 신뢰도의 피싱이 격리로 전송 되어야 합니다. 관리자만이 맬웨어 또는 높은 자신감 피싱 메일로 격리 된 메시지를 관리할 수 있으며, Microsoft에 가양성을 보고할 수도 있습니다. 자세한 내용은 [격리 된 메시지 및 파일을 관리자 권한으로 EOP에서 관리](manage-quarantined-messages-and-files.md) 를 참조 하세요.

## <a name="exceptions"></a>예외

높은 신뢰도 피싱 메시지는 Exchange 메일 흐름 규칙 (전송 규칙이 라고도 함)은 필터링을 우회 하도록 허용 하는 유일한 재정의입니다. 메일 흐름 규칙을 사용 하 여 필터링을 우회 하려면 [메일 흐름 규칙을 사용 하 여 메시지에 SCL을 설정](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)합니다 .를 참조 하십시오.

재정의는 다음에 대해서만 사용 해야 합니다.

- 피싱 시뮬레이션: 시뮬레이션 된 공격은 실제 공격이 조직에 영향을 미치는 경우 취약 한 사용자를 식별 하는 데 도움이 될 수 있습니다.
- Security/SecOps 사서함: 보안 팀에서 필터링 되지 않은 메시지를 가져오는 데 사용 하는 전용 사서함입니다 (정상 및 불량). 그런 다음 팀이 악성 콘텐츠가 포함 되어 있는지 검토할 수 있습니다.
- 타사 필터: 타사 필터는 메일 필터링을 관리 하기 때문에 제 3 자 공급 업체가 EOP (SCL =-1)를 해제 하는 것이 좋습니다. Office 365 용 Defender에는 EOP as EOP이 필요 하므로이 기능을 해제 하는 것은 권장 되지 않습니다.
- 가양성: 여전히 [관리자 제출을 통해](admin-submission.md)Microsoft가 분석 중인 특정 메시지를 허용 하려고 할 수 있습니다. 모든 재정의와 마찬가지로 임시적으로 사용 하는 것이 좋습니다.
