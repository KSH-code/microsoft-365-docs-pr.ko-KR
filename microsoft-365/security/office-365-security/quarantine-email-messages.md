---
title: Quarantined email messages
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 관리자는 위험할 수 있는 메시지나 원치 않는 메시지를 보유하는 EOP(Exchange Online Protection)의 검역에 대해 학습할 수 있습니다.
ms.openlocfilehash: f4e3f668ac94abfea6dc19f6f256141b2a7b9915
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616035"
---
# <a name="quarantined-email-messages-in-eop"></a>EOP에서 Quarantined email messages(EOP에서 전자 메일 메시지)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online 사서함이 없는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 위험하거나 원치 않는 메시지를 보유할 수 있습니다.

맬웨어 방지 정책은 맬웨어가 포함된 첨부 파일이 있는 경우 메시지를 자동으로 차단합니다.  자세한 내용은 [EOP에서 맬웨어 방지 정책 구성을 참조하세요.](configure-anti-malware-policies.md)

기본적으로 스팸 방지 정책은 피싱 메시지를 차단하고 스팸 및 대량 전자 메일 메시지를 사용자의 정크 메일 폴더로 배달합니다. 그러나 스팸 방지 정책을 만들고 사용자 지정하여 스팸 및 대량 전자 메일 메시지를 차단할 수도 있습니다. 자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

사용자와 관리자는 모두 다음을 통해 분리된 메시지로 작업할 수 있습니다.

- 관리자는 모든 사용자에 대해 모든 유형의 분리된 메시지로 작업할 수 있습니다. 관리자만 맬웨어, 높은 신뢰도 피싱 또는 메일 흐름 규칙(전송 규칙)의 결과로 고지된 메시지에 대해 작업할 수 있습니다. 자세한 내용은 [EOP에서 관리자로 격리된 메시지 관리하기](manage-quarantined-messages-and-files.md)를 참조하세요.

- 사용자는 메시지가 스팸, 대량 전자 메일 또는 (2020년 4월 현재) 피싱으로 스팸으로 분류된 경우 받는 사람인 분리된 메시지로 작업할 수 있습니다. 자세한 내용은 EOP에서 사용자로 고지된 메시지 찾기 및 [릴리스를 참조하세요.](find-and-release-quarantined-messages-as-a-user.md)

  사용자가 자신의 고지된 피싱 메시지를 관리하지 못하도록 관리자는 스팸 방지 정책에서  피싱 전자 메일 필터링 판정에 대해 다른 작업을 구성할 수 있습니다. 자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

- 관리자와 사용자는 Microsoft에 가짓 긍정을 보고할 수 있습니다.

자세한 내용은 [Quarantine FAQ를 참조하십시오.](quarantine-faq.md)
