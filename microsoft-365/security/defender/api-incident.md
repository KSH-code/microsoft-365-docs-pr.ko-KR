---
title: Microsoft 365 수비수 인시던트 API 및 인시던트 리소스 유형
description: Microsoft 365 Defender에서 인시던트 리소스 유형의 메서드 및 속성에 대해 알아보기
keywords: 인시던트, 인시던트, API
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
ms.openlocfilehash: 5cc149668e49e21b38b5fb95ae3f40db6c296e1d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572588"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="b5309-104">Microsoft 365 수비수 인시던트 API 및 인시던트 리소스 유형</span><span class="sxs-lookup"><span data-stu-id="b5309-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b5309-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b5309-105">**Applies to:**</span></span>

- <span data-ttu-id="b5309-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b5309-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5309-107">일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b5309-108">Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="b5309-109">[인시던트는](incidents-overview.md) 공격을 설명하는 데 도움이 되는 관련 경고 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="b5309-110">조직의 여러 엔터티의 이벤트는 Microsoft 365 Defender에 의해 자동으로 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="b5309-111">인시던트 API를 사용하여 조직의 인시던트 및 관련 경고에 프로그래밍하여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="b5309-112">할당량 및 리소스 할당</span><span class="sxs-lookup"><span data-stu-id="b5309-112">Quotas and resource allocation</span></span>

<span data-ttu-id="b5309-113">분당 최대 50건의 통화 또는 시간당 1,500건의 통화를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="b5309-114">각 메서드에는 자체 할당량도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-114">Each method also has its own quotas.</span></span> <span data-ttu-id="b5309-115">메서드별 할당량에 대한 자세한 내용은 사용하려는 메서드에 대한 각 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b5309-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="b5309-116">`429`HTTP 응답 코드는 전송된 요청 수 또는 할당된 실행 시간으로 할당량에 도달했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="b5309-117">응답 본문에는 도달한 할당량이 재설정될 때까지의 시간이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="b5309-118">권한</span><span class="sxs-lookup"><span data-stu-id="b5309-118">Permissions</span></span>

<span data-ttu-id="b5309-119">인시던트 API에는 각 메서드에 대해 서로 다른 종류의 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="b5309-120">필요한 권한에 대한 자세한 내용은 각 메서드의 문서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b5309-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="b5309-121">메서드</span><span class="sxs-lookup"><span data-stu-id="b5309-121">Methods</span></span>

