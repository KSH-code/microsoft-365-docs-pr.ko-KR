---
title: EOP의 후방 산란
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 후방산자 및 EOP(후방 보호)에 Microsoft Exchange Online 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 79a6dd1be6c33bdbfc3d87b834f231de7cd08a0c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60199456"
---
# <a name="backscatter-in-eop"></a>EOP의 후방 산란

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*후방산은* 보내지 않은 메시지에 대해 수신하는 배달 못지 않은 보고서(NDRs 또는 반송 메시지라고도 알려지기)입니다. 후방 스패터는 스패머가 메시지의 보낸사서 주소(또는 P2 주소라고도)를위조(스푸핑)하여 `5322.From` 발생했습니다. 스팸 발송자는 종종 실제 전자 메일 주소를 보낸사용자 주소로 사용하여 메시지에 대한 신뢰성을 제공합니다. 스팸이 존재하지 않는 받는 사람에게 전송되는 경우 대상 전자 메일 서버는 기본적으로 NDR에서 배달할 수 없는 메시지를 보낸 사람 주소의 위조된 보낸 사람에게 반환하는 속임수입니다.

Microsoft 365 사서함이 없는 Exchange Online 또는 EOP(독립 실행형 Exchange Online Protection) 조직에서 EOP는 Exchange Online NDR을 생성하지 않고 의심스러운 원본에서 메시지를 식별하고 자동으로 삭제하기 위해 모든 노력을 다합니다. 그러나 서비스를 통해 흐르는 전방 볼륨 전자 메일에 따라 EOP에서 의도치 않은 후방 메일을 보낼 가능성이 항상 있습니다.

Backscatterer.org 전송을 담당하는 전자 메일 서버의 차단 목록(DNS 차단 목록 또는 DNSBL)을 유지 관리하며 EOP 서버가 이 목록에 표시될 수 있습니다. 그러나 (자신의 입장에서) 목록이 스머 목록이 아니기 때문에 Backscatterer.org 차단 목록에서 제거하려고 하지 않습니다.

> [!TIP]
> 대규모 Backscatterer.org 서비스는 거의 항상 일부 후방산을 보내기 때문에 거부 모드 대신 금고 모드에서 서비스를 사용하는 <http://www.backscatterer.org/?target=usage> 것이 좋습니다.
