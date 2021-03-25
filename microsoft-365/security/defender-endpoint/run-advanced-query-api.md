---
title: 고급 헌팅 API
ms.reviewer: ''
description: 고급 헌팅 API를 사용하여 끝점용 Microsoft Defender에서 고급 쿼리를 실행하는 방법을 학습합니다. 제한 사항을 찾아 예제를 참조합니다.
keywords: api, 지원되는 api, 고급 헌팅, 쿼리
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
ms.openlocfilehash: caf7a1bacfd726c560356d542bec3cf56c6b39d4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200200"
---
# <a name="advanced-hunting-api"></a><span data-ttu-id="6ec01-105">고급 헌팅 API</span><span class="sxs-lookup"><span data-stu-id="6ec01-105">Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6ec01-106">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="6ec01-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="6ec01-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="6ec01-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6ec01-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6ec01-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a><span data-ttu-id="6ec01-109">제한 사항</span><span class="sxs-lookup"><span data-stu-id="6ec01-109">Limitations</span></span>
1. <span data-ttu-id="6ec01-110">지난 30일 동안의 데이터에 대한 쿼리만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ec01-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="6ec01-111">결과에는 최대 100,000개 행이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ec01-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="6ec01-112">실행 수는 테넌트당 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ec01-112">The number of executions is limited per tenant:</span></span>
   - <span data-ttu-id="6ec01-113">API 호출: 분당 최대 45통입니다.</span><span class="sxs-lookup"><span data-stu-id="6ec01-113">API calls: Up to 45 calls per minute.</span></span>
   - <span data-ttu-id="6ec01-114">실행 시간: 매시간 10분의 실행 시간 및 하루 3시간의 실행 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6ec01-114">Execution time: 10 minutes of running time every hour and 3 hours of running time a day.</span></span>
4. <span data-ttu-id="6ec01-115">단일 요청의 최대 실행 시간은 10분입니다.</span><span class="sxs-lookup"><span data-stu-id="6ec01-115">The maximal execution time of a single request is 10 minutes.</span></span>
5. <span data-ttu-id="6ec01-116">429 응답은 요청 수 또는 CPU에 의해 할당량 제한에 도달하는 경우를 나타내게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ec01-116">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="6ec01-117">응답 본문을 읽고 도달한 제한을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="6ec01-117">Read response body to understand what limit has been reached.</span></span> 

## <a name="permissions"></a><span data-ttu-id="6ec01-118">사용 권한</span><span class="sxs-lookup"><span data-stu-id="6ec01-118">Permissions</span></span>
<span data-ttu-id="6ec01-119">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6ec01-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6ec01-120">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6ec01-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="6ec01-121">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="6ec01-121">Permission type</span></span> |   <span data-ttu-id="6ec01-122">사용 권한</span><span class="sxs-lookup"><span data-stu-id="6ec01-122">Permission</span></span>  |   <span data-ttu-id="6ec01-123">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="6ec01-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6ec01-124">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="6ec01-124">Application</span></span> |   <span data-ttu-id="6ec01-125">AdvancedQuery.Read.All</span><span class="sxs-lookup"><span data-stu-id="6ec01-125">AdvancedQuery.Read.All</span></span> |    <span data-ttu-id="6ec01-126">'고급 쿼리 실행'</span><span class="sxs-lookup"><span data-stu-id="6ec01-126">'Run advanced queries'</span></span>
<span data-ttu-id="6ec01-127">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="6ec01-127">Delegated (work or school account)</span></span> | <span data-ttu-id="6ec01-128">AdvancedQuery.Read</span><span class="sxs-lookup"><span data-stu-id="6ec01-128">AdvancedQuery.Read</span></span> | <span data-ttu-id="6ec01-129">'고급 쿼리 실행'</span><span class="sxs-lookup"><span data-stu-id="6ec01-129">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="6ec01-130">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="6ec01-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="6ec01-131">사용자에게 '데이터 보기' AD 역할이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6ec01-131">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="6ec01-132">사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="6ec01-132">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="6ec01-133">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="6ec01-133">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a><span data-ttu-id="6ec01-134">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="6ec01-134">Request headers</span></span>

