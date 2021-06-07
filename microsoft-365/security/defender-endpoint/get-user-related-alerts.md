---
title: 사용자 관련 알림 API를 얻습니다.
description: 끝점용 Microsoft Defender를 사용하여 특정 사용자 ID와 관련된 경고 컬렉션을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, 사용자, 관련, 경고
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
ms.openlocfilehash: ab0d0e97365b5ce38b29f2b0d65e3aea48d6c28c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769932"
---
# <a name="get-user-related-alerts-api"></a><span data-ttu-id="55ef4-104">사용자 관련 알림 API를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="55ef4-104">Get user-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="55ef4-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="55ef4-105">**Applies to:**</span></span>
- [<span data-ttu-id="55ef4-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="55ef4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="55ef4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="55ef4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="55ef4-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="55ef4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="55ef4-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="55ef4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="55ef4-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="55ef4-110">API description</span></span>
<span data-ttu-id="55ef4-111">지정한 사용자 ID와 관련된 경고 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="55ef4-111">Retrieves a collection of alerts related to a given user ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="55ef4-112">제한 사항</span><span class="sxs-lookup"><span data-stu-id="55ef4-112">Limitations</span></span>
1. <span data-ttu-id="55ef4-113">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="55ef4-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="55ef4-114">사용 권한</span><span class="sxs-lookup"><span data-stu-id="55ef4-114">Permissions</span></span>
<span data-ttu-id="55ef4-115">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="55ef4-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="55ef4-116">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="55ef4-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="55ef4-117">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="55ef4-117">Permission type</span></span> |   <span data-ttu-id="55ef4-118">사용 권한</span><span class="sxs-lookup"><span data-stu-id="55ef4-118">Permission</span></span>  |   <span data-ttu-id="55ef4-119">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="55ef4-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="55ef4-120">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="55ef4-120">Application</span></span> |   <span data-ttu-id="55ef4-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="55ef4-121">Alert.Read.All</span></span> |    <span data-ttu-id="55ef4-122">'모든 경고 읽기'</span><span class="sxs-lookup"><span data-stu-id="55ef4-122">'Read all alerts'</span></span>
<span data-ttu-id="55ef4-123">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="55ef4-123">Application</span></span> |   <span data-ttu-id="55ef4-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="55ef4-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="55ef4-125">'모든 경고 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="55ef4-125">'Read and write all alerts'</span></span>
<span data-ttu-id="55ef4-126">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="55ef4-126">Delegated (work or school account)</span></span> | <span data-ttu-id="55ef4-127">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="55ef4-127">Alert.Read</span></span> | <span data-ttu-id="55ef4-128">'경고 읽기'</span><span class="sxs-lookup"><span data-stu-id="55ef4-128">'Read alerts'</span></span>
<span data-ttu-id="55ef4-129">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="55ef4-129">Delegated (work or school account)</span></span> | <span data-ttu-id="55ef4-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="55ef4-130">Alert.ReadWrite</span></span> | <span data-ttu-id="55ef4-131">'경고 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="55ef4-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="55ef4-132">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="55ef4-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="55ef4-133">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="55ef4-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="55ef4-134">자세한 내용은 역할 만들기 [및 관리를 참조하세요.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="55ef4-134">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="55ef4-135">응답에는 장치 그룹 설정에 따라 사용자가 액세스할 수 있는 알림만 포함됩니다(자세한 내용은 장치 그룹 [만들기](machine-groups.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="55ef4-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="55ef4-136">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="55ef4-136">HTTP request</span></span>
```
GET /api/users/{id}/alerts
```

<span data-ttu-id="55ef4-137">**ID는 전체 UPN이 아니라 사용자 이름입니다. (예: /api/users/user1/alerts를 user1@contoso.com 경고를 검색하는 경우)**</span><span class="sxs-lookup"><span data-stu-id="55ef4-137">**The ID is not the full UPN, but only the user name. (for example, to retrieve alerts for user1@contoso.com use /api/users/user1/alerts)**</span></span>

## <a name="request-headers"></a><span data-ttu-id="55ef4-138">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="55ef4-138">Request headers</span></span>

<span data-ttu-id="55ef4-139">이름</span><span class="sxs-lookup"><span data-stu-id="55ef4-139">Name</span></span> | <span data-ttu-id="55ef4-140">유형</span><span class="sxs-lookup"><span data-stu-id="55ef4-140">Type</span></span> | <span data-ttu-id="55ef4-141">설명</span><span class="sxs-lookup"><span data-stu-id="55ef4-141">Description</span></span>
:---|:---|:---
<span data-ttu-id="55ef4-142">권한 부여</span><span class="sxs-lookup"><span data-stu-id="55ef4-142">Authorization</span></span> | <span data-ttu-id="55ef4-143">String</span><span class="sxs-lookup"><span data-stu-id="55ef4-143">String</span></span> | <span data-ttu-id="55ef4-144">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="55ef4-144">Bearer {token}.</span></span> <span data-ttu-id="55ef4-145">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="55ef4-145">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="55ef4-146">요청 본문</span><span class="sxs-lookup"><span data-stu-id="55ef4-146">Request body</span></span>
<span data-ttu-id="55ef4-147">비어 있음</span><span class="sxs-lookup"><span data-stu-id="55ef4-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="55ef4-148">응답</span><span class="sxs-lookup"><span data-stu-id="55ef4-148">Response</span></span>
<span data-ttu-id="55ef4-149">성공적이고 사용자가 있는 경우 - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="55ef4-149">If successful and user exists - 200 OK.</span></span> <span data-ttu-id="55ef4-150">사용자가 존재하지 않는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55ef4-150">If the user does not exist - 404 Not Found.</span></span> 


## <a name="example"></a><span data-ttu-id="55ef4-151">예시</span><span class="sxs-lookup"><span data-stu-id="55ef4-151">Example</span></span>

<span data-ttu-id="55ef4-152">**요청**</span><span class="sxs-lookup"><span data-stu-id="55ef4-152">**Request**</span></span>

<span data-ttu-id="55ef4-153">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="55ef4-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/alerts
```
