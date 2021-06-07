---
title: 태그 API로 장치 찾기
description: 지정 태그가 포함된 모든 장치 찾기
keywords: api, 지원되는 api, get, 디바이스, 찾기, 디바이스 찾기, 태그, 태그
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
ms.openlocfilehash: 88ad63d8b7cc71f7d3f809c7cb0371fc41bb9f5d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771168"
---
# <a name="find-devices-by-tag-api"></a>태그 API로 장치 찾기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 설명
태그로 [컴퓨터를](machine.md) [검색합니다.](machine-tags.md)
<br>```startswith``` 쿼리가 지원됩니다. 

## <a name="limitations"></a>제한 사항
1. 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.


## <a name="permissions"></a>사용 권한
이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)

사용 권한 유형 |   사용 권한  |   사용 권한 표시 이름
:---|:---|:---
응용 프로그램 |   Machine.Read.All |  '모든 컴퓨터 프로필 읽기'
응용 프로그램 |   Machine.ReadWrite.All | '모든 컴퓨터 정보 읽기 및 쓰기'
위임(직장 또는 학교 계정) | Machine.Read | '컴퓨터 정보 읽기'
위임(직장 또는 학교 계정) | Machine.ReadWrite | '컴퓨터 정보 읽기 및 쓰기'

>[!Note]
> 사용자 자격 증명을 사용하여 토큰을 얻을 때:
> - 응답에는 사용자가 장치 그룹 설정에 따라 액세스할 수 있는 장치만 포함됩니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).
> - 사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).
> - 응답에는 사용자가 장치 그룹 설정에 따라 액세스할 수 있는 장치만 포함됩니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).

## <a name="http-request"></a>HTTP 요청
```
GET /api/machines/findbytag?tag={tag}&useStartsWithFilter={true/false}
```

## <a name="request-headers"></a>요청 헤더

이름 | 유형 | 설명
:---|:---|:---
권한 부여 | String | Bearer {token}. **필수입니다**.

## <a name="request-uri-parameters"></a>요청 URI 매개 변수

이름 | 유형 | 설명
:---|:---|:---
tag | String | 태그 이름입니다. **필수입니다**.
useStartsWithFilter | 부울 | true로 설정하면 쿼리에서 태그 이름이 지정한 태그로 시작하는 모든 장치가 검색됩니다. 기본값은 false입니다. 선택 사항입니다.

## <a name="request-body"></a>요청 본문
비어 있음

## <a name="response"></a>응답
성공적이면 - 응답 본문에 컴퓨터 목록이 있는 200 OK.

## <a name="example"></a>예시

**요청**

다음은 요청의 예입니다.

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbytag?tag=testTag&useStartsWithFilter=true
```