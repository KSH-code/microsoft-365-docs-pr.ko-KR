---
title: Microsoft Threat Protection의 문제 해결 API 목록
description: Microsoft Threat Protection에서 문제 API를 나열 하는 방법 알아보기
keywords: 목록, 인시던트, 인시던트, api
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
ms.openlocfilehash: 54f5ba640ecc175e78c7087df8016e9b715f17f7
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775114"
---
# <a name="list-incidents-api-in-microsoft-threat-protection"></a><span data-ttu-id="21cc7-104">Microsoft Threat Protection의 문제 해결 API 목록</span><span class="sxs-lookup"><span data-stu-id="21cc7-104">List incidents API in Microsoft Threat Protection</span></span>

<span data-ttu-id="21cc7-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="21cc7-105">**Applies to:**</span></span>

- <span data-ttu-id="21cc7-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="21cc7-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21cc7-107">일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="21cc7-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="21cc7-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="21cc7-109">API 설명</span><span class="sxs-lookup"><span data-stu-id="21cc7-109">API description</span></span>

<span data-ttu-id="21cc7-110">인시던트 API를 사용 하면 인시던트를 정렬 하 여 우선 순위를 지정 하 고 의사 cybersecurity 응답을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-110">The Incident API allows you to sort through incidents to prioritize and create an informed cybersecurity response.</span></span> <span data-ttu-id="21cc7-111">이는 환경 보존 정책에서 지정한 시간 범위 내에서 장치, 전자 메일 계정 및 네트워크 사용자 로부터 플래그가 지정 된 인시던트 모음을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-111">It exposes a collection of incidents that were flagged from devices, email accounts, and users in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="21cc7-112">가장 최근 인시던트가 목록 맨 위에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="21cc7-113">각 인시던트에는 관련 된 경고의 배열과 관련 엔터티가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<br><span data-ttu-id="21cc7-114">이 API는 다음 **OData** 연산자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-114">The API supports the following **OData** operators:</span></span>
<br><span data-ttu-id="21cc7-115">```$filter``` 설정: ```lastUpdateTime``` , ```createdTime``` ```status``` 및 ```assignedTo``` 속성</span><span class="sxs-lookup"><span data-stu-id="21cc7-115">```$filter``` on: ```lastUpdateTime```, ```createdTime```, ```status``` and ```assignedTo``` properties.</span></span>
<br><span data-ttu-id="21cc7-116">```$top``` max 값 **100**</span><span class="sxs-lookup"><span data-stu-id="21cc7-116">```$top``` with max value of **100**</span></span>
<br>```$skip```

## <a name="limitations"></a><span data-ttu-id="21cc7-117">제한 사항</span><span class="sxs-lookup"><span data-stu-id="21cc7-117">Limitations</span></span>

1. <span data-ttu-id="21cc7-118">최대 페이지 크기는 **100 인시던트**입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="21cc7-119">최대 요청 속도는 **분당 50 통화** 이 고 **시간당 1500 통화**입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="21cc7-120">사용 권한</span><span class="sxs-lookup"><span data-stu-id="21cc7-120">Permissions</span></span>

