---
title: Microsoft 365의 최종 사용자 스팸 알림
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
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP (Exchange Online Protection)에서 격리 된 메시지에 대 한 최종 사용자 스팸 알림에 대해 알아볼 수 있습니다.
ms.openlocfilehash: 2786c90f6f5fb66cbb96b0375dacf7793894f72e
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778507"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>사용자 스팸 알림을 사용 하 여 격리 된 메시지 릴리스 및 보고

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange online Protection) 조직에서 격리는 위험할 가능성이 있거나 원치 않는 메시지를 보유합니다. 자세한 내용은 [EOP에서 격리 된 메시지](quarantine-email-messages.md)를 참조 하십시오.

기본적으로 스팸 방지 정책에서는 최종 사용자 스팸 알림이 사용 되지 않도록 설정 됩니다. 관리자가 [최종 사용자 스팸 알림을 사용](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)하도록 설정 하면 받는 사람 (automapping을 사용 하는 공유 사서함 포함)은 스팸으로, 대량 전자 메일로, 또는 (4 월 2020) 피싱 메일로 격리 된 메시지에 대 한 주기적인 알림을 받습니다.

공유 사서함의 경우에는 공유 사서함에 대 한 FullAccess 권한이 부여 된 사용자만 최종 사용자 스팸 알림을 지원 합니다. 자세한 내용은 [EAC를 사용 하 여 공유 사서함 위임 편집](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)을 참조 하십시오.

최종 사용자 스팸 알림은 그룹에 대해 지원 되지 않습니다.

> [!NOTE]
> 높은 신뢰도의 피싱, 맬웨어 또는 메일 흐름 규칙 (전송 규칙이 라고도 함)으로 격리 된 메시지는 관리자만 사용할 수 있습니다. 자세한 내용은 [EOP에서 관리자로 격리된 메시지 관리하기](manage-quarantined-messages-and-files.md)를 참조하세요.

최종 사용자 스팸 알림에는 격리 된 각 메시지에 대 한 다음 정보가 포함 됩니다.

- **보낸 사람**: 격리 된 메시지의 보내기 이름과 전자 메일 주소입니다.

- **제목**: 격리 된 메시지의 제목 줄 텍스트입니다.

- **Date**: 메시지가 격리 된 날짜와 시간 (UTC)입니다.

- **보낸 사람 차단**:이 링크를 클릭 하 여 수신 거부 목록에 보낸 사람을 추가 합니다. 자세한 내용은 [메일 보낸 사람 차단을](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)참조 하세요.

- **Release**: 스팸 (피싱 아님) 메시지의 경우 보안 & 준수 센터를 격리 하지 않고 여기에서 메시지를 릴리스할 수 있습니다.

- **검토**: 보안 & 준수 센터에서 격리로 이동 하려면이 링크를 클릭 합니다 (메시지가 격리 된 이유에 따라 다름). 격리 된 메시지를 확인, 해제, 삭제 또는 보고 합니다. 자세한 내용은 [EOP의 사용자로 격리 된 메시지 찾기 및 릴리스](find-and-release-quarantined-messages-as-a-user.md)를 참조 하세요.

![최종 사용자 스팸 알림 예](../../media/end-user-spam-notification.png)
