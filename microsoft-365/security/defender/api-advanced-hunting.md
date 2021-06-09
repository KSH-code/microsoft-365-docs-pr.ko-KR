---
title: Microsoft 365 Defender 고급 헌팅 API
description: Defender의 고급 헌팅 API를 사용하여 Microsoft 365 헌팅 쿼리를 실행하는 방법에 대해 자세히 알아보기
keywords: 고급 헌팅, API, api, M365 Defender, Microsoft 365 Defender
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
ms.openlocfilehash: 3ff62265783be846a95964164e372100fe1ef662
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769589"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="482c5-104">Microsoft 365 Defender 고급 헌팅 API</span><span class="sxs-lookup"><span data-stu-id="482c5-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="482c5-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="482c5-105">**Applies to:**</span></span>

- <span data-ttu-id="482c5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="482c5-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="482c5-107">일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="482c5-108">Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="482c5-109">[고급 헌팅은](advanced-hunting-overview.md) 특수하게 생성한 [](advanced-hunting-query-language.md) 쿼리를 사용하여 Defender에서 지난 30일 동안의 이벤트 데이터를 Microsoft 365 위협 헌팅 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="482c5-110">고급 헌팅 쿼리를 사용하여 비정상적인 활동을 검사하고, 가능한 위협을 감지하고, 공격에 대응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="482c5-111">고급 헌팅 API를 사용하면 프로그래밍적으로 이벤트 데이터를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="482c5-112">할당량 및 리소스 할당</span><span class="sxs-lookup"><span data-stu-id="482c5-112">Quotas and resource allocation</span></span>

<span data-ttu-id="482c5-113">다음 조건은 모든 쿼리와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="482c5-114">쿼리는 지난 30일 동안의 데이터를 탐색하고 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="482c5-115">결과는 최대 100,000개 행을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="482c5-116">테넌트당 분당 최대 15통의 통화를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="482c5-117">다음 15분 주기 후에 테넌트가 100%에 도달하면 쿼리가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-117">Queries are blocked if the tenant has reached 100% until after the next 15-minute cycle.</span></span>
5. <span data-ttu-id="482c5-118">단일 요청이 10분 이상 실행되는 경우 시간이 너무 까다로우며 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-118">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
6. <span data-ttu-id="482c5-119">HTTP 응답 코드는 전송된 요청 수 또는 할당된 실행 시간으로 할당량에 도달했다는 `429` 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-119">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="482c5-120">응답 본문을 읽고 도달한 제한을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-120">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="482c5-121">위에 나열된 모든 할당량(예: 분당 통화 수 15개)은 테넌트 크기당입니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-121">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="482c5-122">이러한 할당량은 최소값입니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-122">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="482c5-123">사용 권한</span><span class="sxs-lookup"><span data-stu-id="482c5-123">Permissions</span></span>

<span data-ttu-id="482c5-124">고급 헌팅 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-124">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="482c5-125">권한을 선택하는 방법을 포함하여 자세한 내용은 [Access the Microsoft 365 Defender Protection API를 참조합니다.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="482c5-125">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="482c5-126">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="482c5-126">Permission type</span></span> | <span data-ttu-id="482c5-127">사용 권한</span><span class="sxs-lookup"><span data-stu-id="482c5-127">Permission</span></span> | <span data-ttu-id="482c5-128">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="482c5-128">Permission display name</span></span>
-|-|-
<span data-ttu-id="482c5-129">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="482c5-129">Application</span></span> | <span data-ttu-id="482c5-130">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="482c5-130">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="482c5-131">고급 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="482c5-131">Run advanced queries</span></span>
<span data-ttu-id="482c5-132">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="482c5-132">Delegated (work or school account)</span></span> | <span data-ttu-id="482c5-133">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="482c5-133">AdvancedHunting.Read</span></span> | <span data-ttu-id="482c5-134">고급 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="482c5-134">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="482c5-135">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="482c5-135">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="482c5-136">사용자에게 '데이터 보기' AD 역할이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-136">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="482c5-137">사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-137">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="482c5-138">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="482c5-138">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="482c5-139">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="482c5-139">Request headers</span></span>

<span data-ttu-id="482c5-140">머리글</span><span class="sxs-lookup"><span data-stu-id="482c5-140">Header</span></span> | <span data-ttu-id="482c5-141">값</span><span class="sxs-lookup"><span data-stu-id="482c5-141">Value</span></span>
-|-
<span data-ttu-id="482c5-142">권한 부여</span><span class="sxs-lookup"><span data-stu-id="482c5-142">Authorization</span></span> | <span data-ttu-id="482c5-143">Bearer {token} **참고: 필수**</span><span class="sxs-lookup"><span data-stu-id="482c5-143">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="482c5-144">Content-Type</span><span class="sxs-lookup"><span data-stu-id="482c5-144">Content-Type</span></span> | <span data-ttu-id="482c5-145">application/json</span><span class="sxs-lookup"><span data-stu-id="482c5-145">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="482c5-146">요청 본문</span><span class="sxs-lookup"><span data-stu-id="482c5-146">Request body</span></span>

<span data-ttu-id="482c5-147">요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-147">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="482c5-148">매개 변수</span><span class="sxs-lookup"><span data-stu-id="482c5-148">Parameter</span></span> | <span data-ttu-id="482c5-149">유형</span><span class="sxs-lookup"><span data-stu-id="482c5-149">Type</span></span> | <span data-ttu-id="482c5-150">설명</span><span class="sxs-lookup"><span data-stu-id="482c5-150">Description</span></span>
-|-|-
<span data-ttu-id="482c5-151">Query</span><span class="sxs-lookup"><span data-stu-id="482c5-151">Query</span></span> | <span data-ttu-id="482c5-152">텍스트</span><span class="sxs-lookup"><span data-stu-id="482c5-152">Text</span></span> | <span data-ttu-id="482c5-153">실행할 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-153">The query to run.</span></span> <span data-ttu-id="482c5-154">**참고: 필수**</span><span class="sxs-lookup"><span data-stu-id="482c5-154">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="482c5-155">응답</span><span class="sxs-lookup"><span data-stu-id="482c5-155">Response</span></span>

<span data-ttu-id="482c5-156">성공하면 이 메서드는 응답 본문에 `200 OK` 및 _QueryResponse_ 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-156">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="482c5-157">응답 개체에는 세 가지 최상위 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-157">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="482c5-158">통계 - 쿼리 성능 통계 사전입니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-158">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="482c5-159">Schema - 응답의 schema, 각 열에 Name-Type 쌍의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-159">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="482c5-160">결과 - 고급 헌팅 이벤트 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-160">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="482c5-161">예시</span><span class="sxs-lookup"><span data-stu-id="482c5-161">Example</span></span>

<span data-ttu-id="482c5-162">다음 예제에서는 사용자가 아래 쿼리를 보내고 , 및 가 포함된 API 응답 개체를 `Stats` `Schema` `Results` 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="482c5-162">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="482c5-163">Query</span><span class="sxs-lookup"><span data-stu-id="482c5-163">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="482c5-164">응답 개체</span><span class="sxs-lookup"><span data-stu-id="482c5-164">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="482c5-165">관련 문서</span><span class="sxs-lookup"><span data-stu-id="482c5-165">Related articles</span></span>

- [<span data-ttu-id="482c5-166">Microsoft 365 Defender API에 액세스</span><span class="sxs-lookup"><span data-stu-id="482c5-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="482c5-167">API 제한 및 라이선싱에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="482c5-167">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="482c5-168">오류 코드 이해</span><span class="sxs-lookup"><span data-stu-id="482c5-168">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="482c5-169">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="482c5-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
