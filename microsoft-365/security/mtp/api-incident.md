---
title: Microsoft 365 Defender 인시던트 API 및 인시던트 리소스 유형
description: Microsoft 365 Defender의 인시던트 리소스 유형의 방법 및 속성에 대해 자세히 알아보기
keywords: 인시던트, 인시던트, api
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
ms.openlocfilehash: 372c939f5eed29832725e6b048735040ca7391d6
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719337"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="f69c2-104">Microsoft 365 Defender 인시던트 API 및 인시던트 리소스 유형</span><span class="sxs-lookup"><span data-stu-id="f69c2-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f69c2-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f69c2-105">**Applies to:**</span></span>

- <span data-ttu-id="f69c2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f69c2-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f69c2-107">일부 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 미리 판매된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f69c2-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="f69c2-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="f69c2-109">인시던트는 공격을 설명하는 데 도움이 되는 관련 경고 모음입니다. [](incidents-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f69c2-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="f69c2-110">조직의 여러 엔터티의 이벤트는 Microsoft 365 Defender에 의해 자동으로 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="f69c2-111">인시던트 API를 사용하여 프로그래밍하여 조직의 인시던트 및 관련 경고에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="f69c2-112">할당량 및 리소스 할당</span><span class="sxs-lookup"><span data-stu-id="f69c2-112">Quotas and resource allocation</span></span>

<span data-ttu-id="f69c2-113">분당 최대 50통 또는 시간당 1500통의 통화를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="f69c2-114">각 메서드에는 자체 할당량도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-114">Each method also has its own quotas.</span></span> <span data-ttu-id="f69c2-115">메서드별 할당량에 대한 자세한 내용은 사용할 메서드에 대한 각 문서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f69c2-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="f69c2-116">HTTP 응답 코드는 전송된 요청 수 또는 할당된 실행 시간으로 할당량에 도달했다는 `429` 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="f69c2-117">응답 본문에는 도달한 할당량 설정이 다시 설정될 때까지의 시간이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="f69c2-118">권한</span><span class="sxs-lookup"><span data-stu-id="f69c2-118">Permissions</span></span>

<span data-ttu-id="f69c2-119">인시던트 API에는 각 메서드에 대해 서로 다른 종류의 사용 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="f69c2-120">필요한 사용 권한에 대한 자세한 내용은 해당 방법의 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f69c2-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="f69c2-121">메서드</span><span class="sxs-lookup"><span data-stu-id="f69c2-121">Methods</span></span>

