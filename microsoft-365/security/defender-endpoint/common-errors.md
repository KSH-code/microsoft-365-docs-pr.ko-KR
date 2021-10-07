---
title: 끝점 API 오류에 대한 일반적인 Microsoft Defender
description: 설명이 있는 일반적인 끝점 API 오류에 대한 Microsoft Defender 목록입니다.
keywords: API, 끝점 API용 Microsoft Defender, 오류, 문제 해결
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 065a82521e8dad8ea4594ba6b3364471b99927ae
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60178494"
---
# <a name="common-rest-api-error-codes"></a>일반적인 REST API 오류 코드

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* 다음 표에 나열된 오류 코드는 끝점 API용 Microsoft Defender에 대한 작업으로 반환될 수 있습니다.
* 오류 코드 외에도 모든 오류 응답에는 문제 해결에 도움이 될 수 있는 오류 메시지가 포함되어 있습니다.
* 메시지는 변경할 수 있는 무료 텍스트입니다.
* 페이지 아래쪽에서 응답 예제를 찾을 수 있습니다.

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

오류 코드|HTTP 상태 코드|메시지
---|---|---
BadRequest|BadRequest (400)|일반 잘못된 요청 오류 메시지입니다.
ODataError|BadRequest (400)|OData URI 쿼리가 잘못되었습니다(특정 오류가 지정되었습니다).
InvalidInput|BadRequest (400)|입력 {잘못된 입력}이(가) 잘못되었습니다.
InvalidRequestBody|BadRequest (400)|요청 본문이 잘못되었습니다.
InvalidHashValue|BadRequest (400)|해시 값 {the invalid hash}가 잘못되었습니다.
InvalidDomainName|BadRequest (400)|도메인 이름 {잘못된 도메인}이(가) 잘못되었습니다.
InvalidIpAddress|BadRequest (400)|IP 주소 {잘못된 IP}가 잘못되었습니다.
InvalidUrl|BadRequest (400)|URL {잘못된 URL}이(가) 잘못되었습니다.
MaximumBatchSizeExceeded|BadRequest (400)|최대 일괄 처리 크기가 초과됩니다. Received: {batch size received}, allowed: {batch size allowed}.
MissingRequiredParameter|BadRequest (400)|매개 변수 {누락된 매개 변수}가 없습니다.
OsPlatformNotSupported|BadRequest (400)|OS 플랫폼 {클라이언트 OS 플랫폼}은 이 작업에서 지원되지 않습니다.
ClientVersionNotSupported|BadRequest (400)|{요청된 작업}은 클라이언트 버전 {지원되는 클라이언트 버전} 이상에서 지원됩니다.
권한이 없는 경우|권한이 없는 경우(401)|권한이 부여되지 않았습니다(유효하지 않은 또는 만료된 권한 부여 헤더).
금지|금지(403)|금지됩니다(유효한 토큰이지만 작업의 사용 권한이 부족).
DisabledFeature|금지(403)|테넌트 기능을 사용할 수 없습니다.
DisallowedOperation|금지(403)|{the disallowed operation and the reason}.
NotFound|찾을 수 없습니다(404)|일반 찾을 수 없는 오류 메시지입니다.
ResourceNotFound|찾을 수 없습니다(404)|리소스 {요청된 자원}을(를) 찾을 수 없습니다.
InternalServerError|내부 서버 오류(500)|(오류 메시지 없음, 작업을 다시 시도)
TooManyRequests|요청 수가 너무 많음(429)|응답은 요청 수 또는 CPU에 의해 할당량 제한에 도달하는 경우를 나타내게 됩니다.

## <a name="body-parameters-are-case-sensitive"></a>본문 매개 변수는 대소문자 구분

제출된 본문 매개 변수는 현재 대소문자 구분됩니다.

**InvalidRequestBody** 또는 **MissingRequiredParameter** 오류가 발생하는 경우 매개 변수의 대/소문자 오류가 발생할 수 있습니다.

API 설명서 페이지를 검토하고 제출된 매개 변수가 관련 예제와 일치하는지 확인하십시오.

## <a name="correlation-request-id"></a>상관 관계 요청 ID

각 오류 응답에는 추적을 위한 고유 ID 매개 변수가 포함되어 있습니다.

이 매개 변수의 속성 이름은 "target"입니다.

오류에 대해 문의할 때 이 ID를 첨부하면 문제의 근본 원인을 찾는 데 도움이 됩니다.

## <a name="examples"></a>예

```json
{
    "error": {
        "code": "ResourceNotFound",
        "message": "Machine 123123123 was not found",
        "target": "43f4cb08-8fac-4b65-9db1-745c2ae65f3a"
    }
}
```

```json
{
    "error": {
        "code": "InvalidRequestBody",
        "message": "Request body is incorrect",
        "target": "1fa66c0f-18bd-4133-b378-36d76f3a2ba0"
    }
}
```
