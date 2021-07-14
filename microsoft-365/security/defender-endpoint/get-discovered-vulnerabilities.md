---
title: 발견된 취약성 가져오기
description: 특정 장치 ID와 관련된 검색된 취약성 컬렉션을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, 다운로드, 목록, 파일, 정보, 발견된 취약성, 위협 & 취약성 관리 api, 끝점 tvm api용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: cd3b1343711a5bed9ad606a6b8dc754f223ed279
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430783"
---
# <a name="get-discovered-vulnerabilities"></a>발견된 취약성 가져오기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명
특정 장치 ID와 관련된 검색된 취약성 컬렉션을 검색합니다.

## <a name="limitations"></a>제한 사항
1. 이 API의 속도 제한은 분당 50통, 시간당 1500통입니다.

## <a name="permissions"></a>사용 권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)

사용 권한 유형 | 사용 권한 | 사용 권한 표시 이름
:---|:---|:---
응용 프로그램 |Vulnerability.Read.All | '위협 및 취약성 관리 취약성 정보 읽기'
위임(직장 또는 학교 계정) | Vulnerability.Read | '위협 및 취약성 관리 취약성 정보 읽기'

## <a name="http-request"></a>HTTP 요청

```
GET /api/machines/{machineId}/vulnerabilities
```

## <a name="request-headers"></a>요청 헤더

이름 | 유형 | 설명
:---|:---|:---
권한 부여 | 문자열 | Bearer {token}. **필수입니다**.

## <a name="request-body"></a>요청 본문

비어 있음

## <a name="response"></a>응답

성공하면 이 메서드는 본문에서 발견된 취약성 정보를 사용하여 200 OK를 반환합니다.

## <a name="example"></a>예제

### <a name="request"></a>요청

다음은 요청의 예입니다.

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/vulnerabilities
```

### <a name="response"></a>응답

다음은 응답의 예입니다.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-1348",
            "name": "CVE-2019-1348",
            "description": "Git could allow a remote attacker to bypass security restrictions, caused by a flaw in the --export-marks option of git fast-import. By persuading a victim to import specially-crafted content, an attacker could exploit this vulnerability to overwrite arbitrary paths.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 1,
            "publishedOn": "2019-12-13T00:00:00Z",
            "updatedOn": "2019-12-13T00:00:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
    ]
}
```

## <a name="see-also"></a>참고 항목

- [위험 기반 위협 & 관리](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [조직의 취약성](/microsoft-365/security/defender-endpoint/tvm-weaknesses)
