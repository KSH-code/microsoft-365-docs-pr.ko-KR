---
title: Microsoft Threat Protection의 미리 보기 기능
description: Microsoft 365 보안의 새로운 기능에 대해 알아보기
keywords: 미리 보기, 새로 만들기, m365 보안, 보안, 365, 기능
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
ms.openlocfilehash: 8a3e4b8979a346266336e2729d18465d391c28f9
ms.sourcegitcommit: efd4dd29af0ea2b71b674534de3b2dcbfd7482db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44689269"
---
# <a name="microsoft-threat-protection-preview-features"></a>Microsoft Threat Protection 미리 보기 기능

**적용 대상:**
- Microsoft 위협 방지


Microsoft Threat Protection 서비스는 새로운 기능 향상 및 기능을 포함 하도록 지속적으로 업데이트 됩니다.

미리 보기 환경을 설정 하 여 Microsoft Threat Protection preview 릴리스의 새로운 기능과 첫 번째 기능에 대해 설명 합니다.

일반 공급되는 새 기능에 대한 자세한 내용은 [Microsoft 위협 방지의 새 기능](whats-new.md)을 참조하세요.

## <a name="turn-on-preview-features"></a>미리 보기 기능 설정
일반적으로 기능을 사용할 수 있으려면 전체 환경을 개선 하는 데 도움이 되는 피드백을 제공할 수 있는 예정 된 기능에 대 한 액세스 권한이 있어야 합니다.

미리 보기 환경 설정을 첫 번째로 설정 하 여 예정 된 기능을 시도해 봅니다.

1. 탐색 창에서 **설정을**선택 합니다.

2. **Microsoft Threat Protection**을 선택 합니다.


3. **미리 보기 기능**을 선택 하 여  >  **미리 보기 기능을 켭니다**. 

3. **저장**을 선택합니다.

**미리 보기 기능 켜기** 확인란이 선택 되어 있으면 미리 보기 기능이 설정 되어 있는 것을 알 수 있습니다. 

## <a name="preview-features"></a>미리 보기 기능
현재 미리 보기에서는 다음과 같은 기능을 사용할 수 있습니다.

- **[Id 및 앱 테이블](advanced-hunting-schema-tables.md)** -고급 구하기 스키마에서 [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)및 [appfileevents](advanced-hunting-appfileevents-table.md) 테이블을 사용 하 여 인증 이벤트, Active Directory 쿼리 및 앱 관련 작업에 대 한 가시성을 가져옵니다.

- **[헌트](advanced-hunting-go-hunt.md)** -쿼리 기반 [고급 구하기](advanced-hunting-overview.md) 기능을 사용 하 여 특정 이벤트, 사용자, 장치 또는 기타 엔터티 유형을 검사 하는 인시던트 조사에서 빠르게 피벗 합니다.

- **[EmailPostDeliveryEvents 테이블](advanced-hunting-emailpostdeliveryevents-table.md)** -이 표를 사용 하 여 받는 사람 사서함으로 배달 된 후 전자 메일에 대해 수행 되는 작업을 확인 하는 [고급 구하기](advanced-hunting-overview.md) 쿼리를 만들 수 있습니다.

- **[Fileprofile () 함수](advanced-hunting-fileprofile-function.md)** - [고급 구하기](advanced-hunting-overview.md) 쿼리에서 포괄적인 파일 정보를 통합 하는 데 사용 됩니다.
