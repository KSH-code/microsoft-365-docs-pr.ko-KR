---
title: UpdateModelSettings
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
description: REST API 사용하여 SharePoint Syntex 문서 이해 모델에 사용할 수 있는 모델 설정을 업데이트합니다.
ms.openlocfilehash: cd288812044f3b02839c3c11c321947bd02cccaa
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177168"
---
# <a name="updatemodelsettings"></a>UpdateModelSettings

SharePoint Syntex 문서 이해 모델에 대해 사용 가능한 모델 설정(관련 보존 레이블 및 모델 설명)을 업데이트합니다([예제](rest-updatemodelsettings-method.md#examples) 참조).

## <a name="http-request"></a>HTTP 요청

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a>URI 매개 변수

|이름 |In |필수|유형|설명|
|-----|---|--------|----|-----------|
|modelFileName|쿼리|True|문자열|Syntex 모델 파일의 이름입니다.|

## <a name="request-headers"></a>요청 헤더

| 헤더 | 값 |
|--------|-------|
|수락|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|현재 사이트에 적합한 다이제스트입니다.|

## <a name="request-body"></a>요청 본문

|이름    |유형   |설명 |
|--------|-------|-------|
|ModelSettings|문자열|모델 설정의 JSON입니다.|
|설명|문자열|모델 설명입니다.|
|RetentionLabel| |연결된 레이블(레이블 ID 및 이름)에 대한 정보입니다.|

## <a name="responses"></a>응답

| 이름   | 유형  | 설명|
|--------|-------|------------|
|200 OK| |성공|

## <a name="examples"></a>예제

### <a name="update-model-settings-for-contoso-contract"></a>Contoso 계약에 대한 모델 설정 업데이트

이 예제에서는 모델 설명 및 "표준 보류" 보존 레이블이 업데이트됩니다. 보존 레이블의 ID는 `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`입니다.

#### <a name="sample-request"></a>샘플 요청

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a>샘플 응답

**상태 코드:** 200

## <a name="see-also"></a>참고 항목

[Syntex 문서 이해 모델 REST API](syntex-model-rest-api.md)
