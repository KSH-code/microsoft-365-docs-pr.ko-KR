---
title: 문제 API 업데이트
description: Microsoft Threat Protection API를 사용 하 여 인시던트를 업데이트 하는 방법에 대해 알아봅니다.
keywords: 업데이트, api, 인시던트
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
ms.openlocfilehash: e790f4f415575323cfdd5fc15db41baa8b59c7f6
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650436"
---
# <a name="update-incidents-api"></a>문제 API 업데이트

**적용 대상:**
- Microsoft 위협 방지

>[!IMPORTANT] 
>일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다. Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="api-description"></a>API 설명
기존 인시던트의 속성을 업데이트 합니다.
<br>업데이트할 수 있는 속성은 ```status``` ,, ```determination``` ```classification``` ```assignedTo``` 및 ```tags``` 입니다.


## <a name="limitations"></a>제한 사항
1. 이 API의 속도 제한은 분당 50 통화이 고 시간당 1500 통화입니다.
2. ```determination```분류가 TruePositive로 설정 된 경우에만 설정할 수 있습니다.


## <a name="permissions"></a>사용 권한
이 API를 호출 하려면 다음 사용 권한 중 하나가 필요 합니다. 사용 권한을 선택 하는 방법을 비롯 하 여 자세한 내용은 [Microsoft Threat Protection Api 액세스](api-access.md)를 참조 하십시오.

사용 권한 유형 |   사용 권한  |   사용 권한 표시 이름
:---|:---|:---
응용 프로그램 |   인시던트의 모든 |    ' 모든 인시던트 읽기 및 쓰기 '
위임 됨 (회사 또는 학교 계정) | 인시던트-ReadWrite | ' 인시던트 읽기 및 쓰기 '

>[!NOTE]
> 사용자 자격 증명을 사용 하 여 토큰을 가져올 때:
>- 사용자에 게 포털의 인시던트를 업데이트할 수 있는 권한이 있어야 합니다.


## <a name="http-request"></a>HTTP 요청

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>요청 헤더

이름 | 유형 | 설명
:---|:---|:---
권한 부여 | 문자열 | 전달자 {토큰}. **필수**입니다.
Content-Type | 문자열 | application/json **필수**입니다.


## <a name="request-body"></a>요청 본문
요청 본문에서 업데이트 해야 하는 관련 필드의 값을 입력 합니다.
<br>요청 본문에 포함 되지 않은 기존 속성은 이전 값을 유지 하거나 다른 속성 값의 변경 내용에 따라 다시 계산 됩니다. 
<br>최적의 성능을 위해 변경 되지 않은 기존 값은 포함할 수 없습니다.

속성 | 유형 | 설명
:---|:---|:---
상태별 | 열거할 | 알림의 현재 상태를 지정 합니다. 가능한 값은 ```Active``` ```Resolved``` 및 ```Redirected``` 입니다.
assignedTo | 문자열 | 인시던트의 소유자입니다.
유형을 | 열거할 | 경고의 사양입니다. 가능한 값은 ```Unknown``` , ```FalsePositive``` 및 ```TruePositive``` 입니다.
가져옴을 | 열거할 | 경고에 대 한 결정을 지정 합니다. 가능한 값은 ```NotAvailable``` ,, ```Apt``` ```Malware``` , ```SecurityPersonnel``` , ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` 입니다.
사이 | 문자열 목록 | 인시던트 태그의 목록입니다.



## <a name="response"></a>응답
성공한 경우이 메서드는 200 OK를 반환 하 고 업데이트 된 속성을 사용 하 여 응답 본문에 인시던트 엔티티를 구합니다. 지정 된 id를 가진 인시던트를 찾을 수 없는 경우-404를 찾을 수 없습니다.


## <a name="example"></a>예제

**요청이**

다음은 요청의 예입니다.

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a>관련 항목
- [인시던트 Api](api-incident.md)
- [인시던트 목록](api-list-incidents.md)