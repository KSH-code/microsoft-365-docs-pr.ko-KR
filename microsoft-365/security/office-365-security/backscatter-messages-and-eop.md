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
localization_priority: Normal
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
ms.openlocfilehash: e5882f611c3feec9a22760e696973cd0713649b2
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192372"
---
# <a name="backscatter-in-eop"></a>EOP의 후방 산란

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*후방산은* 보내지 않은 메시지에 대해 수신하는 배달 못지 않은 보고서(NDRs 또는 반송 메시지라고도 알려지기)입니다. 스팸 발송자는 메시지의 보낸 사람: 주소를 위조(스푸핑)하며 메시지에 대한 신뢰성을 제공하기 위해 실제 전자 메일 주소를 사용하는 경우가 많습니다. 따라서 스패머가 존재하지 않는 받는 사람에게 메시지를 불가피하게 보내는 경우(스팸은 대량의 작업임) 대상 전자 메일 서버는 기본적으로 NDR에서 배달할 수 없는 메시지를 보낸 사람: 주소의 위조된 보낸 사람에게 반환하는 속임수입니다.

Microsoft 365 사서함이 없는 Exchange Online 또는 EOP(독립 실행형 Exchange Online Protection) 조직에서 EOP는 Exchange Online NDR을 생성하지 않고 의심스러운 원본에서 메시지를 식별하고 자동으로 삭제하기 위해 모든 노력을 다합니다. 그러나 서비스를 통해 흐르는 전방 볼륨 전자 메일에 따라 EOP에서 의도치 않은 후방 메일을 보낼 가능성이 항상 있습니다.

Backscatterer.org 후방산 전송을 담당하는 전자 메일 서버의 차단 목록(DNS 차단 목록 또는 DNSBL)을 유지 관리하며 EOP 서버가 이 목록에 표시될 수 있습니다. 그러나 스태머 목록이 아니기 때문에(자신의 입장에 따라) Backscatterer.org 차단 목록에서 제거하려고 하지 않습니다.

> [!TIP]
> Backscatter.org 웹 사이트()는 서비스를 사용하여 거부 모드 대신 금고 모드에서 받는 전자 메일을 검사하는 것이 좋습니다(대규모 전자 메일 서비스는 거의 항상 일부 <http://www.backscatterer.org/?target=usage> 후방산을 전송).
