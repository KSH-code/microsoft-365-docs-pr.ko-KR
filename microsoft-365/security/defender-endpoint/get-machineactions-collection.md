---
title: MachineActions API 나열
description: List MachineActions API를 사용하여 끝점용 Microsoft Defender에서 컴퓨터 작업 컬렉션을 검색하는 방법을 배워보세요.
keywords: api, 그래프 api, 지원되는 api, machineaction 컬렉션
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
ms.openlocfilehash: 2ee9a4e29dded3e299ffbb2c2997fd02f32d1abf
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771120"
---
# <a name="list-machineactions-api"></a><span data-ttu-id="d2284-104">MachineActions API 나열</span><span class="sxs-lookup"><span data-stu-id="d2284-104">List MachineActions API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d2284-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="d2284-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="d2284-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="d2284-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d2284-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d2284-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="d2284-108">API 설명</span><span class="sxs-lookup"><span data-stu-id="d2284-108">API description</span></span>
<span data-ttu-id="d2284-109">Machine [Actions 컬렉션을 검색합니다.](machineaction.md)</span><span class="sxs-lookup"><span data-stu-id="d2284-109">Retrieves a collection of [Machine Actions](machineaction.md).</span></span>
<br><span data-ttu-id="d2284-110">[OData V4 쿼리를 지원합니다.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="d2284-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="d2284-111">OData의 쿼리는 ```$filter``` ```status``` , , ```machineId``` 및 ```type``` ```requestor``` 속성에서 ```creationDateTimeUtc``` 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2284-111">The OData's ```$filter``` query is supported on: ```status```, ```machineId```, ```type```, ```requestor``` and ```creationDateTimeUtc``` properties.</span></span>
<br><span data-ttu-id="d2284-112">[끝점용 Microsoft Defender를 사용하여 OData 쿼리 예제 보기](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="d2284-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="d2284-113">제한 사항</span><span class="sxs-lookup"><span data-stu-id="d2284-113">Limitations</span></span>
1. <span data-ttu-id="d2284-114">최대 페이지 크기는 10,000개입니다.</span><span class="sxs-lookup"><span data-stu-id="d2284-114">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="d2284-115">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="d2284-115">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="d2284-116">사용 권한</span><span class="sxs-lookup"><span data-stu-id="d2284-116">Permissions</span></span>
<span data-ttu-id="d2284-117">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d2284-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d2284-118">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d2284-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="d2284-119">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="d2284-119">Permission type</span></span> |   <span data-ttu-id="d2284-120">사용 권한</span><span class="sxs-lookup"><span data-stu-id="d2284-120">Permission</span></span>  |   <span data-ttu-id="d2284-121">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="d2284-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d2284-122">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="d2284-122">Application</span></span> |   <span data-ttu-id="d2284-123">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="d2284-123">Machine.Read.All</span></span> |  <span data-ttu-id="d2284-124">'모든 컴퓨터 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="d2284-124">'Read all machine profiles'</span></span>
<span data-ttu-id="d2284-125">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="d2284-125">Application</span></span> |   <span data-ttu-id="d2284-126">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="d2284-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="d2284-127">'모든 컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="d2284-127">'Read and write all machine information'</span></span>
<span data-ttu-id="d2284-128">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="d2284-128">Delegated (work or school account)</span></span> | <span data-ttu-id="d2284-129">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="d2284-129">Machine.Read</span></span> | <span data-ttu-id="d2284-130">'컴퓨터 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="d2284-130">'Read machine information'</span></span>
<span data-ttu-id="d2284-131">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="d2284-131">Delegated (work or school account)</span></span> | <span data-ttu-id="d2284-132">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d2284-132">Machine.ReadWrite</span></span> | <span data-ttu-id="d2284-133">'컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="d2284-133">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="d2284-134">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="d2284-134">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="d2284-135">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="d2284-135">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="d2284-136">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="d2284-136">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

## <a name="request-headers"></a><span data-ttu-id="d2284-137">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="d2284-137">Request headers</span></span>

<span data-ttu-id="d2284-138">이름</span><span class="sxs-lookup"><span data-stu-id="d2284-138">Name</span></span> | <span data-ttu-id="d2284-139">유형</span><span class="sxs-lookup"><span data-stu-id="d2284-139">Type</span></span> | <span data-ttu-id="d2284-140">설명</span><span class="sxs-lookup"><span data-stu-id="d2284-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="d2284-141">권한 부여</span><span class="sxs-lookup"><span data-stu-id="d2284-141">Authorization</span></span> | <span data-ttu-id="d2284-142">String</span><span class="sxs-lookup"><span data-stu-id="d2284-142">String</span></span> | <span data-ttu-id="d2284-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="d2284-143">Bearer {token}.</span></span> <span data-ttu-id="d2284-144">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="d2284-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="d2284-145">요청 본문</span><span class="sxs-lookup"><span data-stu-id="d2284-145">Request body</span></span>
<span data-ttu-id="d2284-146">비어 있음</span><span class="sxs-lookup"><span data-stu-id="d2284-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d2284-147">응답</span><span class="sxs-lookup"><span data-stu-id="d2284-147">Response</span></span>
<span data-ttu-id="d2284-148">성공하면 이 메서드는 [machineAction](machineaction.md) 엔터티 컬렉션이 있는 200, 확인 응답 코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d2284-148">If successful, this method returns 200, Ok response code with a collection of [machineAction](machineaction.md) entities.</span></span>


## <a name="example-1"></a><span data-ttu-id="d2284-149">예 1</span><span class="sxs-lookup"><span data-stu-id="d2284-149">Example 1</span></span>

<span data-ttu-id="d2284-150">**요청**</span><span class="sxs-lookup"><span data-stu-id="d2284-150">**Request**</span></span>

<span data-ttu-id="d2284-151">다음은 MachineAction이 세 개 있는 조직에 대한 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d2284-151">Here is an example of the request on an organization that has three MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

<span data-ttu-id="d2284-152">**응답**</span><span class="sxs-lookup"><span data-stu-id="d2284-152">**Response**</span></span>

<span data-ttu-id="d2284-153">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d2284-153">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
        {
            "id": "2e9da30d-27f6-4208-81f2-9cd3d67893ba",
            "type": "RunAntiVirusScan",
            "scope": "Full",
            "requestor": "Analyst@contoso.com",
            "requestorComment": "Check machine for viruses due to alert 3212",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:18:27.1293487Z",
            "lastUpdateTimeUtc": "2018-12-04T12:18:57.5511934Z",
            "relatedFileInfo": null
        },
        {
            "id": "44cffc15-0e3d-4cbf-96aa-bf76f9b27f5e",
            "type": "StopAndQuarantineFile",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:15:40.6052029Z",
            "lastUpdateTimeUtc": "2018-12-04T12:16:14.2899973Z",
            "relatedFileInfo": {
                "fileIdentifier": "a0c659857ccbe457fdaf5fe21d54efdcbf6f6508",
                "fileIdentifierType": "Sha1"
            }
        }
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="d2284-154">예 2</span><span class="sxs-lookup"><span data-stu-id="d2284-154">Example 2</span></span>

<span data-ttu-id="d2284-155">**요청**</span><span class="sxs-lookup"><span data-stu-id="d2284-155">**Request**</span></span>

<span data-ttu-id="d2284-156">다음은 컴퓨터 ID로 MachineActions를 필터하고 최신 두 MachineActions를 표시하는 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d2284-156">Here is an example of a request that filters the MachineActions by machine ID and shows the latest two MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions?$filter=machineId eq 'f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f'&$top=2
```

<span data-ttu-id="d2284-157">**응답**</span><span class="sxs-lookup"><span data-stu-id="d2284-157">**Response**</span></span>

<span data-ttu-id="d2284-158">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d2284-158">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
        {
            "id": "2e9da30d-27f6-4208-81f2-9cd3d67893ba",
            "type": "RunAntiVirusScan",
            "scope": "Full",
            "requestor": "Analyst@contoso.com",
            "requestorComment": "Check machine for viruses due to alert 3212",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:18:27.1293487Z",
            "lastUpdateTimeUtc": "2018-12-04T12:18:57.5511934Z",
            "relatedFileInfo": null
        }
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="d2284-159">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d2284-159">Related topics</span></span>
- [<span data-ttu-id="d2284-160">끝점용 Microsoft Defender를 사용하여 OData 쿼리</span><span class="sxs-lookup"><span data-stu-id="d2284-160">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
