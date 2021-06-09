---
title: 목록 표시기 API
description: 목록 표시기 API를 사용하여 끝점용 Microsoft Defender에서 모든 활성 표시기 컬렉션을 검색하는 방법을 배워보세요.
keywords: api, 공용 api, 지원되는 api, Indicators 컬렉션
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d9ec8610957af0bc7741848e7c7bd4fe850f5e32
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770430"
---
# <a name="list-indicators-api"></a><span data-ttu-id="0dcda-104">목록 표시기 API</span><span class="sxs-lookup"><span data-stu-id="0dcda-104">List Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0dcda-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="0dcda-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="0dcda-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="0dcda-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0dcda-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0dcda-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="0dcda-108">API 설명</span><span class="sxs-lookup"><span data-stu-id="0dcda-108">API description</span></span>
<span data-ttu-id="0dcda-109">모든 활성 표시기 [컬렉션을 검색합니다.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="0dcda-109">Retrieves a collection of all active [Indicators](ti-indicator.md).</span></span>
<br><span data-ttu-id="0dcda-110">[OData V4 쿼리를 지원합니다.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="0dcda-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="0dcda-111">OData의 쿼리는 ```$filter``` , , , 및 ```indicatorValue``` ```indicatorType``` ```creationTimeDateTimeUtc``` ```createdBy``` ```action``` 속성에서 ```severity``` 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dcda-111">The OData's ```$filter``` query is supported on: ```indicatorValue```, ```indicatorType```, ```creationTimeDateTimeUtc```, ```createdBy```, ```action``` and ```severity``` properties.</span></span>
<br><span data-ttu-id="0dcda-112">[끝점용 Microsoft Defender를 사용하여 OData 쿼리 예제 보기](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="0dcda-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="0dcda-113">제한 사항</span><span class="sxs-lookup"><span data-stu-id="0dcda-113">Limitations</span></span>
1. <span data-ttu-id="0dcda-114">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="0dcda-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="0dcda-115">사용 권한</span><span class="sxs-lookup"><span data-stu-id="0dcda-115">Permissions</span></span>
<span data-ttu-id="0dcda-116">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0dcda-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0dcda-117">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [시작을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="0dcda-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="0dcda-118">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="0dcda-118">Permission type</span></span> |   <span data-ttu-id="0dcda-119">사용 권한</span><span class="sxs-lookup"><span data-stu-id="0dcda-119">Permission</span></span>  |   <span data-ttu-id="0dcda-120">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="0dcda-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0dcda-121">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="0dcda-121">Application</span></span> |   <span data-ttu-id="0dcda-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="0dcda-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="0dcda-123">'읽기 및 쓰기 표시기'</span><span class="sxs-lookup"><span data-stu-id="0dcda-123">'Read and write Indicators'</span></span>
<span data-ttu-id="0dcda-124">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="0dcda-124">Application</span></span> |   <span data-ttu-id="0dcda-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="0dcda-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="0dcda-126">'모든 지표 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="0dcda-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="0dcda-127">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="0dcda-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="0dcda-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="0dcda-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="0dcda-129">'읽기 및 쓰기 표시기'</span><span class="sxs-lookup"><span data-stu-id="0dcda-129">'Read and write Indicators'</span></span>

## <a name="http-request"></a><span data-ttu-id="0dcda-130">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="0dcda-130">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="0dcda-131">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="0dcda-131">Request headers</span></span>

<span data-ttu-id="0dcda-132">이름</span><span class="sxs-lookup"><span data-stu-id="0dcda-132">Name</span></span> | <span data-ttu-id="0dcda-133">유형</span><span class="sxs-lookup"><span data-stu-id="0dcda-133">Type</span></span> | <span data-ttu-id="0dcda-134">설명</span><span class="sxs-lookup"><span data-stu-id="0dcda-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="0dcda-135">권한 부여</span><span class="sxs-lookup"><span data-stu-id="0dcda-135">Authorization</span></span> | <span data-ttu-id="0dcda-136">String</span><span class="sxs-lookup"><span data-stu-id="0dcda-136">String</span></span> | <span data-ttu-id="0dcda-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="0dcda-137">Bearer {token}.</span></span> <span data-ttu-id="0dcda-138">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="0dcda-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="0dcda-139">요청 본문</span><span class="sxs-lookup"><span data-stu-id="0dcda-139">Request body</span></span>
<span data-ttu-id="0dcda-140">비어 있음</span><span class="sxs-lookup"><span data-stu-id="0dcda-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="0dcda-141">응답</span><span class="sxs-lookup"><span data-stu-id="0dcda-141">Response</span></span>
<span data-ttu-id="0dcda-142">성공하면 이 메서드는 표시기 엔터티 컬렉션이 있는 200, 확인 응답 [코드를](ti-indicator.md) 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0dcda-142">If successful, this method returns 200, Ok response code with a collection of [Indicator](ti-indicator.md) entities.</span></span>

>[!Note]
> <span data-ttu-id="0dcda-143">응용 프로그램에 'Ti.ReadWrite.All' 권한이 있는 경우 모든 지표에 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dcda-143">If the Application has 'Ti.ReadWrite.All' permission, it will be exposed to all Indicators.</span></span> <span data-ttu-id="0dcda-144">그렇지 않으면 만든 표시기에만 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dcda-144">Otherwise, it will be exposed only to the Indicators it created.</span></span>

## <a name="example-1"></a><span data-ttu-id="0dcda-145">예제 1:</span><span class="sxs-lookup"><span data-stu-id="0dcda-145">Example 1:</span></span>

<span data-ttu-id="0dcda-146">**요청**</span><span class="sxs-lookup"><span data-stu-id="0dcda-146">**Request**</span></span>

<span data-ttu-id="0dcda-147">다음은 모든 지표를 나타내는 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0dcda-147">Here is an example of a request that gets all Indicators</span></span>

```
GET https://api.securitycenter.microsoft.com/api/indicators
```

<span data-ttu-id="0dcda-148">**응답**</span><span class="sxs-lookup"><span data-stu-id="0dcda-148">**Response**</span></span>

<span data-ttu-id="0dcda-149">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0dcda-149">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "995",
            "indicatorValue": "12.13.14.15",
            "indicatorType": "IpAddress",
            "action": "Alert",
            "application": "demo-test",
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T11:15:35.3688259Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "test",
            "rbacGroupNames": []
        },
        {
            "id": "996",
            "indicatorValue": "220e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="0dcda-150">예제 2:</span><span class="sxs-lookup"><span data-stu-id="0dcda-150">Example 2:</span></span>

<span data-ttu-id="0dcda-151">**요청**</span><span class="sxs-lookup"><span data-stu-id="0dcda-151">**Request**</span></span>

<span data-ttu-id="0dcda-152">다음은 'AlertAndBlock' 작업이 있는 모든 지표를 나타내는 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0dcda-152">Here is an example of a request that gets all Indicators with 'AlertAndBlock' action</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/indicators?$filter=action+eq+'AlertAndBlock'
```

<span data-ttu-id="0dcda-153">**응답**</span><span class="sxs-lookup"><span data-stu-id="0dcda-153">**Response**</span></span>

<span data-ttu-id="0dcda-154">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0dcda-154">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "997",
            "indicatorValue": "111e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```