<span data-ttu-id="f69c2-122">메서드</span><span class="sxs-lookup"><span data-stu-id="f69c2-122">Method</span></span> | <span data-ttu-id="f69c2-123">반환 형식</span><span class="sxs-lookup"><span data-stu-id="f69c2-123">Return Type</span></span> | <span data-ttu-id="f69c2-124">설명</span><span class="sxs-lookup"><span data-stu-id="f69c2-124">Description</span></span>
-|-|-
[<span data-ttu-id="f69c2-125">인시던트 열거</span><span class="sxs-lookup"><span data-stu-id="f69c2-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="f69c2-126">[인시던트](api-incident.md) 목록</span><span class="sxs-lookup"><span data-stu-id="f69c2-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="f69c2-127">인시던트 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-127">Get a list of incidents.</span></span>
[<span data-ttu-id="f69c2-128">인시던트 업데이트</span><span class="sxs-lookup"><span data-stu-id="f69c2-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="f69c2-129">인시던트</span><span class="sxs-lookup"><span data-stu-id="f69c2-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="f69c2-130">특정 인시던트 업데이트</span><span class="sxs-lookup"><span data-stu-id="f69c2-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="f69c2-131">요청 본문, 응답 및 예제</span><span class="sxs-lookup"><span data-stu-id="f69c2-131">Request body, response, and examples</span></span>

<span data-ttu-id="f69c2-132">요청을 생성하거나 응답을 구문 분석하는 방법에 대한 자세한 내용과 실제 예제는 각 메서드 문서를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="f69c2-133">일반 속성</span><span class="sxs-lookup"><span data-stu-id="f69c2-133">Common properties</span></span>

<span data-ttu-id="f69c2-134">속성</span><span class="sxs-lookup"><span data-stu-id="f69c2-134">Property</span></span> | <span data-ttu-id="f69c2-135">유형</span><span class="sxs-lookup"><span data-stu-id="f69c2-135">Type</span></span> | <span data-ttu-id="f69c2-136">설명</span><span class="sxs-lookup"><span data-stu-id="f69c2-136">Description</span></span>
-|-|-
<span data-ttu-id="f69c2-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="f69c2-137">incidentId</span></span> | <span data-ttu-id="f69c2-138">long</span><span class="sxs-lookup"><span data-stu-id="f69c2-138">long</span></span> | <span data-ttu-id="f69c2-139">인시던트 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-139">Incident unique ID.</span></span>
<span data-ttu-id="f69c2-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="f69c2-140">redirectIncidentId</span></span> | <span data-ttu-id="f69c2-141">nullable long</span><span class="sxs-lookup"><span data-stu-id="f69c2-141">nullable long</span></span> | <span data-ttu-id="f69c2-142">현재 인시던트가 병합된 인시던트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="f69c2-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="f69c2-143">incidentName</span></span> | <span data-ttu-id="f69c2-144">문자열</span><span class="sxs-lookup"><span data-stu-id="f69c2-144">string</span></span> | <span data-ttu-id="f69c2-145">인시던트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-145">The name of the Incident.</span></span>
<span data-ttu-id="f69c2-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="f69c2-146">createdTime</span></span> | <span data-ttu-id="f69c2-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="f69c2-147">DateTimeOffset</span></span> | <span data-ttu-id="f69c2-148">인시던트가 만들어진 날짜 및 시간(UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="f69c2-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="f69c2-149">lastUpdateTime</span></span> | <span data-ttu-id="f69c2-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="f69c2-150">DateTimeOffset</span></span> | <span data-ttu-id="f69c2-151">인시던트가 마지막으로 업데이트된 날짜 및 시간(UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="f69c2-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="f69c2-152">assignedTo</span></span> | <span data-ttu-id="f69c2-153">문자열</span><span class="sxs-lookup"><span data-stu-id="f69c2-153">string</span></span> | <span data-ttu-id="f69c2-154">인시던트의 소유자입니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-154">Owner of the Incident.</span></span>
<span data-ttu-id="f69c2-155">심각도</span><span class="sxs-lookup"><span data-stu-id="f69c2-155">severity</span></span> | <span data-ttu-id="f69c2-156">Enum</span><span class="sxs-lookup"><span data-stu-id="f69c2-156">Enum</span></span> | <span data-ttu-id="f69c2-157">인시던트의 심각도입니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-157">Severity of the Incident.</span></span> <span data-ttu-id="f69c2-158">가능한 값은 ```UnSpecified``` , ```Informational``` , , 및 ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="f69c2-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="f69c2-159">status</span><span class="sxs-lookup"><span data-stu-id="f69c2-159">status</span></span> | <span data-ttu-id="f69c2-160">Enum</span><span class="sxs-lookup"><span data-stu-id="f69c2-160">Enum</span></span> | <span data-ttu-id="f69c2-161">인시던트의 현재 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="f69c2-162">가능한 값은 ```Active``` , ```Resolved``` 및 ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="f69c2-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="f69c2-163">classification</span><span class="sxs-lookup"><span data-stu-id="f69c2-163">classification</span></span> | <span data-ttu-id="f69c2-164">Enum</span><span class="sxs-lookup"><span data-stu-id="f69c2-164">Enum</span></span> | <span data-ttu-id="f69c2-165">인시던트 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-165">Specification of the incident.</span></span> <span data-ttu-id="f69c2-166">가능한 값은 ```Unknown``` ```FalsePositive``` , , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="f69c2-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="f69c2-167">determination</span><span class="sxs-lookup"><span data-stu-id="f69c2-167">determination</span></span> | <span data-ttu-id="f69c2-168">Enum</span><span class="sxs-lookup"><span data-stu-id="f69c2-168">Enum</span></span> | <span data-ttu-id="f69c2-169">인시던트의 결정</span><span class="sxs-lookup"><span data-stu-id="f69c2-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="f69c2-170">가능한 값은 ```NotAvailable``` ```Apt``` , ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` 입니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="f69c2-171">tags</span><span class="sxs-lookup"><span data-stu-id="f69c2-171">tags</span></span> | <span data-ttu-id="f69c2-172">string List</span><span class="sxs-lookup"><span data-stu-id="f69c2-172">string List</span></span> | <span data-ttu-id="f69c2-173">인시던트 태그 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-173">List of Incident tags.</span></span>
<span data-ttu-id="f69c2-174">alerts</span><span class="sxs-lookup"><span data-stu-id="f69c2-174">alerts</span></span> | <span data-ttu-id="f69c2-175">경고 목록</span><span class="sxs-lookup"><span data-stu-id="f69c2-175">Alert List</span></span> | <span data-ttu-id="f69c2-176">관련 경고 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f69c2-176">List of related alerts.</span></span> <span data-ttu-id="f69c2-177">목록 인시던트 API [설명서에서 예제를](api-list-incidents.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f69c2-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f69c2-178">관련 문서</span><span class="sxs-lookup"><span data-stu-id="f69c2-178">Related articles</span></span>

- [<span data-ttu-id="f69c2-179">Microsoft 365 Defender API 개요</span><span class="sxs-lookup"><span data-stu-id="f69c2-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="f69c2-180">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="f69c2-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="f69c2-181">인시던트 목록 API</span><span class="sxs-lookup"><span data-stu-id="f69c2-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="f69c2-182">인시던트 업데이트 API</span><span class="sxs-lookup"><span data-stu-id="f69c2-182">Update incident API</span></span>](api-update-incidents.md)
