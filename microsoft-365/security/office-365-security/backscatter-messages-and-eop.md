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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 백 분산 및 Microsoft EOP (Exchange Online Protection)에 대해 설명 합니다.
ms.openlocfilehash: 2a752c89e2430f24441d14178942b89362736322
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203590"
---
# <a name="backscatter-in-eop"></a>EOP의 후방 산란

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


*Backscatter* 은 보내지 않은 메시지에 대해 수신 하는 배달 못 함 보고서 (ndr 또는 바운스 메시지)입니다. 스팸 발송자가 메시지의 보낸 사람: 주소를 위조 하 고, 실제 전자 메일 주소를 사용 하 여 메시지에 대 한 신뢰성을 전송 하는 경우가 많습니다. 따라서 스팸 발송자가 보낸 사람이 존재 하지 않는 받는 사람에 게 메시지를 보내는 경우 (스팸을 사용 하는 경우), 대상 전자 메일 서버가 본질적으로 NDR에 배달할 수 없는 메시지를 From: 주소에 있는 위조 된 보낸 사람에 게 반환 tricked 합니다.

Exchange online 사서함이 없는 Microsoft 365의 EOP (exchange online Protection) 조직에 사서함이 EOP에서는 NDR을 생성 하지 않고 dubious 원본에서 메시지를 식별 하 고 자동으로 삭제 하기 위한 모든 작업을 수행 합니다. 그러나 서비스를 통해 전달 되는 양은 대량 전자 메일을 기반으로 EOP에서 실수로 산을 보낼 가능성이 있습니다.

Backscatterer.org에서는 백 산 발송을 담당 하는 전자 메일 서버의 차단 목록 (DNS 차단 목록 또는 DNSBL이 라고도 함)을 유지 관리 하 고이 목록에 EOP 서버를 표시할 수 있습니다. 그러나 Backscatterer.org 차단 목록에서 본인을 제거 하지는 않습니다 (자체 허용).

> [!TIP]
> Backscatter.org website ( <http://www.backscatterer.org/?target=usage> )는 서비스를 사용 하 여 거부 모드 대신 안전 모드에서 들어오는 전자 메일을 확인 하는 것이 좋습니다 (대규모 전자 메일 서비스는 거의 모든 백 분산을 보내는 경우).
