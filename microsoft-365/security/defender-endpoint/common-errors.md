---
title: 끝점 API 오류에 대한 일반적인 Microsoft Defender
description: 설명이 있는 일반적인 끝점 API 오류에 대한 Microsoft Defender 목록입니다.
keywords: API, 끝점 API용 Microsoft Defender, 오류, 문제 해결
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 54ae77c28523d3be6092e1567424d2d87a5f2927
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934792"
---
# <a name="common-rest-api-error-codes"></a><span data-ttu-id="c845c-104">일반적인 REST API 오류 코드</span><span class="sxs-lookup"><span data-stu-id="c845c-104">Common REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* <span data-ttu-id="c845c-105">다음 표에 나열된 오류 코드는 끝점 API용 Microsoft Defender에 대한 작업으로 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-105">The error codes listed in the following table may be returned by an operation on any of Microsoft Defender for Endpoint APIs.</span></span>
* <span data-ttu-id="c845c-106">오류 코드 외에도 모든 오류 응답에는 문제 해결에 도움이 될 수 있는 오류 메시지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-106">In addition to the error code, every error response contains an error message, which can help resolve the problem.</span></span>
* <span data-ttu-id="c845c-107">메시지는 변경할 수 있는 무료 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-107">The message is a free text that can be changed.</span></span>
* <span data-ttu-id="c845c-108">페이지 아래쪽에서 응답 예제를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-108">At the bottom of the page, you can find response examples.</span></span>

