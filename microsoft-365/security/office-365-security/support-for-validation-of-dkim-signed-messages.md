---
title: DKIM(Domain Keys Identified Mail) 서명된 메시지의 유효성 검사 지원
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Exchange Online Protection 및 Exchange Online에서 DKIM 서명된 메시지의 유효성 검사에 대해 자세히
ms.openlocfilehash: 91a01f89bb633a38d27ddd3f2945b8707643d7e9
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845062"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>DKIM으로 서명된 메시지의 유효성 검사 지원

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

EOP(Exchange Online Protection) 및 Exchange Online은[모두 DKIM(Domain](https://www.rfc-editor.org/rfc/rfc6376.txt)Keys Identified Mail) 메시지의 인바운드 유효성 검사를 지원합니다.

DKIM은 다른 사람이 전자 메일  메시지를 스푸핑하지 않은지 확인하고 전자 메일  메시지가 보낸 도메인에서 전송된 것으로 확인됩니다. 전자 메일 메시지를 보낸 조직에 링크합니다. DKIM 확인은 IPv6으로 전송된 모든 메시지에 자동으로 사용됩니다. 또한 Microsoft 365는 IPv4를 통해 메일을 보낼 때 DKIM도 지원됩니다. IPv6 지원에 대한 자세한 내용은 [IPv6을](support-for-anonymous-inbound-email-messages-over-ipv6.md)통해 익명 인바운드 전자 메일 메시지 지원 참조

DKIM은 메시지 헤더의 DKIM-Signature 디지털 서명된 메시지의 유효성을 검사합니다. 테스트 유효성 검사의 DKIM-Signature 스탬프가 Authentication-Results 있습니다. 메시지 헤더 텍스트는 다음과 유사합니다(contoso.com 보낸 사람).

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> Authentication-Results 대한 자세한 내용은 RFC 7001(메시지 인증 상태를 나타내는 메시지 헤더 필드)을[참조하십시오.](https://www.rfc-editor.org/rfc/rfc7001.txt) Microsoft의 DKIM 구현은 이 RFC를 준수합니다.

관리자는 DKIM 유효성 검사 결과에 [대해](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) Exchange 메일 흐름 규칙(전송 규칙)을 만들 수 있습니다. 이러한 메일 흐름 규칙을 통해 관리자는 필요한 경우 메시지를 필터링하거나 라우팅할 수 있습니다.
