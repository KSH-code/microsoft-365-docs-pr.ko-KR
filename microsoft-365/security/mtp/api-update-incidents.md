---
title: 인시던트 업데이트 API
description: Microsoft 365 Defender API를 사용하여 인시던트 업데이트 방법 학습
keywords: 업데이트, api, 인시던트
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 6fc1ff730994f03aa500ad9a4559b66970e32d87
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719407"
---
# <a name="update-incidents-api"></a><span data-ttu-id="783e4-104">인시던트 업데이트 API</span><span class="sxs-lookup"><span data-stu-id="783e4-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="783e4-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="783e4-105">**Applies to:**</span></span>

- <span data-ttu-id="783e4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="783e4-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="783e4-107">일부 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 미리 판매된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="783e4-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="783e4-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="783e4-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="783e4-109">API 설명</span><span class="sxs-lookup"><span data-stu-id="783e4-109">API description</span></span>

<span data-ttu-id="783e4-110">기존 인시던트의 속성을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="783e4-110">Updates properties of existing incident.</span></span> <span data-ttu-id="783e4-111">업데이트할 수 있는 속성은 ```status``` , ```determination``` 및 ```classification``` ```assignedTo``` ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="783e4-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, and ```tags```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="783e4-112">할당량, 리소스 할당 및 기타 제약 조건</span><span class="sxs-lookup"><span data-stu-id="783e4-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="783e4-113">제한 임계값에 도달하기 전에 분당 최대 50통 또는 시간당 1500통의 통화를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="783e4-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="783e4-114">이 속성은 `determination` `classification` TruePositive로 설정된 경우만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="783e4-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="783e4-115">요청이 스로틀된 경우 응답 `429` 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="783e4-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="783e4-116">응답 본문은 새 통화를 시작할 수 있는 시간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="783e4-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="783e4-117">권한</span><span class="sxs-lookup"><span data-stu-id="783e4-117">Permissions</span></span>

<span data-ttu-id="783e4-118">이 API를 호출하려면 다음 권한 중 하나를 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="783e4-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="783e4-119">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Microsoft 365 Defender API](api-access.md)액세스를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="783e4-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="783e4-120">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="783e4-120">Permission type</span></span> | <span data-ttu-id="783e4-121">사용 권한</span><span class="sxs-lookup"><span data-stu-id="783e4-121">Permission</span></span> | <span data-ttu-id="783e4-122">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="783e4-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="783e4-123">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="783e4-123">Application</span></span> | <span data-ttu-id="783e4-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="783e4-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="783e4-125">모든 인시던트 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="783e4-125">Read and write all incidents</span></span>
<span data-ttu-id="783e4-126">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="783e4-126">Delegated (work or school account)</span></span> | <span data-ttu-id="783e4-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="783e4-127">Incident.ReadWrite</span></span> | <span data-ttu-id="783e4-128">인시던트 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="783e4-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="783e4-129">사용자 자격 증명을 사용하여 토큰을 얻을 때 사용자는 포털에서 인시던트 업데이트 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="783e4-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="783e4-130">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="783e4-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="783e4-131">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="783e4-131">Request headers</span></span>

<span data-ttu-id="783e4-132">이름</span><span class="sxs-lookup"><span data-stu-id="783e4-132">Name</span></span> | <span data-ttu-id="783e4-133">유형</span><span class="sxs-lookup"><span data-stu-id="783e4-133">Type</span></span> | <span data-ttu-id="783e4-134">설명</span><span class="sxs-lookup"><span data-stu-id="783e4-134">Description</span></span>
-|-|-
<span data-ttu-id="783e4-135">권한 부여</span><span class="sxs-lookup"><span data-stu-id="783e4-135">Authorization</span></span> | <span data-ttu-id="783e4-136">문자열</span><span class="sxs-lookup"><span data-stu-id="783e4-136">String</span></span> | <span data-ttu-id="783e4-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="783e4-137">Bearer {token}.</span></span> <span data-ttu-id="783e4-138">**필수 .**</span><span class="sxs-lookup"><span data-stu-id="783e4-138">**Required**.</span></span>
<span data-ttu-id="783e4-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="783e4-139">Content-Type</span></span> | <span data-ttu-id="783e4-140">문자열</span><span class="sxs-lookup"><span data-stu-id="783e4-140">String</span></span> | <span data-ttu-id="783e4-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="783e4-141">application/json.</span></span> <span data-ttu-id="783e4-142">**필수 .**</span><span class="sxs-lookup"><span data-stu-id="783e4-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="783e4-143">요청 본문</span><span class="sxs-lookup"><span data-stu-id="783e4-143">Request body</span></span>

