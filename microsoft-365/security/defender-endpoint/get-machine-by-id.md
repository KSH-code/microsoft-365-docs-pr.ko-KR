---
title: ID로 컴퓨터 사용 API
description: ID로 컴퓨터 다운로드 API를 사용하여 끝점용 Microsoft Defender에서 장치 ID 또는 컴퓨터 이름으로 컴퓨터를 검색하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, get, 장치, 엔터티, ID
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: ce90523430ce1d9602609820221b9aca49efa4db
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59210322"
---
# <a name="get-machine-by-id-api"></a>ID로 컴퓨터 사용 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)


> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명
장치 [ID](machine.md) 또는 컴퓨터 이름으로 특정 컴퓨터를 검색합니다.

## <a name="limitations"></a>제한 사항

1. 구성된 보존 정책에 따라 장치를 마지막으로 볼 수 있습니다.
2. 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.

## <a name="permissions"></a>권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)

사용 권한 유형|사용 권한|사용 권한 표시 이름
:---|:---|:---
응용 프로그램|Machine.Read.All|'모든 컴퓨터 프로필 읽기'
응용 프로그램|Machine.ReadWrite.All|'모든 컴퓨터 정보 읽기 및 쓰기'
위임(직장 또는 학교 계정) | Machine.Read | '컴퓨터 정보 읽기'
위임(직장 또는 학교 계정) | Machine.ReadWrite | '컴퓨터 정보 읽기 및 쓰기'

> [!NOTE]
> 사용자 자격 증명을 사용하여 토큰을 얻을 때:
>
> - 사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).
> - 사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).

## <a name="http-request"></a>HTTP 요청

```http
GET /api/machines/{id}
```

## <a name="request-headers"></a>요청 헤더

이름|유형|설명
:---|:---|:---
권한 부여 | String | Bearer {token}. **필수입니다**.

## <a name="request-body"></a>요청 본문

비어 있음

## <a name="response"></a>응답

성공적이고 장치가 있는 경우 - 본문에 컴퓨터 엔터티가 있는 200 OK. [](machine.md)
지정한 ID가 있는 머신을 찾을 수 없는 경우 - 404 찾을 수 없습니다.

## <a name="example"></a>예제

### <a name="request-example"></a>요청 예제

다음은 요청의 예입니다.

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07
```

### <a name="response-example"></a>응답 예제

다음은 응답의 예입니다.

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machine",
    "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "computerDnsName": "mymachine1.contoso.com",
    "firstSeen": "2018-08-02T14:55:03.7791856Z",
    "lastSeen": "2018-08-02T14:55:03.7791856Z",
    "osPlatform": "Windows10",
    "version": "1709",
    "osProcessor": "x64",
    "lastIpAddress": "172.17.230.209",
    "lastExternalIpAddress": "167.220.196.71",
    "osBuild": 18209,
    "healthStatus": "Active",
    "rbacGroupId": 140,
    "rbacGroupName": "The-A-Team",
    "riskScore": "Low",
    "exposureLevel": "Medium",
    "isAadJoined": true,
    "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
    "machineTags": [ "test tag 1", "test tag 2" ]
}
```
