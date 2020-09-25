---
title: Microsoft Threat Protection의 미리보기 기능
description: Microsoft 365 보안의 새로운 기능에 대해 알아봅니다.
keywords: 미리 보기, 신규, M365 보안, 보안, 365, 기능
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f01f76ac591b4c2be9873fa87ec416939158acd3
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195506"
---
# <a name="microsoft-threat-protection-preview-features"></a>Microsoft Threat Protection의 미리 보기 기능

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 위협 방지


Microsoft Threat Protection 서비스는 새로운 기능 향상 및 기능을 포함하기 위해 지속적으로 업데이트됩니다.

Microsoft Threat Protection 미리 보기 릴리스의 새 기능에 대해 알아보고 미리 보기 환경을 설정하여 출시 예정 기능을 먼저 사용해보세요.

일반적으로 제공되는 새 기능에 대한 자세한 내용은 [Microsoft Threat Protection의 새 기능](whats-new.md)을 참조하세요.

## <a name="turn-on-preview-features"></a>미리 보기 기능 설정
기능이 일반적으로 사용되기 전에 전체 환경을 개선하는 데 도움이 되는 피드백을 제공할 수 있는 예정된 기능에 액세스할 수 있습니다.

미리 보기 환경을 설정하여 최초로 예정된 기능을 사용해보세요.

1. 탐색 창에서 **설정**을 선택합니다.

2. **Microsoft Threat Protection**을 선택합니다.


3. **미리 보기 기능** > **미리 보기 기능 설정**을 선택합니다. 

3. **저장**을 선택합니다.

**미리 보기 기능 설정** 확인란이 선택되어 있는 경우, 미리 보기 기능을 설정했음을 알 수 있습니다. 

## <a name="preview-features"></a>미리 보기 기능
다음 기능과 향상 기능은 현재 미리 보기에서 사용할 수 있습니다.

- **[Microsoft Threat Protection API](api-overview.md)**- lop 수준의 Microsoft Threat Protection API는 사용자가 공유 인시던트와 고급 헌팅 테이블에 따라 워크플로를 자동화할 수 있도록 해줍니다. 
- **[고급 헌팅의 IdentityDirectoryEvents 테이블](advanced-hunting-identitydirectoryevents-table.md)**- Active Directory(AD)를 실행하는 온-프레미스 도메인 컨트롤러와 관련된 이벤트를 찾습니다. 이 테이블에서는 도메인 컨트롤러의 다양한 ID 관련 이벤트뿐만 아니라 시스템도 포함합니다.
- **[고급 헌팅에서의 조치 취하기](advanced-hunting-take-action.md)** — [고급 헌팅](advanced-hunting-overview.md)에서 찾은 위협혹은 주소가 손상된 자산을 신속하게 포함합니다.
- **[포털 스키마 참조](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** — 고급 헌팅 스키마 테이블에 대한 정보를 보안 센터에서 직접 확인하세요. 테이블 및 열 설명 외에도 이 편리한 참조는 지원되는 이벤트 유형(`ActionType` 값) 및 예제 쿼리에 대 한 정보를 제공합니다.

