---
title: 컴퓨터 엔터티 API 업데이트
description: 이 API를 사용하여 컴퓨터 태그를 업데이트하는 방법을 학습합니다. 태그 및 devicevalue 속성을 업데이트할 수 있습니다.
keywords: api, 그래프 api, 지원되는 api, get, alert, information, id
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
ms.openlocfilehash: 8f08b1fdafd653561ac2aae10a73f37b21874b59
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985750"
---
# <a name="update-machine"></a><span data-ttu-id="7783c-105">컴퓨터 업데이트</span><span class="sxs-lookup"><span data-stu-id="7783c-105">Update machine</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7783c-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7783c-106">**Applies to:**</span></span>
- [<span data-ttu-id="7783c-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7783c-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="7783c-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7783c-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7783c-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="7783c-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7783c-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="7783c-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="7783c-111">API 설명</span><span class="sxs-lookup"><span data-stu-id="7783c-111">API description</span></span>
<span data-ttu-id="7783c-112">기존 Machine의 속성을 [업데이트합니다.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="7783c-112">Updates properties of existing [Machine](machine.md).</span></span>
<br><span data-ttu-id="7783c-113">업데이트할 수 있는 속성은 ```machineTags``` 및 ```deviceValue``` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7783c-113">Updatable properties are: ```machineTags``` and ```deviceValue```.</span></span>


## <a name="limitations"></a><span data-ttu-id="7783c-114">제한 사항</span><span class="sxs-lookup"><span data-stu-id="7783c-114">Limitations</span></span>
1. <span data-ttu-id="7783c-115">API에서 사용할 수 있는 컴퓨터를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7783c-115">You can update machines that are available in the API.</span></span> 
2. <span data-ttu-id="7783c-116">업데이트 컴퓨터는 태그 컬렉션에 태그만 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7783c-116">Update machine only appends tags to the tag collection.</span></span> <span data-ttu-id="7783c-117">태그가 있는 경우 태그는 본문의 tags 컬렉션에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7783c-117">If tags exist, they must be included in the tags collection in the body.</span></span>
3. <span data-ttu-id="7783c-118">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="7783c-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="7783c-119">사용 권한</span><span class="sxs-lookup"><span data-stu-id="7783c-119">Permissions</span></span>
<span data-ttu-id="7783c-120">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7783c-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="7783c-121">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="7783c-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="7783c-122">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="7783c-122">Permission type</span></span> |   <span data-ttu-id="7783c-123">사용 권한</span><span class="sxs-lookup"><span data-stu-id="7783c-123">Permission</span></span>  |   <span data-ttu-id="7783c-124">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="7783c-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="7783c-125">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="7783c-125">Application</span></span> |   <span data-ttu-id="7783c-126">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="7783c-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="7783c-127">'모든 컴퓨터의 컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="7783c-127">'Read and write machine information for all machines'</span></span>
<span data-ttu-id="7783c-128">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="7783c-128">Delegated (work or school account)</span></span> | <span data-ttu-id="7783c-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="7783c-129">Machine.ReadWrite</span></span> | <span data-ttu-id="7783c-130">'컴퓨터 정보 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="7783c-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="7783c-131">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="7783c-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="7783c-132">사용자에게 최소한 '경고 조사'의 역할 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7783c-132">The user needs to have at least the following role permission: 'Alerts investigation'.</span></span> <span data-ttu-id="7783c-133">자세한 내용은 역할 만들기 [및 관리를 참조하세요.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="7783c-133">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="7783c-134">사용자는 장치 그룹 설정에 따라 경고와 연결된 장치에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7783c-134">The user needs to have access to the device associated with the alert, based on device group settings.</span></span> <span data-ttu-id="7783c-135">자세한 내용은 장치 그룹 [만들기 및 관리를 참조하세요.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="7783c-135">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="7783c-136">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="7783c-136">HTTP request</span></span>
```
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a><span data-ttu-id="7783c-137">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="7783c-137">Request headers</span></span>

<span data-ttu-id="7783c-138">이름</span><span class="sxs-lookup"><span data-stu-id="7783c-138">Name</span></span> | <span data-ttu-id="7783c-139">유형</span><span class="sxs-lookup"><span data-stu-id="7783c-139">Type</span></span> | <span data-ttu-id="7783c-140">설명</span><span class="sxs-lookup"><span data-stu-id="7783c-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="7783c-141">권한 부여</span><span class="sxs-lookup"><span data-stu-id="7783c-141">Authorization</span></span> | <span data-ttu-id="7783c-142">String</span><span class="sxs-lookup"><span data-stu-id="7783c-142">String</span></span> | <span data-ttu-id="7783c-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="7783c-143">Bearer {token}.</span></span> <span data-ttu-id="7783c-144">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="7783c-144">**Required**.</span></span>
<span data-ttu-id="7783c-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="7783c-145">Content-Type</span></span> | <span data-ttu-id="7783c-146">String</span><span class="sxs-lookup"><span data-stu-id="7783c-146">String</span></span> | <span data-ttu-id="7783c-147">application/json.</span><span class="sxs-lookup"><span data-stu-id="7783c-147">application/json.</span></span> <span data-ttu-id="7783c-148">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="7783c-148">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="7783c-149">요청 본문</span><span class="sxs-lookup"><span data-stu-id="7783c-149">Request body</span></span>
<span data-ttu-id="7783c-150">요청 본문에서 업데이트해야 하는 관련 필드의 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7783c-150">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="7783c-151">요청 본문에 포함되지 않은 기존 속성은 이전 값을 유지 관리하거나 다른 속성 값의 변경 내용에 따라 다시 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="7783c-151">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="7783c-152">최상의 성능을 위해 변경되지 않은 기존 값을 포함하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7783c-152">For best performance, you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="7783c-153">속성</span><span class="sxs-lookup"><span data-stu-id="7783c-153">Property</span></span> | <span data-ttu-id="7783c-154">유형</span><span class="sxs-lookup"><span data-stu-id="7783c-154">Type</span></span> | <span data-ttu-id="7783c-155">설명</span><span class="sxs-lookup"><span data-stu-id="7783c-155">Description</span></span>
:---|:---|:---
<span data-ttu-id="7783c-156">machineTags</span><span class="sxs-lookup"><span data-stu-id="7783c-156">machineTags</span></span> | <span data-ttu-id="7783c-157">문자열 컬렉션</span><span class="sxs-lookup"><span data-stu-id="7783c-157">String collection</span></span> | <span data-ttu-id="7783c-158">컴퓨터 [태그](machine.md) 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="7783c-158">Set of [machine](machine.md) tags.</span></span>
<span data-ttu-id="7783c-159">deviceValue</span><span class="sxs-lookup"><span data-stu-id="7783c-159">deviceValue</span></span> | <span data-ttu-id="7783c-160">Nullable Enum</span><span class="sxs-lookup"><span data-stu-id="7783c-160">Nullable Enum</span></span> | <span data-ttu-id="7783c-161">디바이스의 [값입니다.](tvm-assign-device-value.md)</span><span class="sxs-lookup"><span data-stu-id="7783c-161">The [value of the device](tvm-assign-device-value.md).</span></span> <span data-ttu-id="7783c-162">가능한 값은 '보통', '낮음' 및 '높음'입니다.</span><span class="sxs-lookup"><span data-stu-id="7783c-162">Possible values are: 'Normal', 'Low' and 'High'.</span></span>

## <a name="response"></a><span data-ttu-id="7783c-163">응답</span><span class="sxs-lookup"><span data-stu-id="7783c-163">Response</span></span>
<span data-ttu-id="7783c-164">성공하면 이 메서드는 200 OK를 [](machine.md) 반환하고 업데이트된 속성을 사용하여 응답 본문의 컴퓨터 엔터티를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7783c-164">If successful, this method returns 200 OK, and the [machine](machine.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="7783c-165">본문에 있는 컴퓨터 태그 컬렉션에 기존 컴퓨터 태그가 없는 경우 - 400 잘못된 입력 및 누락된 태그/s를 알리는 메시지</span><span class="sxs-lookup"><span data-stu-id="7783c-165">If machine tags collection in body doesn't contain existing machine tags - 400 Invalid Input and a message informing of the missing tag/s.</span></span>
<span data-ttu-id="7783c-166">지정한 ID가 있는 머신을 찾을 수 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7783c-166">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="7783c-167">예시</span><span class="sxs-lookup"><span data-stu-id="7783c-167">Example</span></span>

<span data-ttu-id="7783c-168">**요청**</span><span class="sxs-lookup"><span data-stu-id="7783c-168">**Request**</span></span>

<span data-ttu-id="7783c-169">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7783c-169">Here's an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10",
                     "Windows Insider - Fast"
    ]
}
```