<span data-ttu-id="6ec01-135">머리글</span><span class="sxs-lookup"><span data-stu-id="6ec01-135">Header</span></span> | <span data-ttu-id="6ec01-136">값</span><span class="sxs-lookup"><span data-stu-id="6ec01-136">Value</span></span> 
:---|:---
<span data-ttu-id="6ec01-137">권한 부여</span><span class="sxs-lookup"><span data-stu-id="6ec01-137">Authorization</span></span> | <span data-ttu-id="6ec01-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="6ec01-138">Bearer {token}.</span></span> <span data-ttu-id="6ec01-139">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="6ec01-139">**Required**.</span></span>
<span data-ttu-id="6ec01-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="6ec01-140">Content-Type</span></span>    | <span data-ttu-id="6ec01-141">application/json</span><span class="sxs-lookup"><span data-stu-id="6ec01-141">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="6ec01-142">요청 본문</span><span class="sxs-lookup"><span data-stu-id="6ec01-142">Request body</span></span>
<span data-ttu-id="6ec01-143">요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6ec01-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="6ec01-144">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6ec01-144">Parameter</span></span> | <span data-ttu-id="6ec01-145">유형</span><span class="sxs-lookup"><span data-stu-id="6ec01-145">Type</span></span>    | <span data-ttu-id="6ec01-146">설명</span><span class="sxs-lookup"><span data-stu-id="6ec01-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="6ec01-147">Query</span><span class="sxs-lookup"><span data-stu-id="6ec01-147">Query</span></span> | <span data-ttu-id="6ec01-148">텍스트</span><span class="sxs-lookup"><span data-stu-id="6ec01-148">Text</span></span> |  <span data-ttu-id="6ec01-149">실행할 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="6ec01-149">The query to run.</span></span> <span data-ttu-id="6ec01-150">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="6ec01-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="6ec01-151">응답</span><span class="sxs-lookup"><span data-stu-id="6ec01-151">Response</span></span>
<span data-ttu-id="6ec01-152">성공하면 이 메서드는 응답 본문에 200 OK 및 _QueryResponse_ 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6ec01-152">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="6ec01-153">예제</span><span class="sxs-lookup"><span data-stu-id="6ec01-153">Example</span></span>

<span data-ttu-id="6ec01-154">요청</span><span class="sxs-lookup"><span data-stu-id="6ec01-154">Request</span></span>

<span data-ttu-id="6ec01-155">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="6ec01-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents  
    | where InitiatingProcessFileName =~ 'powershell.exe'
    | where ProcessCommandLine contains 'appdata'
    | project Timestamp, FileName, InitiatingProcessFileName, DeviceId
    | limit 2"
}
```

<span data-ttu-id="6ec01-156">응답</span><span class="sxs-lookup"><span data-stu-id="6ec01-156">Response</span></span>

<span data-ttu-id="6ec01-157">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="6ec01-157">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="6ec01-158">여기에 표시된 응답 개체는 표시가 까다로우면 자르기될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ec01-158">The response object shown here may be truncated for brevity.</span></span> <span data-ttu-id="6ec01-159">모든 속성은 실제 호출에서 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ec01-159">All of the properties will be returned from an actual call.</span></span>

```json
{
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
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topic"></a><span data-ttu-id="6ec01-160">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6ec01-160">Related topic</span></span>
- [<span data-ttu-id="6ec01-161">끝점 API용 Microsoft Defender 소개</span><span class="sxs-lookup"><span data-stu-id="6ec01-161">Microsoft Defender for Endpoint APIs introduction</span></span>](apis-intro.md)
- [<span data-ttu-id="6ec01-162">포털에서 고급 헌팅</span><span class="sxs-lookup"><span data-stu-id="6ec01-162">Advanced Hunting from Portal</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6ec01-163">PowerShell을 사용한 고급 헌팅</span><span class="sxs-lookup"><span data-stu-id="6ec01-163">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)
