---
title: 대량 불만 수준 값
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 관리자는 EOP (Exchange Online Protection)에서 사용 되는 BCL (대량 준수 수준) 값에 대해 알아볼 수 있습니다.
ms.openlocfilehash: d59bb152de075bb807e3cae72839fe459d7da40f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203530"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>EOP의 BCL (대량 불만 수준)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange online 사서함이 없는 Microsoft 365 조직의 EOP (exchange online Protection) 조직에 사서함이 대량 우편물의 인바운드 메시지에 대 한 BCL (대량 준수 수준)을 할당 EOP. BCL은 X-헤더의 메시지에 추가 되며 메시지를 스팸으로 식별 하는 데 사용 되는 [SCL (스팸](spam-confidence-levels.md) 지 수)과 유사 합니다. BCL이 높을수록 대량 메시지가 불만을 더 많이 창출 하 게 되며, 따라서 스팸으로 발생할 가능성이 높습니다. Microsoft에서는 내부 및 타사 소스를 모두 사용 하 여 대량 메일을 식별 하 고 적절 한 BCL을 결정 합니다.

대량 메일 발송은 해당 보내는 패턴, 콘텐츠 만들기 및 받는 사람 가져오기 방법에 따라 달라 집니다. 좋은 대량 메일 보낸 사람에 게 관련 콘텐츠가 포함 된 원하는 메시지를 구독자에 게 보냅니다. 이러한 메시지는 받는 사람의 불만을 거의 발생 시킵니다. 기타 대량 메일 전송 스팸과 유사한 원치 않는 메시지를 보내며 받는 사람 으로부터 많은 불만을 생성 합니다. 대량 메일 프로그램에서 보내는 메시지를 bulk mail 또는 회색 메일 이라고 합니다.

 스팸 필터링은 메시지를 BCL 임계값 (기본값 또는 지정한 값)을 기반으로 **대량 전자 메일로** 표시 하 고 메시지에 대해 지정 된 작업을 수행 합니다 (기본 작업은 메시지를 받는 사람의 정크 메일 폴더로 배달 됨). 자세한 내용은 [스팸 방지 정책 구성](configure-your-spam-filter-policies.md) 및 [정크 메일과 대량 전자 메일의 차이점](what-s-the-difference-between-junk-email-and-bulk-email.md) 을 참조 하세요.

다음 표에는 BCL 임계값에 대 한 설명이 나와 있습니다.

****

|BCL|설명|
|:---:|---|
|개|메시지가 대량 보낸 사람 으로부터 온 것이 아닙니다.|
|1, 2, 3|메시지가 몇 가지 불만을 생성 하는 대량 보낸 사람의 메시지입니다.|
|4, 5, 6, 7|이 메시지는 수많은 불만을 생성 하는 대량 보낸 사람 으로부터 온 것입니다.|
|8, 9|이 메시지는 많은 수의 불만을 생성 하는 대량 보낸 사람 으로부터 온 것입니다.|
|
