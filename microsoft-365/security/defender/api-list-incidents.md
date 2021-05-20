---
title: Microsoft 365 수비수에 인시던트 API 목록
description: Microsoft 365 Defender에서 인시던트 API를 나열하는 방법 알아보기
keywords: 목록, 인시던트, 인시던트, API
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
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="61b27-104">Microsoft 365 수비수에 인시던트 API 목록</span><span class="sxs-lookup"><span data-stu-id="61b27-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="61b27-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="61b27-105">**Applies to:**</span></span>

- <span data-ttu-id="61b27-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61b27-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61b27-107">일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="61b27-108">Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="61b27-109">API 설명</span><span class="sxs-lookup"><span data-stu-id="61b27-109">API description</span></span>

<span data-ttu-id="61b27-110">목록 인시던트 API를 사용하면 인시던트를 정렬하여 정보에 입각한 사이버 보안 응답을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="61b27-111">환경 보존 정책에 지정한 시간 범위 내에서 네트워크에 플래그가 지정된 인시던트 컬렉션을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="61b27-112">가장 최근의 인시던트는 목록의 맨 위에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="61b27-113">각 인시던트에는 관련 경고 배열과 관련 엔터티가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="61b27-114">API는 다음과 같은 **OData** 연산업체를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="61b27-115">`$filter` 에 `lastUpdateTime` `createdTime` , `status` 및 `assignedTo` 속성</span><span class="sxs-lookup"><span data-stu-id="61b27-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="61b27-116">`$top`최대 **값100**</span><span class="sxs-lookup"><span data-stu-id="61b27-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="61b27-117">제한 사항</span><span class="sxs-lookup"><span data-stu-id="61b27-117">Limitations</span></span>

1. <span data-ttu-id="61b27-118">최대 페이지 크기는 **100인시입니다.**</span><span class="sxs-lookup"><span data-stu-id="61b27-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="61b27-119">최대 요청 속도는 **분당 50회 통화,** **시간당 1,500건의 통화입니다.**</span><span class="sxs-lookup"><span data-stu-id="61b27-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="61b27-120">권한</span><span class="sxs-lookup"><span data-stu-id="61b27-120">Permissions</span></span>

