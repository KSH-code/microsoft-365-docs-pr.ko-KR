---
title: 스팸 지수
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
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)에서 메시지에 적용되는 SCL(스팸 지수)에 대해 자세히 알아보할 수 있습니다.
ms.openlocfilehash: 44687b8234e38e7f818aee908d1b65f382c908fe
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827400"
---
# <a name="spam-confidence-level-scl-in-eop"></a>EOP의 SCL(스팸 지수)

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 인바운드 메시지는 EOP의 스팸 필터링을 통과하여 스팸 점수가 할당됩니다. X-헤더의 메시지에 추가되는 개별 SCL(스팸 지수)에 매핑되는 점수입니다. SCL이 높을수록 메시지가 스팸일 크기가 커집니다. EOP는 SCL을 기반으로 메시지에 대해 조치를 취합니다.

SCL의 의미와 메시지에 대해 수행되는 기본 작업은 다음 표에 설명되어 있습니다. 스팸 필터링 필터에 따라 메시지에 대해 수행할 수 있는 작업에 대한 자세한 내용은 [EOP에서 스팸 방지 정책 구성을 참조하세요.](configure-your-spam-filter-policies.md)

****

|SCL|정의|기본 작업|
|:---:|---|---|
|-1|메시지가 스팸 필터링을 건너뛰어 예를 들어 Safe-SENDER FROM 의 메시지이거나 수신 허용 - 받는 사람에게 전송된 경우 또는 IP 허용 목록의 전자 메일 원본 서버에서 보내는 경우입니다. 자세한 내용은 [EOP에서 수신 허용 - 보낸 사람 목록 만들기를 참조하세요.](create-safe-sender-lists-in-office-365.md)|메시지를 받는 사람의 받은 편지함에 배달합니다.|
|0, 1|스팸 필터링을 통해 메시지가 스팸이 아오지 않았음을 확인했습니다.|메시지를 받는 사람의 받은 편지함에 배달합니다.|
|5, 6|메시지가 스팸으로 표시됨 스팸 **필터링**|메시지를 받는 사람의 정크 메일 폴더로 배달합니다.|
|9 |스팸 필터링 결과 메시지를 높은 **신뢰도의 스팸으로 표시**|메시지를 받는 사람의 정크 메일 폴더로 배달합니다.|
|

SCL 2, 3, 4, 7, 8은 스팸 필터링에서 사용되지 않습니다.

메일 흐름 규칙(전송 규칙이라고도 함)을 사용하여 SCL을 메시지에 스탬프 처리할 수 있습니다. 메일 흐름 규칙을 사용하여 SCL을 설정하는 경우 값 5 또는 6은 스팸에 대한 스팸 필터링 작업을 **트리거하고,** 7, 8 또는 9는 높은 스팸 지수에 대한 스팸 필터링 **작업을 트리거합니다.** 자세한 내용은 메일 [흐름 규칙을 사용하여 메시지의 스팸 신뢰 수준(SCL)을 설정하는 방법을 참조하세요.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

SCL과 마찬가지로 BCL(대량 호환 수준)은 대량 전자 메일(회색 메일이라고도 _함)을 식별합니다._ BCL이 높다는 것은 대량 메일 메시지가 위조를 생성할 가능성이 높다는 것을 의미합니다(그러기도 하다점). 스팸 방지 정책에서 BCL 임계값을 구성합니다. 자세한 내용은 [EOP에서 스팸 방지 정책 구성, EOP의](configure-your-spam-filter-policies.md) [BCL(대량 비정신 수준)](bulk-complaint-level-values.md)및 정크 메일과 대량 전자 메일의 차이점은 [무엇인가요?](what-s-the-difference-between-junk-email-and-bulk-email.md)

|<!-- -->|
|---|
|![LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New의** 짧은 아이콘 LinkedIn Learning에서 **제공한 Microsoft 365 admins and IT pros의**무료 비디오 과정을 확인해보세요.|
