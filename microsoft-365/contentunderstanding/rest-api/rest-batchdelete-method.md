---
title: BatchDelete
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
description: 하나 이상의 라이브러리에서 적용된 문서 이해 모델을 제거합니다.
ms.openlocfilehash: 8c7aeb449da161fe49050631643c63c93268a13f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904274"
---
# <a name="batchdelete"></a>BatchDelete

하나 이상의 라이브러리에서 적용된 문서 이해 모델을 제거합니다. 모델을 삭제하려면 먼저 모든 라이브러리에서 모델을 제거해야 합니다( [예제](rest-batchdelete-method.md#examples)참조).

## <a name="http-request"></a>HTTP 요청

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
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
|ModelUniqueId|예|문자열|모델 파일의 고유 ID입니다.|
TargetSiteUrl|예|문자열|대상 라이브러리 사이트의 전체 URL입니다.|
TargetWebServerRelativeUrl|예|문자열|대상 라이브러리에 대한 웹의 서버 상대 URL입니다.|
TargetLibraryServerRelativeUrl|예|문자열|대상 라이브러리의 서버 상대 URL입니다.|
ViewOption|아니요|문자열|새 모델 뷰를 라이브러리 기본값으로 설정할지 여부를 지정합니다.|

## <a name="response"></a>응답

| 이름   | 유형  | 설명|
|--------|-------|------------|
|200 OK| |성공|


## <a name="examples"></a>예제

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a>리포지토리 사이트의 계약 문서 라이브러리에서 모델 제거

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

응답에서 TotalFailures 및 TotalSuccesses는 지정된 라이브러리에 적용되는 모델의 실패 및 성공 횟수를 나타냅니다.

**상태 코드:** 200

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
            "StatusCode": 200
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>참고 항목

[Syntex 문서 이해 모델 REST API](syntex-model-rest-api.md)
