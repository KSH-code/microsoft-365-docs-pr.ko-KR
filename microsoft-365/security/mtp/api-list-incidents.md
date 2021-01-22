---
title: Microsoft 365 Defender의 목록 인시던트 API
description: Microsoft 365 Defender에서 인시던트 API를 나열하는 방법에 대해 자세히 알아보기
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 39a170a1845ab33f67d77b2de3d5f298f67fdc99
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932073"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="bc421-104">Microsoft 365 Defender의 목록 인시던트 API</span><span class="sxs-lookup"><span data-stu-id="bc421-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bc421-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="bc421-105">**Applies to:**</span></span>

- <span data-ttu-id="bc421-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bc421-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc421-107">일부 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 미리 판매된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="bc421-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="bc421-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="bc421-109">API 설명</span><span class="sxs-lookup"><span data-stu-id="bc421-109">API description</span></span>

<span data-ttu-id="bc421-110">목록 인시던트 API를 사용하면 인시던트들을 정렬하여 정보를 토대한 사이버 보안 대응을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="bc421-111">네트워크에서 플래그가 지정된 인시던트 컬렉션을 환경 보존 정책에 지정한 시간 범위 내에 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="bc421-112">가장 최근 인시던트가 목록 맨 위에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="bc421-113">각 인시던트에는 관련 경고 및 관련 엔터티의 배열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="bc421-114">API는 다음 **OData 연산자를** 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="bc421-115">`$filter``lastUpdateTime`의 `createdTime` , `status` , 및 `assignedTo` 속성</span><span class="sxs-lookup"><span data-stu-id="bc421-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="bc421-116">`$top`의 **최대값이 100인 경우**</span><span class="sxs-lookup"><span data-stu-id="bc421-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="bc421-117">제한 사항</span><span class="sxs-lookup"><span data-stu-id="bc421-117">Limitations</span></span>

1. <span data-ttu-id="bc421-118">최대 페이지 크기는 **인시던트 100개입니다.**</span><span class="sxs-lookup"><span data-stu-id="bc421-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="bc421-119">최대 요청 속도는 분당 **50통,** 시간당 **1500통입니다.**</span><span class="sxs-lookup"><span data-stu-id="bc421-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="bc421-120">권한</span><span class="sxs-lookup"><span data-stu-id="bc421-120">Permissions</span></span>

<span data-ttu-id="bc421-121">이 API를 호출하려면 다음 권한 중 하나를 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="bc421-122">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Microsoft 365 Defender API 액세스](api-access.md) 참조</span><span class="sxs-lookup"><span data-stu-id="bc421-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="bc421-123">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="bc421-123">Permission type</span></span> | <span data-ttu-id="bc421-124">사용 권한</span><span class="sxs-lookup"><span data-stu-id="bc421-124">Permission</span></span> | <span data-ttu-id="bc421-125">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="bc421-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="bc421-126">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="bc421-126">Application</span></span> | <span data-ttu-id="bc421-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="bc421-127">Incident.Read.All</span></span> | <span data-ttu-id="bc421-128">모든 인시던트 읽기</span><span class="sxs-lookup"><span data-stu-id="bc421-128">Read all incidents</span></span>
<span data-ttu-id="bc421-129">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="bc421-129">Application</span></span> | <span data-ttu-id="bc421-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="bc421-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="bc421-131">모든 인시던트 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="bc421-131">Read and write all incidents</span></span>
<span data-ttu-id="bc421-132">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="bc421-132">Delegated (work or school account)</span></span> | <span data-ttu-id="bc421-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="bc421-133">Incident.Read</span></span> | <span data-ttu-id="bc421-134">인시던트 읽기</span><span class="sxs-lookup"><span data-stu-id="bc421-134">Read incidents</span></span>
<span data-ttu-id="bc421-135">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="bc421-135">Delegated (work or school account)</span></span> | <span data-ttu-id="bc421-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="bc421-136">Incident.ReadWrite</span></span> | <span data-ttu-id="bc421-137">인시던트 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="bc421-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="bc421-138">사용자 자격 증명을 사용하여 토큰을 얻을 때:</span><span class="sxs-lookup"><span data-stu-id="bc421-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="bc421-139">사용자에게 포털에서 인시던트에 대한 보기 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="bc421-140">응답에는 사용자가 노출하는 인시던트만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="bc421-141">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="bc421-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="bc421-142">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="bc421-142">Request headers</span></span>

