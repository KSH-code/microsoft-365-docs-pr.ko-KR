---
title: 컴퓨터 관련 경고 API를 얻습니다.
description: 컴퓨터 관련 알림 다운로드 API를 사용하여 끝점용 Microsoft Defender의 특정 장치와 관련된 모든 경고를 검색하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, get, 장치, 관련, 경고
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
ms.openlocfilehash: 837643bf5793437380a6f33c0eeca55ccef2100b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199254"
---
# <a name="get-machine-related-alerts--api"></a>컴퓨터 관련 경고 API를 얻습니다.

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명
특정 [장치와](alerts.md) 관련된 모든 경고를 검색합니다.


## <a name="limitations"></a>제한 사항
1. 구성된 보존 기간에 따라 마지막으로 업데이트된 장치에서 쿼리할 수 있습니다.
2. 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.


사용 권한 유형 |   사용 권한  |   사용 권한 표시 이름
:---|:---|:---
응용 프로그램 |   Alert.Read.All |    '모든 경고 읽기'
응용 프로그램 |   Alert.ReadWrite.All |   '모든 경고 읽기 및 쓰기'
위임(직장 또는 학교 계정) | Alert.Read | '경고 읽기'
위임(직장 또는 학교 계정) | Alert.ReadWrite | '경고 읽기 및 쓰기'

>[!Note]
> 사용자 자격 증명을 사용하여 토큰을 얻을 때:
>- 사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).
>- 사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).

## <a name="http-request"></a>HTTP 요청
```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a>요청 헤더

이름 | 유형 | 설명
:---|:---|:---
권한 부여 | 문자열 | Bearer {token}. **필수입니다**.


## <a name="request-body"></a>요청 본문
비어 있음

## <a name="response"></a>응답
성공 및 장치가 있는 경우 - 본문에 [](alerts.md) 경고 엔터티 목록이 있는 200 OK. 장치를 찾을 수 없는 경우 - 404 찾을 수 없습니다.
