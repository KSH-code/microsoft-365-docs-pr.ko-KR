---
title: Microsoft 365 Defender 인시던트 API 및 인시던트 리소스 유형
description: Defender에서 인시던트 리소스 유형의 방법 및 속성에 Microsoft 365 정보
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0c0c2e280f63076687a0854e25c47577b050a8f7
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888436"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a><span data-ttu-id="36ab4-104">Microsoft 365 Defender 인시던트 API 및 인시던트 리소스 유형</span><span class="sxs-lookup"><span data-stu-id="36ab4-104">Microsoft 365 Defender incidents API and the incidents resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="36ab4-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="36ab4-105">**Applies to:**</span></span>

- [<span data-ttu-id="36ab4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36ab4-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="36ab4-107">일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="36ab4-108">Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="36ab4-109">인시던트는 공격을 설명하는 데 도움이 되는 관련 경고 모음입니다. [](incidents-overview.md)</span><span class="sxs-lookup"><span data-stu-id="36ab4-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="36ab4-110">조직의 여러 엔터티의 이벤트는 Defender에 의해 Microsoft 365 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="36ab4-111">인시던트 API를 사용하여 조직의 인시던트 및 관련 경고에 프로그래밍적으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="36ab4-112">할당량 및 리소스 할당</span><span class="sxs-lookup"><span data-stu-id="36ab4-112">Quotas and resource allocation</span></span>

<span data-ttu-id="36ab4-113">분당 최대 50통 또는 시간당 1500통을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="36ab4-114">각 메서드에는 자체 할당량도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-114">Each method also has its own quotas.</span></span> <span data-ttu-id="36ab4-115">메서드별 할당량에 대한 자세한 내용은 사용하려는 메서드에 대한 각 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36ab4-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="36ab4-116">HTTP 응답 코드는 전송된 요청 수 또는 할당된 실행 시간으로 할당량에 도달했다는 `429` 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="36ab4-117">응답 본문에는 도달한 할당량이 다시 설정될 때까지의 시간이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="36ab4-118">사용 권한</span><span class="sxs-lookup"><span data-stu-id="36ab4-118">Permissions</span></span>

<span data-ttu-id="36ab4-119">인시던트 API에는 각 메서드에 대해 서로 다른 종류의 사용 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="36ab4-120">필요한 사용 권한에 대한 자세한 내용은 해당 방법의 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36ab4-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="36ab4-121">메서드</span><span class="sxs-lookup"><span data-stu-id="36ab4-121">Methods</span></span>

<span data-ttu-id="36ab4-122">메서드</span><span class="sxs-lookup"><span data-stu-id="36ab4-122">Method</span></span> | <span data-ttu-id="36ab4-123">반환 형식</span><span class="sxs-lookup"><span data-stu-id="36ab4-123">Return Type</span></span> | <span data-ttu-id="36ab4-124">설명</span><span class="sxs-lookup"><span data-stu-id="36ab4-124">Description</span></span>
-|-|-
[<span data-ttu-id="36ab4-125">인시던트 열거</span><span class="sxs-lookup"><span data-stu-id="36ab4-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="36ab4-126">[인시던트](api-incident.md) 목록</span><span class="sxs-lookup"><span data-stu-id="36ab4-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="36ab4-127">인시던트 목록을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-127">Get a list of incidents.</span></span>
[<span data-ttu-id="36ab4-128">인시던트 업데이트</span><span class="sxs-lookup"><span data-stu-id="36ab4-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="36ab4-129">인시던트</span><span class="sxs-lookup"><span data-stu-id="36ab4-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="36ab4-130">특정 인시던트 업데이트</span><span class="sxs-lookup"><span data-stu-id="36ab4-130">Update a specific incident.</span></span>
[<span data-ttu-id="36ab4-131">인시던트 발생</span><span class="sxs-lookup"><span data-stu-id="36ab4-131">Get incident</span></span>](api-get-incident.md) | [<span data-ttu-id="36ab4-132">인시던트</span><span class="sxs-lookup"><span data-stu-id="36ab4-132">Incident</span></span>](api-incident.md) | <span data-ttu-id="36ab4-133">인시던트 하나만 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-133">Get a single incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="36ab4-134">요청 본문, 응답 및 예제</span><span class="sxs-lookup"><span data-stu-id="36ab4-134">Request body, response, and examples</span></span>

<span data-ttu-id="36ab4-135">요청을 생성하거나 응답을 구문 분석하는 방법에 대한 자세한 내용과 실용적인 예제는 각 메서드 문서를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-135">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="36ab4-136">공통 속성</span><span class="sxs-lookup"><span data-stu-id="36ab4-136">Common properties</span></span>

<span data-ttu-id="36ab4-137">속성</span><span class="sxs-lookup"><span data-stu-id="36ab4-137">Property</span></span> | <span data-ttu-id="36ab4-138">유형</span><span class="sxs-lookup"><span data-stu-id="36ab4-138">Type</span></span> | <span data-ttu-id="36ab4-139">설명</span><span class="sxs-lookup"><span data-stu-id="36ab4-139">Description</span></span>
-|-|-
<span data-ttu-id="36ab4-140">incidentId</span><span class="sxs-lookup"><span data-stu-id="36ab4-140">incidentId</span></span> | <span data-ttu-id="36ab4-141">long</span><span class="sxs-lookup"><span data-stu-id="36ab4-141">long</span></span> | <span data-ttu-id="36ab4-142">인시던트 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-142">Incident unique ID.</span></span>
<span data-ttu-id="36ab4-143">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="36ab4-143">redirectIncidentId</span></span> | <span data-ttu-id="36ab4-144">nullable long</span><span class="sxs-lookup"><span data-stu-id="36ab4-144">nullable long</span></span> | <span data-ttu-id="36ab4-145">현재 인시던트가 병합된 인시던트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-145">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="36ab4-146">incidentName</span><span class="sxs-lookup"><span data-stu-id="36ab4-146">incidentName</span></span> | <span data-ttu-id="36ab4-147">문자열</span><span class="sxs-lookup"><span data-stu-id="36ab4-147">string</span></span> | <span data-ttu-id="36ab4-148">인시던트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-148">The name of the Incident.</span></span>
<span data-ttu-id="36ab4-149">createdTime</span><span class="sxs-lookup"><span data-stu-id="36ab4-149">createdTime</span></span> | <span data-ttu-id="36ab4-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="36ab4-150">DateTimeOffset</span></span> | <span data-ttu-id="36ab4-151">인시던트가 만들어진 날짜 및 시간(UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-151">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="36ab4-152">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="36ab4-152">lastUpdateTime</span></span> | <span data-ttu-id="36ab4-153">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="36ab4-153">DateTimeOffset</span></span> | <span data-ttu-id="36ab4-154">인시던트가 마지막으로 업데이트된 날짜 및 시간(UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-154">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="36ab4-155">assignedTo</span><span class="sxs-lookup"><span data-stu-id="36ab4-155">assignedTo</span></span> | <span data-ttu-id="36ab4-156">문자열</span><span class="sxs-lookup"><span data-stu-id="36ab4-156">string</span></span> | <span data-ttu-id="36ab4-157">인시던트의 소유자입니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-157">Owner of the Incident.</span></span>
<span data-ttu-id="36ab4-158">심각도</span><span class="sxs-lookup"><span data-stu-id="36ab4-158">severity</span></span> | <span data-ttu-id="36ab4-159">Enum</span><span class="sxs-lookup"><span data-stu-id="36ab4-159">Enum</span></span> | <span data-ttu-id="36ab4-160">인시던트의 심각도입니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-160">Severity of the Incident.</span></span> <span data-ttu-id="36ab4-161">가능한 값은 ```UnSpecified``` , ```Informational``` ```Low``` , , ```Medium``` 및 ```High``` 입니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-161">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="36ab4-162">status</span><span class="sxs-lookup"><span data-stu-id="36ab4-162">status</span></span> | <span data-ttu-id="36ab4-163">Enum</span><span class="sxs-lookup"><span data-stu-id="36ab4-163">Enum</span></span> | <span data-ttu-id="36ab4-164">인시던트의 현재 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-164">Specifies the current status of the incident.</span></span> <span data-ttu-id="36ab4-165">가능한 값은 ```Active``` , ```Resolved``` , 및 ```Redirected``` 입니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-165">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="36ab4-166">classification</span><span class="sxs-lookup"><span data-stu-id="36ab4-166">classification</span></span> | <span data-ttu-id="36ab4-167">Enum</span><span class="sxs-lookup"><span data-stu-id="36ab4-167">Enum</span></span> | <span data-ttu-id="36ab4-168">인시던트 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-168">Specification of the incident.</span></span> <span data-ttu-id="36ab4-169">가능한 값은 ```Unknown``` , ```FalsePositive``` , ```TruePositive``` 입니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-169">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="36ab4-170">determination</span><span class="sxs-lookup"><span data-stu-id="36ab4-170">determination</span></span> | <span data-ttu-id="36ab4-171">Enum</span><span class="sxs-lookup"><span data-stu-id="36ab4-171">Enum</span></span> | <span data-ttu-id="36ab4-172">인시던트 결정</span><span class="sxs-lookup"><span data-stu-id="36ab4-172">Specifies the determination of the incident.</span></span> <span data-ttu-id="36ab4-173">가능한 값은 ```NotAvailable``` , ```Apt``` ```Malware``` , , , , ```SecurityPersonnel``` ```SecurityTesting``` , ```UnwantedSoftware``` ```Other``` 입니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-173">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="36ab4-174">tags</span><span class="sxs-lookup"><span data-stu-id="36ab4-174">tags</span></span> | <span data-ttu-id="36ab4-175">문자열 목록</span><span class="sxs-lookup"><span data-stu-id="36ab4-175">string List</span></span> | <span data-ttu-id="36ab4-176">인시던트 태그 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-176">List of Incident tags.</span></span>
<span data-ttu-id="36ab4-177">설명</span><span class="sxs-lookup"><span data-stu-id="36ab4-177">comments</span></span> | <span data-ttu-id="36ab4-178">인시던트 설명 목록</span><span class="sxs-lookup"><span data-stu-id="36ab4-178">List of incident comments</span></span> | <span data-ttu-id="36ab4-179">Incident Comment 개체에는 주석 문자열, createdBy 문자열 및 createTime 날짜 시간이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-179">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="36ab4-180">alerts</span><span class="sxs-lookup"><span data-stu-id="36ab4-180">alerts</span></span> | <span data-ttu-id="36ab4-181">경고 목록</span><span class="sxs-lookup"><span data-stu-id="36ab4-181">Alert List</span></span> | <span data-ttu-id="36ab4-182">관련 경고 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="36ab4-182">List of related alerts.</span></span> <span data-ttu-id="36ab4-183">목록 [인시던트](api-list-incidents.md) API 설명서에서 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36ab4-183">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="36ab4-184">관련 문서</span><span class="sxs-lookup"><span data-stu-id="36ab4-184">Related articles</span></span>

- [<span data-ttu-id="36ab4-185">Microsoft 365 Defender API 개요</span><span class="sxs-lookup"><span data-stu-id="36ab4-185">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="36ab4-186">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="36ab4-186">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="36ab4-187">인시던트 목록 API</span><span class="sxs-lookup"><span data-stu-id="36ab4-187">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="36ab4-188">인시던트 API 업데이트</span><span class="sxs-lookup"><span data-stu-id="36ab4-188">Update incident API</span></span>](api-update-incidents.md)
