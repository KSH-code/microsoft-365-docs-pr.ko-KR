---
title: 지원되는 Microsoft 365 Defender API
description: 지원되는 Microsoft 365 Defender API
keywords: Microsoft 365 Defender, API, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: c77e825fa680a038ba89a9054e04ce939dcb7941
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60203918"
---
# <a name="supported-microsoft-365-defender-apis"></a>지원되는 Microsoft 365 Defender API 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

> [!IMPORTANT]
> 일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다. Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.

## <a name="list-of-available-apis"></a>사용 가능한 API 목록

문서 | 설명
-|-
[고급 헌팅 API](api-advanced-hunting.md) | 고급 헌팅 쿼리를 실행합니다.
[인시던트 API](api-incident.md) | 다른 실용적인 작업과 함께 인시던트 나열 및 업데이트
[스트리밍 API](streaming-api.md) | 단일 데이터 스트림에서 발생하는 실시간 이벤트 및 경고를 제공합니다.

### <a name="endpoint-uris"></a>끝점 URIS

두 기본 API의 기본 URI는 https://api.security.microsoft.com 입니다. 더 나은 성능을 위해 지리적 위치와 더 가까운 서버를 사용 합니다.

- 미국: api-us.security.microsoft.com
- 유럽: api-eu.security.microsoft.com
- 영국: api-uk.security.microsoft.com

토큰은 에 액세스하여 획득할 수 https://api.security.microsoft.com 있습니다.

경로의 모든 `/api` API는 [OData](/odata/overview) 프로토콜(예: )을 https://api.security.microsoft.com/api/incidents 사용합니다.

## <a name="related-articles"></a>관련 문서

- [Microsoft 365 Defender API 개요](api-overview.md)
- [MICROSOFT 365 DEFENDER API에 액세스](api-access.md)
- [스트리밍 API](../defender-endpoint/raw-data-export.md)
- [API 제한 및 라이선싱에 대해 자세히 알아보기](api-terms.md)
- [오류 코드 이해](api-error-codes.md)
