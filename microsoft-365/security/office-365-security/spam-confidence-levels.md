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
description: 관리자는 SCL (스팸 지 수)에 따라 메시지의 스팸이 얼마나 되는지 또는 발생할 가능성이 어떻게 결정 되는지, 스팸 필터링이 SCL을 기반으로 하는 메시지에 적용 되는 기본 작업에 대해 알아볼 수 있습니다.
ms.openlocfilehash: 519bc48e7285283ad0570b8f3ac598615b132875
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638287"
---
# <a name="spam-confidence-level-scl-in-office-365"></a>Office 365의 SCL (스팸 지 수)

Exchange Online 사서함 없이 Microsoft 365 (Exchange online 또는 독립 실행형 Exchange Online Protection (EOP)이 인바운드 전자 메일 메시지를 수신 하면 메시지는 스팸 필터링을 통과 하며 스팸 점수가 할당 됩니다. 이 점수는 X-헤더의 메시지에 추가 된 개별 SCL (스팸 지 수)에 매핑됩니다. SCL이 높을수록 메시지가 스팸으로 표시 되는 것을 나타냅니다. 이 서비스는 SCL을 기반으로 메시지에 대해 작업을 수행 합니다.

SCL의 의미와 메시지에 대해 수행 되는 기본 작업에 대 한 설명은 다음 표에 나와 있습니다. 스팸 필터링 결과을 기반으로 하는 메시지에 대해 수행할 수 있는 작업에 대 한 자세한 내용은 [Configure 스팸 방지 정책 Office 365](configure-your-spam-filter-policies.md)을 참조 하십시오.

||||
|:---:|---|---|
|**SCL**|**정의**|**기본 작업**|
|-1|메시지가 스팸 필터링을 건너뛰었습니다. 예를 들어 수신 허용-보낸 사람에 게 전송 된 메시지 이거나, 수신 하는 전자 메일 서버에서 온 것은 아닙니다. 자세한 내용은 [Office 365에서 수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조 하세요.|받는 사람의 받은 편지 함으로 메시지를 배달 합니다.|
|0, 1|스팸 필터링에서 메시지가 스팸으로 확인 되었습니다.|받는 사람의 받은 편지 함으로 메시지를 배달 합니다.|
|5, 6|스팸 필터링에서 메시지를 **스팸으로** 표시|받는 사람의 정크 메일 폴더로 메시지를 배달 합니다.|
|9 |스팸 필터링에서 메시지가 **높은 신뢰도 스팸으로** 표시 됨|받는 사람의 정크 메일 폴더로 메시지를 배달 합니다.|
|

SCL 2, 3, 4, 7, 8은 스팸 필터링에서 사용 되지 않는다는 것을 알 수 있습니다.

메일 흐름 규칙 (전송 규칙이 라고도 함)을 사용 하 여 메시지의 SCL을 스탬프 처리할 수 있습니다. 메일 흐름 규칙을 사용 하 여 SCL을 설정 하는 경우 값 5 또는 6은 **스팸**에 대 한 스팸 필터링 작업을 트리거하고 값 7, 8 또는 9는 **신뢰도가 높은 스팸**에 대 한 스팸 필터링 작업을 트리거합니다. 자세한 내용은 [메일 흐름 규칙을 사용 하 여 메시지에서 SCL (스팸 지 수) 설정을](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)참조 하십시오.

SCL과 마찬가지로, BCL (bulk 불만 수준)은 잘못 된 대량 전자 메일 ( _회색 메일이_라고도 함)을 식별 합니다. BCL이 많을 수록 대량 메일 메시지가 불만을 창출 하는 것 이며, 따라서 스팸으로 발생할 가능성이 높습니다. 스팸 방지 정책에서 BCL 임계값을 구성 합니다. 자세한 내용은 [office 365에서 스팸 방지 정책 구성](configure-your-spam-filter-policies.md), [OFFICE 365의 BCL (대량 불만 수준)](bulk-complaint-level-values.md)및 [정크 메일 및 대량 전자 메일의 차이점](what-s-the-difference-between-junk-email-and-bulk-email.md)을 참조 하세요.

||
|:-----|
|![LinkedIn Learning용 단축 아이콘](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Office 365를 처음 사용하시나요?**         LinkedIn 학습을 통해 제공 되는 **Microsoft 365 관리자 및 IT 전문가**를 위한 무료 비디오 과정을 소개 합니다.|
