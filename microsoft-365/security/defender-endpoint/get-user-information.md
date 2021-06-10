---
title: 사용자 정보 얻기 API
description: 끝점용 Microsoft Defender에서 사용자 정보 다운로드 API를 사용하여 키 또는 사용자 이름으로 사용자 엔터티를 검색하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, 검색, 사용자, 사용자 정보
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
ms.openlocfilehash: 1c5b8fa6e0f1fd887c857bd4e6451a5e59b708af
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198544"
---
# <a name="get-user-information-api"></a><span data-ttu-id="f2d58-104">사용자 정보 얻기 API</span><span class="sxs-lookup"><span data-stu-id="f2d58-104">Get user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f2d58-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f2d58-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="f2d58-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="f2d58-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f2d58-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d58-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

> <span data-ttu-id="f2d58-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="f2d58-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f2d58-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d58-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)
<span data-ttu-id="f2d58-110">키(사용자 이름)를 사용하여 사용자 엔터티를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d58-110">Retrieve a User entity by key (user name).</span></span>

## <a name="permissions"></a><span data-ttu-id="f2d58-111">사용 권한</span><span class="sxs-lookup"><span data-stu-id="f2d58-111">Permissions</span></span>
<span data-ttu-id="f2d58-112">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d58-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f2d58-113">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f2d58-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f2d58-114">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="f2d58-114">Permission type</span></span> |   <span data-ttu-id="f2d58-115">사용 권한</span><span class="sxs-lookup"><span data-stu-id="f2d58-115">Permission</span></span>  |   <span data-ttu-id="f2d58-116">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="f2d58-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f2d58-117">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="f2d58-117">Application</span></span> |   <span data-ttu-id="f2d58-118">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="f2d58-118">User.Read.All</span></span> | <span data-ttu-id="f2d58-119">'모든 사용자 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="f2d58-119">'Read all user profiles'</span></span>

## <a name="http-request"></a><span data-ttu-id="f2d58-120">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="f2d58-120">HTTP request</span></span>
```
GET /api/users/{id}/
```

## <a name="request-headers"></a><span data-ttu-id="f2d58-121">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="f2d58-121">Request headers</span></span>

<span data-ttu-id="f2d58-122">이름</span><span class="sxs-lookup"><span data-stu-id="f2d58-122">Name</span></span> | <span data-ttu-id="f2d58-123">유형</span><span class="sxs-lookup"><span data-stu-id="f2d58-123">Type</span></span> | <span data-ttu-id="f2d58-124">설명</span><span class="sxs-lookup"><span data-stu-id="f2d58-124">Description</span></span>
:---|:---|:---
<span data-ttu-id="f2d58-125">권한 부여</span><span class="sxs-lookup"><span data-stu-id="f2d58-125">Authorization</span></span> | <span data-ttu-id="f2d58-126">String</span><span class="sxs-lookup"><span data-stu-id="f2d58-126">String</span></span> | <span data-ttu-id="f2d58-127">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f2d58-127">Bearer {token}.</span></span> <span data-ttu-id="f2d58-128">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="f2d58-128">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="f2d58-129">요청 본문</span><span class="sxs-lookup"><span data-stu-id="f2d58-129">Request body</span></span>
<span data-ttu-id="f2d58-130">비어 있음</span><span class="sxs-lookup"><span data-stu-id="f2d58-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f2d58-131">응답</span><span class="sxs-lookup"><span data-stu-id="f2d58-131">Response</span></span>
<span data-ttu-id="f2d58-132">성공적이고 사용자가 있는 경우 - [](user.md) 본문에 사용자 엔터티가 있는 200 OK.</span><span class="sxs-lookup"><span data-stu-id="f2d58-132">If successful and user exists - 200 OK with [user](user.md) entity in the body.</span></span> <span data-ttu-id="f2d58-133">사용자가 존재하지 않는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2d58-133">If user does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="f2d58-134">예시</span><span class="sxs-lookup"><span data-stu-id="f2d58-134">Example</span></span>

<span data-ttu-id="f2d58-135">**요청**</span><span class="sxs-lookup"><span data-stu-id="f2d58-135">**Request**</span></span>

<span data-ttu-id="f2d58-136">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f2d58-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/users/user1
Content-type: application/json
```

<span data-ttu-id="f2d58-137">**응답**</span><span class="sxs-lookup"><span data-stu-id="f2d58-137">**Response**</span></span>

<span data-ttu-id="f2d58-138">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f2d58-138">Here is an example of the response.</span></span>


```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "user1",
    "firstSeen": "2018-08-02T00:00:00Z",
    "lastSeen": "2018-08-04T00:00:00Z",
    "mostPrevalentMachineId": null,
    "leastPrevalentMachineId": null,
    "logonTypes": "Network",
    "logOnMachinesCount": 3,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": null
}
```
