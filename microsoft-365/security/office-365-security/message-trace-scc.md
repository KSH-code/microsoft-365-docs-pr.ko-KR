---
title: Microsoft 365 Defender 포털의 메시지 추적
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: 관리자는 Microsoft 365 Defender 포털의 메시지 추적 링크를 사용하여 메시지에 대해 어떻게 Microsoft 365 Defender 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0a5a62c437581228fc17fa7af159583029ef42ec
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60196504"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender 포털의 메시지 추적

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Defender 포털의 메시지 추적은 조직을 통과하는 전자 메일 메시지를 Exchange Online 추적합니다. 서비스에서 메시지를 수신, 거부, 지연 또는 배달할지 여부를 확인할 수 있습니다. 또한 최종 상태에 도달하기 전에 메시지에 대해 수행된 작업도 보여 주며,

메시지 추적의 정보를 사용하여 메시지에 대해 진행된 문제에 대한 사용자 질문에 효율적으로 답변하고, 메일 흐름 문제를 해결하고, 정책 변경의 유효성을 검사할 수 있습니다.

> [!NOTE]
> Microsoft 365 Defender 포털의 메시지 추적은 Exchange 관리 센터의 메시지 추적을 통과하는 Exchange 있습니다. 자세한 내용은 최신 관리 센터의 메시지 [Exchange 참조하세요.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 사항은 무엇인가요?

- 메시지 추적을 사용하려면 조직 **관리,** 준수  관리 또는 지원 센터 역할  **Exchange Online** 구성원이 되어야 합니다. 자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.

  **참고:** Microsoft 365 관리 센터 역할의 해당 Azure Active Directory 구성원 자격은 사용자에게 Microsoft 365.  자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.

- 메시지 추적 결과에 표시되는 최대 메시지 수는 선택한 보고서 유형에 따라 다릅니다(자세한 [](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) 내용은 보고서 유형 선택 섹션 참조). PowerShell 또는 Exchange Online 독립 실행형 EOP PowerShell의 [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) cmdlet은 결과에 모든 메시지를 반환합니다.

## <a name="open-message-trace"></a>메시지 추적 열기

in the Microsoft 365 Defender portal ( <https://security.microsoft.com> ) go to Email & **collaboration** Exchange \> **message trace**. 또는 메시지 추적 페이지로 직접 이동하기 위해 를 <https://admin.exchange.microsoft.com/#/messagetrace> 사용하세요.

이때 EAC의 메시지 추적이 열립니다. 자세한 내용은 최신 관리 센터의 메시지 [Exchange 참조하세요.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)
