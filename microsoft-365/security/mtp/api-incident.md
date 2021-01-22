---
title: Microsoft 365 Defender 인시던트 API 및 인시던트 리소스 유형
description: Microsoft 365 Defender의 인시던트 리소스 유형의 방법 및 속성에 대해 자세히 알아보기
keywords: 인시던트, 인시던트, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 37413c3c7458527e90d4657ddfb3afb058e1dfaa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928357"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="6fe12-104">Microsoft 365 Defender 인시던트 API 및 인시던트 리소스 유형</span><span class="sxs-lookup"><span data-stu-id="6fe12-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6fe12-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6fe12-105">**Applies to:**</span></span>

- <span data-ttu-id="6fe12-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6fe12-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fe12-107">일부 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 미리 판매된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6fe12-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="6fe12-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="6fe12-109">인시던트는 공격을 설명하는 데 도움이 되는 관련 경고 모음입니다. [](incidents-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6fe12-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="6fe12-110">조직의 여러 엔터티의 이벤트는 Microsoft 365 Defender에 의해 자동으로 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="6fe12-111">인시던트 API를 사용하여 프로그래밍하여 조직의 인시던트 및 관련 경고에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="6fe12-112">할당량 및 리소스 할당</span><span class="sxs-lookup"><span data-stu-id="6fe12-112">Quotas and resource allocation</span></span>

<span data-ttu-id="6fe12-113">분당 최대 50통 또는 시간당 1500통의 통화를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="6fe12-114">각 메서드에는 자체 할당량도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-114">Each method also has its own quotas.</span></span> <span data-ttu-id="6fe12-115">메서드별 할당량에 대한 자세한 내용은 사용할 메서드에 대한 각 문서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6fe12-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="6fe12-116">HTTP 응답 코드는 전송된 요청 수 또는 할당된 실행 시간으로 할당량에 도달했다는 `429` 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="6fe12-117">응답 본문에는 도달한 할당량 설정이 다시 설정될 때까지의 시간이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="6fe12-118">권한</span><span class="sxs-lookup"><span data-stu-id="6fe12-118">Permissions</span></span>

<span data-ttu-id="6fe12-119">인시던트 API에는 각 메서드에 대해 서로 다른 종류의 사용 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="6fe12-120">필요한 사용 권한에 대한 자세한 내용은 해당 방법의 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6fe12-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="6fe12-121">메서드</span><span class="sxs-lookup"><span data-stu-id="6fe12-121">Methods</span></span>

