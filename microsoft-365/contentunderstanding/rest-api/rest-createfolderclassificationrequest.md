---
title: 폴더 분류 요청 만들기
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: REST API를 사용하여 학습된 문서 이해 모델을 사용하여 전체 폴더를 분류하는 요청을 만듭니다.
ms.openlocfilehash: 44e1969628fb61b797f59a7378b95403c94dda8a
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59777129"
---
# <a name="create-folder-classification-request"></a>폴더 분류 요청 만들기

적용된 문서 이해 모델을 사용하여 사용량이 적은 시간에 전체 폴더를 분류하는 요청을 생성합니다. (자세한 내용은 [예시](rest-createfolderclassificationrequest.md#examples)를 참조하세요) 이 API는 루트 폴더에 대한 작업 항목을 만들어 전체 문서 라이브러리를 분류하는 데 사용할 수 있습니다.

## <a name="http-request"></a>HTTP 요청

```http
POST /_api/machinelearning/workItems HTTP/1.1
```

## <a name="uri-parameters"></a>URI 매개 변수

없음

## <a name="request-headers"></a>요청 헤더

| 헤더 | 값 |
|--------|-------|
|수락|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|현재 사이트에 적합한 다이제스트|

## <a name="request-body"></a>요청 본문

|이름    |유형   |설명 |
|--------|-------|------------|
|_metadata|문자열 |SPO에 개체 메타를 설정합니다. 항상 {“type”: “Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData”} 값을 사용합니다. |
|TargetSiteId|GUID|분류할 폴더가 있는 사이트의 ID입니다. TargetSiteUrl에 값이 있으면 생략할 수 있습니다. |
|TargetSiteUrl|문자열|분류할 폴더가 있는 사이트의 전체 URL입니다. TargeSiteId에 값이 있으면 생략할 수 있습니다.|
|TargetWebId|GUID|분류할 폴더가 있는 웹의 ID입니다. TargetWebServerRelativeUrl에 값이 있는 경우 생략할 수 있습니다. |
|TargetWebServerRelativeUrl|문자열|분류할 폴더가 있는 웹의 서버 상대 URL입니다. TargetWebId에 값이 있는 경우 생략할 수 있습니다.  |
|TargetUniqueId|GUID|분류할 폴더의 ID입니다. TargetServerRelativeUrl에 값이 있는 경우 생략할 수 있습니다. |
|TargetServerRelativeUrl|문자열|분류할 폴더의 서버 상대 URL입니다. TargetUniqueId에 값이 있으면 생략할 수 있습니다.|
|IsFolder|부울|분류할 항목이 폴더인지를 나타내는 플래그입니다. 폴더 분류 작업 항목을 만들기 위해 항상 true로 설정합니다. |


## <a name="responses"></a>응답

| 이름   | 유형  | 설명|
|--------|-------|------------|
|201 생성됨| |응답이 사용자 지정됩니다. 오류가 있는 경우에도 201 Created를 반환할 수 있습니다. 호출자는 응답 본문을 추가로 확인하여 정확한 결과를 확인해야 합니다.|

## <a name="response-body"></a>응답 본문

| 이름   | 유형  | 설명|
|--------|-------|------------|
|StatusCode |int |HTTP 상태 코드입니다. 200 또는 201이 아닌 경우 API가 실패했을 것입니다.|
|ErrorMessage |문자열 |문서 라이브러리에 모델을 적용할 때 무엇이 잘못되었는지 알려 주는 오류 메시지입니다.|

## <a name="examples"></a>예제

### <a name="enqueue-a-request-to-classify-a-whole-folder-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a>ID "e6cff8b7-c90c-4564-b5b8-033449090932"의 전체 폴더를 분류하는 요청을 큐에 추가합니다.


#### <a name="sample-request"></a>샘플 요청

```JSON
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932",
    "IsFolder": true 
}
```

#### <a name="sample-response"></a>샘플 응답

**상태 코드:** 201

```JSON
{
    "ErrorMessage":  null,
    "StatusCode":  201
}
```

## <a name="see-also"></a>참고 항목

[Syntex 문서 이해 모델 REST API](syntex-model-rest-api.md)
