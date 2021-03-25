---
title: 컴퓨터 보안 상태 수집 API를 얻습니다.
description: 끝점용 Microsoft Defender를 사용하여 장치 보안 상태 컬렉션을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, 장치, 보안, 상태
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: 9dab4bdccc1fead5bc2cc5b9bdff8f2a45b6c8db
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200368"
---
# <a name="get-machines-security-states-collection-api"></a>컴퓨터 보안 상태 수집 API를 얻습니다.

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

장치 보안 상태 컬렉션을 검색합니다.

## <a name="permissions"></a>사용 권한
사용자에게 읽기 권한이 필요합니다.

## <a name="http-request"></a>HTTP 요청
```
GET /testwdatppreview/machinesecuritystates
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

## <a name="example"></a>예제

**요청**

다음은 요청의 예입니다.

```
GET https://graph.microsoft.com/testwdatppreview/machinesecuritystates
Content-type: application/json
```

**응답**

다음은 응답의 예입니다.
필드 *ID는* 디바이스 ID를 포함하며 디바이스 정보의 필드 *ID**에 해당합니다. 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineSecurityStates",
    "@odata.count":444,
    "@odata.nextLink":"https://graph.microsoft.com/testwdatppreview/machinesecuritystates?$skiptoken=[continuation token]",
    "value":[
        {
            "id":"000050e1b4afeee3742489ede9ad7a3e16bbd9c4",
            "build":14393,
            "revision":2485,
            "architecture":"Amd64",
            "osVersion":"10.0.14393.2485.amd64fre.rs1_release.180827-1809",
            "propertiesRequireAttention":[
                "AntivirusNotReporting",
                "EdrImpairedCommunications"
            ]
        },
        …
    ]
}
```