<span data-ttu-id="61b27-121">다음 권한 중 하나는 이 API를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="61b27-122">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [액세스 Microsoft 365 수비수 API를 참조하십시오.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="61b27-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="61b27-123">권한 유형</span><span class="sxs-lookup"><span data-stu-id="61b27-123">Permission type</span></span> | <span data-ttu-id="61b27-124">사용 권한</span><span class="sxs-lookup"><span data-stu-id="61b27-124">Permission</span></span> | <span data-ttu-id="61b27-125">권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="61b27-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="61b27-126">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="61b27-126">Application</span></span> | <span data-ttu-id="61b27-127">사건.읽기.모든</span><span class="sxs-lookup"><span data-stu-id="61b27-127">Incident.Read.All</span></span> | <span data-ttu-id="61b27-128">모든 인시던트 읽기</span><span class="sxs-lookup"><span data-stu-id="61b27-128">Read all incidents</span></span>
<span data-ttu-id="61b27-129">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="61b27-129">Application</span></span> | <span data-ttu-id="61b27-130">인시던트.읽기쓰기.모든 것</span><span class="sxs-lookup"><span data-stu-id="61b27-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="61b27-131">모든 인시던트 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="61b27-131">Read and write all incidents</span></span>
<span data-ttu-id="61b27-132">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="61b27-132">Delegated (work or school account)</span></span> | <span data-ttu-id="61b27-133">인시던트.읽기</span><span class="sxs-lookup"><span data-stu-id="61b27-133">Incident.Read</span></span> | <span data-ttu-id="61b27-134">인시던트 읽기</span><span class="sxs-lookup"><span data-stu-id="61b27-134">Read incidents</span></span>
<span data-ttu-id="61b27-135">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="61b27-135">Delegated (work or school account)</span></span> | <span data-ttu-id="61b27-136">인시던트.읽기</span><span class="sxs-lookup"><span data-stu-id="61b27-136">Incident.ReadWrite</span></span> | <span data-ttu-id="61b27-137">인시던트 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="61b27-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="61b27-138">사용자 자격 증명을 사용하여 토큰을 획득하는 경우:</span><span class="sxs-lookup"><span data-stu-id="61b27-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="61b27-139">사용자는 포털에서 인시던트에 대한 보기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="61b27-140">응답에는 사용자가 노출되는 인시던트만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="61b27-141">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="61b27-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="61b27-142">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="61b27-142">Request headers</span></span>

<span data-ttu-id="61b27-143">이름</span><span class="sxs-lookup"><span data-stu-id="61b27-143">Name</span></span> | <span data-ttu-id="61b27-144">유형</span><span class="sxs-lookup"><span data-stu-id="61b27-144">Type</span></span> | <span data-ttu-id="61b27-145">설명</span><span class="sxs-lookup"><span data-stu-id="61b27-145">Description</span></span>
-|-|-
<span data-ttu-id="61b27-146">권한 부여</span><span class="sxs-lookup"><span data-stu-id="61b27-146">Authorization</span></span> | <span data-ttu-id="61b27-147">문자열</span><span class="sxs-lookup"><span data-stu-id="61b27-147">String</span></span> | <span data-ttu-id="61b27-148">베어러 {토큰}.</span><span class="sxs-lookup"><span data-stu-id="61b27-148">Bearer {token}.</span></span> <span data-ttu-id="61b27-149">**필수**</span><span class="sxs-lookup"><span data-stu-id="61b27-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="61b27-150">요청 본문</span><span class="sxs-lookup"><span data-stu-id="61b27-150">Request body</span></span>

<span data-ttu-id="61b27-151">없음</span><span class="sxs-lookup"><span data-stu-id="61b27-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="61b27-152">응답</span><span class="sxs-lookup"><span data-stu-id="61b27-152">Response</span></span>

<span data-ttu-id="61b27-153">성공하면 이 `200 OK` 메서드가 반환되고 응답 본문에 [인시던트](api-incident.md) 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="61b27-154">스키마 매핑</span><span class="sxs-lookup"><span data-stu-id="61b27-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="61b27-155">인시던트 메타데이터</span><span class="sxs-lookup"><span data-stu-id="61b27-155">Incident metadata</span></span>

<span data-ttu-id="61b27-156">필드 이름</span><span class="sxs-lookup"><span data-stu-id="61b27-156">Field name</span></span> | <span data-ttu-id="61b27-157">설명</span><span class="sxs-lookup"><span data-stu-id="61b27-157">Description</span></span> | <span data-ttu-id="61b27-158">예제 값</span><span class="sxs-lookup"><span data-stu-id="61b27-158">Example value</span></span>
-|-|-
<span data-ttu-id="61b27-159">인시던트Id</span><span class="sxs-lookup"><span data-stu-id="61b27-159">incidentId</span></span> | <span data-ttu-id="61b27-160">인시던트를 나타내는 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="61b27-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="61b27-161">924565</span><span class="sxs-lookup"><span data-stu-id="61b27-161">924565</span></span>
<span data-ttu-id="61b27-162">리디렉션우연히이드</span><span class="sxs-lookup"><span data-stu-id="61b27-162">redirectIncidentId</span></span> | <span data-ttu-id="61b27-163">인시던트 처리 논리의 일부로 인시던트가 다른 인시던트와 함께 그룹화되는 경우에만 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="61b27-164">924569</span><span class="sxs-lookup"><span data-stu-id="61b27-164">924569</span></span>
<span data-ttu-id="61b27-165">인시던트 이름</span><span class="sxs-lookup"><span data-stu-id="61b27-165">incidentName</span></span> | <span data-ttu-id="61b27-166">모든 인시던트에 사용할 수 있는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-166">String value available for every incident.</span></span> | <span data-ttu-id="61b27-167">랜섬웨어 활동</span><span class="sxs-lookup"><span data-stu-id="61b27-167">Ransomware activity</span></span>
<span data-ttu-id="61b27-168">만든 시간</span><span class="sxs-lookup"><span data-stu-id="61b27-168">createdTime</span></span> | <span data-ttu-id="61b27-169">인시던트를 처음 만든 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-169">Time when incident was first created.</span></span> | <span data-ttu-id="61b27-170">2020-09-06T14:46:57.0733333Z</span><span class="sxs-lookup"><span data-stu-id="61b27-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="61b27-171">마지막 업데이트 시간</span><span class="sxs-lookup"><span data-stu-id="61b27-171">lastUpdateTime</span></span> | <span data-ttu-id="61b27-172">백엔드에서 사건이 마지막으로 업데이트된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="61b27-173">이 필드는 인시던트가 검색되는 시간 범위에 대한 요청 매개 변수를 설정할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="61b27-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="61b27-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="61b27-175">할당To</span><span class="sxs-lookup"><span data-stu-id="61b27-175">assignedTo</span></span> | <span data-ttu-id="61b27-176">인시던트 소유자 또는 소유자가 할당되지 않은 경우 *null입니다.*</span><span class="sxs-lookup"><span data-stu-id="61b27-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="61b27-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b27-177">secop2@contoso.com</span></span>
<span data-ttu-id="61b27-178">분류</span><span class="sxs-lookup"><span data-stu-id="61b27-178">classification</span></span> | <span data-ttu-id="61b27-179">인시던트 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-179">The specification for the incident.</span></span> <span data-ttu-id="61b27-180">속성 값은 다음과 같습니다: *알 수 없는,* *거짓 긍정,* *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="61b27-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="61b27-181">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="61b27-181">Unknown</span></span>
<span data-ttu-id="61b27-182">결심</span><span class="sxs-lookup"><span data-stu-id="61b27-182">determination</span></span> | <span data-ttu-id="61b27-183">인시던트 의 결정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="61b27-184">속성 값은 다음과 같습니다 사용할 *수 없음,* *Apt,* *악성 코드,* *보안 담당자,* *보안 테스트,* *원치 않는 소프트웨어,* *기타*</span><span class="sxs-lookup"><span data-stu-id="61b27-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="61b27-185">사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="61b27-185">NotAvailable</span></span>
<span data-ttu-id="61b27-186">상태</span><span class="sxs-lookup"><span data-stu-id="61b27-186">status</span></span> | <span data-ttu-id="61b27-187">인시던트를 *분류합니다(활성* 또는 *해결됨).*</span><span class="sxs-lookup"><span data-stu-id="61b27-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="61b27-188">그것은 당신이 조직하고 인시던트에 대한 응답을 관리하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="61b27-189">활성</span><span class="sxs-lookup"><span data-stu-id="61b27-189">Active</span></span>
<span data-ttu-id="61b27-190">심각도</span><span class="sxs-lookup"><span data-stu-id="61b27-190">severity</span></span> | <span data-ttu-id="61b27-191">자산에 미치는 영향을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="61b27-192">심각도가 높을수록 영향이 커지를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="61b27-193">일반적으로 심각도가 높을수록 가장 즉각적인 주의가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="61b27-194">다음 값 중 하나: \*정보, 낮음,\*\*중간 값 및 *높음*. </span><span class="sxs-lookup"><span data-stu-id="61b27-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="61b27-195">보통</span><span class="sxs-lookup"><span data-stu-id="61b27-195">Medium</span></span>
<span data-ttu-id="61b27-196">태그</span><span class="sxs-lookup"><span data-stu-id="61b27-196">tags</span></span> | <span data-ttu-id="61b27-197">인시던트와 관련된 사용자 지정 태그배열(예: 공통 특성을 가진 인시던트 그룹에 플래그지정).</span><span class="sxs-lookup"><span data-stu-id="61b27-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="61b27-198">코멘트</span><span class="sxs-lookup"><span data-stu-id="61b27-198">comments</span></span> | <span data-ttu-id="61b27-199">인시던트를 관리할 때 secops에서 만든 주석 배열(예: 분류 선택에 대한 추가 정보).</span><span class="sxs-lookup"><span data-stu-id="61b27-199">Array of comments created by secops when managing the incident, for example additional information about the classification selection.</span></span> | \[\]
<span data-ttu-id="61b27-200">경고</span><span class="sxs-lookup"><span data-stu-id="61b27-200">alerts</span></span> | <span data-ttu-id="61b27-201">인시던트와 관련된 모든 경고와 심각도, 경고에 관련된 엔터티 및 경고소스와 같은 기타 정보가 포함된 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-201">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="61b27-202">\[\] (아래 경고 필드에 대한 세부 정보 참조)</span><span class="sxs-lookup"><span data-stu-id="61b27-202">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="61b27-203">알림 메타데이터</span><span class="sxs-lookup"><span data-stu-id="61b27-203">Alerts metadata</span></span>

<span data-ttu-id="61b27-204">필드 이름</span><span class="sxs-lookup"><span data-stu-id="61b27-204">Field name</span></span> | <span data-ttu-id="61b27-205">설명</span><span class="sxs-lookup"><span data-stu-id="61b27-205">Description</span></span> | <span data-ttu-id="61b27-206">예제 값</span><span class="sxs-lookup"><span data-stu-id="61b27-206">Example value</span></span>
-|-|-
<span data-ttu-id="61b27-207">경고Id</span><span class="sxs-lookup"><span data-stu-id="61b27-207">alertId</span></span> | <span data-ttu-id="61b27-208">경고를 나타내는 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="61b27-208">Unique identifier to represent the alert</span></span> | <span data-ttu-id="61b27-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="61b27-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="61b27-210">인시던트Id</span><span class="sxs-lookup"><span data-stu-id="61b27-210">incidentId</span></span> | <span data-ttu-id="61b27-211">이 경고가 연관된 인시던트를 나타내는 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="61b27-211">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="61b27-212">924565</span><span class="sxs-lookup"><span data-stu-id="61b27-212">924565</span></span>
<span data-ttu-id="61b27-213">서비스 소스</span><span class="sxs-lookup"><span data-stu-id="61b27-213">serviceSource</span></span> | <span data-ttu-id="61b27-214">엔드포인트에 대한 Microsoft Defender, Microsoft Cloud App Security, 신원에 대한 Microsoft 수비수 또는 Office 365 대한 Microsoft Defender와 같이 경고가 시작된 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-214">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="61b27-215">마이크로소프트클라우드앱시큐리티</span><span class="sxs-lookup"><span data-stu-id="61b27-215">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="61b27-216">창조시간</span><span class="sxs-lookup"><span data-stu-id="61b27-216">creationTime</span></span> | <span data-ttu-id="61b27-217">경고가 처음 생성된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-217">Time when alert was first created.</span></span> | <span data-ttu-id="61b27-218">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="61b27-218">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="61b27-219">마지막 업데이트 시간</span><span class="sxs-lookup"><span data-stu-id="61b27-219">lastUpdatedTime</span></span> | <span data-ttu-id="61b27-220">백엔드에서 경고가 마지막으로 업데이트된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-220">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="61b27-221">2020-09-06T14:46:57.2433333Z</span><span class="sxs-lookup"><span data-stu-id="61b27-221">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="61b27-222">해결시간</span><span class="sxs-lookup"><span data-stu-id="61b27-222">resolvedTime</span></span> | <span data-ttu-id="61b27-223">경고가 해결된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-223">Time when alert was resolved.</span></span> | <span data-ttu-id="61b27-224">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="61b27-224">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="61b27-225">첫 번째 활동</span><span class="sxs-lookup"><span data-stu-id="61b27-225">firstActivity</span></span> | <span data-ttu-id="61b27-226">경고가 백엔드에서 활동이 업데이트되었다고 처음 보고한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-226">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="61b27-227">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="61b27-227">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="61b27-228">title</span><span class="sxs-lookup"><span data-stu-id="61b27-228">title</span></span> | <span data-ttu-id="61b27-229">각 경고에 사용할 수 있는 문자열 값을 간략하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-229">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="61b27-230">랜섬웨어 활동</span><span class="sxs-lookup"><span data-stu-id="61b27-230">Ransomware activity</span></span>
<span data-ttu-id="61b27-231">설명</span><span class="sxs-lookup"><span data-stu-id="61b27-231">description</span></span> | <span data-ttu-id="61b27-232">각 경고를 설명하는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-232">String value describing each alert.</span></span> | <span data-ttu-id="61b27-233">사용자 테스트 User2(testUser2@contoso.com)는 99개의 파일을 조작하여 여러 개의 확장이 드문 확장 으로 끝나는 *경우를 대지* 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-233">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="61b27-234">이것은 파일 조작의 특이한 수이며 잠재적 인 랜섬웨어 공격을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-234">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="61b27-235">범주</span><span class="sxs-lookup"><span data-stu-id="61b27-235">category</span></span> | <span data-ttu-id="61b27-236">공격이 킬 체인을 따라 얼마나 진행되었는지에 대한 시각적 이고 숫자보기입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-236">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="61b27-237">[MITRE ATT&CK™ 프레임워크에](https://attack.mitre.org/)정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-237">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="61b27-238">영향</span><span class="sxs-lookup"><span data-stu-id="61b27-238">Impact</span></span>
<span data-ttu-id="61b27-239">상태</span><span class="sxs-lookup"><span data-stu-id="61b27-239">status</span></span> | <span data-ttu-id="61b27-240">경고를 *분류합니다(새,* *활성* 또는 *해결됨).*</span><span class="sxs-lookup"><span data-stu-id="61b27-240">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="61b27-241">경고에 대한 응답을 구성하고 관리하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-241">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="61b27-242">신규</span><span class="sxs-lookup"><span data-stu-id="61b27-242">New</span></span>
<span data-ttu-id="61b27-243">심각도</span><span class="sxs-lookup"><span data-stu-id="61b27-243">severity</span></span> | <span data-ttu-id="61b27-244">자산에 미치는 영향을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-244">Indicates the possible impact on assets.</span></span> <span data-ttu-id="61b27-245">심각도가 높을수록 영향이 커지를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-245">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="61b27-246">일반적으로 심각도가 높을수록 가장 즉각적인 주의가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-246">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="61b27-247">다음 값 중 하나: \*정보, 낮음,\*\*중간 값 및 *높음*. </span><span class="sxs-lookup"><span data-stu-id="61b27-247">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="61b27-248">보통</span><span class="sxs-lookup"><span data-stu-id="61b27-248">Medium</span></span>
<span data-ttu-id="61b27-249">조사 Id</span><span class="sxs-lookup"><span data-stu-id="61b27-249">investigationId</span></span> | <span data-ttu-id="61b27-250">이 경고로 트리거된 자동 조사 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-250">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="61b27-251">1234</span><span class="sxs-lookup"><span data-stu-id="61b27-251">1234</span></span>
<span data-ttu-id="61b27-252">조사 상태</span><span class="sxs-lookup"><span data-stu-id="61b27-252">investigationState</span></span> | <span data-ttu-id="61b27-253">조사의 현재 상태에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-253">Information on the investigation's current status.</span></span> <span data-ttu-id="61b27-254">다음 값 중 하나 : *알 수없는,* *종료,* *성공적으로 Remediated,* *양성,* *실패,* *부분적으로 Remediated,* *실행,* *보류 중인 승인, 보류* *자원,* *부분적으로 조사,* *종료ByUser,* *종료BySystem,* *대기열,* *내부 실패,* *기존 경고,* *지원되지* 않는 *경고 유형,* 억제 *경고.*</span><span class="sxs-lookup"><span data-stu-id="61b27-254">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="61b27-255">지원되지 않는 경고 유형</span><span class="sxs-lookup"><span data-stu-id="61b27-255">UnsupportedAlertType</span></span>
<span data-ttu-id="61b27-256">분류</span><span class="sxs-lookup"><span data-stu-id="61b27-256">classification</span></span> | <span data-ttu-id="61b27-257">인시던트 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-257">The specification for the incident.</span></span> <span data-ttu-id="61b27-258">속성 값은 다음과 같습니다: *알 수 없음,* *거짓 긍정,* *TruePositive* 또는 *null*</span><span class="sxs-lookup"><span data-stu-id="61b27-258">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="61b27-259">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="61b27-259">Unknown</span></span>
<span data-ttu-id="61b27-260">결심</span><span class="sxs-lookup"><span data-stu-id="61b27-260">determination</span></span> | <span data-ttu-id="61b27-261">인시던트 의 결정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-261">Specifies the determination of the incident.</span></span> <span data-ttu-id="61b27-262">속성 값은 다음과 같습니다 사용할 *수 없음,* *Apt,* *악성 코드,* *보안 담당자,* *보안 테스트,* *원치 않는 소프트웨어,* *기타* 또는  *null*</span><span class="sxs-lookup"><span data-stu-id="61b27-262">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="61b27-263">Apt</span><span class="sxs-lookup"><span data-stu-id="61b27-263">Apt</span></span>
<span data-ttu-id="61b27-264">할당To</span><span class="sxs-lookup"><span data-stu-id="61b27-264">assignedTo</span></span> | <span data-ttu-id="61b27-265">인시던트 소유자 또는 소유자가 할당되지 않은 경우 *null입니다.*</span><span class="sxs-lookup"><span data-stu-id="61b27-265">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="61b27-266">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b27-266">secop2@contoso.com</span></span>
<span data-ttu-id="61b27-267">배우 이름</span><span class="sxs-lookup"><span data-stu-id="61b27-267">actorName</span></span> | <span data-ttu-id="61b27-268">이 경고와 연결된 활동 그룹(있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-268">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="61b27-269">붕소</span><span class="sxs-lookup"><span data-stu-id="61b27-269">BORON</span></span>
<span data-ttu-id="61b27-270">위협가족이름</span><span class="sxs-lookup"><span data-stu-id="61b27-270">threatFamilyName</span></span> | <span data-ttu-id="61b27-271">이 경고와 관련된 위협 패밀리입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-271">Threat family associated with this alert.</span></span> | <span data-ttu-id="61b27-272">null</span><span class="sxs-lookup"><span data-stu-id="61b27-272">null</span></span>
<span data-ttu-id="61b27-273">미트레테크닉</span><span class="sxs-lookup"><span data-stu-id="61b27-273">mitreTechniques</span></span> | <span data-ttu-id="61b27-274">[MITRE ATT&CK](https://attack.mitre.org/)™ 프레임워크와 정렬된 공격 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-274">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="61b27-275">장치</span><span class="sxs-lookup"><span data-stu-id="61b27-275">devices</span></span> | <span data-ttu-id="61b27-276">인시던트와 관련된 경고가 전송된 모든 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-276">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="61b27-277">\[\] (아래 엔터티 필드에 대한 세부 정보 참조)</span><span class="sxs-lookup"><span data-stu-id="61b27-277">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="61b27-278">장치 형식</span><span class="sxs-lookup"><span data-stu-id="61b27-278">Device format</span></span>

<span data-ttu-id="61b27-279">필드 이름</span><span class="sxs-lookup"><span data-stu-id="61b27-279">Field name</span></span> | <span data-ttu-id="61b27-280">설명</span><span class="sxs-lookup"><span data-stu-id="61b27-280">Description</span></span> | <span data-ttu-id="61b27-281">예제 값</span><span class="sxs-lookup"><span data-stu-id="61b27-281">Example value</span></span>
-|-|-
<span data-ttu-id="61b27-282">DeviceId</span><span class="sxs-lookup"><span data-stu-id="61b27-282">DeviceId</span></span> | <span data-ttu-id="61b27-283">엔드포인트에 대한 Microsoft Defender에 지정된 장치 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-283">The device ID as designated in Microsoft Defender for Endpoint.</span></span> | <span data-ttu-id="61b27-284">24c222b0b60fe148eece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="61b27-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="61b27-285">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="61b27-285">aadDeviceId</span></span> |  <span data-ttu-id="61b27-286">[Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis)지정된 장치 ID.</span><span class="sxs-lookup"><span data-stu-id="61b27-286">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="61b27-287">도메인에 가입한 장치에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-287">Only available for domain-joined devices.</span></span> | <span data-ttu-id="61b27-288">null</span><span class="sxs-lookup"><span data-stu-id="61b27-288">null</span></span>
<span data-ttu-id="61b27-289">장치DnsName</span><span class="sxs-lookup"><span data-stu-id="61b27-289">deviceDnsName</span></span> | <span data-ttu-id="61b27-290">장치에 대한 완전히 인증된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-290">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="61b27-291">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b27-291">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="61b27-292">오스 플랫폼</span><span class="sxs-lookup"><span data-stu-id="61b27-292">osPlatform</span></span> | <span data-ttu-id="61b27-293">장치가 실행 중인 OS 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-293">The OS platform the device is running.</span></span>| <span data-ttu-id="61b27-294">윈도우 서버2016</span><span class="sxs-lookup"><span data-stu-id="61b27-294">WindowsServer2016</span></span>
<span data-ttu-id="61b27-295">osBuild</span><span class="sxs-lookup"><span data-stu-id="61b27-295">osBuild</span></span> | <span data-ttu-id="61b27-296">장치가 실행 중인 OS의 빌드 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-296">The build version for the OS the device is running.</span></span> | <span data-ttu-id="61b27-297">14393</span><span class="sxs-lookup"><span data-stu-id="61b27-297">14393</span></span>
<span data-ttu-id="61b27-298">rbac그룹이름</span><span class="sxs-lookup"><span data-stu-id="61b27-298">rbacGroupName</span></span> | <span data-ttu-id="61b27-299">장치와 연결된 역할 기반 액세스 제어(RBAC) 그룹입니다. [](/azure/role-based-access-control/overview)</span><span class="sxs-lookup"><span data-stu-id="61b27-299">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="61b27-300">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="61b27-300">WDATP-Ring0</span></span>
<span data-ttu-id="61b27-301">첫 번째 본</span><span class="sxs-lookup"><span data-stu-id="61b27-301">firstSeen</span></span> | <span data-ttu-id="61b27-302">장치가 처음 본 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-302">Time when device was first seen.</span></span> | <span data-ttu-id="61b27-303">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="61b27-303">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="61b27-304">건강 상태</span><span class="sxs-lookup"><span data-stu-id="61b27-304">healthStatus</span></span> | <span data-ttu-id="61b27-305">장치의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-305">The health state of the device.</span></span> | <span data-ttu-id="61b27-306">활성</span><span class="sxs-lookup"><span data-stu-id="61b27-306">Active</span></span>
<span data-ttu-id="61b27-307">위험점수</span><span class="sxs-lookup"><span data-stu-id="61b27-307">riskScore</span></span> | <span data-ttu-id="61b27-308">장치의 위험 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-308">The risk score for the  device.</span></span> | <span data-ttu-id="61b27-309">높음</span><span class="sxs-lookup"><span data-stu-id="61b27-309">High</span></span>
<span data-ttu-id="61b27-310">엔터티</span><span class="sxs-lookup"><span data-stu-id="61b27-310">entities</span></span> | <span data-ttu-id="61b27-311">지정된 경고의 일부 또는 관련 것으로 확인된 모든 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-311">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="61b27-312">\[\] (아래 엔터티 필드에 대한 세부 정보 참조)</span><span class="sxs-lookup"><span data-stu-id="61b27-312">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="61b27-313">엔터티 형식</span><span class="sxs-lookup"><span data-stu-id="61b27-313">Entity Format</span></span>

<span data-ttu-id="61b27-314">필드 이름</span><span class="sxs-lookup"><span data-stu-id="61b27-314">Field name</span></span> | <span data-ttu-id="61b27-315">설명</span><span class="sxs-lookup"><span data-stu-id="61b27-315">Description</span></span> | <span data-ttu-id="61b27-316">예제 값</span><span class="sxs-lookup"><span data-stu-id="61b27-316">Example value</span></span>
-|-|-
<span data-ttu-id="61b27-317">엔터티Type</span><span class="sxs-lookup"><span data-stu-id="61b27-317">entityType</span></span> | <span data-ttu-id="61b27-318">지정된 경고의 일부 또는 관련 것으로 확인된 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-318">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="61b27-319">속성 값은 : *사용자,* *IP,* *URL,* *파일,* *프로세스,* *사서함,* *사서 함,* *우편 클러스터,* *레지스트리*</span><span class="sxs-lookup"><span data-stu-id="61b27-319">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="61b27-320">사용자</span><span class="sxs-lookup"><span data-stu-id="61b27-320">User</span></span>
<span data-ttu-id="61b27-321">샤1</span><span class="sxs-lookup"><span data-stu-id="61b27-321">sha1</span></span> | <span data-ttu-id="61b27-322">엔터티Type이 *파일인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-322">Available if entityType is *File*.</span></span><br><span data-ttu-id="61b27-323">파일 또는 프로세스와 연결된 경고에 대한 파일 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-323">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="61b27-324">5de839186691aa96e2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="61b27-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="61b27-325">샤256</span><span class="sxs-lookup"><span data-stu-id="61b27-325">sha256</span></span> | <span data-ttu-id="61b27-326">엔터티Type이 *파일인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-326">Available if entityType is *File*.</span></span><br><span data-ttu-id="61b27-327">파일 또는 프로세스와 연결된 경고에 대한 파일 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-327">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="61b27-328">28cb017dfc907a1b477c1b30f413e3ce7744c49991eb4158de50f9dbb36d80433</span><span class="sxs-lookup"><span data-stu-id="61b27-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="61b27-329">파일</span><span class="sxs-lookup"><span data-stu-id="61b27-329">fileName</span></span> | <span data-ttu-id="61b27-330">엔터티Type이 *파일인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-330">Available if entityType is *File*.</span></span><br><span data-ttu-id="61b27-331">파일 또는 프로세스와 연결된 경고의 파일 이름</span><span class="sxs-lookup"><span data-stu-id="61b27-331">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="61b27-332">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="61b27-332">Detector.UnitTests.dll</span></span>
<span data-ttu-id="61b27-333">파일 경로</span><span class="sxs-lookup"><span data-stu-id="61b27-333">filePath</span></span> | <span data-ttu-id="61b27-334">엔터티Type이 *파일인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-334">Available if entityType is *File*.</span></span><br><span data-ttu-id="61b27-335">파일 또는 프로세스와 연결된 경고에 대한 파일 경로</span><span class="sxs-lookup"><span data-stu-id="61b27-335">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="61b27-336">C: \\ \agent_work_temp\배포\시스템\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="61b27-336">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="61b27-337">프로세스Id</span><span class="sxs-lookup"><span data-stu-id="61b27-337">processId</span></span> | <span data-ttu-id="61b27-338">엔터티Type이 *프로세스인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-338">Available if entityType is *Process*.</span></span> | <span data-ttu-id="61b27-339">24348</span><span class="sxs-lookup"><span data-stu-id="61b27-339">24348</span></span>
<span data-ttu-id="61b27-340">프로세스 커맨드라인</span><span class="sxs-lookup"><span data-stu-id="61b27-340">processCommandLine</span></span> | <span data-ttu-id="61b27-341">엔터티Type이 *프로세스인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-341">Available if entityType is *Process*.</span></span> | <span data-ttu-id="61b27-342">"파일은1911150169.exe 다운로드할 준비가 \_ 되었습니다."</span><span class="sxs-lookup"><span data-stu-id="61b27-342">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="61b27-343">프로세스창조시간</span><span class="sxs-lookup"><span data-stu-id="61b27-343">processCreationTime</span></span> | <span data-ttu-id="61b27-344">엔터티Type이 *프로세스인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-344">Available if entityType is *Process*.</span></span> | <span data-ttu-id="61b27-345">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="61b27-345">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="61b27-346">부모 프로세스Id</span><span class="sxs-lookup"><span data-stu-id="61b27-346">parentProcessId</span></span> | <span data-ttu-id="61b27-347">엔터티Type이 *프로세스인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-347">Available if entityType is *Process*.</span></span> | <span data-ttu-id="61b27-348">16840</span><span class="sxs-lookup"><span data-stu-id="61b27-348">16840</span></span>
<span data-ttu-id="61b27-349">부모 프로세스 창조시간</span><span class="sxs-lookup"><span data-stu-id="61b27-349">parentProcessCreationTime</span></span> | <span data-ttu-id="61b27-350">엔터티Type이 *프로세스인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-350">Available if entityType is *Process*.</span></span> | <span data-ttu-id="61b27-351">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="61b27-351">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="61b27-352">ipAddress</span><span class="sxs-lookup"><span data-stu-id="61b27-352">ipAddress</span></span> | <span data-ttu-id="61b27-353">엔터티Type이 Ip인 경우 사용할 수 *있습니다.*</span><span class="sxs-lookup"><span data-stu-id="61b27-353">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="61b27-354">*악성 네트워크 대상에* 대한 통신과 같은 네트워크 이벤트와 관련된 경고에 대한 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-354">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="61b27-355">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="61b27-355">62.216.203.204</span></span>
<span data-ttu-id="61b27-356">URL</span><span class="sxs-lookup"><span data-stu-id="61b27-356">url</span></span> | <span data-ttu-id="61b27-357">엔터티Type이 *URL인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-357">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="61b27-358">*악성 네트워크 대상에* 대한 통신과 같은 네트워크 이벤트와 관련된 경고에 대한 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-358">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="61b27-359">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="61b27-359">down.esales360.cn</span></span>
<span data-ttu-id="61b27-360">계정 이름</span><span class="sxs-lookup"><span data-stu-id="61b27-360">accountName</span></span> | <span data-ttu-id="61b27-361">엔터티Type이 *사용자인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-361">Available if entityType is *User*.</span></span> | <span data-ttu-id="61b27-362">testUser2</span><span class="sxs-lookup"><span data-stu-id="61b27-362">testUser2</span></span>
<span data-ttu-id="61b27-363">도메인 이름</span><span class="sxs-lookup"><span data-stu-id="61b27-363">domainName</span></span> | <span data-ttu-id="61b27-364">엔터티Type이 *사용자인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-364">Available if entityType is *User*.</span></span> | <span data-ttu-id="61b27-365">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="61b27-365">europe.corp.contoso</span></span>
<span data-ttu-id="61b27-366">사용자 시드</span><span class="sxs-lookup"><span data-stu-id="61b27-366">userSid</span></span> | <span data-ttu-id="61b27-367">엔터티Type이 *사용자인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-367">Available if entityType is *User*.</span></span> | <span data-ttu-id="61b27-368">S-1-5-21-1721254763-462695806-153882281-4156657</span><span class="sxs-lookup"><span data-stu-id="61b27-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="61b27-369">아드두이지드</span><span class="sxs-lookup"><span data-stu-id="61b27-369">aadUserId</span></span> | <span data-ttu-id="61b27-370">엔터티Type이 *사용자인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-370">Available if entityType is *User*.</span></span> | <span data-ttu-id="61b27-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="61b27-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="61b27-372">사용자PrincipalName</span><span class="sxs-lookup"><span data-stu-id="61b27-372">userPrincipalName</span></span> | <span data-ttu-id="61b27-373">엔터티Type이 *사용자* / *사서함* / *사서메시지인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-373">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="61b27-374">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b27-374">testUser2@contoso.com</span></span>
<span data-ttu-id="61b27-375">사서함디스플레이이름</span><span class="sxs-lookup"><span data-stu-id="61b27-375">mailboxDisplayName</span></span> | <span data-ttu-id="61b27-376">엔터티Type이 *사서함인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-376">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="61b27-377">테스트 사용자2</span><span class="sxs-lookup"><span data-stu-id="61b27-377">test User2</span></span>
<span data-ttu-id="61b27-378">사서함 주소 지정</span><span class="sxs-lookup"><span data-stu-id="61b27-378">mailboxAddress</span></span> | <span data-ttu-id="61b27-379">엔터티Type이 *사용자* / *사서함* / *사서메시지인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-379">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="61b27-380">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b27-380">testUser2@contoso.com</span></span>
<span data-ttu-id="61b27-381">클러스터바이</span><span class="sxs-lookup"><span data-stu-id="61b27-381">clusterBy</span></span> | <span data-ttu-id="61b27-382">엔터티Type이  *메일클러스터인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-382">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="61b27-383">주제; P2센더도메인; 콘텐츠 유형</span><span class="sxs-lookup"><span data-stu-id="61b27-383">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="61b27-384">보낸 사람</span><span class="sxs-lookup"><span data-stu-id="61b27-384">sender</span></span> | <span data-ttu-id="61b27-385">엔터티Type이 *사용자* / *사서함* / *사서메시지인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-385">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="61b27-386">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="61b27-386">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="61b27-387">받는 사람</span><span class="sxs-lookup"><span data-stu-id="61b27-387">recipient</span></span> | <span data-ttu-id="61b27-388">엔터티Type이 *메일메시지인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-388">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="61b27-389">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b27-389">testUser2@contoso.com</span></span>
<span data-ttu-id="61b27-390">subject</span><span class="sxs-lookup"><span data-stu-id="61b27-390">subject</span></span> | <span data-ttu-id="61b27-391">엔터티Type이 *메일메시지인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-391">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="61b27-392">\[외부 \] 주의</span><span class="sxs-lookup"><span data-stu-id="61b27-392">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="61b27-393">배달 조치</span><span class="sxs-lookup"><span data-stu-id="61b27-393">deliveryAction</span></span> | <span data-ttu-id="61b27-394">엔터티Type이 *메일메시지인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-394">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="61b27-395">배달</span><span class="sxs-lookup"><span data-stu-id="61b27-395">Delivered</span></span>
<span data-ttu-id="61b27-396">보안 그룹Id</span><span class="sxs-lookup"><span data-stu-id="61b27-396">securityGroupId</span></span> | <span data-ttu-id="61b27-397">엔터티Type이  *보안 그룹인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-397">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="61b27-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="61b27-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="61b27-399">보안 그룹 이름</span><span class="sxs-lookup"><span data-stu-id="61b27-399">securityGroupName</span></span> | <span data-ttu-id="61b27-400">엔터티Type이  *보안 그룹인* 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-400">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="61b27-401">네트워크 구성 연산자</span><span class="sxs-lookup"><span data-stu-id="61b27-401">Network Configuration Operators</span></span>
<span data-ttu-id="61b27-402">레지스트리하이브</span><span class="sxs-lookup"><span data-stu-id="61b27-402">registryHive</span></span> | <span data-ttu-id="61b27-403">엔터티Type이 레지스트리인 경우 사용할 수 *있습니다.*</span><span class="sxs-lookup"><span data-stu-id="61b27-403">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="61b27-404">HKEY \_ 로컬 \_ 기계</span><span class="sxs-lookup"><span data-stu-id="61b27-404">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="61b27-405">레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="61b27-405">registryKey</span></span> | <span data-ttu-id="61b27-406">엔터티Type이 레지스트리인 경우 사용할 수 *있습니다.*</span><span class="sxs-lookup"><span data-stu-id="61b27-406">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="61b27-407">소프트웨어\마이크로소프트\Windows NT\현재버전\윈로곤</span><span class="sxs-lookup"><span data-stu-id="61b27-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="61b27-408">레지스트리 값 유형</span><span class="sxs-lookup"><span data-stu-id="61b27-408">registryValueType</span></span> | <span data-ttu-id="61b27-409">엔터티Type이 레지스트리인 경우 사용할 수 *있습니다.*</span><span class="sxs-lookup"><span data-stu-id="61b27-409">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="61b27-410">문자열</span><span class="sxs-lookup"><span data-stu-id="61b27-410">String</span></span>
<span data-ttu-id="61b27-411">레지스트리값</span><span class="sxs-lookup"><span data-stu-id="61b27-411">registryValue</span></span> | <span data-ttu-id="61b27-412">엔터티Type이 레지스트리인 경우 사용할 수 *있습니다.*</span><span class="sxs-lookup"><span data-stu-id="61b27-412">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="61b27-413">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="61b27-413">31-00-00-00</span></span>
<span data-ttu-id="61b27-414">장치Id</span><span class="sxs-lookup"><span data-stu-id="61b27-414">deviceId</span></span> | <span data-ttu-id="61b27-415">엔터티와 관련된 장치의 ID(있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="61b27-415">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="61b27-416">986e5df8b73dacd43c8917e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="61b27-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="61b27-417">예제</span><span class="sxs-lookup"><span data-stu-id="61b27-417">Example</span></span>

<span data-ttu-id="61b27-418">**요청**</span><span class="sxs-lookup"><span data-stu-id="61b27-418">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="61b27-419">**응답**</span><span class="sxs-lookup"><span data-stu-id="61b27-419">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="61b27-420">관련 문서</span><span class="sxs-lookup"><span data-stu-id="61b27-420">Related articles</span></span>

- [<span data-ttu-id="61b27-421">Microsoft 365 수비수 API에 액세스</span><span class="sxs-lookup"><span data-stu-id="61b27-421">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="61b27-422">API 제한 및 라이선스에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="61b27-422">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="61b27-423">오류 코드 이해</span><span class="sxs-lookup"><span data-stu-id="61b27-423">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="61b27-424">인시던트 개요</span><span class="sxs-lookup"><span data-stu-id="61b27-424">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="61b27-425">인시던트 API</span><span class="sxs-lookup"><span data-stu-id="61b27-425">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="61b27-426">인시던트 API 업데이트</span><span class="sxs-lookup"><span data-stu-id="61b27-426">Update incident API</span></span>](api-update-incidents.md)