<span data-ttu-id="21cc7-121">이 API를 호출 하려면 다음 사용 권한 중 하나가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="21cc7-122">사용 권한을 선택 하는 방법을 비롯 하 여 자세히 알아보려면 [Access Microsoft Threat Protection api](api-access.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21cc7-122">To learn more, including how to choose permissions, see [Access Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="21cc7-123">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="21cc7-123">Permission type</span></span> |   <span data-ttu-id="21cc7-124">사용 권한</span><span class="sxs-lookup"><span data-stu-id="21cc7-124">Permission</span></span>  |   <span data-ttu-id="21cc7-125">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="21cc7-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="21cc7-126">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="21cc7-126">Application</span></span> |   <span data-ttu-id="21cc7-127">보안 문제를 모두 읽고</span><span class="sxs-lookup"><span data-stu-id="21cc7-127">Incident.Read.All</span></span> | <span data-ttu-id="21cc7-128">' 모든 인시던트 읽기 '</span><span class="sxs-lookup"><span data-stu-id="21cc7-128">'Read all incidents'</span></span>
<span data-ttu-id="21cc7-129">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="21cc7-129">Application</span></span> |   <span data-ttu-id="21cc7-130">인시던트의 모든</span><span class="sxs-lookup"><span data-stu-id="21cc7-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="21cc7-131">' 모든 인시던트 읽기 및 쓰기 '</span><span class="sxs-lookup"><span data-stu-id="21cc7-131">'Read and write all incidents'</span></span>
<span data-ttu-id="21cc7-132">위임 됨 (회사 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="21cc7-132">Delegated (work or school account)</span></span> | <span data-ttu-id="21cc7-133">문제점. 읽기</span><span class="sxs-lookup"><span data-stu-id="21cc7-133">Incident.Read</span></span> | <span data-ttu-id="21cc7-134">' 인시던트 읽기 '</span><span class="sxs-lookup"><span data-stu-id="21cc7-134">'Read incidents'</span></span>
<span data-ttu-id="21cc7-135">위임 됨 (회사 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="21cc7-135">Delegated (work or school account)</span></span> | <span data-ttu-id="21cc7-136">인시던트-ReadWrite</span><span class="sxs-lookup"><span data-stu-id="21cc7-136">Incident.ReadWrite</span></span> | <span data-ttu-id="21cc7-137">' 인시던트 읽기 및 쓰기 '</span><span class="sxs-lookup"><span data-stu-id="21cc7-137">'Read and write incidents'</span></span>

> [!Note]
> <span data-ttu-id="21cc7-138">사용자 자격 증명을 사용 하 여 토큰을 가져올 때:</span><span class="sxs-lookup"><span data-stu-id="21cc7-138">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="21cc7-139">사용자에 게 포털의 인시던트에 대 한 보기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="21cc7-140">응답에는 사용자에 게 노출 되는 인시던트만 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="21cc7-141">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="21cc7-141">HTTP request</span></span>

```
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="21cc7-142">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="21cc7-142">Request headers</span></span>

<span data-ttu-id="21cc7-143">이름</span><span class="sxs-lookup"><span data-stu-id="21cc7-143">Name</span></span> | <span data-ttu-id="21cc7-144">유형</span><span class="sxs-lookup"><span data-stu-id="21cc7-144">Type</span></span> | <span data-ttu-id="21cc7-145">설명</span><span class="sxs-lookup"><span data-stu-id="21cc7-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="21cc7-146">권한 부여</span><span class="sxs-lookup"><span data-stu-id="21cc7-146">Authorization</span></span> | <span data-ttu-id="21cc7-147">문자열</span><span class="sxs-lookup"><span data-stu-id="21cc7-147">String</span></span> | <span data-ttu-id="21cc7-148">전달자 {토큰}.</span><span class="sxs-lookup"><span data-stu-id="21cc7-148">Bearer {token}.</span></span> <span data-ttu-id="21cc7-149">**필수**입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-149">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="21cc7-150">요청 본문</span><span class="sxs-lookup"><span data-stu-id="21cc7-150">Request body</span></span>
<span data-ttu-id="21cc7-151">없음</span><span class="sxs-lookup"><span data-stu-id="21cc7-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="21cc7-152">응답</span><span class="sxs-lookup"><span data-stu-id="21cc7-152">Response</span></span>
<span data-ttu-id="21cc7-153">성공한 경우이 메서드는 200 OK를 반환 하 고 응답 본문에 [인시던트](api-incident.md) 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-153">If successful, this method returns 200 OK, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="21cc7-154">스키마 매핑</span><span class="sxs-lookup"><span data-stu-id="21cc7-154">Schema mapping</span></span>

| <span data-ttu-id="21cc7-155">필드 이름</span><span class="sxs-lookup"><span data-stu-id="21cc7-155">Field name</span></span>                                | <span data-ttu-id="21cc7-156">설명</span><span class="sxs-lookup"><span data-stu-id="21cc7-156">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="21cc7-157">예제 값</span><span class="sxs-lookup"><span data-stu-id="21cc7-157">Example value</span></span>                                                                                                                                                                                                                                     |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="21cc7-158">**인시던트 메타 데이터**</span><span class="sxs-lookup"><span data-stu-id="21cc7-158">**Incident metadata**</span></span>                         |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="21cc7-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="21cc7-159">incidentId</span></span>                                | <span data-ttu-id="21cc7-160">인시던트를 나타내는 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-160">Unique identifier to represent the incident.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="21cc7-161">924565</span><span class="sxs-lookup"><span data-stu-id="21cc7-161">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="21cc7-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="21cc7-162">redirectIncidentId</span></span>                        | <span data-ttu-id="21cc7-163">인시던트 처리 논리의 일부로 사고가 다른 인시던트에 함께 그룹화 되는 경우에만 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span>                                                                                                                                                                                                                                                           | <span data-ttu-id="21cc7-164">924569</span><span class="sxs-lookup"><span data-stu-id="21cc7-164">924569</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="21cc7-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="21cc7-165">incidentName</span></span>                              | <span data-ttu-id="21cc7-166">모든 인시던트에 제공 되는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-166">String value available for every incident.</span></span>                                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="21cc7-167">랜 섬 웨어 활동</span><span class="sxs-lookup"><span data-stu-id="21cc7-167">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="21cc7-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="21cc7-168">createdTime</span></span>                               | <span data-ttu-id="21cc7-169">인시던트를 처음으로 만든 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-169">Time when incident was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                      | <span data-ttu-id="21cc7-170">2020-09-06T14:46:57.0733333 Z</span><span class="sxs-lookup"><span data-stu-id="21cc7-170">2020-09-06T14:46:57.0733333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="21cc7-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="21cc7-171">lastUpdateTime</span></span>                            | <span data-ttu-id="21cc7-172">백 엔드에서 인시던트를 마지막으로 업데이트 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-172">Time when incident was last updated at the backend.</span></span><br> <span data-ttu-id="21cc7-173">이 필드는 인시던트가 검색 되는 범위에 대해 request 매개 변수를 설정할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-173">This field can be used when setting the request parameter for the range of time that incidents are retrieved.</span></span>                                                                                                                                                                                                                      | <span data-ttu-id="21cc7-174">2020-09-06T14:46:57.29 Z</span><span class="sxs-lookup"><span data-stu-id="21cc7-174">2020-09-06T14:46:57.29Z</span></span>                                                                                                                                                                                                                           |
| <span data-ttu-id="21cc7-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="21cc7-175">assignedTo</span></span>                                | <span data-ttu-id="21cc7-176">인시던트의 소유자 이거나 소유자가 할당 되지 않은 경우 *null* 입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-176">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="21cc7-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="21cc7-177">secop2@contoso.com</span></span>                                                                                                                                                                                                |
| <span data-ttu-id="21cc7-178">유형을</span><span class="sxs-lookup"><span data-stu-id="21cc7-178">classification</span></span>                            | <span data-ttu-id="21cc7-179">인시던트에 대 한 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-179">The specification for the incident.</span></span> <span data-ttu-id="21cc7-180">속성 값은 *Unknown*, *FalsePositive*, *TruePositive* 입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span>                                                                                                                                                                                                                                                                           | <span data-ttu-id="21cc7-181">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="21cc7-181">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="21cc7-182">가져옴을</span><span class="sxs-lookup"><span data-stu-id="21cc7-182">determination</span></span>                             | <span data-ttu-id="21cc7-183">문제에 대 한 결정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="21cc7-184">속성 값은 *Notavailable*, *Apt*, *맬웨어*, *securitypersonnel*, *securitypersonnel*, *UnwantedSoftware*등입니다. *Other*</span><span class="sxs-lookup"><span data-stu-id="21cc7-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span>                                                                                                                                                                                                                | <span data-ttu-id="21cc7-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="21cc7-185">NotAvailable</span></span>                                                                                                                                                                                                                                      |
| <span data-ttu-id="21cc7-186">상태별</span><span class="sxs-lookup"><span data-stu-id="21cc7-186">status</span></span>                                    | <span data-ttu-id="21cc7-187">인시던트를 *활성*또는 *확인*된 것으로 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="21cc7-188">이를 통해 인시던트에 대 한 응답을 구성 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-188">This helps you organize and manage your response to incidents.</span></span>                                                                                                                                                                                                                                                                  | <span data-ttu-id="21cc7-189">활성</span><span class="sxs-lookup"><span data-stu-id="21cc7-189">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="21cc7-190">이상인</span><span class="sxs-lookup"><span data-stu-id="21cc7-190">severity</span></span>                                  | <span data-ttu-id="21cc7-191">자산에 미칠 수 있는 영향을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="21cc7-192">심각도가 높을수록 영향은 더 커집니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="21cc7-193">일반적으로 심각도가 높은 항목은 즉각적인 주의가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-193">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="21cc7-194">*정보용*, *Low*, \* Medium 및 *High*값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                | <span data-ttu-id="21cc7-195">보통</span><span class="sxs-lookup"><span data-stu-id="21cc7-195">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="21cc7-196">사이</span><span class="sxs-lookup"><span data-stu-id="21cc7-196">tags</span></span>                                      | <span data-ttu-id="21cc7-197">인시던트에 연결 된 사용자 지정 태그의 배열로, 인시던트 그룹에 공통 특성을 지정 하는 것을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span>                                                                                                                                                                                                                                                                  | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="21cc7-198">경고가</span><span class="sxs-lookup"><span data-stu-id="21cc7-198">alerts</span></span>                                    | <span data-ttu-id="21cc7-199">문제와 관련 된 모든 경고 및 기타 정보 (예: 경고에 포함 된 엔터티, 경고 원본)의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-199">Array of all the alerts related to the incident and other information, such as severity, entities that were involved in the alert, the source of the alerts.</span></span>                                                                                                                                                                                                                     | <span data-ttu-id="21cc7-200">\[\] (아래의 경고 필드에 대 한 세부 정보 참조)</span><span class="sxs-lookup"><span data-stu-id="21cc7-200">\[\] (see details on alert fields below)</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="21cc7-201">**경고 메타 데이터**</span><span class="sxs-lookup"><span data-stu-id="21cc7-201">**Alerts metadata**</span></span>                           |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="21cc7-202">Alertid로 변경</span><span class="sxs-lookup"><span data-stu-id="21cc7-202">alertId</span></span>                                   | <span data-ttu-id="21cc7-203">경고를 나타내는 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-203">Unique identifier to represent the alert</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="21cc7-204">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="21cc7-204">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>                                                                                                                                                                                                            |
| <span data-ttu-id="21cc7-205">incidentId</span><span class="sxs-lookup"><span data-stu-id="21cc7-205">incidentId</span></span>                                | <span data-ttu-id="21cc7-206">이 경고가 연결 된 인시던트를 나타내는 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-206">Unique identifier to represent the incident this alert is associated with</span></span>                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="21cc7-207">924565</span><span class="sxs-lookup"><span data-stu-id="21cc7-207">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="21cc7-208">servic</span><span class="sxs-lookup"><span data-stu-id="21cc7-208">serviceSource</span></span>                             | <span data-ttu-id="21cc7-209">Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP 또는 Office 365 ATP와 같은 알림을 보낸 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-209">Service that the alert originates from, such as Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, or Office 365 ATP.</span></span>                                                                                                                                                                                                                                                                     | <span data-ttu-id="21cc7-210">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="21cc7-210">MicrosoftCloudAppSecurity</span></span>                                                                                                                                                                                                                         |
| <span data-ttu-id="21cc7-211">creationTime</span><span class="sxs-lookup"><span data-stu-id="21cc7-211">creationTime</span></span>                              | <span data-ttu-id="21cc7-212">알림을 처음 만든 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-212">Time when alert was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="21cc7-213">2020-09-06T14:46:55.7182276 Z</span><span class="sxs-lookup"><span data-stu-id="21cc7-213">2020-09-06T14:46:55.7182276Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="21cc7-214">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="21cc7-214">lastUpdatedTime</span></span>                           | <span data-ttu-id="21cc7-215">백 엔드에서 경고가 마지막으로 업데이트 된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-215">Time when alert was last updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="21cc7-216">2020-09-06T14:46:57.2433333 Z</span><span class="sxs-lookup"><span data-stu-id="21cc7-216">2020-09-06T14:46:57.2433333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="21cc7-217">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="21cc7-217">resolvedTime</span></span>                              | <span data-ttu-id="21cc7-218">경고가 해결 된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-218">Time when alert was resolved.</span></span>                                                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="21cc7-219">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="21cc7-219">2020-09-10T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="21cc7-220">firstActivity</span><span class="sxs-lookup"><span data-stu-id="21cc7-220">firstActivity</span></span>                             | <span data-ttu-id="21cc7-221">경고 처음에 작업이 백 엔드에서 업데이트 되었음을 보고 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-221">Time when alert first reported that activity was updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="21cc7-222">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="21cc7-222">2020-09-04T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="21cc7-223">title</span><span class="sxs-lookup"><span data-stu-id="21cc7-223">title</span></span>                                     | <span data-ttu-id="21cc7-224">각 경고에 대해 사용할 수 있는 간단한 식별 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-224">Brief identifying string value available for each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="21cc7-225">랜 섬 웨어 활동</span><span class="sxs-lookup"><span data-stu-id="21cc7-225">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="21cc7-226">설명</span><span class="sxs-lookup"><span data-stu-id="21cc7-226">description</span></span>                               | <span data-ttu-id="21cc7-227">각 경고를 설명 하는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-227">String value describing each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="21cc7-228">사용자 테스트 (testUser2@contoso.com)는 여러 확장명을 포함 하는 99 파일을 흔히 사용 되지 않는 확장 *herunterladen*로 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-228">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="21cc7-229">이는 비정상적으로 발생 하는 파일 조작 수 이며 잠재적인 랜 섬 웨어 공격을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-229">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span> |
| <span data-ttu-id="21cc7-230">범주</span><span class="sxs-lookup"><span data-stu-id="21cc7-230">category</span></span>                                  | <span data-ttu-id="21cc7-231">Kill 체인을 따라 공격이 진행 된 정도에 대 한 시각적인 및 수치 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-231">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="21cc7-232">[MITRE at&t&접시 헤드™ 프레임 워크](https://attack.mitre.org/)에 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-232">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span>                                                                                                                                                                                                                           | <span data-ttu-id="21cc7-233">영향</span><span class="sxs-lookup"><span data-stu-id="21cc7-233">Impact</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="21cc7-234">상태별</span><span class="sxs-lookup"><span data-stu-id="21cc7-234">status</span></span>                                    | <span data-ttu-id="21cc7-235">알림을 *새*, *활성*또는 *확인*된 것으로 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-235">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="21cc7-236">이를 통해 경고에 대 한 응답을 구성 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-236">This helps you organize and manage your response to alerts.</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="21cc7-237">신규</span><span class="sxs-lookup"><span data-stu-id="21cc7-237">New</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="21cc7-238">이상인</span><span class="sxs-lookup"><span data-stu-id="21cc7-238">severity</span></span>                                  | <span data-ttu-id="21cc7-239">자산에 미칠 수 있는 영향을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-239">Indicates the possible impact on assets.</span></span> <span data-ttu-id="21cc7-240">심각도가 높을수록 영향은 더 커집니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-240">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="21cc7-241">일반적으로 심각도가 높은 항목은 즉각적인 주의가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-241">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="21cc7-242">*정보용*, *Low*, \* Medium 및 *High*값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-242">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                   | <span data-ttu-id="21cc7-243">보통</span><span class="sxs-lookup"><span data-stu-id="21cc7-243">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="21cc7-244">investigationId</span><span class="sxs-lookup"><span data-stu-id="21cc7-244">investigationId</span></span>                           | <span data-ttu-id="21cc7-245">이 경고에 의해 트리거되는 자동화 된 조사 id입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-245">The automated investigation id triggered by this alert.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="21cc7-246">1234</span><span class="sxs-lookup"><span data-stu-id="21cc7-246">1234</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="21cc7-247">investigationState</span><span class="sxs-lookup"><span data-stu-id="21cc7-247">investigationState</span></span>                        | <span data-ttu-id="21cc7-248">조사의 현재 상태에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-248">Information on the investigation's current status.</span></span> <span data-ttu-id="21cc7-249">*알 수 없음*, *종료*됨, *SuccessfullyRemediated*, *양성*, *실패*, *PartiallyRemediated*, *실행*, *pendingapproval*, *pendingapproval*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *대기*, *innerfailure*, *preexistingalert*, *UnsupportedOs*, *unsupportedalerttype*, *SuppressedAlert*중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-249">One of the following: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="21cc7-250">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="21cc7-250">UnsupportedAlertType</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="21cc7-251">유형을</span><span class="sxs-lookup"><span data-stu-id="21cc7-251">classification</span></span>                            | <span data-ttu-id="21cc7-252">인시던트에 대 한 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-252">The specification for the incident.</span></span> <span data-ttu-id="21cc7-253">속성 값은 *Unknown*, *FalsePositive*, *TruePositive* 또는 *null* 입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-253">The property values are: *Unknown*, *FalsePositive*, *TruePositive* or *null*</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="21cc7-254">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="21cc7-254">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="21cc7-255">가져옴을</span><span class="sxs-lookup"><span data-stu-id="21cc7-255">determination</span></span>                             | <span data-ttu-id="21cc7-256">문제에 대 한 결정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-256">Specifies the determination of the incident.</span></span> <span data-ttu-id="21cc7-257">속성 값은 *Notavailable*, *Apt*, *맬웨어*, *securitypersonnel*, *securitypersonnel*, *UnwantedSoftware*, *Other* 또는 *null* 입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-257">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="21cc7-258">Apt</span><span class="sxs-lookup"><span data-stu-id="21cc7-258">Apt</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="21cc7-259">assignedTo</span><span class="sxs-lookup"><span data-stu-id="21cc7-259">assignedTo</span></span>                                | <span data-ttu-id="21cc7-260">인시던트의 소유자 이거나 소유자가 할당 되지 않은 경우 *null* 입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-260">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                            | <span data-ttu-id="21cc7-261">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="21cc7-261">secop2@contoso.com</span></span>                                                                                                                                                                                                 |
| <span data-ttu-id="21cc7-262">actorName</span><span class="sxs-lookup"><span data-stu-id="21cc7-262">actorName</span></span>                                 | <span data-ttu-id="21cc7-263">이 경고와 연결 된 활동 그룹 (있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-263">The activity group, if any, the  associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="21cc7-264">BORON</span><span class="sxs-lookup"><span data-stu-id="21cc7-264">BORON</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="21cc7-265">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="21cc7-265">threatFamilyName</span></span>                          | <span data-ttu-id="21cc7-266">이 경고와 연결 된 위협 계열입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-266">Threat family associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="21cc7-267">null</span><span class="sxs-lookup"><span data-stu-id="21cc7-267">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="21cc7-268">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="21cc7-268">mitreTechniques</span></span>                           | <span data-ttu-id="21cc7-269">[MITRE at&t&접시 헤드](https://attack.mitre.org/)™ 프레임 워크에 맞춰진 공격 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-269">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span>                                                                                                                                                                                                                                                                                                                              | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="21cc7-270">장치</span><span class="sxs-lookup"><span data-stu-id="21cc7-270">devices</span></span>                                   | <span data-ttu-id="21cc7-271">인시던트와 관련 된 알림을 보낸 모든 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-271">All devices where alerts related to the incident were sent.</span></span>                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="21cc7-272">\[\] (아래 엔터티 필드에 대 한 세부 정보 참조)</span><span class="sxs-lookup"><span data-stu-id="21cc7-272">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="21cc7-273">**장치 형식**</span><span class="sxs-lookup"><span data-stu-id="21cc7-273">**Device format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="21cc7-274">DeviceId</span><span class="sxs-lookup"><span data-stu-id="21cc7-274">DeviceId</span></span>                                  | <span data-ttu-id="21cc7-275">Microsoft Defender ATP에 지정 된 장치 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-275">The device ID as designated in Microsoft Defender ATP.</span></span>                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="21cc7-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="21cc7-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="21cc7-277">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="21cc7-277">aadDeviceId</span></span>                               |  <span data-ttu-id="21cc7-278">AAD ( [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) )에 지정 된 장치 Id입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-278">The device Id as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD).</span></span> <span data-ttu-id="21cc7-279">도메인에 가입 된 장치에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-279">Only available for domain-joined devices.</span></span>                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="21cc7-280">null</span><span class="sxs-lookup"><span data-stu-id="21cc7-280">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="21cc7-281">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="21cc7-281">deviceDnsName</span></span>                             | <span data-ttu-id="21cc7-282">장치에 대 한 정규화 된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-282">The fully qualified domain name for the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="21cc7-283">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="21cc7-283">user5cx.middleeast.corp.contoso.com</span></span>                                                                                                                                                                                                    |
| <span data-ttu-id="21cc7-284">osPlatform</span><span class="sxs-lookup"><span data-stu-id="21cc7-284">osPlatform</span></span>                                | <span data-ttu-id="21cc7-285">장치가 실행 되 고 있는 OS 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-285">The OS platform the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="21cc7-286">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="21cc7-286">WindowsServer2016</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="21cc7-287">osBuild</span><span class="sxs-lookup"><span data-stu-id="21cc7-287">osBuild</span></span>                                   | <span data-ttu-id="21cc7-288">장치에서 실행 중인 OS의 빌드 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-288">The build version for the OS the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="21cc7-289">14393</span><span class="sxs-lookup"><span data-stu-id="21cc7-289">14393</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="21cc7-290">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="21cc7-290">rbacGroupName</span></span>                             | <span data-ttu-id="21cc7-291">장치와 연결 된 RBAC ( [역할 기반 액세스 제어](https://docs.microsoft.com/azure/role-based-access-control/overview) ) 그룹</span><span class="sxs-lookup"><span data-stu-id="21cc7-291">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="21cc7-292">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="21cc7-292">WDATP-Ring0</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="21cc7-293">firstSeen</span><span class="sxs-lookup"><span data-stu-id="21cc7-293">firstSeen</span></span>                                 | <span data-ttu-id="21cc7-294">장치를 처음으로 본 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-294">Time when device was first seen.</span></span>                                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="21cc7-295">2020-02-06-06T14:16:01.9330135 Z</span><span class="sxs-lookup"><span data-stu-id="21cc7-295">2020-02-06T14:16:01.9330135Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="21cc7-296">healthStatus</span><span class="sxs-lookup"><span data-stu-id="21cc7-296">healthStatus</span></span>                              | <span data-ttu-id="21cc7-297">장치의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-297">The health state of the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="21cc7-298">활성</span><span class="sxs-lookup"><span data-stu-id="21cc7-298">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="21cc7-299">riskScore</span><span class="sxs-lookup"><span data-stu-id="21cc7-299">riskScore</span></span>                                 | <span data-ttu-id="21cc7-300">장치에 대 한 위험 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-300">The risk score for the  device.</span></span>                                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="21cc7-301">높음</span><span class="sxs-lookup"><span data-stu-id="21cc7-301">High</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="21cc7-302">엔터티</span><span class="sxs-lookup"><span data-stu-id="21cc7-302">entities</span></span>                                  | <span data-ttu-id="21cc7-303">지정 된 경고에 포함 되거나 연결 되는 것으로 식별 된 모든 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-303">All entities that have been identified to be part of, or related to, a given alert.</span></span>                                                                                                                                                                                                                                                                                | <span data-ttu-id="21cc7-304">\[\] (아래 엔터티 필드에 대 한 세부 정보 참조)</span><span class="sxs-lookup"><span data-stu-id="21cc7-304">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="21cc7-305">**엔터티 형식**</span><span class="sxs-lookup"><span data-stu-id="21cc7-305">**Entity Format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="21cc7-306">이어야</span><span class="sxs-lookup"><span data-stu-id="21cc7-306">entityType</span></span>                                | <span data-ttu-id="21cc7-307">지정 된 경고에 포함 되거나이에 연결 되는 것으로 식별 된 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-307">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="21cc7-308">Properties 값은 *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *mailcluster*, *Registry* 입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-308">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="21cc7-309">사용자</span><span class="sxs-lookup"><span data-stu-id="21cc7-309">User</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="21cc7-310">sha1</span><span class="sxs-lookup"><span data-stu-id="21cc7-310">sha1</span></span>                                      | <span data-ttu-id="21cc7-311">EntityType이 *파일인*경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-311">Available if entityType is *File*.</span></span><br><span data-ttu-id="21cc7-312">파일 또는 프로세스와 연결 된 경고에 대 한 파일 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-312">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="21cc7-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="21cc7-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="21cc7-314">sha256</span><span class="sxs-lookup"><span data-stu-id="21cc7-314">sha256</span></span>                                    | <span data-ttu-id="21cc7-315">EntityType이 *파일인*경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-315">Available if entityType is *File*.</span></span><br><span data-ttu-id="21cc7-316">파일 또는 프로세스와 연결 된 경고에 대 한 파일 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-316">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="21cc7-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="21cc7-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>                                                                                                                                                                                  |
| <span data-ttu-id="21cc7-318">이름을</span><span class="sxs-lookup"><span data-stu-id="21cc7-318">fileName</span></span>                                  | <span data-ttu-id="21cc7-319">EntityType이 *파일인*경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-319">Available if entityType is *File*.</span></span><br><span data-ttu-id="21cc7-320">파일 또는 프로세스와 연결 된 알림의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-320">The file name for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="21cc7-321">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="21cc7-321">Detector.UnitTests.dll</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="21cc7-322">filePath</span><span class="sxs-lookup"><span data-stu-id="21cc7-322">filePath</span></span>                                  | <span data-ttu-id="21cc7-323">EntityType이 *파일인*경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-323">Available if entityType is *File*.</span></span><br><span data-ttu-id="21cc7-324">파일 또는 프로세스와 연결 된 경고의 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-324">The file path for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="21cc7-325">C: \\ \\ 에이전트 \\ \\ \_ 작업 \\ \\ \_ temp \\ \\ 배포 \_ 시스템 2020-09-06 12 \_ 14 \_ 54 \\ \\</span><span class="sxs-lookup"><span data-stu-id="21cc7-325">C:\\\\Agent\\\\\_work\\\\\_temp\\\\Deploy\_SYSTEM 2020-09-06 12\_14\_54\\\\Out</span></span>                                                                                                                                                                    |
| <span data-ttu-id="21cc7-326">processId</span><span class="sxs-lookup"><span data-stu-id="21cc7-326">processId</span></span>                                 | <span data-ttu-id="21cc7-327">EntityType이 *프로세스*인 경우 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-327">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="21cc7-328">24348</span><span class="sxs-lookup"><span data-stu-id="21cc7-328">24348</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="21cc7-329">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="21cc7-329">processCommandLine</span></span>                        | <span data-ttu-id="21cc7-330">EntityType이 *프로세스*인 경우 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-330">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="21cc7-331">" \\ " 파일 다운로드 준비 완료 \_1911150169.exe\\ ""</span><span class="sxs-lookup"><span data-stu-id="21cc7-331">"\\"Your File Is Ready To Download\_1911150169.exe\\" "</span></span>                                                                                                                                                                                           |
| <span data-ttu-id="21cc7-332">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="21cc7-332">processCreationTime</span></span>                       | <span data-ttu-id="21cc7-333">EntityType이 *프로세스*인 경우 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-333">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="21cc7-334">2020-07-18T03:25:38.5269993 Z</span><span class="sxs-lookup"><span data-stu-id="21cc7-334">2020-07-18T03:25:38.5269993Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="21cc7-335">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="21cc7-335">parentProcessId</span></span>                           | <span data-ttu-id="21cc7-336">EntityType이 *프로세스*인 경우 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-336">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="21cc7-337">16840</span><span class="sxs-lookup"><span data-stu-id="21cc7-337">16840</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="21cc7-338">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="21cc7-338">parentProcessCreationTime</span></span>                 | <span data-ttu-id="21cc7-339">EntityType이 *프로세스*인 경우 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-339">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="21cc7-340">2020-07-18T02:12:32.8616797 Z</span><span class="sxs-lookup"><span data-stu-id="21cc7-340">2020-07-18T02:12:32.8616797Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="21cc7-341">Address</span><span class="sxs-lookup"><span data-stu-id="21cc7-341">ipAddress</span></span>                                 | <span data-ttu-id="21cc7-342">EntityType이 *Ip*인 경우 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-342">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="21cc7-343">네트워크 이벤트에 연결 된 경고의 IP 주소 (예: *악의적인 네트워크 대상에 대 한 통신*)</span><span class="sxs-lookup"><span data-stu-id="21cc7-343">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                   | <span data-ttu-id="21cc7-344">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="21cc7-344">62.216.203.204</span></span>                                                                                                                                                                                                                                    |
| <span data-ttu-id="21cc7-345">url</span><span class="sxs-lookup"><span data-stu-id="21cc7-345">url</span></span>                                       | <span data-ttu-id="21cc7-346">EntityType이 *Url*인 경우 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-346">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="21cc7-347">네트워크 이벤트에 연결 된 경고의 Url (예: *악의적인 네트워크 대상에*대 한 통신)입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-347">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                  | <span data-ttu-id="21cc7-348">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="21cc7-348">down.esales360.cn</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="21cc7-349">계정</span><span class="sxs-lookup"><span data-stu-id="21cc7-349">accountName</span></span>                               | <span data-ttu-id="21cc7-350">EntityType 인 경우 사용 *가능 합니다.*</span><span class="sxs-lookup"><span data-stu-id="21cc7-350">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="21cc7-351">testUser2</span><span class="sxs-lookup"><span data-stu-id="21cc7-351">testUser2</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="21cc7-352">도메인</span><span class="sxs-lookup"><span data-stu-id="21cc7-352">domainName</span></span>                                | <span data-ttu-id="21cc7-353">EntityType 인 경우 사용 *가능 합니다.*</span><span class="sxs-lookup"><span data-stu-id="21cc7-353">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="21cc7-354">동유럽</span><span class="sxs-lookup"><span data-stu-id="21cc7-354">europe.corp.contoso</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="21cc7-355">userSid</span><span class="sxs-lookup"><span data-stu-id="21cc7-355">userSid</span></span>                                   | <span data-ttu-id="21cc7-356">EntityType 인 경우 사용 *가능 합니다.*</span><span class="sxs-lookup"><span data-stu-id="21cc7-356">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="21cc7-357">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="21cc7-357">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="21cc7-358">aadUserId</span><span class="sxs-lookup"><span data-stu-id="21cc7-358">aadUserId</span></span>                                 | <span data-ttu-id="21cc7-359">EntityType 인 경우 사용 *가능 합니다.*</span><span class="sxs-lookup"><span data-stu-id="21cc7-359">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="21cc7-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="21cc7-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="21cc7-361">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="21cc7-361">userPrincipalName</span></span>                         | <span data-ttu-id="21cc7-362">EntityType이 *사용자* / *사서함* / *MailMessage*경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-362">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="21cc7-363">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="21cc7-363">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="21cc7-364">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="21cc7-364">mailboxDisplayName</span></span>                        | <span data-ttu-id="21cc7-365">EntityType이 *사서함*인 경우 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-365">Available if entityType is *MailBox*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="21cc7-366">test%</span><span class="sxs-lookup"><span data-stu-id="21cc7-366">test User2</span></span>                                                                                                                                                                                                                                        |
| <span data-ttu-id="21cc7-367">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="21cc7-367">mailboxAddress</span></span>                            | <span data-ttu-id="21cc7-368">EntityType이 *사용자* / *사서함* / *MailMessage*경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-368">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="21cc7-369">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="21cc7-369">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="21cc7-370">clusterBy</span><span class="sxs-lookup"><span data-stu-id="21cc7-370">clusterBy</span></span>                                 | <span data-ttu-id="21cc7-371">EntityType이  *Mailcluster*인 경우 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-371">Available if entityType is  *MailCluster*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="21cc7-372">주체 P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="21cc7-372">Subject;P2SenderDomain;ContentType</span></span>                                                                                                                                                                                                                |
| <span data-ttu-id="21cc7-373">보낸 사람</span><span class="sxs-lookup"><span data-stu-id="21cc7-373">sender</span></span>                                    | <span data-ttu-id="21cc7-374">EntityType이 *사용자* / *사서함* / *MailMessage*경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-374">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="21cc7-375">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="21cc7-375">user.abc@mail.contoso.co.in</span></span>                                                                                                                                                                 |
| <span data-ttu-id="21cc7-376">받는 사람</span><span class="sxs-lookup"><span data-stu-id="21cc7-376">recipient</span></span>                                 | <span data-ttu-id="21cc7-377">EntityType이 *MailMessage*인 경우 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-377">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="21cc7-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="21cc7-378">testUser2@contoso.com</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="21cc7-379">subject</span><span class="sxs-lookup"><span data-stu-id="21cc7-379">subject</span></span>                                   | <span data-ttu-id="21cc7-380">EntityType이 *MailMessage*인 경우 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-380">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="21cc7-381">\[외부 \] 주의</span><span class="sxs-lookup"><span data-stu-id="21cc7-381">\[EXTERNAL\] Attention</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="21cc7-382">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="21cc7-382">deliveryAction</span></span>                            | <span data-ttu-id="21cc7-383">EntityType이 *MailMessage*인 경우 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-383">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="21cc7-384">배달</span><span class="sxs-lookup"><span data-stu-id="21cc7-384">Delivered</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="21cc7-385">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="21cc7-385">securityGroupId</span></span>                           | <span data-ttu-id="21cc7-386">EntityType이  *Securitygroup*인 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-386">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="21cc7-387">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="21cc7-387">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="21cc7-388">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="21cc7-388">securityGroupName</span></span>                         | <span data-ttu-id="21cc7-389">EntityType이  *Securitygroup*인 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-389">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="21cc7-390">네트워크 구성 운영자</span><span class="sxs-lookup"><span data-stu-id="21cc7-390">Network Configuration Operators</span></span>                                                                                                                                                                                                                   |
| <span data-ttu-id="21cc7-391">registryHive</span><span class="sxs-lookup"><span data-stu-id="21cc7-391">registryHive</span></span>                              | <span data-ttu-id="21cc7-392">EntityType이  *Registry*인 경우 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-392">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="21cc7-393">HKEY \_ 로컬 \_ 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="21cc7-393">HKEY\_LOCAL\_MACHINE</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="21cc7-394">registryKey</span><span class="sxs-lookup"><span data-stu-id="21cc7-394">registryKey</span></span>                               | <span data-ttu-id="21cc7-395">EntityType이  *Registry*인 경우 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-395">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="21cc7-396">소프트웨어 \\ \\ MICROSOFT \\ \\ Windows NT \\ \\ CurrentVersion \\ \\ Winlogon</span><span class="sxs-lookup"><span data-stu-id="21cc7-396">SOFTWARE\\\\Microsoft\\\\Windows NT\\\\CurrentVersion\\\\Winlogon</span></span>                                                                                                                                                                                 |
| <span data-ttu-id="21cc7-397">registryValueType</span><span class="sxs-lookup"><span data-stu-id="21cc7-397">registryValueType</span></span>                         | <span data-ttu-id="21cc7-398">EntityType이  *Registry*인 경우 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-398">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="21cc7-399">문자열</span><span class="sxs-lookup"><span data-stu-id="21cc7-399">String</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="21cc7-400">registryValue</span><span class="sxs-lookup"><span data-stu-id="21cc7-400">registryValue</span></span>                             | <span data-ttu-id="21cc7-401">EntityType이  *Registry*인 경우 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-401">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="21cc7-402">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="21cc7-402">31-00-00-00</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="21cc7-403">deviceId</span><span class="sxs-lookup"><span data-stu-id="21cc7-403">deviceId</span></span>                                  | <span data-ttu-id="21cc7-404">엔터티와 관련 된 장치의 ID (있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="21cc7-404">The ID, if any, of the device related to the entity.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="21cc7-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="21cc7-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>                                                                                                                                                                                                          |



## <a name="example"></a><span data-ttu-id="21cc7-406">예제</span><span class="sxs-lookup"><span data-stu-id="21cc7-406">Example</span></span>

<span data-ttu-id="21cc7-407">**요청이**</span><span class="sxs-lookup"><span data-stu-id="21cc7-407">**Request**</span></span>

```
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="21cc7-408">**응답률**</span><span class="sxs-lookup"><span data-stu-id="21cc7-408">**Response**</span></span>
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

## <a name="related-topic"></a><span data-ttu-id="21cc7-409">관련 항목</span><span class="sxs-lookup"><span data-stu-id="21cc7-409">Related topic</span></span>
- [<span data-ttu-id="21cc7-410">인시던트 Api</span><span class="sxs-lookup"><span data-stu-id="21cc7-410">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="21cc7-411">인시던트 업데이트</span><span class="sxs-lookup"><span data-stu-id="21cc7-411">Update incident</span></span>](api-update-incidents.md)
