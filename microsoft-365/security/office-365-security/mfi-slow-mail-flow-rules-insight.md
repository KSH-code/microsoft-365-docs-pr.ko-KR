---
title: 느린 메일 흐름 규칙 인사이트 수정
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: 관리자는 & 보안 및 준수 센터의 느린 메일 흐름 규칙 수정 정보를 사용하여 조직에서 비효율적 또는 손상된 메일 흐름 규칙(전송 규칙)을 식별하고 수정하는 방법을 알 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a50fa0d36cb025f5d0627a2212254b9d08dc5d9c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290696"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>보안 및 준수 센터에서 느린 메일 흐름 & 정보 수정

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

비효율적인 메일 흐름 규칙(전송 규칙)은 조직의 메일 흐름 지연으로 이어질 수 있습니다. 이 인사이트는 조직의 메일 흐름에 영향을 미치는 메일 흐름 규칙을 보고합니다. 이러한 유형의 규칙의 예는 다음과 같습니다.

- 사용하는 **조건은 큰 그룹의** 구성원입니다.
- 복잡한 정규식(regex) 패턴 일치를 사용하는 조건입니다.
- 첨부 파일에서 콘텐츠 검사를 사용하는 조건입니다.

The **Fix slow mail flow rules insight** in the Recommended for **you** area of the Mail [flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance [Center는](https://protection.office.com) 메일 흐름 규칙이 완료되는 데 너무 오래 걸립니다.

이 인사이트는 조건이 검색된 후에만 나타납니다(메일 루프가 없는 경우 인사이트를 볼 수 없습니다).

이 알림을 사용하여 메일 흐름 규칙을 식별하고 미세 조정하여 메일 흐름 지연을 줄일 수 있습니다.

![메일 흐름 대시보드의 권장 영역에 있는 느린 메일 흐름 규칙 정보 수정](../../media/mfi-fix-slow-mail-flow-rules.png)

위젯에서 **세부** 정보 보기를 클릭하면 자세한 정보가 있는 플라이아웃이 나타납니다.

- **규칙:** 요약 위에 마우스를 대고 규칙의 모든 조건, 예외 및 작업을 볼 수 있습니다. 요약을 클릭하여 EAC(Exchange 관리 센터)에서 규칙을 편집할 수 있습니다.
- **평가된** 메시지 수: 샘플  메시지 보기를 클릭하여 [](message-trace-scc.md) 규칙의 영향을 받은 메시지의 샘플에 대한 메시지 추적 결과를 볼 수 있습니다.
- **각 메시지에 소요된 평균 시간**
- **메시지에** 소요된 중간 시간: 시간 데이터의 하한값과 상한값을 구분하는 중간 값입니다.

![느린 메일 흐름 규칙 수정에 대한 세부 정보 보기를 클릭한 후 나타나는 세부 정보 플라이아웃](../../media/mfi-fix-slow-mail-flow-rules-details.png)

메일 흐름 규칙의 조건 및 예외에 대한 자세한 내용은 Exchange Online의 메일 흐름 규칙 조건 및 예외(조건자)를 [참조하세요.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

## <a name="see-also"></a>참고 항목

메일 흐름 대시보드의 다른 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 메일 [흐름 & 참조하세요.](mail-flow-insights-v2.md)
