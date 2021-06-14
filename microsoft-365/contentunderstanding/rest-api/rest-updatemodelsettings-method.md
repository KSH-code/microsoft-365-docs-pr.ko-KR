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
ms.openlocfilehash: f24fc8428adbf22ded2ca6d7a49cabc84b385770
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904304"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="b9f73-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="b9f73-103">UpdateModelSettings</span></span>

<span data-ttu-id="b9f73-104">SharePoint Syntex 문서 이해 모델에 대해 사용 가능한 모델 설정(관련 보존 레이블 및 모델 설명)을 업데이트합니다([예제](rest-updatemodelsettings-method.md#examples) 참조).</span><span class="sxs-lookup"><span data-stu-id="b9f73-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="b9f73-105">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="b9f73-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="b9f73-106">URI 매개 변수</span><span class="sxs-lookup"><span data-stu-id="b9f73-106">URI parameters</span></span>

<span data-ttu-id="b9f73-107">없음</span><span class="sxs-lookup"><span data-stu-id="b9f73-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="b9f73-108">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="b9f73-108">Request headers</span></span>

| <span data-ttu-id="b9f73-109">헤더</span><span class="sxs-lookup"><span data-stu-id="b9f73-109">Header</span></span> | <span data-ttu-id="b9f73-110">값</span><span class="sxs-lookup"><span data-stu-id="b9f73-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="b9f73-111">수락</span><span class="sxs-lookup"><span data-stu-id="b9f73-111">Accept</span></span>|<span data-ttu-id="b9f73-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="b9f73-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="b9f73-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="b9f73-113">Content-Type</span></span>|<span data-ttu-id="b9f73-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="b9f73-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="b9f73-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="b9f73-115">x-requestdigest</span></span>|<span data-ttu-id="b9f73-116">현재 사이트에 적합한 다이제스트입니다.</span><span class="sxs-lookup"><span data-stu-id="b9f73-116">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="b9f73-117">요청 본문</span><span class="sxs-lookup"><span data-stu-id="b9f73-117">Request body</span></span>

|<span data-ttu-id="b9f73-118">이름</span><span class="sxs-lookup"><span data-stu-id="b9f73-118">Name</span></span>    |<span data-ttu-id="b9f73-119">유형</span><span class="sxs-lookup"><span data-stu-id="b9f73-119">Type</span></span>   |<span data-ttu-id="b9f73-120">설명</span><span class="sxs-lookup"><span data-stu-id="b9f73-120">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="b9f73-121">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="b9f73-121">ModelSettings</span></span>|<span data-ttu-id="b9f73-122">문자열</span><span class="sxs-lookup"><span data-stu-id="b9f73-122">string</span></span>|<span data-ttu-id="b9f73-123">모델 설정의 JSON입니다.</span><span class="sxs-lookup"><span data-stu-id="b9f73-123">JSON of model settings.</span></span>|
|<span data-ttu-id="b9f73-124">설명</span><span class="sxs-lookup"><span data-stu-id="b9f73-124">Description</span></span>|<span data-ttu-id="b9f73-125">문자열</span><span class="sxs-lookup"><span data-stu-id="b9f73-125">string</span></span>|<span data-ttu-id="b9f73-126">모델 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="b9f73-126">The model description.</span></span>|
|<span data-ttu-id="b9f73-127">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="b9f73-127">RetentionLabel</span></span>| |<span data-ttu-id="b9f73-128">연결된 레이블(레이블 ID 및 이름)에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="b9f73-128">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="b9f73-129">응답</span><span class="sxs-lookup"><span data-stu-id="b9f73-129">Responses</span></span>

| <span data-ttu-id="b9f73-130">이름</span><span class="sxs-lookup"><span data-stu-id="b9f73-130">Name</span></span>   | <span data-ttu-id="b9f73-131">유형</span><span class="sxs-lookup"><span data-stu-id="b9f73-131">Type</span></span>  | <span data-ttu-id="b9f73-132">설명</span><span class="sxs-lookup"><span data-stu-id="b9f73-132">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="b9f73-133">200 OK</span><span class="sxs-lookup"><span data-stu-id="b9f73-133">200 OK</span></span>| |<span data-ttu-id="b9f73-134">성공</span><span class="sxs-lookup"><span data-stu-id="b9f73-134">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="b9f73-135">예제</span><span class="sxs-lookup"><span data-stu-id="b9f73-135">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="b9f73-136">Contoso 계약에 대한 모델 설정 업데이트</span><span class="sxs-lookup"><span data-stu-id="b9f73-136">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="b9f73-137">이 예제에서는 모델 설명 및 "표준 보류" 보존 레이블이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9f73-137">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="b9f73-138">보존 레이블의 ID는 `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`입니다.</span><span class="sxs-lookup"><span data-stu-id="b9f73-138">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="b9f73-139">샘플 요청</span><span class="sxs-lookup"><span data-stu-id="b9f73-139">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="b9f73-140">샘플 응답</span><span class="sxs-lookup"><span data-stu-id="b9f73-140">Sample response</span></span>

<span data-ttu-id="b9f73-141">**상태 코드:** 200</span><span class="sxs-lookup"><span data-stu-id="b9f73-141">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="b9f73-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9f73-142">See also</span></span>

[<span data-ttu-id="b9f73-143">Syntex 문서 이해 모델 REST API</span><span class="sxs-lookup"><span data-stu-id="b9f73-143">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