<span data-ttu-id="6fe12-122">메서드</span><span class="sxs-lookup"><span data-stu-id="6fe12-122">Method</span></span> | <span data-ttu-id="6fe12-123">반환 형식</span><span class="sxs-lookup"><span data-stu-id="6fe12-123">Return Type</span></span> | <span data-ttu-id="6fe12-124">설명</span><span class="sxs-lookup"><span data-stu-id="6fe12-124">Description</span></span>
-|-|-
[<span data-ttu-id="6fe12-125">인시던트 열거</span><span class="sxs-lookup"><span data-stu-id="6fe12-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="6fe12-126">[인시던트](api-incident.md) 목록</span><span class="sxs-lookup"><span data-stu-id="6fe12-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="6fe12-127">인시던트 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-127">Get a list of incidents.</span></span>
[<span data-ttu-id="6fe12-128">인시던트 업데이트</span><span class="sxs-lookup"><span data-stu-id="6fe12-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="6fe12-129">인시던트</span><span class="sxs-lookup"><span data-stu-id="6fe12-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="6fe12-130">특정 인시던트 업데이트</span><span class="sxs-lookup"><span data-stu-id="6fe12-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="6fe12-131">요청 본문, 응답 및 예제</span><span class="sxs-lookup"><span data-stu-id="6fe12-131">Request body, response, and examples</span></span>

<span data-ttu-id="6fe12-132">요청을 생성하거나 응답을 구문 분석하는 방법에 대한 자세한 내용과 실제 예제는 각 메서드 문서를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="6fe12-133">일반 속성</span><span class="sxs-lookup"><span data-stu-id="6fe12-133">Common properties</span></span>

<span data-ttu-id="6fe12-134">속성</span><span class="sxs-lookup"><span data-stu-id="6fe12-134">Property</span></span> | <span data-ttu-id="6fe12-135">유형</span><span class="sxs-lookup"><span data-stu-id="6fe12-135">Type</span></span> | <span data-ttu-id="6fe12-136">설명</span><span class="sxs-lookup"><span data-stu-id="6fe12-136">Description</span></span>
-|-|-
<span data-ttu-id="6fe12-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="6fe12-137">incidentId</span></span> | <span data-ttu-id="6fe12-138">long</span><span class="sxs-lookup"><span data-stu-id="6fe12-138">long</span></span> | <span data-ttu-id="6fe12-139">인시던트 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-139">Incident unique ID.</span></span>
<span data-ttu-id="6fe12-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="6fe12-140">redirectIncidentId</span></span> | <span data-ttu-id="6fe12-141">nullable long</span><span class="sxs-lookup"><span data-stu-id="6fe12-141">nullable long</span></span> | <span data-ttu-id="6fe12-142">현재 인시던트가 병합된 인시던트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="6fe12-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="6fe12-143">incidentName</span></span> | <span data-ttu-id="6fe12-144">문자열</span><span class="sxs-lookup"><span data-stu-id="6fe12-144">string</span></span> | <span data-ttu-id="6fe12-145">인시던트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-145">The name of the Incident.</span></span>
<span data-ttu-id="6fe12-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="6fe12-146">createdTime</span></span> | <span data-ttu-id="6fe12-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="6fe12-147">DateTimeOffset</span></span> | <span data-ttu-id="6fe12-148">인시던트가 만들어진 날짜 및 시간(UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="6fe12-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="6fe12-149">lastUpdateTime</span></span> | <span data-ttu-id="6fe12-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="6fe12-150">DateTimeOffset</span></span> | <span data-ttu-id="6fe12-151">인시던트가 마지막으로 업데이트된 날짜 및 시간(UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="6fe12-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="6fe12-152">assignedTo</span></span> | <span data-ttu-id="6fe12-153">문자열</span><span class="sxs-lookup"><span data-stu-id="6fe12-153">string</span></span> | <span data-ttu-id="6fe12-154">인시던트의 소유자입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-154">Owner of the Incident.</span></span>
<span data-ttu-id="6fe12-155">심각도</span><span class="sxs-lookup"><span data-stu-id="6fe12-155">severity</span></span> | <span data-ttu-id="6fe12-156">Enum</span><span class="sxs-lookup"><span data-stu-id="6fe12-156">Enum</span></span> | <span data-ttu-id="6fe12-157">인시던트의 심각도입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-157">Severity of the Incident.</span></span> <span data-ttu-id="6fe12-158">가능한 값은 ```UnSpecified``` , ```Informational``` , , 및 ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="6fe12-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="6fe12-159">status</span><span class="sxs-lookup"><span data-stu-id="6fe12-159">status</span></span> | <span data-ttu-id="6fe12-160">Enum</span><span class="sxs-lookup"><span data-stu-id="6fe12-160">Enum</span></span> | <span data-ttu-id="6fe12-161">인시던트의 현재 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="6fe12-162">가능한 값은 ```Active``` , ```Resolved``` 및 ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="6fe12-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="6fe12-163">classification</span><span class="sxs-lookup"><span data-stu-id="6fe12-163">classification</span></span> | <span data-ttu-id="6fe12-164">Enum</span><span class="sxs-lookup"><span data-stu-id="6fe12-164">Enum</span></span> | <span data-ttu-id="6fe12-165">인시던트 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-165">Specification of the incident.</span></span> <span data-ttu-id="6fe12-166">가능한 값은 ```Unknown``` ```FalsePositive``` , , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="6fe12-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="6fe12-167">determination</span><span class="sxs-lookup"><span data-stu-id="6fe12-167">determination</span></span> | <span data-ttu-id="6fe12-168">Enum</span><span class="sxs-lookup"><span data-stu-id="6fe12-168">Enum</span></span> | <span data-ttu-id="6fe12-169">인시던트의 결정</span><span class="sxs-lookup"><span data-stu-id="6fe12-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="6fe12-170">가능한 값은 ```NotAvailable``` ```Apt``` , ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` 입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="6fe12-171">tags</span><span class="sxs-lookup"><span data-stu-id="6fe12-171">tags</span></span> | <span data-ttu-id="6fe12-172">string List</span><span class="sxs-lookup"><span data-stu-id="6fe12-172">string List</span></span> | <span data-ttu-id="6fe12-173">인시던트 태그 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-173">List of Incident tags.</span></span>
<span data-ttu-id="6fe12-174">alerts</span><span class="sxs-lookup"><span data-stu-id="6fe12-174">alerts</span></span> | <span data-ttu-id="6fe12-175">경고 목록</span><span class="sxs-lookup"><span data-stu-id="6fe12-175">Alert List</span></span> | <span data-ttu-id="6fe12-176">관련 경고 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe12-176">List of related alerts.</span></span> <span data-ttu-id="6fe12-177">목록 인시던트 API [설명서의](api-list-incidents.md) 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6fe12-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6fe12-178">관련 문서</span><span class="sxs-lookup"><span data-stu-id="6fe12-178">Related articles</span></span>

- [<span data-ttu-id="6fe12-179">Microsoft 365 Defender API 개요</span><span class="sxs-lookup"><span data-stu-id="6fe12-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="6fe12-180">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="6fe12-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="6fe12-181">인시던트 목록 API</span><span class="sxs-lookup"><span data-stu-id="6fe12-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="6fe12-182">인시던트 업데이트 API</span><span class="sxs-lookup"><span data-stu-id="6fe12-182">Update incident API</span></span>](api-update-incidents.md)