<span data-ttu-id="783e4-144">요청 본문에 업데이트해야 하는 필드의 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="783e4-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="783e4-145">관련 값의 변경으로 인해 다시 계산해야 하는 경우를 위해 요청 본문에 포함되지 않은 기존 속성은 해당 값을 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="783e4-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="783e4-146">최상의 성능을 위해 변경되지 않은 기존 값을 생략해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="783e4-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="783e4-147">속성</span><span class="sxs-lookup"><span data-stu-id="783e4-147">Property</span></span> | <span data-ttu-id="783e4-148">유형</span><span class="sxs-lookup"><span data-stu-id="783e4-148">Type</span></span> | <span data-ttu-id="783e4-149">설명</span><span class="sxs-lookup"><span data-stu-id="783e4-149">Description</span></span>
-|-|-
<span data-ttu-id="783e4-150">status</span><span class="sxs-lookup"><span data-stu-id="783e4-150">status</span></span> | <span data-ttu-id="783e4-151">Enum</span><span class="sxs-lookup"><span data-stu-id="783e4-151">Enum</span></span> | <span data-ttu-id="783e4-152">경고의 현재 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="783e4-152">Specifies the current status of the alert.</span></span> <span data-ttu-id="783e4-153">가능한 값은 ```Active``` , ```Resolved``` 및 ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="783e4-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="783e4-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="783e4-154">assignedTo</span></span> | <span data-ttu-id="783e4-155">문자열</span><span class="sxs-lookup"><span data-stu-id="783e4-155">string</span></span> | <span data-ttu-id="783e4-156">인시던트의 소유자입니다.</span><span class="sxs-lookup"><span data-stu-id="783e4-156">Owner of the incident.</span></span>
<span data-ttu-id="783e4-157">classification</span><span class="sxs-lookup"><span data-stu-id="783e4-157">classification</span></span> | <span data-ttu-id="783e4-158">Enum</span><span class="sxs-lookup"><span data-stu-id="783e4-158">Enum</span></span> | <span data-ttu-id="783e4-159">경고 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="783e4-159">Specification of the alert.</span></span> <span data-ttu-id="783e4-160">가능한 값은 ```Unknown``` ```FalsePositive``` , , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="783e4-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="783e4-161">determination</span><span class="sxs-lookup"><span data-stu-id="783e4-161">determination</span></span> | <span data-ttu-id="783e4-162">Enum</span><span class="sxs-lookup"><span data-stu-id="783e4-162">Enum</span></span> | <span data-ttu-id="783e4-163">경고 결정</span><span class="sxs-lookup"><span data-stu-id="783e4-163">Specifies the determination of the alert.</span></span> <span data-ttu-id="783e4-164">가능한 값은 ```NotAvailable``` ```Apt``` , ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` 입니다.</span><span class="sxs-lookup"><span data-stu-id="783e4-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="783e4-165">tags</span><span class="sxs-lookup"><span data-stu-id="783e4-165">tags</span></span> | <span data-ttu-id="783e4-166">string List</span><span class="sxs-lookup"><span data-stu-id="783e4-166">string List</span></span> | <span data-ttu-id="783e4-167">인시던트 태그 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="783e4-167">List of Incident tags.</span></span>

## <a name="response"></a><span data-ttu-id="783e4-168">응답</span><span class="sxs-lookup"><span data-stu-id="783e4-168">Response</span></span>

<span data-ttu-id="783e4-169">성공하면 이 메서드는 `200 OK` 를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="783e4-169">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="783e4-170">응답 본문에는 업데이트된 속성이 포함된 인시던트 엔터티가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="783e4-170">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="783e4-171">지정한 ID의 인시던트가 발견되지 않으면 메서드에서 `404 Not Found` 를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="783e4-171">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="783e4-172">예제</span><span class="sxs-lookup"><span data-stu-id="783e4-172">Example</span></span>

<span data-ttu-id="783e4-173">**요청**</span><span class="sxs-lookup"><span data-stu-id="783e4-173">**Request**</span></span>

<span data-ttu-id="783e4-174">요청의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="783e4-174">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="783e4-175">**응답**</span><span class="sxs-lookup"><span data-stu-id="783e4-175">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a><span data-ttu-id="783e4-176">관련 문서</span><span class="sxs-lookup"><span data-stu-id="783e4-176">Related articles</span></span>

- [<span data-ttu-id="783e4-177">Microsoft 365 Defender API 액세스</span><span class="sxs-lookup"><span data-stu-id="783e4-177">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="783e4-178">API 제한 및 라이선싱에 대해 자세히</span><span class="sxs-lookup"><span data-stu-id="783e4-178">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="783e4-179">오류 코드 이해</span><span class="sxs-lookup"><span data-stu-id="783e4-179">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="783e4-180">인시던트 API</span><span class="sxs-lookup"><span data-stu-id="783e4-180">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="783e4-181">인시던트 열거</span><span class="sxs-lookup"><span data-stu-id="783e4-181">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="783e4-182">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="783e4-182">Incidents overview</span></span>](incidents-overview.md)
