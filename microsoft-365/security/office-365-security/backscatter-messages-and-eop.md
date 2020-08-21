---
title: EOP의 후방 산란
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 후방 분산 및 EOP(기능 Microsoft Exchange Online 대한 정보)에 대해 설명합니다.
ms.openlocfilehash: f1705fd7fc30c9a8cde5f6acfaf145861de3af08
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827788"
---
# <a name="backscatter-in-eop"></a>EOP의 후방 산란

*후방 분산 장치는* 보내지 않은 메시지에 대해 받은 배달 못 함 보고서(NDR 또는 반송 메시지라고도 함)입니다. 스푸핑(스푸핑) 메시지의 보낸 사람: 주소를 사용하며 메시지에 신중한 전자 메일 주소를 보내는 경우가 종종 있습니다. 따라서 스프라이트가 존재하지 않는 받는 사람에게 메시지를 보내는 경우(스팸은 볼륨이 많이) 대상 전자 메일 서버는 기본적으로 NDR에서 배달할 수 없는 메시지를 보낸 사람: 주소의 위조된 보낸 사람으로 반환하는 데 대비하게 됩니다.

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 EOP는 NDR을 생성하지 않고 초대된 원본으로부터 메시지를 식별하고 자동으로 삭제할 수 있도록 하기 위해 매우 계획입니다. 그러나 이 경우에는 서비스를 통과하는 볼륨 전자 메일이 여연히 나오는 경우에 대비하여 EOP가 의도치 않게 후방 방송을 전송할 가능성이 있습니다.

Backscatterer.org 후방 산란을 추적하는 전자 메일 서버의 차단 목록(DNS 차단 목록 또는 DNSBL이라고도 함)을 유지 관리하며 EOP 서버가 이 목록에 있을 수 있습니다. 하지만 Backscatterer.org 차단 목록은 스패커 목록이 아니기 때문에(자체 허용에 따라) 이 를 제거하지 않아보겠습니다.

> [!TIP]
> 웹 Backscatter.org() 서비스에서는 거부 모드 대신(대부분의 경우 항상 일부 후방 분산을 보냅니다)의 안전 모드에서 수신 전자 <http://www.backscatterer.org/?target=usage> 메일을 확인하는 것이 좋습니다.
