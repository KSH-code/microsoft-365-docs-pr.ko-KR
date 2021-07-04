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
ms.openlocfilehash: bbd3e496b50d3fddb31342fbc07d30984544e744
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287456"
---
# <a name="batchdelete"></a><span data-ttu-id="54ed0-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="54ed0-103">BatchDelete</span></span>

<span data-ttu-id="54ed0-104">하나 이상의 라이브러리에서 적용된 문서 이해 모델을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="54ed0-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="54ed0-105">모델을 삭제하려면 먼저 모든 라이브러리에서 모델을 제거해야 합니다( [예제](rest-batchdelete-method.md#examples)참조).</span><span class="sxs-lookup"><span data-stu-id="54ed0-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="54ed0-106">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="54ed0-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="54ed0-107">URI 매개 변수</span><span class="sxs-lookup"><span data-stu-id="54ed0-107">URI parameters</span></span>

<span data-ttu-id="54ed0-108">없음</span><span class="sxs-lookup"><span data-stu-id="54ed0-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="54ed0-109">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="54ed0-109">Request headers</span></span>

| <span data-ttu-id="54ed0-110">헤더</span><span class="sxs-lookup"><span data-stu-id="54ed0-110">Header</span></span> | <span data-ttu-id="54ed0-111">값</span><span class="sxs-lookup"><span data-stu-id="54ed0-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="54ed0-112">수락</span><span class="sxs-lookup"><span data-stu-id="54ed0-112">Accept</span></span>|<span data-ttu-id="54ed0-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="54ed0-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="54ed0-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="54ed0-114">Content-Type</span></span>|<span data-ttu-id="54ed0-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="54ed0-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="54ed0-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="54ed0-116">x-requestdigest</span></span>|<span data-ttu-id="54ed0-117">현재 사이트에 적합한 다이제스트입니다.</span><span class="sxs-lookup"><span data-stu-id="54ed0-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="54ed0-118">요청 본문</span><span class="sxs-lookup"><span data-stu-id="54ed0-118">Request body</span></span>

| <span data-ttu-id="54ed0-119">이름</span><span class="sxs-lookup"><span data-stu-id="54ed0-119">Name</span></span> | <span data-ttu-id="54ed0-120">필수</span><span class="sxs-lookup"><span data-stu-id="54ed0-120">Required</span></span> | <span data-ttu-id="54ed0-121">유형</span><span class="sxs-lookup"><span data-stu-id="54ed0-121">Type</span></span> | <span data-ttu-id="54ed0-122">설명</span><span class="sxs-lookup"><span data-stu-id="54ed0-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="54ed0-123">Publications</span><span class="sxs-lookup"><span data-stu-id="54ed0-123">Publications</span></span>|<span data-ttu-id="54ed0-124">예</span><span class="sxs-lookup"><span data-stu-id="54ed0-124">yes</span></span>|<span data-ttu-id="54ed0-125">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="54ed0-125">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="54ed0-126">각각 모델 및 대상 문서 라이브러리를 지정하는 MachineLearningPublicationEntityData의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="54ed0-126">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="54ed0-127">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="54ed0-127">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="54ed0-128">이름</span><span class="sxs-lookup"><span data-stu-id="54ed0-128">Name</span></span> | <span data-ttu-id="54ed0-129">필수</span><span class="sxs-lookup"><span data-stu-id="54ed0-129">Required</span></span> | <span data-ttu-id="54ed0-130">유형</span><span class="sxs-lookup"><span data-stu-id="54ed0-130">Type</span></span> | <span data-ttu-id="54ed0-131">설명</span><span class="sxs-lookup"><span data-stu-id="54ed0-131">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="54ed0-132">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="54ed0-132">ModelUniqueId</span></span>|<span data-ttu-id="54ed0-133">예</span><span class="sxs-lookup"><span data-stu-id="54ed0-133">yes</span></span>|<span data-ttu-id="54ed0-134">문자열</span><span class="sxs-lookup"><span data-stu-id="54ed0-134">string</span></span>|<span data-ttu-id="54ed0-135">모델 파일의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="54ed0-135">The unique ID of the model file.</span></span>|
|<span data-ttu-id="54ed0-136">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="54ed0-136">TargetSiteUrl</span></span>|<span data-ttu-id="54ed0-137">예</span><span class="sxs-lookup"><span data-stu-id="54ed0-137">yes</span></span>|<span data-ttu-id="54ed0-138">문자열</span><span class="sxs-lookup"><span data-stu-id="54ed0-138">string</span></span>|<span data-ttu-id="54ed0-139">대상 라이브러리 사이트의 전체 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="54ed0-139">The full URL of the target library site.</span></span>|
|<span data-ttu-id="54ed0-140">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="54ed0-140">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="54ed0-141">예</span><span class="sxs-lookup"><span data-stu-id="54ed0-141">yes</span></span>|<span data-ttu-id="54ed0-142">문자열</span><span class="sxs-lookup"><span data-stu-id="54ed0-142">string</span></span>|<span data-ttu-id="54ed0-143">대상 라이브러리에 대한 웹의 서버 상대 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="54ed0-143">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="54ed0-144">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="54ed0-144">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="54ed0-145">예</span><span class="sxs-lookup"><span data-stu-id="54ed0-145">yes</span></span>|<span data-ttu-id="54ed0-146">문자열</span><span class="sxs-lookup"><span data-stu-id="54ed0-146">string</span></span>|<span data-ttu-id="54ed0-147">대상 라이브러리의 서버 상대 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="54ed0-147">The server relative URL of the target library.</span></span>|

