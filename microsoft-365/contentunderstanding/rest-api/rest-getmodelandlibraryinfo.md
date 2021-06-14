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
ms.openlocfilehash: 6cd61364ed3b360ef235aaba21a2735002fe481e
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904301"
---
# <a name="get-model-and-library-information"></a><span data-ttu-id="33a53-103">모델 및 라이브러리 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="33a53-103">Get model and library information</span></span>

<span data-ttu-id="33a53-104">모델 및 모델이 적용된 라이브러리에 대한 정보를 가져옵니다([예제](rest-getmodelandlibraryinfo.md#examples) 참조).</span><span class="sxs-lookup"><span data-stu-id="33a53-104">Gets information about a model and the library where it has been applied (see [example](rest-getmodelandlibraryinfo.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="33a53-105">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="33a53-105">HTTP request</span></span>

```HTTP
GET /_api/machinelearning/publications/getbyuniqueid(‘{modelUniqueId}’) HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="33a53-106">URI 매개 변수</span><span class="sxs-lookup"><span data-stu-id="33a53-106">URI parameters</span></span>

| <span data-ttu-id="33a53-107">이름</span><span class="sxs-lookup"><span data-stu-id="33a53-107">Name</span></span> | <span data-ttu-id="33a53-108">In</span><span class="sxs-lookup"><span data-stu-id="33a53-108">In</span></span> | <span data-ttu-id="33a53-109">필수</span><span class="sxs-lookup"><span data-stu-id="33a53-109">Required</span></span> | <span data-ttu-id="33a53-110">유형</span><span class="sxs-lookup"><span data-stu-id="33a53-110">Type</span></span> | <span data-ttu-id="33a53-111">설명</span><span class="sxs-lookup"><span data-stu-id="33a53-111">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="33a53-112">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="33a53-112">ModelUniqueId</span></span>|<span data-ttu-id="33a53-113">쿼리</span><span class="sxs-lookup"><span data-stu-id="33a53-113">query</span></span>|<span data-ttu-id="33a53-114">True</span><span class="sxs-lookup"><span data-stu-id="33a53-114">True</span></span>|<span data-ttu-id="33a53-115">GUID</span><span class="sxs-lookup"><span data-stu-id="33a53-115">GUID</span></span>|<span data-ttu-id="33a53-116">모델 파일의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="33a53-116">The unique id of the model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="33a53-117">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="33a53-117">Request headers</span></span>

| <span data-ttu-id="33a53-118">헤더</span><span class="sxs-lookup"><span data-stu-id="33a53-118">Header</span></span> | <span data-ttu-id="33a53-119">값</span><span class="sxs-lookup"><span data-stu-id="33a53-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="33a53-120">수락</span><span class="sxs-lookup"><span data-stu-id="33a53-120">Accept</span></span>|<span data-ttu-id="33a53-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="33a53-121">application/json;odata=verbose</span></span>|


## <a name="request-body"></a><span data-ttu-id="33a53-122">요청 본문</span><span class="sxs-lookup"><span data-stu-id="33a53-122">Request body</span></span>

| <span data-ttu-id="33a53-123">이름</span><span class="sxs-lookup"><span data-stu-id="33a53-123">Name</span></span> | <span data-ttu-id="33a53-124">필수</span><span class="sxs-lookup"><span data-stu-id="33a53-124">Required</span></span> | <span data-ttu-id="33a53-125">유형</span><span class="sxs-lookup"><span data-stu-id="33a53-125">Type</span></span> | <span data-ttu-id="33a53-126">설명</span><span class="sxs-lookup"><span data-stu-id="33a53-126">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="33a53-127">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="33a53-127">ModelUniqueId</span></span>|<span data-ttu-id="33a53-128">예</span><span class="sxs-lookup"><span data-stu-id="33a53-128">yes</span></span>|<span data-ttu-id="33a53-129">문자열</span><span class="sxs-lookup"><span data-stu-id="33a53-129">string</span></span>|<span data-ttu-id="33a53-130">모델 파일의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="33a53-130">The unique ID of the model file.</span></span>|
|<span data-ttu-id="33a53-131">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="33a53-131">TargetSiteUrl</span></span>|<span data-ttu-id="33a53-132">예</span><span class="sxs-lookup"><span data-stu-id="33a53-132">yes</span></span>|<span data-ttu-id="33a53-133">문자열</span><span class="sxs-lookup"><span data-stu-id="33a53-133">string</span></span>|<span data-ttu-id="33a53-134">대상 라이브러리 사이트의 전체 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="33a53-134">The full URL of the target library site.</span></span>|
|<span data-ttu-id="33a53-135">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="33a53-135">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="33a53-136">예</span><span class="sxs-lookup"><span data-stu-id="33a53-136">yes</span></span>|<span data-ttu-id="33a53-137">문자열</span><span class="sxs-lookup"><span data-stu-id="33a53-137">string</span></span>|<span data-ttu-id="33a53-138">대상 라이브러리에 대한 웹의 서버 상대 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="33a53-138">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="33a53-139">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="33a53-139">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="33a53-140">예</span><span class="sxs-lookup"><span data-stu-id="33a53-140">yes</span></span>|<span data-ttu-id="33a53-141">문자열</span><span class="sxs-lookup"><span data-stu-id="33a53-141">string</span></span>|<span data-ttu-id="33a53-142">대상 라이브러리의 서버 상대 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="33a53-142">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="33a53-143">TargetLibraryRemoved</span><span class="sxs-lookup"><span data-stu-id="33a53-143">TargetLibraryRemoved</span></span>|<span data-ttu-id="33a53-144">예</span><span class="sxs-lookup"><span data-stu-id="33a53-144">yes</span></span>|<span data-ttu-id="33a53-145">int</span><span class="sxs-lookup"><span data-stu-id="33a53-145">int</span></span>|<span data-ttu-id="33a53-146">대상 라이브러리가 제거되었는지 여부를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="33a53-146">The flag that indicates if the target library has been removed or not.</span></span>|

## <a name="response"></a><span data-ttu-id="33a53-147">응답</span><span class="sxs-lookup"><span data-stu-id="33a53-147">Response</span></span>

| <span data-ttu-id="33a53-148">이름</span><span class="sxs-lookup"><span data-stu-id="33a53-148">Name</span></span>   | <span data-ttu-id="33a53-149">유형</span><span class="sxs-lookup"><span data-stu-id="33a53-149">Type</span></span>  | <span data-ttu-id="33a53-150">설명</span><span class="sxs-lookup"><span data-stu-id="33a53-150">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="33a53-151">200 OK</span><span class="sxs-lookup"><span data-stu-id="33a53-151">200 OK</span></span>| |<span data-ttu-id="33a53-152">성공</span><span class="sxs-lookup"><span data-stu-id="33a53-152">Success</span></span>|
|<span data-ttu-id="33a53-153">201 생성됨</span><span class="sxs-lookup"><span data-stu-id="33a53-153">201 Created</span></span>| |<span data-ttu-id="33a53-154">이 API는 여러 라이브러리에 모델 적용을 지원하므로 라이브러리 중 하나에 모델을 적용하는 데 오류가 있어도 201이 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33a53-154">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="33a53-155">응답 본문을 확인하여 지정된 모든 라이브러리에 모델이 성공적으로 적용되었는지 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="33a53-155">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="33a53-156">자세한 내용은 [요청 본문](rest-getmodelandlibraryinfo.md#request-body)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33a53-156">See [Request body](rest-getmodelandlibraryinfo.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="33a53-157">예제</span><span class="sxs-lookup"><span data-stu-id="33a53-157">Examples</span></span>

### <a name="get-information-about-the-contracts-model-and-primed-document-library-in-the-repository-site"></a><span data-ttu-id="33a53-158">리포지토리 사이트에서 계약 모델 및 기본 문서 라이브러리에 대한 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="33a53-158">Get information about the contracts model and primed document library in the repository site</span></span>

<span data-ttu-id="33a53-159">이 샘플에서 Contoso 계약 문서 이해 모델의 ID는 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`입니다.</span><span class="sxs-lookup"><span data-stu-id="33a53-159">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="33a53-160">샘플 요청</span><span class="sxs-lookup"><span data-stu-id="33a53-160">Sample request</span></span>

```HTTP
GET /sites/TestCC/_api/machinelearning/publications/getbymodeluniqueid(‘{7645e69d-21fb-4a24-a17a-9bdfa7cb63dc}’) HTTP/1.1
```
#### <a name="sample-response"></a><span data-ttu-id="33a53-161">샘플 응답</span><span class="sxs-lookup"><span data-stu-id="33a53-161">Sample response</span></span>

<span data-ttu-id="33a53-162">**상태 코드:** 200</span><span class="sxs-lookup"><span data-stu-id="33a53-162">**Status code:** 200</span></span>

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
}```
```

## <a name="see-also"></a><span data-ttu-id="33a53-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33a53-163">See also</span></span>

[<span data-ttu-id="33a53-164">Syntex 문서 이해 모델 REST API</span><span class="sxs-lookup"><span data-stu-id="33a53-164">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
