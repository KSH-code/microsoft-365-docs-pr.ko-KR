---
title: Microsoft Threat Protection API의 문제 리소스 종류
description: Microsoft Threat Protection에서 문제 리소스 유형의 방법 및 속성에 대해 자세히 알아보기
keywords: 인시던트, 사건, api
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
ms.openlocfilehash: 310e3105c973223ea79373d770eb10f7753b917e
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650456"
---
# <a name="incident-resource-type"></a>문제 리소스 종류

**적용 대상:**
- Microsoft 위협 방지

>[!IMPORTANT] 
>일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="methods"></a>메서드

메서드 |반환 형식 |설명
:---|:---|:---
[인시던트 목록](api-list-incidents.md) | [인시던트](api-incident.md) 목록 | 인시던트 목록을 가져옵니다.
[인시던트 업데이트](api-update-incidents.md) | [문제점](api-incident.md) | 특정 인시던트를 업데이트 합니다.


## <a name="properties"></a>속성

속성 |    유형    |    설명
:---|:---|:---
incidentId | long | 인시던트 고유 ID입니다.
redirectIncidentId | nullable long | 현재 인시던트가 병합 된 인시던트 ID입니다.
incidentName | 문자열 | 인시던트 이름입니다.
createdTime | DateTimeOffset | 인시던트가 만들어진 날짜 및 시간 (UTC)입니다.
lastUpdateTime | DateTimeOffset | 인시던트가 마지막으로 업데이트 된 날짜 및 시간 (UTC)입니다.
assignedTo | 문자열 | 인시던트의 소유자입니다.
이상인 | 열거할 | 인시던트의 심각도입니다. 가능한 값은 ```UnSpecified``` , ```Informational``` , ```Low``` ```Medium``` 및 ```High``` 입니다.
상태별 | 열거할 | 인시던트의 현재 상태를 지정 합니다. 가능한 값은 ```Active``` ```Resolved``` 및 ```Redirected``` 입니다.
유형을 | 열거할 | 인시던트 사양입니다. 가능한 값은 ```Unknown``` , ```FalsePositive``` 및 ```TruePositive``` 입니다.
가져옴을 | 열거할 | 문제에 대 한 결정을 지정 합니다. 가능한 값은 ```NotAvailable``` ,, ```Apt``` ```Malware``` , ```SecurityPersonnel``` , ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` 입니다.
사이 | 문자열 목록 | 인시던트 태그의 목록입니다.
경고가 | 알림 목록 | 관련 경고 목록 [List 인시던트](api-list-incidents.md) API 설명서의 예를 참조 하세요.