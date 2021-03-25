---
title: ID로 컴퓨터 사용 API
description: ID로 컴퓨터 다운로드 API를 사용하여 끝점용 Microsoft Defender에서 장치 ID 또는 컴퓨터 이름으로 컴퓨터를 검색하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, get, 장치, 엔터티, ID
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
ms.openlocfilehash: 29423230d0d8d4baaa1acca9a3661dc3436f303d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200100"
---
# <a name="get-machine-by-id-api"></a><span data-ttu-id="416d6-104">ID로 컴퓨터 사용 API</span><span class="sxs-lookup"><span data-stu-id="416d6-104">Get machine by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="416d6-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="416d6-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>


> <span data-ttu-id="416d6-106">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="416d6-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="416d6-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="416d6-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="416d6-108">API 설명</span><span class="sxs-lookup"><span data-stu-id="416d6-108">API description</span></span>
<span data-ttu-id="416d6-109">장치 [ID](machine.md) 또는 컴퓨터 이름으로 특정 컴퓨터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="416d6-109">Retrieves specific [Machine](machine.md) by its device ID or computer name.</span></span>


## <a name="limitations"></a><span data-ttu-id="416d6-110">제한 사항</span><span class="sxs-lookup"><span data-stu-id="416d6-110">Limitations</span></span>
1. <span data-ttu-id="416d6-111">구성된 보존 정책에 따라 장치를 마지막으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="416d6-111">You can get devices last seen according to your configured retention policy.</span></span>
2. <span data-ttu-id="416d6-112">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="416d6-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="416d6-113">사용 권한</span><span class="sxs-lookup"><span data-stu-id="416d6-113">Permissions</span></span>
<span data-ttu-id="416d6-114">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="416d6-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="416d6-115">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="416d6-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="416d6-116">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="416d6-116">Permission type</span></span> |   <span data-ttu-id="416d6-117">사용 권한</span><span class="sxs-lookup"><span data-stu-id="416d6-117">Permission</span></span>  |   <span data-ttu-id="416d6-118">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="416d6-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="416d6-119">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="416d6-119">Application</span></span> |   <span data-ttu-id="416d6-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="416d6-120">Machine.Read.All</span></span> |  <span data-ttu-id="416d6-121">'모든 컴퓨터 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="416d6-121">'Read all machine profiles'</span></span>
<span data-ttu-id="416d6-122">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="416d6-122">Application</span></span> |   <span data-ttu-id="416d6-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="416d6-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="416d6-124">'모든 컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="416d6-124">'Read and write all machine information'</span></span>
<span data-ttu-id="416d6-125">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="416d6-125">Delegated (work or school account)</span></span> | <span data-ttu-id="416d6-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="416d6-126">Machine.Read</span></span> | <span data-ttu-id="416d6-127">'컴퓨터 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="416d6-127">'Read machine information'</span></span>
<span data-ttu-id="416d6-128">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="416d6-128">Delegated (work or school account)</span></span> | <span data-ttu-id="416d6-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="416d6-129">Machine.ReadWrite</span></span> | <span data-ttu-id="416d6-130">'컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="416d6-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="416d6-131">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="416d6-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="416d6-132">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="416d6-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="416d6-133">사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="416d6-133">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="416d6-134">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="416d6-134">HTTP request</span></span>
```http
GET /api/machines/{id}
```

## <a name="request-headers"></a><span data-ttu-id="416d6-135">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="416d6-135">Request headers</span></span>

<span data-ttu-id="416d6-136">이름</span><span class="sxs-lookup"><span data-stu-id="416d6-136">Name</span></span> | <span data-ttu-id="416d6-137">유형</span><span class="sxs-lookup"><span data-stu-id="416d6-137">Type</span></span> | <span data-ttu-id="416d6-138">설명</span><span class="sxs-lookup"><span data-stu-id="416d6-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="416d6-139">권한 부여</span><span class="sxs-lookup"><span data-stu-id="416d6-139">Authorization</span></span> | <span data-ttu-id="416d6-140">문자열</span><span class="sxs-lookup"><span data-stu-id="416d6-140">String</span></span> | <span data-ttu-id="416d6-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="416d6-141">Bearer {token}.</span></span> <span data-ttu-id="416d6-142">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="416d6-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="416d6-143">요청 본문</span><span class="sxs-lookup"><span data-stu-id="416d6-143">Request body</span></span>
<span data-ttu-id="416d6-144">비어 있음</span><span class="sxs-lookup"><span data-stu-id="416d6-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="416d6-145">응답</span><span class="sxs-lookup"><span data-stu-id="416d6-145">Response</span></span>
<span data-ttu-id="416d6-146">성공적이고 장치가 있는 경우 - 본문에 컴퓨터 엔터티가 있는 200 OK. [](machine.md)</span><span class="sxs-lookup"><span data-stu-id="416d6-146">If successful and device exists - 200 OK with the [machine](machine.md) entity in the body.</span></span>
<span data-ttu-id="416d6-147">지정한 ID가 있는 머신을 찾을 수 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="416d6-147">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="416d6-148">예제</span><span class="sxs-lookup"><span data-stu-id="416d6-148">Example</span></span>

<span data-ttu-id="416d6-149">**요청**</span><span class="sxs-lookup"><span data-stu-id="416d6-149">**Request**</span></span>

<span data-ttu-id="416d6-150">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="416d6-150">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07
```

<span data-ttu-id="416d6-151">**응답**</span><span class="sxs-lookup"><span data-stu-id="416d6-151">**Response**</span></span>

<span data-ttu-id="416d6-152">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="416d6-152">Here is an example of the response.</span></span>


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machine",
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

```
