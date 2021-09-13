---
title: 도메인 관련 알림 API를 얻습니다.
description: 도메인 관련 알림 다운로드 API를 사용하여 끝점용 Microsoft Defender에서 특정 도메인 주소와 관련된 경고를 검색하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, get, 도메인, 관련, 경고
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
ms.openlocfilehash: 7712500caf2e30d6ecdb8146ecfa4173e087f154
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221467"
---
# <a name="get-domain-related-alerts-api"></a>도메인 관련 알림 API를 얻습니다.

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명

지정한 도메인 주소와 관련된 [Alerts](alerts.md) 컬렉션을 검색합니다.

## <a name="limitations"></a>제한 사항

1. 구성된 보존 기간에 따라 마지막으로 업데이트된 경고에 대해 쿼리할 수 있습니다.
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
> - 응답에는 장치 그룹 설정에 따라 사용자가 액세스할 수 있는 알림만 포함됩니다(자세한 내용은 장치 그룹 [만들기](machine-groups.md) 및 관리 참조).

## <a name="http-request"></a>HTTP 요청

```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a>요청 헤더

|헤더|값|
|---|---|
|권한 부여|문자열|

## <a name="request-body"></a>요청 본문

비어 있음

## <a name="response"></a>응답

성공적이고 도메인이 있는 경우 - 경고 [](alerts.md) 엔터티 목록이 있는 200 OK. domain이 존재하지 않는 경우 - 200 OK(빈 집합)입니다.

## <a name="example"></a>예제

### <a name="request"></a>요청

다음은 요청의 예입니다.

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
