---
title: 경고 관련 사용자 정보 가져오기
description: 경고 관련 사용자 정보 다운로드 API를 사용하여 끝점용 Microsoft Defender의 특정 경고와 관련된 사용자를 검색하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, get, 경고, 정보, 관련, 사용자
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
ms.openlocfilehash: e895885a638c60a845ed4857c682cd472e42615c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772320"
---
# <a name="get-alert-related-user-information-api"></a><span data-ttu-id="c1b05-104">경고 관련 사용자 정보 얻기 API</span><span class="sxs-lookup"><span data-stu-id="c1b05-104">Get alert related user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c1b05-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c1b05-105">**Applies to:**</span></span>
- [<span data-ttu-id="c1b05-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c1b05-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c1b05-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c1b05-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="c1b05-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="c1b05-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c1b05-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c1b05-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="c1b05-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="c1b05-110">API description</span></span>
<span data-ttu-id="c1b05-111">특정 경고와 관련된 사용자를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c1b05-111">Retrieves the User related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="c1b05-112">제한 사항</span><span class="sxs-lookup"><span data-stu-id="c1b05-112">Limitations</span></span>
1. <span data-ttu-id="c1b05-113">구성된 보존 기간에 따라 마지막으로 업데이트된 경고에 대해 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1b05-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="c1b05-114">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="c1b05-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="c1b05-115">사용 권한</span><span class="sxs-lookup"><span data-stu-id="c1b05-115">Permissions</span></span>
<span data-ttu-id="c1b05-116">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c1b05-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c1b05-117">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c1b05-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c1b05-118">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="c1b05-118">Permission type</span></span> |   <span data-ttu-id="c1b05-119">사용 권한</span><span class="sxs-lookup"><span data-stu-id="c1b05-119">Permission</span></span>  |   <span data-ttu-id="c1b05-120">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="c1b05-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c1b05-121">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="c1b05-121">Application</span></span> |   <span data-ttu-id="c1b05-122">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="c1b05-122">User.Read.All</span></span> | <span data-ttu-id="c1b05-123">'사용자 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="c1b05-123">'Read user profiles'</span></span>
<span data-ttu-id="c1b05-124">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="c1b05-124">Delegated (work or school account)</span></span> | <span data-ttu-id="c1b05-125">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="c1b05-125">User.Read.All</span></span> | <span data-ttu-id="c1b05-126">'사용자 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="c1b05-126">'Read user profiles'</span></span>

>[!Note]
> <span data-ttu-id="c1b05-127">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="c1b05-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c1b05-128">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="c1b05-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="c1b05-129">사용자는 장치 그룹 설정에 따라 경고와 연결된 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="c1b05-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="c1b05-130">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="c1b05-130">HTTP request</span></span>
```
GET /api/alerts/{id}/user
```

## <a name="request-headers"></a><span data-ttu-id="c1b05-131">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="c1b05-131">Request headers</span></span>

<span data-ttu-id="c1b05-132">이름</span><span class="sxs-lookup"><span data-stu-id="c1b05-132">Name</span></span> | <span data-ttu-id="c1b05-133">유형</span><span class="sxs-lookup"><span data-stu-id="c1b05-133">Type</span></span> | <span data-ttu-id="c1b05-134">설명</span><span class="sxs-lookup"><span data-stu-id="c1b05-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="c1b05-135">권한 부여</span><span class="sxs-lookup"><span data-stu-id="c1b05-135">Authorization</span></span> | <span data-ttu-id="c1b05-136">String</span><span class="sxs-lookup"><span data-stu-id="c1b05-136">String</span></span> | <span data-ttu-id="c1b05-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c1b05-137">Bearer {token}.</span></span> <span data-ttu-id="c1b05-138">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="c1b05-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="c1b05-139">요청 본문</span><span class="sxs-lookup"><span data-stu-id="c1b05-139">Request body</span></span>
<span data-ttu-id="c1b05-140">비어 있음</span><span class="sxs-lookup"><span data-stu-id="c1b05-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c1b05-141">응답</span><span class="sxs-lookup"><span data-stu-id="c1b05-141">Response</span></span>
<span data-ttu-id="c1b05-142">성공 및 알림 및 사용자가 있는 경우 - 본문에 사용자가 200 OK입니다.</span><span class="sxs-lookup"><span data-stu-id="c1b05-142">If successful and alert and a user exists - 200 OK with user in the body.</span></span> <span data-ttu-id="c1b05-143">경고 또는 사용자를 찾을 수 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1b05-143">If alert or user not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="c1b05-144">예시</span><span class="sxs-lookup"><span data-stu-id="c1b05-144">Example</span></span>

<span data-ttu-id="c1b05-145">**요청**</span><span class="sxs-lookup"><span data-stu-id="c1b05-145">**Request**</span></span>

<span data-ttu-id="c1b05-146">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="c1b05-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/user
```

<span data-ttu-id="c1b05-147">**응답**</span><span class="sxs-lookup"><span data-stu-id="c1b05-147">**Response**</span></span>

<span data-ttu-id="c1b05-148">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="c1b05-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "contoso\\user1",
    "accountName": "user1",
    "accountDomain": "contoso",
    "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
    "firstSeen": "2019-12-08T06:33:39Z",
    "lastSeen": "2020-01-05T06:58:34Z",
    "mostPrevalentMachineId": "0111b647235c26159bec3e5eb6c8c3a0cc3ab766",
    "leastPrevalentMachineId": "0111b647235c26159bec3e5eb6c8c3a0cc3ab766",
    "logonTypes": "Network",
    "logOnMachinesCount": 1,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": false
}
```
