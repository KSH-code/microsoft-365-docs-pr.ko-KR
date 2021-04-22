---
title: 소프트웨어 목록
description: 소프트웨어 인벤토리 목록을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, 다운로드, 목록, 파일, 정보, 소프트웨어 인벤토리, 위협 & 취약성 관리 api, 끝점 tvm api용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 6522b546dfde7447a03b3c417be93d288e261908
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934012"
---
# <a name="list-software-inventory-api"></a>소프트웨어 인벤토리 목록 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

조직 소프트웨어 인벤토리를 검색합니다.

## <a name="permissions"></a>사용 권한
이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.

사용 권한 유형 |   사용 권한  |   사용 권한 표시 이름
:---|:---|:---
응용 프로그램 |Software.Read.All |    '위협 및 취약성 관리 소프트웨어 정보 읽기'
위임(직장 또는 학교 계정) | Software.Read |    '위협 및 취약성 관리 소프트웨어 정보 읽기'

## <a name="http-request"></a>HTTP 요청
```
GET /api/Software
```

## <a name="request-headers"></a>요청 헤더

이름 | 유형 | 설명
:---|:---|:---
권한 부여 | 문자열 | Bearer {token}. **필수입니다**.


## <a name="request-body"></a>요청 본문
비어 있음

## <a name="response"></a>응답
성공하면 이 메서드는 본문에 소프트웨어 인벤토리가 있는 200 OK를 반환합니다.


## <a name="example"></a>예시

**요청**

다음은 요청의 예입니다.

```
GET https://api.securitycenter.microsoft.com/api/Software
```

**응답**

다음은 응답의 예입니다.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
    "value": [
            {
                "id": "microsoft-_-edge",
                "name": "edge",
                "vendor": "microsoft",
                "weaknesses": 467,
                "publicExploit": true,
                "activeAlert": false,
                "exposedMachines": 172,
                "impactScore": 2.39947438
            }
            ...
        ]
}
```

## <a name="related-topics"></a>관련 항목
- [위험 기반 위협 & 관리](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [위협 & 소프트웨어 인벤토리](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
