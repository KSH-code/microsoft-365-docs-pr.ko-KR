---
title: 앱의 미리 보기 Microsoft 365 Defender
description: Microsoft 365 보안의 새로운 기능에 대해 알아봅니다.
keywords: 미리 보기, 신규, M365 보안, 보안, 365, 기능
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ba3e607b54294a8aa61fd0a6c9c0d13e07f873035b0b98d336328b4c1e858bcf
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "53799265"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Defender 미리 보기 기능

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

새로운 Microsoft 365 Defender 기능을 포함하기 위해 Microsoft 365 Defender 서비스를 지속적으로 업데이트하고 있습니다.

Microsoft 365 Defender 릴리스의 새로운 기능에 대해 알아보고 미리 보기 환경을 켜서 예정된 기능을 처음 사용해 볼 수 있습니다.

일반적으로 사용할 수 있는 새로운 기능에 대한 자세한 내용은 에서 새로운 기능을 [Microsoft 365 Defender.](whats-new.md)

 ## <a name="what-you-need-to-know"></a>알아야 할 것

공개 미리 보기에서 기능을 사용할 때 다음과 같은 기능을 사용할 수 있습니다.

- 기능이 제한되거나 제한될 수 있습니다. 예를 들어 이 기능은 하나의 플랫폼에만 적용할 수 있습니다.
- 일반적으로 GA(일반 제공)되기 전에 기능 변경 사항을 거치게 됩니다.
- Microsoft에서 완전히 지원됩니다.
- 선택한 지리적 지역 또는 클라우드 환경에서만 사용할 수 있습니다. 예를 들어 이 기능은 정부 클라우드에 존재하지 않을 수 있습니다.
- 미리 보기의 개별 기능에는 더 많은 사용 및 지원 제한이 있을 수 있습니다. 이 경우 이 정보는 일반적으로 기능 설명서에 기록됩니다.
- 미리 보기 버전은 표준 지원 수준으로 제공될 수 있으며 프로덕션 환경에 사용할 수 있습니다. 



## <a name="required-permissions"></a>필수 권한

Azure AD(Azure Active Directory) 역할이 할당된 계정은 미리 보기 Microsoft 365 Defender 수 있습니다.

- 전역 관리자
- 보안 관리자
- 보안 운영자

## <a name="turn-on-preview-features"></a>미리 보기 기능 설정

기능을 일반적으로 사용할 수 있도록 하기 전에 전반적인 환경을 개선하는 데 도움이 되기 위해 피드백을 제공할 수 있는 예정된 기능에 액세스할 수 있습니다.

미리 보기 환경을 설정하여 최초로 예정된 기능을 사용해보세요.

1. 탐색 창에서 **설정** 을 선택합니다.
2. 를 **Microsoft 365 Defender.**
3. **미리 보기 기능** > **미리 보기 기능 설정** 을 선택합니다. 
4. **저장** 을 선택합니다.

**미리 보기 기능 설정** 확인란이 선택되어 있는 경우, 미리 보기 기능을 설정했음을 알 수 있습니다. 

## <a name="preview-features"></a>미리 보기 기능

다음 기능과 향상 기능은 현재 미리 보기에서 사용할 수 있습니다.

- **[위협 태그별](threat-analytics.md#view-reports-per-threat-tags)** 보고서 보기 - 위협 태그를 사용하면 특정 위협 범주에 집중하고 가장 관련성이 높은 보고서를 검토할 수 있습니다.
- **[스트리밍 API](../defender-endpoint/raw-data-export.md)** - Microsoft 365 Defender 헌팅을 통해 사용할 수 있는 모든 이벤트를 이벤트 허브 및/또는 Azure 저장소 계정으로 스트리밍할 수 있습니다.
- **[Microsoft 365 Defender API](api-overview.md)** - 최상위 Microsoft 365 Defender API를 사용하면 공유 인시던트 및 고급 헌팅 테이블을 기반으로 워크플로를 자동화할 수 있습니다. 
- **[고급 헌팅](advanced-hunting-take-action.md)** 작업 수행 - 고급 헌팅에서 발견된 위협을 빠르게 포함하거나 손상된 자산을 [해결합니다.](advanced-hunting-overview.md)
- **[포털 내 스마마 참조](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** - 보안 센터에서 직접 고급 헌팅 스마 테이블에 대한 정보를 얻습니다. 테이블 및 열 설명 외에도 이 참조에는 지원되는 이벤트 유형(값) 및 `ActionType` 예제 쿼리가 포함됩니다.
- **[DeviceFromIP() 기능](advanced-hunting-devicefromip-function.md)** - 지정된 시간 범위에서 특정 IP 주소 또는 주소가 할당된 장치에 대한 정보를 얻습니다.
