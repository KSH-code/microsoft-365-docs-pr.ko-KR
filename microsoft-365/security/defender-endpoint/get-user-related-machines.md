---
title: 사용자 관련 컴퓨터 사용 API
description: 사용자 관련 컴퓨터 다운로드 API를 사용하여 끝점용 Microsoft Defender의 사용자 ID와 관련된 장치 컬렉션을 검색하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, get, 사용자, 사용자 관련 경고
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
ms.openlocfilehash: 230af2311c52437e01cdb28d823236347cf34b8f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769903"
---
# <a name="get-user-related-machines-api"></a><span data-ttu-id="8146f-104">사용자 관련 컴퓨터 사용 API</span><span class="sxs-lookup"><span data-stu-id="8146f-104">Get user-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8146f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8146f-105">**Applies to:**</span></span>
- [<span data-ttu-id="8146f-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8146f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8146f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8146f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8146f-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="8146f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8146f-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8146f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="8146f-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="8146f-110">API description</span></span>
<span data-ttu-id="8146f-111">지정한 사용자 ID와 관련된 장치 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8146f-111">Retrieves a collection of devices related to a given user ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="8146f-112">제한 사항</span><span class="sxs-lookup"><span data-stu-id="8146f-112">Limitations</span></span>
1. <span data-ttu-id="8146f-113">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="8146f-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="8146f-114">사용 권한</span><span class="sxs-lookup"><span data-stu-id="8146f-114">Permissions</span></span>
<span data-ttu-id="8146f-115">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8146f-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8146f-116">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8146f-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="8146f-117">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="8146f-117">Permission type</span></span> |   <span data-ttu-id="8146f-118">사용 권한</span><span class="sxs-lookup"><span data-stu-id="8146f-118">Permission</span></span>  |   <span data-ttu-id="8146f-119">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="8146f-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8146f-120">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="8146f-120">Application</span></span> |   <span data-ttu-id="8146f-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="8146f-121">Machine.Read.All</span></span> |  <span data-ttu-id="8146f-122">'모든 컴퓨터 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="8146f-122">'Read all machine profiles'</span></span>
<span data-ttu-id="8146f-123">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="8146f-123">Application</span></span> |   <span data-ttu-id="8146f-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8146f-124">Machine.ReadWrite.All</span></span> | <span data-ttu-id="8146f-125">'모든 컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="8146f-125">'Read and write all machine information'</span></span>
<span data-ttu-id="8146f-126">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="8146f-126">Delegated (work or school account)</span></span> | <span data-ttu-id="8146f-127">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="8146f-127">Machine.Read</span></span> | <span data-ttu-id="8146f-128">'컴퓨터 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="8146f-128">'Read machine information'</span></span>
<span data-ttu-id="8146f-129">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="8146f-129">Delegated (work or school account)</span></span> | <span data-ttu-id="8146f-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="8146f-130">Machine.ReadWrite</span></span> | <span data-ttu-id="8146f-131">'컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="8146f-131">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="8146f-132">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="8146f-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="8146f-133">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8146f-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="8146f-134">자세한 내용은 역할 만들기 [및 관리를 참조하세요.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="8146f-134">For more information, see [Create and manage roles](user-roles.md) )</span></span>
>- <span data-ttu-id="8146f-135">응답에는 사용자가 장치 그룹 설정에 따라 액세스할 수 있는 장치만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8146f-135">Response will include only devices that the user can access, based on device group settings.</span></span> <span data-ttu-id="8146f-136">자세한 내용은 장치 그룹 [만들기 및 관리를 참조하세요.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="8146f-136">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="8146f-137">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="8146f-137">HTTP request</span></span>
```
GET /api/users/{id}/machines
```

<span data-ttu-id="8146f-138">**ID는 전체 UPN이 아니라 사용자 이름입니다. (예: /api/users/user1/machines를 user1@contoso.com 컴퓨터를 검색하는 경우)**</span><span class="sxs-lookup"><span data-stu-id="8146f-138">**The ID is not the full UPN, but only the user name. (for example, to retrieve machines for user1@contoso.com use /api/users/user1/machines)**</span></span>


## <a name="request-headers"></a><span data-ttu-id="8146f-139">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="8146f-139">Request headers</span></span>

<span data-ttu-id="8146f-140">이름</span><span class="sxs-lookup"><span data-stu-id="8146f-140">Name</span></span> | <span data-ttu-id="8146f-141">유형</span><span class="sxs-lookup"><span data-stu-id="8146f-141">Type</span></span> | <span data-ttu-id="8146f-142">설명</span><span class="sxs-lookup"><span data-stu-id="8146f-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="8146f-143">권한 부여</span><span class="sxs-lookup"><span data-stu-id="8146f-143">Authorization</span></span> | <span data-ttu-id="8146f-144">String</span><span class="sxs-lookup"><span data-stu-id="8146f-144">String</span></span> | <span data-ttu-id="8146f-145">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="8146f-145">Bearer {token}.</span></span> <span data-ttu-id="8146f-146">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="8146f-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="8146f-147">요청 본문</span><span class="sxs-lookup"><span data-stu-id="8146f-147">Request body</span></span>
<span data-ttu-id="8146f-148">비어 있음</span><span class="sxs-lookup"><span data-stu-id="8146f-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="8146f-149">응답</span><span class="sxs-lookup"><span data-stu-id="8146f-149">Response</span></span>
<span data-ttu-id="8146f-150">성공 및 사용자가 있는 경우 - 본문에 [](machine.md) 컴퓨터 엔터티 목록이 있는 200 OK.</span><span class="sxs-lookup"><span data-stu-id="8146f-150">If successful and user exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="8146f-151">사용자가 존재하지 않는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8146f-151">If user does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="8146f-152">예시</span><span class="sxs-lookup"><span data-stu-id="8146f-152">Example</span></span>

<span data-ttu-id="8146f-153">**요청**</span><span class="sxs-lookup"><span data-stu-id="8146f-153">**Request**</span></span>

<span data-ttu-id="8146f-154">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8146f-154">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```
