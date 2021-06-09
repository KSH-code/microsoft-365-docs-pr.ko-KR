---
title: 경고 엔터티 API 업데이트
description: 이 API를 사용하여 끝점용 Microsoft Defender 경고를 업데이트하는 방법을 학습합니다. 상태, 결정, 분류 및 assignedTo 속성을 업데이트할 수 있습니다.
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
ms.openlocfilehash: 043d423e1016d77cad4a175aa41718329f464252
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768931"
---
# <a name="update-alert"></a><span data-ttu-id="1681d-105">업데이트 경고</span><span class="sxs-lookup"><span data-stu-id="1681d-105">Update alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1681d-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="1681d-106">**Applies to:**</span></span>
- [<span data-ttu-id="1681d-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1681d-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="1681d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1681d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1681d-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="1681d-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1681d-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="1681d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="1681d-111">API 설명</span><span class="sxs-lookup"><span data-stu-id="1681d-111">API description</span></span>
<span data-ttu-id="1681d-112">기존 Alert의 속성을 [업데이트합니다.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="1681d-112">Updates properties of existing [Alert](alerts.md).</span></span>
<br><span data-ttu-id="1681d-113">설명 **제출은** 속성을 업데이트하거나 업데이트하지 않고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1681d-113">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="1681d-114">업데이트할 수 있는 속성은 ```status``` ```determination``` , 및 ```classification``` ```assignedTo``` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1681d-114">Updatable properties are: ```status```, ```determination```, ```classification``` and ```assignedTo```.</span></span>


## <a name="limitations"></a><span data-ttu-id="1681d-115">제한 사항</span><span class="sxs-lookup"><span data-stu-id="1681d-115">Limitations</span></span>
1. <span data-ttu-id="1681d-116">API에서 사용할 수 있는 경고를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1681d-116">You can update alerts that available in the API.</span></span> <span data-ttu-id="1681d-117">자세한 [내용은 목록 경고를](get-alerts.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1681d-117">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="1681d-118">이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.</span><span class="sxs-lookup"><span data-stu-id="1681d-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="1681d-119">사용 권한</span><span class="sxs-lookup"><span data-stu-id="1681d-119">Permissions</span></span>
<span data-ttu-id="1681d-120">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1681d-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1681d-121">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1681d-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="1681d-122">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="1681d-122">Permission type</span></span> |   <span data-ttu-id="1681d-123">사용 권한</span><span class="sxs-lookup"><span data-stu-id="1681d-123">Permission</span></span>  |   <span data-ttu-id="1681d-124">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="1681d-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1681d-125">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="1681d-125">Application</span></span> |   <span data-ttu-id="1681d-126">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="1681d-126">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="1681d-127">'모든 경고 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="1681d-127">'Read and write all alerts'</span></span>
<span data-ttu-id="1681d-128">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="1681d-128">Delegated (work or school account)</span></span> | <span data-ttu-id="1681d-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="1681d-129">Alert.ReadWrite</span></span> | <span data-ttu-id="1681d-130">'경고 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="1681d-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="1681d-131">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="1681d-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="1681d-132">사용자에게 최소한 '경고 조사'와 같은 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="1681d-132">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="1681d-133">사용자는 장치 그룹 설정에 따라 경고와 연결된 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="1681d-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="1681d-134">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="1681d-134">HTTP request</span></span>
```
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="1681d-135">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="1681d-135">Request headers</span></span>

<span data-ttu-id="1681d-136">이름</span><span class="sxs-lookup"><span data-stu-id="1681d-136">Name</span></span> | <span data-ttu-id="1681d-137">유형</span><span class="sxs-lookup"><span data-stu-id="1681d-137">Type</span></span> | <span data-ttu-id="1681d-138">설명</span><span class="sxs-lookup"><span data-stu-id="1681d-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="1681d-139">권한 부여</span><span class="sxs-lookup"><span data-stu-id="1681d-139">Authorization</span></span> | <span data-ttu-id="1681d-140">String</span><span class="sxs-lookup"><span data-stu-id="1681d-140">String</span></span> | <span data-ttu-id="1681d-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1681d-141">Bearer {token}.</span></span> <span data-ttu-id="1681d-142">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="1681d-142">**Required**.</span></span>
<span data-ttu-id="1681d-143">Content-Type</span><span class="sxs-lookup"><span data-stu-id="1681d-143">Content-Type</span></span> | <span data-ttu-id="1681d-144">String</span><span class="sxs-lookup"><span data-stu-id="1681d-144">String</span></span> | <span data-ttu-id="1681d-145">application/json.</span><span class="sxs-lookup"><span data-stu-id="1681d-145">application/json.</span></span> <span data-ttu-id="1681d-146">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="1681d-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1681d-147">요청 본문</span><span class="sxs-lookup"><span data-stu-id="1681d-147">Request body</span></span>
<span data-ttu-id="1681d-148">요청 본문에서 업데이트해야 하는 관련 필드의 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1681d-148">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="1681d-149">요청 본문에 포함되지 않은 기존 속성은 이전 값을 유지 관리하거나 다른 속성 값의 변경 내용에 따라 다시 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="1681d-149">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="1681d-150">최상의 성능을 위해 변경되지 않은 기존 값은 포함하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1681d-150">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="1681d-151">속성</span><span class="sxs-lookup"><span data-stu-id="1681d-151">Property</span></span> | <span data-ttu-id="1681d-152">유형</span><span class="sxs-lookup"><span data-stu-id="1681d-152">Type</span></span> | <span data-ttu-id="1681d-153">설명</span><span class="sxs-lookup"><span data-stu-id="1681d-153">Description</span></span>
:---|:---|:---
<span data-ttu-id="1681d-154">status</span><span class="sxs-lookup"><span data-stu-id="1681d-154">status</span></span> | <span data-ttu-id="1681d-155">String</span><span class="sxs-lookup"><span data-stu-id="1681d-155">String</span></span> | <span data-ttu-id="1681d-156">경고의 현재 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1681d-156">Specifies the current status of the alert.</span></span> <span data-ttu-id="1681d-157">속성 값은 'New', 'InProgress' 및 'Resolved'입니다.</span><span class="sxs-lookup"><span data-stu-id="1681d-157">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="1681d-158">assignedTo</span><span class="sxs-lookup"><span data-stu-id="1681d-158">assignedTo</span></span> | <span data-ttu-id="1681d-159">String</span><span class="sxs-lookup"><span data-stu-id="1681d-159">String</span></span> | <span data-ttu-id="1681d-160">경고의 소유자</span><span class="sxs-lookup"><span data-stu-id="1681d-160">Owner of the alert</span></span>
<span data-ttu-id="1681d-161">classification</span><span class="sxs-lookup"><span data-stu-id="1681d-161">classification</span></span> | <span data-ttu-id="1681d-162">String</span><span class="sxs-lookup"><span data-stu-id="1681d-162">String</span></span> | <span data-ttu-id="1681d-163">경고의 사양을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1681d-163">Specifies the specification of the alert.</span></span> <span data-ttu-id="1681d-164">속성 값은 '알 수 없음', 'FalsePositive', 'TruePositive'입니다.</span><span class="sxs-lookup"><span data-stu-id="1681d-164">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="1681d-165">determination</span><span class="sxs-lookup"><span data-stu-id="1681d-165">determination</span></span> | <span data-ttu-id="1681d-166">String</span><span class="sxs-lookup"><span data-stu-id="1681d-166">String</span></span> | <span data-ttu-id="1681d-167">경고 결정</span><span class="sxs-lookup"><span data-stu-id="1681d-167">Specifies the determination of the alert.</span></span> <span data-ttu-id="1681d-168">속성 값은 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'입니다.</span><span class="sxs-lookup"><span data-stu-id="1681d-168">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="1681d-169">comment</span><span class="sxs-lookup"><span data-stu-id="1681d-169">comment</span></span> | <span data-ttu-id="1681d-170">String</span><span class="sxs-lookup"><span data-stu-id="1681d-170">String</span></span> | <span data-ttu-id="1681d-171">경고에 추가할 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="1681d-171">Comment to be added to the alert.</span></span>

## <a name="response"></a><span data-ttu-id="1681d-172">응답</span><span class="sxs-lookup"><span data-stu-id="1681d-172">Response</span></span>
<span data-ttu-id="1681d-173">성공하면 이 메서드는 200 OK를 [](alerts.md) 반환하고 업데이트된 속성을 사용하여 응답 본문의 경고 엔터티를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1681d-173">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="1681d-174">지정된 ID가 있는 알림을 찾을 수 없는 경우 - 404 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1681d-174">If alert with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="1681d-175">예시</span><span class="sxs-lookup"><span data-stu-id="1681d-175">Example</span></span>

<span data-ttu-id="1681d-176">**요청**</span><span class="sxs-lookup"><span data-stu-id="1681d-176">**Request**</span></span>

<span data-ttu-id="1681d-177">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1681d-177">Here is an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
