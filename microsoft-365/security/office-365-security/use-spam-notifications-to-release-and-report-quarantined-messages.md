---
title: Office 365에서 사용자 스팸 알림을 사용하여 격리된 메시지 릴리스 및 보고
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 03/14/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: 관리자가 사용자에 게 알림을 사용 하도록 설정 하는 경우 사서함에 전송 된 메시지를 스팸, 대량 또는 피싱 메시지로 식별 하는 알림 메시지가 표시 됩니다. 알림을 받은 후에는 메시지를 해제 하거나 보고할 수 있습니다.
ms.openlocfilehash: 51fcdefc08987b153d045994927f56df3b670fd0
ms.sourcegitcommit: 836bd8135cc49d6db37e78a7cfeb7d2cc4159e4e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722039"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a>Office 365에서 사용자 스팸 알림을 사용하여 격리된 메시지 릴리스 및 보고

관리자가 사용자에 게 스팸 알림을 사용 하도록 설정 하는 경우 사서함으로 주소가 지정 되어 스팸, 대량 또는 피싱으로 식별 된 메시지를 나열 하는 알림 메시지를 받게 됩니다.

> [!TIP]
> 관리자가이 기능을 사용 하도록 설정 하려는 경우에는 [기본 스팸 방지 정책을 수정](configure-your-spam-filter-policies.md)하는 경우 옵션을 선택할 수 있습니다.

수신 되는 메시지에는 스팸 격리 된 메시지의 수와 목록에 있는 마지막 메시지의 날짜와 시간 (utc (Universal 협정 세계시))이 포함 됩니다. 이 목록에는 각 메시지에 대 한 다음이 포함 됩니다.

- **보낸 사람** 격리 된 메시지의 보내기 이름 및 전자 메일 주소입니다.

- **제목** 격리된 메시지의 제목 줄 텍스트입니다.

- **날짜** 메시지가 격리된 날짜와 시간(UTC)입니다.

격리 된 메시지를 사용 하 여 수행할 수 있는 작업은 다음과 같습니다.

- Office 365에서 수신 거부 목록에 보낸 사람을 추가 하려는 경우 **보낸 사람을 차단** 합니다.

- 메시지가 스팸으로 아니면 Office 365에서 사서함으로 메시지를 보내도록 하려면 **릴리스** 를 선택 합니다.

- Preview 또는 Release와 같은 다른 작업을 수행 하려는 경우 보안 및 준수 센터 내의 격리 포털로 이동 하는 방법을 **검토** 합니다.

다음에 대해 숙지 합니다.

- 맬웨어 및 높은 신뢰도 피싱 메시지와 메일 흐름 규칙과 일치 하는 메시지는 사용자 스팸 알림에 포함 되지 않으므로 격리 됩니다. 

- 메시지를 릴리스하고 가양성으로(정크 아님) 한 번만 보고할 수 있습니다.
