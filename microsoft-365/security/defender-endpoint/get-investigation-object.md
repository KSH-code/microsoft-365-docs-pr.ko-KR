---
title: 조사 개체 GET API
description: 이 API를 사용하여 조사 개체 얻기와 관련된 호출 만들기
keywords: api, 그래프 api, 지원되는 api, 조사 개체
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
ms.technology: mde
ms.openlocfilehash: 9f011f10a9fe3c3aec535e157abee2367998b1a4
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166801"
---
# <a name="get-investigation-api"></a>조사 API를 얻습니다.

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 설명
ID로 [특정 조사를](investigation.md) 검색합니다.
<br> ID는 조사 ID 또는 경고 ID를 트리거하는 조사일 수 있습니다.


## <a name="limitations"></a>제한 사항
1. 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.


## <a name="permissions"></a>사용 권한
이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)

사용 권한 유형 |   사용 권한  |   사용 권한 표시 이름
:---|:---|:---
응용 프로그램 |   Alert.Read.All |    '모든 경고 읽기'
응용 프로그램 |   Alert.ReadWrite.All |   '모든 경고 읽기 및 쓰기'
위임(직장 또는 학교 계정) | Alert.Read | '경고 읽기'
위임(직장 또는 학교 계정) | Alert.ReadWrite | '경고 읽기 및 쓰기'

>[!Note]
> 사용자 자격 증명을 사용하여 토큰을 얻을 때:
>- 사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).

## <a name="http-request"></a>HTTP 요청
```
GET https://api.securitycenter.microsoft.com/api/investigations/{id}
```

## <a name="request-headers"></a>요청 헤더

이름 | 유형 | 설명
:---|:---|:---
권한 부여 | 문자열 | Bearer {token}. **필수입니다**.


## <a name="request-body"></a>요청 본문
비어 있음

## <a name="response"></a>응답
성공하면 이 메서드는 [Investigations](investigation.md) 엔터티가 있는 200, 확인 응답 코드를 반환합니다.

