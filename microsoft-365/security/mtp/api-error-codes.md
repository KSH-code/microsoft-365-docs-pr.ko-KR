---
title: 일반적인 Microsoft Threat Protection REST API 오류 코드
description: 일반적인 Microsoft Threat Protection REST API 오류 코드에 대해 자세히 알아보기
keywords: api, 오류, 코드, 일반 오류, mtp, api 오류 코드
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 81375b919b52ff895e5ec7014feb747b1a0eae65
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201342"
---
# <a name="common-microsoft-threat-protection-rest-api-error-codes"></a><span data-ttu-id="5cfae-104">일반적인 Microsoft Threat Protection REST API 오류 코드</span><span class="sxs-lookup"><span data-stu-id="5cfae-104">Common Microsoft Threat Protection REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5cfae-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5cfae-105">**Applies to:**</span></span>
- <span data-ttu-id="5cfae-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="5cfae-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="5cfae-107">일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="5cfae-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="5cfae-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="5cfae-109">다음 표에 나와 있는 오류 코드는 Microsoft Threat Protection Api에서 작업에 의해 반환 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-109">The error codes listed in the following table may be returned by an operation on any of Microsoft Threat Protection APIs.</span></span>

<span data-ttu-id="5cfae-110">모든 오류 응답에 오류 메시지가 포함 되어 있어 문제를 해결 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-110">Every error response contains an error message, which can help resolving the problem.</span></span>

<span data-ttu-id="5cfae-111">메시지는 변경할 수 있는 자유로운 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-111">The message is a free text that can be changed.</span></span>

<span data-ttu-id="5cfae-112">페이지 맨 아래에서 응답 예를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-112">At the bottom of the page, you can find response examples.</span></span>

