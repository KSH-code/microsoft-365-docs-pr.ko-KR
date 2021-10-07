---
title: 컴퓨터 관련 경고 API를 얻습니다.
description: 컴퓨터 관련 알림 표시 API를 사용하는 방법을 배워야 합니다. 이 API를 사용하면 끝점용 Microsoft Defender의 특정 장치와 관련된 모든 경고를 검색할 수 있습니다.
keywords: api, 그래프 api, 지원되는 api, get, 장치, 관련, 경고
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: f9797d80bb0b7b66644b021169abf340c6071698
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60184584"
---
# <a name="get-machine-related-alerts--api"></a>컴퓨터 관련 경고 API를 얻습니다.

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명

특정 [장치와](alerts.md) 관련된 모든 경고를 검색합니다.

## <a name="limitations"></a>제한 사항

1. 구성된 보존 기간에 따라 마지막으로 업데이트된 장치에서 쿼리할 수 있습니다.
2. 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.

사용 권한 유형|사용 권한|사용 권한 표시 이름
:---|:---|:---
응용 프로그램|Alert.Read.All|'모든 경고 읽기'
응용 프로그램|Alert.ReadWrite.All|'모든 경고 읽기 및 쓰기'
위임(직장 또는 학교 계정) | Alert.Read | '경고 읽기'
위임(직장 또는 학교 계정) | Alert.ReadWrite | '경고 읽기 및 쓰기'

> [!NOTE]
> 사용자 자격 증명을 사용하여 토큰을 얻을 때:
>
> - 사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다. 사용 권한에 대한 자세한 내용은 역할 만들기 [및 관리를 참조하세요.](user-roles.md)
> - 사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다. 장치 그룹 설정에 대한 자세한 내용은 장치 그룹 [만들기 및 관리를 참조하세요.](machine-groups.md)

## <a name="http-request"></a>HTTP 요청

```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a>요청 헤더

이름|유형|설명
:---|:---|:---
권한 부여 | String | Bearer {token}. **필수입니다**.

## <a name="request-body"></a>요청 본문

비어 있음

## <a name="response"></a>응답

성공 및 장치가 있는 경우: 본문에 경고 [](alerts.md) 엔터티 목록이 있는 200 OK. 장치를 찾을 수 없는 경우: 404 찾을 수 없습니다.
