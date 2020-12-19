---
title: 일반적인 Microsoft 365 Defender REST API 오류 코드
description: 일반적인 Microsoft 365 Defender REST API 오류 코드에 대해 자세히
keywords: api, 오류, 코드, 일반적인 오류, mtp, api 오류 코드
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
ms.openlocfilehash: 0df741efb7555d587a6033acc23716e93f542d5e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719217"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="125d2-104">일반적인 Microsoft 365 Defender REST API 오류 코드</span><span class="sxs-lookup"><span data-stu-id="125d2-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="125d2-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="125d2-105">**Applies to:**</span></span>

- <span data-ttu-id="125d2-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="125d2-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="125d2-107">일부 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 미리 판매된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="125d2-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="125d2-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="125d2-109">오류 코드는 Microsoft 365 Defender API에 대한 작업으로 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="125d2-110">모든 오류 응답에는 문제 해결에 도움이 될 수 있는 오류 메시지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="125d2-111">표 섹션의 오류 메시지 열에는 몇 가지 예제 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="125d2-112">실제 메시지의 내용은 응답을 트리거한 요인에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="125d2-113">가변 콘텐츠는 표에 앵글 괄호로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="125d2-114">오류 코드</span><span class="sxs-lookup"><span data-stu-id="125d2-114">Error codes</span></span>

