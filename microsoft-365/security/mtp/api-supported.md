---
title: 지원 되는 Microsoft Threat Protection Api
description: 지원 되는 Microsoft Threat Protection Api
keywords: MTP, Api, api
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
ms.openlocfilehash: 49fa182a6142748ca7769411fe74389f365ba75f
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650438"
---
# <a name="supported-microsoft-threat-protection-apis"></a>지원 되는 Microsoft Threat Protection Api 
**적용 대상:**
- Microsoft 위협 방지

>[!IMPORTANT] 
>일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다. Microsoft makes no warranties, express or implied, with respect to the information provided here.


### <a name="end-point-uris"></a>끝점 Uri:

- 서비스 기본 URI는 다음과 같습니다. https://api.security.microsoft.com <br>

>[!NOTE]
>성능 향상을 위해 서버를 지리적 위치에 더 가깝게 사용할 수 있습니다.
> - api-us.security.microsoft.com
> - api-eu.security.microsoft.com
> - api-uk.security.microsoft.com

 - 토큰 취득 리소스는 다음과 같아야 합니다. https://api.security.microsoft.com

 - Path 아래의 모든 Api는 ```/api``` OData api입니다. 예:. ```https://api.security.microsoft.com/api/incidents```

## <a name="list-of-available-apis"></a>사용 가능한 Api 목록:

항목 | 설명
:---|:---
[고급 구하기 API](api-advanced-hunting.md) | API에서 고급 구하기 쿼리를 실행 합니다.
[인시던트 Api](api-incident.md) | 인시던트 목록, 업데이트 인시던트 등의 관련 API 호출을 실행 합니다.
