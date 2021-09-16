---
title: Stream Microsoft 365 Defender 이벤트
description: 고급 헌팅 이벤트를 Microsoft 365 Defender 허브 또는 Azure 저장소 계정으로 스트리밍하도록 구성하는 방법을 설명합니다.
keywords: 원시 데이터 내보내기, 스트리밍 API, API, 이벤트 허브, Azure 저장소, 저장소 계정, 고급 헌팅, 원시 데이터 공유
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.technology: mde
ms.openlocfilehash: 0b8912ee40c090522a0b6228643f37b161dbde14
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2021
ms.locfileid: "59401233"
---
# <a name="streaming-api"></a>스트리밍 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>고급 헌팅 이벤트를 이벤트 허브 및/또는 Azure 저장소 계정으로 스트리밍합니다.

Microsoft 365 Defender 고급 헌팅을 [](../defender/advanced-hunting-overview.md) 통해 이벤트 [](/azure/event-hubs/) 허브 및/또는 Azure 저장소 계정으로 스트리밍 이벤트를 [지원합니다.](/azure/event-hubs/)

스트리밍 API의 Microsoft 365 Defender 자세한 내용은 비디오를 [참조하세요.](https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga)

## <a name="in-this-section"></a>이 섹션의 내용

항목 | 설명
:---|:---
[Azure 이벤트 허브로 이벤트 스트림](streaming-api-event-hub.md)| 테넌트에서 스트리밍 API를 사용하도록 설정하는 방법을 알아보고 고급 헌팅을 이벤트 Microsoft 365 Defender 스트리밍하도록 구성합니다. [](../defender/advanced-hunting-overview.md)
[Azure 저장소 계정으로 이벤트 스트림](streaming-api-storage.md)| 테넌트에서 스트리밍 API를 사용하도록 설정하는 방법을 알아보고 Azure Microsoft 365 Defender 고급 [헌팅을](advanced-hunting-overview.md) 스트리밍하도록 구성합니다.
[지원되는 이벤트 유형](supported-event-types.md) | 스트리밍 API에서 지원하는 고급 헌팅 이벤트 유형에 대해 자세히 알아보습니다.


## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](../defender/advanced-hunting-overview.md)
- [Azure 이벤트 허브 설명서](/azure/event-hubs/)
- [Azure Storage 계정 설명서](/azure/storage/common/storage-account-overview)
