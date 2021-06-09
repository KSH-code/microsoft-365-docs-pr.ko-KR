---
title: 컴퓨터 로그온 사용자 확인 API
description: 컴퓨터 로그온 사용자 다운로드 API를 사용하여 끝점용 Microsoft Defender의 장치에서 로그온한 사용자 컬렉션을 검색하는 방법을 확인합니다.
keywords: api, 그래프 api, 지원되는 api, get, 장치, 로그온, 사용자
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
ms.openlocfilehash: 1c81d2978677b751a8085f88b5c4732fd4a5a247
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770052"
---
# <a name="get-machine-logon-users-api"></a><span data-ttu-id="06c55-104">컴퓨터 로그온 사용자 확인 API</span><span class="sxs-lookup"><span data-stu-id="06c55-104">Get machine logon users API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="06c55-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="06c55-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="06c55-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="06c55-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="06c55-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="06c55-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="06c55-108">API 설명</span><span class="sxs-lookup"><span data-stu-id="06c55-108">API description</span></span>
<span data-ttu-id="06c55-109">특정 장치에서 로그온한 사용자 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="06c55-109">Retrieves a collection of logged on users on a specific device.</span></span>


## <a name="limitations"></a><span data-ttu-id="06c55-110">제한 사항</span><span class="sxs-lookup"><span data-stu-id="06c55-110">Limitations</span></span>
1. <span data-ttu-id="06c55-111">구성된 보존 기간에 따라 마지막으로 업데이트된 경고에 대해 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c55-111">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="06c55-112">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="06c55-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="06c55-113">사용 권한</span><span class="sxs-lookup"><span data-stu-id="06c55-113">Permissions</span></span>
<span data-ttu-id="06c55-114">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="06c55-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="06c55-115">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="06c55-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="06c55-116">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="06c55-116">Permission type</span></span> |   <span data-ttu-id="06c55-117">사용 권한</span><span class="sxs-lookup"><span data-stu-id="06c55-117">Permission</span></span>  |   <span data-ttu-id="06c55-118">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="06c55-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="06c55-119">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="06c55-119">Application</span></span> |   <span data-ttu-id="06c55-120">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="06c55-120">User.Read.All</span></span> | <span data-ttu-id="06c55-121">'사용자 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="06c55-121">'Read user profiles'</span></span>
<span data-ttu-id="06c55-122">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="06c55-122">Delegated (work or school account)</span></span> | <span data-ttu-id="06c55-123">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="06c55-123">User.Read.All</span></span> | <span data-ttu-id="06c55-124">'사용자 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="06c55-124">'Read user profiles'</span></span>

>[!Note]
> <span data-ttu-id="06c55-125">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="06c55-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="06c55-126">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="06c55-126">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="06c55-127">자세한 내용은 역할 만들기 [및 관리를 참조하세요.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="06c55-127">For more information, see [Create and manage roles](user-roles.md) )</span></span>
>- <span data-ttu-id="06c55-128">응답에는 장치 그룹 설정에 따라 장치가 사용자에게 표시되는 경우만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="06c55-128">Response will include users only if the device is visible to the user, based on device group settings.</span></span> <span data-ttu-id="06c55-129">자세한 내용은 장치 그룹 [만들기 및 관리를 참조하세요.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="06c55-129">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="06c55-130">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="06c55-130">HTTP request</span></span>
```http
GET /api/machines/{id}/logonusers
```

## <a name="request-headers"></a><span data-ttu-id="06c55-131">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="06c55-131">Request headers</span></span>

<span data-ttu-id="06c55-132">이름</span><span class="sxs-lookup"><span data-stu-id="06c55-132">Name</span></span> | <span data-ttu-id="06c55-133">유형</span><span class="sxs-lookup"><span data-stu-id="06c55-133">Type</span></span> | <span data-ttu-id="06c55-134">설명</span><span class="sxs-lookup"><span data-stu-id="06c55-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="06c55-135">권한 부여</span><span class="sxs-lookup"><span data-stu-id="06c55-135">Authorization</span></span> | <span data-ttu-id="06c55-136">String</span><span class="sxs-lookup"><span data-stu-id="06c55-136">String</span></span> | <span data-ttu-id="06c55-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="06c55-137">Bearer {token}.</span></span> <span data-ttu-id="06c55-138">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="06c55-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="06c55-139">요청 본문</span><span class="sxs-lookup"><span data-stu-id="06c55-139">Request body</span></span>
<span data-ttu-id="06c55-140">비어 있음</span><span class="sxs-lookup"><span data-stu-id="06c55-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="06c55-141">응답</span><span class="sxs-lookup"><span data-stu-id="06c55-141">Response</span></span>
<span data-ttu-id="06c55-142">성공 및 장치가 있는 경우 - 본문에 [](user.md) 사용자 엔터티 목록이 있는 200 OK.</span><span class="sxs-lookup"><span data-stu-id="06c55-142">If successful and device exists - 200 OK with list of [user](user.md) entities in the body.</span></span> <span data-ttu-id="06c55-143">장치를 찾을 수 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06c55-143">If device was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="06c55-144">예시</span><span class="sxs-lookup"><span data-stu-id="06c55-144">Example</span></span>

<span data-ttu-id="06c55-145">**요청**</span><span class="sxs-lookup"><span data-stu-id="06c55-145">**Request**</span></span>

<span data-ttu-id="06c55-146">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="06c55-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/logonusers
```

<span data-ttu-id="06c55-147">**응답**</span><span class="sxs-lookup"><span data-stu-id="06c55-147">**Response**</span></span>

<span data-ttu-id="06c55-148">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="06c55-148">Here is an example of the response.</span></span>


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users",
    "value": [
        {
            "id": "contoso\\user1",
            "accountName": "user1",
            "accountDomain": "contoso",
            "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
            "firstSeen": "2019-12-18T08:02:54Z",
            "lastSeen": "2020-01-06T08:01:48Z",
            "logonTypes": "Interactive",
            "logOnMachinesCount": 8,
            "isDomainAdmin": true,
            "isOnlyNetworkUser": false
        },
        ...
    ]
}
```
