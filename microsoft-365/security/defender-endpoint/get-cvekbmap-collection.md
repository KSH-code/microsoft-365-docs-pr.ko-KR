---
title: CVE-KB 지도 API 사용
description: CVE-KB 지도 다운로드 API를 사용하여 끝점용 Microsoft Defender에서 CVE의 KB 및 CVE 세부 정보 맵을 검색하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, get, cve, kb
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
ms.openlocfilehash: 85c4d82f07354193fb1e997abb98dbdaa02dc8ef
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166890"
---
# <a name="get-cve-kb-map-api"></a>CVE-KB 지도 API 사용

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

CVE의 지도를 KB 및 CVE 세부 정보로 검색합니다.

## <a name="permissions"></a>사용 권한
사용자에게 읽기 권한이 필요합니다.

## <a name="http-request"></a>HTTP 요청
```
GET /testwdatppreview/cvekbmap
```

## <a name="request-headers"></a>요청 헤더

머리글 | 값 
:---|:---
권한 부여 | Bearer {token}. **필수입니다**.
콘텐츠 형식 | application/json

## <a name="request-body"></a>요청 본문
비어 있음

## <a name="response"></a>응답
성공 및 지도가 있는 경우 - 200 OK.

## <a name="example"></a>예시

**요청**

다음은 요청의 예입니다.

```http
GET https://graph.microsoft.com/testwdatppreview/CveKbMap
```

**응답**

다음은 응답의 예입니다.

```json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#CveKbMap",
    "@odata.count": 4168,
    "value": [
        {
            "cveKbId": "CVE-2015-2482-3097617",
            "cveId": "CVE-2015-2482",
            "kbId":"3097617",
            "title": "Cumulative Security Update for Internet Explorer",
            "severity": "Critical"
        },
    …
}

```
