---
title: 후방 분산 메시지 및 EOP
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Backscatter 메시지는 위조 된 전자 메일 주소로 전송 되는 자동 바운스 메시지입니다. 후방 분산 DNSBL는 여러 합법적인 전자 메일 원본을 포함할 수 있는 백 분산 메시지를 전송 하는 서버를 식별 합니다. 이는 스팸 발송자 목록이 아니기 때문에 후방 분산 DNSBL에서 직접 제거 하려고 하지 않습니다.
ms.openlocfilehash: 20ed828680dd20e82819730e6dcd509b896d8616
ms.sourcegitcommit: 1b1425142ae06deae3da10a7d30dce4db029d6d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "42313813"
---
# <a name="backscatter-messages-and-eop"></a>후방 분산 메시지 및 EOP

*Backscatter 메시지* 는 보내지 않은 메시지에 대해 수신 하는 배달 못 함 보고서 (ndr 또는 바운스 메시지)입니다. 스팸 발송자가 메시지의 보낸 사람: 주소를 위조 하 고, 실제 전자 메일 주소를 사용 하 여 메시지에 대 한 신뢰성을 전송 하는 경우가 많습니다. 따라서 발신자가 존재 하지 않는 받는 사람에 게 메시지를 보내는 경우 (스팸 is 고용량 작업) 대상 전자 메일 서버는 NDR에 배달할 수 없는 메시지를 반환 하 여 보낸 사람: 주소에서 위조 된 송신자에 게 보낼 수 있습니다.

EOP (Exchange Online Protection)를 사용 하면 NDR을 생성 하지 않고 dubious 원본에서 메시지를 식별 하 고 자동으로 삭제할 수 있습니다. 그러나 서비스를 통해 전달 되는 엄청난 양의 전자 메일을 기반으로 하는 경우에는 EOP에서 실수로 분산 된 메시지를 보낼 가능성이 항상 있습니다.

Backscatterer.org에서는 후방 산란 메시지를 전송 하는 데 사용한 전자 메일 서버의 차단 목록 (DNS 차단 목록 또는 DNSBL이 라고도 함)을 유지 관리 하 고이 목록에 EOP 서버를 표시할 수 있습니다. 그러나 Backscatterer.org 차단 목록에서 본인을 제거 하지는 않습니다 (자체 허용).

> [!TIP]
> Backscatter.org website (<http://www.backscatterer.org/?target=usage>)는 서비스를 사용 하 여 거부 모드 대신 안전 모드에서 들어오는 전자 메일을 확인 하는 것이 좋습니다 (큰 전자 메일 서비스는 거의 모든 메시지를 항상 발송 합니다.).
