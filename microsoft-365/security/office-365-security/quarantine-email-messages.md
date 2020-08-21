---
title: 격리된 전자 메일 메시지
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
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)에서 위험할 수 있거나 원치 않는 메시지를 보유하는 격리 방법에 대해 알아질 수 있습니다.
ms.openlocfilehash: d2ccf174ae929c6db14f2a5319e9594495c0778e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826804"
---
# <a name="quarantined-email-messages-in-eop"></a>EOP에서 격리된 전자 메일 메시지

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 위험할 가능성이 있거나 원치 않는 메시지를 보존할 수 있습니다.

맬웨어 방지 정책은 첨부 파일이 맬웨어를 포함하는지를 *확인하는* 경우 자동으로 메시지를 격리합니다. 자세한 내용은 [EOP에서 맬웨어 방지 정책 구성을 참조하세요.](configure-anti-malware-policies.md)

기본적으로 스팸 방지 정책은 피싱 메시지를 격리하고 사용자의 정크 메일 폴더로 스팸 및 대량 전자 메일 메시지를 배달합니다. 그러나 스팸 방지 정책을 만들고 사용자 지정하여 스팸 및 대량 전자 메일 메시지를 격리할 수 있습니다. 자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

사용자와 관리자는 격리된 메시지를 사용하여 작업할 수 있습니다.

- 관리자는 모든 사용자에 대해 모든 유형의 격리된 메시지를 사용할 수 있습니다. 관리자만 맬웨어로 격리된 메시지, 높은 신뢰도의 피싱 또는 메일 흐름 규칙(전송 규칙이라고도 함)의 결과로 작업할 수 있습니다. 자세한 내용은 [EOP에서 관리자로 격리된 메시지 관리하기](manage-quarantined-messages-and-files.md)를 참조하세요.

- 사용자는 메시지가 스팸, 대량 전자 메일 또는 (2020년 4월에 의해) 피싱으로 격리된 경우 받는 사람인 격리된 메시지로 작업할 수 있습니다. 자세한 내용은 [EOP에서 사용자로 격리된 메시지 찾기 및 릴리스를 참조하세요.](find-and-release-quarantined-messages-as-a-user.md)

  사용자가 자신의 격리된 피싱 메시지를 관리하지 못하도록 하기 위해 관리자는 스팸 방지 정책의 **피싱 전자** 메일 필터링 결과에 대해 다른 작업을 구성할 수 있습니다. 자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

- 관리자 및 사용자는 격리된 상태에서 가양성을 Microsoft에 보고할 수 있습니다.

격리에 대한 자세한 내용은 격리 [FAQ를 참조하세요.](quarantine-faq.md)
