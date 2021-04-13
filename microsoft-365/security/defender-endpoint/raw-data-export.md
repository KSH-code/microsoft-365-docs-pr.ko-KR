---
title: Endpoint용 Microsoft Defender 이벤트 스트림
description: 고급 헌팅 이벤트를 이벤트 허브 또는 Azure 저장소 계정으로 스트리밍하도록 끝점용 Microsoft Defender를 구성하는 방법을 설명합니다.
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
ms.openlocfilehash: f6a45629d610ea3cc3ca7d517021a215b72b1439
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688756"
---
# <a name="raw-data-streaming-api"></a>원시 데이터 스트리밍 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037) 

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>고급 헌팅 이벤트를 이벤트 허브 및/또는 Azure 저장소 계정으로 스트리밍합니다.

Endpoint용 Defender는 고급 헌팅을 통해 사용할 수 있는 모든 이벤트를 이벤트 [허브](https://docs.microsoft.com/azure/event-hubs/) 및/또는 Azure 저장소 계정으로 [스트리밍할 수 있도록 지원합니다.](https://docs.microsoft.com/azure/event-hubs/) [](advanced-hunting-overview.md)

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a>이 섹션의 내용

항목 | 설명
:---|:---
[Azure 이벤트 허브로 끝점용 Microsoft Defender 이벤트 스트림](raw-data-export-event-hub.md)| 테넌트에서 스트리밍 API를 사용하도록 설정하는 방법을 알아보고 [](advanced-hunting-overview.md) 고급 헌팅을 이벤트 허브로 스트리밍하도록 끝점용 Defender를 구성합니다.
[Azure 저장소 계정으로 끝점 이벤트용 Stream Defender](raw-data-export-storage.md)| 테넌트에서 스트리밍 API를 사용하도록 설정하는 방법을 알아보고 [](advanced-hunting-overview.md) Azure 저장소 계정으로 고급 헌팅을 스트리밍하도록 끝점용 Defender를 구성합니다.


## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [Azure 이벤트 허브 설명서](https://docs.microsoft.com/azure/event-hubs/)
- [Azure Storage 계정 설명서](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
