---
title: 일반적인 Microsoft Threat Protection REST API 오류 코드
description: 일반적인 Microsoft Threat Protection REST API 오류 코드에 대해 자세히 알아보기
keywords: api, 오류, 코드, 일반 오류, mtp, api 오류 코드
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
ms.openlocfilehash: 81375b919b52ff895e5ec7014feb747b1a0eae65
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201342"
---
# <a name="common-microsoft-threat-protection-rest-api-error-codes"></a>일반적인 Microsoft Threat Protection REST API 오류 코드

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 위협 방지

>[!IMPORTANT] 
>일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다. Microsoft makes no warranties, express or implied, with respect to the information provided here.

다음 표에 나와 있는 오류 코드는 Microsoft Threat Protection Api에서 작업에 의해 반환 될 수 있습니다.

모든 오류 응답에 오류 메시지가 포함 되어 있어 문제를 해결 하는 데 도움이 됩니다.

메시지는 변경할 수 있는 자유로운 텍스트입니다.

페이지 맨 아래에서 응답 예를 확인할 수 있습니다.

오류 코드 |HTTP 상태 코드 |메시지 
:---|:---|:---
BadRequest | BadRequest (400) | 일반적인 잘못 된 요청 오류 메시지입니다.
ODataError | BadRequest (400) | 잘못 된 OData URI 쿼리 (특정 오류가 지정 됨)입니다.
InvalidInput | BadRequest (400) | 입력 {잘못 된 입력}입니다.
InvalidRequestBody | BadRequest (400) | 요청 본문이 잘못 되었습니다.
InvalidHashValue | BadRequest (400) | 해시 값 {잘못 된 해시}가 잘못 되었습니다.
InvalidDomainName | BadRequest (400) | 도메인 이름 {잘못 된 도메인}이 잘못 되었습니다.
InvalidIpAddress | BadRequest (400) | IP 주소 {잘못 된 IP}가 잘못 되었습니다.
InvalidUrl | BadRequest (400) | URL {잘못 된 URL}이 잘못 되었습니다.
MaximumBatchSizeExceeded | BadRequest (400) | 최대 일괄 처리 크기를 초과 했습니다. Received: {batch size received}, 허용: {일괄 처리 크기 허용}.
MissingRequiredParameter | BadRequest (400) | 매개 변수 {누락 된 매개 변수}가 누락 되었습니다.
OsPlatformNotSupported | BadRequest (400) | OS 플랫폼 {클라이언트 OS 플랫폼}은이 작업에 지원 되지 않습니다.
ClientVersionNotSupported | BadRequest (400) | {요청 된 작업}은 클라이언트 버전 {지원 되는 클라이언트 버전} 이상에서 지원 됩니다.
권한 | 인증 되지 않음 (401) | 인증 되지 않음 (대개 잘못 되었거나 만료 된 인증 헤더)
권한 | 금지 (403) | 사용할 수 없음 (유효한 토큰 이지만 해당 작업에 대 한 권한이 부족 함)
DisabledFeature | 금지 (403) | 테 넌 트 기능을 사용할 수 없습니다.
DisallowedOperation | 금지 (403) | {허용 되지 않는 작업 및 이유}.
NotFound | 찾을 수 없음 (404) | General을 찾을 수 없음 오류 메시지입니다.
ResourceNotFound | 찾을 수 없음 (404) | 자원 {요청한 자원}을 찾을 수 없습니다.
InternalServerError | 내부 서버 오류 (500) | (오류 메시지 없음, 작업을 다시 시도 하거나, 확인 되지 않으면 문의해 주세요.)

## <a name="body-parameters-are-case-sensitive"></a>본문 매개 변수는 대/소문자를 구분 합니다.

전송 된 본문 매개 변수는 현재 대/소문자를 구분 합니다.
<br>**Invalidrequestbody** 또는 **MissingRequiredParameter** 오류가 발생 하는 경우 잘못 된 매개 변수 대문자 또는 소문자로 인해 발생 한 것일 수 있습니다.
<br>API 설명서 페이지를 검토 하 여 전송 된 매개 변수가 관련 예제와 일치 하는지 확인 하는 것이 좋습니다.

## <a name="correlation-request-id"></a>상관 관계 요청 ID

각 오류 응답에는 추적을 위한 고유한 ID 매개 변수가 포함 되어 있습니다.
<br>이 매개 변수의 속성 이름은 "target"입니다.
<br>이 ID를 연결 하 여 오류에 대 한 정보를 문의할 때 문제의 근본적인 원인을 찾을 수 있습니다.

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