## <a name="response"></a><span data-ttu-id="54ed0-148">응답</span><span class="sxs-lookup"><span data-stu-id="54ed0-148">Response</span></span>

| <span data-ttu-id="54ed0-149">이름</span><span class="sxs-lookup"><span data-stu-id="54ed0-149">Name</span></span>   | <span data-ttu-id="54ed0-150">유형</span><span class="sxs-lookup"><span data-stu-id="54ed0-150">Type</span></span>  | <span data-ttu-id="54ed0-151">설명</span><span class="sxs-lookup"><span data-stu-id="54ed0-151">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="54ed0-152">200 OK</span><span class="sxs-lookup"><span data-stu-id="54ed0-152">200 OK</span></span>||<span data-ttu-id="54ed0-p102">다중 문서 라이브러리에서 모델을 제거하도록 지원하는 사용자 지정 API입니다. 부분적으로 성공하는 경우에도 200 OK가 반환될 수 있으며, 호출자는 응답 본문을 검사하여 모델이 문서 라이브러리에서 성공적으로 제거되었는지 파악해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54ed0-p102">This is a customized API to support removing a model from multi document libraries. In the case of partial success, 200 OK could still be returned and the caller needs to inspect the response body to understand if the model has been successfully removed from a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="54ed0-155">응답 본문</span><span class="sxs-lookup"><span data-stu-id="54ed0-155">Response Body</span></span>

| <span data-ttu-id="54ed0-156">이름</span><span class="sxs-lookup"><span data-stu-id="54ed0-156">Name</span></span>   | <span data-ttu-id="54ed0-157">유형</span><span class="sxs-lookup"><span data-stu-id="54ed0-157">Type</span></span>  | <span data-ttu-id="54ed0-158">설명</span><span class="sxs-lookup"><span data-stu-id="54ed0-158">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="54ed0-159">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="54ed0-159">TotalSuccesses</span></span>|<span data-ttu-id="54ed0-160">int</span><span class="sxs-lookup"><span data-stu-id="54ed0-160">int</span></span>|<span data-ttu-id="54ed0-161">문서 라이브러리에서 성공적으로 제거한 모델의 총수입니다.</span><span class="sxs-lookup"><span data-stu-id="54ed0-161">The total number of a model being successfully removed from a document library.</span></span>|
|<span data-ttu-id="54ed0-162">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="54ed0-162">TotalFailures</span></span>|<span data-ttu-id="54ed0-163">int</span><span class="sxs-lookup"><span data-stu-id="54ed0-163">int</span></span>|<span data-ttu-id="54ed0-164">문서 라이브러리에서 제거하지 못한 모델의 총수입니다.</span><span class="sxs-lookup"><span data-stu-id="54ed0-164">The total number of a model failing to be removed from a document library.</span></span>|
|<span data-ttu-id="54ed0-165">세부 정보</span><span class="sxs-lookup"><span data-stu-id="54ed0-165">Details</span></span>|<span data-ttu-id="54ed0-166">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="54ed0-166">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="54ed0-167">각각 문서 라이브러리에서 모델을 제거한 자세한 결과를 지정하는 MachineLearningPublicationResult의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="54ed0-167">The collection of MachineLearningPublicationResult each of which specifies the detailed result of removing the model from a document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="54ed0-168">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="54ed0-168">MachineLearningPublicationResult</span></span>

