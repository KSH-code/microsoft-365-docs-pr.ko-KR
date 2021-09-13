---
title: 목록 조사 API
description: 이 API를 사용하여 Investigations 컬렉션을 받을 때와 관련된 호출을 만들 수 있습니다.
keywords: api, 그래프 api, 지원되는 api, 조사 컬렉션
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.openlocfilehash: 73dd701eff97d7afb3fee7f4480a16296fa3d983
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221368"
---
# <a name="list-investigations-api"></a>목록 조사 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명

조사 [컬렉션을 검색합니다.](investigation.md)

[OData V4 쿼리를 지원합니다.](https://www.odata.org/documentation/)

OData의 쿼리는 `$filter` `startTime` , , `id` 및 `state` `machineId` 속성에서 `triggeringAlertId` 지원됩니다.
<br>```$stop``` 최대값 10,000
<br>```$skip```

[끝점용 Microsoft Defender를 사용하여 OData 쿼리 예제 보기](exposed-apis-odata-samples.md)

## <a name="limitations"></a>제한 사항

1. 최대 페이지 크기는 10,000개입니다.
2. 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.

## <a name="permissions"></a>권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)

사용 권한 유형|사용 권한|사용 권한 표시 이름
:---|:---|:---
응용 프로그램|Alert.Read.All|'모든 경고 읽기'
응용 프로그램|Alert.ReadWrite.All|'모든 경고 읽기 및 쓰기'
위임(직장 또는 학교 계정)|Alert.Read|'경고 읽기'
위임(직장 또는 학교 계정)|Alert.ReadWrite|'경고 읽기 및 쓰기'

> [!NOTE]
> 사용자 자격 증명을 사용하여 토큰을 얻을 때:
>
> - 사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).

## <a name="http-request"></a>HTTP 요청

```http
GET https://api.securitycenter.microsoft.com/api/investigations
```

## <a name="request-headers"></a>요청 헤더

이름|유형|설명
:---|:---|:---
권한 부여|문자열|Bearer {token}. **필수입니다**.

## <a name="request-body"></a>요청 본문

비어 있음

## <a name="response"></a>응답

성공하면 이 메서드는 조사 엔터티 컬렉션이 있는 200, 확인 응답 [코드를](investigation.md) 반환합니다.

## <a name="example"></a>예제

### <a name="request-example"></a>요청 예제

다음은 모든 조사를 요청하는 예입니다.

```http
GET https://api.securitycenter.microsoft.com/api/investigations
```

### <a name="response-example"></a>응답 예제

응답의 예는 다음과 같습니다.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Investigations",
    "value": [
        {
            "id": "63017",
            "startTime": "2020-01-06T14:11:34Z",
            "endTime": null,
            "state": "Running",
            "cancelledBy": null,
            "statusDetails": null,
            "machineId": "a69a22debe5f274d8765ea3c368d00762e057b30",
            "computerDnsName": "desktop-gtrcon0",
            "triggeringAlertId": "da637139166940871892_-598649278"
        }
        ...
    ]
}
```