<span data-ttu-id="125d2-115">오류 코드</span><span class="sxs-lookup"><span data-stu-id="125d2-115">Error code</span></span> | <span data-ttu-id="125d2-116">HTTP 상태 코드</span><span class="sxs-lookup"><span data-stu-id="125d2-116">HTTP status code</span></span> | <span data-ttu-id="125d2-117">메시지</span><span class="sxs-lookup"><span data-stu-id="125d2-117">Message</span></span>
-|-|-
<span data-ttu-id="125d2-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="125d2-118">BadRequest</span></span> | <span data-ttu-id="125d2-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="125d2-119">BadRequest (400)</span></span> | <span data-ttu-id="125d2-120">일반 잘못된 요청 오류 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-120">General Bad Request error message.</span></span>
<span data-ttu-id="125d2-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="125d2-121">ODataError</span></span> | <span data-ttu-id="125d2-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="125d2-122">BadRequest (400)</span></span> | <span data-ttu-id="125d2-123">잘못된 OData URI \<the specific error is specified\> 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="125d2-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="125d2-124">InvalidInput</span></span> | <span data-ttu-id="125d2-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="125d2-125">BadRequest (400)</span></span> | <span data-ttu-id="125d2-126">입력이 \<the invalid input\> 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="125d2-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="125d2-127">InvalidRequestBody</span></span> | <span data-ttu-id="125d2-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="125d2-128">BadRequest (400)</span></span> | <span data-ttu-id="125d2-129">요청 본문이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-129">Invalid request body.</span></span>
<span data-ttu-id="125d2-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="125d2-130">InvalidHashValue</span></span> | <span data-ttu-id="125d2-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="125d2-131">BadRequest (400)</span></span> | <span data-ttu-id="125d2-132">해시 값이 \<the invalid hash\> 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="125d2-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="125d2-133">InvalidDomainName</span></span> | <span data-ttu-id="125d2-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="125d2-134">BadRequest (400)</span></span> | <span data-ttu-id="125d2-135">도메인 이름이 \<the invalid domain\> 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="125d2-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="125d2-136">InvalidIpAddress</span></span> | <span data-ttu-id="125d2-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="125d2-137">BadRequest (400)</span></span> | <span data-ttu-id="125d2-138">IP \<the invalid IP\> 주소가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="125d2-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="125d2-139">InvalidUrl</span></span> | <span data-ttu-id="125d2-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="125d2-140">BadRequest (400)</span></span> | <span data-ttu-id="125d2-141">URL이 \<the invalid URL\> 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="125d2-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="125d2-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="125d2-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="125d2-143">BadRequest (400)</span></span> | <span data-ttu-id="125d2-144">최대 일괄 처리 크기가 초과됩니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="125d2-145">Received: \<batch size received\> , allowed: {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="125d2-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="125d2-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="125d2-146">MissingRequiredParameter</span></span> | <span data-ttu-id="125d2-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="125d2-147">BadRequest (400)</span></span> | <span data-ttu-id="125d2-148">매개 \<the missing parameter\> 변수가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="125d2-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="125d2-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="125d2-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="125d2-150">BadRequest (400)</span></span> | <span data-ttu-id="125d2-151">이 \<the client OS Platform\> 작업에서 OS 플랫폼이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="125d2-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="125d2-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="125d2-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="125d2-153">BadRequest (400)</span></span> | <span data-ttu-id="125d2-154">\<The requested action\> 는 클라이언트 버전 \<supported client version\> 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="125d2-155">권한이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="125d2-155">Unauthorized</span></span> | <span data-ttu-id="125d2-156">권한이 없는 경우(401)</span><span class="sxs-lookup"><span data-stu-id="125d2-156">Unauthorized (401)</span></span> | <span data-ttu-id="125d2-157">권한이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="125d2-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="125d2-158">*참고: 일반적으로 유효하지 않은 또는 만료된 권한 부여 헤더로 인해 발생했습니다.*</span><span class="sxs-lookup"><span data-stu-id="125d2-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="125d2-159">금지</span><span class="sxs-lookup"><span data-stu-id="125d2-159">Forbidden</span></span> | <span data-ttu-id="125d2-160">금지(403)</span><span class="sxs-lookup"><span data-stu-id="125d2-160">Forbidden (403)</span></span> | <span data-ttu-id="125d2-161">금지</span><span class="sxs-lookup"><span data-stu-id="125d2-161">Forbidden</span></span> <br /><br /><span data-ttu-id="125d2-162">*참고: 유효한 토큰이지만* 작업 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="125d2-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="125d2-163">DisabledFeature</span></span> | <span data-ttu-id="125d2-164">금지(403)</span><span class="sxs-lookup"><span data-stu-id="125d2-164">Forbidden (403)</span></span> | <span data-ttu-id="125d2-165">테넌트 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="125d2-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="125d2-166">DisallowedOperation</span></span> | <span data-ttu-id="125d2-167">금지(403)</span><span class="sxs-lookup"><span data-stu-id="125d2-167">Forbidden (403)</span></span> | <span data-ttu-id="125d2-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="125d2-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="125d2-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="125d2-169">NotFound</span></span> | <span data-ttu-id="125d2-170">찾을 수 없습니다(404)</span><span class="sxs-lookup"><span data-stu-id="125d2-170">Not Found (404)</span></span> | <span data-ttu-id="125d2-171">일반 찾을 수 없는 오류 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-171">General Not Found error message.</span></span>
<span data-ttu-id="125d2-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="125d2-172">ResourceNotFound</span></span> | <span data-ttu-id="125d2-173">찾을 수 없습니다(404)</span><span class="sxs-lookup"><span data-stu-id="125d2-173">Not Found (404)</span></span> | <span data-ttu-id="125d2-174">리소스를 \<the requested resource\> 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="125d2-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="125d2-175">InternalServerError</span></span> | <span data-ttu-id="125d2-176">내부 서버 오류(500)</span><span class="sxs-lookup"><span data-stu-id="125d2-176">Internal Server Error (500)</span></span> | <span data-ttu-id="125d2-177">*참고: 오류 메시지가 없는 경우 작업을 다시 시도하거나 해결되지 않은 경우 Microsoft에 문의하십시오.*</span><span class="sxs-lookup"><span data-stu-id="125d2-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="125d2-178">예</span><span class="sxs-lookup"><span data-stu-id="125d2-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="125d2-179">본문 매개 변수</span><span class="sxs-lookup"><span data-stu-id="125d2-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="125d2-180">본문 매개 변수는 대소문자 구분입니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="125d2-181">*InvalidRequestBody* 또는 *MissingRequiredParameter* 오류가 발생하는 경우 오타로 인해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="125d2-182">API 설명서를 검토하고 제출된 매개 변수가 관련 예제와 일치하는지 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="125d2-183">추적 ID</span><span class="sxs-lookup"><span data-stu-id="125d2-183">Tracking ID</span></span>

<span data-ttu-id="125d2-184">각 오류 응답에는 추적을 위한 고유한 ID 매개 변수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="125d2-185">이 매개 변수의 속성 이름은 *target입니다.*</span><span class="sxs-lookup"><span data-stu-id="125d2-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="125d2-186">오류에 대해 문의할 때 이 ID를 첨부하면 문제의 근본 원인을 찾는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="125d2-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="125d2-187">관련 문서</span><span class="sxs-lookup"><span data-stu-id="125d2-187">Related articles</span></span>

- [<span data-ttu-id="125d2-188">Microsoft 365 Defender API 개요</span><span class="sxs-lookup"><span data-stu-id="125d2-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="125d2-189">지원되는 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="125d2-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="125d2-190">Microsoft 365 Defender API 액세스</span><span class="sxs-lookup"><span data-stu-id="125d2-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="125d2-191">API 제한 및 라이선싱에 대해 자세히</span><span class="sxs-lookup"><span data-stu-id="125d2-191">Learn about API limits and licensing</span></span>](api-terms.md)
