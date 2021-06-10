---
title: 일반적인 Microsoft 365 Defender REST API 오류 코드
description: Defender REST API Microsoft 365 일반적인 코드에 대해 자세히 알아보시고
keywords: api, 오류, 코드, 일반적인 오류, Microsoft 365 Defender, api 오류 코드
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e621b79d37a2c3a22394bd51e0493334eff461c7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932884"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="c82b4-104">일반적인 Microsoft 365 Defender REST API 오류 코드</span><span class="sxs-lookup"><span data-stu-id="c82b4-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c82b4-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c82b4-105">**Applies to:**</span></span>

- <span data-ttu-id="c82b4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c82b4-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c82b4-107">일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c82b4-108">Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="c82b4-109">오류 코드는 Defender API의 모든 Microsoft 365 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="c82b4-110">모든 오류 응답에는 문제 해결에 도움이 될 수 있는 오류 메시지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="c82b4-111">표 섹션의 오류 메시지 열에는 몇 가지 예제 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="c82b4-112">실제 메시지의 내용은 응답을 트리거한 요인에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="c82b4-113">가변 콘텐츠는 표에 괄호로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="c82b4-114">오류 코드</span><span class="sxs-lookup"><span data-stu-id="c82b4-114">Error codes</span></span>

<span data-ttu-id="c82b4-115">오류 코드</span><span class="sxs-lookup"><span data-stu-id="c82b4-115">Error code</span></span> | <span data-ttu-id="c82b4-116">HTTP 상태 코드</span><span class="sxs-lookup"><span data-stu-id="c82b4-116">HTTP status code</span></span> | <span data-ttu-id="c82b4-117">메시지</span><span class="sxs-lookup"><span data-stu-id="c82b4-117">Message</span></span>
-|-|-
<span data-ttu-id="c82b4-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="c82b4-118">BadRequest</span></span> | <span data-ttu-id="c82b4-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c82b4-119">BadRequest (400)</span></span> | <span data-ttu-id="c82b4-120">일반 잘못된 요청 오류 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-120">General Bad Request error message.</span></span>
<span data-ttu-id="c82b4-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="c82b4-121">ODataError</span></span> | <span data-ttu-id="c82b4-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c82b4-122">BadRequest (400)</span></span> | <span data-ttu-id="c82b4-123">OData URI 쿼리가 \<the specific error is specified\> 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="c82b4-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="c82b4-124">InvalidInput</span></span> | <span data-ttu-id="c82b4-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c82b4-125">BadRequest (400)</span></span> | <span data-ttu-id="c82b4-126">입력이 \<the invalid input\> 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="c82b4-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="c82b4-127">InvalidRequestBody</span></span> | <span data-ttu-id="c82b4-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c82b4-128">BadRequest (400)</span></span> | <span data-ttu-id="c82b4-129">요청 본문이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-129">Invalid request body.</span></span>
<span data-ttu-id="c82b4-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="c82b4-130">InvalidHashValue</span></span> | <span data-ttu-id="c82b4-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c82b4-131">BadRequest (400)</span></span> | <span data-ttu-id="c82b4-132">해시 값이 \<the invalid hash\> 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="c82b4-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="c82b4-133">InvalidDomainName</span></span> | <span data-ttu-id="c82b4-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c82b4-134">BadRequest (400)</span></span> | <span data-ttu-id="c82b4-135">도메인 이름이 \<the invalid domain\> 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="c82b4-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="c82b4-136">InvalidIpAddress</span></span> | <span data-ttu-id="c82b4-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c82b4-137">BadRequest (400)</span></span> | <span data-ttu-id="c82b4-138">IP \<the invalid IP\> 주소가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="c82b4-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="c82b4-139">InvalidUrl</span></span> | <span data-ttu-id="c82b4-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c82b4-140">BadRequest (400)</span></span> | <span data-ttu-id="c82b4-141">URL이 \<the invalid URL\> 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="c82b4-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="c82b4-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="c82b4-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c82b4-143">BadRequest (400)</span></span> | <span data-ttu-id="c82b4-144">최대 일괄 처리 크기가 초과됩니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="c82b4-145">Received: \<batch size received\> , allowed: {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="c82b4-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="c82b4-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="c82b4-146">MissingRequiredParameter</span></span> | <span data-ttu-id="c82b4-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c82b4-147">BadRequest (400)</span></span> | <span data-ttu-id="c82b4-148">매개 \<the missing parameter\> 변수가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="c82b4-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="c82b4-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="c82b4-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c82b4-150">BadRequest (400)</span></span> | <span data-ttu-id="c82b4-151">이 \<the client OS Platform\> 작업에서 OS 플랫폼이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="c82b4-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="c82b4-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="c82b4-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c82b4-153">BadRequest (400)</span></span> | <span data-ttu-id="c82b4-154">\<The requested action\> 는 클라이언트 버전 \<supported client version\> 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="c82b4-155">권한이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="c82b4-155">Unauthorized</span></span> | <span data-ttu-id="c82b4-156">권한이 없는 경우(401)</span><span class="sxs-lookup"><span data-stu-id="c82b4-156">Unauthorized (401)</span></span> | <span data-ttu-id="c82b4-157">권한이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="c82b4-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="c82b4-158">*참고: 일반적으로 유효하지 않은 또는 만료된 권한 부여 헤더로 인해 발생했습니다.*</span><span class="sxs-lookup"><span data-stu-id="c82b4-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="c82b4-159">금지</span><span class="sxs-lookup"><span data-stu-id="c82b4-159">Forbidden</span></span> | <span data-ttu-id="c82b4-160">금지(403)</span><span class="sxs-lookup"><span data-stu-id="c82b4-160">Forbidden (403)</span></span> | <span data-ttu-id="c82b4-161">금지</span><span class="sxs-lookup"><span data-stu-id="c82b4-161">Forbidden</span></span> <br /><br /><span data-ttu-id="c82b4-162">*참고: 유효한 토큰이지만* 작업의 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="c82b4-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="c82b4-163">DisabledFeature</span></span> | <span data-ttu-id="c82b4-164">금지(403)</span><span class="sxs-lookup"><span data-stu-id="c82b4-164">Forbidden (403)</span></span> | <span data-ttu-id="c82b4-165">테넌트 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="c82b4-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="c82b4-166">DisallowedOperation</span></span> | <span data-ttu-id="c82b4-167">금지(403)</span><span class="sxs-lookup"><span data-stu-id="c82b4-167">Forbidden (403)</span></span> | <span data-ttu-id="c82b4-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="c82b4-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="c82b4-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="c82b4-169">NotFound</span></span> | <span data-ttu-id="c82b4-170">찾을 수 없습니다(404)</span><span class="sxs-lookup"><span data-stu-id="c82b4-170">Not Found (404)</span></span> | <span data-ttu-id="c82b4-171">일반 찾을 수 없는 오류 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-171">General Not Found error message.</span></span>
<span data-ttu-id="c82b4-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="c82b4-172">ResourceNotFound</span></span> | <span data-ttu-id="c82b4-173">찾을 수 없습니다(404)</span><span class="sxs-lookup"><span data-stu-id="c82b4-173">Not Found (404)</span></span> | <span data-ttu-id="c82b4-174">리소스를 \<the requested resource\> 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="c82b4-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="c82b4-175">InternalServerError</span></span> | <span data-ttu-id="c82b4-176">내부 서버 오류(500)</span><span class="sxs-lookup"><span data-stu-id="c82b4-176">Internal Server Error (500)</span></span> | <span data-ttu-id="c82b4-177">*참고: 오류 메시지가 없음, 작업을 다시 시도하거나 해결되지 않은 경우 Microsoft에 문의*</span><span class="sxs-lookup"><span data-stu-id="c82b4-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="c82b4-178">예제</span><span class="sxs-lookup"><span data-stu-id="c82b4-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="c82b4-179">Body 매개 변수</span><span class="sxs-lookup"><span data-stu-id="c82b4-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c82b4-180">본문 매개 변수는 대소문자 구분입니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="c82b4-181">*InvalidRequestBody* 또는 *MissingRequiredParameter* 오류가 발생하는 경우 오타로 인해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="c82b4-182">API 설명서를 검토하고 제출된 매개 변수가 관련 예제와 일치하는지 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="c82b4-183">추적 ID</span><span class="sxs-lookup"><span data-stu-id="c82b4-183">Tracking ID</span></span>

<span data-ttu-id="c82b4-184">각 오류 응답에는 추적을 위한 고유 ID 매개 변수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="c82b4-185">이 매개 변수의 속성 이름은 *대상입니다.*</span><span class="sxs-lookup"><span data-stu-id="c82b4-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="c82b4-186">오류에 대해 문의할 때 이 ID를 첨부하면 문제의 근본 원인을 찾는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c82b4-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="c82b4-187">관련 문서</span><span class="sxs-lookup"><span data-stu-id="c82b4-187">Related articles</span></span>

- [<span data-ttu-id="c82b4-188">Microsoft 365 Defender API 개요</span><span class="sxs-lookup"><span data-stu-id="c82b4-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="c82b4-189">지원되는 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="c82b4-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="c82b4-190">Microsoft 365 Defender API에 액세스</span><span class="sxs-lookup"><span data-stu-id="c82b4-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="c82b4-191">API 제한 및 라이선싱에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="c82b4-191">Learn about API limits and licensing</span></span>](api-terms.md)
