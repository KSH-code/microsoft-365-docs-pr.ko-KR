---
title: 자동 전달 메시지 인사이트
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: 관리자는 보안 및 준수 센터의 메일 흐름 대시보드에서 자동 전달된 메시지 & 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c892400152df15adb3dfeb0c747ed7fae034d3d6
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029945"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>보안 및 준수 센터의 & 전달된 메시지 정보

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Security  [&](https://protection.office.com) 준수 센터의 메일 [](mail-flow-insights-v2.md) 흐름 대시보드에서 자동 전달된 메시지 정보에는 조직에서 외부 도메인의 받는 사람에게 자동으로 전달되는 메시지에 대한 정보가 표시됩니다.

![보안 및 준수 센터의 & 메시지 위젯](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>자동 전달된 메시지 세부 정보

위젯에서 메시지 수를 클릭하면 자동 전달된 메시지에 대한 자세한 정보를 표시하는 플라이아웃 창이 나타납니다.

- 전달 방법을 사용하여 자동 **전달된 메시지:**

  - **메일 흐름 규칙**
  - **받은 편지함 규칙**
  - **SMTP 전달:** 이 방법은 사서함에 대한 전자 메일 전달 구성에 설명된 바와 같이 관리자가 사서함에 대해 구성할 수 있는 자동 [전달을 나타냅니다.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)
  - 자세한 내용은 [전달 보고서에](view-mail-flow-reports.md#forwarding-report) 대한 링크입니다.

- **도메인 및 사용자에 의해 자동 전달된 메시지:**

  - **상위 5개 도메인으로 전달**
  - **새 도메인(지난 주)**
  - **상위 5명 전달 사용자**
  - **새 사용자(지난 주)**
  - 자세한 내용은 전달 수정 [보고서에](mfi-new-users-forwarding-email.md#forwarding-modifications-report) 대한 링크입니다.

![보안 및 준수 센터의 자동 전달된 메시지 보고서에 대한 & 플라이아웃](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>인사이트

보고서 데이터를 기반으로 두 가지 인사이트가 생성됩니다.

- [전자 메일을 전달하는 새 사용자](mfi-new-users-forwarding-email.md)
- [전자 메일로 전달되는 새 도메인](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>참고 항목

메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)
