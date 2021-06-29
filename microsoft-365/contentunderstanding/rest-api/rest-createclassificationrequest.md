---
title: 분류 요청 만들기
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
description: REST API를 사용하여 학습된 문서 이해 모델을 사용하여 하나 이상의 파일을 분류하는 요청을 만듭니다.
ms.openlocfilehash: 3a796bcdb38a9a6930b51f7d585febb69082732e
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177084"
---
# <a name="create-classification-request"></a><span data-ttu-id="16a1d-103">분류 요청 만들기</span><span class="sxs-lookup"><span data-stu-id="16a1d-103">Create classification request</span></span>

<span data-ttu-id="16a1d-104">적용된 문서 이해 모델을 사용하여 하나 이상의 파일을 분류하는 요청을 만듭니다( [예제](rest-createclassificationrequest.md#examples)참조).</span><span class="sxs-lookup"><span data-stu-id="16a1d-104">Creates a request to classify one or more files using the applied document understanding model (see [example](rest-createclassificationrequest.md#examples)).</span></span>

<span data-ttu-id="16a1d-105">SharePoint Online(및 SharePoint 2016 이상 온-프레미스) REST 서비스는 여러 요청의 결합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="16a1d-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests.</span></span> <span data-ttu-id="16a1d-106">요청은 OData $batch 쿼리 옵션을 사용하여 서비스에 대한 단일 호출로 결합됩니다.</span><span class="sxs-lookup"><span data-stu-id="16a1d-106">Requests are combined into a single call to the service by using the OData $batch query option.</span></span> <span data-ttu-id="16a1d-107">이 메서드는 한 번에 수백 개의 문서에 대한 분류 작업 항목을 큐에 넣기 위해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16a1d-107">This method can be used to enqueue classification work items for hundreds of documents at one time.</span></span>

## <a name="http-request"></a><span data-ttu-id="16a1d-108">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="16a1d-108">HTTP request</span></span>

```
POST /_api/machinelearning/workItems HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="16a1d-109">URI 매개 변수</span><span class="sxs-lookup"><span data-stu-id="16a1d-109">URI Parameters</span></span>

<span data-ttu-id="16a1d-110">없음</span><span class="sxs-lookup"><span data-stu-id="16a1d-110">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="16a1d-111">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="16a1d-111">Request headers</span></span>

| <span data-ttu-id="16a1d-112">헤더</span><span class="sxs-lookup"><span data-stu-id="16a1d-112">Header</span></span> | <span data-ttu-id="16a1d-113">값</span><span class="sxs-lookup"><span data-stu-id="16a1d-113">Value</span></span> |
|--------|-------|
|<span data-ttu-id="16a1d-114">수락</span><span class="sxs-lookup"><span data-stu-id="16a1d-114">Accept</span></span>|<span data-ttu-id="16a1d-115">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="16a1d-115">application/json;odata=verbose</span></span>|
|<span data-ttu-id="16a1d-116">Content-Type</span><span class="sxs-lookup"><span data-stu-id="16a1d-116">Content-Type</span></span>|<span data-ttu-id="16a1d-117">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="16a1d-117">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="16a1d-118">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="16a1d-118">x-requestdigest</span></span>|<span data-ttu-id="16a1d-119">현재 사이트에 적합한 다이제스트</span><span class="sxs-lookup"><span data-stu-id="16a1d-119">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="16a1d-120">요청 본문</span><span class="sxs-lookup"><span data-stu-id="16a1d-120">Request body</span></span>

|<span data-ttu-id="16a1d-121">이름</span><span class="sxs-lookup"><span data-stu-id="16a1d-121">Name</span></span>    |<span data-ttu-id="16a1d-122">유형</span><span class="sxs-lookup"><span data-stu-id="16a1d-122">Type</span></span>   |<span data-ttu-id="16a1d-123">설명</span><span class="sxs-lookup"><span data-stu-id="16a1d-123">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="16a1d-124">_metadata</span><span class="sxs-lookup"><span data-stu-id="16a1d-124">_metadata</span></span>|<span data-ttu-id="16a1d-125">문자열</span><span class="sxs-lookup"><span data-stu-id="16a1d-125">string</span></span> |<span data-ttu-id="16a1d-126">SPO에 개체 메타를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="16a1d-126">Set the object meta on the SPO.</span></span> <span data-ttu-id="16a1d-127">항상 {“type”: “Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData”} 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="16a1d-127">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}.</span></span> |
|<span data-ttu-id="16a1d-128">TargetSiteId</span><span class="sxs-lookup"><span data-stu-id="16a1d-128">TargetSiteId</span></span>|<span data-ttu-id="16a1d-129">GUID</span><span class="sxs-lookup"><span data-stu-id="16a1d-129">guid</span></span>|<span data-ttu-id="16a1d-130">분류할 파일이 있는 사이트의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="16a1d-130">The id of the site where the file to classify is located.</span></span>|
|<span data-ttu-id="16a1d-131">TargetWebId</span><span class="sxs-lookup"><span data-stu-id="16a1d-131">TargetWebId</span></span>|<span data-ttu-id="16a1d-132">GUID</span><span class="sxs-lookup"><span data-stu-id="16a1d-132">guid</span></span>|<span data-ttu-id="16a1d-133">분류할 파일이 있는 웹의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="16a1d-133">The id of the web where the file to classify is located.</span></span>|
|<span data-ttu-id="16a1d-134">TargetUniqueId</span><span class="sxs-lookup"><span data-stu-id="16a1d-134">TargetUniqueId</span></span>|<span data-ttu-id="16a1d-135">GUID</span><span class="sxs-lookup"><span data-stu-id="16a1d-135">guid</span></span>|<span data-ttu-id="16a1d-136">분류할 파일의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="16a1d-136">The id of the file to classify.</span></span>|

## <a name="responses"></a><span data-ttu-id="16a1d-137">응답</span><span class="sxs-lookup"><span data-stu-id="16a1d-137">Responses</span></span>

| <span data-ttu-id="16a1d-138">이름</span><span class="sxs-lookup"><span data-stu-id="16a1d-138">Name</span></span>   | <span data-ttu-id="16a1d-139">유형</span><span class="sxs-lookup"><span data-stu-id="16a1d-139">Type</span></span>  | <span data-ttu-id="16a1d-140">설명</span><span class="sxs-lookup"><span data-stu-id="16a1d-140">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="16a1d-141">201 생성됨</span><span class="sxs-lookup"><span data-stu-id="16a1d-141">201 Created</span></span>| |<span data-ttu-id="16a1d-142">성공</span><span class="sxs-lookup"><span data-stu-id="16a1d-142">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="16a1d-143">예제</span><span class="sxs-lookup"><span data-stu-id="16a1d-143">Examples</span></span>

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a><span data-ttu-id="16a1d-144">ID가 "e6cff8b7-c90c-4564-b5b8-033449090932"인 파일을 분류하는 요청을 큐에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="16a1d-144">Enqueue a request to classify a file of id "e6cff8b7-c90c-4564-b5b8-033449090932"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="16a1d-145">샘플 요청</span><span class="sxs-lookup"><span data-stu-id="16a1d-145">Sample request</span></span>

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
}
```

#### <a name="sample-response"></a><span data-ttu-id="16a1d-146">샘플 응답</span><span class="sxs-lookup"><span data-stu-id="16a1d-146">Sample response</span></span>

<span data-ttu-id="16a1d-147">**상태 코드:** 201</span><span class="sxs-lookup"><span data-stu-id="16a1d-147">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="16a1d-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16a1d-148">See also</span></span>

[<span data-ttu-id="16a1d-149">Syntex 문서 이해 모델 REST API</span><span class="sxs-lookup"><span data-stu-id="16a1d-149">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
