---
title: 전자 메일 인사이트가 전달되는 새 도메인
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
ms.assetid: ''
description: '& 관리자는 보안 및 준수 센터의 메일 흐름 대시보드에서 새 도메인이 전달되는 전자 메일 정보를 사용하여 사용자가 전달되지 않은 외부 도메인으로 메시지를 전달하는 경우를 조사하는 방법을 배울 수 있습니다.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 25440898dfd29097985ddf1ffc0c17aa9c017793
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190260"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>보안 및 준수 센터에서 전달되는 새 & 정보

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

특정 도메인의 외부 받는 사람에게 전자 메일 메시지를 전달해야 하는 유효한 비즈니스 이유가 있습니다. 그러나 조직의 사용자가 갑자기 조직의 어느 누구도 (새 도메인)에게 메시지를 전달한 적 없는 도메인에 메시지를 전달하기 시작하면 의심스러우게 됩니다.

이 조건은 사용자 계정이 손상된 것일 수 있습니다. 계정이 손상된 것으로 의심되는 경우 손상된 전자 메일 계정에 응답을 [참조하세요.](responding-to-a-compromised-email-account.md)

Security **&** Compliance [Center에서](https://protection.office.com) 전달되는 새 도메인은 조직의 사용자가 메시지를 새 도메인으로 전달할 때 사용자에게 이를 통보합니다.

이 인사이트는 문제가 검색된 경우만 표시되고 전달 보고서 페이지에 [표시됩니다.](view-mail-flow-reports.md#forwarding-report)

![전자 메일 인사이트를 전달하는 새 도메인입니다.](../../media/mfi-new-domains-being-forwarded.png)

위젯을 클릭하면 전달 보고서에 대한 링크를 포함하여 전달된 메시지에 대한 자세한 정보를 찾을 수 있는 플라이아웃이 [나타납니다.](view-mail-flow-reports.md#forwarding-report)

![전자 메일 인사이트를 전달하는 새 도메인을 클릭한 후 나타나는 플라이아웃에 대한 세부 정보입니다.](../../media/mfi-new-domains-being-forwarded-details.png)

또한 ( 보고서 대시보드 또는 **)의** 상위 인사이트 및 추천 영역에 있는 모든 정보 보기를 클릭한 & 세부 정보 페이지로 이동될 **수도**  \>  <https://protection.office.com/insightdashboard> 있습니다.

외부 도메인으로 자동 메시지 전달을 방지하려면 일부 또는 모든 외부 도메인에 대해 원격 도메인을 구성합니다. 자세한 내용은 Manage [remote domains in Exchange Online.](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)

## <a name="related-topics"></a>관련 항목

메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)