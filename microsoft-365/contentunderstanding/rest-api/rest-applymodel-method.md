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
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286540"
---
# <a name="batch-apply-model"></a><span data-ttu-id="4e63c-103">모델 일괄 적용</span><span class="sxs-lookup"><span data-stu-id="4e63c-103">Batch Apply model</span></span>

<span data-ttu-id="4e63c-104">학습된 문서 이해 모델을 하나 이상의 라이브러리에 적용하거나 동기화합니다([예제](rest-applymodel-method.md#examples)참조).</span><span class="sxs-lookup"><span data-stu-id="4e63c-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="4e63c-105">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="4e63c-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="4e63c-106">URI 매개 변수</span><span class="sxs-lookup"><span data-stu-id="4e63c-106">URI parameters</span></span>

<span data-ttu-id="4e63c-107">없음</span><span class="sxs-lookup"><span data-stu-id="4e63c-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="4e63c-108">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="4e63c-108">Request headers</span></span>

| <span data-ttu-id="4e63c-109">헤더</span><span class="sxs-lookup"><span data-stu-id="4e63c-109">Header</span></span> | <span data-ttu-id="4e63c-110">값</span><span class="sxs-lookup"><span data-stu-id="4e63c-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="4e63c-111">수락</span><span class="sxs-lookup"><span data-stu-id="4e63c-111">Accept</span></span>|<span data-ttu-id="4e63c-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="4e63c-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="4e63c-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="4e63c-113">Content-Type</span></span>|<span data-ttu-id="4e63c-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="4e63c-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="4e63c-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="4e63c-115">x-requestdigest</span></span>|<span data-ttu-id="4e63c-116">현재 사이트에 적합한 다이제스트입니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="4e63c-117">요청 본문</span><span class="sxs-lookup"><span data-stu-id="4e63c-117">Request body</span></span>

| <span data-ttu-id="4e63c-118">이름</span><span class="sxs-lookup"><span data-stu-id="4e63c-118">Name</span></span> | <span data-ttu-id="4e63c-119">필수</span><span class="sxs-lookup"><span data-stu-id="4e63c-119">Required</span></span> | <span data-ttu-id="4e63c-120">유형</span><span class="sxs-lookup"><span data-stu-id="4e63c-120">Type</span></span> | <span data-ttu-id="4e63c-121">설명</span><span class="sxs-lookup"><span data-stu-id="4e63c-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="4e63c-122">__metadata</span><span class="sxs-lookup"><span data-stu-id="4e63c-122">__metadata</span></span>|<span data-ttu-id="4e63c-123">예</span><span class="sxs-lookup"><span data-stu-id="4e63c-123">yes</span></span>|<span data-ttu-id="4e63c-124">문자열</span><span class="sxs-lookup"><span data-stu-id="4e63c-124">string</span></span>|<span data-ttu-id="4e63c-125">SPO에 개체 메타를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-125">Set the object meta on the SPO.</span></span> <span data-ttu-id="4e63c-126">항상 {“type”: “Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData”} 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-126">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.</span></span>|
|<span data-ttu-id="4e63c-127">Publications</span><span class="sxs-lookup"><span data-stu-id="4e63c-127">Publications</span></span>|<span data-ttu-id="4e63c-128">예</span><span class="sxs-lookup"><span data-stu-id="4e63c-128">yes</span></span>|<span data-ttu-id="4e63c-129">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="4e63c-129">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="4e63c-130">각각 모델 및 대상 문서 라이브러리를 지정하는 MachineLearningPublicationEntityData의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-130">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="4e63c-131">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="4e63c-131">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="4e63c-132">이름</span><span class="sxs-lookup"><span data-stu-id="4e63c-132">Name</span></span> | <span data-ttu-id="4e63c-133">필수</span><span class="sxs-lookup"><span data-stu-id="4e63c-133">Required</span></span> | <span data-ttu-id="4e63c-134">유형</span><span class="sxs-lookup"><span data-stu-id="4e63c-134">Type</span></span> | <span data-ttu-id="4e63c-135">설명</span><span class="sxs-lookup"><span data-stu-id="4e63c-135">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="4e63c-136">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="4e63c-136">ModelUniqueId</span></span>|<span data-ttu-id="4e63c-137">예</span><span class="sxs-lookup"><span data-stu-id="4e63c-137">yes</span></span>|<span data-ttu-id="4e63c-138">문자열</span><span class="sxs-lookup"><span data-stu-id="4e63c-138">string</span></span>|<span data-ttu-id="4e63c-139">모델 파일의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-139">The unique ID of the model file.</span></span>|
|<span data-ttu-id="4e63c-140">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="4e63c-140">TargetSiteUrl</span></span>|<span data-ttu-id="4e63c-141">예</span><span class="sxs-lookup"><span data-stu-id="4e63c-141">yes</span></span>|<span data-ttu-id="4e63c-142">문자열</span><span class="sxs-lookup"><span data-stu-id="4e63c-142">string</span></span>|<span data-ttu-id="4e63c-143">대상 라이브러리 사이트의 전체 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-143">The full URL of the target library site.</span></span>|
|<span data-ttu-id="4e63c-144">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="4e63c-144">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="4e63c-145">예</span><span class="sxs-lookup"><span data-stu-id="4e63c-145">yes</span></span>|<span data-ttu-id="4e63c-146">문자열</span><span class="sxs-lookup"><span data-stu-id="4e63c-146">string</span></span>|<span data-ttu-id="4e63c-147">대상 라이브러리에 대한 웹의 서버 상대 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-147">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="4e63c-148">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="4e63c-148">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="4e63c-149">예</span><span class="sxs-lookup"><span data-stu-id="4e63c-149">yes</span></span>|<span data-ttu-id="4e63c-150">문자열</span><span class="sxs-lookup"><span data-stu-id="4e63c-150">string</span></span>|<span data-ttu-id="4e63c-151">대상 라이브러리의 서버 상대 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-151">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="4e63c-152">ViewOption</span><span class="sxs-lookup"><span data-stu-id="4e63c-152">ViewOption</span></span>|<span data-ttu-id="4e63c-153">아니요</span><span class="sxs-lookup"><span data-stu-id="4e63c-153">no</span></span>|<span data-ttu-id="4e63c-154">문자열</span><span class="sxs-lookup"><span data-stu-id="4e63c-154">string</span></span>|<span data-ttu-id="4e63c-155">새 모델 뷰를 라이브러리 기본값으로 설정할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-155">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="4e63c-156">응답</span><span class="sxs-lookup"><span data-stu-id="4e63c-156">Response</span></span>

| <span data-ttu-id="4e63c-157">이름</span><span class="sxs-lookup"><span data-stu-id="4e63c-157">Name</span></span>   | <span data-ttu-id="4e63c-158">유형</span><span class="sxs-lookup"><span data-stu-id="4e63c-158">Type</span></span>  | <span data-ttu-id="4e63c-159">설명</span><span class="sxs-lookup"><span data-stu-id="4e63c-159">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="4e63c-160">201 생성됨</span><span class="sxs-lookup"><span data-stu-id="4e63c-160">201 Created</span></span>||<span data-ttu-id="4e63c-p102">다중 문서 라이브러리에 모델을 적용하도록 지원하는 사용자 지정 API입니다. 부분적으로 성공하는 경우에도 생성된 201이 반환될 수 있으며, 호출자는 응답 본문을 검사하여 모델이 문서 라이브러리에 성공적으로 적용되었는지 파악해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-p102">This is a customized API to support applying a model to multi document libraries. In the case of partial success, 201 created could still be returned and the caller needs to inspect the response body to understand if the model has been successfully applied to a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="4e63c-163">응답 본문</span><span class="sxs-lookup"><span data-stu-id="4e63c-163">Response Body</span></span>

| <span data-ttu-id="4e63c-164">이름</span><span class="sxs-lookup"><span data-stu-id="4e63c-164">Name</span></span>   | <span data-ttu-id="4e63c-165">유형</span><span class="sxs-lookup"><span data-stu-id="4e63c-165">Type</span></span>  | <span data-ttu-id="4e63c-166">설명</span><span class="sxs-lookup"><span data-stu-id="4e63c-166">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="4e63c-167">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="4e63c-167">TotalSuccesses</span></span>|<span data-ttu-id="4e63c-168">int</span><span class="sxs-lookup"><span data-stu-id="4e63c-168">int</span></span>|<span data-ttu-id="4e63c-169">문서 라이브러리에 성공적으로 적용된 모델의 총수입니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-169">The total number of a model being successfully applied to a document library.</span></span>|
|<span data-ttu-id="4e63c-170">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="4e63c-170">TotalFailures</span></span>|<span data-ttu-id="4e63c-171">int</span><span class="sxs-lookup"><span data-stu-id="4e63c-171">int</span></span>|<span data-ttu-id="4e63c-172">문서 라이브러리에 적용되지 못한 모델의 총수입니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-172">The total number of a model failing to be applied to a document library.</span></span>|
|<span data-ttu-id="4e63c-173">세부 정보</span><span class="sxs-lookup"><span data-stu-id="4e63c-173">Details</span></span>|<span data-ttu-id="4e63c-174">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="4e63c-174">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="4e63c-175">각각 문서 라이브러리에 모델을 적용한 자세한 결과를 지정하는 MachineLearningPublicationResult의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-175">The collection of MachineLearningPublicationResult each of which specifies the detailed result of applying the model to the document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="4e63c-176">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="4e63c-176">MachineLearningPublicationResult</span></span>

| <span data-ttu-id="4e63c-177">이름</span><span class="sxs-lookup"><span data-stu-id="4e63c-177">Name</span></span>   | <span data-ttu-id="4e63c-178">유형</span><span class="sxs-lookup"><span data-stu-id="4e63c-178">Type</span></span>  | <span data-ttu-id="4e63c-179">설명</span><span class="sxs-lookup"><span data-stu-id="4e63c-179">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="4e63c-180">StatusCode</span><span class="sxs-lookup"><span data-stu-id="4e63c-180">StatusCode</span></span>|<span data-ttu-id="4e63c-181">int</span><span class="sxs-lookup"><span data-stu-id="4e63c-181">int</span></span>|<span data-ttu-id="4e63c-182">HTTP 상태 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-182">The HTTP status code.</span></span>|
|<span data-ttu-id="4e63c-183">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="4e63c-183">ErrorMessage</span></span>|<span data-ttu-id="4e63c-184">문자열</span><span class="sxs-lookup"><span data-stu-id="4e63c-184">string</span></span>|<span data-ttu-id="4e63c-185">문서 라이브러리에 모델을 적용할 때 무엇이 잘못되었는지 알려 주는 오류 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-185">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="4e63c-186">Publication</span><span class="sxs-lookup"><span data-stu-id="4e63c-186">Publication</span></span>|<span data-ttu-id="4e63c-187">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="4e63c-187">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="4e63c-188">모델 정보 및 대상 문서 라이브러리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-188">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="4e63c-189">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="4e63c-189">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="4e63c-190">이름</span><span class="sxs-lookup"><span data-stu-id="4e63c-190">Name</span></span> | <span data-ttu-id="4e63c-191">유형</span><span class="sxs-lookup"><span data-stu-id="4e63c-191">Type</span></span> | <span data-ttu-id="4e63c-192">설명</span><span class="sxs-lookup"><span data-stu-id="4e63c-192">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="4e63c-193">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="4e63c-193">ModelUniqueId</span></span>|<span data-ttu-id="4e63c-194">문자열</span><span class="sxs-lookup"><span data-stu-id="4e63c-194">string</span></span>|<span data-ttu-id="4e63c-195">모델 파일의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-195">The unique ID of the model file.</span></span>|
|<span data-ttu-id="4e63c-196">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="4e63c-196">TargetSiteUrl</span></span>|<span data-ttu-id="4e63c-197">문자열</span><span class="sxs-lookup"><span data-stu-id="4e63c-197">string</span></span>|<span data-ttu-id="4e63c-198">대상 라이브러리 사이트의 전체 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-198">The full URL of the target library site.</span></span>|
|<span data-ttu-id="4e63c-199">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="4e63c-199">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="4e63c-200">문자열</span><span class="sxs-lookup"><span data-stu-id="4e63c-200">string</span></span>|<span data-ttu-id="4e63c-201">대상 라이브러리에 대한 웹의 서버 상대 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-201">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="4e63c-202">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="4e63c-202">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="4e63c-203">문자열</span><span class="sxs-lookup"><span data-stu-id="4e63c-203">string</span></span>|<span data-ttu-id="4e63c-204">대상 라이브러리의 서버 상대 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-204">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="4e63c-205">예제</span><span class="sxs-lookup"><span data-stu-id="4e63c-205">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="4e63c-206">리포지토리 사이트의 계약 문서 라이브러리에 모델 적용</span><span class="sxs-lookup"><span data-stu-id="4e63c-206">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="4e63c-207">이 샘플에서는 Contoso 계약 문서 이해 모델의 ID가 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`입니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-207">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="4e63c-208">샘플 요청</span><span class="sxs-lookup"><span data-stu-id="4e63c-208">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="4e63c-209">샘플 응답</span><span class="sxs-lookup"><span data-stu-id="4e63c-209">Sample response</span></span>

<span data-ttu-id="4e63c-210">응답 내 TotalFailures 및 TotalSuccesses는 지정된 라이브러리에 모델을 적용하지 못한 횟수와 성공적으로 적용한 횟수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4e63c-210">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="4e63c-211">**상태 코드:** 201</span><span class="sxs-lookup"><span data-stu-id="4e63c-211">**Status code:** 201</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4e63c-212">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e63c-212">See also</span></span>

[<span data-ttu-id="4e63c-213">Syntex 문서 이해 모델 REST API</span><span class="sxs-lookup"><span data-stu-id="4e63c-213">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
