---
title: 발생할 수 있는 메일 루프 인사이트 수정
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 및 준수 센터의 메일 흐름 대시보드에서 가능한 메일 루프 수정 정보를 사용하여 조직의 메일 루프를 식별하고 & 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0c866dbec4a406c47bec072225dbe038510d71de
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218002"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>보안 및 준수 센터에서 가능한 메일 루프 & 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

메일 루프는 좋지 않습니다.

- 시스템 리소스를 낭비합니다.
- 조직의 메일 볼륨 할당량을 사용하게 됩니다.
- NDRs 또는 반송 메시지라고도 하는 배달 못 한 보고서를 원본 메시지 보낸 사람에 전송합니다.

보안 **및** 준수 센터의  메일 흐름 대시보드에 있는 권장 영역의 가능한 메일 루프 정보 수정은 조직에서 메일 [루프가 &](https://protection.office.com) 감지될 때 통보합니다. [](mail-flow-insights-v2.md)

이 인사이트는 조건이 검색된 후에만 나타납니다(메일 루프가 없는 경우 인사이트를 볼 수 없습니다).

![메일 흐름 대시보드의 권장 영역의 느린 메일 흐름 규칙 정보를 수정합니다.](../../media/mfi-fix-possible-mail-loop.png)

위젯에서 세부 **정보** 보기를 클릭하면 추가 정보가 있는 플라이아웃이 나타납니다.

- **도메인**
- **메시지 수:** 샘플 메시지  보기를 클릭하여 루프의 영향을 받은 메시지 샘플에 대한 메시지 추적 결과를 볼 수 있습니다. [](message-trace-scc.md)
- **도메인 유형**" 예: Authoritative 또는 Non-authoritative.
- **MX 레코드:** 도메인에 대한  MX 레코드의 호스트(**메일** 서버) 및 우선 순위 값입니다.
- **루프 이유** 및 해결 **방법:** 가장 일반적인 메일 루프 시나리오를 식별하고 루프를 해결하기 위한 권장 작업을 제공합니다.

![가능한 메일 루프 정보 수정에서 세부 정보 보기를 클릭한 후 나타나는 플라이아웃에 대한 세부 정보입니다.](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>참고 항목

메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)
