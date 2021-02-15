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
ms.openlocfilehash: 99f39a10de6231a72220c5c2a90ec915b1a4e44a
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988119"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="ccde6-104">Microsoft 365 Defender 고급 헌팅 API</span><span class="sxs-lookup"><span data-stu-id="ccde6-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="ccde6-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ccde6-105">**Applies to:**</span></span>

- <span data-ttu-id="ccde6-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="ccde6-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ccde6-107">일부 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 미리 판매된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="ccde6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="ccde6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="ccde6-109">[고급 헌팅은](advanced-hunting-overview.md) Microsoft [365](advanced-hunting-query-language.md) Defender에서 지난 30일 동안의 이벤트 데이터를 검사하기 위해 특별히 생성한 쿼리를 사용하는 위협 헌팅 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="ccde6-110">고급 헌팅 쿼리를 사용하여 비정상적인 활동을 검사하고, 가능한 위협을 감지하고, 공격에 대응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="ccde6-111">고급 헌팅 API를 사용하면 프로그래밍하여 이벤트 데이터를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="ccde6-112">할당량 및 리소스 할당</span><span class="sxs-lookup"><span data-stu-id="ccde6-112">Quotas and resource allocation</span></span>

<span data-ttu-id="ccde6-113">다음 조건은 모든 쿼리와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="ccde6-114">쿼리는 지난 30일 동안의 데이터를 탐색하고 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="ccde6-115">결과는 최대 100,000개 행을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="ccde6-116">테넌트당 분당 최대 15통의 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="ccde6-117">테넌트당 시간당 10분의 실행 시간이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="ccde6-118">테넌트당 하루 총 4시간의 실행 시간이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-118">You have four total hours of running time per day per tenant.</span></span>
6. <span data-ttu-id="ccde6-119">단일 요청이 10분 넘게 실행되는 경우 시간이 지났다가 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="ccde6-120">HTTP 응답 코드는 전송된 요청 수 또는 할당된 실행 시간으로 할당량에 도달했다는 `429` 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="ccde6-121">응답 본문을 읽고 도달한 제한을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-121">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="ccde6-122">위에 나열된 모든 할당량(예: 분당 통화 15개)은 테넌트 크기당입니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-122">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="ccde6-123">이러한 할당량은 최소값입니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-123">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="ccde6-124">사용 권한</span><span class="sxs-lookup"><span data-stu-id="ccde6-124">Permissions</span></span>

<span data-ttu-id="ccde6-125">고급 헌팅 API를 호출하려면 다음 권한 중 하나를 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-125">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="ccde6-126">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Microsoft 365 Defender Protection API 액세스 참조](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="ccde6-126">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="ccde6-127">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="ccde6-127">Permission type</span></span> | <span data-ttu-id="ccde6-128">사용 권한</span><span class="sxs-lookup"><span data-stu-id="ccde6-128">Permission</span></span> | <span data-ttu-id="ccde6-129">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="ccde6-129">Permission display name</span></span>
-|-|-
<span data-ttu-id="ccde6-130">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="ccde6-130">Application</span></span> | <span data-ttu-id="ccde6-131">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="ccde6-131">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="ccde6-132">고급 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="ccde6-132">Run advanced queries</span></span>
<span data-ttu-id="ccde6-133">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="ccde6-133">Delegated (work or school account)</span></span> | <span data-ttu-id="ccde6-134">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="ccde6-134">AdvancedHunting.Read</span></span> | <span data-ttu-id="ccde6-135">고급 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="ccde6-135">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="ccde6-136">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="ccde6-136">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="ccde6-137">사용자에게 '데이터 보기' AD 역할이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-137">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="ccde6-138">사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-138">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="ccde6-139">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="ccde6-139">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="ccde6-140">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="ccde6-140">Request headers</span></span>

<span data-ttu-id="ccde6-141">Header</span><span class="sxs-lookup"><span data-stu-id="ccde6-141">Header</span></span> | <span data-ttu-id="ccde6-142">값</span><span class="sxs-lookup"><span data-stu-id="ccde6-142">Value</span></span>
-|-
<span data-ttu-id="ccde6-143">권한 부여</span><span class="sxs-lookup"><span data-stu-id="ccde6-143">Authorization</span></span> | <span data-ttu-id="ccde6-144">Bearer {token} **참고: 필수**</span><span class="sxs-lookup"><span data-stu-id="ccde6-144">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="ccde6-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="ccde6-145">Content-Type</span></span> | <span data-ttu-id="ccde6-146">application/json</span><span class="sxs-lookup"><span data-stu-id="ccde6-146">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="ccde6-147">요청 본문</span><span class="sxs-lookup"><span data-stu-id="ccde6-147">Request body</span></span>

<span data-ttu-id="ccde6-148">요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-148">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="ccde6-149">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ccde6-149">Parameter</span></span> | <span data-ttu-id="ccde6-150">유형</span><span class="sxs-lookup"><span data-stu-id="ccde6-150">Type</span></span> | <span data-ttu-id="ccde6-151">설명</span><span class="sxs-lookup"><span data-stu-id="ccde6-151">Description</span></span>
-|-|-
<span data-ttu-id="ccde6-152">Query</span><span class="sxs-lookup"><span data-stu-id="ccde6-152">Query</span></span> | <span data-ttu-id="ccde6-153">텍스트</span><span class="sxs-lookup"><span data-stu-id="ccde6-153">Text</span></span> | <span data-ttu-id="ccde6-154">실행할 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-154">The query to run.</span></span> <span data-ttu-id="ccde6-155">**참고: 필수**</span><span class="sxs-lookup"><span data-stu-id="ccde6-155">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="ccde6-156">응답</span><span class="sxs-lookup"><span data-stu-id="ccde6-156">Response</span></span>

<span data-ttu-id="ccde6-157">성공하면 이 메서드는 응답 본문에 `200 OK` _QueryResponse_ 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-157">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="ccde6-158">응답 개체에는 세 가지 최상위 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-158">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="ccde6-159">통계 - 쿼리 성능 통계 사전입니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-159">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="ccde6-160">schema - 응답의 schema, 각 열에 Name-Type 쌍의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-160">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="ccde6-161">결과 - 고급 헌팅 이벤트 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-161">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="ccde6-162">예시</span><span class="sxs-lookup"><span data-stu-id="ccde6-162">Example</span></span>

<span data-ttu-id="ccde6-163">다음 예제에서는 사용자가 아래에서 쿼리를 보내고 , 및 . 및 를 포함하는 API 응답 `Stats` 개체를 `Schema` `Results` 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="ccde6-163">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="ccde6-164">Query</span><span class="sxs-lookup"><span data-stu-id="ccde6-164">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="ccde6-165">응답 개체</span><span class="sxs-lookup"><span data-stu-id="ccde6-165">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="ccde6-166">관련 문서</span><span class="sxs-lookup"><span data-stu-id="ccde6-166">Related articles</span></span>

- [<span data-ttu-id="ccde6-167">Microsoft 365 Defender API 액세스</span><span class="sxs-lookup"><span data-stu-id="ccde6-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="ccde6-168">API 제한 및 라이선싱에 대해 자세히</span><span class="sxs-lookup"><span data-stu-id="ccde6-168">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="ccde6-169">오류 코드 이해</span><span class="sxs-lookup"><span data-stu-id="ccde6-169">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="ccde6-170">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="ccde6-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
