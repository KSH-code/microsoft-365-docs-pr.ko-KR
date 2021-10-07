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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 3921f79172bbbcc32b8510809b54bec477e44b85
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192860"
---
# <a name="get-cve-kb-map-api"></a>CVE-KB 지도 API 사용

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

CVE의 지도를 KB 및 CVE 세부 정보로 검색합니다.

## <a name="permissions"></a>권한

사용자에게 읽기 권한이 필요합니다.

## <a name="http-request"></a>HTTP 요청

```http
GET /testwdatppreview/cvekbmap
```

## <a name="request-headers"></a>요청 헤더

헤더|값
:---|:---
권한 부여|Bearer {token}. **필수입니다**.
콘텐츠 형식|application/json

## <a name="request-body"></a>요청 본문

비어 있음

## <a name="response"></a>응답

성공 및 지도가 있는 경우 - 200 OK.

## <a name="example"></a>예제

### <a name="request-example"></a>요청 예제

다음은 요청의 예입니다.

```http
GET https://graph.microsoft.com/testwdatppreview/CveKbMap
```

### <a name="response-example"></a>응답 예제

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
    ...
}
```
