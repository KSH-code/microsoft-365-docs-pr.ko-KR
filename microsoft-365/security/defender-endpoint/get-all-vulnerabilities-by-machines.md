---
title: 컴퓨터 및 소프트웨어로 모든 취약성 확인
description: Machine and Software로 조직에 영향을 주는 모든 취약점 목록을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, 취약성 정보, Endpoint tvm api용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: b7a339c3083c69b926f46134061a263bdb5bfeba
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221527"
---
# <a name="list-vulnerabilities-by-machine-and-software"></a>컴퓨터 및 소프트웨어별 취약성 목록

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

컴퓨터 및 소프트웨어당 조직에 영향을 주는 모든 취약점 [목록을](machine.md) [검색합니다.](software.md)

- 취약성에 수정 KB가 있는 경우 응답에 표시됩니다.
- [OData V4 쿼리를 지원합니다.](https://www.odata.org/documentation/)
- OData의 쿼리는 `$filter` , , , , , , , `id` 및 `cveId` `machineId` `fixingKbId` `productName` `productVersion` `severity` `productVendor` 속성에서 지원됩니다.
<br>```$stop``` 최대값 10,000
<br>```$skip```

> [!TIP]
> 이는 통합된 에 [Power BI 좋은 API입니다.](api-power-bi.md)

## <a name="permissions"></a>권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.

사용 권한 유형|사용 권한|사용 권한 표시 이름
:---|:---|:---
응용 프로그램|Vulnerability.Read.All|'위협 및 취약성 관리 취약성 정보 읽기'
위임(직장 또는 학교 계정)|Vulnerability.Read|'위협 및 취약성 관리 취약성 정보 읽기'

## <a name="http-request"></a>HTTP 요청

```http
GET /api/vulnerabilities/machinesVulnerabilities
```

## <a name="request-headers"></a>요청 헤더

이름|유형|설명
:---|:---|:---
권한 부여|String|Bearer {token}. **필수입니다**.

## <a name="request-body"></a>요청 본문

비어 있음

## <a name="response"></a>응답

성공하면 이 메서드는 본문의 취약점 목록과 함께 200 OK를 반환합니다.

## <a name="example"></a>예제

### <a name="request-example"></a>요청 예제

다음은 요청의 예입니다.

```http
GET https://api.securitycenter.microsoft.com/api/vulnerabilities/machinesVulnerabilities
```

### <a name="response-example"></a>응답 예제

다음은 응답의 예입니다.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicAssetVulnerabilityDto)",
    "value": [
        {
            "id": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21-_-CVE-2020-6494-_-microsoft-_-edge_chromium-based-_-81.0.416.77-_-",
            "cveId": "CVE-2020-6494",
            "machineId": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21",
            "fixingKbId": null,
            "productName": "edge_chromium-based",
            "productVendor": "microsoft",
            "productVersion": "81.0.416.77",
            "severity": "Low"
        },
        {
            "id": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283-_-CVE-2016-3348-_-microsoft-_-windows_server_2012_r2-_-6.3.9600.19728-_-3185911",
            "cveId": "CVE-2016-3348",
            "machineId": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283",
            "fixingKbId": "3185911",
            "productName": "windows_server_2012_r2",
            "productVendor": "microsoft",
            "productVersion": "6.3.9600.19728",
            "severity": "Low"
        },
        ...
    ]

}
```

## <a name="see-also"></a>참고 항목

- [위험 기반 위협 및 취약성 관리](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [조직의 취약성](/microsoft-365/security/defender-endpoint/tvm-weaknesses)
