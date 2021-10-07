---
title: 인시던트 API 사용
description: 인시던트 발생 API를 사용하여 인시던트에서 단일 인시던트가 발생하게 하는 방법을 Microsoft 365 Defender.
keywords: api, 그래프 api, 지원되는 api, 다운로드, 파일, 해시
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
ms.openlocfilehash: 8861dc3752d2c4cc798bc83475f6a51f8245191a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159057"
---
# <a name="get-incident-information-api"></a>인시던트 정보 얻기 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명

ID로 특정 인시던트 검색

## <a name="limitations"></a>제한 사항

1. 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.

## <a name="permissions"></a>권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다.

사용 권한 유형|사용 권한|사용 권한 표시 이름
---|---|---
응용 프로그램|Incident.Read.All|'모든 인시던트 읽기'
응용 프로그램|Incident.ReadWrite.All|'모든 인시던트 읽기 및 쓰기'
위임(직장 또는 학교 계정)|Incident.Read|'인시던트 읽기'
위임(직장 또는 학교 계정)|Incident.ReadWrite|'인시던트 읽기 및 쓰기'

> [!NOTE]
>
> 사용자 자격 증명을 사용하여 토큰을 얻을 때:
>
> - 사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다.
> - 응답에는 사용자가 노출된 인시던트만 포함됩니다.

## <a name="http-request"></a>HTTP 요청

```console
GET .../api/incidents/{id}
```

## <a name="request-headers"></a>요청 헤더

이름|유형|설명
---|---|---
권한 부여|String|Bearer {token}. **필수입니다**.

## <a name="request-body"></a>요청 본문

비어 있음

## <a name="response"></a>응답

성공하면 이 메서드는 200 OK를 반환하고 응답 본문의 인시던트 엔터티를 반환합니다.
지정한 ID가 있는 인시던트가 발견되지 않은 경우 - 404 찾을 수 없습니다.

## <a name="example"></a>예제

### <a name="request"></a>요청

다음은 요청의 예입니다.

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
