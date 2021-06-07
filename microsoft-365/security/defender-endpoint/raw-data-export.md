---
title: Defender Microsoft 365 스트림
description: 고급 헌팅 이벤트를 이벤트 허브 Microsoft 365 Azure 저장소 계정으로 스트리밍하도록 Defender를 구성하는 방법을 설명합니다.
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
ms.openlocfilehash: 971cc757dcbd0a190917d2a5f11eb7f68b758008
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778200"
---
# <a name="streaming-api"></a>스트리밍 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>고급 헌팅 이벤트를 이벤트 허브 및/또는 Azure 저장소 계정으로 스트리밍합니다.

Microsoft 365 Defender는 고급 헌팅을 [](../defender/advanced-hunting-overview.md) 통해 사용할 수 있는 모든 이벤트를 이벤트 [허브](/azure/event-hubs/) 및/또는 Azure 저장소 계정으로 [스트리밍할 수 있도록 지원합니다.](/azure/event-hubs/)



## <a name="in-this-section"></a>이 섹션의 내용

항목 | 설명
:---|:---
[Azure 이벤트 허브로 이벤트 스트림](raw-data-export-event-hub.md)| 테넌트에서 스트리밍 API를 사용하도록 설정하는 방법을 알아보고 고급 [](../defender/advanced-hunting-overview.md) 헌팅을 이벤트 허브로 Microsoft 365 Defender를 구성합니다.
[Azure 저장소 계정으로 이벤트 스트림](raw-data-export-storage.md)| 테넌트에서 스트리밍 API를 사용하도록 설정하는 방법을 알아보고 Azure [](../defender/advanced-hunting-overview.md) Microsoft 365 고급 헌팅을 스트리밍하도록 Defender를 구성합니다.


## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](../defender/advanced-hunting-overview.md)
- [Azure 이벤트 허브 설명서](/azure/event-hubs/)
- [Azure Storage 계정 설명서](/azure/storage/common/storage-account-overview)
