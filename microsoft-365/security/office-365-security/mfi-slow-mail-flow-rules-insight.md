---
title: 느린 메일 흐름 규칙 인사이트 수정
f1.keywords:
- NOCSH
ms.author: chrisda
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
description: 관리자는 보안 & 준수 센터의 메일 흐름 규칙 검사 기능을 사용하여 조직에서 비효율적이거나 유효하지 않은 메일 흐름 규칙(전송 규칙이라고도 함)을 식별하고 수정하는 방법에 대해 알아볼 수 있습니다.
ms.openlocfilehash: 6319633c47e34d7b62c4f68bfbda7fe298c0deb3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826884"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>준수 센터에서 보안 전자 메일 흐름 규칙 정보를 & 줍니다.

비효율적인 메일 흐름 규칙(전송 규칙이라고도 함)이 조직의 메일 흐름 지연으로 이어질 수 있습니다. 이 정보에서는 조직의 메일 흐름에 영향을 미치는 메일 흐름 규칙을 보고합니다. 이러한 유형의 규칙의 예는 다음과 같습니다.

- 대규모 그룹의 **구성원인** 조건
- 복잡한 정규식(regex) 패턴 일치를 사용하는 조건
- 첨부 파일에서 콘텐츠 확인을 사용하는 조건

보안 & **규정 준수 센터의 메일 흐름** 대시보드에서 **추천한** 메일 흐름 규칙 정보는 너무 오래 걸리는 경우 이를 알리는 메일 흐름 규칙을 제공합니다. [Mail flow dashboard](mail-flow-insights-v2.md) 이 인사이트는 조건이 감지된 후에만 나타납니다(메일 루프가 없는 경우 사용자가 정보를 볼 수 없습니다).

이 알림을 사용하면 메일 흐름 지연을 줄이는 데 도움이 되는 메일 흐름 규칙을 식별하고 미세 치는 데 도움이 될 수 있습니다.

![메일 흐름 대시보드의 인용에 대한 권장 사항의 느린 메일 흐름 규칙 정보를 해결합니다.](../../media/mfi-fix-slow-mail-flow-rules.png)

위로에서 **세부 정보 보기를** 클릭하면 다음과 같은 정보가 포함된 플라이아웃이 표시됩니다.

- **규칙:** 요약 위로 가리키면 규칙의 모든 조건, 예외 및 작업을 볼 수 있습니다. 요약을 클릭하여 EAC(Exchange 관리 센터)에서 규칙을 편집할 수 있습니다.
- **평가된 메시지 수**: 예제 [message trace](message-trace-scc.md) **메시지를 보려면 샘플 메시지를 클릭하면** 규칙의 영향을 받는 메시지 샘플에 대한 메시지 추적 결과를 확인할 수 있습니다.
- **각 메시지에 사용된 평균 시간**
- **메시지에 소요된 중간값:** 상한절절과 반을 이시간 데이터의 절반 분리하는 중간값입니다.

![속도가 느린 메일 흐름 규칙 정보 수정을 클릭하여 표시되는 세부 정보 플라이아웃](../../media/mfi-fix-slow-mail-flow-rules-details.png)

Exchange Online의 메일 흐름 규칙의 조건 및 예외에 대한 자세한 내용은 Exchange Online의 메일 흐름 규칙 조건 및 [예외(조건자)를 참조하세요.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

## <a name="related-topics"></a>관련 항목

메일 흐름 대시보드의 기타 정보에 대한 내용은 규정 준수 센터의 [보안 흐름 정보를 & 참조하세요.](mail-flow-insights-v2.md)
