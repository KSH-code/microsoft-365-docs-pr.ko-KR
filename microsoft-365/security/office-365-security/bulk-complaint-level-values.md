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
description: 관리자는 EOP(대량 불만 수준)에 사용되는 BCL(대량 불만 수준) 값에 대해 Exchange Online Protection 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11f884ec6b32795deba09c0f1ba88055a6422e9b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192379"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>EOP의 BCL(대량 불만 수준)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 사서함이 없는 Exchange Online 또는 EOP(독립 실행형 Exchange Online Protection)에 사서함이 있는 Exchange Online 조직에서 EOP는 대량 메일러의 인바운드 메시지에 BCL(대량 불만 수준)을 할당합니다. BCL은 X-헤더의 메시지에 추가된 후 메시지를 스팸으로 식별하는 데 사용되는 [SCL(스팸](spam-confidence-levels.md) 지수)과 유사합니다. BCL이 높을수록 대량 메시지가 불만을 생성할 가능성이 높기 때문에 스팸일 가능성이 더 높을 수 있습니다. Microsoft는 내부 및 타사 소스를 모두 사용하여 대량 메일을 식별하고 적절한 BCL을 파악합니다.

대량 메일은 보내는 패턴, 콘텐츠 생성 및 받는 사람 취득 관행에 따라 다릅니다. 양호한 대량 메일러는 구독자에게 관련 콘텐츠가 있는 원하는 메시지를 전송합니다. 이러한 메시지는 받는 사람으로부터 몇 가지 불만을 생성합니다. 다른 대량 메일러는 스팸과 매우 많고 받는 사람으로부터 많은 불만을 생성하는 원치 않는 메시지를 보냅니다. 대량 메일러의 메시지는 대량 메일 또는 회색 메일로 알려져 있습니다.

 스팸 필터링은 BCL  임계값(지정한 값)을 기준으로 메시지를 대량 전자 메일로 표시하고 메시지에 대해 지정된 작업을 실행합니다(기본 작업은 메시지를 받는 사람의 정크 메일 폴더로 배달). 자세한 내용은 [스팸](configure-your-spam-filter-policies.md) 방지 정책 구성 및 정크 메일과 대량 전자 메일의 [차이점을 참조하세요.](what-s-the-difference-between-junk-email-and-bulk-email.md)

테넌트 허용/차단 목록을 사용하여 대량 메일 필터링에 대한 예외를 구성할 수 있습니다. 지정된 도메인의 보낸 사람이 보낸 메시지는 스팸 방지  정책에서 대량 전자 메일 스팸 필터링 판정에 대한 작업을 받지 않습니다. 자세한 내용은 [테넌트 허용/차단 목록 관리를 참조하세요.](tenant-allow-block-list.md)

BCL 임계값은 다음 표에 설명되어 있습니다.

****

|BCL|설명|
|:---:|---|
|0|메시지가 대량 보낸 사람이 아닌 경우|
|1, 2, 3|이 메시지는 몇 가지 불만을 생성하는 대량 보낸 사람이 보낸 것입니다.|
|4, 5, 6, 7<sup>\*</sup>|이 메시지는 불만이 혼합된 수의 불만을 생성하는 대량 보낸 사람이 보낸 것입니다.|
|8, 9|이 메시지는 많은 불만을 생성하는 대량 보낸 사람이 보낸 것입니다.|
|

<sup>\*</sup> 스팸 방지 정책에 사용되는 기본 임계값입니다.
