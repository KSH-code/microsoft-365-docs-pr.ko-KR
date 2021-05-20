---
title: Defender의 인시던트 Microsoft 365 API 나열
description: Defender에서 인시던트 API를 나열하는 Microsoft 365 방법
keywords: 목록, 인시던트, 인시던트, api
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
ms.openlocfilehash: 6f0c92371e7e9b7a3348f90df788ee8c3a46374b
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572156"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="6e271-104">Defender의 인시던트 Microsoft 365 API 나열</span><span class="sxs-lookup"><span data-stu-id="6e271-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6e271-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6e271-105">**Applies to:**</span></span>

- <span data-ttu-id="6e271-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6e271-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e271-107">일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6e271-108">Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="6e271-109">API 설명</span><span class="sxs-lookup"><span data-stu-id="6e271-109">API description</span></span>

<span data-ttu-id="6e271-110">인시던트 목록 API를 사용하면 인시던트들을 정렬하여 정보를 토대한 사이버 보안 대응을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="6e271-111">네트워크에서 플래그가 지정된 인시던트 모음을 환경 보존 정책에서 지정한 시간 범위 내에 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="6e271-112">가장 최근 인시던트가 목록 맨 위에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="6e271-113">각 인시던트에는 관련 경고 및 관련 엔터티의 배열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="6e271-114">API는 다음 **OData 연산자를** 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="6e271-115">`$filter` , `lastUpdateTime` `createdTime` , `status` 및 `assignedTo` 속성</span><span class="sxs-lookup"><span data-stu-id="6e271-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="6e271-116">`$top`의 **최대값은 100입니다.**</span><span class="sxs-lookup"><span data-stu-id="6e271-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="6e271-117">제한 사항</span><span class="sxs-lookup"><span data-stu-id="6e271-117">Limitations</span></span>

1. <span data-ttu-id="6e271-118">최대 페이지 크기는 **인시던트 100개입니다.**</span><span class="sxs-lookup"><span data-stu-id="6e271-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="6e271-119">최대 요청 속도는 **분당 50통,** **시간당 1500통입니다.**</span><span class="sxs-lookup"><span data-stu-id="6e271-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="6e271-120">권한</span><span class="sxs-lookup"><span data-stu-id="6e271-120">Permissions</span></span>

<span data-ttu-id="6e271-121">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6e271-122">권한을 선택하는 방법을 포함하여 자세한 내용은 Access Microsoft 365 [Defender API를 참조합니다.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="6e271-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="6e271-123">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="6e271-123">Permission type</span></span> | <span data-ttu-id="6e271-124">사용 권한</span><span class="sxs-lookup"><span data-stu-id="6e271-124">Permission</span></span> | <span data-ttu-id="6e271-125">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="6e271-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="6e271-126">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="6e271-126">Application</span></span> | <span data-ttu-id="6e271-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="6e271-127">Incident.Read.All</span></span> | <span data-ttu-id="6e271-128">모든 인시던트 읽기</span><span class="sxs-lookup"><span data-stu-id="6e271-128">Read all incidents</span></span>
<span data-ttu-id="6e271-129">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="6e271-129">Application</span></span> | <span data-ttu-id="6e271-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="6e271-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="6e271-131">모든 인시던트 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="6e271-131">Read and write all incidents</span></span>
<span data-ttu-id="6e271-132">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="6e271-132">Delegated (work or school account)</span></span> | <span data-ttu-id="6e271-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="6e271-133">Incident.Read</span></span> | <span data-ttu-id="6e271-134">인시던트 읽기</span><span class="sxs-lookup"><span data-stu-id="6e271-134">Read incidents</span></span>
<span data-ttu-id="6e271-135">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="6e271-135">Delegated (work or school account)</span></span> | <span data-ttu-id="6e271-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="6e271-136">Incident.ReadWrite</span></span> | <span data-ttu-id="6e271-137">인시던트 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="6e271-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="6e271-138">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="6e271-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="6e271-139">사용자에게 포털의 인시던트에 대한 보기 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="6e271-140">응답에는 사용자가 노출되는 인시던트만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="6e271-141">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="6e271-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="6e271-142">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="6e271-142">Request headers</span></span>