<span data-ttu-id="5cfae-113">오류 코드</span><span class="sxs-lookup"><span data-stu-id="5cfae-113">Error code</span></span> |<span data-ttu-id="5cfae-114">HTTP 상태 코드</span><span class="sxs-lookup"><span data-stu-id="5cfae-114">HTTP status code</span></span> |<span data-ttu-id="5cfae-115">메시지</span><span class="sxs-lookup"><span data-stu-id="5cfae-115">Message</span></span> 
:---|:---|:---
<span data-ttu-id="5cfae-116">BadRequest</span><span class="sxs-lookup"><span data-stu-id="5cfae-116">BadRequest</span></span> | <span data-ttu-id="5cfae-117">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5cfae-117">BadRequest (400)</span></span> | <span data-ttu-id="5cfae-118">일반적인 잘못 된 요청 오류 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-118">General Bad Request error message.</span></span>
<span data-ttu-id="5cfae-119">ODataError</span><span class="sxs-lookup"><span data-stu-id="5cfae-119">ODataError</span></span> | <span data-ttu-id="5cfae-120">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5cfae-120">BadRequest (400)</span></span> | <span data-ttu-id="5cfae-121">잘못 된 OData URI 쿼리 (특정 오류가 지정 됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-121">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="5cfae-122">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="5cfae-122">InvalidInput</span></span> | <span data-ttu-id="5cfae-123">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5cfae-123">BadRequest (400)</span></span> | <span data-ttu-id="5cfae-124">입력 {잘못 된 입력}입니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-124">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="5cfae-125">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="5cfae-125">InvalidRequestBody</span></span> | <span data-ttu-id="5cfae-126">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5cfae-126">BadRequest (400)</span></span> | <span data-ttu-id="5cfae-127">요청 본문이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-127">Invalid request body.</span></span>
<span data-ttu-id="5cfae-128">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="5cfae-128">InvalidHashValue</span></span> | <span data-ttu-id="5cfae-129">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5cfae-129">BadRequest (400)</span></span> | <span data-ttu-id="5cfae-130">해시 값 {잘못 된 해시}가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-130">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="5cfae-131">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="5cfae-131">InvalidDomainName</span></span> | <span data-ttu-id="5cfae-132">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5cfae-132">BadRequest (400)</span></span> | <span data-ttu-id="5cfae-133">도메인 이름 {잘못 된 도메인}이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-133">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="5cfae-134">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="5cfae-134">InvalidIpAddress</span></span> | <span data-ttu-id="5cfae-135">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5cfae-135">BadRequest (400)</span></span> | <span data-ttu-id="5cfae-136">IP 주소 {잘못 된 IP}가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-136">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="5cfae-137">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="5cfae-137">InvalidUrl</span></span> | <span data-ttu-id="5cfae-138">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5cfae-138">BadRequest (400)</span></span> | <span data-ttu-id="5cfae-139">URL {잘못 된 URL}이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-139">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="5cfae-140">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="5cfae-140">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="5cfae-141">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5cfae-141">BadRequest (400)</span></span> | <span data-ttu-id="5cfae-142">최대 일괄 처리 크기를 초과 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-142">Maximum batch size exceeded.</span></span> <span data-ttu-id="5cfae-143">Received: {batch size received}, 허용: {일괄 처리 크기 허용}.</span><span class="sxs-lookup"><span data-stu-id="5cfae-143">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="5cfae-144">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="5cfae-144">MissingRequiredParameter</span></span> | <span data-ttu-id="5cfae-145">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5cfae-145">BadRequest (400)</span></span> | <span data-ttu-id="5cfae-146">매개 변수 {누락 된 매개 변수}가 누락 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-146">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="5cfae-147">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="5cfae-147">OsPlatformNotSupported</span></span> | <span data-ttu-id="5cfae-148">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5cfae-148">BadRequest (400)</span></span> | <span data-ttu-id="5cfae-149">OS 플랫폼 {클라이언트 OS 플랫폼}은이 작업에 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-149">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="5cfae-150">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="5cfae-150">ClientVersionNotSupported</span></span> | <span data-ttu-id="5cfae-151">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5cfae-151">BadRequest (400)</span></span> | <span data-ttu-id="5cfae-152">{요청 된 작업}은 클라이언트 버전 {지원 되는 클라이언트 버전} 이상에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-152">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="5cfae-153">권한</span><span class="sxs-lookup"><span data-stu-id="5cfae-153">Unauthorized</span></span> | <span data-ttu-id="5cfae-154">인증 되지 않음 (401)</span><span class="sxs-lookup"><span data-stu-id="5cfae-154">Unauthorized (401)</span></span> | <span data-ttu-id="5cfae-155">인증 되지 않음 (대개 잘못 되었거나 만료 된 인증 헤더)</span><span class="sxs-lookup"><span data-stu-id="5cfae-155">Unauthorized (usually invalid or expired authorization header).</span></span>
<span data-ttu-id="5cfae-156">권한</span><span class="sxs-lookup"><span data-stu-id="5cfae-156">Forbidden</span></span> | <span data-ttu-id="5cfae-157">금지 (403)</span><span class="sxs-lookup"><span data-stu-id="5cfae-157">Forbidden (403)</span></span> | <span data-ttu-id="5cfae-158">사용할 수 없음 (유효한 토큰 이지만 해당 작업에 대 한 권한이 부족 함)</span><span class="sxs-lookup"><span data-stu-id="5cfae-158">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="5cfae-159">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="5cfae-159">DisabledFeature</span></span> | <span data-ttu-id="5cfae-160">금지 (403)</span><span class="sxs-lookup"><span data-stu-id="5cfae-160">Forbidden (403)</span></span> | <span data-ttu-id="5cfae-161">테 넌 트 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-161">Tenant feature is not enabled.</span></span>
<span data-ttu-id="5cfae-162">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="5cfae-162">DisallowedOperation</span></span> | <span data-ttu-id="5cfae-163">금지 (403)</span><span class="sxs-lookup"><span data-stu-id="5cfae-163">Forbidden (403)</span></span> | <span data-ttu-id="5cfae-164">{허용 되지 않는 작업 및 이유}.</span><span class="sxs-lookup"><span data-stu-id="5cfae-164">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="5cfae-165">NotFound</span><span class="sxs-lookup"><span data-stu-id="5cfae-165">NotFound</span></span> | <span data-ttu-id="5cfae-166">찾을 수 없음 (404)</span><span class="sxs-lookup"><span data-stu-id="5cfae-166">Not Found (404)</span></span> | <span data-ttu-id="5cfae-167">General을 찾을 수 없음 오류 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-167">General Not Found error message.</span></span>
<span data-ttu-id="5cfae-168">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="5cfae-168">ResourceNotFound</span></span> | <span data-ttu-id="5cfae-169">찾을 수 없음 (404)</span><span class="sxs-lookup"><span data-stu-id="5cfae-169">Not Found (404)</span></span> | <span data-ttu-id="5cfae-170">자원 {요청한 자원}을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-170">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="5cfae-171">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="5cfae-171">InternalServerError</span></span> | <span data-ttu-id="5cfae-172">내부 서버 오류 (500)</span><span class="sxs-lookup"><span data-stu-id="5cfae-172">Internal Server Error (500)</span></span> | <span data-ttu-id="5cfae-173">(오류 메시지 없음, 작업을 다시 시도 하거나, 확인 되지 않으면 문의해 주세요.)</span><span class="sxs-lookup"><span data-stu-id="5cfae-173">(No error message,  retry the operation or contact us if it does not get resolved)</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="5cfae-174">본문 매개 변수는 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-174">Body parameters are case-sensitive</span></span>

<span data-ttu-id="5cfae-175">전송 된 본문 매개 변수는 현재 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-175">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="5cfae-176">**Invalidrequestbody** 또는 **MissingRequiredParameter** 오류가 발생 하는 경우 잘못 된 매개 변수 대문자 또는 소문자로 인해 발생 한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-176">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="5cfae-177">API 설명서 페이지를 검토 하 여 전송 된 매개 변수가 관련 예제와 일치 하는지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-177">We recommend that you review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="5cfae-178">상관 관계 요청 ID</span><span class="sxs-lookup"><span data-stu-id="5cfae-178">Correlation request ID</span></span>

<span data-ttu-id="5cfae-179">각 오류 응답에는 추적을 위한 고유한 ID 매개 변수가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-179">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="5cfae-180">이 매개 변수의 속성 이름은 "target"입니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-180">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="5cfae-181">이 ID를 연결 하 여 오류에 대 한 정보를 문의할 때 문제의 근본적인 원인을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cfae-181">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="5cfae-182">예</span><span class="sxs-lookup"><span data-stu-id="5cfae-182">Examples</span></span>

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

