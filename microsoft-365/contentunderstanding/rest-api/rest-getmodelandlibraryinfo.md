---
title: 모델 및 라이브러리 정보 가져오기
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
description: REST API를 사용하여 모델 및 모델이 적용된 라이브러리에 대한 정보를 가져옵니다.
ms.openlocfilehash: 2449084653c6d9af8d774edc306c485e7a466bf6
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177072"
---
# <a name="get-model-and-library-information"></a><span data-ttu-id="d6c9b-103">모델 및 라이브러리 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="d6c9b-103">Get model and library information</span></span>

<span data-ttu-id="d6c9b-104">모델 및 모델이 적용된 라이브러리에 대한 정보를 가져옵니다([예제](rest-getmodelandlibraryinfo.md#examples) 참조).</span><span class="sxs-lookup"><span data-stu-id="d6c9b-104">Gets information about a model and the library where it has been applied (see [example](rest-getmodelandlibraryinfo.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="d6c9b-105">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="d6c9b-105">HTTP request</span></span>

```HTTP
GET /_api/machinelearning/publications/getbymodeluniqueid('{modelUniqueId}') HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="d6c9b-106">URI 매개 변수</span><span class="sxs-lookup"><span data-stu-id="d6c9b-106">URI parameters</span></span>

| <span data-ttu-id="d6c9b-107">이름</span><span class="sxs-lookup"><span data-stu-id="d6c9b-107">Name</span></span> | <span data-ttu-id="d6c9b-108">In</span><span class="sxs-lookup"><span data-stu-id="d6c9b-108">In</span></span> | <span data-ttu-id="d6c9b-109">필수</span><span class="sxs-lookup"><span data-stu-id="d6c9b-109">Required</span></span> | <span data-ttu-id="d6c9b-110">유형</span><span class="sxs-lookup"><span data-stu-id="d6c9b-110">Type</span></span> | <span data-ttu-id="d6c9b-111">설명</span><span class="sxs-lookup"><span data-stu-id="d6c9b-111">Description</span></span> |
|--------|-------|--------|------------|-----------|
|<span data-ttu-id="d6c9b-112">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="d6c9b-112">ModelUniqueId</span></span>|<span data-ttu-id="d6c9b-113">쿼리</span><span class="sxs-lookup"><span data-stu-id="d6c9b-113">query</span></span>|<span data-ttu-id="d6c9b-114">True</span><span class="sxs-lookup"><span data-stu-id="d6c9b-114">True</span></span>|<span data-ttu-id="d6c9b-115">GUID</span><span class="sxs-lookup"><span data-stu-id="d6c9b-115">GUID</span></span>|<span data-ttu-id="d6c9b-116">모델 파일의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d6c9b-116">The unique id of the model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="d6c9b-117">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="d6c9b-117">Request headers</span></span>

| <span data-ttu-id="d6c9b-118">헤더</span><span class="sxs-lookup"><span data-stu-id="d6c9b-118">Header</span></span> | <span data-ttu-id="d6c9b-119">값</span><span class="sxs-lookup"><span data-stu-id="d6c9b-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="d6c9b-120">수락</span><span class="sxs-lookup"><span data-stu-id="d6c9b-120">Accept</span></span>|<span data-ttu-id="d6c9b-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="d6c9b-121">application/json;odata=verbose</span></span>|


## <a name="response"></a><span data-ttu-id="d6c9b-122">응답</span><span class="sxs-lookup"><span data-stu-id="d6c9b-122">Response</span></span>

| <span data-ttu-id="d6c9b-123">이름</span><span class="sxs-lookup"><span data-stu-id="d6c9b-123">Name</span></span>   | <span data-ttu-id="d6c9b-124">유형</span><span class="sxs-lookup"><span data-stu-id="d6c9b-124">Type</span></span>  | <span data-ttu-id="d6c9b-125">설명</span><span class="sxs-lookup"><span data-stu-id="d6c9b-125">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="d6c9b-126">200 OK</span><span class="sxs-lookup"><span data-stu-id="d6c9b-126">200 OK</span></span>| |<span data-ttu-id="d6c9b-127">성공</span><span class="sxs-lookup"><span data-stu-id="d6c9b-127">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="d6c9b-128">예제</span><span class="sxs-lookup"><span data-stu-id="d6c9b-128">Examples</span></span>

### <a name="get-information-about-the-contracts-model-and-primed-document-library-in-the-repository-site"></a><span data-ttu-id="d6c9b-129">리포지토리 사이트에서 계약 모델 및 기본 문서 라이브러리에 대한 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="d6c9b-129">Get information about the contracts model and primed document library in the repository site</span></span>

<span data-ttu-id="d6c9b-130">이 샘플에서 Contoso 계약 문서 이해 모델의 ID는 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`입니다.</span><span class="sxs-lookup"><span data-stu-id="d6c9b-130">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="d6c9b-131">샘플 요청</span><span class="sxs-lookup"><span data-stu-id="d6c9b-131">Sample request</span></span>

```HTTP
GET /sites/TestCC/_api/machinelearning/publications/getbymodeluniqueid('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc') HTTP/1.1
```
#### <a name="sample-response"></a><span data-ttu-id="d6c9b-132">샘플 응답</span><span class="sxs-lookup"><span data-stu-id="d6c9b-132">Sample response</span></span>

<span data-ttu-id="d6c9b-133">**상태 코드:** 200</span><span class="sxs-lookup"><span data-stu-id="d6c9b-133">**Status code:** 200</span></span>

```JSON
{
    "@odata.context": "https://contoso.sharepoint.com/sites/TestCC/_api/$metadata#publications",
    "value": [
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com/sites/repository /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,94\"",
            "@odata.editLink": " https://contoso.sharepoint.com/sites/TestCC /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-04-27T03:05:25Z",
            "CreatedBy": "i:0#.f|membership|meganb@contoso.com",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 26,
            "ModelId": 16,
            "ModelName": "contosocontract.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T17:56:42Z",
            "ModifiedBy": "i:0#.f|membership|joedoe@contoso.com",
            "ObjectId": "01ZBWEM5FZRILGLXTEB5CZ2NNNSCTWBJMQ",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
            "TargetLibraryUrl": " https://contoso.sharepoint.com/sites/repository/contracts",
            "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository",
            "TargetWebServerRelativeUrl": "/sites/repository",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        },
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,101\"",
            "@odata.editLink": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-01-27T03:17:44Z",
            "CreatedBy": "i:0#.f|membership|esherman@contoso.com ",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 27,
            "ModelId": 16,
            "ModelName": "dispositions.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T23:17:46Z",
            "ModifiedBy": "i:0#.f|membership|esherman@contoso.com ",
            "ObjectId": "01ZBWEM5B3ERSZK4PAARGLFZ7JP6GMXG2R",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/legal/dispositions",
            "TargetLibraryUrl": "https://contoso.sharepoint.com/sites/legal/dispositions",
            "TargetSiteUrl": " https://contoso.sharepoint.com/sites/legal",
            "TargetWebServerRelativeUrl": "/sites/legal",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="d6c9b-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6c9b-134">See also</span></span>

[<span data-ttu-id="d6c9b-135">Syntex 문서 이해 모델 REST API</span><span class="sxs-lookup"><span data-stu-id="d6c9b-135">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
