---
title: 일괄 업데이트 경고 엔터티 API
description: 이 API를 사용하여 일괄적으로 끝점 경고에 대한 Microsoft Defender를 업데이트하는 방법을 학습합니다. 상태, 결정, 분류 및 assignedTo 속성을 업데이트할 수 있습니다.
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
ms.technology: mde
ms.openlocfilehash: 80f88b31c1e07d1f40f3f58a1bd21b4a5c58c60b
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290210"
---
# <a name="batch-update-alerts"></a><span data-ttu-id="d864d-105">일괄 업데이트 경고</span><span class="sxs-lookup"><span data-stu-id="d864d-105">Batch update alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d864d-106">**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="d864d-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="d864d-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="d864d-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d864d-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d864d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="d864d-109">API 설명</span><span class="sxs-lookup"><span data-stu-id="d864d-109">API description</span></span>

<span data-ttu-id="d864d-110">기존 Alerts 일괄 처리의 [속성을 업데이트합니다.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="d864d-110">Updates properties of a batch of existing [Alerts](alerts.md).</span></span>

<span data-ttu-id="d864d-111">설명 **제출은** 속성을 업데이트하거나 업데이트하지 않고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d864d-111">Submission of **comment** is available with or without updating properties.</span></span>

<span data-ttu-id="d864d-112">업데이트할 수 있는 속성은 `status` `determination` , 및 `classification` `assignedTo` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d864d-112">Updatable properties are: `status`, `determination`, `classification` and `assignedTo`.</span></span>

## <a name="limitations"></a><span data-ttu-id="d864d-113">제한 사항</span><span class="sxs-lookup"><span data-stu-id="d864d-113">Limitations</span></span>

1. <span data-ttu-id="d864d-114">API에서 사용할 수 있는 경고를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d864d-114">You can update alerts that are available in the API.</span></span> <span data-ttu-id="d864d-115">자세한 [내용은 목록 경고를](get-alerts.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d864d-115">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="d864d-116">이 API에 대한 속도 제한은 분당 10개 호출과 시간당 500개 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="d864d-116">Rate limitations for this API are 10 calls per minute and 500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="d864d-117">사용 권한</span><span class="sxs-lookup"><span data-stu-id="d864d-117">Permissions</span></span>

<span data-ttu-id="d864d-118">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d864d-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d864d-119">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d864d-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="d864d-120">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="d864d-120">Permission type</span></span> | <span data-ttu-id="d864d-121">사용 권한</span><span class="sxs-lookup"><span data-stu-id="d864d-121">Permission</span></span> | <span data-ttu-id="d864d-122">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="d864d-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d864d-123">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="d864d-123">Application</span></span> | <span data-ttu-id="d864d-124">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="d864d-124">Alerts.ReadWrite.All</span></span> | <span data-ttu-id="d864d-125">'모든 경고 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="d864d-125">'Read and write all alerts'</span></span>
<span data-ttu-id="d864d-126">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="d864d-126">Delegated (work or school account)</span></span> | <span data-ttu-id="d864d-127">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d864d-127">Alert.ReadWrite</span></span> | <span data-ttu-id="d864d-128">'경고 읽기 및 쓰기'</span><span class="sxs-lookup"><span data-stu-id="d864d-128">'Read and write alerts'</span></span>

> [!NOTE]
> <span data-ttu-id="d864d-129">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="d864d-129">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="d864d-130">사용자에게 최소한 '경고 조사'와 같은 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).</span><span class="sxs-lookup"><span data-stu-id="d864d-130">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="d864d-131">사용자는 장치 그룹 설정에 따라 경고와 연결된 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="d864d-131">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="d864d-132">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="d864d-132">HTTP request</span></span>

