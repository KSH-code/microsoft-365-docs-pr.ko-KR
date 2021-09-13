---
title: 모델 일괄 적용
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
description: REST API를 사용하여 하나 이상의 라이브러리에 문서 이해 모델을 적용합니다.
ms.openlocfilehash: 04f1dfdb0c16110c9ba7de12f5f0735d498d50cf
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221080"
---
# <a name="batch-apply-model"></a>모델 일괄 적용

학습된 문서 이해 모델을 하나 이상의 라이브러리에 적용하거나 동기화합니다([예제](rest-applymodel-method.md#examples)참조).

## <a name="http-request"></a>HTTP 요청

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a>URI 매개 변수

없음

## <a name="request-headers"></a>요청 헤더

| 헤더 | 값 |
|--------|-------|
|수락|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|현재 사이트에 적합한 다이제스트입니다.|

## <a name="request-body"></a>요청 본문

| 이름 | 필수 | 유형 | 설명 |
|--------|-------|--------|------------|
|__metadata|예|문자열|SPO에 개체 메타를 설정합니다. 항상 {“type”: “Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData”} 값을 사용합니다.|
|Publications|예|MachineLearningPublicationEntityData[]|각각 모델 및 대상 문서 라이브러리를 지정하는 MachineLearningPublicationEntityData의 컬렉션입니다.|

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| 이름 | 필수 | 유형 | 설명 |
|--------|-------|--------|------------|
|ModelUniqueId|예|문자열|모델 파일의 고유 ID입니다.|
|TargetSiteUrl|예|문자열|대상 라이브러리 사이트의 전체 URL입니다.|
|TargetWebServerRelativeUrl|예|문자열|대상 라이브러리에 대한 웹의 서버 상대 URL입니다.|
|TargetLibraryServerRelativeUrl|예|문자열|대상 라이브러리의 서버 상대 URL입니다.|
|ViewOption|아니요|문자열|새 모델 뷰를 라이브러리 기본값으로 설정할지 여부를 지정합니다.|

## <a name="response"></a>응답

| 이름   | 유형  | 설명|
|--------|-------|------------|
|201 생성됨||다중 문서 라이브러리에 모델을 적용하도록 지원하는 사용자 지정 API입니다. 부분적으로 성공하는 경우에도 생성된 201이 반환될 수 있으며, 호출자는 응답 본문을 검사하여 모델이 문서 라이브러리에 성공적으로 적용되었는지 파악해야 합니다.|

## <a name="response-body"></a>응답 본문

| 이름   | 유형  | 설명|
|--------|-------|------------|
|TotalSuccesses|int|문서 라이브러리에 성공적으로 적용된 모델의 총수입니다.|
|TotalFailures|int|문서 라이브러리에 적용되지 못한 모델의 총수입니다.|
|세부 정보|MachineLearningPublicationResult[]|각각 문서 라이브러리에 모델을 적용한 자세한 결과를 지정하는 MachineLearningPublicationResult의 컬렉션입니다.|

### <a name="machinelearningpublicationresult"></a>MachineLearningPublicationResult

| 이름   | 유형  | 설명|
|--------|-------|------------|
|StatusCode|int|HTTP 상태 코드입니다.|
|ErrorMessage|문자열|문서 라이브러리에 모델을 적용할 때 무엇이 잘못되었는지 알려 주는 오류 메시지입니다.|
|Publication|MachineLearningPublicationEntityData|모델 정보 및 대상 문서 라이브러리를 지정합니다.| 

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| 이름 | 유형 | 설명 |
|--------|--------|------------|
|ModelUniqueId|문자열|모델 파일의 고유 ID입니다.|
|TargetSiteUrl|문자열|대상 라이브러리 사이트의 전체 URL입니다.|
|TargetWebServerRelativeUrl|문자열|대상 라이브러리에 대한 웹의 서버 상대 URL입니다.|
|TargetLibraryServerRelativeUrl|문자열|대상 라이브러리의 서버 상대 URL입니다.|

## <a name="examples"></a>예제

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a>리포지토리 사이트의 계약 문서 라이브러리에 모델 적용

이 샘플에서는 Contoso 계약 문서 이해 모델의 ID가 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`입니다.

#### <a name="sample-request"></a>샘플 요청

```HTTP
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"
    },
    "Publications": {
        "results": [
            {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            }
        ]
    }
}
```


#### <a name="sample-response"></a>샘플 응답

응답 내 TotalFailures 및 TotalSuccesses는 지정된 라이브러리에 모델을 적용하지 못한 횟수와 성공적으로 적용한 횟수를 나타냅니다.

**상태 코드:** 201

```JSON
{
    "Details": [
        {
            "ErrorMessage": null,
            "Publication": {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            },
            "StatusCode": 201
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>참고 항목

[Syntex 문서 이해 모델 REST API](syntex-model-rest-api.md)
