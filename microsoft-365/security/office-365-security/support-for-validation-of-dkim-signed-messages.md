---
title: DKIM(Domain Keys Identified Mail) 서명된 메시지의 유효성 검사 지원
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: DKIM 서명된 메시지의 유효성 검사에 대해 Exchange Online Protection Exchange Online
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8695e25000390cf6c5d58adf63db1984c873d75b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192272"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>DKIM으로 서명된 메시지의 유효성 검사 지원

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection(EOP) 및 Exchange Online 도메인 키 식별[메일(DKIM)](https://www.rfc-editor.org/rfc/rfc6376.txt)메시지의 인바운드 유효성 검사를 모두 지원합니다.

DKIM은 다른 사람이 전자 메일  메시지를 스푸핑하지 않은지 확인하고 전자 메일  메시지가 보낸 것으로 도메인에서 전송된 것입니다. 전자 메일 메시지를 보낸 조직에 링크합니다. DKIM 확인은 IPv6을 사용하여 보낸 모든 메시지에 자동으로 사용됩니다. Microsoft 365 IPv4를 통해 메일을 보낼 때 DKIM도 지원됩니다. IPv6 지원에 대한 자세한 내용은 [IPv6을](support-for-anonymous-inbound-email-messages-over-ipv6.md)통해 익명 인바운드 전자 메일 메시지 지원을 참조하세요.

DKIM은 메시지 헤더의 DKIM-Signature 디지털 서명된 메시지의 유효성을 검사합니다. 테스트 유효성 검사의 DKIM-Signature 스탬프가 Authentication-Results 있습니다. 메시지 헤더 텍스트는 다음과 유사하게 표시됩니다(여기서 contoso.com 보낸 사람).

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> Authentication-Results 대한 자세한 내용은 RFC 7001([Message Header Field for Indicating Message Authentication Status를 참조하십시오.](https://www.rfc-editor.org/rfc/rfc7001.txt) Microsoft의 DKIM 구현은 이 RFC를 준수합니다.

관리자는 DKIM Exchange [](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) 메일 흐름 규칙(전송 규칙)을 만들 수 있습니다. 이러한 메일 흐름 규칙을 통해 관리자는 필요할 때 메시지를 필터링하거나 라우팅할 수 있습니다.