```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a><span data-ttu-id="d864d-133">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="d864d-133">Request headers</span></span>

<span data-ttu-id="d864d-134">이름</span><span class="sxs-lookup"><span data-stu-id="d864d-134">Name</span></span> | <span data-ttu-id="d864d-135">유형</span><span class="sxs-lookup"><span data-stu-id="d864d-135">Type</span></span> | <span data-ttu-id="d864d-136">설명</span><span class="sxs-lookup"><span data-stu-id="d864d-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="d864d-137">권한 부여</span><span class="sxs-lookup"><span data-stu-id="d864d-137">Authorization</span></span> | <span data-ttu-id="d864d-138">문자열</span><span class="sxs-lookup"><span data-stu-id="d864d-138">String</span></span> | <span data-ttu-id="d864d-139">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="d864d-139">Bearer {token}.</span></span> <span data-ttu-id="d864d-140">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="d864d-140">**Required**.</span></span>
<span data-ttu-id="d864d-141">Content-Type</span><span class="sxs-lookup"><span data-stu-id="d864d-141">Content-Type</span></span> | <span data-ttu-id="d864d-142">문자열</span><span class="sxs-lookup"><span data-stu-id="d864d-142">String</span></span> | <span data-ttu-id="d864d-143">application/json.</span><span class="sxs-lookup"><span data-stu-id="d864d-143">application/json.</span></span> <span data-ttu-id="d864d-144">**필수입니다**.</span><span class="sxs-lookup"><span data-stu-id="d864d-144">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="d864d-145">요청 본문</span><span class="sxs-lookup"><span data-stu-id="d864d-145">Request body</span></span>

<span data-ttu-id="d864d-146">요청 본문에 업데이트할 경고의 ID와 이러한 경고에 대해 업데이트할 관련 필드의 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d864d-146">In the request body, supply the IDs of the alerts to be updated and the values of the relevant fields that you wish to update for these alerts.</span></span>

<span data-ttu-id="d864d-147">요청 본문에 포함되지 않은 기존 속성은 이전 값을 유지 관리하거나 다른 속성 값의 변경 내용에 따라 다시 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="d864d-147">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span>

<span data-ttu-id="d864d-148">최상의 성능을 위해 변경되지 않은 기존 값은 포함하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d864d-148">For best performance you shouldn't include existing values that haven't changed.</span></span>

<span data-ttu-id="d864d-149">속성</span><span class="sxs-lookup"><span data-stu-id="d864d-149">Property</span></span> | <span data-ttu-id="d864d-150">유형</span><span class="sxs-lookup"><span data-stu-id="d864d-150">Type</span></span> | <span data-ttu-id="d864d-151">설명</span><span class="sxs-lookup"><span data-stu-id="d864d-151">Description</span></span>
:---|:---|:---
<span data-ttu-id="d864d-152">alertIds</span><span class="sxs-lookup"><span data-stu-id="d864d-152">alertIds</span></span> | <span data-ttu-id="d864d-153">목록 &lt; 문자열&gt;</span><span class="sxs-lookup"><span data-stu-id="d864d-153">List&lt;String&gt;</span></span>| <span data-ttu-id="d864d-154">업데이트할 경고의 IDS 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d864d-154">A list of the IDs of the alerts to be updated.</span></span> <span data-ttu-id="d864d-155">**필수**</span><span class="sxs-lookup"><span data-stu-id="d864d-155">**Required**</span></span>
<span data-ttu-id="d864d-156">status</span><span class="sxs-lookup"><span data-stu-id="d864d-156">status</span></span> | <span data-ttu-id="d864d-157">문자열</span><span class="sxs-lookup"><span data-stu-id="d864d-157">String</span></span> | <span data-ttu-id="d864d-158">지정한 경고의 업데이트된 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d864d-158">Specifies the updated status of the specified alerts.</span></span> <span data-ttu-id="d864d-159">속성 값은 'New', 'InProgress' 및 'Resolved'입니다.</span><span class="sxs-lookup"><span data-stu-id="d864d-159">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="d864d-160">assignedTo</span><span class="sxs-lookup"><span data-stu-id="d864d-160">assignedTo</span></span> | <span data-ttu-id="d864d-161">문자열</span><span class="sxs-lookup"><span data-stu-id="d864d-161">String</span></span> | <span data-ttu-id="d864d-162">지정된 경고의 소유자</span><span class="sxs-lookup"><span data-stu-id="d864d-162">Owner of the specified alerts</span></span>
<span data-ttu-id="d864d-163">classification</span><span class="sxs-lookup"><span data-stu-id="d864d-163">classification</span></span> | <span data-ttu-id="d864d-164">문자열</span><span class="sxs-lookup"><span data-stu-id="d864d-164">String</span></span> | <span data-ttu-id="d864d-165">지정한 경고의 사양을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d864d-165">Specifies the specification of the specified alerts.</span></span> <span data-ttu-id="d864d-166">속성 값은 '알 수 없음', 'FalsePositive', 'TruePositive'입니다.</span><span class="sxs-lookup"><span data-stu-id="d864d-166">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="d864d-167">determination</span><span class="sxs-lookup"><span data-stu-id="d864d-167">determination</span></span> | <span data-ttu-id="d864d-168">문자열</span><span class="sxs-lookup"><span data-stu-id="d864d-168">String</span></span> | <span data-ttu-id="d864d-169">지정한 경고의 결정에 대해 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d864d-169">Specifies the determination of the specified alerts.</span></span> <span data-ttu-id="d864d-170">속성 값은 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'입니다.</span><span class="sxs-lookup"><span data-stu-id="d864d-170">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="d864d-171">comment</span><span class="sxs-lookup"><span data-stu-id="d864d-171">comment</span></span> | <span data-ttu-id="d864d-172">문자열</span><span class="sxs-lookup"><span data-stu-id="d864d-172">String</span></span> | <span data-ttu-id="d864d-173">지정한 경고에 추가할 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="d864d-173">Comment to be added to the specified alerts.</span></span>

## <a name="response"></a><span data-ttu-id="d864d-174">응답</span><span class="sxs-lookup"><span data-stu-id="d864d-174">Response</span></span>

<span data-ttu-id="d864d-175">성공하면 이 메서드는 응답 본문이 비어 있는 200 OK를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d864d-175">If successful, this method returns 200 OK, with an empty response body.</span></span>

## <a name="example"></a><span data-ttu-id="d864d-176">예제</span><span class="sxs-lookup"><span data-stu-id="d864d-176">Example</span></span>

### <a name="request"></a><span data-ttu-id="d864d-177">요청</span><span class="sxs-lookup"><span data-stu-id="d864d-177">Request</span></span>

<span data-ttu-id="d864d-178">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d864d-178">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/batchUpdate
```

```json
{
    "alertIds": ["da637399794050273582_760707377", "da637399989469816469_51697947354"],
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
