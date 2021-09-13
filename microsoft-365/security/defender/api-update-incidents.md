---
title: 인시던트 API 업데이트
description: API를 사용하여 인시던트 업데이트 Microsoft 365 Defender 정보
keywords: update, api, incident
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
ms.openlocfilehash: c30d9918e4e61973dc03e6a2e621ffda5e7e01e5
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59185691"
---
# <a name="update-incidents-api"></a>인시던트 업데이트 API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> 일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다. Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.

## <a name="api-description"></a>API 설명

기존 인시던트의 속성을 업데이트합니다. 업데이트할 수 있는 속성은 `status` , , , , 및 `determination` `classification` `assignedTo` `tags` `comments` 입니다.

### <a name="quotas-resource-allocation-and-other-constraints"></a>할당량, 리소스 할당 및 기타 제약 조건

1. 제한 임계값에 도달하기 전에 분당 최대 50통의 통화를 만들거나 시간당 1500통을 설정할 수 있습니다.
2. `determination` `classification` 속성을 TruePositive로 설정한 경우만 설정할 수 있습니다.

요청이 스로틀된 경우 응답 `429` 코드가 반환됩니다. 응답 본문은 새 통화를 시작할 수 있는 시간을 나타냅니다.

## <a name="permissions"></a>권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 Access the Microsoft 365 Defender [참조합니다.](api-access.md)

사용 권한 유형|사용 권한|사용 권한 표시 이름
---|---|---
응용 프로그램|Incident.ReadWrite.All|모든 인시던트 읽기 및 쓰기
위임(직장 또는 학교 계정)|Incident.ReadWrite|인시던트 읽기 및 쓰기

> [!NOTE]
> 사용자 자격 증명을 사용하여 토큰을 얻을 때 사용자는 포털에서 인시던트 업데이트 권한이 필요합니다.

## <a name="http-request"></a>HTTP 요청

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>요청 헤더

이름|유형|설명
---|---|---
권한 부여|문자열|Bearer {token}. **필수입니다**.
Content-Type|String|application/json. **필수입니다**.

## <a name="request-body"></a>요청 본문

요청 본문에서 업데이트해야 하는 필드의 값을 제공합니다. 관련 값의 변경으로 인해 다시 계산하지 않는 한 요청 본문에 포함되지 않은 기존 속성은 해당 값을 유지 관리합니다. 최상의 성능을 위해 변경되지 않은 기존 값을 생략해야 합니다.

속성|유형|설명
---|---|---
status|Enum|인시던트의 현재 상태를 지정합니다. 가능한 값은 `Active` , `Resolved` , 및 `Redirected` 입니다.
assignedTo|문자열|인시던트의 소유자입니다.
classification|Enum|인시던트 사양입니다. 가능한 값은 `Unknown` , `FalsePositive` , `TruePositive` 입니다.
determination|Enum|인시던트 결정 가능한 값은 `NotAvailable` , `Apt` `Malware` , , , , `SecurityPersonnel` `SecurityTesting` , `UnwantedSoftware` `Other` 입니다.
tags|문자열 목록|인시던트 태그 목록입니다.
comment|문자열|인시던트에 추가할 설명입니다.

## <a name="response"></a>응답

성공하면 이 메서드는 `200 OK` 를 반환합니다. 응답 본문에는 업데이트된 속성이 있는 인시던트 엔터티가 포함되어 있습니다. 지정한 ID가 있는 인시던트가 발견되지 않으면 메서드는 를 `404 Not Found` 반환합니다.

## <a name="example"></a>예제

### <a name="request-example"></a>요청 예제

다음은 요청의 예입니다.

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

### <a name="response-example"></a>응답 예제

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

- [MICROSOFT 365 DEFENDER API에 액세스](api-access.md)
- [API 제한 및 라이선싱에 대해 자세히 알아보기](api-terms.md)
- [오류 코드 이해](api-error-codes.md)
- [인시던트 API](api-incident.md)
- [인시던트 열거](api-list-incidents.md)
- [인시던트 개요](incidents-overview.md)
