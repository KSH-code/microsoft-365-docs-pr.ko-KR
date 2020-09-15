---
title: 고급 구하기 Api
description: Microsoft Threat Protection API를 사용 하 여 고급 구하기 쿼리를 실행 하는 방법 알아보기
keywords: 고급 구하기, Api, api, MTP
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
ms.openlocfilehash: 92d5d2840963ae00ae0f03e3359f287371f770ee
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650468"
---
# <a name="advanced-hunting-apis"></a><span data-ttu-id="59c49-104">고급 구하기 Api</span><span class="sxs-lookup"><span data-stu-id="59c49-104">Advanced hunting APIs</span></span>

<span data-ttu-id="59c49-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="59c49-105">**Applies to:**</span></span>
- <span data-ttu-id="59c49-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="59c49-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="59c49-107">일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59c49-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="59c49-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="59c49-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="limitations"></a><span data-ttu-id="59c49-109">제한 사항</span><span class="sxs-lookup"><span data-stu-id="59c49-109">Limitations</span></span>
1. <span data-ttu-id="59c49-110">지난 30 일간의 데이터에 대해서만 쿼리를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59c49-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="59c49-111">결과에는 최대 10만 행이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59c49-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="59c49-112">실행 횟수는 테 넌 트 당 최대 15 개의 통화, 시간당 15 분의 실행 시간, 그리고 하루 동안 4 시간까지 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59c49-112">The number of executions is limited per tenant: up to 15 calls per minute, 15 minutes of running time every hour and 4 hours of running time a day.</span></span>
4. <span data-ttu-id="59c49-113">단일 요청의 최대 실행 시간은 10 분입니다.</span><span class="sxs-lookup"><span data-stu-id="59c49-113">The maximal execution time of a single request is 10 minutes.</span></span>

