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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 관리자는 EOP(Exchange Online Protection)에서 사용되는 BCL(대량 준수 수준) 값에 대해 학습할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 403f79a1ce81ae13a23aa77f4cca7654939d7814
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165970"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>EOP의 BCL(대량 불만 수준)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 요금제 1 및 계획 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Exchange Online 사서함이 없는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 EOP는 대량 메일러의 인바운드 메시지에 BCL(대량 규격 수준)을 할당합니다. BCL은 X-헤더의 메시지에 추가된 후 메시지를 스팸으로 식별하는 데 사용되는 [SCL(스팸](spam-confidence-levels.md) 지수)과 유사합니다. BCL이 높을수록 대량 메시지가 불만을 생성할 가능성이 높기 때문에 스팸일 가능성이 더 높음 Microsoft는 내부 및 타사 원본을 모두 사용하여 대량 메일을 식별하고 적절한 BCL을 파악합니다.

대량 메일러는 보내는 패턴, 콘텐츠 생성 및 받는 사람 취득 사례에 따라 다릅니다. 양호한 대량 메일러는 구독자에게 관련 콘텐츠가 있는 원하는 메시지를 전송합니다. 이러한 메시지는 받는 사람으로부터 몇 가지 불만을 생성합니다. 다른 대량 메일러는 스팸과 매우 많고 받는 사람으로부터 많은 불만을 생성하는 원치 않는 메시지를 보냅니다. 대량 메일러의 메시지는 대량 메일 또는 회색 메일로 알려져 있습니다.

 스팸 필터링은 BCL  임계값(기본값 또는 지정한 값)에 따라 메시지를 대량 전자 메일로 표시하고 메시지에 대해 지정된 작업을 실행합니다(기본 작업은 메시지를 받는 사람의 정크 메일 폴더로 배달). 자세한 내용은 스팸 [](configure-your-spam-filter-policies.md) 방지 정책 구성 및 정크 메일과 대량 전자 메일의 [차이점을 참조하세요.](what-s-the-difference-between-junk-email-and-bulk-email.md)

BCL 임계값은 다음 표에 설명되어 있습니다.

****

|BCL|설명|
|:---:|---|
|0|메시지가 대량 보낸 사람이 아닌 경우|
|1, 2, 3|이 메시지는 몇 가지 불만을 생성하는 대량 보낸 사람이 보낸 것입니다.|
|4, 5, 6, 7<sup>\*</sup>|이 메시지는 혼합된 불만 수를 생성하는 대량 보낸 사람이 보낸 것입니다.|
|8, 9|이 메시지는 많은 불만을 생성하는 대량 보낸 사람이 보낸 것입니다.|
|

<sup>\*</sup> 스팸 방지 정책에 사용되는 기본 임계값입니다.
