---
title: 표시기 가져오기 API
description: 끝점용 Microsoft Defender에서 지표 API의 가져오기 일괄 처리를 사용하는 방법을 학습합니다.
keywords: api, 지원되는 api, 제출, ti, 표시기, 업데이트
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: b1777adf7b97083fae2daf4213a4bda742ba097d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198248"
---
# <a name="import-indicators-api"></a><span data-ttu-id="6277e-104">표시기 가져오기 API</span><span class="sxs-lookup"><span data-stu-id="6277e-104">Import Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6277e-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="6277e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="6277e-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="6277e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6277e-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6277e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="6277e-108">API 설명</span><span class="sxs-lookup"><span data-stu-id="6277e-108">API description</span></span>
<span data-ttu-id="6277e-109">표시기 엔터티의 일괄 [처리를 제출하거나](ti-indicator.md) 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="6277e-109">Submits or Updates batch of [Indicator](ti-indicator.md) entities.</span></span>
<br><span data-ttu-id="6277e-110">IP에 대한 CIDR은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6277e-110">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="6277e-111">제한 사항</span><span class="sxs-lookup"><span data-stu-id="6277e-111">Limitations</span></span>
1. <span data-ttu-id="6277e-112">이 API에 대한 속도 제한은 분당 30개 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="6277e-112">Rate limitations for this API are 30 calls per minute.</span></span>
2. <span data-ttu-id="6277e-113">테넌트당 활성 표시기는 15,000개로 제한됩니다. [](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="6277e-113">There is a limit of 15,000 active [Indicators](ti-indicator.md) per tenant.</span></span> 
3. <span data-ttu-id="6277e-114">하나의 API 호출에 대한 최대 일괄 처리 크기는 500입니다.</span><span class="sxs-lookup"><span data-stu-id="6277e-114">Maximum batch size for one API call is 500.</span></span>

## <a name="permissions"></a><span data-ttu-id="6277e-115">사용 권한</span><span class="sxs-lookup"><span data-stu-id="6277e-115">Permissions</span></span>
<span data-ttu-id="6277e-116">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6277e-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6277e-117">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [시작을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6277e-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="6277e-118">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="6277e-118">Permission type</span></span> |   <span data-ttu-id="6277e-119">사용 권한</span><span class="sxs-lookup"><span data-stu-id="6277e-119">Permission</span></span>  |   <span data-ttu-id="6277e-120">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="6277e-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6277e-121">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="6277e-121">Application</span></span> |   <span data-ttu-id="6277e-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="6277e-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="6277e-123">'읽기 및 쓰기 표시기'</span><span class="sxs-lookup"><span data-stu-id="6277e-123">'Read and write Indicators'</span></span>
<span data-ttu-id="6277e-124">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="6277e-124">Application</span></span> |   <span data-ttu-id="6277e-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="6277e-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="6277e-126">'모든 지표 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="6277e-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="6277e-127">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="6277e-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="6277e-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="6277e-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="6277e-129">'읽기 및 쓰기 표시기'</span><span class="sxs-lookup"><span data-stu-id="6277e-129">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="6277e-130">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="6277e-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

## <a name="request-headers"></a><span data-ttu-id="6277e-131">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="6277e-131">Request headers</span></span>

<span data-ttu-id="6277e-132">이름</span><span class="sxs-lookup"><span data-stu-id="6277e-132">Name</span></span> | <span data-ttu-id="6277e-133">유형</span><span class="sxs-lookup"><span data-stu-id="6277e-133">Type</span></span> | <span data-ttu-id="6277e-134">설명</span><span class="sxs-lookup"><span data-stu-id="6277e-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="6277e-135">권한 부여</span><span class="sxs-lookup"><span data-stu-id="6277e-135">Authorization</span></span> | <span data-ttu-id="6277e-136">String</span><span class="sxs-lookup"><span data-stu-id="6277e-136">String</span></span> | <span data-ttu-id="6277e-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="6277e-137">Bearer {token}.</span></span> <span data-ttu-id="6277e-138">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="6277e-138">**Required**.</span></span>
<span data-ttu-id="6277e-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="6277e-139">Content-Type</span></span> | <span data-ttu-id="6277e-140">문자열</span><span class="sxs-lookup"><span data-stu-id="6277e-140">string</span></span> | <span data-ttu-id="6277e-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="6277e-141">application/json.</span></span> <span data-ttu-id="6277e-142">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="6277e-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="6277e-143">요청 본문</span><span class="sxs-lookup"><span data-stu-id="6277e-143">Request body</span></span>
<span data-ttu-id="6277e-144">요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6277e-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="6277e-145">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6277e-145">Parameter</span></span> | <span data-ttu-id="6277e-146">유형</span><span class="sxs-lookup"><span data-stu-id="6277e-146">Type</span></span>    | <span data-ttu-id="6277e-147">설명</span><span class="sxs-lookup"><span data-stu-id="6277e-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="6277e-148">지표</span><span class="sxs-lookup"><span data-stu-id="6277e-148">Indicators</span></span> | <span data-ttu-id="6277e-149">목록<[표시기](ti-indicator.md)></span><span class="sxs-lookup"><span data-stu-id="6277e-149">List<[Indicator](ti-indicator.md)></span></span> | <span data-ttu-id="6277e-150">표시기 [목록입니다.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="6277e-150">List of [Indicators](ti-indicator.md).</span></span> <span data-ttu-id="6277e-151">**필수**</span><span class="sxs-lookup"><span data-stu-id="6277e-151">**Required**</span></span>


## <a name="response"></a><span data-ttu-id="6277e-152">응답</span><span class="sxs-lookup"><span data-stu-id="6277e-152">Response</span></span>
- <span data-ttu-id="6277e-153">성공하면 이 메서드는 표시기당 가져오기 결과 목록이 있는 200 - 확인 응답 코드를 반환합니다. 아래 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6277e-153">If successful, this method returns 200 - OK response code with a list of import results per indicator, see example below.</span></span>
- <span data-ttu-id="6277e-154">성공하지 못하면 이 메서드는 400 - 잘못된 요청을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6277e-154">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="6277e-155">잘못된 요청은 일반적으로 잘못된 본문을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6277e-155">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="6277e-156">예시</span><span class="sxs-lookup"><span data-stu-id="6277e-156">Example</span></span>

<span data-ttu-id="6277e-157">**요청**</span><span class="sxs-lookup"><span data-stu-id="6277e-157">**Request**</span></span>

<span data-ttu-id="6277e-158">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="6277e-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

```json
{
    "Indicators":
    [
        {
            "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "title": "demo",
            "application": "demo-test",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Informational",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": ["group1", "group2"]
        },
        {
            "indicatorValue": "2233223322332233223322332233223322332233223322332233223322332222",
            "indicatorType": "FileSha256",
            "title": "demo2",
            "application": "demo-test2",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Medium",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": []
        }
    ]
}
```

<span data-ttu-id="6277e-159">**응답**</span><span class="sxs-lookup"><span data-stu-id="6277e-159">**Response**</span></span>

<span data-ttu-id="6277e-160">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="6277e-160">Here is an example of the response.</span></span>

```json
{
    "value": [
        {
            "id": "2841",
            "indicator": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "isFailed": false,
            "failureReason": null
        },
        {
            "id": "2842",
            "indicator": "2233223322332233223322332233223322332233223322332233223322332222",
            "isFailed": false,
            "failureReason": null
        }
    ]
}
```

## <a name="related-topic"></a><span data-ttu-id="6277e-161">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6277e-161">Related topic</span></span>
- [<span data-ttu-id="6277e-162">지표 관리</span><span class="sxs-lookup"><span data-stu-id="6277e-162">Manage indicators</span></span>](manage-indicators.md)