><span data-ttu-id="c845c-109">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="c845c-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c845c-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="c845c-111">오류 코드</span><span class="sxs-lookup"><span data-stu-id="c845c-111">Error code</span></span> |<span data-ttu-id="c845c-112">HTTP 상태 코드</span><span class="sxs-lookup"><span data-stu-id="c845c-112">HTTP status code</span></span> |<span data-ttu-id="c845c-113">메시지</span><span class="sxs-lookup"><span data-stu-id="c845c-113">Message</span></span> 
:---|:---|:---
<span data-ttu-id="c845c-114">BadRequest</span><span class="sxs-lookup"><span data-stu-id="c845c-114">BadRequest</span></span> | <span data-ttu-id="c845c-115">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c845c-115">BadRequest (400)</span></span> | <span data-ttu-id="c845c-116">일반 잘못된 요청 오류 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-116">General Bad Request error message.</span></span>
<span data-ttu-id="c845c-117">ODataError</span><span class="sxs-lookup"><span data-stu-id="c845c-117">ODataError</span></span> | <span data-ttu-id="c845c-118">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c845c-118">BadRequest (400)</span></span> | <span data-ttu-id="c845c-119">OData URI 쿼리가 잘못되었습니다(특정 오류가 지정되었습니다).</span><span class="sxs-lookup"><span data-stu-id="c845c-119">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="c845c-120">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="c845c-120">InvalidInput</span></span> | <span data-ttu-id="c845c-121">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c845c-121">BadRequest (400)</span></span> | <span data-ttu-id="c845c-122">입력 {잘못된 입력}이(가) 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-122">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="c845c-123">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="c845c-123">InvalidRequestBody</span></span> | <span data-ttu-id="c845c-124">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c845c-124">BadRequest (400)</span></span> | <span data-ttu-id="c845c-125">요청 본문이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-125">Invalid request body.</span></span>
<span data-ttu-id="c845c-126">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="c845c-126">InvalidHashValue</span></span> | <span data-ttu-id="c845c-127">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c845c-127">BadRequest (400)</span></span> | <span data-ttu-id="c845c-128">해시 값 {the invalid hash}가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-128">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="c845c-129">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="c845c-129">InvalidDomainName</span></span> | <span data-ttu-id="c845c-130">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c845c-130">BadRequest (400)</span></span> | <span data-ttu-id="c845c-131">도메인 이름 {잘못된 도메인}이(가) 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-131">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="c845c-132">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="c845c-132">InvalidIpAddress</span></span> | <span data-ttu-id="c845c-133">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c845c-133">BadRequest (400)</span></span> | <span data-ttu-id="c845c-134">IP 주소 {잘못된 IP}가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-134">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="c845c-135">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="c845c-135">InvalidUrl</span></span> | <span data-ttu-id="c845c-136">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c845c-136">BadRequest (400)</span></span> | <span data-ttu-id="c845c-137">URL {잘못된 URL}이(가) 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-137">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="c845c-138">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="c845c-138">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="c845c-139">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c845c-139">BadRequest (400)</span></span> | <span data-ttu-id="c845c-140">최대 일괄 처리 크기가 초과됩니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-140">Maximum batch size exceeded.</span></span> <span data-ttu-id="c845c-141">Received: {batch size received}, allowed: {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="c845c-141">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="c845c-142">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="c845c-142">MissingRequiredParameter</span></span> | <span data-ttu-id="c845c-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c845c-143">BadRequest (400)</span></span> | <span data-ttu-id="c845c-144">매개 변수 {누락된 매개 변수}가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-144">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="c845c-145">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="c845c-145">OsPlatformNotSupported</span></span> | <span data-ttu-id="c845c-146">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c845c-146">BadRequest (400)</span></span> | <span data-ttu-id="c845c-147">OS 플랫폼 {클라이언트 OS 플랫폼}은 이 작업에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-147">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="c845c-148">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="c845c-148">ClientVersionNotSupported</span></span> | <span data-ttu-id="c845c-149">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c845c-149">BadRequest (400)</span></span> | <span data-ttu-id="c845c-150">{요청된 작업}은 클라이언트 버전 {지원되는 클라이언트 버전} 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-150">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="c845c-151">권한이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="c845c-151">Unauthorized</span></span> | <span data-ttu-id="c845c-152">권한이 없는 경우(401)</span><span class="sxs-lookup"><span data-stu-id="c845c-152">Unauthorized (401)</span></span> | <span data-ttu-id="c845c-153">권한이 부여되지 않았습니다(유효하지 않은 또는 만료된 권한 부여 헤더).</span><span class="sxs-lookup"><span data-stu-id="c845c-153">Unauthorized (invalid or expired authorization header).</span></span>
<span data-ttu-id="c845c-154">금지</span><span class="sxs-lookup"><span data-stu-id="c845c-154">Forbidden</span></span> | <span data-ttu-id="c845c-155">금지(403)</span><span class="sxs-lookup"><span data-stu-id="c845c-155">Forbidden (403)</span></span> | <span data-ttu-id="c845c-156">금지됩니다(유효한 토큰이지만 작업의 사용 권한이 부족).</span><span class="sxs-lookup"><span data-stu-id="c845c-156">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="c845c-157">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="c845c-157">DisabledFeature</span></span> | <span data-ttu-id="c845c-158">금지(403)</span><span class="sxs-lookup"><span data-stu-id="c845c-158">Forbidden (403)</span></span> | <span data-ttu-id="c845c-159">테넌트 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-159">Tenant feature is not enabled.</span></span>
<span data-ttu-id="c845c-160">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="c845c-160">DisallowedOperation</span></span> | <span data-ttu-id="c845c-161">금지(403)</span><span class="sxs-lookup"><span data-stu-id="c845c-161">Forbidden (403)</span></span> | <span data-ttu-id="c845c-162">{the disallowed operation and the reason}.</span><span class="sxs-lookup"><span data-stu-id="c845c-162">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="c845c-163">NotFound</span><span class="sxs-lookup"><span data-stu-id="c845c-163">NotFound</span></span> | <span data-ttu-id="c845c-164">찾을 수 없습니다(404)</span><span class="sxs-lookup"><span data-stu-id="c845c-164">Not Found (404)</span></span> | <span data-ttu-id="c845c-165">일반 찾을 수 없는 오류 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-165">General Not Found error message.</span></span>
<span data-ttu-id="c845c-166">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="c845c-166">ResourceNotFound</span></span> | <span data-ttu-id="c845c-167">찾을 수 없습니다(404)</span><span class="sxs-lookup"><span data-stu-id="c845c-167">Not Found (404)</span></span> | <span data-ttu-id="c845c-168">리소스 {요청된 자원}을(를) 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-168">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="c845c-169">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="c845c-169">InternalServerError</span></span> | <span data-ttu-id="c845c-170">내부 서버 오류(500)</span><span class="sxs-lookup"><span data-stu-id="c845c-170">Internal Server Error (500)</span></span> | <span data-ttu-id="c845c-171">(오류 메시지 없음, 작업을 다시 시도)</span><span class="sxs-lookup"><span data-stu-id="c845c-171">(No error message, retry the operation)</span></span>
<span data-ttu-id="c845c-172">TooManyRequests</span><span class="sxs-lookup"><span data-stu-id="c845c-172">TooManyRequests</span></span> | <span data-ttu-id="c845c-173">요청 수가 너무 많음(429)</span><span class="sxs-lookup"><span data-stu-id="c845c-173">Too Many Requests (429)</span></span> | <span data-ttu-id="c845c-174">응답은 요청 수 또는 CPU에 의해 할당량 제한에 도달하는 경우를 나타내게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-174">Response will represent reaching quota limit either by number of requests or by CPU.</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="c845c-175">본문 매개 변수는 대소문자 구분</span><span class="sxs-lookup"><span data-stu-id="c845c-175">Body parameters are case-sensitive</span></span>

<span data-ttu-id="c845c-176">제출된 본문 매개 변수는 현재 대소문자 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-176">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="c845c-177">**InvalidRequestBody** 또는 **MissingRequiredParameter** 오류가 발생하는 경우 매개 변수의 대/소문자 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-177">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="c845c-178">API 설명서 페이지를 검토하고 제출된 매개 변수가 관련 예제와 일치하는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="c845c-178">Review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="c845c-179">상관 관계 요청 ID</span><span class="sxs-lookup"><span data-stu-id="c845c-179">Correlation request ID</span></span>

<span data-ttu-id="c845c-180">각 오류 응답에는 추적을 위한 고유 ID 매개 변수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-180">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="c845c-181">이 매개 변수의 속성 이름은 "target"입니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-181">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="c845c-182">오류에 대해 문의할 때 이 ID를 첨부하면 문제의 근본 원인을 찾는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c845c-182">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="c845c-183">예제</span><span class="sxs-lookup"><span data-stu-id="c845c-183">Examples</span></span>

```json
{
    "error": {
        "code": "ResourceNotFound",
        "message": "Machine 123123123 was not found",
        "target": "43f4cb08-8fac-4b65-9db1-745c2ae65f3a"
    }
}
```


```json
{
    "error": {
        "code": "InvalidRequestBody",
        "message": "Request body is incorrect",
        "target": "1fa66c0f-18bd-4133-b378-36d76f3a2ba0"
    }
}
```
