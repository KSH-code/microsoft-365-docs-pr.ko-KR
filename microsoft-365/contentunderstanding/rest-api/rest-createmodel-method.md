---
title: 모델 만들기
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
description: REST API를 사용하여 모델 및 관련 콘텐츠 형식을 만듭니다.
ms.openlocfilehash: 0a1b6ef9b7e38f2c4f52082103530da432e3e855
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177156"
---
# <a name="create-model"></a><span data-ttu-id="a8bb8-103">모델 만들기</span><span class="sxs-lookup"><span data-stu-id="a8bb8-103">Create model</span></span>

<span data-ttu-id="a8bb8-104">모델 및 관련 콘텐츠 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8bb8-104">Creates a model and its associated content type.</span></span> <span data-ttu-id="a8bb8-105">이렇게 하면 모델만 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8bb8-105">Note that this only creates the model.</span></span> <span data-ttu-id="a8bb8-106">콘텐츠 센터에서 계속 학습해야 합니다( [예제](rest-createmodel-method.md#examples)참조).</span><span class="sxs-lookup"><span data-stu-id="a8bb8-106">It will still need to be trained in the content center (see [example](rest-createmodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="a8bb8-107">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="a8bb8-107">HTTP request</span></span>

```
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="a8bb8-108">URI 매개 변수</span><span class="sxs-lookup"><span data-stu-id="a8bb8-108">URI Parameters</span></span>

<span data-ttu-id="a8bb8-109">없음</span><span class="sxs-lookup"><span data-stu-id="a8bb8-109">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="a8bb8-110">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="a8bb8-110">Request headers</span></span>

| <span data-ttu-id="a8bb8-111">헤더</span><span class="sxs-lookup"><span data-stu-id="a8bb8-111">Header</span></span> | <span data-ttu-id="a8bb8-112">값</span><span class="sxs-lookup"><span data-stu-id="a8bb8-112">Value</span></span> |
|--------|-------|
|<span data-ttu-id="a8bb8-113">수락</span><span class="sxs-lookup"><span data-stu-id="a8bb8-113">Accept</span></span>|<span data-ttu-id="a8bb8-114">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="a8bb8-114">application/json;odata=verbose</span></span>|
|<span data-ttu-id="a8bb8-115">Content-Type</span><span class="sxs-lookup"><span data-stu-id="a8bb8-115">Content-Type</span></span>|<span data-ttu-id="a8bb8-116">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="a8bb8-116">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="a8bb8-117">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="a8bb8-117">x-requestdigest</span></span>|<span data-ttu-id="a8bb8-118">현재 사이트에 적합한 다이제스트</span><span class="sxs-lookup"><span data-stu-id="a8bb8-118">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="a8bb8-119">요청 본문</span><span class="sxs-lookup"><span data-stu-id="a8bb8-119">Request body</span></span>

|<span data-ttu-id="a8bb8-120">이름</span><span class="sxs-lookup"><span data-stu-id="a8bb8-120">Name</span></span>    |<span data-ttu-id="a8bb8-121">유형</span><span class="sxs-lookup"><span data-stu-id="a8bb8-121">Type</span></span>   |<span data-ttu-id="a8bb8-122">설명</span><span class="sxs-lookup"><span data-stu-id="a8bb8-122">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="a8bb8-123">_metadata</span><span class="sxs-lookup"><span data-stu-id="a8bb8-123">_metadata</span></span>|  |<span data-ttu-id="a8bb8-124">SPO에 개체 메타를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8bb8-124">Set the object meta on the SPO.</span></span> <span data-ttu-id="a8bb8-125">항상 값 {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a8bb8-125">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span></span> |
|<span data-ttu-id="a8bb8-126">ContentTypeGroup</span><span class="sxs-lookup"><span data-stu-id="a8bb8-126">ContentTypeGroup</span></span>|<span data-ttu-id="a8bb8-127">문자열</span><span class="sxs-lookup"><span data-stu-id="a8bb8-127">string</span></span>|<span data-ttu-id="a8bb8-128">모델과 연결된 연결된 콘텐츠 형식 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="a8bb8-128">The associated content type group associated with the model.</span></span> <span data-ttu-id="a8bb8-129">기본값은 "지능형 문서 콘텐츠 형식"입니다.</span><span class="sxs-lookup"><span data-stu-id="a8bb8-129">Defaulted to "Intelligent Document Content Types".</span></span>|
|<span data-ttu-id="a8bb8-130">ContentTypeName</span><span class="sxs-lookup"><span data-stu-id="a8bb8-130">ContentTypeName</span></span>|<span data-ttu-id="a8bb8-131">문자열</span><span class="sxs-lookup"><span data-stu-id="a8bb8-131">string</span></span>|<span data-ttu-id="a8bb8-132">연결된 콘텐츠 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a8bb8-132">The associated content type name.</span></span> <span data-ttu-id="a8bb8-133">만든 모델 파일의 이름이 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a8bb8-133">The created model file will have the same name.</span></span>|

## <a name="responses"></a><span data-ttu-id="a8bb8-134">응답</span><span class="sxs-lookup"><span data-stu-id="a8bb8-134">Responses</span></span>

| <span data-ttu-id="a8bb8-135">이름</span><span class="sxs-lookup"><span data-stu-id="a8bb8-135">Name</span></span>   | <span data-ttu-id="a8bb8-136">유형</span><span class="sxs-lookup"><span data-stu-id="a8bb8-136">Type</span></span>  | <span data-ttu-id="a8bb8-137">설명</span><span class="sxs-lookup"><span data-stu-id="a8bb8-137">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="a8bb8-138">201 생성됨</span><span class="sxs-lookup"><span data-stu-id="a8bb8-138">201 Created</span></span>| |<span data-ttu-id="a8bb8-139">성공</span><span class="sxs-lookup"><span data-stu-id="a8bb8-139">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="a8bb8-140">예제</span><span class="sxs-lookup"><span data-stu-id="a8bb8-140">Examples</span></span>

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a><span data-ttu-id="a8bb8-141">"Contoso Contract"라는 새 문서 이해 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="a8bb8-141">Create a new document understanding model called "Contoso Contract"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="a8bb8-142">샘플 요청</span><span class="sxs-lookup"><span data-stu-id="a8bb8-142">Sample request</span></span>

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract"
}
```

#### <a name="sample-response"></a><span data-ttu-id="a8bb8-143">샘플 응답</span><span class="sxs-lookup"><span data-stu-id="a8bb8-143">Sample response</span></span>

<span data-ttu-id="a8bb8-144">**상태 코드:** 201</span><span class="sxs-lookup"><span data-stu-id="a8bb8-144">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="a8bb8-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8bb8-145">See also</span></span>

[<span data-ttu-id="a8bb8-146">Syntex 문서 이해 모델 REST API</span><span class="sxs-lookup"><span data-stu-id="a8bb8-146">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
