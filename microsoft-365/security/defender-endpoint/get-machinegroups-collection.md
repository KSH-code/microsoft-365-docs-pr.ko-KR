---
title: RBAC 컴퓨터 그룹 컬렉션 수집 API 사용
description: KB 컬렉션 다운로드 API를 사용하여 Microsoft Defender Advanced Threat Protection에서 RBAC 장치 그룹 컬렉션을 검색하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, get, RBAC, 그룹
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
ms.date: 10/07/2018
ms.openlocfilehash: 54a0edb47204fe6e48666f0927d05121af95e00a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167022"
---
# <a name="get-kb-collection-api"></a>KB 컬렉션 API 사용

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


RBAC 장치 그룹 컬렉션을 검색합니다.

## <a name="permissions"></a>사용 권한
사용자에게 읽기 권한이 필요합니다.

## <a name="http-request"></a>HTTP 요청
```
GET /testwdatppreview/machinegroups
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
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

**응답**

다음은 응답의 예입니다.
필드 ID에는 장치 그룹 **ID가** 포함되어 있으며 디바이스 정보의 **필드 rbacGroupId와** 동일합니다. **그룹화되지 않은** 필드는 그룹에 할당되지 않은 모든 장치에 대해 하나의 그룹에만 true입니다. 이 그룹은 평소와 같이 이름이 "UnassignedGroup"입니다.

```
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
        …
}
```
