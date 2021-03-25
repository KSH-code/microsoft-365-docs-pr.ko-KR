---
title: 제출 또는 업데이트 표시기 API
description: 제출 또는 업데이트 표시기 API를 사용하여 끝점용 Microsoft Defender에서 새 지표 엔터티를 제출하거나 업데이트하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, 제출, ti, 표시기, 업데이트
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
ms.openlocfilehash: 42bab0a9d20d5e1ef78b98b3538cef209240d890
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187361"
---
# <a name="submit-or-update-indicator-api"></a><span data-ttu-id="c3b57-104">제출 또는 업데이트 표시기 API</span><span class="sxs-lookup"><span data-stu-id="c3b57-104">Submit or Update Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c3b57-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c3b57-105">**Applies to:**</span></span>
- [<span data-ttu-id="c3b57-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c3b57-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c3b57-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3b57-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c3b57-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="c3b57-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c3b57-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c3b57-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="c3b57-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="c3b57-110">API description</span></span>
<span data-ttu-id="c3b57-111">새 Indicator [엔터티를 제출하거나 업데이트합니다.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="c3b57-111">Submits or Updates new [Indicator](ti-indicator.md) entity.</span></span>
<br><span data-ttu-id="c3b57-112">IP에 대한 CIDR은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3b57-112">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="c3b57-113">제한 사항</span><span class="sxs-lookup"><span data-stu-id="c3b57-113">Limitations</span></span>
1. <span data-ttu-id="c3b57-114">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="c3b57-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="c3b57-115">테넌트당 활성 표시기는 15,000개로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3b57-115">There is a limit of 15,000 active indicators per tenant.</span></span> 


## <a name="permissions"></a><span data-ttu-id="c3b57-116">사용 권한</span><span class="sxs-lookup"><span data-stu-id="c3b57-116">Permissions</span></span>
<span data-ttu-id="c3b57-117">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c3b57-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c3b57-118">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [시작을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c3b57-118">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="c3b57-119">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="c3b57-119">Permission type</span></span> |   <span data-ttu-id="c3b57-120">사용 권한</span><span class="sxs-lookup"><span data-stu-id="c3b57-120">Permission</span></span>  |   <span data-ttu-id="c3b57-121">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="c3b57-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c3b57-122">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="c3b57-122">Application</span></span> |   <span data-ttu-id="c3b57-123">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="c3b57-123">Ti.ReadWrite</span></span> |  <span data-ttu-id="c3b57-124">'읽기 및 쓰기 표시기'</span><span class="sxs-lookup"><span data-stu-id="c3b57-124">'Read and write Indicators'</span></span>
<span data-ttu-id="c3b57-125">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="c3b57-125">Application</span></span> |   <span data-ttu-id="c3b57-126">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c3b57-126">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="c3b57-127">'모든 지표 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="c3b57-127">'Read and write All Indicators'</span></span>
<span data-ttu-id="c3b57-128">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="c3b57-128">Delegated (work or school account)</span></span> |    <span data-ttu-id="c3b57-129">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="c3b57-129">Ti.ReadWrite</span></span> |  <span data-ttu-id="c3b57-130">'읽기 및 쓰기 표시기'</span><span class="sxs-lookup"><span data-stu-id="c3b57-130">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="c3b57-131">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="c3b57-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="c3b57-132">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="c3b57-132">Request headers</span></span>

<span data-ttu-id="c3b57-133">이름</span><span class="sxs-lookup"><span data-stu-id="c3b57-133">Name</span></span> | <span data-ttu-id="c3b57-134">유형</span><span class="sxs-lookup"><span data-stu-id="c3b57-134">Type</span></span> | <span data-ttu-id="c3b57-135">설명</span><span class="sxs-lookup"><span data-stu-id="c3b57-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="c3b57-136">권한 부여</span><span class="sxs-lookup"><span data-stu-id="c3b57-136">Authorization</span></span> | <span data-ttu-id="c3b57-137">문자열</span><span class="sxs-lookup"><span data-stu-id="c3b57-137">String</span></span> | <span data-ttu-id="c3b57-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c3b57-138">Bearer {token}.</span></span> <span data-ttu-id="c3b57-139">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="c3b57-139">**Required**.</span></span>
<span data-ttu-id="c3b57-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="c3b57-140">Content-Type</span></span> | <span data-ttu-id="c3b57-141">문자열</span><span class="sxs-lookup"><span data-stu-id="c3b57-141">string</span></span> | <span data-ttu-id="c3b57-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="c3b57-142">application/json.</span></span> <span data-ttu-id="c3b57-143">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="c3b57-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="c3b57-144">요청 본문</span><span class="sxs-lookup"><span data-stu-id="c3b57-144">Request body</span></span>
<span data-ttu-id="c3b57-145">요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c3b57-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="c3b57-146">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3b57-146">Parameter</span></span> | <span data-ttu-id="c3b57-147">유형</span><span class="sxs-lookup"><span data-stu-id="c3b57-147">Type</span></span>    | <span data-ttu-id="c3b57-148">설명</span><span class="sxs-lookup"><span data-stu-id="c3b57-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="c3b57-149">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="c3b57-149">indicatorValue</span></span> | <span data-ttu-id="c3b57-150">문자열</span><span class="sxs-lookup"><span data-stu-id="c3b57-150">String</span></span> | <span data-ttu-id="c3b57-151">Indicator [엔터티의 ID입니다.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="c3b57-151">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="c3b57-152">**필수**</span><span class="sxs-lookup"><span data-stu-id="c3b57-152">**Required**</span></span>
<span data-ttu-id="c3b57-153">indicatorType</span><span class="sxs-lookup"><span data-stu-id="c3b57-153">indicatorType</span></span> | <span data-ttu-id="c3b57-154">Enum</span><span class="sxs-lookup"><span data-stu-id="c3b57-154">Enum</span></span> | <span data-ttu-id="c3b57-155">표시기 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="c3b57-155">Type of the indicator.</span></span> <span data-ttu-id="c3b57-156">가능한 값은 "FileSha1", "FileSha256", "IpAddress", "DomainName" 및 "Url"입니다.</span><span class="sxs-lookup"><span data-stu-id="c3b57-156">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="c3b57-157">**필수**</span><span class="sxs-lookup"><span data-stu-id="c3b57-157">**Required**</span></span>
<span data-ttu-id="c3b57-158">조치</span><span class="sxs-lookup"><span data-stu-id="c3b57-158">action</span></span> | <span data-ttu-id="c3b57-159">Enum</span><span class="sxs-lookup"><span data-stu-id="c3b57-159">Enum</span></span> | <span data-ttu-id="c3b57-160">표시기가 조직에서 검색되는 경우 수행되는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="c3b57-160">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="c3b57-161">가능한 값은 "Alert", "AlertAndBlock" 및 "Allowed"입니다.</span><span class="sxs-lookup"><span data-stu-id="c3b57-161">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="c3b57-162">**필수**</span><span class="sxs-lookup"><span data-stu-id="c3b57-162">**Required**</span></span>
<span data-ttu-id="c3b57-163">application</span><span class="sxs-lookup"><span data-stu-id="c3b57-163">application</span></span> | <span data-ttu-id="c3b57-164">문자열</span><span class="sxs-lookup"><span data-stu-id="c3b57-164">String</span></span> | <span data-ttu-id="c3b57-165">표시기와 연결된 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="c3b57-165">The application associated with the indicator.</span></span> <span data-ttu-id="c3b57-166">**선택**</span><span class="sxs-lookup"><span data-stu-id="c3b57-166">**Optional**</span></span>
<span data-ttu-id="c3b57-167">title</span><span class="sxs-lookup"><span data-stu-id="c3b57-167">title</span></span> | <span data-ttu-id="c3b57-168">문자열</span><span class="sxs-lookup"><span data-stu-id="c3b57-168">String</span></span> | <span data-ttu-id="c3b57-169">표시기 경고 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="c3b57-169">Indicator alert title.</span></span> <span data-ttu-id="c3b57-170">**필수**</span><span class="sxs-lookup"><span data-stu-id="c3b57-170">**Required**</span></span>
<span data-ttu-id="c3b57-171">설명</span><span class="sxs-lookup"><span data-stu-id="c3b57-171">description</span></span> | <span data-ttu-id="c3b57-172">문자열</span><span class="sxs-lookup"><span data-stu-id="c3b57-172">String</span></span> | <span data-ttu-id="c3b57-173">표시기 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="c3b57-173">Description of the indicator.</span></span> <span data-ttu-id="c3b57-174">**필수**</span><span class="sxs-lookup"><span data-stu-id="c3b57-174">**Required**</span></span>
<span data-ttu-id="c3b57-175">expirationTime</span><span class="sxs-lookup"><span data-stu-id="c3b57-175">expirationTime</span></span> | <span data-ttu-id="c3b57-176">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="c3b57-176">DateTimeOffset</span></span> | <span data-ttu-id="c3b57-177">표시기 만료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c3b57-177">The expiration time of the indicator.</span></span> <span data-ttu-id="c3b57-178">**선택**</span><span class="sxs-lookup"><span data-stu-id="c3b57-178">**Optional**</span></span>
<span data-ttu-id="c3b57-179">심각도</span><span class="sxs-lookup"><span data-stu-id="c3b57-179">severity</span></span> | <span data-ttu-id="c3b57-180">Enum</span><span class="sxs-lookup"><span data-stu-id="c3b57-180">Enum</span></span> | <span data-ttu-id="c3b57-181">표시기 심각도입니다.</span><span class="sxs-lookup"><span data-stu-id="c3b57-181">The severity of the indicator.</span></span> <span data-ttu-id="c3b57-182">가능한 값은 "Informational", "Low", "Medium" 및 "High"입니다.</span><span class="sxs-lookup"><span data-stu-id="c3b57-182">possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="c3b57-183">**선택**</span><span class="sxs-lookup"><span data-stu-id="c3b57-183">**Optional**</span></span>
<span data-ttu-id="c3b57-184">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="c3b57-184">recommendedActions</span></span> | <span data-ttu-id="c3b57-185">문자열</span><span class="sxs-lookup"><span data-stu-id="c3b57-185">String</span></span> | <span data-ttu-id="c3b57-186">TI 표시기 경고 권장 작업.</span><span class="sxs-lookup"><span data-stu-id="c3b57-186">TI indicator alert recommended actions.</span></span> <span data-ttu-id="c3b57-187">**선택**</span><span class="sxs-lookup"><span data-stu-id="c3b57-187">**Optional**</span></span>
<span data-ttu-id="c3b57-188">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="c3b57-188">rbacGroupNames</span></span> | <span data-ttu-id="c3b57-189">문자열</span><span class="sxs-lookup"><span data-stu-id="c3b57-189">String</span></span> | <span data-ttu-id="c3b57-190">콤보로 구분된 RBAC 그룹 이름 목록 표시기가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3b57-190">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="c3b57-191">**선택**</span><span class="sxs-lookup"><span data-stu-id="c3b57-191">**Optional**</span></span>


## <a name="response"></a><span data-ttu-id="c3b57-192">응답</span><span class="sxs-lookup"><span data-stu-id="c3b57-192">Response</span></span>
- <span data-ttu-id="c3b57-193">성공하면 이 메서드는 응답 본문에 200 - 확인 응답 코드와 생성/업데이트된 [Indicator](ti-indicator.md) 엔터티를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c3b57-193">If successful, this method returns 200 - OK response code and the created / updated [Indicator](ti-indicator.md) entity in the response body.</span></span>
- <span data-ttu-id="c3b57-194">성공하지 못하면 이 메서드는 400 - 잘못된 요청을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c3b57-194">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="c3b57-195">잘못된 요청은 일반적으로 잘못된 본문을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c3b57-195">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="c3b57-196">예제</span><span class="sxs-lookup"><span data-stu-id="c3b57-196">Example</span></span>

<span data-ttu-id="c3b57-197">**요청**</span><span class="sxs-lookup"><span data-stu-id="c3b57-197">**Request**</span></span>

<span data-ttu-id="c3b57-198">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="c3b57-198">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a><span data-ttu-id="c3b57-199">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c3b57-199">Related topic</span></span>
- [<span data-ttu-id="c3b57-200">표시기 관리</span><span class="sxs-lookup"><span data-stu-id="c3b57-200">Manage indicators</span></span>](manage-indicators.md)
