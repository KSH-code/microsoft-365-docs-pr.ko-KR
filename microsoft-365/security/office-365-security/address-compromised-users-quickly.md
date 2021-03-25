---
title: 자동화된 조사 및 응답을 통해 손상된 사용자 계정 해결
keywords: AIR, autoIR, ATP, 자동화된, 조사, 대응, 수정, 위협, 고급, 위협, 보호, 손상
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Microsoft Defender for Office 365 계획 2에서 자동화된 조사 및 응답 기능을 통해 손상된 사용자 계정을 검색하고 처리하는 프로세스를 빠르게 진행하는 방법을 학습합니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2428cc2c1f82b4f2b881433fde991dd04b268d6e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206746"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>자동화된 조사 및 응답을 통해 손상된 사용자 계정 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


[Microsoft Defender for Office 365 계획 2에는](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) 강력한 자동화된 조사 및 대응(AIR) 기능이 포함되어 있습니다. [](office-365-air.md) 이러한 기능을 통해 보안 운영 팀이 위협을 처리하기 위한 시간과 노력을 많이 절약할 수 있습니다. Microsoft는 계속해서 보안 기능을 개선하고 있습니다. 최근에는 손상된 사용자 보안 플레이북(현재 미리 보기에서)을 포함하도록 AIR 기능이 향상했습니다. 손상된 사용자 보안 플레이북에 대한 자세한 내용은 이 문서를 읽어 하세요. 추가 세부 정보는 Microsoft [Defender for Office 365를](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) 통해 사용자 손상을 감지하고 대응하고 위반 범위를 제한하는 시간 향상 블로그 게시물을 참조하세요.

![손상된 사용자에 대한 자동화된 조사](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

손상된 사용자 보안 플레이북을 사용하면 조직의 보안 팀에서 다음을 할 수 있습니다.

- 손상된 사용자 계정의 검색 속도를 향상합니다.

- 계정이 손상된 경우 위반 범위를 제한합니다. 및

- 손상된 사용자에 대해 보다 효율적이고 효율적으로 대응합니다.

## <a name="compromised-user-alerts"></a>손상된 사용자 경고

사용자 계정이 손상되면 이상하거나 이상한 동작이 발생합니다. 예를 들어 피싱 및 스팸 메시지는 신뢰할 수 있는 사용자 계정에서 내부적으로 전송될 수 있습니다. Office 365용 Defender는 Office 365 내의 전자 메일 패턴 및 공동 작업 활동에서 이러한 변호를 감지할 수 있습니다. 이 경우 경고가 트리거되면 위협 완화 프로세스가 시작됩니다.

예를 들어 다음은 의심스러운 전자 메일을 보내기 때문에 트리거된 경고입니다.

![의심스러운 전자 메일 보내기 때문에 트리거된 경고](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

다음은 사용자에 대한 전송 제한에 도달할 때 트리거된 경고의 예입니다.

![전송 제한에 도달하여 트리거된 경고](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>손상된 사용자 조사 및 대응

사용자 계정이 손상되면 경고가 트리거됩니다. 경우에 따라 해당 사용자 계정이 차단된 후 조직의 보안 운영 팀에서 문제를 해결할 때까지 추가 전자 메일 메시지를 보낼 수 없습니다. 그 외의 경우에는 자동화된 조사가 시작되어 보안 팀에서 권장 조치를 취할 수 있습니다.

- [제한된 사용자 보기 및 조사](#view-and-investigate-restricted-users)

- [자동화된 조사에 대한 세부 정보 보기](#view-details-about-automated-investigations)

> [!IMPORTANT]
> 다음 작업을 수행하려면 적절한 권한이 있어야 합니다. [AIR 기능을 사용하는 데 필요한 사용 권한을 참조합니다.](office-365-air.md#required-permissions-to-use-air-capabilities)

### <a name="view-and-investigate-restricted-users"></a>제한된 사용자 보기 및 조사

제한된 사용자 목록으로의 몇 가지 옵션을 사용할 수 있습니다. 예를 들어 보안 및 준수 & 위협 관리 검토  제한된 \>  \> **사용자로 이동하면 됩니다.** 다음 절차에서는 트리거될 수 있는 다양한 종류의 경고를 볼 수 있는 좋은 방법인 **Alerts** 대시보드를 사용하여 탐색에 대해 설명합니다.

1. <https://protection.office.com>으로 이동하여 로그인합니다.

2. 탐색 창에서 경고 **대시보드 를** \> **선택합니다.**

3. 기타 **알림 위젯에서** 제한된 사용자 **를 선택 합니다.**

   ![기타 알림 위젯](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   그러면 제한된 사용자 목록이 열립니다.

   ![Office 365의 제한된 사용자](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. 목록에서 사용자 계정을 선택하여 세부 정보를 보고 제한된 사용자 를 공개하는 등의 작업을 [실행합니다.](removing-user-from-restricted-users-portal-after-spam.md)

### <a name="view-details-about-automated-investigations"></a>자동화된 조사에 대한 세부 정보 보기

자동화된 조사가 시작된 경우 보안 및 준수 센터에서 해당 세부 정보 및 결과를 & 있습니다. 위협 관리 **조사로** 이동한 다음 조사를 선택하여 세부 \> 정보를 본다.

자세한 내용은 조사 세부 [정보 보기를 참조합니다.](air-view-investigation-results.md)

## <a name="keep-the-following-points-in-mind"></a>다음에 유의해야 합니다.

- **경고를 계속 확인 합니다.** 아시다시피, 손상이 더 오래 발생하면 조직, 고객 및 파트너에게 광범위한 영향과 비용의 가능성이 커집니다. 조기 감지 및 시기적의 대응은 위협을 완화하는 데 중요하며 특히 사용자의 계정이 손상된 경우입니다.

- 자동화는 보안 운영 팀을 지원하지만 **대체하지는 않습니다.** 자동화된 조사 및 대응 기능은 초기에 손상된 사용자를 감지할 수 있지만 보안 운영 팀은 일부 조사 및 수정을 수행하고 참여해야 할 수 있습니다. 이에 대한 도움이 필요하세요? 작업 [검토 및 승인을 참조합니다.](air-review-approve-pending-completed-actions.md)

- 의심스러운 로그인 경고를 유일한 표시기로 **사용하지 않습니다.** 사용자 계정이 손상되면 의심스러운 로그인 경고를 트리거하거나 트리거하지 않을 수 있습니다. 경우에 따라 경고를 트리거하는 계정이 손상된 후 발생하는 일련의 활동입니다. 경고에 대해 더 알고 싶나요? 경고 [정책 을 참조합니다.](../../compliance/alert-policies.md)

## <a name="next-steps"></a>다음 단계

- [AIR 기능을 사용하는 데 필요한 사용 권한 검토](office-365-air.md#required-permissions-to-use-air-capabilities)

- [Office 365에서 악성 전자 메일 찾기 및 조사](investigate-malicious-email-that-was-delivered.md)

- [끝점용 Microsoft Defender의 AIR에 대해 자세히 알아보기](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsoft 365 로드맵을 방문하여 출시 예정 및 출시 예정 보기](https://www.microsoft.com/microsoft-365/roadmap?filters=)