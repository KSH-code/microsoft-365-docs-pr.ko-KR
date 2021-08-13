---
title: 사용자 리소스 유형
description: 사용자와 관련된 최신 Microsoft Defender for Endpoint 경고를 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: f74e37e502db8a0406a8930dc29d3d35652de7a75d517c332ef219446e129a51
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "53817174"
---
# <a name="user-resource-type"></a>사용자 리소스 유형

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


메서드|반환 형식 |설명
:---|:---|:---
[목록 사용자 관련 경고](get-user-related-alerts.md) | [경고](alerts.md) 컬렉션 |  사용자와 연결된 모든 경고를 [나열합니다.](user.md)
[사용자 관련 장치 목록](get-user-related-machines.md) | [machine collection(컴퓨터](machine.md) 컬렉션) | 사용자가 로그온한 모든 장치를 [나열합니다.](user.md)
