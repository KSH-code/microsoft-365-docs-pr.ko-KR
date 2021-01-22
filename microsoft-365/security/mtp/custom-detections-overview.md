---
title: Microsoft 365 Defender의 사용자 지정 검색 개요
description: 고급 헌팅을 사용하여 사용자 지정 검색을 만들고 경고를 생성하는 방법 이해
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 사용자 지정 감지, schema, kusto, microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ae9617a55fd5efb40a3aba07202ebfb1494d4db6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928811"
---
# <a name="custom-detections-overview"></a>사용자 지정 검색 개요

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

사용자 지정 검색을 사용하면 위반 의심 활동 및 잘못 구성된 끝점을 포함하여 다양한 이벤트 및 시스템 상태의 사전 대응을 모니터링하고 대응할 수 있습니다. 이 작업은 응답 작업뿐만 아니라 경고를 자동으로 트리거하는 사용자 지정 가능한 검색 규칙에 의해 가능합니다.

사용자 지정 검색은 고급 헌팅과 함께 [작동하며,](advanced-hunting-overview.md)네트워크의 광범위한 이벤트 및 시스템 정보를 다루는 강력하고 유연한 쿼리 언어를 제공합니다. 이러한 규칙이 정기적으로 실행될 수 있으며, 일치할 때마다 경고를 생성하고 응답 작업을 수행할 수 있습니다.

사용자 지정 검색은 제공하는 사항:
- 고급 헌팅 쿼리에서 구축된 규칙 기반 검색에 대한 알림
- 자동 응답 작업

## <a name="related-topic"></a>관련 항목
- [사용자 지정 검색 규칙 만들기 및 관리](custom-detection-rules.md)
- [고급 헌팅 개요](advanced-hunting-overview.md)
