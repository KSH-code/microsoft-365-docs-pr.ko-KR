---
title: 격리 된 전자 메일 메시지
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
description: 관리자는 잠재적으로 위험한 또는 원치 않는 메시지를 포함 하는 EOP (Exchange Online Protection)의 격리에 대해 자세히 알아볼 수 있습니다.
ms.openlocfilehash: 74f420dd1d37acb9949aae2e1f01688c44e5b1bc
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430874"
---
# <a name="quarantined-email-messages-in-eop"></a>EOP에서 격리 된 전자 메일 메시지

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange online 사서함이 없는 Microsoft 365 조직의 EOP (독립 실행형 Exchange Online 보호) 조직에서 격리를 사용 하 여 잠재적으로 위험할 수도 있고 원치 않는 메시지를 저장할 수 있습니다.

맬웨어를 포함 하 *는 첨부 파일이 있는 경우* 맬웨어 방지 정책은 메시지를 자동으로 격리 합니다. 자세한 내용은 [EOP에서 맬웨어 방지 정책 구성을](configure-anti-malware-policies.md)참조 하세요.

기본적으로 스팸 방지 정책은 피싱 메시지를 격리 하 고 사용자의 정크 메일 폴더에 스팸 및 대량 전자 메일 메시지를 배달 합니다. 그러나 스팸 방지 정책을 만들고 사용자 지정 하 여 스팸을 격리 하 고 대량 전자 메일 메시지를 격리할 수도 있습니다. 자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

사용자와 관리자가 격리 된 메시지를 사용 하 여 작업할 수 있습니다.

- 관리자는 모든 사용자에 대해 격리 된 모든 유형의 메시지를 사용할 수 있습니다. 관리자만이 맬웨어, 높은 신뢰도 피싱 또는 메일 흐름 규칙 (전송 규칙이 라고도 함)의 결과로 격리 된 메시지를 사용할 수 있습니다. 자세한 내용은 [EOP에서 관리자로 격리된 메시지 관리하기](manage-quarantined-messages-and-files.md)를 참조하세요.

- 메시지가 스팸으로, 대량 전자 메일 또는 (4 월 2020) 피싱 메일로 격리 된 경우 사용자는 격리 된 메시지를 사용 하 여 작업할 수 있습니다. 자세한 내용은 [EOP의 사용자로 격리 된 메시지 찾기 및 릴리스](find-and-release-quarantined-messages-as-a-user.md)를 참조 하세요.

  사용자가 격리 된 자체 피싱 메시지를 관리 하지 못하도록 하기 위해 관리자는 스팸 방지 정책에서 **피싱 전자 메일** 필터링 결과에 대해 다른 작업을 구성할 수 있습니다. 자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

- 관리자 및 사용자는 차단 되는 Microsoft에 가양성을 보고할 수 있습니다.

격리에 대 한 자세한 내용은 [격리 FAQ](quarantine-faq.md)를 참조 하세요.
