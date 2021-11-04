---
title: 컴퓨터 작업 취소 API
description: 이미 시작된 컴퓨터 작업을 취소하는 방법 학습
keywords: api, 그래프 api,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: df72be4ce5965476801dea9ea804ea9ebf548210
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60755750"
---
# <a name="cancel-machine-action-api"></a>컴퓨터 작업 취소 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명

아직 최종 상태가 아닌 이미 시작된 컴퓨터 작업 취소(완료, 취소, 실패)

## <a name="limitations"></a>제한 사항

1. 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.

## <a name="permissions"></a>사용 권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [시작을 참조합니다.](apis-intro.md)

|사용 권한 유형|사용 권한|사용 권한 표시 이름|
|---|---|---|
|응용 프로그램|Machine.CollectForensics <br> Machine.Isolate <br> Machine.RestrictExecution <br> Machine.Scan <br> Machine.Offboard <br> Machine.StopAndQuarantine <br> Machine.LiveResponse|포렌식 수집 <br>컴퓨터 격리<br>코드 실행 제한<br>  컴퓨터 검사<br>  컴퓨터 등록 취소<br> 중지 및 Quarantine<br> 특정 컴퓨터의 실시간 응답 실행|
|위임(직장 또는 학교 계정)|Machine.CollectForensics<br> Machine.Isolate  <br>Machine.RestrictExecution<br> Machine.Scan<br> Machine.Offboard<br> Machine.StopAndQuarantineMachine.LiveResponse|포렌식 수집<br> 컴퓨터 격리<br>  코드 실행 제한<br> 컴퓨터 검사<br>컴퓨터 등록 취소<br> 중지 및 Quarantine<br> 특정 컴퓨터의 실시간 응답 실행|

## <a name="http-request"></a>HTTP 요청

```http
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel
```

## <a name="request-headers"></a>요청 헤더

|이름|유형|설명|
|---|---|---|
|권한 부여|문자열|Bearer {token}. 필수 특성입니다.|
|Content-Type|문자열|application/json. 필수 특성입니다.|

## <a name="request-body"></a>요청 본문

|매개 변수|유형|설명|
|---|---|---|
|Comment|String|취소 작업과 연결되는 설명입니다.|

## <a name="response"></a>응답

성공하면 이 메서드는 Machine Action 엔터티가 있는 200, 확인 응답 코드를 반환합니다. 지정된 ID가 있는 컴퓨터 작업 엔터티를 찾을 수 없는 경우 - 404 찾을 수 없습니다.

## <a name="example"></a>예제

### <a name="request"></a>요청

다음은 요청의 예입니다.

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```

```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a>관련 항목

- [컴퓨터 작업 API를 얻습니다.](get-machineaction-object.md)
