---
title: 대량 불만 수준 값, 대량 메일, BCL 수준, BCL works, BCL 등급, 스팸 방지, 스팸 방지 헤더, 대량 메일 필터링, 대량 메일 중지
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Office 365의 BCL (대량 확인 수준) 값에 대해 알아봅니다.
ms.openlocfilehash: b0eb922323421834eae77b8c5430f1bd8f48c8ee
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599725"
---
# <a name="bulk-complaint-level-values"></a>대량 불만 수준 값

대량 메일 발송은 해당 보내는 패턴, 콘텐츠 작성 및 목록 가져오기 방법에 따라 달라 집니다. 일부는 관련 콘텐츠가 포함 된 메시지를 구독자에 게 보내는 좋은 대량 메일입니다. 이러한 메시지는 받는 사람의 불만을 거의 발생 시킵니다. 기타 대량 메일 전송 스팸과 유사한 원치 않는 메시지를 보내며 받는 사람 으로부터 많은 불만을 생성 합니다.

이러한 유형의 대량 메일을 구별 하기 위해 대량 우편물의 메시지에 BCL (대량 불만 수준) 등급이 할당 됩니다. BCL 등급은 대량 메일에 불만을 생성 하기 위해 얼마나 큰 지에 따라 1에서 9 사이의 범위를 가집니다. BCL 9의 등급이 있는 보낸 사람은 받는 사람에 게 많은 불만을 생성할 수 있는 반면, BCL 3의 등급은 많은 불만을 생성할 가능성이 적습니다. Microsoft에서는 내부 및 타사 소스를 모두 사용 하 여 대량 메일을 식별 하 고 적절 한 BCL을 결정 합니다. 이 메시지 헤더에 대 한 자세한 내용은 [스팸 방지 메시지 헤더](anti-spam-message-headers.md)를 참조 하세요.

등급이 9 인 대량 메일 발송은 불만을 창출 하기 때문에 기본 BCL은 7입니다. 즉, 그 이후에는 불만 수준이 7이 고 메일이 수락 되지 않을 때까지 대량 메일이 수락 됩니다. 등급이 낮을수록 대량 메일이 더 적게 수락 됩니다. 사용자가 있고, 대량 메일을 구분 하 고, BCL을 4로 설정 하는 경우에는 4 보다 더 높은 BCL을 사용 하는 대량 메일이 허용 되지 않습니다.

BCL 값을 사용 하 여 조직에서 필요한 대량 필터링 수준을 설정 하려면 [스팸 필터 정책 구성](configure-your-spam-filter-policies.md)의 단계를 수행 합니다.

다음 표에는 현재 사용 중인 BCL 값에 대 한 설명이 나와 있습니다.

|||
|:-----|:-----|
|**BCL 값**|**설명**|
|개|메시지가 대량 보낸 사람 으로부터 온 것이 아닙니다.|
|1, 2, 3|메시지가 몇 가지 불만을 생성 하는 대량 보낸 사람의 메시지입니다.|
|4, 5, 6, 7|이 메시지는 수많은 불만을 생성 하는 대량 보낸 사람 으로부터 온 것입니다.|
|8, 9|이 메시지는 많은 수의 불만을 생성 하는 대량 보낸 사람 으로부터 온 것입니다.|