<span data-ttu-id="6e271-143">이름</span><span class="sxs-lookup"><span data-stu-id="6e271-143">Name</span></span> | <span data-ttu-id="6e271-144">유형</span><span class="sxs-lookup"><span data-stu-id="6e271-144">Type</span></span> | <span data-ttu-id="6e271-145">설명</span><span class="sxs-lookup"><span data-stu-id="6e271-145">Description</span></span>
-|-|-
<span data-ttu-id="6e271-146">권한 부여</span><span class="sxs-lookup"><span data-stu-id="6e271-146">Authorization</span></span> | <span data-ttu-id="6e271-147">문자열</span><span class="sxs-lookup"><span data-stu-id="6e271-147">String</span></span> | <span data-ttu-id="6e271-148">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="6e271-148">Bearer {token}.</span></span> <span data-ttu-id="6e271-149">**필수**</span><span class="sxs-lookup"><span data-stu-id="6e271-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="6e271-150">요청 본문</span><span class="sxs-lookup"><span data-stu-id="6e271-150">Request body</span></span>

<span data-ttu-id="6e271-151">없음</span><span class="sxs-lookup"><span data-stu-id="6e271-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="6e271-152">응답</span><span class="sxs-lookup"><span data-stu-id="6e271-152">Response</span></span>

