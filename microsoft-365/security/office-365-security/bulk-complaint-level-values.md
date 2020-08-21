---
title: 대량 부상 수준 값
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
description: 관리자는 EOP(Exchange Online Protection)에서 사용되는 BCL(대량 준수 수준) 값에 대해 자세히 배우할 수 있습니다.
ms.openlocfilehash: e24c0c97afcca2e7aa014d929d7b2131c6a2d074
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827436"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>EOP의 BCL(대량 부과 수준)

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 EOP는 대량 메일러의 인바운드 메시지에 BCL(대량 준수 수준)을 할당합니다. BCL은 X-헤더의 메시지에 추가되며 메시지를 스팸으로 식별하는 데 사용되는 [SCL(스팸 지수)과](spam-confidence-levels.md) 유사합니다. BCL이 높다는 것은 대량 메시지가 위조를 생성할 수 있음을 의미합니다(그러기도 하다점). Microsoft는 내부 및 타사 원본을 둘 다 사용하여 대량 메일을 식별하고 해당 BCL을 확인합니다.

메일 대량 메일은 송신 패턴, 콘텐츠 생성, 받는 사람 취득 관행에 따라 다릅니다. 양질 메일 러스터는 관련 내용이 있는 원하는 메시지를 구독자에게 보냅니다. 이러한 메시지는 받는 사람이 몇 가지 일만할 수 있는 사서함 요소입니다. 다른 대량 메일러는 스팸과 비밀히 유사한 원치 않는 메시지를 보내고 받는 사람이 많은 위한 문제를 생성합니다. 대량 메일러에서 보낸 메시지를 대량 메일 또는 회색 메일이라고 합니다.

 스팸 필터링은 BCL **Bulk email** 임계값(지정한 값 또는 값)을 기준으로 메시지를 대량 전자 메일로 표시하고 메시지에 대해 지정된 작업을 수행합니다(기본 작업은 메시지를 받는 사람의 정크 메일 폴더로 배달됨). 자세한 내용은 [스팸 방지 정책 구성 및 정크](configure-your-spam-filter-policies.md) 메일과 [대량 전자 메일의 차이점을 확인하세요.](what-s-the-difference-between-junk-email-and-bulk-email.md)

BCL 임계값은 다음 표에 설명되어 있습니다.

****

|BCL|설명|
|:---:|---|
|0|이 메시지는 대량 메일로 보낸 사람이 보낸 것이 아없습니다.|
|1, 2, 3|몇 가지 만한 추가 정보가 생성되는 대량의 보낸 사람이 메시지를 보냅니다.|
|4, 5, 6, 7|"사서함"에 대한 메시지는 혼합 수의 위만을 생성하는 대량 메일보낸 사람입니다.|
|8, 9|수량의 수의 문제를 일체하는 대량 메일 보낸 사람이 메시지를 받은 경우|
|
