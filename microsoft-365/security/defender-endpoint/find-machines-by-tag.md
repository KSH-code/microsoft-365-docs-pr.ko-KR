---
title: 태그 API로 장치 찾기
description: 지정 태그가 포함된 모든 장치 찾기
keywords: api, 지원되는 api, get, 디바이스, 찾기, 디바이스 찾기, 태그, 태그
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
ms.openlocfilehash: 88ad63d8b7cc71f7d3f809c7cb0371fc41bb9f5d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771168"
---
# <a name="find-devices-by-tag-api"></a><span data-ttu-id="e7b04-104">태그 API로 장치 찾기</span><span class="sxs-lookup"><span data-stu-id="e7b04-104">Find devices by tag API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e7b04-105">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="e7b04-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="e7b04-106">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="e7b04-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e7b04-107">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e7b04-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="e7b04-108">API 설명</span><span class="sxs-lookup"><span data-stu-id="e7b04-108">API description</span></span>
<span data-ttu-id="e7b04-109">태그로 [컴퓨터를](machine.md) [검색합니다.](machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="e7b04-109">Find [Machines](machine.md) by [Tag](machine-tags.md).</span></span>
<br><span data-ttu-id="e7b04-110">```startswith``` 쿼리가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7b04-110">```startswith``` query is supported.</span></span> 

## <a name="limitations"></a><span data-ttu-id="e7b04-111">제한 사항</span><span class="sxs-lookup"><span data-stu-id="e7b04-111">Limitations</span></span>
1. <span data-ttu-id="e7b04-112">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="e7b04-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="e7b04-113">사용 권한</span><span class="sxs-lookup"><span data-stu-id="e7b04-113">Permissions</span></span>
<span data-ttu-id="e7b04-114">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e7b04-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e7b04-115">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e7b04-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e7b04-116">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="e7b04-116">Permission type</span></span> |   <span data-ttu-id="e7b04-117">사용 권한</span><span class="sxs-lookup"><span data-stu-id="e7b04-117">Permission</span></span>  |   <span data-ttu-id="e7b04-118">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="e7b04-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e7b04-119">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="e7b04-119">Application</span></span> |   <span data-ttu-id="e7b04-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="e7b04-120">Machine.Read.All</span></span> |  <span data-ttu-id="e7b04-121">'모든 컴퓨터 프로필 읽기'</span><span class="sxs-lookup"><span data-stu-id="e7b04-121">'Read all machine profiles'</span></span>
<span data-ttu-id="e7b04-122">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="e7b04-122">Application</span></span> |   <span data-ttu-id="e7b04-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e7b04-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="e7b04-124">'모든 컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="e7b04-124">'Read and write all machine information'</span></span>
<span data-ttu-id="e7b04-125">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="e7b04-125">Delegated (work or school account)</span></span> | <span data-ttu-id="e7b04-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="e7b04-126">Machine.Read</span></span> | <span data-ttu-id="e7b04-127">'컴퓨터 정보 읽기'</span><span class="sxs-lookup"><span data-stu-id="e7b04-127">'Read machine information'</span></span>
<span data-ttu-id="e7b04-128">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="e7b04-128">Delegated (work or school account)</span></span> | <span data-ttu-id="e7b04-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e7b04-129">Machine.ReadWrite</span></span> | <span data-ttu-id="e7b04-130">'컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="e7b04-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="e7b04-131">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="e7b04-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="e7b04-132">응답에는 사용자가 장치 그룹 설정에 따라 액세스할 수 있는 장치만 포함됩니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="e7b04-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="e7b04-133">사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="e7b04-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="e7b04-134">응답에는 사용자가 장치 그룹 설정에 따라 액세스할 수 있는 장치만 포함됩니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="e7b04-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="e7b04-135">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="e7b04-135">HTTP request</span></span>
```
GET /api/machines/findbytag?tag={tag}&useStartsWithFilter={true/false}
```

## <a name="request-headers"></a><span data-ttu-id="e7b04-136">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="e7b04-136">Request headers</span></span>

<span data-ttu-id="e7b04-137">이름</span><span class="sxs-lookup"><span data-stu-id="e7b04-137">Name</span></span> | <span data-ttu-id="e7b04-138">유형</span><span class="sxs-lookup"><span data-stu-id="e7b04-138">Type</span></span> | <span data-ttu-id="e7b04-139">설명</span><span class="sxs-lookup"><span data-stu-id="e7b04-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="e7b04-140">권한 부여</span><span class="sxs-lookup"><span data-stu-id="e7b04-140">Authorization</span></span> | <span data-ttu-id="e7b04-141">String</span><span class="sxs-lookup"><span data-stu-id="e7b04-141">String</span></span> | <span data-ttu-id="e7b04-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="e7b04-142">Bearer {token}.</span></span> <span data-ttu-id="e7b04-143">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="e7b04-143">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="e7b04-144">요청 URI 매개 변수</span><span class="sxs-lookup"><span data-stu-id="e7b04-144">Request URI parameters</span></span>

<span data-ttu-id="e7b04-145">이름</span><span class="sxs-lookup"><span data-stu-id="e7b04-145">Name</span></span> | <span data-ttu-id="e7b04-146">유형</span><span class="sxs-lookup"><span data-stu-id="e7b04-146">Type</span></span> | <span data-ttu-id="e7b04-147">설명</span><span class="sxs-lookup"><span data-stu-id="e7b04-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="e7b04-148">tag</span><span class="sxs-lookup"><span data-stu-id="e7b04-148">tag</span></span> | <span data-ttu-id="e7b04-149">String</span><span class="sxs-lookup"><span data-stu-id="e7b04-149">String</span></span> | <span data-ttu-id="e7b04-150">태그 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e7b04-150">The tag name.</span></span> <span data-ttu-id="e7b04-151">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="e7b04-151">**Required**.</span></span>
<span data-ttu-id="e7b04-152">useStartsWithFilter</span><span class="sxs-lookup"><span data-stu-id="e7b04-152">useStartsWithFilter</span></span> | <span data-ttu-id="e7b04-153">부울</span><span class="sxs-lookup"><span data-stu-id="e7b04-153">Boolean</span></span> | <span data-ttu-id="e7b04-154">true로 설정하면 쿼리에서 태그 이름이 지정한 태그로 시작하는 모든 장치가 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7b04-154">When set to true, the search will find all devices with tag name that starts with the given tag in the query.</span></span> <span data-ttu-id="e7b04-155">기본값은 false입니다.</span><span class="sxs-lookup"><span data-stu-id="e7b04-155">Defaults to false.</span></span> <span data-ttu-id="e7b04-156">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e7b04-156">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="e7b04-157">요청 본문</span><span class="sxs-lookup"><span data-stu-id="e7b04-157">Request body</span></span>
<span data-ttu-id="e7b04-158">비어 있음</span><span class="sxs-lookup"><span data-stu-id="e7b04-158">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e7b04-159">응답</span><span class="sxs-lookup"><span data-stu-id="e7b04-159">Response</span></span>
<span data-ttu-id="e7b04-160">성공적이면 - 응답 본문에 컴퓨터 목록이 있는 200 OK.</span><span class="sxs-lookup"><span data-stu-id="e7b04-160">If successful - 200 OK with list of the machines in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="e7b04-161">예시</span><span class="sxs-lookup"><span data-stu-id="e7b04-161">Example</span></span>

<span data-ttu-id="e7b04-162">**요청**</span><span class="sxs-lookup"><span data-stu-id="e7b04-162">**Request**</span></span>

<span data-ttu-id="e7b04-163">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e7b04-163">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbytag?tag=testTag&useStartsWithFilter=true
```