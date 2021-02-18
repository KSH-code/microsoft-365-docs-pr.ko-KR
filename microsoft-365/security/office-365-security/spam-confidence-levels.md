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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)의 메시지에 적용된 SCL(스팸 지수)에 대해 학습할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 05faec8101bfb13265d3cca7c661f2e86ac21c8d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290408"
---
# <a name="spam-confidence-level-scl-in-eop"></a>EOP의 SCL(스팸 지수)

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Exchange Online 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에 사서함이 있는 Microsoft 365 조직에서 인바운드 메시지는 EOP의 스팸 필터링을 통과하고 스팸 점수가 할당됩니다. 이 점수는 X-헤더의 메시지에 추가된 개별 SCL(스팸 지수)에 매핑됩니다. SCL이 높을수록 메시지가 스팸일 가능성이 더 높을 수 있습니다. EOP는 SCL에 따라 메시지에 대한 작업을 실행합니다.

다음 표에는 SCL의 의미와 메시지에 대해 수행되는 기본 작업이 설명되어 있습니다. 스팸 필터링 판정에 따라 메시지에 대해 수행할 수 있는 작업에 대한 자세한 내용은 EOP에서 스팸 방지 정책 구성을 [참조하세요.](configure-your-spam-filter-policies.md)

****

|SCL|정의|기본 작업|
|:---:|---|---|
|-1|메시지가 스팸 필터링을 건너뜁니다. 예를 들어 수신 허용 - 보낸 사람이 보낸 메시지, 수신 허용 - 받는 사람에게 전송된 메시지 또는 IP 허용 목록의 전자 메일 원본 서버에서 보낸 메시지입니다. 자세한 내용은 [EOP에서 수신이 가능한 보낸 사람 목록 만들기를 참조하세요.](create-safe-sender-lists-in-office-365.md)|받는 사람의 받은 편지함으로 메시지를 배달합니다.|
|0, 1|스팸 필터링에서 메시지가 스팸이 아닌 것으로 확인되었습니다.|받는 사람의 받은 편지함으로 메시지를 배달합니다.|
|5, 6|스팸 필터링에서 메시지를 스팸으로 **표시**|받는 사람의 정크 메일 폴더로 메시지를 배달합니다.|
|9 |스팸 필터링에서 메시지를 높은 신뢰도 **스팸으로 표시**|받는 사람의 정크 메일 폴더로 메시지를 배달합니다.|
|

SCL 2, 3, 4, 7 및 8은 스팸 필터링에 사용되지 않습니다.

메일 흐름 규칙(전송 규칙)을 사용하여 메시지에 SCL 스탬프 처리를 할 수 있습니다. 메일 흐름 규칙을 사용하여 SCL을 설정하는 경우 값 5 또는 6은 스팸에 대한 스팸 필터링 작업을 트리거하고 값 7, 8 또는 9는 높은 신뢰도 스팸에 대한 스팸 필터링 작업을 트리거합니다.  자세한 내용은 메일 흐름 규칙을 사용하여 메시지의 [SCL(스팸 지수)을 설정하세요.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

SCL과 유사하게 BCL(대량 불만 수준)은 잘못된 대량 전자 메일(회색 메일)을 _식별합니다._ BCL이 높을수록 대량 메일 메시지가 불만을 발생시킬 가능성이 높으므로 스팸일 가능성이 더 높습니다. 스팸 방지 정책에서 BCL 임계값을 구성합니다. 자세한 내용은 [EOP에서](configure-your-spam-filter-policies.md)스팸 방지 정책 구성, [EOP의 BCL(대량](bulk-complaint-level-values.md)불만 수준) 및 정크 메일과 대량 전자 메일의 차이점을 [참조하세요.](what-s-the-difference-between-junk-email-and-bulk-email.md)

****

![](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Microsoft 365의** 새로운 LinkedIn Learning에 대한 짧은 아이콘이 있나요? LinkedIn Learning에서 제공한 **Microsoft 365** 관리자 및 IT pros를 위한 무료 비디오 과정을 검색합니다.
