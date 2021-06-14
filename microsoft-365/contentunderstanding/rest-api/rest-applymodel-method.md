---
title: 모델 적용
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
ms.openlocfilehash: d4cadad3c45dd7af0cdaeb4e1b367426289db870
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904354"
---
# <a name="apply-model"></a><span data-ttu-id="5276b-103">모델 적용</span><span class="sxs-lookup"><span data-stu-id="5276b-103">Apply model</span></span>

<span data-ttu-id="5276b-104">학습된 문서 이해 모델을 하나 이상의 라이브러리에 적용하거나 동기화합니다([예제](rest-applymodel-method.md#examples)참조).</span><span class="sxs-lookup"><span data-stu-id="5276b-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="5276b-105">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="5276b-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="5276b-106">URI 매개 변수</span><span class="sxs-lookup"><span data-stu-id="5276b-106">URI parameters</span></span>

<span data-ttu-id="5276b-107">없음</span><span class="sxs-lookup"><span data-stu-id="5276b-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="5276b-108">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="5276b-108">Request headers</span></span>

| <span data-ttu-id="5276b-109">헤더</span><span class="sxs-lookup"><span data-stu-id="5276b-109">Header</span></span> | <span data-ttu-id="5276b-110">값</span><span class="sxs-lookup"><span data-stu-id="5276b-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="5276b-111">수락</span><span class="sxs-lookup"><span data-stu-id="5276b-111">Accept</span></span>|<span data-ttu-id="5276b-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="5276b-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="5276b-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="5276b-113">Content-Type</span></span>|<span data-ttu-id="5276b-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="5276b-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="5276b-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="5276b-115">x-requestdigest</span></span>|<span data-ttu-id="5276b-116">현재 사이트에 적합한 다이제스트입니다.</span><span class="sxs-lookup"><span data-stu-id="5276b-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="5276b-117">요청 본문</span><span class="sxs-lookup"><span data-stu-id="5276b-117">Request body</span></span>

| <span data-ttu-id="5276b-118">이름</span><span class="sxs-lookup"><span data-stu-id="5276b-118">Name</span></span> | <span data-ttu-id="5276b-119">필수</span><span class="sxs-lookup"><span data-stu-id="5276b-119">Required</span></span> | <span data-ttu-id="5276b-120">유형</span><span class="sxs-lookup"><span data-stu-id="5276b-120">Type</span></span> | <span data-ttu-id="5276b-121">설명</span><span class="sxs-lookup"><span data-stu-id="5276b-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="5276b-122">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="5276b-122">ModelUniqueId</span></span>|<span data-ttu-id="5276b-123">예</span><span class="sxs-lookup"><span data-stu-id="5276b-123">yes</span></span>|<span data-ttu-id="5276b-124">문자열</span><span class="sxs-lookup"><span data-stu-id="5276b-124">string</span></span>|<span data-ttu-id="5276b-125">모델 파일의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5276b-125">The unique ID of the model file.</span></span>|
<span data-ttu-id="5276b-126">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="5276b-126">TargetSiteUrl</span></span>|<span data-ttu-id="5276b-127">예</span><span class="sxs-lookup"><span data-stu-id="5276b-127">yes</span></span>|<span data-ttu-id="5276b-128">문자열</span><span class="sxs-lookup"><span data-stu-id="5276b-128">string</span></span>|<span data-ttu-id="5276b-129">대상 라이브러리 사이트의 전체 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="5276b-129">The full URL of the target library site.</span></span>|
<span data-ttu-id="5276b-130">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="5276b-130">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="5276b-131">예</span><span class="sxs-lookup"><span data-stu-id="5276b-131">yes</span></span>|<span data-ttu-id="5276b-132">문자열</span><span class="sxs-lookup"><span data-stu-id="5276b-132">string</span></span>|<span data-ttu-id="5276b-133">대상 라이브러리에 대한 웹의 서버 상대 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="5276b-133">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="5276b-134">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="5276b-134">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="5276b-135">예</span><span class="sxs-lookup"><span data-stu-id="5276b-135">yes</span></span>|<span data-ttu-id="5276b-136">문자열</span><span class="sxs-lookup"><span data-stu-id="5276b-136">string</span></span>|<span data-ttu-id="5276b-137">대상 라이브러리의 서버 상대 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="5276b-137">The server relative URL of the target library.</span></span>|
<span data-ttu-id="5276b-138">ViewOption</span><span class="sxs-lookup"><span data-stu-id="5276b-138">ViewOption</span></span>|<span data-ttu-id="5276b-139">아니요</span><span class="sxs-lookup"><span data-stu-id="5276b-139">no</span></span>|<span data-ttu-id="5276b-140">문자열</span><span class="sxs-lookup"><span data-stu-id="5276b-140">string</span></span>|<span data-ttu-id="5276b-141">새 모델 뷰를 라이브러리 기본값으로 설정할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5276b-141">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="5276b-142">응답</span><span class="sxs-lookup"><span data-stu-id="5276b-142">Response</span></span>

| <span data-ttu-id="5276b-143">이름</span><span class="sxs-lookup"><span data-stu-id="5276b-143">Name</span></span>   | <span data-ttu-id="5276b-144">유형</span><span class="sxs-lookup"><span data-stu-id="5276b-144">Type</span></span>  | <span data-ttu-id="5276b-145">설명</span><span class="sxs-lookup"><span data-stu-id="5276b-145">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="5276b-146">200 OK</span><span class="sxs-lookup"><span data-stu-id="5276b-146">200 OK</span></span>| |<span data-ttu-id="5276b-147">성공</span><span class="sxs-lookup"><span data-stu-id="5276b-147">Success</span></span>|
|<span data-ttu-id="5276b-148">201 생성됨</span><span class="sxs-lookup"><span data-stu-id="5276b-148">201 Created</span></span>| |<span data-ttu-id="5276b-149">이 API는 여러 라이브러리에 모델 적용을 지원하므로 라이브러리 중 하나에 모델을 적용하는 데 오류가 있어도 201이 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5276b-149">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="5276b-150">응답 본문을 확인하여 모델이 지정된 모든 라이브러리에 성공적으로 적용되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5276b-150">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="5276b-151">자세한 내용은 [요청 본문](rest-applymodel-method.md#request-body)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5276b-151">See [Request body](rest-applymodel-method.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="5276b-152">예제</span><span class="sxs-lookup"><span data-stu-id="5276b-152">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="5276b-153">리포지토리 사이트의 계약 문서 라이브러리에 모델 적용</span><span class="sxs-lookup"><span data-stu-id="5276b-153">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="5276b-154">이 샘플에서는 Contoso 계약 문서 이해 모델의 ID가 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`입니다.</span><span class="sxs-lookup"><span data-stu-id="5276b-154">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="5276b-155">샘플 요청</span><span class="sxs-lookup"><span data-stu-id="5276b-155">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="5276b-156">샘플 응답</span><span class="sxs-lookup"><span data-stu-id="5276b-156">Sample response</span></span>

<span data-ttu-id="5276b-157">응답에서 TotalFailures 및 TotalSuccesses는 지정된 라이브러리에 적용되는 모델의 실패 및 성공 횟수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5276b-157">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="5276b-158">**상태 코드:** 200</span><span class="sxs-lookup"><span data-stu-id="5276b-158">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5276b-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5276b-159">See also</span></span>

[<span data-ttu-id="5276b-160">구문 문서 이해 모델 REST API</span><span class="sxs-lookup"><span data-stu-id="5276b-160">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
