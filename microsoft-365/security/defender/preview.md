---
title: Microsoft 365 Defender의 미리 보기 기능
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
ms.openlocfilehash: 291ee6d2f72579a6daf731c121265164b2aaa547
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074780"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Defender 미리 보기 기능

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> 미리 보기 버전은 서비스 수준 계약 없이 제공하며 프로덕션 워크로드에는 권장되지 않습니다. 일부 기능은 지원되지 않을 수도, 기능이 제한될 수도 있습니다.

**적용 대상:**
- Microsoft 365 Defender

Microsoft 365 Defender 서비스는 새로운 기능 향상 및 기능을 포함하기 위해 지속적으로 업데이트되고 있습니다.

Microsoft 365 Defender 미리 보기 릴리스의 새로운 기능에 대해 알아보고 미리 보기 환경을 켜서 예정된 기능을 처음 사용해 볼 수 있습니다.

일반적으로 사용할 수 있는 새로운 기능에 대한 자세한 내용은 [Microsoft 365 Defender의](whats-new.md)새로운 기능을 참조하세요.

## <a name="required-permissions"></a>필요한 사용 권한

다음 Azure AD(Azure Active Directory) 역할이 할당된 계정은 Microsoft 365 Defender 미리 보기 기능을 켜는 데 사용할 수 있습니다.

- 전역 관리자
- 보안 관리자
- 보안 운영자

## <a name="turn-on-preview-features"></a>미리 보기 기능 설정

기능을 일반적으로 사용할 수 있도록 하기 전에 전반적인 환경을 개선하는 데 도움이 되기 위해 피드백을 제공할 수 있는 예정된 기능에 액세스할 수 있습니다.

미리 보기 환경을 설정하여 최초로 예정된 기능을 사용해보세요.

1. 탐색 창에서 **설정** 을 선택합니다.
2. **Microsoft 365 Defender 를 선택합니다.**
3. **미리 보기 기능** > **미리 보기 기능 설정** 을 선택합니다. 
4. **저장** 을 선택합니다.

**미리 보기 기능 설정** 확인란이 선택되어 있는 경우, 미리 보기 기능을 설정했음을 알 수 있습니다. 

## <a name="preview-features"></a>미리 보기 기능

다음 기능과 향상 기능은 현재 미리 보기에서 사용할 수 있습니다.

### <a name="improved-microsoft-365-security-center"></a>개선된 Microsoft 365 보안 센터
개선된 [Microsoft 365 보안 센터](https://security.microsoft.com)를 공개 미리 보기에서 사용할 수 있습니다. 이 새로운 환경은 엔드포인트용 Defender, Office 365용 Defender, Microsoft 365 Defender 등을 Microsoft 365 보안 센터에 제공합니다. 보안 제어를 관리하는 새로운 홈입니다. [새로운 기능에 대해 알아보세요](./overview-security-center.md).

- **[Microsoft 365 Defender 위협 분석 보고서](threat-analytics.md)** - 위협 분석을 통해 활성 공격에 대응하고 영향을 최소화할 수 있습니다. 또한 Microsoft 365 Defender 솔루션에 의해 차단되는 공격 시도에 대해 알아보고 추가 노출 및 탄력성 증가의 위험을 완화하는 예방 조치를 취할 수 있습니다. 통합 보안 환경의 일부로, 끝점용 Microsoft Defender 및 Office E5용 Microsoft Defender 라이선스 소유자에게 위협 분석을 사용할 수 있습니다.
- **[Microsoft 365 Defender API](api-overview.md)** - 최상위 Microsoft 365 Defender API를 사용하면 공유 인시던트 및 고급 헌팅 테이블을 기반으로 워크플로를 자동화할 수 있습니다. 
- **[고급 헌팅 작업](advanced-hunting-take-action.md)** 수행 - 고급 헌팅에서 발견된 위협을 빠르게 포함하거나 손상된 자산을 [해결합니다.](advanced-hunting-overview.md)
- **[포털 내 schema 참조](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**- 보안 센터에서 직접 고급 헌팅 스마 테이블에 대한 정보를 얻습니다. 테이블 및 열 설명 외에도 이 참조에는 지원되는 이벤트 유형(값) 및 `ActionType` 예제 쿼리가 포함됩니다.
- **[DeviceFromIP() 기능](advanced-hunting-devicefromip-function.md)**- 지정된 시간 범위에서 특정 IP 주소 또는 주소가 할당된 장치에 대한 정보를 얻습니다.