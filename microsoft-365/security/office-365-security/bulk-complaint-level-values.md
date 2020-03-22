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
description: Office 365에서 BCL (대량 bomplain 수준) 값에 대해 알아봅니다.
ms.openlocfilehash: 6b90064db7dd9b27fdc729b65fb798dfbe756da7
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895396"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a>Office 365의 BCL (대량 불만 수준)

대량 메일 발송은 해당 보내는 패턴, 콘텐츠 만들기 및 받는 사람 가져오기 방법에 따라 달라 집니다. 일부는 필요한 메시지를 구독자에 게 관련 콘텐츠와 함께 전송 하는 좋은 대량 메일입니다. 이러한 메시지는 받는 사람의 불만을 거의 발생 시킵니다. 기타 대량 메일 전송 스팸과 유사한 원치 않는 메시지를 보내며 받는 사람 으로부터 많은 불만을 생성 합니다. 대량 메일 프로그램에서 보내는 메시지를 bulk mail 또는 회색 메일 이라고 합니다.

서로 다른 유형의 대량 메일 메일과 메시지를 구별 하기 위해 Exchange Online 사서함을 사용 하지 않고 Exchange Online 또는 독립 실행형 Exchange Online Protection (EOP) 365에 대량 우편물을 전송 하는 경우 인바운드 전자 메일이 추가 된 BCL (대량 불만 수준)에 할당 됩니다. X-헤더에 있는 메시지입니다. BCL은 메시지를 스팸으로 식별 하는 데 사용 되는 [SCL (스팸](spam-confidence-levels.md) 지 수)과 유사 합니다. BCL이 높을수록 대량 메시지가 불만을 더 많이 창출 하 게 되며, 따라서 스팸으로 발생할 가능성이 높습니다. Microsoft에서는 내부 및 타사 소스를 모두 사용 하 여 대량 메일을 식별 하 고 적절 한 BCL을 결정 합니다.

 스팸 필터링은 메시지를 BCL 임계값 (기본값 또는 지정한 값)을 기반으로 **대량 전자 메일로** 표시 하 고 메시지에 대해 지정 된 작업을 수행 합니다 (기본 작업은 메시지를 받는 사람의 정크 메일 폴더로 배달 됨). 자세한 내용은 [Office 365에서 스팸 방지 정책 구성](configure-your-spam-filter-policies.md) 및 [정크 메일과 대량 전자 메일의 차이점](what-s-the-difference-between-junk-email-and-bulk-email.md)을 참조 하세요.

다음 표에는 BCL 임계값에 대 한 설명이 나와 있습니다.

|||
|:---:|---|
|**BCL**|**설명**|
|개|메시지가 대량 보낸 사람 으로부터 온 것이 아닙니다.|
|1, 2, 3|메시지가 몇 가지 불만을 생성 하는 대량 보낸 사람의 메시지입니다.|
|4, 5, 6, 7|이 메시지는 수많은 불만을 생성 하는 대량 보낸 사람 으로부터 온 것입니다.|
|8, 9|이 메시지는 많은 수의 불만을 생성 하는 대량 보낸 사람 으로부터 온 것입니다.|
|
