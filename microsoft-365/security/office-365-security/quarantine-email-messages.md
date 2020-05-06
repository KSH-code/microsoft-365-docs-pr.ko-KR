---
title: Office 365에서 격리
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 Microsoft 365의 격리에 대해 설명 합니다. 격리는 잠재적으로 위험할 수도 있고 원치 않는 메시지를 보관 합니다.
ms.openlocfilehash: 396be17e07a347ab4d28a3e0b67dd137bda999db
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033869"
---
# <a name="quarantine-email-messages"></a>전자 메일 메시지 격리

Exchange online 사서함이 없는 Microsoft 365, 독립 실행형 EOP (Exchange Online Protection) 고객의 사서함을 사용 하는 경우에는 격리를 사용 하 여 위험할 수도 있고 원치 않는 메시지를 저장할 수 있습니다.

맬웨어를 포함 하 *는 첨부 파일이 있는 경우* 맬웨어 방지 정책은 메시지를 자동으로 격리 합니다. 자세한 내용은 [Office 365에서 맬웨어 방지 정책 구성을](configure-anti-malware-policies.md)참조 하세요.

기본적으로 스팸 방지 정책은 피싱 메시지를 격리 하 고 사용자의 정크 메일 폴더에 스팸 및 대량 전자 메일 메시지를 배달 합니다. 그러나 스팸 방지 정책을 만들고 사용자 지정 하 여 스팸을 격리 하 고 대량 전자 메일 메시지를 격리할 수도 있습니다. 자세한 내용은 [Office 365의 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

사용자와 관리자가 격리 된 메시지를 사용 하 여 작업할 수 있습니다.

- 관리자는 모든 사용자에 대해 격리 된 모든 유형의 메시지를 사용할 수 있습니다. 관리자만이 맬웨어, 높은 신뢰도 피싱 또는 메일 흐름 규칙 (전송 규칙이 라고도 함)의 결과로 격리 된 메시지를 사용할 수 있습니다. 자세한 내용은 [Office 365에서 관리자로 격리된 메시지 관리하기](manage-quarantined-messages-and-files.md)를 참조하세요.

- 사용자는 메시지가 스팸으로, 대량 전자 메일 또는 (4 월, 2020) 피싱 메일로 격리 된 경우 받는 사람 인 격리 된 메시지를 사용 하 여 작업할 수 있습니다. 자세한 내용은 [Office 365의 사용자로 격리 된 메시지 찾기 및 릴리스](find-and-release-quarantined-messages-as-a-user.md)를 참조 하세요.

  사용자가 격리 된 자체 피싱 메시지를 관리 하지 못하도록 하기 위해 관리자는 스팸 방지 정책에서 **피싱 전자 메일** 필터링 결과에 대해 다른 작업을 구성할 수 있습니다. 자세한 내용은 [Office 365의 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

- 관리자 및 사용자는 차단 되는 Microsoft에 가양성을 보고할 수 있습니다.

격리에 대 한 자세한 내용은 [격리 FAQ](quarantine-faq.md)를 참조 하세요.
