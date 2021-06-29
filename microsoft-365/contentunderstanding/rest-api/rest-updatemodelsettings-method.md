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
# <a name="updatemodelsettings"></a><span data-ttu-id="4b75a-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="4b75a-103">UpdateModelSettings</span></span>

<span data-ttu-id="4b75a-104">SharePoint Syntex 문서 이해 모델에 대해 사용 가능한 모델 설정(관련 보존 레이블 및 모델 설명)을 업데이트합니다([예제](rest-updatemodelsettings-method.md#examples) 참조).</span><span class="sxs-lookup"><span data-stu-id="4b75a-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="4b75a-105">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="4b75a-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="4b75a-106">URI 매개 변수</span><span class="sxs-lookup"><span data-stu-id="4b75a-106">URI parameters</span></span>

|<span data-ttu-id="4b75a-107">이름</span><span class="sxs-lookup"><span data-stu-id="4b75a-107">Name</span></span> |<span data-ttu-id="4b75a-108">In</span><span class="sxs-lookup"><span data-stu-id="4b75a-108">In</span></span> |<span data-ttu-id="4b75a-109">필수</span><span class="sxs-lookup"><span data-stu-id="4b75a-109">Required</span></span>|<span data-ttu-id="4b75a-110">유형</span><span class="sxs-lookup"><span data-stu-id="4b75a-110">Type</span></span>|<span data-ttu-id="4b75a-111">설명</span><span class="sxs-lookup"><span data-stu-id="4b75a-111">Description</span></span>|
|-----|---|--------|----|-----------|
|<span data-ttu-id="4b75a-112">modelFileName</span><span class="sxs-lookup"><span data-stu-id="4b75a-112">modelFileName</span></span>|<span data-ttu-id="4b75a-113">쿼리</span><span class="sxs-lookup"><span data-stu-id="4b75a-113">query</span></span>|<span data-ttu-id="4b75a-114">True</span><span class="sxs-lookup"><span data-stu-id="4b75a-114">True</span></span>|<span data-ttu-id="4b75a-115">문자열</span><span class="sxs-lookup"><span data-stu-id="4b75a-115">string</span></span>|<span data-ttu-id="4b75a-116">Syntex 모델 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4b75a-116">Name of the Syntex model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="4b75a-117">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="4b75a-117">Request headers</span></span>

| <span data-ttu-id="4b75a-118">헤더</span><span class="sxs-lookup"><span data-stu-id="4b75a-118">Header</span></span> | <span data-ttu-id="4b75a-119">값</span><span class="sxs-lookup"><span data-stu-id="4b75a-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="4b75a-120">수락</span><span class="sxs-lookup"><span data-stu-id="4b75a-120">Accept</span></span>|<span data-ttu-id="4b75a-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="4b75a-121">application/json;odata=verbose</span></span>|
|<span data-ttu-id="4b75a-122">Content-Type</span><span class="sxs-lookup"><span data-stu-id="4b75a-122">Content-Type</span></span>|<span data-ttu-id="4b75a-123">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="4b75a-123">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="4b75a-124">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="4b75a-124">x-requestdigest</span></span>|<span data-ttu-id="4b75a-125">현재 사이트에 적합한 다이제스트입니다.</span><span class="sxs-lookup"><span data-stu-id="4b75a-125">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="4b75a-126">요청 본문</span><span class="sxs-lookup"><span data-stu-id="4b75a-126">Request body</span></span>

|<span data-ttu-id="4b75a-127">이름</span><span class="sxs-lookup"><span data-stu-id="4b75a-127">Name</span></span>    |<span data-ttu-id="4b75a-128">유형</span><span class="sxs-lookup"><span data-stu-id="4b75a-128">Type</span></span>   |<span data-ttu-id="4b75a-129">설명</span><span class="sxs-lookup"><span data-stu-id="4b75a-129">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="4b75a-130">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="4b75a-130">ModelSettings</span></span>|<span data-ttu-id="4b75a-131">문자열</span><span class="sxs-lookup"><span data-stu-id="4b75a-131">string</span></span>|<span data-ttu-id="4b75a-132">모델 설정의 JSON입니다.</span><span class="sxs-lookup"><span data-stu-id="4b75a-132">JSON of model settings.</span></span>|
|<span data-ttu-id="4b75a-133">설명</span><span class="sxs-lookup"><span data-stu-id="4b75a-133">Description</span></span>|<span data-ttu-id="4b75a-134">문자열</span><span class="sxs-lookup"><span data-stu-id="4b75a-134">string</span></span>|<span data-ttu-id="4b75a-135">모델 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="4b75a-135">The model description.</span></span>|
|<span data-ttu-id="4b75a-136">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="4b75a-136">RetentionLabel</span></span>| |<span data-ttu-id="4b75a-137">연결된 레이블(레이블 ID 및 이름)에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="4b75a-137">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="4b75a-138">응답</span><span class="sxs-lookup"><span data-stu-id="4b75a-138">Responses</span></span>

| <span data-ttu-id="4b75a-139">이름</span><span class="sxs-lookup"><span data-stu-id="4b75a-139">Name</span></span>   | <span data-ttu-id="4b75a-140">유형</span><span class="sxs-lookup"><span data-stu-id="4b75a-140">Type</span></span>  | <span data-ttu-id="4b75a-141">설명</span><span class="sxs-lookup"><span data-stu-id="4b75a-141">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="4b75a-142">200 OK</span><span class="sxs-lookup"><span data-stu-id="4b75a-142">200 OK</span></span>| |<span data-ttu-id="4b75a-143">성공</span><span class="sxs-lookup"><span data-stu-id="4b75a-143">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="4b75a-144">예제</span><span class="sxs-lookup"><span data-stu-id="4b75a-144">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="4b75a-145">Contoso 계약에 대한 모델 설정 업데이트</span><span class="sxs-lookup"><span data-stu-id="4b75a-145">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="4b75a-146">이 예제에서는 모델 설명 및 "표준 보류" 보존 레이블이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b75a-146">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="4b75a-147">보존 레이블의 ID는 `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`입니다.</span><span class="sxs-lookup"><span data-stu-id="4b75a-147">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="4b75a-148">샘플 요청</span><span class="sxs-lookup"><span data-stu-id="4b75a-148">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="4b75a-149">샘플 응답</span><span class="sxs-lookup"><span data-stu-id="4b75a-149">Sample response</span></span>

<span data-ttu-id="4b75a-150">**상태 코드:** 200</span><span class="sxs-lookup"><span data-stu-id="4b75a-150">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="4b75a-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b75a-151">See also</span></span>

[<span data-ttu-id="4b75a-152">Syntex 문서 이해 모델 REST API</span><span class="sxs-lookup"><span data-stu-id="4b75a-152">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
