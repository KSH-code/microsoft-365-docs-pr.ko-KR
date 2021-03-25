---
title: 도메인 통계 얻기 API
description: 도메인 통계 다운로드 API를 사용하여 끝점용 Microsoft Defender에서 지정한 도메인에 대한 통계를 검색하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, get, 도메인, 도메인 관련 장치
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: eef06657d7f691a89e5985640431c2cc706557b4
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167137"
---
# <a name="get-domain-statistics-api"></a>도메인 통계 얻기 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 설명
지정한 도메인에 대한 통계를 검색합니다.


## <a name="limitations"></a>제한 사항
1. 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.


## <a name="permissions"></a>사용 권한
이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)

사용 권한 유형 |   사용 권한  |   사용 권한 표시 이름
:---|:---|:---
응용 프로그램 |   URL. Read.All |  'URL 읽기'
위임(직장 또는 학교 계정) | URL. Read.All | 'URL 읽기'

>[!Note]
> 사용자 자격 증명을 사용하여 토큰을 얻을 때:
>- 사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).

## <a name="http-request"></a>HTTP 요청
```
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a>요청 헤더

머리글 | 값 
:---|:---
권한 부여 | Bearer {token}. **필수입니다**.

## <a name="request-uri-parameters"></a>요청 URI 매개 변수

이름 | 유형 | 설명
:---|:---|:---
lookBackHours | Int32 | 통계를 얻기 위해 다시 검색하는 시간을 정의합니다. 기본값은 30일입니다. 선택 사항입니다.

## <a name="request-body"></a>요청 본문
비어 있음

## <a name="response"></a>응답
성공 및 도메인이 있는 경우 - 응답 본문에 statistics 개체가 있는 200 OK. 도메인이 없는 경우 - 404 찾을 수 없습니다.


## <a name="example"></a>예제

**요청**

다음은 요청의 예입니다.

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

**응답**

다음은 응답의 예입니다.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "orgPrevalence": "4070",
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```
