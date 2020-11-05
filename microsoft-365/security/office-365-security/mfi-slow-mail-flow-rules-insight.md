---
title: 느린 메일 흐름 규칙 인사이트 수정
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 & 준수 센터에서 문제 해결을 사용 하 여 조직에서 비효율적인 메일 흐름 규칙 (전송 규칙이 라고도 함)을 식별 하 고 수정 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: f51c5a577fc6d9c52e35a5217cae4ae94c546c9d
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920551"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>보안 & 준수 센터의 메일 흐름 규칙에 대 한 자세한 정보를 수정 합니다.

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


비효율적인 메일 흐름 규칙 (전송 규칙이 라고도 함)은 조직에 대 한 메일 흐름 지연을 야기할 수 있습니다. 이 통찰력은 조직의 메일 흐름에 영향을 주는 메일 흐름 규칙을 보고 합니다. 이러한 규칙 유형의 예는 다음과 같습니다.

- 이를 사용 하는 조건은 대규모 그룹 **의 구성원** 입니다.
- 정규식 (regex) 패턴 일치를 사용 하는 조건입니다.
- 첨부 파일에서 콘텐츠 검사를 사용 하는 조건입니다.

[보안 & 준수 센터](https://protection.office.com) 의 [메일 흐름 대시보드의](mail-flow-insights-v2.md) **권장 사항에 대 한** **수정 메일 흐름 규칙** 에 대 한 자세한 정보는 메일 흐름 규칙을 완료 하는 데 시간이 너무 오래 걸려 사용자에 게 알려 줍니다.

이 통찰력은 조건이 감지 된 후에만 표시 됩니다 (메일 루프가 없는 경우에는 통찰력을 볼 수 없음).

이 알림을 사용 하면 메일 흐름 규칙을 식별 하 고 미세 조정 하 여 메일 흐름 지연을 줄이는 데 도움을 줄 수 있습니다.

![메일 흐름 대시보드의 권장 사용자 영역에서 느린 메일 흐름 규칙 통찰력을 수정 합니다.](../../media/mfi-fix-slow-mail-flow-rules.png)

위젯에 대 한 **세부 정보 보기** 를 클릭 하면 추가 정보가 포함 된 플라이 아웃이 나타납니다.

- **규칙** : 요약을 마우스로 가리키면 규칙의 모든 조건, 예외 및 작업을 볼 수 있습니다. 요약을 클릭 하 여 Exchange 관리 센터 (EAC)에서 규칙을 편집할 수 있습니다.
- **평가 된 메시지 수** : **예제 메시지 보기** 를 클릭 하 여 규칙의 영향을 받는 메시지의 예제에 대 한 [메시지 추적](message-trace-scc.md) 결과를 볼 수 있습니다.
- **각 메시지에 소요 된 평균 시간**
- **평균 메시지에 소요 된 시간** : 데이터의 하한값에서 위쪽을 구분 하는 가운데 값입니다.

![문제 해결에 대 한 세부 정보 보기를 클릭 한 후 표시 되는 세부 정보 플라이 인 느린 메일 흐름 규칙 이해](../../media/mfi-fix-slow-mail-flow-rules-details.png)

메일 흐름 규칙의 조건 및 예외에 대 한 자세한 내용은 [Exchange Online의 메일 흐름 규칙 조건 및 예외 (조건자)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)를 참조 하십시오.

## <a name="see-also"></a>참고 항목

메일 흐름 대시보드의 다른 정보에 대 한 자세한 내용은 [Security & 준수 센터의 메일 흐름 정보](mail-flow-insights-v2.md)를 참조 하십시오.
