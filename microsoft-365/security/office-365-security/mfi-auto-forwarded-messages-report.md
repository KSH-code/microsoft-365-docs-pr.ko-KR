---
title: 자동 전달 메시지 인사이트
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: 관리자는 보안 & 준수 센터의 메일 흐름 대시보드에 있는 자동 전달 메시지 보고서에 대해 알아볼 수 있습니다.
ms.openlocfilehash: 28cb593d56d0b0054c8c8cbe4596d4f7df6442ab
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920599"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>보안 & 준수 센터에 대 한 자동 전달 메시지 이해

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[보안 & 준수 센터](https://protection.office.com) 의 [메일 흐름 대시보드의](mail-flow-insights-v2.md) **자동 전달 메시지** 이해 조직에서 외부 도메인의 받는 사람에 게 자동으로 전달 되는 메시지에 대 한 정보를 표시 합니다.

![보안 & 준수 센터에서 메시지 위젯 자동 전달](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>자동 전달 메시지 세부 정보

위젯의 메시지 수를 클릭 하면 자동 전달 메시지에 대 한 자세한 내용을 보여주는 플라이 아웃 창이 표시 됩니다.

- **전달 메서드를 사용 하 여 메시지 자동 전달** :

  - **메일 흐름 규칙에 따라**
  - **받은 편지함 규칙에 따라**
  - **SMTP 전달** :이 메서드는 관리자가 [사서함에 대 한 전자 메일 전달 구성](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)에 설명 된 대로 사서함에 대해 구성할 수 있는 자동 전달을 나타냅니다.
  - 자세한 내용은 [전달 보고서](view-mail-flow-reports.md#forwarding-report) 에 대 한 링크를 참조 하십시오.

- **도메인 및 사용자가 자동으로 메시지를 전달 하는** 경우:

  - **다음에 전달 된 상위 5 개 도메인**
  - **새 도메인 (지난 주)**
  - **상위 5 개 사용자 전달**
  - **새 사용자 (지난 주)**
  - 자세한 내용은 [전달 수정 보고서](mfi-new-users-forwarding-email.md#forwarding-modifications-report) 에 대 한 링크를 참조 하세요.

![보안 & 준수 센터의 자동 전달 메시지 보고서에 대 한 세부 정보 플라이 아웃](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>인사이트

보고서 데이터를 기반으로 두 개의 정보가 생성 됩니다.

- [전자 메일을 전달 하는 새 사용자](mfi-new-users-forwarding-email.md)
- [전달 되는 새 도메인 전자 메일](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>참고 항목

메일 흐름 대시보드의 다른 정보에 대 한 자세한 내용은 [Security & 준수 센터의 메일 흐름 정보](mail-flow-insights-v2.md)를 참조 하십시오.
