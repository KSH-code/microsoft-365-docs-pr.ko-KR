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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 320f2bfd06f7f01c15419f4bd6dc0eb5536079f0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60176814"
---
# <a name="get-machines-security-states-collection-api"></a>컴퓨터 보안 상태 수집 API를 얻습니다.

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

장치 보안 상태 컬렉션을 검색합니다.

## <a name="permissions"></a>권한

사용자에게 읽기 권한이 필요합니다.

## <a name="http-request"></a>HTTP 요청

```http
GET /testwdatppreview/machinesecuritystates
```

## <a name="request-headers"></a>요청 헤더

헤더|값
:---|:---
권한 부여|Bearer {token}. **필수입니다**.
콘텐츠 형식|application/json

## <a name="request-body"></a>요청 본문

비어 있음

## <a name="response"></a>응답

성공적이면 - 200 OK.

## <a name="example"></a>예제

### <a name="request-example"></a>요청 예제

다음은 요청의 예입니다.

```http
GET https://graph.microsoft.com/testwdatppreview/machinesecuritystates
Content-type: application/json
```

### <a name="response-example"></a>응답 예제

다음은 응답의 예입니다.

필드 *ID는* 디바이스 ID를 포함하며 디바이스 정보의 필드 *ID**에 해당합니다.

```json
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
        ...
    ]
}
```
