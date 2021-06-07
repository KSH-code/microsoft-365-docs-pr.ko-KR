---
title: 목록 컴퓨터 API
description: 목록 컴퓨터 API를 사용하여 끝점 클라우드용 Microsoft Defender와 통신한 컴퓨터 컬렉션을 검색하는 방법을 배워보세요.
keywords: api, 그래프 api, 지원되는 api, get, 장치
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: f06973bc45ecac05c15d48afe5f0e2e9e7788f78
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770752"
---
# <a name="list-machines-api"></a><span data-ttu-id="962e0-104">목록 컴퓨터 API</span><span class="sxs-lookup"><span data-stu-id="962e0-104">List machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="962e0-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="962e0-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="962e0-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="962e0-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="962e0-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="962e0-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="962e0-108">API 설명</span><span class="sxs-lookup"><span data-stu-id="962e0-108">API description</span></span>
<span data-ttu-id="962e0-109">Endpoint 클라우드용 [](machine.md) Microsoft Defender와 통신한 컴퓨터 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="962e0-109">Retrieves a collection of [Machines](machine.md) that have communicated with  Microsoft Defender for Endpoint cloud.</span></span>
<br><span data-ttu-id="962e0-110">[OData V4 쿼리를 지원합니다.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="962e0-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="962e0-111">OData의 쿼리는 `$filter` , , , 및 `computerDnsName` `lastSeen` `healthStatus` `osPlatform` 에서 `riskScore` `rbacGroupId` 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="962e0-111">The OData's `$filter` query is supported on: `computerDnsName`, `lastSeen`, `healthStatus`, `osPlatform`, `riskScore` and `rbacGroupId`.</span></span>
<br><span data-ttu-id="962e0-112">[끝점용 Defender를 사용하여 OData 쿼리의 예 참조](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="962e0-112">See examples at [OData queries with Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="962e0-113">제한 사항</span><span class="sxs-lookup"><span data-stu-id="962e0-113">Limitations</span></span>
1. <span data-ttu-id="962e0-114">구성된 보존 기간에 따라 장치를 마지막으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="962e0-114">You can get devices last seen according to your configured retention period.</span></span>
2. <span data-ttu-id="962e0-115">최대 페이지 크기는 10,000개입니다.</span><span class="sxs-lookup"><span data-stu-id="962e0-115">Maximum page size is 10,000.</span></span>
3. <span data-ttu-id="962e0-116">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="962e0-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="962e0-117">사용 권한</span><span class="sxs-lookup"><span data-stu-id="962e0-117">Permissions</span></span>

<span data-ttu-id="962e0-118">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="962e0-118">Permission type</span></span> |   <span data-ttu-id="962e0-119">사용 권한</span><span class="sxs-lookup"><span data-stu-id="962e0-119">Permission</span></span>  |   <span data-ttu-id="962e0-120">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="962e0-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="962e0-121">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="962e0-121">Application</span></span> |   <span data-ttu-id="962e0-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="962e0-122">Machine.Read.All</span></span> |  <span data-ttu-id="962e0-123">'모든 컴퓨터 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="962e0-123">'Read all machine profiles'</span></span>
<span data-ttu-id="962e0-124">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="962e0-124">Application</span></span> |   <span data-ttu-id="962e0-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="962e0-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="962e0-126">'모든 컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="962e0-126">'Read and write all machine information'</span></span>
<span data-ttu-id="962e0-127">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="962e0-127">Delegated (work or school account)</span></span> | <span data-ttu-id="962e0-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="962e0-128">Machine.Read</span></span> | <span data-ttu-id="962e0-129">'컴퓨터 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="962e0-129">'Read machine information'</span></span>
<span data-ttu-id="962e0-130">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="962e0-130">Delegated (work or school account)</span></span> | <span data-ttu-id="962e0-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="962e0-131">Machine.ReadWrite</span></span> | <span data-ttu-id="962e0-132">'컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="962e0-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="962e0-133">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="962e0-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="962e0-134">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="962e0-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="962e0-135">응답에는 장치 그룹 설정에 따라 사용자가 액세스할 수 있는 장치만 포함됩니다(자세한 내용은 장치 그룹 [만들기](machine-groups.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="962e0-135">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="962e0-136">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="962e0-136">HTTP request</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a><span data-ttu-id="962e0-137">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="962e0-137">Request headers</span></span>

<span data-ttu-id="962e0-138">이름</span><span class="sxs-lookup"><span data-stu-id="962e0-138">Name</span></span> | <span data-ttu-id="962e0-139">유형</span><span class="sxs-lookup"><span data-stu-id="962e0-139">Type</span></span> | <span data-ttu-id="962e0-140">설명</span><span class="sxs-lookup"><span data-stu-id="962e0-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="962e0-141">권한 부여</span><span class="sxs-lookup"><span data-stu-id="962e0-141">Authorization</span></span> | <span data-ttu-id="962e0-142">String</span><span class="sxs-lookup"><span data-stu-id="962e0-142">String</span></span> | <span data-ttu-id="962e0-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="962e0-143">Bearer {token}.</span></span> <span data-ttu-id="962e0-144">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="962e0-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="962e0-145">요청 본문</span><span class="sxs-lookup"><span data-stu-id="962e0-145">Request body</span></span>
<span data-ttu-id="962e0-146">비어 있음</span><span class="sxs-lookup"><span data-stu-id="962e0-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="962e0-147">응답</span><span class="sxs-lookup"><span data-stu-id="962e0-147">Response</span></span>
<span data-ttu-id="962e0-148">성공 및 컴퓨터 존재 - 본문에 컴퓨터 [](machine.md) 엔터티 목록이 있는 200 OK.</span><span class="sxs-lookup"><span data-stu-id="962e0-148">If successful and machines exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="962e0-149">최신 컴퓨터를 찾을 수 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="962e0-149">If no recent machines - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="962e0-150">예시</span><span class="sxs-lookup"><span data-stu-id="962e0-150">Example</span></span>

<span data-ttu-id="962e0-151">**요청**</span><span class="sxs-lookup"><span data-stu-id="962e0-151">**Request**</span></span>

<span data-ttu-id="962e0-152">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="962e0-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

<span data-ttu-id="962e0-153">**응답**</span><span class="sxs-lookup"><span data-stu-id="962e0-153">**Response**</span></span>

<span data-ttu-id="962e0-154">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="962e0-154">Here is an example of the response.</span></span>

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
            "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
            "computerDnsName": "mymachine1.contoso.com",
            "firstSeen": "2018-08-02T14:55:03.7791856Z",
            "lastSeen": "2018-08-02T14:55:03.7791856Z",
            "osPlatform": "Windows10",
            "version": "1709",
            "osProcessor": "x64",
            "lastIpAddress": "172.17.230.209",
            "lastExternalIpAddress": "167.220.196.71",
            "osBuild": 18209,
            "healthStatus": "Active",
            "rbacGroupId": 140,
            "rbacGroupName": "The-A-Team",
            "riskScore": "Low",
            "exposureLevel": "Medium",
            "isAadJoined": true,
            "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
            "machineTags": [ "test tag 1", "test tag 2" ]
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="962e0-155">관련 항목</span><span class="sxs-lookup"><span data-stu-id="962e0-155">Related topics</span></span>
- [<span data-ttu-id="962e0-156">끝점용 Microsoft Defender를 사용하여 OData 쿼리</span><span class="sxs-lookup"><span data-stu-id="962e0-156">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