<span data-ttu-id="bc421-143">이름</span><span class="sxs-lookup"><span data-stu-id="bc421-143">Name</span></span> | <span data-ttu-id="bc421-144">유형</span><span class="sxs-lookup"><span data-stu-id="bc421-144">Type</span></span> | <span data-ttu-id="bc421-145">설명</span><span class="sxs-lookup"><span data-stu-id="bc421-145">Description</span></span>
-|-|-
<span data-ttu-id="bc421-146">권한 부여</span><span class="sxs-lookup"><span data-stu-id="bc421-146">Authorization</span></span> | <span data-ttu-id="bc421-147">문자열</span><span class="sxs-lookup"><span data-stu-id="bc421-147">String</span></span> | <span data-ttu-id="bc421-148">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="bc421-148">Bearer {token}.</span></span> <span data-ttu-id="bc421-149">**필수**</span><span class="sxs-lookup"><span data-stu-id="bc421-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="bc421-150">요청 본문</span><span class="sxs-lookup"><span data-stu-id="bc421-150">Request body</span></span>

<span data-ttu-id="bc421-151">없음</span><span class="sxs-lookup"><span data-stu-id="bc421-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="bc421-152">응답</span><span class="sxs-lookup"><span data-stu-id="bc421-152">Response</span></span>