## <a name="permissions"></a><span data-ttu-id="59c49-114">사용 권한</span><span class="sxs-lookup"><span data-stu-id="59c49-114">Permissions</span></span>
<span data-ttu-id="59c49-115">이 API를 호출 하려면 다음 사용 권한 중 하나가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="59c49-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="59c49-116">사용 권한을 선택 하는 방법을 비롯 하 여 자세한 내용은 [Microsoft Threat Protection Api 액세스](api-access.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="59c49-116">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="59c49-117">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="59c49-117">Permission type</span></span> |   <span data-ttu-id="59c49-118">사용 권한</span><span class="sxs-lookup"><span data-stu-id="59c49-118">Permission</span></span>  |   <span data-ttu-id="59c49-119">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="59c49-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="59c49-120">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="59c49-120">Application</span></span> |   <span data-ttu-id="59c49-121">AdvancedHunting 모든</span><span class="sxs-lookup"><span data-stu-id="59c49-121">AdvancedHunting.Read.All</span></span> |  <span data-ttu-id="59c49-122">' 고급 쿼리 실행 '</span><span class="sxs-lookup"><span data-stu-id="59c49-122">'Run advanced queries'</span></span>
<span data-ttu-id="59c49-123">위임 됨 (회사 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="59c49-123">Delegated (work or school account)</span></span> | <span data-ttu-id="59c49-124">AdvancedHunting 읽기</span><span class="sxs-lookup"><span data-stu-id="59c49-124">AdvancedHunting.Read</span></span> | <span data-ttu-id="59c49-125">' 고급 쿼리 실행 '</span><span class="sxs-lookup"><span data-stu-id="59c49-125">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="59c49-126">사용자 자격 증명을 사용 하 여 토큰을 가져올 때:</span><span class="sxs-lookup"><span data-stu-id="59c49-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="59c49-127">사용자에 게 ' View Data ' AD 역할이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59c49-127">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="59c49-128">장치 그룹 설정에 따라 사용자에 게 장치에 대 한 액세스 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59c49-128">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="59c49-129">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="59c49-129">HTTP request</span></span>
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="59c49-130">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="59c49-130">Request headers</span></span>

<span data-ttu-id="59c49-131">Header</span><span class="sxs-lookup"><span data-stu-id="59c49-131">Header</span></span> | <span data-ttu-id="59c49-132">값</span><span class="sxs-lookup"><span data-stu-id="59c49-132">Value</span></span> 
:---|:---
<span data-ttu-id="59c49-133">권한 부여</span><span class="sxs-lookup"><span data-stu-id="59c49-133">Authorization</span></span> | <span data-ttu-id="59c49-134">전달자 {토큰}.</span><span class="sxs-lookup"><span data-stu-id="59c49-134">Bearer {token}.</span></span> <span data-ttu-id="59c49-135">**필수**입니다.</span><span class="sxs-lookup"><span data-stu-id="59c49-135">**Required**.</span></span>
<span data-ttu-id="59c49-136">Content-Type</span><span class="sxs-lookup"><span data-stu-id="59c49-136">Content-Type</span></span>    | <span data-ttu-id="59c49-137">application/json</span><span class="sxs-lookup"><span data-stu-id="59c49-137">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="59c49-138">요청 본문</span><span class="sxs-lookup"><span data-stu-id="59c49-138">Request body</span></span>
<span data-ttu-id="59c49-139">요청 본문에서 다음 매개 변수를 사용 하 여 JSON 개체를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="59c49-139">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="59c49-140">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59c49-140">Parameter</span></span> | <span data-ttu-id="59c49-141">유형</span><span class="sxs-lookup"><span data-stu-id="59c49-141">Type</span></span>    | <span data-ttu-id="59c49-142">설명</span><span class="sxs-lookup"><span data-stu-id="59c49-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="59c49-143">Query</span><span class="sxs-lookup"><span data-stu-id="59c49-143">Query</span></span> | <span data-ttu-id="59c49-144">텍스트</span><span class="sxs-lookup"><span data-stu-id="59c49-144">Text</span></span> |  <span data-ttu-id="59c49-145">실행할 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="59c49-145">The query to run.</span></span> <span data-ttu-id="59c49-146">**필수**입니다.</span><span class="sxs-lookup"><span data-stu-id="59c49-146">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="59c49-147">응답</span><span class="sxs-lookup"><span data-stu-id="59c49-147">Response</span></span>
<span data-ttu-id="59c49-148">성공 하면이 메서드는 응답 본문에 200 OK 및 _Queryresponse_ 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="59c49-148">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span> <br><br>

<span data-ttu-id="59c49-149">Response 개체는 3 개의 부분으로 나뉩니다 (속성).</span><span class="sxs-lookup"><span data-stu-id="59c49-149">The response object is divided to 3 parts (properties):</span></span><br>
1) <span data-ttu-id="59c49-150">```Stats``` -성능 통계를 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="59c49-150">```Stats``` - Query performance statistics.</span></span><br>
2) <span data-ttu-id="59c49-151">```Schema``` -응답의 스키마 이며 각 열에 대 한 이름 형식 쌍의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="59c49-151">```Schema``` - The schema of the response, a list of Name-Type pairs for each column.</span></span> <br>
3) <span data-ttu-id="59c49-152">```Results``` -고급 구하기 이벤트 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="59c49-152">```Results``` - A list of Advanced Hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="59c49-153">예제</span><span class="sxs-lookup"><span data-stu-id="59c49-153">Example</span></span>

<span data-ttu-id="59c49-154">요청이</span><span class="sxs-lookup"><span data-stu-id="59c49-154">Request</span></span>

<span data-ttu-id="59c49-155">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="59c49-155">Here is an example of the request.</span></span>


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

<span data-ttu-id="59c49-156">응답</span><span class="sxs-lookup"><span data-stu-id="59c49-156">Response</span></span>

<span data-ttu-id="59c49-157">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="59c49-157">Here is an example of the response.</span></span>


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

## <a name="related-topic"></a><span data-ttu-id="59c49-158">관련 항목</span><span class="sxs-lookup"><span data-stu-id="59c49-158">Related topic</span></span>
- [<span data-ttu-id="59c49-159">Microsoft Threat Protection Api 액세스</span><span class="sxs-lookup"><span data-stu-id="59c49-159">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
