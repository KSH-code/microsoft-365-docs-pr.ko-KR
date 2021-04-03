---
title: Microsoft Defender ATP의 사용자 지정 검색 개요
ms.reviewer: ''
description: 고급 헌팅을 사용하여 사용자 지정 검색을 만들고 경고를 생성하는 방법 이해
keywords: 사용자 지정 검색, 경고, 검색 규칙, 고급 헌팅, 헌팅, 쿼리, 응답 작업, 간격, mdatp, Microsoft Defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 20bd70653f535bb732c252224c1e6efd5cf65035
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500649"
---
# <a name="custom-detections-overview"></a>사용자 지정 검색 개요

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


사용자 지정 검색을 사용하면 위반 활동 및 잘못 구성된 장치를 포함하여 다양한 이벤트 및 시스템 상태의 사전 모니터링 및 대응을 할 수 있습니다. 경고 및 응답 작업을 자동으로 트리거하는 사용자 지정 가능한 검색 규칙으로 이 작업을 수행할 수 있습니다.

사용자 지정 검색은 고급 헌팅과 함께 작동하며, 네트워크의 광범위한 이벤트 및 시스템 정보 집합을 다루는 강력하고 유연한 쿼리 언어를 제공합니다. [](advanced-hunting-overview.md) 이러한 경고를 정기적으로 실행하여 일치하는 경우 경고를 생성하고 응답 작업을 수행할 수 있습니다.

사용자 지정 검색을 통해:
- 고급 헌팅 쿼리로 구축된 규칙 기반 검색에 대한 알림
- 파일 및 장치에 적용되는 자동 응답 작업

## <a name="related-topics"></a>관련 항목
- [검색 규칙 만들기](custom-detection-rules.md)
- [검색 규칙 보기 및 관리](custom-detections-manage.md)
- [지능형 헌팅 개요](advanced-hunting-overview.md)
