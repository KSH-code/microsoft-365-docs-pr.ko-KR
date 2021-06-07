---
title: 도메인 관련 컴퓨터 확인 API
description: 도메인 관련 컴퓨터 다운로드 API를 사용하여 끝점용 Microsoft Defender의 도메인과 통신한 컴퓨터를 다운로드하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, get, 도메인, 관련, 장치
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
ms.openlocfilehash: 362e3db0ed89924c58fa9662f7acbbe0c16c37c6
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772224"
---
# <a name="get-domain-related-machines-api"></a>도메인 관련 컴퓨터 확인 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 설명
특정 도메인 [주소와](machine.md) 통신한 컴퓨터 컬렉션을 검색합니다.


## <a name="limitations"></a>제한 사항
1. 구성된 보존 기간에 따라 마지막으로 업데이트된 장치에서 쿼리할 수 있습니다.
2. 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.


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
>- 사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).
>- 응답에는 장치 그룹 설정에 따라 사용자가 액세스할 수 있는 장치만 포함됩니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).

## <a name="http-request"></a>HTTP 요청
```http
GET /api/domains/{domain}/machines
```

## <a name="request-headers"></a>요청 헤더

이름 | 유형 | 설명
:---|:---|:---
권한 부여 | String | Bearer {token}. **필수입니다**.


## <a name="request-body"></a>요청 본문
비어 있음

## <a name="response"></a>응답
성공 및 도메인이 있는 경우 - 컴퓨터 [](machine.md) 엔터티 목록이 있는 200 OK. 도메인이 존재하지 않는 경우 - 404 찾을 수 없습니다.


## <a name="example"></a>예시

**요청**

다음은 요청의 예입니다.

```http
GET https://api.securitycenter.microsoft.com/api/domains/api.securitycenter.microsoft.com/machines
```
