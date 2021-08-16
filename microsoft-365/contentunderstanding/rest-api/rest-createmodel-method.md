---
title: 모델 만들기
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
description: REST API를 사용하여 모델 및 관련 콘텐츠 형식을 만듭니다.
ms.openlocfilehash: ac5a48f92352c2c286323b8a679a975e0dbdca80703f9f727d16a4999b4a2f65
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "53899814"
---
# <a name="create-model"></a>모델 만들기

모델 및 관련 콘텐츠 형식을 만듭니다. 이렇게 하면 모델만 생성됩니다. 콘텐츠 센터에서 계속 학습해야 합니다( [예제](rest-createmodel-method.md#examples)참조).

## <a name="http-request"></a>HTTP 요청

```http
POST /_api/machinelearning/models HTTP/1.1
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
|_metadata|  |SPO에 개체 메타를 설정합니다. 항상 값 {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}를 사용합니다. |
|ContentTypeGroup|문자열|모델과 연결된 연결된 콘텐츠 형식 그룹입니다. 기본값은 "지능형 문서 콘텐츠 형식"입니다.|
|ContentTypeName|문자열|연결된 콘텐츠 형식 이름입니다. 만든 모델 파일의 이름이 같습니다.|

## <a name="responses"></a>응답

| 이름   | 유형  | 설명|
|--------|-------|------------|
|201 생성됨| |성공|

## <a name="examples"></a>예제

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a>"Contoso Contract"라는 새 문서 이해 모델 만들기

#### <a name="sample-request"></a>샘플 요청

```json
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract"
}
```

#### <a name="sample-response"></a>샘플 응답

**상태 코드:** 201

## <a name="see-also"></a>참고 항목

[Syntex 문서 이해 모델 REST API](syntex-model-rest-api.md)
