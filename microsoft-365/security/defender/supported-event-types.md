---
title: Microsoft 365 Defender 스트리밍 API에서 지원되는 이벤트 유형
description: 스트리밍 API에서 지원되는 헌팅 이벤트 유형(테이블)에 대해 자세히 알아보기
keywords: 원시 데이터 내보내기, 스트리밍 API, API, 이벤트 허브, Azure 저장소, 저장소 계정, 헌팅, 원시 데이터 공유
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 780cac298206127d52e14b3888a0a8d7f05ae0c5
ms.sourcegitcommit: afee35210f8d68a7f20676ff2a829464b0b0adb2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2021
ms.locfileid: "60216973"
---
# <a name="supported-microsoft-365-defender-event-types-in-event-streaming-api"></a>이벤트 Microsoft 365 Defender API에서 지원되는 이벤트 유형

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


이벤트 스트리밍 API는 더 많은 이벤트 유형을 지원하기 위해 지속적으로 확장되고 있습니다. 일반적으로 사용할 수 있는 헌팅 테이블, 현재 공개 미리 보기 또는 아직 지원되지 않는 헌팅 테이블에 대해 자세히 알아보습니다. 
**신규 - 전자 메일 이벤트 유형/테이블이 이제 GA가 됩니다.**

## <a name="hunting-tables-support-status-in-event-streaming-api"></a>헌팅 테이블은 이벤트 스트리밍 API에서 상태를 지원합니다.

| 테이블 이름 | 상태 |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | GA |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | GA  |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | 아직 지원되지 않습니다. |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** |GA |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** |GA |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | GA |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | GA |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | GA |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | GA |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** |GA |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | GA |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | GA |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | GA |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | GA |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | GA |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | GA |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | GA |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | 아직 지원되지 않습니다. |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | 아직 지원되지 않습니다. |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | 아직 지원되지 않습니다. |