<span data-ttu-id="b5309-122">메서드</span><span class="sxs-lookup"><span data-stu-id="b5309-122">Method</span></span> | <span data-ttu-id="b5309-123">리턴 타입</span><span class="sxs-lookup"><span data-stu-id="b5309-123">Return Type</span></span> | <span data-ttu-id="b5309-124">설명</span><span class="sxs-lookup"><span data-stu-id="b5309-124">Description</span></span>
-|-|-
[<span data-ttu-id="b5309-125">인시던트 열거</span><span class="sxs-lookup"><span data-stu-id="b5309-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="b5309-126">[인시던트](api-incident.md) 목록</span><span class="sxs-lookup"><span data-stu-id="b5309-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="b5309-127">인시던트 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-127">Get a list of incidents.</span></span>
[<span data-ttu-id="b5309-128">인시던트 업데이트</span><span class="sxs-lookup"><span data-stu-id="b5309-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="b5309-129">인시던트</span><span class="sxs-lookup"><span data-stu-id="b5309-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="b5309-130">특정 인시던트를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="b5309-131">본문, 응답 및 예제 요청</span><span class="sxs-lookup"><span data-stu-id="b5309-131">Request body, response, and examples</span></span>

<span data-ttu-id="b5309-132">요청을 구성하거나 응답을 구문 분석하는 방법과 실제 예제에 대한 자세한 내용은 각 메서드 문서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b5309-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="b5309-133">공통 속성</span><span class="sxs-lookup"><span data-stu-id="b5309-133">Common properties</span></span>

<span data-ttu-id="b5309-134">속성</span><span class="sxs-lookup"><span data-stu-id="b5309-134">Property</span></span> | <span data-ttu-id="b5309-135">유형</span><span class="sxs-lookup"><span data-stu-id="b5309-135">Type</span></span> | <span data-ttu-id="b5309-136">설명</span><span class="sxs-lookup"><span data-stu-id="b5309-136">Description</span></span>
-|-|-
<span data-ttu-id="b5309-137">인시던트Id</span><span class="sxs-lookup"><span data-stu-id="b5309-137">incidentId</span></span> | <span data-ttu-id="b5309-138">long</span><span class="sxs-lookup"><span data-stu-id="b5309-138">long</span></span> | <span data-ttu-id="b5309-139">인시던트 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-139">Incident unique ID.</span></span>
<span data-ttu-id="b5309-140">리디렉션우연히이드</span><span class="sxs-lookup"><span data-stu-id="b5309-140">redirectIncidentId</span></span> | <span data-ttu-id="b5309-141">무효화 할 수 있는 긴</span><span class="sxs-lookup"><span data-stu-id="b5309-141">nullable long</span></span> | <span data-ttu-id="b5309-142">현재 인시던트인시던트 ID가 병합되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="b5309-143">인시던트 이름</span><span class="sxs-lookup"><span data-stu-id="b5309-143">incidentName</span></span> | <span data-ttu-id="b5309-144">문자열</span><span class="sxs-lookup"><span data-stu-id="b5309-144">string</span></span> | <span data-ttu-id="b5309-145">인시던트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-145">The name of the Incident.</span></span>
<span data-ttu-id="b5309-146">만든 시간</span><span class="sxs-lookup"><span data-stu-id="b5309-146">createdTime</span></span> | <span data-ttu-id="b5309-147">날짜 시간 오프셋</span><span class="sxs-lookup"><span data-stu-id="b5309-147">DateTimeOffset</span></span> | <span data-ttu-id="b5309-148">인시던트(UTC)에서 인시던트가 생성된 날짜와 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="b5309-149">마지막 업데이트 시간</span><span class="sxs-lookup"><span data-stu-id="b5309-149">lastUpdateTime</span></span> | <span data-ttu-id="b5309-150">날짜 시간 오프셋</span><span class="sxs-lookup"><span data-stu-id="b5309-150">DateTimeOffset</span></span> | <span data-ttu-id="b5309-151">인시던트(UTC)에서 인시던트가 마지막으로 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="b5309-152">할당To</span><span class="sxs-lookup"><span data-stu-id="b5309-152">assignedTo</span></span> | <span data-ttu-id="b5309-153">문자열</span><span class="sxs-lookup"><span data-stu-id="b5309-153">string</span></span> | <span data-ttu-id="b5309-154">사건의 소유자.</span><span class="sxs-lookup"><span data-stu-id="b5309-154">Owner of the Incident.</span></span>
<span data-ttu-id="b5309-155">심각도</span><span class="sxs-lookup"><span data-stu-id="b5309-155">severity</span></span> | <span data-ttu-id="b5309-156">이넘 (주)</span><span class="sxs-lookup"><span data-stu-id="b5309-156">Enum</span></span> | <span data-ttu-id="b5309-157">사건의 심각도.</span><span class="sxs-lookup"><span data-stu-id="b5309-157">Severity of the Incident.</span></span> <span data-ttu-id="b5309-158">가능한 값은 다음과 ```UnSpecified``` ```Informational``` ```Low``` ```Medium``` ```High``` 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="b5309-159">상태</span><span class="sxs-lookup"><span data-stu-id="b5309-159">status</span></span> | <span data-ttu-id="b5309-160">이넘 (주)</span><span class="sxs-lookup"><span data-stu-id="b5309-160">Enum</span></span> | <span data-ttu-id="b5309-161">인시던트의 현재 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="b5309-162">가능한 값은 다음과 ```Active``` ```Resolved``` ```Redirected``` 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="b5309-163">분류</span><span class="sxs-lookup"><span data-stu-id="b5309-163">classification</span></span> | <span data-ttu-id="b5309-164">이넘 (주)</span><span class="sxs-lookup"><span data-stu-id="b5309-164">Enum</span></span> | <span data-ttu-id="b5309-165">인시던트 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-165">Specification of the incident.</span></span> <span data-ttu-id="b5309-166">가능한 값은 다음과 ```Unknown``` ```FalsePositive``` ```TruePositive``` 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="b5309-167">결심</span><span class="sxs-lookup"><span data-stu-id="b5309-167">determination</span></span> | <span data-ttu-id="b5309-168">이넘 (주)</span><span class="sxs-lookup"><span data-stu-id="b5309-168">Enum</span></span> | <span data-ttu-id="b5309-169">인시던트 의 결정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="b5309-170">가능한 값은 다음과 같습니다 : ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` . ```Other```</span><span class="sxs-lookup"><span data-stu-id="b5309-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="b5309-171">태그</span><span class="sxs-lookup"><span data-stu-id="b5309-171">tags</span></span> | <span data-ttu-id="b5309-172">문자열 목록</span><span class="sxs-lookup"><span data-stu-id="b5309-172">string List</span></span> | <span data-ttu-id="b5309-173">인시던트 태그 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-173">List of Incident tags.</span></span>
<span data-ttu-id="b5309-174">코멘트</span><span class="sxs-lookup"><span data-stu-id="b5309-174">comments</span></span> | <span data-ttu-id="b5309-175">인시던트 댓글 목록</span><span class="sxs-lookup"><span data-stu-id="b5309-175">List of incident comments</span></span> | <span data-ttu-id="b5309-176">인시던트 주석 개체에는 주석 문자열, 생성됨 문자열 및 createTime 날짜 시간이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-176">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="b5309-177">경고</span><span class="sxs-lookup"><span data-stu-id="b5309-177">alerts</span></span> | <span data-ttu-id="b5309-178">경고 목록</span><span class="sxs-lookup"><span data-stu-id="b5309-178">Alert List</span></span> | <span data-ttu-id="b5309-179">관련 경고 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="b5309-179">List of related alerts.</span></span> <span data-ttu-id="b5309-180">[인시던트 목록](api-list-incidents.md) API 설명서에서 예제를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b5309-180">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="b5309-181">관련 문서</span><span class="sxs-lookup"><span data-stu-id="b5309-181">Related articles</span></span>

- [<span data-ttu-id="b5309-182">Microsoft 365 수비수 API 개요</span><span class="sxs-lookup"><span data-stu-id="b5309-182">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="b5309-183">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="b5309-183">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="b5309-184">인시던트 API 목록</span><span class="sxs-lookup"><span data-stu-id="b5309-184">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="b5309-185">인시던트 API 업데이트</span><span class="sxs-lookup"><span data-stu-id="b5309-185">Update incident API</span></span>](api-update-incidents.md)
