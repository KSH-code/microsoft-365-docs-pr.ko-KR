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
# <a name="batchdelete"></a><span data-ttu-id="6ccbd-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="6ccbd-103">BatchDelete</span></span>

<span data-ttu-id="6ccbd-104">하나 이상의 라이브러리에서 적용된 문서 이해 모델을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbd-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="6ccbd-105">모델을 삭제하려면 먼저 모든 라이브러리에서 모델을 제거해야 합니다( [예제](rest-batchdelete-method.md#examples)참조).</span><span class="sxs-lookup"><span data-stu-id="6ccbd-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="6ccbd-106">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="6ccbd-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="6ccbd-107">URI 매개 변수</span><span class="sxs-lookup"><span data-stu-id="6ccbd-107">URI parameters</span></span>

<span data-ttu-id="6ccbd-108">없음</span><span class="sxs-lookup"><span data-stu-id="6ccbd-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="6ccbd-109">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="6ccbd-109">Request headers</span></span>

| <span data-ttu-id="6ccbd-110">헤더</span><span class="sxs-lookup"><span data-stu-id="6ccbd-110">Header</span></span> | <span data-ttu-id="6ccbd-111">값</span><span class="sxs-lookup"><span data-stu-id="6ccbd-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="6ccbd-112">수락</span><span class="sxs-lookup"><span data-stu-id="6ccbd-112">Accept</span></span>|<span data-ttu-id="6ccbd-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="6ccbd-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="6ccbd-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="6ccbd-114">Content-Type</span></span>|<span data-ttu-id="6ccbd-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="6ccbd-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="6ccbd-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="6ccbd-116">x-requestdigest</span></span>|<span data-ttu-id="6ccbd-117">현재 사이트에 적합한 다이제스트입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbd-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="6ccbd-118">요청 본문</span><span class="sxs-lookup"><span data-stu-id="6ccbd-118">Request body</span></span>

| <span data-ttu-id="6ccbd-119">이름</span><span class="sxs-lookup"><span data-stu-id="6ccbd-119">Name</span></span> | <span data-ttu-id="6ccbd-120">필수</span><span class="sxs-lookup"><span data-stu-id="6ccbd-120">Required</span></span> | <span data-ttu-id="6ccbd-121">유형</span><span class="sxs-lookup"><span data-stu-id="6ccbd-121">Type</span></span> | <span data-ttu-id="6ccbd-122">설명</span><span class="sxs-lookup"><span data-stu-id="6ccbd-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="6ccbd-123">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="6ccbd-123">ModelUniqueId</span></span>|<span data-ttu-id="6ccbd-124">예</span><span class="sxs-lookup"><span data-stu-id="6ccbd-124">yes</span></span>|<span data-ttu-id="6ccbd-125">문자열</span><span class="sxs-lookup"><span data-stu-id="6ccbd-125">string</span></span>|<span data-ttu-id="6ccbd-126">모델 파일의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbd-126">The unique ID of the model file.</span></span>|
<span data-ttu-id="6ccbd-127">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="6ccbd-127">TargetSiteUrl</span></span>|<span data-ttu-id="6ccbd-128">예</span><span class="sxs-lookup"><span data-stu-id="6ccbd-128">yes</span></span>|<span data-ttu-id="6ccbd-129">문자열</span><span class="sxs-lookup"><span data-stu-id="6ccbd-129">string</span></span>|<span data-ttu-id="6ccbd-130">대상 라이브러리 사이트의 전체 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbd-130">The full URL of the target library site.</span></span>|
<span data-ttu-id="6ccbd-131">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="6ccbd-131">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="6ccbd-132">예</span><span class="sxs-lookup"><span data-stu-id="6ccbd-132">yes</span></span>|<span data-ttu-id="6ccbd-133">문자열</span><span class="sxs-lookup"><span data-stu-id="6ccbd-133">string</span></span>|<span data-ttu-id="6ccbd-134">대상 라이브러리에 대한 웹의 서버 상대 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbd-134">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="6ccbd-135">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="6ccbd-135">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="6ccbd-136">예</span><span class="sxs-lookup"><span data-stu-id="6ccbd-136">yes</span></span>|<span data-ttu-id="6ccbd-137">문자열</span><span class="sxs-lookup"><span data-stu-id="6ccbd-137">string</span></span>|<span data-ttu-id="6ccbd-138">대상 라이브러리의 서버 상대 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbd-138">The server relative URL of the target library.</span></span>|
<span data-ttu-id="6ccbd-139">ViewOption</span><span class="sxs-lookup"><span data-stu-id="6ccbd-139">ViewOption</span></span>|<span data-ttu-id="6ccbd-140">아니요</span><span class="sxs-lookup"><span data-stu-id="6ccbd-140">no</span></span>|<span data-ttu-id="6ccbd-141">문자열</span><span class="sxs-lookup"><span data-stu-id="6ccbd-141">string</span></span>|<span data-ttu-id="6ccbd-142">새 모델 뷰를 라이브러리 기본값으로 설정할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbd-142">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="6ccbd-143">응답</span><span class="sxs-lookup"><span data-stu-id="6ccbd-143">Response</span></span>

| <span data-ttu-id="6ccbd-144">이름</span><span class="sxs-lookup"><span data-stu-id="6ccbd-144">Name</span></span>   | <span data-ttu-id="6ccbd-145">유형</span><span class="sxs-lookup"><span data-stu-id="6ccbd-145">Type</span></span>  | <span data-ttu-id="6ccbd-146">설명</span><span class="sxs-lookup"><span data-stu-id="6ccbd-146">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="6ccbd-147">200 OK</span><span class="sxs-lookup"><span data-stu-id="6ccbd-147">200 OK</span></span>| |<span data-ttu-id="6ccbd-148">성공</span><span class="sxs-lookup"><span data-stu-id="6ccbd-148">Success</span></span>|


## <a name="examples"></a><span data-ttu-id="6ccbd-149">예제</span><span class="sxs-lookup"><span data-stu-id="6ccbd-149">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="6ccbd-150">리포지토리 사이트의 계약 문서 라이브러리에서 모델 제거</span><span class="sxs-lookup"><span data-stu-id="6ccbd-150">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="6ccbd-151">이 샘플에서는 Contoso 계약 문서 이해 모델의 ID가 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbd-151">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="6ccbd-152">샘플 요청</span><span class="sxs-lookup"><span data-stu-id="6ccbd-152">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="6ccbd-153">샘플 응답</span><span class="sxs-lookup"><span data-stu-id="6ccbd-153">Sample response</span></span>

<span data-ttu-id="6ccbd-154">응답에서 TotalFailures 및 TotalSuccesses는 지정된 라이브러리에 적용되는 모델의 실패 및 성공 횟수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6ccbd-154">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="6ccbd-155">**상태 코드:** 200</span><span class="sxs-lookup"><span data-stu-id="6ccbd-155">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6ccbd-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ccbd-156">See also</span></span>

[<span data-ttu-id="6ccbd-157">Syntex 문서 이해 모델 REST API</span><span class="sxs-lookup"><span data-stu-id="6ccbd-157">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