<span data-ttu-id="bc421-153">성공하면 이 메서드는 응답 본문의 인시던트 목록과 `200 OK` 인시던트 목록을 반환합니다. [](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="bc421-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="bc421-154">Schema mapping</span><span class="sxs-lookup"><span data-stu-id="bc421-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="bc421-155">인시던트 메타데이터</span><span class="sxs-lookup"><span data-stu-id="bc421-155">Incident metadata</span></span>

<span data-ttu-id="bc421-156">필드 이름</span><span class="sxs-lookup"><span data-stu-id="bc421-156">Field name</span></span> | <span data-ttu-id="bc421-157">설명</span><span class="sxs-lookup"><span data-stu-id="bc421-157">Description</span></span> | <span data-ttu-id="bc421-158">예제 값</span><span class="sxs-lookup"><span data-stu-id="bc421-158">Example value</span></span>
-|-|-
<span data-ttu-id="bc421-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="bc421-159">incidentId</span></span> | <span data-ttu-id="bc421-160">인시던트에 대한 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="bc421-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="bc421-161">924565</span><span class="sxs-lookup"><span data-stu-id="bc421-161">924565</span></span>
<span data-ttu-id="bc421-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="bc421-162">redirectIncidentId</span></span> | <span data-ttu-id="bc421-163">인시던트가 인시던트 처리 논리의 일부로 다른 인시던트와 함께 그룹화되는 경우만 채워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="bc421-164">924569</span><span class="sxs-lookup"><span data-stu-id="bc421-164">924569</span></span>
<span data-ttu-id="bc421-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="bc421-165">incidentName</span></span> | <span data-ttu-id="bc421-166">모든 인시던트에 사용할 수 있는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-166">String value available for every incident.</span></span> | <span data-ttu-id="bc421-167">랜섬웨어 활동</span><span class="sxs-lookup"><span data-stu-id="bc421-167">Ransomware activity</span></span>
<span data-ttu-id="bc421-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="bc421-168">createdTime</span></span> | <span data-ttu-id="bc421-169">인시던트가 처음 만들어진 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-169">Time when incident was first created.</span></span> | <span data-ttu-id="bc421-170">2020-09-06T14:46:57.073333Z</span><span class="sxs-lookup"><span data-stu-id="bc421-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="bc421-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="bc421-171">lastUpdateTime</span></span> | <span data-ttu-id="bc421-172">인시던트가 백엔드에서 마지막으로 업데이트된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="bc421-173">이 필드는 인시던트가 검색된 시간 범위에 대한 요청 매개 변수를 설정할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="bc421-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="bc421-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="bc421-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="bc421-175">assignedTo</span></span> | <span data-ttu-id="bc421-176">인시던트 소유자 또는 소유자가 할당되지 않은 경우 *null입니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="bc421-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="bc421-177">secop2@contoso.com</span></span>
<span data-ttu-id="bc421-178">classification</span><span class="sxs-lookup"><span data-stu-id="bc421-178">classification</span></span> | <span data-ttu-id="bc421-179">인시던트에 대한 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-179">The specification for the incident.</span></span> <span data-ttu-id="bc421-180">속성 값은 알 수 *없음,* *FalsePositive,* *TruePositive입니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="bc421-181">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="bc421-181">Unknown</span></span>
<span data-ttu-id="bc421-182">determination</span><span class="sxs-lookup"><span data-stu-id="bc421-182">determination</span></span> | <span data-ttu-id="bc421-183">인시던트의 결정</span><span class="sxs-lookup"><span data-stu-id="bc421-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="bc421-184">속성 값은 *NotAvailable,* *Apt,* *Malware,* *SecurityPersonnel*, *Security Malwareg,* *UnwantedSoftware*, *Other*</span><span class="sxs-lookup"><span data-stu-id="bc421-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="bc421-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="bc421-185">NotAvailable</span></span>
<span data-ttu-id="bc421-186">status</span><span class="sxs-lookup"><span data-stu-id="bc421-186">status</span></span> | <span data-ttu-id="bc421-187">인시던트(활성 또는 해결된 인시던트)를 *분류합니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="bc421-188">인시던트에 대한 대응을 구성하고 관리하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="bc421-189">활성</span><span class="sxs-lookup"><span data-stu-id="bc421-189">Active</span></span>
<span data-ttu-id="bc421-190">심각도</span><span class="sxs-lookup"><span data-stu-id="bc421-190">severity</span></span> | <span data-ttu-id="bc421-191">자산에 미칠 수 있는 영향을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="bc421-192">심각도가 높을수록 영향이 커집니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="bc421-193">일반적으로 심각도가 높은 항목은 가장 즉각적인 주의가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="bc421-194">정보, 낮음, \*보통 및 *높음* 값 중 하나</span><span class="sxs-lookup"><span data-stu-id="bc421-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="bc421-195">보통</span><span class="sxs-lookup"><span data-stu-id="bc421-195">Medium</span></span>
<span data-ttu-id="bc421-196">tags</span><span class="sxs-lookup"><span data-stu-id="bc421-196">tags</span></span> | <span data-ttu-id="bc421-197">인시던트와 연결된 사용자 지정 태그의 배열입니다. 예를 들어 인시던트 그룹에 공통적인 특성이 있는 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="bc421-198">alerts</span><span class="sxs-lookup"><span data-stu-id="bc421-198">alerts</span></span> | <span data-ttu-id="bc421-199">인시던트와 관련된 모든 경고와 심각도, 경고에 관련된 엔터티, 경고 원본 등의 기타 정보를 포함하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-199">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="bc421-200">\[\] (아래 경고 필드에 대한 세부 정보 참조)</span><span class="sxs-lookup"><span data-stu-id="bc421-200">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="bc421-201">경고 메타데이터</span><span class="sxs-lookup"><span data-stu-id="bc421-201">Alerts metadata</span></span>

<span data-ttu-id="bc421-202">필드 이름</span><span class="sxs-lookup"><span data-stu-id="bc421-202">Field name</span></span> | <span data-ttu-id="bc421-203">설명</span><span class="sxs-lookup"><span data-stu-id="bc421-203">Description</span></span> | <span data-ttu-id="bc421-204">예제 값</span><span class="sxs-lookup"><span data-stu-id="bc421-204">Example value</span></span>
-|-|-
<span data-ttu-id="bc421-205">alertId</span><span class="sxs-lookup"><span data-stu-id="bc421-205">alertId</span></span> | <span data-ttu-id="bc421-206">경고를 나타내는 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="bc421-206">Unique identifier to represent the alert</span></span> | <span data-ttu-id="bc421-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="bc421-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="bc421-208">incidentId</span><span class="sxs-lookup"><span data-stu-id="bc421-208">incidentId</span></span> | <span data-ttu-id="bc421-209">이 경고가 연결된 문제를 나타내는 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-209">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="bc421-210">924565</span><span class="sxs-lookup"><span data-stu-id="bc421-210">924565</span></span>
<span data-ttu-id="bc421-211">serviceSource</span><span class="sxs-lookup"><span data-stu-id="bc421-211">serviceSource</span></span> | <span data-ttu-id="bc421-212">경고가 시작된 서비스(예: Endpoint용 Microsoft Defender, Microsoft Cloud App Security, ID용 Microsoft Defender 또는 Office 365용 Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="bc421-212">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="bc421-213">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="bc421-213">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="bc421-214">creationTime</span><span class="sxs-lookup"><span data-stu-id="bc421-214">creationTime</span></span> | <span data-ttu-id="bc421-215">알림을 처음 만든 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-215">Time when alert was first created.</span></span> | <span data-ttu-id="bc421-216">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="bc421-216">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="bc421-217">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="bc421-217">lastUpdatedTime</span></span> | <span data-ttu-id="bc421-218">백엔드에서 경고가 마지막으로 업데이트된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-218">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="bc421-219">2020-09-06T14:46:57.243333Z</span><span class="sxs-lookup"><span data-stu-id="bc421-219">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="bc421-220">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="bc421-220">resolvedTime</span></span> | <span data-ttu-id="bc421-221">경고가 해결된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-221">Time when alert was resolved.</span></span> | <span data-ttu-id="bc421-222">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="bc421-222">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="bc421-223">firstActivity</span><span class="sxs-lookup"><span data-stu-id="bc421-223">firstActivity</span></span> | <span data-ttu-id="bc421-224">백엔드에서 활동이 업데이트된 것으로 처음 보고된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-224">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="bc421-225">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="bc421-225">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="bc421-226">title</span><span class="sxs-lookup"><span data-stu-id="bc421-226">title</span></span> | <span data-ttu-id="bc421-227">각 경고에 사용할 수 있는 간단한 식별 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-227">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="bc421-228">랜섬웨어 활동</span><span class="sxs-lookup"><span data-stu-id="bc421-228">Ransomware activity</span></span>
<span data-ttu-id="bc421-229">설명</span><span class="sxs-lookup"><span data-stu-id="bc421-229">description</span></span> | <span data-ttu-id="bc421-230">각 경고를 설명하는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-230">String value describing each alert.</span></span> | <span data-ttu-id="bc421-231">사용자 테스트 사용자2(testUser2@contoso.com)가 확장명을 여러 개 사용하여 99개 파일을 *조작했습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-231">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="bc421-232">이는 비정상적인 파일 조작 수로 잠재적인 랜섬웨어 공격을 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-232">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="bc421-233">category</span><span class="sxs-lookup"><span data-stu-id="bc421-233">category</span></span> | <span data-ttu-id="bc421-234">킬체인을 따라 공격이 진행된 거리의 시각적 및 숫자 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-234">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="bc421-235">[MITRE ATT&CK™ 정렬됩니다.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="bc421-235">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="bc421-236">영향</span><span class="sxs-lookup"><span data-stu-id="bc421-236">Impact</span></span>
<span data-ttu-id="bc421-237">status</span><span class="sxs-lookup"><span data-stu-id="bc421-237">status</span></span> | <span data-ttu-id="bc421-238">경고를 새 *경고,* 활성 경고 또는 해결된 *경고로* *분류합니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-238">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="bc421-239">경고에 대한 응답을 구성하고 관리하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-239">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="bc421-240">신규</span><span class="sxs-lookup"><span data-stu-id="bc421-240">New</span></span>
<span data-ttu-id="bc421-241">심각도</span><span class="sxs-lookup"><span data-stu-id="bc421-241">severity</span></span> | <span data-ttu-id="bc421-242">자산에 미칠 수 있는 영향을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-242">Indicates the possible impact on assets.</span></span> <span data-ttu-id="bc421-243">심각도가 높을수록 영향이 커집니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-243">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="bc421-244">일반적으로 심각도가 높은 항목은 가장 즉각적인 주의가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-244">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="bc421-245">정보, 낮음, \*보통 및 *높음* 값 중 하나</span><span class="sxs-lookup"><span data-stu-id="bc421-245">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="bc421-246">보통</span><span class="sxs-lookup"><span data-stu-id="bc421-246">Medium</span></span>
<span data-ttu-id="bc421-247">investigationId</span><span class="sxs-lookup"><span data-stu-id="bc421-247">investigationId</span></span> | <span data-ttu-id="bc421-248">이 경고에 의해 트리거된 자동화된 조사 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-248">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="bc421-249">1234</span><span class="sxs-lookup"><span data-stu-id="bc421-249">1234</span></span>
<span data-ttu-id="bc421-250">investigationState</span><span class="sxs-lookup"><span data-stu-id="bc421-250">investigationState</span></span> | <span data-ttu-id="bc421-251">조사의 현재 상태에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-251">Information on the investigation's current status.</span></span> <span data-ttu-id="bc421-252">다음 값 중 하나: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span><span class="sxs-lookup"><span data-stu-id="bc421-252">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="bc421-253">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="bc421-253">UnsupportedAlertType</span></span>
<span data-ttu-id="bc421-254">classification</span><span class="sxs-lookup"><span data-stu-id="bc421-254">classification</span></span> | <span data-ttu-id="bc421-255">인시던트에 대한 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-255">The specification for the incident.</span></span> <span data-ttu-id="bc421-256">속성 값은 알 수 *없음,* *FalsePositive,* *TruePositive* 또는 *null입니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-256">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="bc421-257">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="bc421-257">Unknown</span></span>
<span data-ttu-id="bc421-258">determination</span><span class="sxs-lookup"><span data-stu-id="bc421-258">determination</span></span> | <span data-ttu-id="bc421-259">인시던트의 결정</span><span class="sxs-lookup"><span data-stu-id="bc421-259">Specifies the determination of the incident.</span></span> <span data-ttu-id="bc421-260">속성 값은 *NotAvailable,* *Apt,* *Malware*, *SecurityPersonnel*, *Security Malware, SecuritySoftware,* *Other* 또는 *null입니다.* </span><span class="sxs-lookup"><span data-stu-id="bc421-260">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="bc421-261">Apt</span><span class="sxs-lookup"><span data-stu-id="bc421-261">Apt</span></span>
<span data-ttu-id="bc421-262">assignedTo</span><span class="sxs-lookup"><span data-stu-id="bc421-262">assignedTo</span></span> | <span data-ttu-id="bc421-263">인시던트 소유자 또는 소유자가 할당되지 않은 경우 *null입니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-263">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="bc421-264">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="bc421-264">secop2@contoso.com</span></span>
<span data-ttu-id="bc421-265">actorName</span><span class="sxs-lookup"><span data-stu-id="bc421-265">actorName</span></span> | <span data-ttu-id="bc421-266">이 경고와 연결된 활동 그룹(있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-266">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="bc421-267">BORON</span><span class="sxs-lookup"><span data-stu-id="bc421-267">BORON</span></span>
<span data-ttu-id="bc421-268">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="bc421-268">threatFamilyName</span></span> | <span data-ttu-id="bc421-269">이 경고와 연결된 위협 패밀리입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-269">Threat family associated with this alert.</span></span> | <span data-ttu-id="bc421-270">null</span><span class="sxs-lookup"><span data-stu-id="bc421-270">null</span></span>
<span data-ttu-id="bc421-271">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="bc421-271">mitreTechniques</span></span> | <span data-ttu-id="bc421-272">[MITRE ATT 및 CK 2013](https://attack.mitre.org/)프레임워크에&공격 ™ 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-272">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="bc421-273">장치</span><span class="sxs-lookup"><span data-stu-id="bc421-273">devices</span></span> | <span data-ttu-id="bc421-274">인시던트와 관련된 경고가 전송된 모든 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-274">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="bc421-275">\[\] (아래 엔터티 필드에 대한 세부 정보 참조)</span><span class="sxs-lookup"><span data-stu-id="bc421-275">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="bc421-276">디바이스 형식</span><span class="sxs-lookup"><span data-stu-id="bc421-276">Device format</span></span>

<span data-ttu-id="bc421-277">필드 이름</span><span class="sxs-lookup"><span data-stu-id="bc421-277">Field name</span></span> | <span data-ttu-id="bc421-278">설명</span><span class="sxs-lookup"><span data-stu-id="bc421-278">Description</span></span> | <span data-ttu-id="bc421-279">예제 값</span><span class="sxs-lookup"><span data-stu-id="bc421-279">Example value</span></span>
-|-|-
<span data-ttu-id="bc421-280">DeviceId</span><span class="sxs-lookup"><span data-stu-id="bc421-280">DeviceId</span></span> | <span data-ttu-id="bc421-281">Microsoft Defender ATP에 지정된 장치 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-281">The device ID as designated in Microsoft Defender ATP.</span></span> | <span data-ttu-id="bc421-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="bc421-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="bc421-283">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="bc421-283">aadDeviceId</span></span> |  <span data-ttu-id="bc421-284">Azure Active Directory에 지정된 장치 [ID입니다.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="bc421-284">The device ID as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="bc421-285">도메인에 가입된 디바이스에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-285">Only available for domain-joined devices.</span></span> | <span data-ttu-id="bc421-286">null</span><span class="sxs-lookup"><span data-stu-id="bc421-286">null</span></span>
<span data-ttu-id="bc421-287">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="bc421-287">deviceDnsName</span></span> | <span data-ttu-id="bc421-288">디바이스의 정식 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-288">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="bc421-289">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bc421-289">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="bc421-290">osPlatform</span><span class="sxs-lookup"><span data-stu-id="bc421-290">osPlatform</span></span> | <span data-ttu-id="bc421-291">디바이스가 실행 중인 OS 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-291">The OS platform the device is running.</span></span>| <span data-ttu-id="bc421-292">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="bc421-292">WindowsServer2016</span></span>
<span data-ttu-id="bc421-293">osBuild</span><span class="sxs-lookup"><span data-stu-id="bc421-293">osBuild</span></span> | <span data-ttu-id="bc421-294">디바이스가 실행 중인 OS의 빌드 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-294">The build version for the OS the device is running.</span></span> | <span data-ttu-id="bc421-295">14393</span><span class="sxs-lookup"><span data-stu-id="bc421-295">14393</span></span>
<span data-ttu-id="bc421-296">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="bc421-296">rbacGroupName</span></span> | <span data-ttu-id="bc421-297">장치와 [연결된](https://docs.microsoft.com/azure/role-based-access-control/overview) RBAC(역할 기반 액세스 제어) 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-297">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="bc421-298">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="bc421-298">WDATP-Ring0</span></span>
<span data-ttu-id="bc421-299">firstSeen</span><span class="sxs-lookup"><span data-stu-id="bc421-299">firstSeen</span></span> | <span data-ttu-id="bc421-300">장치를 처음 본 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-300">Time when device was first seen.</span></span> | <span data-ttu-id="bc421-301">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="bc421-301">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="bc421-302">healthStatus</span><span class="sxs-lookup"><span data-stu-id="bc421-302">healthStatus</span></span> | <span data-ttu-id="bc421-303">장치의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-303">The health state of the device.</span></span> | <span data-ttu-id="bc421-304">활성</span><span class="sxs-lookup"><span data-stu-id="bc421-304">Active</span></span>
<span data-ttu-id="bc421-305">riskScore</span><span class="sxs-lookup"><span data-stu-id="bc421-305">riskScore</span></span> | <span data-ttu-id="bc421-306">장치에 대한 위험 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-306">The risk score for the  device.</span></span> | <span data-ttu-id="bc421-307">높음</span><span class="sxs-lookup"><span data-stu-id="bc421-307">High</span></span>
<span data-ttu-id="bc421-308">엔터티</span><span class="sxs-lookup"><span data-stu-id="bc421-308">entities</span></span> | <span data-ttu-id="bc421-309">지정한 경고의 일부로 식별되거나 이와 관련된 모든 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-309">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="bc421-310">\[\] (아래 엔터티 필드에 대한 세부 정보 참조)</span><span class="sxs-lookup"><span data-stu-id="bc421-310">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="bc421-311">엔터티 형식</span><span class="sxs-lookup"><span data-stu-id="bc421-311">Entity Format</span></span>

<span data-ttu-id="bc421-312">필드 이름</span><span class="sxs-lookup"><span data-stu-id="bc421-312">Field name</span></span> | <span data-ttu-id="bc421-313">설명</span><span class="sxs-lookup"><span data-stu-id="bc421-313">Description</span></span> | <span data-ttu-id="bc421-314">예제 값</span><span class="sxs-lookup"><span data-stu-id="bc421-314">Example value</span></span>
-|-|-
<span data-ttu-id="bc421-315">entityType</span><span class="sxs-lookup"><span data-stu-id="bc421-315">entityType</span></span> | <span data-ttu-id="bc421-316">지정한 경고의 일부로 식별되거나 이와 관련된 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-316">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="bc421-317">속성 값은 *사용자,* *Ip,* *URL,* *파일,* *프로세스,* *MailBox,* *MailMessage,* *MailCluster,* *레지스트리입니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-317">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="bc421-318">사용자</span><span class="sxs-lookup"><span data-stu-id="bc421-318">User</span></span>
<span data-ttu-id="bc421-319">sha1</span><span class="sxs-lookup"><span data-stu-id="bc421-319">sha1</span></span> | <span data-ttu-id="bc421-320">entityType이 File인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-320">Available if entityType is *File*.</span></span><br><span data-ttu-id="bc421-321">파일 또는 프로세스와 연결된 경고에 대한 파일 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-321">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="bc421-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="bc421-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="bc421-323">sha256</span><span class="sxs-lookup"><span data-stu-id="bc421-323">sha256</span></span> | <span data-ttu-id="bc421-324">entityType이 File인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-324">Available if entityType is *File*.</span></span><br><span data-ttu-id="bc421-325">파일 또는 프로세스와 관련된 경고에 대한 파일 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-325">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="bc421-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="bc421-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="bc421-327">fileName</span><span class="sxs-lookup"><span data-stu-id="bc421-327">fileName</span></span> | <span data-ttu-id="bc421-328">entityType이 File인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-328">Available if entityType is *File*.</span></span><br><span data-ttu-id="bc421-329">파일 또는 프로세스와 연결된 경고의 파일 이름</span><span class="sxs-lookup"><span data-stu-id="bc421-329">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="bc421-330">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="bc421-330">Detector.UnitTests.dll</span></span>
<span data-ttu-id="bc421-331">filePath</span><span class="sxs-lookup"><span data-stu-id="bc421-331">filePath</span></span> | <span data-ttu-id="bc421-332">entityType이 File인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-332">Available if entityType is *File*.</span></span><br><span data-ttu-id="bc421-333">파일 또는 프로세스와 연결된 경고의 파일 경로</span><span class="sxs-lookup"><span data-stu-id="bc421-333">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="bc421-334">C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="bc421-334">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="bc421-335">processId</span><span class="sxs-lookup"><span data-stu-id="bc421-335">processId</span></span> | <span data-ttu-id="bc421-336">entityType이 Process인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-336">Available if entityType is *Process*.</span></span> | <span data-ttu-id="bc421-337">24348</span><span class="sxs-lookup"><span data-stu-id="bc421-337">24348</span></span>
<span data-ttu-id="bc421-338">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="bc421-338">processCommandLine</span></span> | <span data-ttu-id="bc421-339">entityType이 Process인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-339">Available if entityType is *Process*.</span></span> | <span data-ttu-id="bc421-340">"파일을 다운로드할 \_ 준비가1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="bc421-340">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="bc421-341">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="bc421-341">processCreationTime</span></span> | <span data-ttu-id="bc421-342">entityType이 Process인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-342">Available if entityType is *Process*.</span></span> | <span data-ttu-id="bc421-343">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="bc421-343">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="bc421-344">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="bc421-344">parentProcessId</span></span> | <span data-ttu-id="bc421-345">entityType이 Process인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-345">Available if entityType is *Process*.</span></span> | <span data-ttu-id="bc421-346">16840</span><span class="sxs-lookup"><span data-stu-id="bc421-346">16840</span></span>
<span data-ttu-id="bc421-347">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="bc421-347">parentProcessCreationTime</span></span> | <span data-ttu-id="bc421-348">entityType이 Process인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-348">Available if entityType is *Process*.</span></span> | <span data-ttu-id="bc421-349">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="bc421-349">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="bc421-350">ipAddress</span><span class="sxs-lookup"><span data-stu-id="bc421-350">ipAddress</span></span> | <span data-ttu-id="bc421-351">entityType이 Ip인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-351">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="bc421-352">악성 네트워크 대상에 대한 통신과 같은 네트워크 이벤트와 관련된 경고의 IP *주소입니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-352">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="bc421-353">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="bc421-353">62.216.203.204</span></span>
<span data-ttu-id="bc421-354">url</span><span class="sxs-lookup"><span data-stu-id="bc421-354">url</span></span> | <span data-ttu-id="bc421-355">entityType이 Url인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-355">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="bc421-356">악성 네트워크 대상에 대한 통신과 같은 네트워크 이벤트와 관련된 *경고의 URL입니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-356">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="bc421-357">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="bc421-357">down.esales360.cn</span></span>
<span data-ttu-id="bc421-358">accountName</span><span class="sxs-lookup"><span data-stu-id="bc421-358">accountName</span></span> | <span data-ttu-id="bc421-359">entityType이 User인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-359">Available if entityType is *User*.</span></span> | <span data-ttu-id="bc421-360">testUser2</span><span class="sxs-lookup"><span data-stu-id="bc421-360">testUser2</span></span>
<span data-ttu-id="bc421-361">domainName</span><span class="sxs-lookup"><span data-stu-id="bc421-361">domainName</span></span> | <span data-ttu-id="bc421-362">entityType이 User인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-362">Available if entityType is *User*.</span></span> | <span data-ttu-id="bc421-363">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="bc421-363">europe.corp.contoso</span></span>
<span data-ttu-id="bc421-364">userSid</span><span class="sxs-lookup"><span data-stu-id="bc421-364">userSid</span></span> | <span data-ttu-id="bc421-365">entityType이 User인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-365">Available if entityType is *User*.</span></span> | <span data-ttu-id="bc421-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="bc421-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="bc421-367">aadUserId</span><span class="sxs-lookup"><span data-stu-id="bc421-367">aadUserId</span></span> | <span data-ttu-id="bc421-368">entityType이 User인 경우 *사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-368">Available if entityType is *User*.</span></span> | <span data-ttu-id="bc421-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="bc421-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="bc421-370">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="bc421-370">userPrincipalName</span></span> | <span data-ttu-id="bc421-371">entityType이 *User* / *MailBox* / *MailMessage인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-371">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="bc421-372">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="bc421-372">testUser2@contoso.com</span></span>
<span data-ttu-id="bc421-373">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="bc421-373">mailboxDisplayName</span></span> | <span data-ttu-id="bc421-374">entityType이 *MailBox인 경우 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-374">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="bc421-375">test User2</span><span class="sxs-lookup"><span data-stu-id="bc421-375">test User2</span></span>
<span data-ttu-id="bc421-376">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="bc421-376">mailboxAddress</span></span> | <span data-ttu-id="bc421-377">entityType이 *User* / *MailBox* / *MailMessage인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-377">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="bc421-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="bc421-378">testUser2@contoso.com</span></span>
<span data-ttu-id="bc421-379">clusterBy</span><span class="sxs-lookup"><span data-stu-id="bc421-379">clusterBy</span></span> | <span data-ttu-id="bc421-380">entityType이 *MailCluster인 경우 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-380">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="bc421-381">제목; P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="bc421-381">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="bc421-382">보낸 사람</span><span class="sxs-lookup"><span data-stu-id="bc421-382">sender</span></span> | <span data-ttu-id="bc421-383">entityType이 *User* / *MailBox* / *MailMessage인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-383">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="bc421-384">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="bc421-384">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="bc421-385">받는 사람</span><span class="sxs-lookup"><span data-stu-id="bc421-385">recipient</span></span> | <span data-ttu-id="bc421-386">entityType이 *MailMessage인 경우 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-386">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="bc421-387">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="bc421-387">testUser2@contoso.com</span></span>
<span data-ttu-id="bc421-388">subject</span><span class="sxs-lookup"><span data-stu-id="bc421-388">subject</span></span> | <span data-ttu-id="bc421-389">entityType이 *MailMessage인 경우 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-389">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="bc421-390">\[외부 \] 주의</span><span class="sxs-lookup"><span data-stu-id="bc421-390">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="bc421-391">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="bc421-391">deliveryAction</span></span> | <span data-ttu-id="bc421-392">entityType이 *MailMessage인 경우 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-392">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="bc421-393">배달</span><span class="sxs-lookup"><span data-stu-id="bc421-393">Delivered</span></span>
<span data-ttu-id="bc421-394">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="bc421-394">securityGroupId</span></span> | <span data-ttu-id="bc421-395">entityType이 *SecurityGroup인 경우 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-395">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="bc421-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="bc421-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="bc421-397">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="bc421-397">securityGroupName</span></span> | <span data-ttu-id="bc421-398">entityType이 *SecurityGroup인 경우 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-398">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="bc421-399">네트워크 구성 연산자</span><span class="sxs-lookup"><span data-stu-id="bc421-399">Network Configuration Operators</span></span>
<span data-ttu-id="bc421-400">registryHive</span><span class="sxs-lookup"><span data-stu-id="bc421-400">registryHive</span></span> | <span data-ttu-id="bc421-401">entityType이 *레지스트리인 경우 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-401">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="bc421-402">HKEY \_ 로컬 \_ 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="bc421-402">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="bc421-403">registryKey</span><span class="sxs-lookup"><span data-stu-id="bc421-403">registryKey</span></span> | <span data-ttu-id="bc421-404">entityType이 *레지스트리인 경우 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-404">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="bc421-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="bc421-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="bc421-406">registryValueType</span><span class="sxs-lookup"><span data-stu-id="bc421-406">registryValueType</span></span> | <span data-ttu-id="bc421-407">entityType이 *레지스트리인 경우 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-407">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="bc421-408">문자열</span><span class="sxs-lookup"><span data-stu-id="bc421-408">String</span></span>
<span data-ttu-id="bc421-409">registryValue</span><span class="sxs-lookup"><span data-stu-id="bc421-409">registryValue</span></span> | <span data-ttu-id="bc421-410">entityType이 *레지스트리인 경우 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bc421-410">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="bc421-411">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="bc421-411">31-00-00-00</span></span>
<span data-ttu-id="bc421-412">deviceId</span><span class="sxs-lookup"><span data-stu-id="bc421-412">deviceId</span></span> | <span data-ttu-id="bc421-413">엔터티와 관련된 장치의 ID(있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="bc421-413">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="bc421-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="bc421-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="bc421-415">예시</span><span class="sxs-lookup"><span data-stu-id="bc421-415">Example</span></span>

<span data-ttu-id="bc421-416">**요청**</span><span class="sxs-lookup"><span data-stu-id="bc421-416">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="bc421-417">**응답**</span><span class="sxs-lookup"><span data-stu-id="bc421-417">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="bc421-418">관련 문서</span><span class="sxs-lookup"><span data-stu-id="bc421-418">Related articles</span></span>

- [<span data-ttu-id="bc421-419">Microsoft 365 Defender API 액세스</span><span class="sxs-lookup"><span data-stu-id="bc421-419">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="bc421-420">API 제한 및 라이선싱에 대해 자세히</span><span class="sxs-lookup"><span data-stu-id="bc421-420">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="bc421-421">오류 코드 이해</span><span class="sxs-lookup"><span data-stu-id="bc421-421">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="bc421-422">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="bc421-422">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="bc421-423">인시던트 API</span><span class="sxs-lookup"><span data-stu-id="bc421-423">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="bc421-424">인시던트 업데이트 API</span><span class="sxs-lookup"><span data-stu-id="bc421-424">Update incident API</span></span>](api-update-incidents.md)
