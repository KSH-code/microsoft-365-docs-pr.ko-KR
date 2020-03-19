---
title: Office 36의 최종 사용자 스팸 알림
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
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
description: 관리자가 스팸 방지 정책에서 최종 사용자 스팸 알림을 사용 하도록 설정 하면 메시지 받는 사람은 격리 된 메시지에 대 한 정기적인 알림을 받게 됩니다.
ms.openlocfilehash: 67dbf311c37ae61c007b78110522033d79c0b161
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857153"
---
# <a name="end-user-spam-notifications-in-office-365"></a>Office 365의 최종 사용자 스팸 알림

격리는 exchange Online 사서함이 없는 Exchange Online 또는 독립 실행형 EOP (Exchange Online Protection)의 사서함을 포함 하는 Office 365 조직에서 위험할 수도 있고 원치 않는 메시지를 보관 합니다. 자세한 내용은 [Office 365의 격리](quarantine-email-messages.md)를 참조 하세요.

기본적으로 스팸 방지 정책에서는 최종 사용자 스팸 알림이 사용 되지 않도록 설정 됩니다. 관리자가 [최종 사용자 스팸 알림을 사용 하도록 설정](configure-your-spam-filter-policies.md)하면 메시지를 받는 사람에 게 스팸으로, 대량 전자 메일로, 또는 (4 월, 2020) 피싱 메일로 격리 된 메시지에 대 한 주기적인 알림을 받게 됩니다.

> [!NOTE]
> 2019 년 10 월에 격리 된 메시지를 최종 사용자 스팸 알림에서 직접 해제 하는 기능이 제거 되었습니다. 대신 사용자가 Office 365 보안 & 준수 센터에서 직접 또는 알림에서 **검토** 를 클릭 하 여 격리 된 메시지를 해제할 수 있습니다. 자세한 내용은 [Office 365의 사용자로 격리 된 메시지 찾기 및 릴리스](find-and-release-quarantined-messages-as-a-user.md)를 참조 하세요. <br/><br/> 높은 신뢰도의 피싱, 맬웨어 또는 메일 흐름 규칙 (전송 규칙이 라고도 함)으로 격리 된 메시지는 관리자만 사용할 수 있습니다. 자세한 내용은 [Office 365의 관리자로 격리 된 메시지 찾기 및 릴리스](find-and-release-quarantined-messages-as-an-administrator.md)를 참조 하세요.

최종 사용자 스팸 알림에는 격리 된 각 메시지에 대 한 다음 정보가 포함 됩니다.

- **보낸 사람**: 격리 된 메시지의 보내기 이름과 전자 메일 주소입니다.

- **제목**: 격리 된 메시지의 제목 줄 텍스트입니다.

- **Date**: 메시지가 격리 된 날짜와 시간 (UTC)입니다.

- **보낸 사람 차단**:이 링크를 클릭 하 여 수신 거부 목록에 보낸 사람을 추가 합니다.

- **검토**: 보안 & 준수 센터의 격리를 클릭 하 여 격리 된 메시지를 해제, 삭제 또는 보고할 수 있습니다.

![최종 사용자 스팸 알림 예](../../media/end-user-spam-notification.png)
