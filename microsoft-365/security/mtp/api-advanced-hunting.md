---
title: Microsoft 365 Defender 고급 헌팅 API
description: Microsoft 365 Defender의 고급 헌팅 API를 사용하여 고급 헌팅 쿼리를 실행하는 방법 학습
keywords: 고급 헌팅, API, api, MTP, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 4213773c3305c28f0913013d8f7634c083811f52
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932085"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="33fae-104">Microsoft 365 Defender 고급 헌팅 API</span><span class="sxs-lookup"><span data-stu-id="33fae-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="33fae-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="33fae-105">**Applies to:**</span></span>

- <span data-ttu-id="33fae-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="33fae-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33fae-107">일부 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 미리 판매된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="33fae-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="33fae-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="33fae-109">[고급 헌팅은](advanced-hunting-overview.md) Microsoft [365](advanced-hunting-query-language.md) Defender에서 지난 30일 동안의 이벤트 데이터를 검사하기 위해 특별히 생성한 쿼리를 사용하는 위협 헌팅 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="33fae-110">고급 헌팅 쿼리를 사용하여 비정상적인 활동을 검사하고, 가능한 위협을 감지하고, 공격에 대응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="33fae-111">고급 헌팅 API를 사용하면 프로그래밍적으로 이벤트 데이터를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="33fae-112">할당량 및 리소스 할당</span><span class="sxs-lookup"><span data-stu-id="33fae-112">Quotas and resource allocation</span></span>

<span data-ttu-id="33fae-113">다음 조건은 모든 쿼리와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="33fae-114">쿼리는 지난 30일 동안의 데이터를 탐색하고 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="33fae-115">결과는 최대 100,000개 행을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="33fae-116">테넌트당 분당 최대 10통의 통화를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-116">You can make up to 10 calls per minute per tenant.</span></span>
4. <span data-ttu-id="33fae-117">테넌트당 시간당 10분의 실행 시간이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="33fae-118">테넌트당 총 4시간의 실행 시간이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-118">You have four total hours of running time day per tenant.</span></span>
6. <span data-ttu-id="33fae-119">단일 요청이 10분 넘게 실행되는 경우 시간이 너무 까다로우며 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="33fae-120">HTTP 응답 코드는 전송된 요청 수 또는 할당된 실행 시간으로 할당량에 도달했다는 `429` 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="33fae-121">응답 본문에는 도달한 할당량에 따라 다시 설정될 때까지의 시간이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-121">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="33fae-122">권한</span><span class="sxs-lookup"><span data-stu-id="33fae-122">Permissions</span></span>

<span data-ttu-id="33fae-123">고급 헌팅 API를 호출하려면 다음 권한 중 하나를 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-123">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="33fae-124">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Microsoft 365 Defender Protection API 액세스를 참조합니다.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="33fae-124">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="33fae-125">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="33fae-125">Permission type</span></span> | <span data-ttu-id="33fae-126">사용 권한</span><span class="sxs-lookup"><span data-stu-id="33fae-126">Permission</span></span> | <span data-ttu-id="33fae-127">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="33fae-127">Permission display name</span></span>
-|-|-
<span data-ttu-id="33fae-128">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="33fae-128">Application</span></span> | <span data-ttu-id="33fae-129">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="33fae-129">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="33fae-130">고급 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="33fae-130">Run advanced queries</span></span>
<span data-ttu-id="33fae-131">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="33fae-131">Delegated (work or school account)</span></span> | <span data-ttu-id="33fae-132">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="33fae-132">AdvancedHunting.Read</span></span> | <span data-ttu-id="33fae-133">고급 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="33fae-133">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="33fae-134">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="33fae-134">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="33fae-135">사용자에게 '데이터 보기' AD 역할이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-135">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="33fae-136">사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-136">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="33fae-137">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="33fae-137">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="33fae-138">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="33fae-138">Request headers</span></span>

<span data-ttu-id="33fae-139">Header</span><span class="sxs-lookup"><span data-stu-id="33fae-139">Header</span></span> | <span data-ttu-id="33fae-140">값</span><span class="sxs-lookup"><span data-stu-id="33fae-140">Value</span></span>
-|-
<span data-ttu-id="33fae-141">권한 부여</span><span class="sxs-lookup"><span data-stu-id="33fae-141">Authorization</span></span> | <span data-ttu-id="33fae-142">Bearer {token} **참고: 필수**</span><span class="sxs-lookup"><span data-stu-id="33fae-142">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="33fae-143">Content-Type</span><span class="sxs-lookup"><span data-stu-id="33fae-143">Content-Type</span></span> | <span data-ttu-id="33fae-144">application/json</span><span class="sxs-lookup"><span data-stu-id="33fae-144">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="33fae-145">요청 본문</span><span class="sxs-lookup"><span data-stu-id="33fae-145">Request body</span></span>

<span data-ttu-id="33fae-146">요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-146">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="33fae-147">매개 변수</span><span class="sxs-lookup"><span data-stu-id="33fae-147">Parameter</span></span> | <span data-ttu-id="33fae-148">유형</span><span class="sxs-lookup"><span data-stu-id="33fae-148">Type</span></span> | <span data-ttu-id="33fae-149">설명</span><span class="sxs-lookup"><span data-stu-id="33fae-149">Description</span></span>
-|-|-
<span data-ttu-id="33fae-150">Query</span><span class="sxs-lookup"><span data-stu-id="33fae-150">Query</span></span> | <span data-ttu-id="33fae-151">텍스트</span><span class="sxs-lookup"><span data-stu-id="33fae-151">Text</span></span> | <span data-ttu-id="33fae-152">실행할 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-152">The query to run.</span></span> <span data-ttu-id="33fae-153">**참고: 필수**</span><span class="sxs-lookup"><span data-stu-id="33fae-153">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="33fae-154">응답</span><span class="sxs-lookup"><span data-stu-id="33fae-154">Response</span></span>

<span data-ttu-id="33fae-155">성공하면 이 메서드는 응답 본문에 `200 OK` _QueryResponse_ 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-155">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="33fae-156">응답 개체에는 세 가지 최상위 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-156">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="33fae-157">통계 - 쿼리 성능 통계 사전입니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-157">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="33fae-158">schema - 응답의 schema, 각 열에 Name-Type 쌍의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-158">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="33fae-159">결과 - 고급 헌팅 이벤트 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="33fae-159">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="33fae-160">예시</span><span class="sxs-lookup"><span data-stu-id="33fae-160">Example</span></span>

<span data-ttu-id="33fae-161">다음 예제에서는 사용자가 아래 쿼리를 보내고 , 및 . `Stats` `Schema` `Results`</span><span class="sxs-lookup"><span data-stu-id="33fae-161">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="33fae-162">Query</span><span class="sxs-lookup"><span data-stu-id="33fae-162">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="33fae-163">응답 개체</span><span class="sxs-lookup"><span data-stu-id="33fae-163">Response object</span></span>

```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}
```

## <a name="related-articles"></a><span data-ttu-id="33fae-164">관련 문서</span><span class="sxs-lookup"><span data-stu-id="33fae-164">Related articles</span></span>

- [<span data-ttu-id="33fae-165">Microsoft 365 Defender API 액세스</span><span class="sxs-lookup"><span data-stu-id="33fae-165">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="33fae-166">API 제한 및 라이선싱에 대해 자세히</span><span class="sxs-lookup"><span data-stu-id="33fae-166">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="33fae-167">오류 코드 이해</span><span class="sxs-lookup"><span data-stu-id="33fae-167">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="33fae-168">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="33fae-168">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
