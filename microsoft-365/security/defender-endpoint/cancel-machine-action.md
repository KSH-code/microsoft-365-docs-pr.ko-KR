---
title: 컴퓨터 작업 취소 API
description: 이미 시작된 컴퓨터 작업을 취소하는 방법 학습
keywords: api, 그래프 api,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 490ee91d5f2d2c02174be94c52fc83fd0ec0fc5e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879758"
---
#   <a name="cancel-machine-action-api"></a><span data-ttu-id="55d26-104">컴퓨터 작업 취소 API</span><span class="sxs-lookup"><span data-stu-id="55d26-104">Cancel machine action API</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="55d26-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="55d26-105">**Applies to:**</span></span>
- [<span data-ttu-id="55d26-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="55d26-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="55d26-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="55d26-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="55d26-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="55d26-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="55d26-109">API 설명</span><span class="sxs-lookup"><span data-stu-id="55d26-109">API description</span></span>

<span data-ttu-id="55d26-110">아직 최종 상태가 아닌 이미 시작된 컴퓨터 작업 취소(완료, 취소, 실패)</span><span class="sxs-lookup"><span data-stu-id="55d26-110">Cancel an already launched machine action that are not yet in final state (completed, cancelled, failed).</span></span>

## <a name="limitations"></a><span data-ttu-id="55d26-111">제한 사항</span><span class="sxs-lookup"><span data-stu-id="55d26-111">Limitations</span></span>

1.  <span data-ttu-id="55d26-112">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="55d26-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="55d26-113">사용 권한</span><span class="sxs-lookup"><span data-stu-id="55d26-113">Permissions</span></span>

<span data-ttu-id="55d26-114">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="55d26-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="55d26-115">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [시작을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="55d26-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

|     <span data-ttu-id="55d26-116">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="55d26-116">Permission    type</span></span>     |     <span data-ttu-id="55d26-117">사용 권한</span><span class="sxs-lookup"><span data-stu-id="55d26-117">Permission</span></span>     |    <span data-ttu-id="55d26-118">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="55d26-118">Permission    display name</span></span>     |
|-|-|-|
|    <br><span data-ttu-id="55d26-119">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="55d26-119">Application</span></span>    |    <br><span data-ttu-id="55d26-120">Machine.CollectForensic</span><span class="sxs-lookup"><span data-stu-id="55d26-120">Machine.CollectForensic</span></span><br>   <span data-ttu-id="55d26-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="55d26-121">Machine.Isolate</span></span>   <br><span data-ttu-id="55d26-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="55d26-122">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="55d26-123">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="55d26-123">Machine.Scan</span></span><br>   <span data-ttu-id="55d26-124">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="55d26-124">Machine.Offboard</span></span><br>   <span data-ttu-id="55d26-125">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="55d26-125">Machine.StopAndQuarantine</span></span><br>   <span data-ttu-id="55d26-126">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="55d26-126">Machine.LiveResponse</span></span>    |    <span data-ttu-id="55d26-127">포렌식 수집</span><span class="sxs-lookup"><span data-stu-id="55d26-127">Collect   forensics</span></span>   <br><span data-ttu-id="55d26-128">컴퓨터 격리</span><span class="sxs-lookup"><span data-stu-id="55d26-128">Isolate   machine</span></span><br><span data-ttu-id="55d26-129">코드 실행 제한</span><span class="sxs-lookup"><span data-stu-id="55d26-129">Restrict   code execution</span></span><br>  <span data-ttu-id="55d26-130">컴퓨터 검사</span><span class="sxs-lookup"><span data-stu-id="55d26-130">Scan   machine</span></span><br>  <span data-ttu-id="55d26-131">컴퓨터 오프보드</span><span class="sxs-lookup"><span data-stu-id="55d26-131">Offboard   machine</span></span><br>   <span data-ttu-id="55d26-132">중지 및 Quarantine</span><span class="sxs-lookup"><span data-stu-id="55d26-132">Stop And   Quarantine</span></span><br>   <span data-ttu-id="55d26-133">특정 컴퓨터의 실시간 응답 실행</span><span class="sxs-lookup"><span data-stu-id="55d26-133">Run live   response on a specific machine</span></span>    |
|    <br><span data-ttu-id="55d26-134">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="55d26-134">Delegated   (work or school account)</span></span>    |    <span data-ttu-id="55d26-135">Machine.CollectForensic</span><span class="sxs-lookup"><span data-stu-id="55d26-135">Machine.CollectForensic</span></span><br>   <span data-ttu-id="55d26-136">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="55d26-136">Machine.Isolate</span></span>    <br><span data-ttu-id="55d26-137">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="55d26-137">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="55d26-138">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="55d26-138">Machine.Scan</span></span><br>   <span data-ttu-id="55d26-139">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="55d26-139">Machine.Offboard</span></span><br>   <span data-ttu-id="55d26-140">Machine.StopAndQuarantineMachine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="55d26-140">Machine.StopAndQuarantineMachine.LiveResponse</span></span>    |    <span data-ttu-id="55d26-141">포렌식 수집</span><span class="sxs-lookup"><span data-stu-id="55d26-141">Collect   forensics</span></span><br>   <span data-ttu-id="55d26-142">컴퓨터 격리</span><span class="sxs-lookup"><span data-stu-id="55d26-142">Isolate   machine</span></span><br>  <span data-ttu-id="55d26-143">코드 실행 제한</span><span class="sxs-lookup"><span data-stu-id="55d26-143">Restrict   code execution</span></span><br> <span data-ttu-id="55d26-144">컴퓨터 검사</span><span class="sxs-lookup"><span data-stu-id="55d26-144">Scan   machine</span></span><br><span data-ttu-id="55d26-145">컴퓨터 오프보드</span><span class="sxs-lookup"><span data-stu-id="55d26-145">Offboard   machine</span></span><br> <span data-ttu-id="55d26-146">중지 및 Quarantine</span><span class="sxs-lookup"><span data-stu-id="55d26-146">Stop And   Quarantine</span></span><br> <span data-ttu-id="55d26-147">특정 컴퓨터의 실시간 응답 실행</span><span class="sxs-lookup"><span data-stu-id="55d26-147">Run live   response on a specific machine</span></span>    |


## <a name="http-request"></a><span data-ttu-id="55d26-148">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="55d26-148">HTTP request</span></span>

```
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel  
```


## <a name="request-headers"></a><span data-ttu-id="55d26-149">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="55d26-149">Request headers</span></span>

| <span data-ttu-id="55d26-150">이름</span><span class="sxs-lookup"><span data-stu-id="55d26-150">Name</span></span>      | <span data-ttu-id="55d26-151">유형</span><span class="sxs-lookup"><span data-stu-id="55d26-151">Type</span></span> | <span data-ttu-id="55d26-152">설명</span><span class="sxs-lookup"><span data-stu-id="55d26-152">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="55d26-153">권한 부여</span><span class="sxs-lookup"><span data-stu-id="55d26-153">Authorization</span></span> | <span data-ttu-id="55d26-154">String</span><span class="sxs-lookup"><span data-stu-id="55d26-154">String</span></span>   | <span data-ttu-id="55d26-155">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="55d26-155">Bearer {token}.</span></span> <span data-ttu-id="55d26-156">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="55d26-156">Required.</span></span>   |
| <span data-ttu-id="55d26-157">Content-Type</span><span class="sxs-lookup"><span data-stu-id="55d26-157">Content-Type</span></span>  | <span data-ttu-id="55d26-158">문자열</span><span class="sxs-lookup"><span data-stu-id="55d26-158">string</span></span>   | <span data-ttu-id="55d26-159">application/json.</span><span class="sxs-lookup"><span data-stu-id="55d26-159">application/json.</span></span> <span data-ttu-id="55d26-160">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="55d26-160">Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="55d26-161">요청 본문</span><span class="sxs-lookup"><span data-stu-id="55d26-161">Request body</span></span>

| <span data-ttu-id="55d26-162">매개 변수</span><span class="sxs-lookup"><span data-stu-id="55d26-162">Parameter</span></span> | <span data-ttu-id="55d26-163">유형</span><span class="sxs-lookup"><span data-stu-id="55d26-163">Type</span></span> | <span data-ttu-id="55d26-164">설명</span><span class="sxs-lookup"><span data-stu-id="55d26-164">Description</span></span>                        |
|---------------|----------|----------------------------------------|
| <span data-ttu-id="55d26-165">Comment</span><span class="sxs-lookup"><span data-stu-id="55d26-165">Comment</span></span>       | <span data-ttu-id="55d26-166">String</span><span class="sxs-lookup"><span data-stu-id="55d26-166">String</span></span>   | <span data-ttu-id="55d26-167">취소 작업과 연결되는 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="55d26-167">Comment to associate with the cancellation action.</span></span>  |

## <a name="response"></a><span data-ttu-id="55d26-168">응답</span><span class="sxs-lookup"><span data-stu-id="55d26-168">Response</span></span>

<span data-ttu-id="55d26-169">성공하면 이 메서드는 Machine Action 엔터티가 있는 200, 확인 응답 코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="55d26-169">If successful, this method returns 200, Ok response code with a Machine Action entity.</span></span> <span data-ttu-id="55d26-170">지정된 ID가 있는 컴퓨터 작업 엔터티를 찾을 수 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55d26-170">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="55d26-171">예시</span><span class="sxs-lookup"><span data-stu-id="55d26-171">Example</span></span>

<span data-ttu-id="55d26-172">**요청**</span><span class="sxs-lookup"><span data-stu-id="55d26-172">**Request**</span></span>

<span data-ttu-id="55d26-173">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="55d26-173">Here is an example of the request.</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```


```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a><span data-ttu-id="55d26-174">관련 항목</span><span class="sxs-lookup"><span data-stu-id="55d26-174">Related topic</span></span>

- [<span data-ttu-id="55d26-175">컴퓨터 작업 API를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="55d26-175">Get machine action API</span></span>](get-machineaction-object.md)