<span data-ttu-id="6e271-153">성공하면 이 메서드는 및 응답 본문의 인시던트 `200 OK` 목록을 반환합니다. [](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="6e271-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="6e271-154">Schema 매핑</span><span class="sxs-lookup"><span data-stu-id="6e271-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="6e271-155">인시던트 메타데이터</span><span class="sxs-lookup"><span data-stu-id="6e271-155">Incident metadata</span></span>

<span data-ttu-id="6e271-156">필드 이름</span><span class="sxs-lookup"><span data-stu-id="6e271-156">Field name</span></span> | <span data-ttu-id="6e271-157">설명</span><span class="sxs-lookup"><span data-stu-id="6e271-157">Description</span></span> | <span data-ttu-id="6e271-158">예제 값</span><span class="sxs-lookup"><span data-stu-id="6e271-158">Example value</span></span>
-|-|-
<span data-ttu-id="6e271-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="6e271-159">incidentId</span></span> | <span data-ttu-id="6e271-160">인시던트 나타내는 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="6e271-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="6e271-161">924565</span><span class="sxs-lookup"><span data-stu-id="6e271-161">924565</span></span>
<span data-ttu-id="6e271-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="6e271-162">redirectIncidentId</span></span> | <span data-ttu-id="6e271-163">인시던트가 인시던트 처리 논리의 일부로 다른 인시던트와 함께 그룹화되는 경우만 채워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="6e271-164">924569</span><span class="sxs-lookup"><span data-stu-id="6e271-164">924569</span></span>
<span data-ttu-id="6e271-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="6e271-165">incidentName</span></span> | <span data-ttu-id="6e271-166">모든 인시던트에 사용할 수 있는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-166">String value available for every incident.</span></span> | <span data-ttu-id="6e271-167">랜섬웨어 활동</span><span class="sxs-lookup"><span data-stu-id="6e271-167">Ransomware activity</span></span>
<span data-ttu-id="6e271-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="6e271-168">createdTime</span></span> | <span data-ttu-id="6e271-169">인시던트가 처음 만들어진 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-169">Time when incident was first created.</span></span> | <span data-ttu-id="6e271-170">2020-09-06T14:46:57.073333Z</span><span class="sxs-lookup"><span data-stu-id="6e271-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="6e271-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="6e271-171">lastUpdateTime</span></span> | <span data-ttu-id="6e271-172">인시던트가 백엔드에서 마지막으로 업데이트된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="6e271-173">이 필드는 인시던트가 검색된 시간 범위에 대한 요청 매개 변수를 설정할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="6e271-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="6e271-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="6e271-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="6e271-175">assignedTo</span></span> | <span data-ttu-id="6e271-176">인시던트의 소유자 또는 소유자가 할당되지 않은 경우 *null입니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="6e271-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6e271-177">secop2@contoso.com</span></span>
<span data-ttu-id="6e271-178">classification</span><span class="sxs-lookup"><span data-stu-id="6e271-178">classification</span></span> | <span data-ttu-id="6e271-179">인시던트에 대한 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-179">The specification for the incident.</span></span> <span data-ttu-id="6e271-180">속성 값은 *알* 수 없음, *FalsePositive,* *TruePositive입니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="6e271-181">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="6e271-181">Unknown</span></span>
<span data-ttu-id="6e271-182">determination</span><span class="sxs-lookup"><span data-stu-id="6e271-182">determination</span></span> | <span data-ttu-id="6e271-183">인시던트 결정</span><span class="sxs-lookup"><span data-stu-id="6e271-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="6e271-184">속성 값은 *NotAvailable*, *Apt,* *Malware,* *SecurityPersonnel,* *SecurityTesting,* *UnwantedSoftware*, *Other입니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="6e271-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="6e271-185">NotAvailable</span></span>
<span data-ttu-id="6e271-186">status</span><span class="sxs-lookup"><span data-stu-id="6e271-186">status</span></span> | <span data-ttu-id="6e271-187">인시던트(활성 또는 *해결된* 인시던트)를 *분류합니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="6e271-188">인시던트에 대한 대응을 구성하고 관리하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="6e271-189">활성</span><span class="sxs-lookup"><span data-stu-id="6e271-189">Active</span></span>
<span data-ttu-id="6e271-190">심각도</span><span class="sxs-lookup"><span data-stu-id="6e271-190">severity</span></span> | <span data-ttu-id="6e271-191">자산에 미칠 수 있는 영향을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="6e271-192">심각도가 높을수록 영향이 커집니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="6e271-193">일반적으로 심각도 항목이 높을수록 가장 즉각적인 주의가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="6e271-194">정보, 낮음, \*중간 및 *높음* 값 중 하나</span><span class="sxs-lookup"><span data-stu-id="6e271-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="6e271-195">보통</span><span class="sxs-lookup"><span data-stu-id="6e271-195">Medium</span></span>
<span data-ttu-id="6e271-196">tags</span><span class="sxs-lookup"><span data-stu-id="6e271-196">tags</span></span> | <span data-ttu-id="6e271-197">인시던트와 연결된 사용자 지정 태그의 배열입니다. 예를 들어 공통 특성이 있는 인시던트 그룹에 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="6e271-198">설명</span><span class="sxs-lookup"><span data-stu-id="6e271-198">comments</span></span> | <span data-ttu-id="6e271-199">인시던트 관리 시 셀프에서 만든 설명의 배열입니다(예: 분류 선택에 대한 추가 정보).</span><span class="sxs-lookup"><span data-stu-id="6e271-199">Array of comments created by secops when managing the incident, for example additional information about the classification selection.</span></span> | \[\]
<span data-ttu-id="6e271-200">alerts</span><span class="sxs-lookup"><span data-stu-id="6e271-200">alerts</span></span> | <span data-ttu-id="6e271-201">인시던트와 관련된 모든 경고와 심각도, 경고에 관련된 엔터티, 경고 원본 등의 기타 정보를 포함하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-201">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="6e271-202">\[\] (아래의 경고 필드에 대한 세부 정보 참조)</span><span class="sxs-lookup"><span data-stu-id="6e271-202">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="6e271-203">경고 메타데이터</span><span class="sxs-lookup"><span data-stu-id="6e271-203">Alerts metadata</span></span>

<span data-ttu-id="6e271-204">필드 이름</span><span class="sxs-lookup"><span data-stu-id="6e271-204">Field name</span></span> | <span data-ttu-id="6e271-205">설명</span><span class="sxs-lookup"><span data-stu-id="6e271-205">Description</span></span> | <span data-ttu-id="6e271-206">예제 값</span><span class="sxs-lookup"><span data-stu-id="6e271-206">Example value</span></span>
-|-|-
<span data-ttu-id="6e271-207">alertId</span><span class="sxs-lookup"><span data-stu-id="6e271-207">alertId</span></span> | <span data-ttu-id="6e271-208">경고를 나타내는 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="6e271-208">Unique identifier to represent the alert</span></span> | <span data-ttu-id="6e271-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="6e271-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="6e271-210">incidentId</span><span class="sxs-lookup"><span data-stu-id="6e271-210">incidentId</span></span> | <span data-ttu-id="6e271-211">이 경고와 연관된 인시던트 표시를 나타내는 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-211">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="6e271-212">924565</span><span class="sxs-lookup"><span data-stu-id="6e271-212">924565</span></span>
<span data-ttu-id="6e271-213">serviceSource</span><span class="sxs-lookup"><span data-stu-id="6e271-213">serviceSource</span></span> | <span data-ttu-id="6e271-214">경고가 시작된 서비스(예: Endpoint용 Microsoft Defender, Microsoft Cloud App Security, ID용 Microsoft Defender 또는 Microsoft Defender for Office 365.</span><span class="sxs-lookup"><span data-stu-id="6e271-214">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="6e271-215">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="6e271-215">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="6e271-216">creationTime</span><span class="sxs-lookup"><span data-stu-id="6e271-216">creationTime</span></span> | <span data-ttu-id="6e271-217">알림을 처음 만든 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-217">Time when alert was first created.</span></span> | <span data-ttu-id="6e271-218">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="6e271-218">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="6e271-219">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="6e271-219">lastUpdatedTime</span></span> | <span data-ttu-id="6e271-220">백엔드에서 경고가 마지막으로 업데이트된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-220">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="6e271-221">2020-09-06T14:46:57.243333Z</span><span class="sxs-lookup"><span data-stu-id="6e271-221">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="6e271-222">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="6e271-222">resolvedTime</span></span> | <span data-ttu-id="6e271-223">경고가 해결된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-223">Time when alert was resolved.</span></span> | <span data-ttu-id="6e271-224">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="6e271-224">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="6e271-225">firstActivity</span><span class="sxs-lookup"><span data-stu-id="6e271-225">firstActivity</span></span> | <span data-ttu-id="6e271-226">활동이 백엔드에서 업데이트된 것으로 처음 보고된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-226">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="6e271-227">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="6e271-227">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="6e271-228">title</span><span class="sxs-lookup"><span data-stu-id="6e271-228">title</span></span> | <span data-ttu-id="6e271-229">각 경고에 사용할 수 있는 간략한 식별 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-229">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="6e271-230">랜섬웨어 활동</span><span class="sxs-lookup"><span data-stu-id="6e271-230">Ransomware activity</span></span>
<span data-ttu-id="6e271-231">설명</span><span class="sxs-lookup"><span data-stu-id="6e271-231">description</span></span> | <span data-ttu-id="6e271-232">각 경고를 설명하는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-232">String value describing each alert.</span></span> | <span data-ttu-id="6e271-233">사용자 Test User2(testUser2@contoso.com)가 99개 파일을 조작하고 여러 확장명은 희미한 *확장명인 herunterladen으로 끝났습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-233">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="6e271-234">이는 비정상적인 파일 조작 수로 잠재적인 랜섬웨어 공격을 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-234">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="6e271-235">category</span><span class="sxs-lookup"><span data-stu-id="6e271-235">category</span></span> | <span data-ttu-id="6e271-236">킬체인을 따라 공격이 얼마나 진행된 지의 시각적 및 숫자 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-236">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="6e271-237">[MITRE ATT CK&프레임워크에 ™ 정렬됩니다.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="6e271-237">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="6e271-238">영향</span><span class="sxs-lookup"><span data-stu-id="6e271-238">Impact</span></span>
<span data-ttu-id="6e271-239">status</span><span class="sxs-lookup"><span data-stu-id="6e271-239">status</span></span> | <span data-ttu-id="6e271-240">경고를 새로, 활성 또는 해결된 경고로 *분류합니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-240">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="6e271-241">경고에 대한 응답을 구성하고 관리하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-241">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="6e271-242">신규</span><span class="sxs-lookup"><span data-stu-id="6e271-242">New</span></span>
<span data-ttu-id="6e271-243">심각도</span><span class="sxs-lookup"><span data-stu-id="6e271-243">severity</span></span> | <span data-ttu-id="6e271-244">자산에 미칠 수 있는 영향을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-244">Indicates the possible impact on assets.</span></span> <span data-ttu-id="6e271-245">심각도가 높을수록 영향이 커집니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-245">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="6e271-246">일반적으로 심각도 항목이 높을수록 가장 즉각적인 주의가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-246">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="6e271-247">정보, 낮음, \*중간 및 *높음* 값 중 하나</span><span class="sxs-lookup"><span data-stu-id="6e271-247">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="6e271-248">보통</span><span class="sxs-lookup"><span data-stu-id="6e271-248">Medium</span></span>
<span data-ttu-id="6e271-249">investigationId</span><span class="sxs-lookup"><span data-stu-id="6e271-249">investigationId</span></span> | <span data-ttu-id="6e271-250">이 경고에 의해 트리거된 자동화된 조사 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-250">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="6e271-251">1234</span><span class="sxs-lookup"><span data-stu-id="6e271-251">1234</span></span>
<span data-ttu-id="6e271-252">investigationState</span><span class="sxs-lookup"><span data-stu-id="6e271-252">investigationState</span></span> | <span data-ttu-id="6e271-253">조사의 현재 상태에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-253">Information on the investigation's current status.</span></span> <span data-ttu-id="6e271-254">다음 값 중 하나: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span><span class="sxs-lookup"><span data-stu-id="6e271-254">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="6e271-255">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="6e271-255">UnsupportedAlertType</span></span>
<span data-ttu-id="6e271-256">classification</span><span class="sxs-lookup"><span data-stu-id="6e271-256">classification</span></span> | <span data-ttu-id="6e271-257">인시던트에 대한 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-257">The specification for the incident.</span></span> <span data-ttu-id="6e271-258">속성 값은 *알* 수 없음, *FalsePositive,* *TruePositive* 또는 *null입니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-258">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="6e271-259">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="6e271-259">Unknown</span></span>
<span data-ttu-id="6e271-260">determination</span><span class="sxs-lookup"><span data-stu-id="6e271-260">determination</span></span> | <span data-ttu-id="6e271-261">인시던트 결정</span><span class="sxs-lookup"><span data-stu-id="6e271-261">Specifies the determination of the incident.</span></span> <span data-ttu-id="6e271-262">속성 값은 *NotAvailable*, *Apt,* *Malware,* *SecurityPersonnel*, *SecurityTesting,* *UnwantedSoftware*, *Other* 또는  *null입니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-262">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="6e271-263">Apt</span><span class="sxs-lookup"><span data-stu-id="6e271-263">Apt</span></span>
<span data-ttu-id="6e271-264">assignedTo</span><span class="sxs-lookup"><span data-stu-id="6e271-264">assignedTo</span></span> | <span data-ttu-id="6e271-265">인시던트의 소유자 또는 소유자가 할당되지 않은 경우 *null입니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-265">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="6e271-266">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6e271-266">secop2@contoso.com</span></span>
<span data-ttu-id="6e271-267">actorName</span><span class="sxs-lookup"><span data-stu-id="6e271-267">actorName</span></span> | <span data-ttu-id="6e271-268">이 경고와 연결된 활동 그룹(있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-268">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="6e271-269">BORON</span><span class="sxs-lookup"><span data-stu-id="6e271-269">BORON</span></span>
<span data-ttu-id="6e271-270">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="6e271-270">threatFamilyName</span></span> | <span data-ttu-id="6e271-271">이 경고와 연결된 위협 패밀리입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-271">Threat family associated with this alert.</span></span> | <span data-ttu-id="6e271-272">null</span><span class="sxs-lookup"><span data-stu-id="6e271-272">null</span></span>
<span data-ttu-id="6e271-273">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="6e271-273">mitreTechniques</span></span> | <span data-ttu-id="6e271-274">[MITRE ATT 및 CK 2013](https://attack.mitre.org/)프레임워크에&공격 ™ 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-274">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="6e271-275">장치</span><span class="sxs-lookup"><span data-stu-id="6e271-275">devices</span></span> | <span data-ttu-id="6e271-276">인시던트와 관련된 경고가 전송된 모든 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-276">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="6e271-277">\[\] (아래 엔터티 필드에 대한 세부 정보 참조)</span><span class="sxs-lookup"><span data-stu-id="6e271-277">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="6e271-278">장치 형식</span><span class="sxs-lookup"><span data-stu-id="6e271-278">Device format</span></span>

<span data-ttu-id="6e271-279">필드 이름</span><span class="sxs-lookup"><span data-stu-id="6e271-279">Field name</span></span> | <span data-ttu-id="6e271-280">설명</span><span class="sxs-lookup"><span data-stu-id="6e271-280">Description</span></span> | <span data-ttu-id="6e271-281">예제 값</span><span class="sxs-lookup"><span data-stu-id="6e271-281">Example value</span></span>
-|-|-
<span data-ttu-id="6e271-282">DeviceId</span><span class="sxs-lookup"><span data-stu-id="6e271-282">DeviceId</span></span> | <span data-ttu-id="6e271-283">끝점용 Microsoft Defender에 지정된 장치 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-283">The device ID as designated in Microsoft Defender for Endpoint.</span></span> | <span data-ttu-id="6e271-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="6e271-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="6e271-285">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="6e271-285">aadDeviceId</span></span> |  <span data-ttu-id="6e271-286">에 지정된 장치 ID [Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="6e271-286">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="6e271-287">도메인에 가입된 디바이스에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-287">Only available for domain-joined devices.</span></span> | <span data-ttu-id="6e271-288">null</span><span class="sxs-lookup"><span data-stu-id="6e271-288">null</span></span>
<span data-ttu-id="6e271-289">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="6e271-289">deviceDnsName</span></span> | <span data-ttu-id="6e271-290">장치의 정식 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-290">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="6e271-291">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6e271-291">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="6e271-292">osPlatform</span><span class="sxs-lookup"><span data-stu-id="6e271-292">osPlatform</span></span> | <span data-ttu-id="6e271-293">디바이스가 실행 중인 OS 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-293">The OS platform the device is running.</span></span>| <span data-ttu-id="6e271-294">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="6e271-294">WindowsServer2016</span></span>
<span data-ttu-id="6e271-295">osBuild</span><span class="sxs-lookup"><span data-stu-id="6e271-295">osBuild</span></span> | <span data-ttu-id="6e271-296">디바이스가 실행 중인 OS의 빌드 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-296">The build version for the OS the device is running.</span></span> | <span data-ttu-id="6e271-297">14393</span><span class="sxs-lookup"><span data-stu-id="6e271-297">14393</span></span>
<span data-ttu-id="6e271-298">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="6e271-298">rbacGroupName</span></span> | <span data-ttu-id="6e271-299">장치와 [연결된](/azure/role-based-access-control/overview) RBAC(역할 기반 액세스 제어) 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-299">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="6e271-300">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="6e271-300">WDATP-Ring0</span></span>
<span data-ttu-id="6e271-301">firstSeen</span><span class="sxs-lookup"><span data-stu-id="6e271-301">firstSeen</span></span> | <span data-ttu-id="6e271-302">장치를 처음 본 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-302">Time when device was first seen.</span></span> | <span data-ttu-id="6e271-303">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="6e271-303">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="6e271-304">healthStatus</span><span class="sxs-lookup"><span data-stu-id="6e271-304">healthStatus</span></span> | <span data-ttu-id="6e271-305">장치의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-305">The health state of the device.</span></span> | <span data-ttu-id="6e271-306">활성</span><span class="sxs-lookup"><span data-stu-id="6e271-306">Active</span></span>
<span data-ttu-id="6e271-307">riskScore</span><span class="sxs-lookup"><span data-stu-id="6e271-307">riskScore</span></span> | <span data-ttu-id="6e271-308">장치에 대한 위험 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-308">The risk score for the  device.</span></span> | <span data-ttu-id="6e271-309">높음</span><span class="sxs-lookup"><span data-stu-id="6e271-309">High</span></span>
<span data-ttu-id="6e271-310">엔터티</span><span class="sxs-lookup"><span data-stu-id="6e271-310">entities</span></span> | <span data-ttu-id="6e271-311">특정 경고의 일부로 식별되거나 이와 관련된 모든 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-311">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="6e271-312">\[\] (아래 엔터티 필드에 대한 세부 정보 참조)</span><span class="sxs-lookup"><span data-stu-id="6e271-312">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="6e271-313">엔터티 형식</span><span class="sxs-lookup"><span data-stu-id="6e271-313">Entity Format</span></span>

<span data-ttu-id="6e271-314">필드 이름</span><span class="sxs-lookup"><span data-stu-id="6e271-314">Field name</span></span> | <span data-ttu-id="6e271-315">설명</span><span class="sxs-lookup"><span data-stu-id="6e271-315">Description</span></span> | <span data-ttu-id="6e271-316">예제 값</span><span class="sxs-lookup"><span data-stu-id="6e271-316">Example value</span></span>
-|-|-
<span data-ttu-id="6e271-317">entityType</span><span class="sxs-lookup"><span data-stu-id="6e271-317">entityType</span></span> | <span data-ttu-id="6e271-318">특정 경고의 일부로 식별되거나 이와 관련된 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-318">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="6e271-319">속성 값은 *사용자,* *Ip,* *Url,* *파일,* *프로세스,* *MailBox,* *MailMessage,* *MailCluster,* *레지스트리입니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-319">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="6e271-320">사용자</span><span class="sxs-lookup"><span data-stu-id="6e271-320">User</span></span>
<span data-ttu-id="6e271-321">sha1</span><span class="sxs-lookup"><span data-stu-id="6e271-321">sha1</span></span> | <span data-ttu-id="6e271-322">entityType이 File인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-322">Available if entityType is *File*.</span></span><br><span data-ttu-id="6e271-323">파일 또는 프로세스와 연결된 경고에 대한 파일 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-323">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="6e271-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="6e271-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="6e271-325">sha256</span><span class="sxs-lookup"><span data-stu-id="6e271-325">sha256</span></span> | <span data-ttu-id="6e271-326">entityType이 File인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-326">Available if entityType is *File*.</span></span><br><span data-ttu-id="6e271-327">파일 또는 프로세스와 연결된 경고에 대한 파일 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-327">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="6e271-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="6e271-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="6e271-329">fileName</span><span class="sxs-lookup"><span data-stu-id="6e271-329">fileName</span></span> | <span data-ttu-id="6e271-330">entityType이 File인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-330">Available if entityType is *File*.</span></span><br><span data-ttu-id="6e271-331">파일 또는 프로세스와 연결된 경고의 파일 이름</span><span class="sxs-lookup"><span data-stu-id="6e271-331">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="6e271-332">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="6e271-332">Detector.UnitTests.dll</span></span>
<span data-ttu-id="6e271-333">filePath</span><span class="sxs-lookup"><span data-stu-id="6e271-333">filePath</span></span> | <span data-ttu-id="6e271-334">entityType이 File인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-334">Available if entityType is *File*.</span></span><br><span data-ttu-id="6e271-335">파일 또는 프로세스와 연결된 경고의 파일 경로</span><span class="sxs-lookup"><span data-stu-id="6e271-335">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="6e271-336">C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="6e271-336">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="6e271-337">processId</span><span class="sxs-lookup"><span data-stu-id="6e271-337">processId</span></span> | <span data-ttu-id="6e271-338">entityType이 Process인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-338">Available if entityType is *Process*.</span></span> | <span data-ttu-id="6e271-339">24348</span><span class="sxs-lookup"><span data-stu-id="6e271-339">24348</span></span>
<span data-ttu-id="6e271-340">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="6e271-340">processCommandLine</span></span> | <span data-ttu-id="6e271-341">entityType이 Process인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-341">Available if entityType is *Process*.</span></span> | <span data-ttu-id="6e271-342">"파일을 다운로드할 \_ 준비가1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="6e271-342">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="6e271-343">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="6e271-343">processCreationTime</span></span> | <span data-ttu-id="6e271-344">entityType이 Process인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-344">Available if entityType is *Process*.</span></span> | <span data-ttu-id="6e271-345">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="6e271-345">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="6e271-346">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="6e271-346">parentProcessId</span></span> | <span data-ttu-id="6e271-347">entityType이 Process인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-347">Available if entityType is *Process*.</span></span> | <span data-ttu-id="6e271-348">16840</span><span class="sxs-lookup"><span data-stu-id="6e271-348">16840</span></span>
<span data-ttu-id="6e271-349">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="6e271-349">parentProcessCreationTime</span></span> | <span data-ttu-id="6e271-350">entityType이 Process인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-350">Available if entityType is *Process*.</span></span> | <span data-ttu-id="6e271-351">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="6e271-351">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="6e271-352">ipAddress</span><span class="sxs-lookup"><span data-stu-id="6e271-352">ipAddress</span></span> | <span data-ttu-id="6e271-353">entityType이 Ip인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-353">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="6e271-354">악성 네트워크 대상에 대한 통신과 같은 네트워크 이벤트와 관련된 경고에 대한 IP *주소입니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-354">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="6e271-355">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="6e271-355">62.216.203.204</span></span>
<span data-ttu-id="6e271-356">url</span><span class="sxs-lookup"><span data-stu-id="6e271-356">url</span></span> | <span data-ttu-id="6e271-357">entityType이 Url인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-357">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="6e271-358">악성 네트워크 대상에 대한 통신과 같은 네트워크 이벤트와 관련된 *경고의 URL입니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-358">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="6e271-359">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="6e271-359">down.esales360.cn</span></span>
<span data-ttu-id="6e271-360">accountName</span><span class="sxs-lookup"><span data-stu-id="6e271-360">accountName</span></span> | <span data-ttu-id="6e271-361">entityType이 User인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-361">Available if entityType is *User*.</span></span> | <span data-ttu-id="6e271-362">testUser2</span><span class="sxs-lookup"><span data-stu-id="6e271-362">testUser2</span></span>
<span data-ttu-id="6e271-363">domainName</span><span class="sxs-lookup"><span data-stu-id="6e271-363">domainName</span></span> | <span data-ttu-id="6e271-364">entityType이 User인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-364">Available if entityType is *User*.</span></span> | <span data-ttu-id="6e271-365">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="6e271-365">europe.corp.contoso</span></span>
<span data-ttu-id="6e271-366">userSid</span><span class="sxs-lookup"><span data-stu-id="6e271-366">userSid</span></span> | <span data-ttu-id="6e271-367">entityType이 User인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-367">Available if entityType is *User*.</span></span> | <span data-ttu-id="6e271-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="6e271-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="6e271-369">aadUserId</span><span class="sxs-lookup"><span data-stu-id="6e271-369">aadUserId</span></span> | <span data-ttu-id="6e271-370">entityType이 User인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-370">Available if entityType is *User*.</span></span> | <span data-ttu-id="6e271-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="6e271-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="6e271-372">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="6e271-372">userPrincipalName</span></span> | <span data-ttu-id="6e271-373">entityType이 *User* / *MailBox* / *MailMessage인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-373">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="6e271-374">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6e271-374">testUser2@contoso.com</span></span>
<span data-ttu-id="6e271-375">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="6e271-375">mailboxDisplayName</span></span> | <span data-ttu-id="6e271-376">entityType이 *MailBox인 경우 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-376">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="6e271-377">test User2</span><span class="sxs-lookup"><span data-stu-id="6e271-377">test User2</span></span>
<span data-ttu-id="6e271-378">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="6e271-378">mailboxAddress</span></span> | <span data-ttu-id="6e271-379">entityType이 *User* / *MailBox* / *MailMessage인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-379">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="6e271-380">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6e271-380">testUser2@contoso.com</span></span>
<span data-ttu-id="6e271-381">clusterBy</span><span class="sxs-lookup"><span data-stu-id="6e271-381">clusterBy</span></span> | <span data-ttu-id="6e271-382">entityType이 *MailCluster인 경우 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-382">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="6e271-383">제목; P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="6e271-383">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="6e271-384">보낸 사람</span><span class="sxs-lookup"><span data-stu-id="6e271-384">sender</span></span> | <span data-ttu-id="6e271-385">entityType이 *User* / *MailBox* / *MailMessage인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-385">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="6e271-386">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="6e271-386">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="6e271-387">받는 사람</span><span class="sxs-lookup"><span data-stu-id="6e271-387">recipient</span></span> | <span data-ttu-id="6e271-388">entityType이 *MailMessage인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-388">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="6e271-389">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6e271-389">testUser2@contoso.com</span></span>
<span data-ttu-id="6e271-390">subject</span><span class="sxs-lookup"><span data-stu-id="6e271-390">subject</span></span> | <span data-ttu-id="6e271-391">entityType이 *MailMessage인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-391">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="6e271-392">\[외부 \] 주의</span><span class="sxs-lookup"><span data-stu-id="6e271-392">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="6e271-393">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="6e271-393">deliveryAction</span></span> | <span data-ttu-id="6e271-394">entityType이 *MailMessage인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-394">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="6e271-395">배달</span><span class="sxs-lookup"><span data-stu-id="6e271-395">Delivered</span></span>
<span data-ttu-id="6e271-396">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="6e271-396">securityGroupId</span></span> | <span data-ttu-id="6e271-397">entityType이 *SecurityGroup인 경우 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-397">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="6e271-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="6e271-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="6e271-399">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="6e271-399">securityGroupName</span></span> | <span data-ttu-id="6e271-400">entityType이 *SecurityGroup인 경우 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-400">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="6e271-401">네트워크 구성 연산자</span><span class="sxs-lookup"><span data-stu-id="6e271-401">Network Configuration Operators</span></span>
<span data-ttu-id="6e271-402">registryHive</span><span class="sxs-lookup"><span data-stu-id="6e271-402">registryHive</span></span> | <span data-ttu-id="6e271-403">entityType이 레지스트리인 *경우 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-403">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="6e271-404">HKEY \_ 로컬 \_ 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="6e271-404">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="6e271-405">registryKey</span><span class="sxs-lookup"><span data-stu-id="6e271-405">registryKey</span></span> | <span data-ttu-id="6e271-406">entityType이 레지스트리인 *경우 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-406">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="6e271-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="6e271-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="6e271-408">registryValueType</span><span class="sxs-lookup"><span data-stu-id="6e271-408">registryValueType</span></span> | <span data-ttu-id="6e271-409">entityType이 레지스트리인 *경우 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-409">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="6e271-410">문자열</span><span class="sxs-lookup"><span data-stu-id="6e271-410">String</span></span>
<span data-ttu-id="6e271-411">registryValue</span><span class="sxs-lookup"><span data-stu-id="6e271-411">registryValue</span></span> | <span data-ttu-id="6e271-412">entityType이 레지스트리인 *경우 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6e271-412">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="6e271-413">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="6e271-413">31-00-00-00</span></span>
<span data-ttu-id="6e271-414">deviceId</span><span class="sxs-lookup"><span data-stu-id="6e271-414">deviceId</span></span> | <span data-ttu-id="6e271-415">엔터티와 관련된 장치의 ID(있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="6e271-415">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="6e271-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="6e271-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="6e271-417">예제</span><span class="sxs-lookup"><span data-stu-id="6e271-417">Example</span></span>

<span data-ttu-id="6e271-418">**요청**</span><span class="sxs-lookup"><span data-stu-id="6e271-418">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="6e271-419">**응답**</span><span class="sxs-lookup"><span data-stu-id="6e271-419">**Response**</span></span>

```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-articles"></a><span data-ttu-id="6e271-420">관련 문서</span><span class="sxs-lookup"><span data-stu-id="6e271-420">Related articles</span></span>

- [<span data-ttu-id="6e271-421">Microsoft 365 Defender API에 액세스</span><span class="sxs-lookup"><span data-stu-id="6e271-421">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="6e271-422">API 제한 및 라이선싱에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="6e271-422">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="6e271-423">오류 코드 이해</span><span class="sxs-lookup"><span data-stu-id="6e271-423">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="6e271-424">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="6e271-424">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="6e271-425">인시던트 API</span><span class="sxs-lookup"><span data-stu-id="6e271-425">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="6e271-426">인시던트 API 업데이트</span><span class="sxs-lookup"><span data-stu-id="6e271-426">Update incident API</span></span>](api-update-incidents.md)
