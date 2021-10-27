---
title: RBAC 컴퓨터 그룹 컬렉션 수집 API 사용
description: KB 컬렉션 다운로드 API를 사용하여 끝점용 Microsoft Defender에서 RBAC 장치 그룹 컬렉션을 검색하는 방법을 확인합니다.
keywords: api, 그래프 api, 지원되는 api, get, RBAC, 그룹
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
ms.date: 10/07/2018
ms.custom: api
ms.openlocfilehash: 0a9180c1705f7a583244d93ff9aa323aed1feb9c
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2021
ms.locfileid: "60586472"
---
# <a name="get-kb-collection-api"></a>KB 컬렉션 API 사용

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

RBAC 장치 그룹 컬렉션을 검색합니다.

## <a name="permissions"></a>사용 권한

사용자에게 읽기 권한이 필요합니다.

## <a name="http-request"></a>HTTP 요청

```http
GET /testwdatppreview/machinegroups
```

## <a name="request-headers"></a>요청 헤더

헤더|값
:---|:---
권한 부여 | Bearer {token}. **필수입니다**.
콘텐츠 형식 | application/json

## <a name="request-body"></a>요청 본문

비어 있음

## <a name="response"></a>응답

성공적이면 - 200 OK.

## <a name="example"></a>예제

### <a name="request"></a>요청

다음은 요청의 예입니다.

```http
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

### <a name="response-example"></a>응답 예제

다음은 응답의 예입니다.
필드 ID에는 장치 그룹 **ID가** 포함되어 있으며 디바이스 정보의 **필드 rbacGroupId와** 동일합니다.
**그룹화되지 않은** 필드는 그룹에 할당되지 않은 모든 장치에 대해 하나의 그룹에만 true입니다. 이 그룹은 평소와 같이 이름이 "UnassignedGroup"입니다.

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        ...
}
```