| <span data-ttu-id="54ed0-169">이름</span><span class="sxs-lookup"><span data-stu-id="54ed0-169">Name</span></span>   | <span data-ttu-id="54ed0-170">유형</span><span class="sxs-lookup"><span data-stu-id="54ed0-170">Type</span></span>  | <span data-ttu-id="54ed0-171">설명</span><span class="sxs-lookup"><span data-stu-id="54ed0-171">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="54ed0-172">StatusCode</span><span class="sxs-lookup"><span data-stu-id="54ed0-172">StatusCode</span></span>|<span data-ttu-id="54ed0-173">int</span><span class="sxs-lookup"><span data-stu-id="54ed0-173">int</span></span>|<span data-ttu-id="54ed0-174">HTTP 상태 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="54ed0-174">The HTTP status code.</span></span>|
|<span data-ttu-id="54ed0-175">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="54ed0-175">ErrorMessage</span></span>|<span data-ttu-id="54ed0-176">문자열</span><span class="sxs-lookup"><span data-stu-id="54ed0-176">string</span></span>|<span data-ttu-id="54ed0-177">문서 라이브러리에 모델을 적용할 때 무엇이 잘못되었는지 알려 주는 오류 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="54ed0-177">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="54ed0-178">Publication</span><span class="sxs-lookup"><span data-stu-id="54ed0-178">Publication</span></span>|<span data-ttu-id="54ed0-179">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="54ed0-179">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="54ed0-180">모델 정보 및 대상 문서 라이브러리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="54ed0-180">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="54ed0-181">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="54ed0-181">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="54ed0-182">이름</span><span class="sxs-lookup"><span data-stu-id="54ed0-182">Name</span></span> | <span data-ttu-id="54ed0-183">유형</span><span class="sxs-lookup"><span data-stu-id="54ed0-183">Type</span></span> | <span data-ttu-id="54ed0-184">설명</span><span class="sxs-lookup"><span data-stu-id="54ed0-184">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="54ed0-185">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="54ed0-185">ModelUniqueId</span></span>|<span data-ttu-id="54ed0-186">문자열</span><span class="sxs-lookup"><span data-stu-id="54ed0-186">string</span></span>|<span data-ttu-id="54ed0-187">모델 파일의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="54ed0-187">The unique ID of the model file.</span></span>|
|<span data-ttu-id="54ed0-188">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="54ed0-188">TargetSiteUrl</span></span>|<span data-ttu-id="54ed0-189">문자열</span><span class="sxs-lookup"><span data-stu-id="54ed0-189">string</span></span>|<span data-ttu-id="54ed0-190">대상 라이브러리 사이트의 전체 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="54ed0-190">The full URL of the target library site.</span></span>|
|<span data-ttu-id="54ed0-191">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="54ed0-191">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="54ed0-192">문자열</span><span class="sxs-lookup"><span data-stu-id="54ed0-192">string</span></span>|<span data-ttu-id="54ed0-193">대상 라이브러리에 대한 웹의 서버 상대 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="54ed0-193">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="54ed0-194">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="54ed0-194">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="54ed0-195">문자열</span><span class="sxs-lookup"><span data-stu-id="54ed0-195">string</span></span>|<span data-ttu-id="54ed0-196">대상 라이브러리의 서버 상대 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="54ed0-196">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="54ed0-197">예제</span><span class="sxs-lookup"><span data-stu-id="54ed0-197">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="54ed0-198">리포지토리 사이트의 계약 문서 라이브러리에서 모델 제거</span><span class="sxs-lookup"><span data-stu-id="54ed0-198">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="54ed0-199">이 샘플에서는 Contoso 계약 문서 이해 모델의 ID가 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`입니다.</span><span class="sxs-lookup"><span data-stu-id="54ed0-199">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="54ed0-200">샘플 요청</span><span class="sxs-lookup"><span data-stu-id="54ed0-200">Sample request</span></span>

```HTTP
{ 
    "publications": [ 
        { 
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc", 
            "TargetSiteUrl": "https://constco.sharepoint-df.com/sites/docsite", 
            "TargetWebServerRelativeUrl": "/sites/docsite ", 
            "TargetLibraryServerRelativeUrl": "/sites/dcocsite/joedcos" 
        } 
    ] 
} 
```

#### <a name="sample-response"></a><span data-ttu-id="54ed0-201">샘플 응답</span><span class="sxs-lookup"><span data-stu-id="54ed0-201">Sample response</span></span>

<span data-ttu-id="54ed0-202">응답 내 TotalFailures 및 TotalSuccesses는 지정된 라이브러리에서 모델을 제거하지 못한 횟수와 성공적으로 제거한 횟수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="54ed0-202">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being removed from the specified libraries.</span></span>

<span data-ttu-id="54ed0-203">**상태 코드:** 200</span><span class="sxs-lookup"><span data-stu-id="54ed0-203">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="54ed0-204">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54ed0-204">See also</span></span>

[<span data-ttu-id="54ed0-205">Syntex 문서 이해 모델 REST API</span><span class="sxs-lookup"><span data-stu-id="54ed0-205">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
