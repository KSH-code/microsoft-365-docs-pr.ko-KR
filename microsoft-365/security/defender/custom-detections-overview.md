---
title: 사용자 지정 검색의 Microsoft 365 Defender
description: 고급 헌팅을 사용하여 사용자 지정 검색을 만들고 경고를 생성하는 방법 이해
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, 사용자 지정 감지, schema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 0ad75d2cf67360c04597f56816e22755fae3388b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208424"
---
# <a name="custom-detections-overview"></a>사용자 지정 검색 개요

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender
- 끝점용 Microsoft Defender

사용자 지정 검색을 사용하면 위반 활동 및 잘못 구성된 끝점을 포함하여 다양한 이벤트 및 시스템 상태의 사전 대응을 모니터링하고 대응할 수 있습니다. 이 작업은 경고 및 응답 작업을 자동으로 트리거하는 사용자 지정 가능한 검색 규칙에 의해 가능합니다.

사용자 지정 검색은 고급 헌팅과 함께 작동하며, 네트워크의 광범위한 이벤트 및 시스템 정보 집합을 다루는 강력하고 유연한 쿼리 언어를 제공합니다. [](advanced-hunting-overview.md) 정기적으로 실행되도록 설정하여 일치하는 항목이 있을 때마다 경고를 생성하고 대응 조치를 취할 수 있습니다.

사용자 지정 검색을 통해:
- 고급 헌팅 쿼리로 구축된 규칙 기반 검색에 대한 알림
- 자동 응답 작업

## <a name="see-also"></a>참고 항목
- [사용자 지정 검색 규칙 만들기 및 관리](custom-detection-rules.md)
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [끝점용 Microsoft Defender에서 고급 헌팅 쿼리 마이그레이션](advanced-hunting-migrate-from-mde.md)
