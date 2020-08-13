---
title: 스팸 지수
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP (Exchange Online Protection)에서 메시지에 적용 되는 SCL (스팸 지 수)에 대해 알아봅니다.
ms.openlocfilehash: 7e8d706f89c5b16bd34ad074498e011dc5d74093
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656542"
---
# <a name="spam-confidence-level-scl-in-eop"></a>EOP의 SCL (스팸 지 수)

Exchange online 사서함이 없는 Microsoft 365 조직의 EOP (독립 실행형 Exchange Online Protection) 조직에서 인바운드 메시지는 EOP의 스팸 필터링을 통해 수행 되며 스팸 점수가 할당 됩니다. 이 점수는 X-헤더의 메시지에 추가 된 개별 SCL (스팸 지 수)에 매핑됩니다. SCL이 높을수록 메시지가 스팸으로 표시 되는 것을 나타냅니다. EOP는 SCL을 기반으로 메시지에 대해 작업을 수행 합니다.

SCL의 의미와 메시지에 대해 수행 되는 기본 작업에 대 한 설명은 다음 표에 나와 있습니다. 스팸 필터링 결과을 기반으로 하는 메시지에 대해 수행할 수 있는 작업에 대 한 자세한 내용은 [Configure 스팸 방지 정책 EOP](configure-your-spam-filter-policies.md)을 참조 하십시오.

****

|SCL|정의|기본 작업|
|:---:|---|---|
|-1|메시지가 스팸 필터링을 건너뛰었습니다. 예를 들어 수신 허용-보낸 사람에 게 전송 된 메시지 이거나, 수신 하는 전자 메일 서버에서 온 것은 아닙니다. 자세한 내용은 [EOP에서 수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조 하십시오.|받는 사람의 받은 편지 함으로 메시지를 배달 합니다.|
|0, 1|스팸 필터링에서 메시지가 스팸으로 확인 되었습니다.|받는 사람의 받은 편지 함으로 메시지를 배달 합니다.|
|5, 6|스팸 필터링에서 메시지를 **스팸으로** 표시|받는 사람의 정크 메일 폴더로 메시지를 배달 합니다.|
|9 |스팸 필터링에서 메시지가 **높은 신뢰도 스팸으로** 표시 됨|받는 사람의 정크 메일 폴더로 메시지를 배달 합니다.|
|

SCL 2, 3, 4, 7, 8은 스팸 필터링에서 사용 되지 않는다는 것을 알 수 있습니다.

메일 흐름 규칙 (전송 규칙이 라고도 함)을 사용 하 여 메시지의 SCL을 스탬프 처리할 수 있습니다. 메일 흐름 규칙을 사용 하 여 SCL을 설정 하는 경우 값 5 또는 6은 **스팸**에 대 한 스팸 필터링 작업을 트리거하고 값 7, 8 또는 9는 **신뢰도가 높은 스팸**에 대 한 스팸 필터링 작업을 트리거합니다. 자세한 내용은 [메일 흐름 규칙을 사용 하 여 메시지에서 SCL (스팸 지 수) 설정을](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)참조 하십시오.

SCL과 마찬가지로, BCL (bulk 불만 수준)은 잘못 된 대량 전자 메일 ( _회색 메일이_라고도 함)을 식별 합니다. BCL이 많을 수록 대량 메일 메시지가 불만을 창출 하는 것 이며, 따라서 스팸으로 발생할 가능성이 높습니다. 스팸 방지 정책에서 BCL 임계값을 구성 합니다. 자세한 내용은 [EOP에서 스팸 방지 정책 구성](configure-your-spam-filter-policies.md), [EOP의 BCL (대량 불만 수준](bulk-complaint-level-values.md)) 및 [정크 메일 및 대량 전자 메일의 차이점](what-s-the-difference-between-junk-email-and-bulk-email.md)을 참조 하세요.

|<!-- -->|
|---|
|![LinkedIn에 대 한 짧은 아이콘은 ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Microsoft 365를 처음으로 학습 하나요?** LinkedIn 학습을 통해 제공 되는 **Microsoft 365 관리자 및 IT 전문가**를 위한 무료 비디오 과정을 소개 합니다.|
