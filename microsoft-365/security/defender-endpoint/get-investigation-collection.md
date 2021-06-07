---
title: 목록 조사 API
description: 이 API를 사용하여 Investigations 컬렉션을 받을 때와 관련된 호출을 만들 수 있습니다.
keywords: api, 그래프 api, 지원되는 api, 조사 컬렉션
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 38485a5028626153c26cd1e11537ef7a2daf5296
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770148"
---
# <a name="list-investigations-api"></a><span data-ttu-id="e3266-104">목록 조사 API</span><span class="sxs-lookup"><span data-stu-id="e3266-104">List Investigations API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e3266-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e3266-105">**Applies to:**</span></span>
- [<span data-ttu-id="e3266-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e3266-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e3266-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3266-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e3266-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="e3266-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e3266-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e3266-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="e3266-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="e3266-110">API description</span></span>
<span data-ttu-id="e3266-111">조사 [컬렉션을 검색합니다.](investigation.md)</span><span class="sxs-lookup"><span data-stu-id="e3266-111">Retrieves a collection of [Investigations](investigation.md).</span></span>
<br><span data-ttu-id="e3266-112">[OData V4 쿼리를 지원합니다.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="e3266-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="e3266-113">OData의 쿼리는 ```$filter``` ```startTime``` , 및 ```state``` ```machineId``` 속성에서 ```triggeringAlertId``` 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3266-113">The OData's ```$filter``` query is supported on: ```startTime```, ```state```, ```machineId``` and ```triggeringAlertId``` properties.</span></span>
<br><span data-ttu-id="e3266-114">[끝점용 Microsoft Defender를 사용하여 OData 쿼리 예제 보기](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="e3266-114">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="e3266-115">제한 사항</span><span class="sxs-lookup"><span data-stu-id="e3266-115">Limitations</span></span>
1. <span data-ttu-id="e3266-116">최대 페이지 크기는 10,000개입니다.</span><span class="sxs-lookup"><span data-stu-id="e3266-116">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="e3266-117">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="e3266-117">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="e3266-118">사용 권한</span><span class="sxs-lookup"><span data-stu-id="e3266-118">Permissions</span></span>
<span data-ttu-id="e3266-119">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e3266-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e3266-120">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e3266-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e3266-121">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="e3266-121">Permission type</span></span> |   <span data-ttu-id="e3266-122">사용 권한</span><span class="sxs-lookup"><span data-stu-id="e3266-122">Permission</span></span>  |   <span data-ttu-id="e3266-123">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="e3266-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e3266-124">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="e3266-124">Application</span></span> |   <span data-ttu-id="e3266-125">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="e3266-125">Alert.Read.All</span></span> |    <span data-ttu-id="e3266-126">'모든 경고 읽기'</span><span class="sxs-lookup"><span data-stu-id="e3266-126">'Read all alerts'</span></span>
<span data-ttu-id="e3266-127">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="e3266-127">Application</span></span> |   <span data-ttu-id="e3266-128">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e3266-128">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="e3266-129">'모든 경고 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="e3266-129">'Read and write all alerts'</span></span>
<span data-ttu-id="e3266-130">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="e3266-130">Delegated (work or school account)</span></span> | <span data-ttu-id="e3266-131">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="e3266-131">Alert.Read</span></span> | <span data-ttu-id="e3266-132">'경고 읽기'</span><span class="sxs-lookup"><span data-stu-id="e3266-132">'Read alerts'</span></span>
<span data-ttu-id="e3266-133">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="e3266-133">Delegated (work or school account)</span></span> | <span data-ttu-id="e3266-134">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e3266-134">Alert.ReadWrite</span></span> | <span data-ttu-id="e3266-135">'경고 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="e3266-135">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="e3266-136">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="e3266-136">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="e3266-137">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="e3266-137">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="e3266-138">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="e3266-138">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations
```

## <a name="request-headers"></a><span data-ttu-id="e3266-139">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="e3266-139">Request headers</span></span>

<span data-ttu-id="e3266-140">이름</span><span class="sxs-lookup"><span data-stu-id="e3266-140">Name</span></span> | <span data-ttu-id="e3266-141">유형</span><span class="sxs-lookup"><span data-stu-id="e3266-141">Type</span></span> | <span data-ttu-id="e3266-142">설명</span><span class="sxs-lookup"><span data-stu-id="e3266-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="e3266-143">권한 부여</span><span class="sxs-lookup"><span data-stu-id="e3266-143">Authorization</span></span> | <span data-ttu-id="e3266-144">String</span><span class="sxs-lookup"><span data-stu-id="e3266-144">String</span></span> | <span data-ttu-id="e3266-145">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="e3266-145">Bearer {token}.</span></span> <span data-ttu-id="e3266-146">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="e3266-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="e3266-147">요청 본문</span><span class="sxs-lookup"><span data-stu-id="e3266-147">Request body</span></span>
<span data-ttu-id="e3266-148">비어 있음</span><span class="sxs-lookup"><span data-stu-id="e3266-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e3266-149">응답</span><span class="sxs-lookup"><span data-stu-id="e3266-149">Response</span></span>
<span data-ttu-id="e3266-150">성공하면 이 메서드는 조사 엔터티 컬렉션이 있는 200, 확인 응답 [코드를](investigation.md) 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e3266-150">If successful, this method returns 200, Ok response code with a collection of [Investigations](investigation.md) entities.</span></span>


## <a name="example"></a><span data-ttu-id="e3266-151">예시</span><span class="sxs-lookup"><span data-stu-id="e3266-151">Example</span></span>

<span data-ttu-id="e3266-152">**요청**</span><span class="sxs-lookup"><span data-stu-id="e3266-152">**Request**</span></span>

<span data-ttu-id="e3266-153">다음은 모든 조사를 요청하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e3266-153">Here is an example of a request to get all investigations:</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/investigations
```

<span data-ttu-id="e3266-154">**응답**</span><span class="sxs-lookup"><span data-stu-id="e3266-154">**Response**</span></span>

<span data-ttu-id="e3266-155">응답의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e3266-155">Here is an example of the response:</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Investigations",
    "value": [
        {
            "id": "63017",
            "startTime": "2020-01-06T14:11:34Z",
            "endTime": null,
            "state": "Running",
            "cancelledBy": null,
            "statusDetails": null,
            "machineId": "a69a22debe5f274d8765ea3c368d00762e057b30",
            "computerDnsName": "desktop-gtrcon0",
            "triggeringAlertId": "da637139166940871892_-598649278"
        }
        ...
    ]
}
```
