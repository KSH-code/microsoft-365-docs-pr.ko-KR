---
title: 인시던트 API 업데이트
description: Microsoft 365 Defender API를 사용하여 인시던트를 업데이트하는 방법 알아보기
keywords: 업데이트, API, 인시던트
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
ms.openlocfilehash: e3f3919d067078ef1fd1e116dc52e8a73c0726d9
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571784"
---
# <a name="update-incident-api"></a>인시던트 API 업데이트

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다. Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.

## <a name="api-description"></a>API 설명

기존 인시던트속성업데이트. 업데이터블 속성은 다음과 ```status``` ```determination``` ```classification``` ```assignedTo``` ```tags``` ```comments``` 같습니다.

### <a name="quotas-resource-allocation-and-other-constraints"></a>할당량, 리소스 할당 및 기타 제약 조건

1. 제한 임계값에 도달하기 전에 분당 최대 50건의 통화 또는 시간당 1,500건의 통화를 수행할 수 있습니다.
2. TruePositive로 설정된 경우에만 속성을 설정할 수 `determination` `classification` 있습니다.

요청이 제한되면 `429` 응답 코드가 반환됩니다. 응답 본문에는 새 통화를 시작할 수 있는 시간을 나타냅니다.

## <a name="permissions"></a>권한

다음 권한 중 하나는 이 API를 호출해야 합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Microsoft 365 수비수 API 액세스권한을](api-access.md)참조하십시오.

권한 유형 | 사용 권한 | 권한 표시 이름
-|-|-
응용 프로그램 | 인시던트.읽기쓰기.모든 것 | 모든 인시던트 읽기 및 쓰기
위임(직장 또는 학교 계정) | 인시던트.읽기 | 인시던트 읽기 및 쓰기

> [!NOTE]
> 사용자 자격 증명을 사용하여 토큰을 획득할 때 사용자는 포털에서 인시던트를 업데이트할 수 있는 권한이 있어야 합니다.

## <a name="http-request"></a>HTTP 요청

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>요청 헤더

이름 | 유형 | 설명
-|-|-
권한 부여 | 문자열 | 베어러 {토큰}. **필수입니다**.
Content-Type | 문자열 | 응용 프로그램 / json. **필수입니다**.

## <a name="request-body"></a>요청 본문

요청 본문에서 업데이트해야 하는 필드에 대한 값을 제공합니다. 요청 본문에 포함되지 않은 기존 속성은 관련 값의 변경으로 인해 다시 계산해야 하지 않는 한 해당 값을 유지합니다. 최상의 성능을 위해 변경되지 않은 기존 값을 생략해야 합니다.

속성 | 유형 | 설명
-|-|-
상태 | 이넘 (주) | 인시던트의 현재 상태를 지정합니다. 가능한 값은 다음과 ```Active``` ```Resolved``` ```Redirected``` 같습니다.
할당To | 문자열 | 사건의 소유자.
분류 | 이넘 (주) | 인시던트 사양입니다. 가능한 값은 다음과 ```Unknown``` ```FalsePositive``` ```TruePositive``` 같습니다.
결심 | 이넘 (주) | 인시던트 의 결정을 지정합니다. 가능한 값은 다음과 같습니다 : ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` . ```Other```
태그 | 문자열 목록 | 인시던트 태그 목록입니다.
주석 | 문자열 | 인시던트에 추가할 주석입니다.

## <a name="response"></a>응답

성공하면 이 메서드가 `200 OK` 반환됩니다. 응답 본문에는 업데이트된 속성이 있는 인시던트 엔터티가 포함됩니다. 지정된 ID가 있는 인시던트를 찾지 못하면 메서드가 `404 Not Found` 반환됩니다.

## <a name="example"></a>예제

**요청**

다음은 요청의 예입니다.

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

**응답**

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"],
    "comments": [
          {
              "comment": "pen testing",
              "createdBy": "secop2@contoso.com",
              "createdTime": "2021-05-02T09:34:21.5519738Z"
          },
          {
              "comment": "valid incident",
              "createdBy": "secop2@contoso.comt",
              "createdTime": "2021-05-02T09:36:27.6652581Z"
          }
      ]
}
```

## <a name="related-articles"></a>관련 문서

- [Microsoft 365 수비수 API에 액세스](api-access.md)
- [API 제한 및 라이선스에 대해 알아보기](api-terms.md)
- [오류 코드 이해](api-error-codes.md)
- [인시던트 API](api-incident.md)
- [인시던트 열거](api-list-incidents.md)
- [인시던트 개요](incidents-overview.md)
