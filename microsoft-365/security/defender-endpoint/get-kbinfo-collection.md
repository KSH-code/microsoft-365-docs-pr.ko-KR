---
title: KB 컬렉션 API 사용
description: Microsoft Defender for Endpoint를 사용하여 기술 자료(KB) 및 KB 세부 정보 컬렉션을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 7becfc4a7246dc32aa244dc96ea423f5d31877f9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167178"
---
# <a name="get-kb-collection-api"></a>KB 컬렉션 API 사용

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

KB 및 KB 세부 정보 컬렉션을 검색합니다.

## <a name="permissions"></a>사용 권한
사용자에게 읽기 권한이 필요합니다.

## <a name="http-request"></a>HTTP 요청
```
GET /testwdatppreview/kbinfo
```

## <a name="request-headers"></a>요청 헤더

머리글 | 값 
:---|:---
권한 부여 | Bearer {token}. **필수입니다**.
콘텐츠 형식 | application/json

## <a name="request-body"></a>요청 본문
비어 있음

## <a name="response"></a>응답
성공적이면 - 200 OK.

## <a name="example"></a>예시

**요청**

다음은 요청의 예입니다.

```http
GET https://graph.microsoft.com/testwdatppreview/KbInfo
```

**응답**

다음은 응답의 예입니다.

```json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#KbInfo",
    "@odata.count": 271,
    "value":[
        {
            "id": "KB3097617 (10240.16549) Amd64",
            "release": "KB3097617 (10240.16549)",
            "publishingDate": "2015-10-16T21:00:00Z",
            "version": "10.0.10240.16549",
            "architecture": "Amd64"
        },
        …
}
```
