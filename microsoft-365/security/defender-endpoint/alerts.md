---
title: 알림 표시 API
description: 끝점용 Microsoft Defender의 경고 리소스 유형의 메서드 및 속성에 대해 자세히 알아보습니다.
keywords: api, 그래프 api, 지원되는 api, get, alerts, recent
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
ms.openlocfilehash: 4997d7118b139d993ed94ed917137ca107940e46
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199624"
---
# <a name="alert-resource-type"></a><span data-ttu-id="3f95e-104">경고 리소스 유형</span><span class="sxs-lookup"><span data-stu-id="3f95e-104">Alert resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3f95e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="3f95e-105">**Applies to:**</span></span>
- [<span data-ttu-id="3f95e-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3f95e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="3f95e-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="3f95e-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3f95e-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a><span data-ttu-id="3f95e-109">메서드</span><span class="sxs-lookup"><span data-stu-id="3f95e-109">Methods</span></span>

<span data-ttu-id="3f95e-110">메서드</span><span class="sxs-lookup"><span data-stu-id="3f95e-110">Method</span></span> |<span data-ttu-id="3f95e-111">반환 형식</span><span class="sxs-lookup"><span data-stu-id="3f95e-111">Return Type</span></span> |<span data-ttu-id="3f95e-112">설명</span><span class="sxs-lookup"><span data-stu-id="3f95e-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="3f95e-113">알림 표시</span><span class="sxs-lookup"><span data-stu-id="3f95e-113">Get alert</span></span>](get-alert-info-by-id.md) | [<span data-ttu-id="3f95e-114">경고</span><span class="sxs-lookup"><span data-stu-id="3f95e-114">Alert</span></span>](alerts.md) | <span data-ttu-id="3f95e-115">단일 경고 [개체를](alerts.md) 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-115">Get a single [alert](alerts.md) object.</span></span>
[<span data-ttu-id="3f95e-116">목록 알림</span><span class="sxs-lookup"><span data-stu-id="3f95e-116">List alerts</span></span>](get-alerts.md) | <span data-ttu-id="3f95e-117">[경고](alerts.md) 컬렉션</span><span class="sxs-lookup"><span data-stu-id="3f95e-117">[Alert](alerts.md) collection</span></span> | <span data-ttu-id="3f95e-118">경고 [컬렉션을 나열합니다.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="3f95e-118">List [alert](alerts.md) collection.</span></span>
[<span data-ttu-id="3f95e-119">업데이트 경고</span><span class="sxs-lookup"><span data-stu-id="3f95e-119">Update alert</span></span>](update-alert.md) | [<span data-ttu-id="3f95e-120">경고</span><span class="sxs-lookup"><span data-stu-id="3f95e-120">Alert</span></span>](alerts.md) | <span data-ttu-id="3f95e-121">특정 경고를 [업데이트합니다.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="3f95e-121">Update specific [alert](alerts.md).</span></span>
[<span data-ttu-id="3f95e-122">일괄 업데이트 경고</span><span class="sxs-lookup"><span data-stu-id="3f95e-122">Batch update alerts</span></span>](batch-update-alerts.md) | | <span data-ttu-id="3f95e-123">경고 일괄 [업데이트](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="3f95e-123">Update a batch of [alerts](alerts.md).</span></span>
[<span data-ttu-id="3f95e-124">경고 만들기</span><span class="sxs-lookup"><span data-stu-id="3f95e-124">Create alert</span></span>](create-alert-by-reference.md)|[<span data-ttu-id="3f95e-125">경고</span><span class="sxs-lookup"><span data-stu-id="3f95e-125">Alert</span></span>](alerts.md)|<span data-ttu-id="3f95e-126">고급 헌팅에서 얻은 이벤트 데이터를 기반으로 [경고를 생성합니다.](run-advanced-query-api.md)</span><span class="sxs-lookup"><span data-stu-id="3f95e-126">Create an alert based on event data obtained from [Advanced Hunting](run-advanced-query-api.md).</span></span>
[<span data-ttu-id="3f95e-127">관련 도메인 목록</span><span class="sxs-lookup"><span data-stu-id="3f95e-127">List related domains</span></span>](get-alert-related-domain-info.md)|<span data-ttu-id="3f95e-128">도메인 컬렉션</span><span class="sxs-lookup"><span data-stu-id="3f95e-128">Domain collection</span></span>| <span data-ttu-id="3f95e-129">경고와 연결된 URL을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-129">List URLs associated with the alert.</span></span>
[<span data-ttu-id="3f95e-130">관련 파일 목록</span><span class="sxs-lookup"><span data-stu-id="3f95e-130">List related files</span></span>](get-alert-related-files-info.md) | <span data-ttu-id="3f95e-131">[파일](files.md) 모음</span><span class="sxs-lookup"><span data-stu-id="3f95e-131">[File](files.md) collection</span></span> |  <span data-ttu-id="3f95e-132">경고와 [](files.md) 연결된 파일 엔터티를 [나열합니다.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="3f95e-132">List the [file](files.md) entities that are associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="3f95e-133">관련 IPS 목록</span><span class="sxs-lookup"><span data-stu-id="3f95e-133">List related IPs</span></span>](get-alert-related-ip-info.md) | <span data-ttu-id="3f95e-134">IP 컬렉션</span><span class="sxs-lookup"><span data-stu-id="3f95e-134">IP collection</span></span> | <span data-ttu-id="3f95e-135">경고와 연결된 IPS를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-135">List IPs that are associated with the alert.</span></span>
[<span data-ttu-id="3f95e-136">관련 컴퓨터 얻기</span><span class="sxs-lookup"><span data-stu-id="3f95e-136">Get related machines</span></span>](get-alert-related-machine-info.md) | [<span data-ttu-id="3f95e-137">컴퓨터</span><span class="sxs-lookup"><span data-stu-id="3f95e-137">Machine</span></span>](machine.md) | <span data-ttu-id="3f95e-138">[경고와](machine.md) 연결된 [컴퓨터입니다.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="3f95e-138">The [machine](machine.md) that is associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="3f95e-139">관련 사용자 얻기</span><span class="sxs-lookup"><span data-stu-id="3f95e-139">Get related users</span></span>](get-alert-related-user-info.md) | [<span data-ttu-id="3f95e-140">사용자</span><span class="sxs-lookup"><span data-stu-id="3f95e-140">User</span></span>](user.md) | <span data-ttu-id="3f95e-141">[경고와](user.md) 연결된 [사용자입니다.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="3f95e-141">The [user](user.md) that is associated with the [alert](alerts.md).</span></span>


## <a name="properties"></a><span data-ttu-id="3f95e-142">속성</span><span class="sxs-lookup"><span data-stu-id="3f95e-142">Properties</span></span>

<span data-ttu-id="3f95e-143">속성</span><span class="sxs-lookup"><span data-stu-id="3f95e-143">Property</span></span> |    <span data-ttu-id="3f95e-144">유형</span><span class="sxs-lookup"><span data-stu-id="3f95e-144">Type</span></span>    |    <span data-ttu-id="3f95e-145">설명</span><span class="sxs-lookup"><span data-stu-id="3f95e-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="3f95e-146">id</span><span class="sxs-lookup"><span data-stu-id="3f95e-146">id</span></span> | <span data-ttu-id="3f95e-147">문자열</span><span class="sxs-lookup"><span data-stu-id="3f95e-147">String</span></span> | <span data-ttu-id="3f95e-148">경고 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-148">Alert ID.</span></span>
<span data-ttu-id="3f95e-149">title</span><span class="sxs-lookup"><span data-stu-id="3f95e-149">title</span></span> | <span data-ttu-id="3f95e-150">문자열</span><span class="sxs-lookup"><span data-stu-id="3f95e-150">String</span></span> | <span data-ttu-id="3f95e-151">경고 제목.</span><span class="sxs-lookup"><span data-stu-id="3f95e-151">Alert title.</span></span>
<span data-ttu-id="3f95e-152">설명</span><span class="sxs-lookup"><span data-stu-id="3f95e-152">description</span></span> | <span data-ttu-id="3f95e-153">문자열</span><span class="sxs-lookup"><span data-stu-id="3f95e-153">String</span></span> | <span data-ttu-id="3f95e-154">경고 설명.</span><span class="sxs-lookup"><span data-stu-id="3f95e-154">Alert description.</span></span>
<span data-ttu-id="3f95e-155">alertCreationTime</span><span class="sxs-lookup"><span data-stu-id="3f95e-155">alertCreationTime</span></span> | <span data-ttu-id="3f95e-156">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="3f95e-156">Nullable DateTimeOffset</span></span> | <span data-ttu-id="3f95e-157">경고가 만들어진 날짜 및 시간(UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-157">The date and time (in UTC) the alert was created.</span></span>
<span data-ttu-id="3f95e-158">lastEventTime</span><span class="sxs-lookup"><span data-stu-id="3f95e-158">lastEventTime</span></span> | <span data-ttu-id="3f95e-159">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="3f95e-159">Nullable DateTimeOffset</span></span> | <span data-ttu-id="3f95e-160">동일한 장치에서 경고를 트리거한 이벤트의 마지막 발생입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-160">The last occurrence of the event that triggered the alert on the same device.</span></span>
<span data-ttu-id="3f95e-161">firstEventTime</span><span class="sxs-lookup"><span data-stu-id="3f95e-161">firstEventTime</span></span> | <span data-ttu-id="3f95e-162">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="3f95e-162">Nullable DateTimeOffset</span></span> | <span data-ttu-id="3f95e-163">해당 디바이스에서 경고를 트리거한 이벤트의 첫 번째 발생입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-163">The first occurrence of the event that triggered the alert on that device.</span></span>
<span data-ttu-id="3f95e-164">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="3f95e-164">lastUpdateTime</span></span> | <span data-ttu-id="3f95e-165">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="3f95e-165">Nullable DateTimeOffset</span></span> | <span data-ttu-id="3f95e-166">경고가 마지막으로 업데이트된 날짜 및 시간(UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-166">The date and time (in UTC) the alert was last updated.</span></span>
<span data-ttu-id="3f95e-167">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="3f95e-167">resolvedTime</span></span> | <span data-ttu-id="3f95e-168">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="3f95e-168">Nullable DateTimeOffset</span></span> | <span data-ttu-id="3f95e-169">경고 상태가 '해결'으로 변경된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-169">The date and time in which the status of the alert was changed to 'Resolved'.</span></span>
<span data-ttu-id="3f95e-170">incidentId</span><span class="sxs-lookup"><span data-stu-id="3f95e-170">incidentId</span></span> | <span data-ttu-id="3f95e-171">Nullable Long</span><span class="sxs-lookup"><span data-stu-id="3f95e-171">Nullable Long</span></span> | <span data-ttu-id="3f95e-172">경고의 [인시던트](view-incidents-queue.md) ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-172">The [Incident](view-incidents-queue.md) ID of the Alert.</span></span>
<span data-ttu-id="3f95e-173">investigationId</span><span class="sxs-lookup"><span data-stu-id="3f95e-173">investigationId</span></span> | <span data-ttu-id="3f95e-174">Nullable Long</span><span class="sxs-lookup"><span data-stu-id="3f95e-174">Nullable Long</span></span> | <span data-ttu-id="3f95e-175">[경고와](automated-investigations.md) 관련된 조사 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-175">The [Investigation](automated-investigations.md) ID related to the Alert.</span></span>
<span data-ttu-id="3f95e-176">investigationState</span><span class="sxs-lookup"><span data-stu-id="3f95e-176">investigationState</span></span> | <span data-ttu-id="3f95e-177">Nullable Enum</span><span class="sxs-lookup"><span data-stu-id="3f95e-177">Nullable Enum</span></span> | <span data-ttu-id="3f95e-178">조사의 현재 [상태입니다.](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="3f95e-178">The current state of the [Investigation](automated-investigations.md).</span></span> <span data-ttu-id="3f95e-179">가능한 값은 '알 수 없음', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span><span class="sxs-lookup"><span data-stu-id="3f95e-179">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="3f95e-180">assignedTo</span><span class="sxs-lookup"><span data-stu-id="3f95e-180">assignedTo</span></span> | <span data-ttu-id="3f95e-181">문자열</span><span class="sxs-lookup"><span data-stu-id="3f95e-181">String</span></span> | <span data-ttu-id="3f95e-182">경고의 소유자입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-182">Owner of the alert.</span></span>
<span data-ttu-id="3f95e-183">심각도</span><span class="sxs-lookup"><span data-stu-id="3f95e-183">severity</span></span> | <span data-ttu-id="3f95e-184">Enum</span><span class="sxs-lookup"><span data-stu-id="3f95e-184">Enum</span></span> | <span data-ttu-id="3f95e-185">경고의 심각도입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-185">Severity of the alert.</span></span> <span data-ttu-id="3f95e-186">가능한 값은 'UnSpecified', 'Informational', 'Low', 'Medium' 및 'High'입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-186">Possible values are: 'UnSpecified', 'Informational', 'Low', 'Medium' and 'High'.</span></span>
<span data-ttu-id="3f95e-187">status</span><span class="sxs-lookup"><span data-stu-id="3f95e-187">status</span></span> | <span data-ttu-id="3f95e-188">Enum</span><span class="sxs-lookup"><span data-stu-id="3f95e-188">Enum</span></span> | <span data-ttu-id="3f95e-189">경고의 현재 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-189">Specifies the current status of the alert.</span></span> <span data-ttu-id="3f95e-190">가능한 값은 '알 수 없음', '신규', 'InProgress' 및 'Resolved'입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-190">Possible values are: 'Unknown', 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="3f95e-191">classification</span><span class="sxs-lookup"><span data-stu-id="3f95e-191">classification</span></span> | <span data-ttu-id="3f95e-192">Nullable Enum</span><span class="sxs-lookup"><span data-stu-id="3f95e-192">Nullable Enum</span></span> | <span data-ttu-id="3f95e-193">경고 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-193">Specification of the alert.</span></span> <span data-ttu-id="3f95e-194">가능한 값은 '알 수 없음', 'FalsePositive', 'TruePositive'입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-194">Possible values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span>
<span data-ttu-id="3f95e-195">determination</span><span class="sxs-lookup"><span data-stu-id="3f95e-195">determination</span></span> | <span data-ttu-id="3f95e-196">Nullable Enum</span><span class="sxs-lookup"><span data-stu-id="3f95e-196">Nullable Enum</span></span> | <span data-ttu-id="3f95e-197">경고 결정</span><span class="sxs-lookup"><span data-stu-id="3f95e-197">Specifies the determination of the alert.</span></span> <span data-ttu-id="3f95e-198">가능한 값은 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-198">Possible values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.</span></span>
<span data-ttu-id="3f95e-199">category</span><span class="sxs-lookup"><span data-stu-id="3f95e-199">category</span></span>| <span data-ttu-id="3f95e-200">문자열</span><span class="sxs-lookup"><span data-stu-id="3f95e-200">String</span></span> | <span data-ttu-id="3f95e-201">경고 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-201">Category of the alert.</span></span>
<span data-ttu-id="3f95e-202">detectionSource</span><span class="sxs-lookup"><span data-stu-id="3f95e-202">detectionSource</span></span> | <span data-ttu-id="3f95e-203">문자열</span><span class="sxs-lookup"><span data-stu-id="3f95e-203">String</span></span> | <span data-ttu-id="3f95e-204">검색 원본.</span><span class="sxs-lookup"><span data-stu-id="3f95e-204">Detection source.</span></span>
<span data-ttu-id="3f95e-205">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="3f95e-205">threatFamilyName</span></span> | <span data-ttu-id="3f95e-206">문자열</span><span class="sxs-lookup"><span data-stu-id="3f95e-206">String</span></span> | <span data-ttu-id="3f95e-207">위협 패밀리.</span><span class="sxs-lookup"><span data-stu-id="3f95e-207">Threat family.</span></span>
<span data-ttu-id="3f95e-208">threatName</span><span class="sxs-lookup"><span data-stu-id="3f95e-208">threatName</span></span> | <span data-ttu-id="3f95e-209">문자열</span><span class="sxs-lookup"><span data-stu-id="3f95e-209">String</span></span> | <span data-ttu-id="3f95e-210">위협 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-210">Threat name.</span></span>
<span data-ttu-id="3f95e-211">machineId</span><span class="sxs-lookup"><span data-stu-id="3f95e-211">machineId</span></span> | <span data-ttu-id="3f95e-212">문자열</span><span class="sxs-lookup"><span data-stu-id="3f95e-212">String</span></span> | <span data-ttu-id="3f95e-213">경고와 [연결된](machine.md) 컴퓨터 엔터티의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-213">ID of a [machine](machine.md) entity that is associated with the alert.</span></span>
<span data-ttu-id="3f95e-214">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="3f95e-214">computerDnsName</span></span> | <span data-ttu-id="3f95e-215">문자열</span><span class="sxs-lookup"><span data-stu-id="3f95e-215">String</span></span> | <span data-ttu-id="3f95e-216">[컴퓨터의](machine.md) 정식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-216">[machine](machine.md) fully qualified name.</span></span>
<span data-ttu-id="3f95e-217">aadTenantId</span><span class="sxs-lookup"><span data-stu-id="3f95e-217">aadTenantId</span></span> | <span data-ttu-id="3f95e-218">문자열</span><span class="sxs-lookup"><span data-stu-id="3f95e-218">String</span></span> | <span data-ttu-id="3f95e-219">Azure Active Directory ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-219">The Azure Active Directory ID.</span></span>
<span data-ttu-id="3f95e-220">detectorId</span><span class="sxs-lookup"><span data-stu-id="3f95e-220">detectorId</span></span> | <span data-ttu-id="3f95e-221">문자열</span><span class="sxs-lookup"><span data-stu-id="3f95e-221">String</span></span> | <span data-ttu-id="3f95e-222">경고를 트리거한 감지기 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-222">The ID of the detector that triggered the alert.</span></span>
<span data-ttu-id="3f95e-223">설명</span><span class="sxs-lookup"><span data-stu-id="3f95e-223">comments</span></span> | <span data-ttu-id="3f95e-224">경고 설명 목록</span><span class="sxs-lookup"><span data-stu-id="3f95e-224">List of Alert comments</span></span> | <span data-ttu-id="3f95e-225">Alert Comment 개체에는 주석 문자열, createdBy 문자열 및 createTime 날짜 시간이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-225">Alert Comment object contains: comment string, createdBy string and createTime date time.</span></span>
<span data-ttu-id="3f95e-226">증거</span><span class="sxs-lookup"><span data-stu-id="3f95e-226">Evidence</span></span> | <span data-ttu-id="3f95e-227">경고 증거 목록</span><span class="sxs-lookup"><span data-stu-id="3f95e-227">List of Alert evidence</span></span> | <span data-ttu-id="3f95e-228">경고와 관련된 증거입니다.</span><span class="sxs-lookup"><span data-stu-id="3f95e-228">Evidence related to the alert.</span></span> <span data-ttu-id="3f95e-229">아래 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f95e-229">See example below.</span></span>

### <a name="response-example-for-getting-single-alert"></a><span data-ttu-id="3f95e-230">단일 경고를 표시하는 응답 예:</span><span class="sxs-lookup"><span data-stu-id="3f95e-230">Response example for getting single alert:</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
{
    "id": "da637472900382838869_1364969609",
    "incidentId": 1126093,
    "investigationId": null,
    "assignedTo": null,
    "severity": "Low",
    "status": "New",
    "classification": null,
    "determination": null,
    "investigationState": "Queued",
    "detectionSource": "WindowsDefenderAtp",
    "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
    "category": "Execution",
    "threatFamilyName": null,
    "title": "Low-reputation arbitrary code executed by signed executable",
    "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
    "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
    "firstEventTime": "2021-01-26T20:31:32.9562661Z",
    "lastEventTime": "2021-01-26T20:31:33.0577322Z",
    "lastUpdateTime": "2021-01-26T20:33:59.2Z",
    "resolvedTime": null,
    "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
    "computerDnsName": "temp123.middleeast.corp.microsoft.com",
    "rbacGroupName": "A",
    "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
    "threatName": null,
    "mitreTechniques": [
        "T1064",
        "T1085",
        "T1220"
    ],
    "relatedUser": {
        "userName": "temp123",
        "domainName": "MIDDLEEAST"
    },
    "comments": [
        {
            "comment": "test comment for docs",
            "createdBy": "secop123@contoso.com",
            "createdTime": "2021-01-26T01:00:37.8404534Z"
        }
    ],
    "evidence": [
        {
            "entityType": "User",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": null,
            "sha256": null,
            "fileName": null,
            "filePath": null,
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": "eranb",
            "domainName": "MIDDLEEAST",
            "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
            "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
            "userPrincipalName": "temp123@microsoft.com",
            "detectionStatus": null
        },
        {
            "entityType": "Process",
            "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
            "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
            "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
            "fileName": "rundll32.exe",
            "filePath": "C:\\Windows\\SysWOW64",
            "processId": 3276,
            "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
            "processCreationTime": "2021-01-26T20:31:32.9581596Z",
            "parentProcessId": 8420,
            "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
            "parentProcessFileName": "rundll32.exe",
            "parentProcessFilePath": "C:\\Windows\\System32",
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        },
        {
            "entityType": "File",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
            "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
            "fileName": "suspicious.dll",
            "filePath": "c:\\temp",
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        }
    ]
}
```
