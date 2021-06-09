---
title: 수정 작업 방법 및 속성
description: API 응답에는 테넌트에서 & 취약성 관리 수정 활동에 대한 위협이 포함되어 있습니다. 모든 재구성 활동, 수정 활동 하나만 또는 선택한 수정 작업에 대해 노출된 장치에 대한 정보를 요청할 수 있습니다.
keywords: api, 수정, 수정 api, get, 수정 작업, 수정 방법, 수정 속성,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 67009961ecc3755b5af21b2e773bc817ea46bec0
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769239"
---
# <a name="remediation-activity-methods-and-properties"></a><span data-ttu-id="049bd-105">수정 작업 방법 및 속성</span><span class="sxs-lookup"><span data-stu-id="049bd-105">Remediation activity methods and properties</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="049bd-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="049bd-106">**Applies to:**</span></span>

- [<span data-ttu-id="049bd-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="049bd-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="049bd-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="049bd-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="049bd-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="049bd-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="049bd-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="049bd-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="049bd-111">API 응답에는 [테넌트에서 & 취약성 관리](next-gen-threat-and-vuln-mgt.md)위협 요소 수정   활동이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="049bd-111">The API response contains [Threat & vulnerability management](next-gen-threat-and-vuln-mgt.md) remediation activities that have been created in your tenant.</span></span>  

## <a name="methods"></a><span data-ttu-id="049bd-112">메서드</span><span class="sxs-lookup"><span data-stu-id="049bd-112">Methods</span></span>

<span data-ttu-id="049bd-113">메서드</span><span class="sxs-lookup"><span data-stu-id="049bd-113">Method</span></span> | <span data-ttu-id="049bd-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="049bd-114">Data type</span></span> | <span data-ttu-id="049bd-115">설명</span><span class="sxs-lookup"><span data-stu-id="049bd-115">Description</span></span>
:---|:---|:---
[<span data-ttu-id="049bd-116">모든 수정 작업 나열s</span><span class="sxs-lookup"><span data-stu-id="049bd-116">List all remediation activities</span></span>](get-remediation-all-activities.md) | <span data-ttu-id="049bd-117">조사 컬렉션</span><span class="sxs-lookup"><span data-stu-id="049bd-117">Investigation collection</span></span> | <span data-ttu-id="049bd-118">모든 수정 활동에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="049bd-118">Returns information about all remediation activities.</span></span>
[<span data-ttu-id="049bd-119">한 번의 수정 작업이 있는 노출된 장치 목록</span><span class="sxs-lookup"><span data-stu-id="049bd-119">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md) | <span data-ttu-id="049bd-120">조사 엔터티</span><span class="sxs-lookup"><span data-stu-id="049bd-120">Investigation entity</span></span> | <span data-ttu-id="049bd-121">지정된 수정 활동에 대해 노출된 장치에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="049bd-121">Returns information about exposed devices for the specified remediation activity.</span></span>
[<span data-ttu-id="049bd-122">ID로 수정 작업 1개 가져오기</span><span class="sxs-lookup"><span data-stu-id="049bd-122">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md) | <span data-ttu-id="049bd-123">조사 엔터티</span><span class="sxs-lookup"><span data-stu-id="049bd-123">Investigation entity</span></span> | <span data-ttu-id="049bd-124">지정한 수정 활동에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="049bd-124">Returns information for the specified remediation activity.</span></span>

<span data-ttu-id="049bd-125">재구성 활동에 [대해 자세히 알아보시다.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="049bd-125">Learn more about [remediation activities](tvm-remediation.md).</span></span>

## <a name="properties"></a><span data-ttu-id="049bd-126">특성</span><span class="sxs-lookup"><span data-stu-id="049bd-126">Properties</span></span>

<span data-ttu-id="049bd-127">속성 ID</span><span class="sxs-lookup"><span data-stu-id="049bd-127">Property id</span></span> | <span data-ttu-id="049bd-128">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="049bd-128">Data type</span></span> | <span data-ttu-id="049bd-129">설명</span><span class="sxs-lookup"><span data-stu-id="049bd-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="049bd-130">category</span><span class="sxs-lookup"><span data-stu-id="049bd-130">category</span></span> | <span data-ttu-id="049bd-131">String</span><span class="sxs-lookup"><span data-stu-id="049bd-131">String</span></span> | <span data-ttu-id="049bd-132">재구성 활동 범주(소프트웨어/보안 구성)</span><span class="sxs-lookup"><span data-stu-id="049bd-132">Category of the remediation activity (Software/Security configuration)</span></span>
<span data-ttu-id="049bd-133">completerEmail</span><span class="sxs-lookup"><span data-stu-id="049bd-133">completerEmail</span></span> | <span data-ttu-id="049bd-134">String</span><span class="sxs-lookup"><span data-stu-id="049bd-134">String</span></span> | <span data-ttu-id="049bd-135">누군가가 수정 작업을 수동으로 완료한 경우 이 열에 전자 메일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="049bd-135">If the remediation activity was manually completed by someone, this column contains their email</span></span>
<span data-ttu-id="049bd-136">completerId</span><span class="sxs-lookup"><span data-stu-id="049bd-136">completerId</span></span> | <span data-ttu-id="049bd-137">String</span><span class="sxs-lookup"><span data-stu-id="049bd-137">String</span></span> | <span data-ttu-id="049bd-138">누군가가 수정 작업을 수동으로 완료한 경우 이 열에는 해당 개체 ID가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="049bd-138">If the remediation activity was manually completed by someone, this column contains their object id</span></span>
<span data-ttu-id="049bd-139">completionMethod</span><span class="sxs-lookup"><span data-stu-id="049bd-139">completionMethod</span></span> | <span data-ttu-id="049bd-140">String</span><span class="sxs-lookup"><span data-stu-id="049bd-140">String</span></span> | <span data-ttu-id="049bd-141">재구성 활동은 "자동"(모든 장치가 패치된 경우) 또는 "완료된 것으로 표시"를 선택한 사용자가 "수동으로" 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="049bd-141">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed.”</span></span>
<span data-ttu-id="049bd-142">createdOn</span><span class="sxs-lookup"><span data-stu-id="049bd-142">createdOn</span></span> | <span data-ttu-id="049bd-143">DateTime</span><span class="sxs-lookup"><span data-stu-id="049bd-143">DateTime</span></span> | <span data-ttu-id="049bd-144">이 수정 활동이 만들어진 시간</span><span class="sxs-lookup"><span data-stu-id="049bd-144">Time this remediation activity was created</span></span>
<span data-ttu-id="049bd-145">설명</span><span class="sxs-lookup"><span data-stu-id="049bd-145">description</span></span> | <span data-ttu-id="049bd-146">String</span><span class="sxs-lookup"><span data-stu-id="049bd-146">String</span></span> | <span data-ttu-id="049bd-147">이 수정 활동에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="049bd-147">Description of this remediation activity</span></span>
<span data-ttu-id="049bd-148">dueOn</span><span class="sxs-lookup"><span data-stu-id="049bd-148">dueOn</span></span> | <span data-ttu-id="049bd-149">DateTime</span><span class="sxs-lookup"><span data-stu-id="049bd-149">DateTime</span></span> | <span data-ttu-id="049bd-150">이 수정 활동에 대한 작성자가 설정한 기한</span><span class="sxs-lookup"><span data-stu-id="049bd-150">Due date the creator set for this remediation activity</span></span>
<span data-ttu-id="049bd-151">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="049bd-151">fixedDevices</span></span> |  | <span data-ttu-id="049bd-152">고정된 장치 수</span><span class="sxs-lookup"><span data-stu-id="049bd-152">The number of devices that have been fixed</span></span>
<span data-ttu-id="049bd-153">id</span><span class="sxs-lookup"><span data-stu-id="049bd-153">id</span></span> | <span data-ttu-id="049bd-154">String</span><span class="sxs-lookup"><span data-stu-id="049bd-154">String</span></span> | <span data-ttu-id="049bd-155">이 수정 활동의 ID</span><span class="sxs-lookup"><span data-stu-id="049bd-155">ID of this remediation activity</span></span>
<span data-ttu-id="049bd-156">nameId</span><span class="sxs-lookup"><span data-stu-id="049bd-156">nameId</span></span> | <span data-ttu-id="049bd-157">String</span><span class="sxs-lookup"><span data-stu-id="049bd-157">String</span></span> | <span data-ttu-id="049bd-158">관련 제품 이름</span><span class="sxs-lookup"><span data-stu-id="049bd-158">Related product name</span></span>
<span data-ttu-id="049bd-159">priority</span><span class="sxs-lookup"><span data-stu-id="049bd-159">priority</span></span> | <span data-ttu-id="049bd-160">String</span><span class="sxs-lookup"><span data-stu-id="049bd-160">String</span></span> | <span data-ttu-id="049bd-161">이 수정 활동의 작성자 집합 우선 순위(높음\중간\낮음)</span><span class="sxs-lookup"><span data-stu-id="049bd-161">Priority the creator set for this remediation activity (High\Medium\Low)</span></span>
<span data-ttu-id="049bd-162">productId</span><span class="sxs-lookup"><span data-stu-id="049bd-162">productId</span></span> | <span data-ttu-id="049bd-163">String</span><span class="sxs-lookup"><span data-stu-id="049bd-163">String</span></span> | <span data-ttu-id="049bd-164">관련 제품 ID</span><span class="sxs-lookup"><span data-stu-id="049bd-164">Related product ID</span></span>
<span data-ttu-id="049bd-165">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="049bd-165">productivityImpactRemediationType</span></span> | <span data-ttu-id="049bd-166">String</span><span class="sxs-lookup"><span data-stu-id="049bd-166">String</span></span> | <span data-ttu-id="049bd-167">사용자 영향이 없는 장치에만 몇 가지 구성 변경을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="049bd-167">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="049bd-168">이 값은 "노출된 모든 장치" 또는 "사용자 영향이 없는 장치만" 선택을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="049bd-168">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span>
<span data-ttu-id="049bd-169">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="049bd-169">rbacGroupNames</span></span> | <span data-ttu-id="049bd-170">String</span><span class="sxs-lookup"><span data-stu-id="049bd-170">String</span></span> | <span data-ttu-id="049bd-171">관련 장치 그룹 이름</span><span class="sxs-lookup"><span data-stu-id="049bd-171">Related device group names</span></span>
<span data-ttu-id="049bd-172">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="049bd-172">recommendedProgram</span></span> | <span data-ttu-id="049bd-173">String</span><span class="sxs-lookup"><span data-stu-id="049bd-173">String</span></span> | <span data-ttu-id="049bd-174">업그레이드할 권장 프로그램</span><span class="sxs-lookup"><span data-stu-id="049bd-174">Recommended program to upgrade to</span></span>
<span data-ttu-id="049bd-175">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="049bd-175">recommendedVendor</span></span> | <span data-ttu-id="049bd-176">String</span><span class="sxs-lookup"><span data-stu-id="049bd-176">String</span></span> | <span data-ttu-id="049bd-177">업그레이드할 권장 공급업체</span><span class="sxs-lookup"><span data-stu-id="049bd-177">Recommended vendor to upgrade to</span></span>
<span data-ttu-id="049bd-178">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="049bd-178">recommendedVersion</span></span> | <span data-ttu-id="049bd-179">String</span><span class="sxs-lookup"><span data-stu-id="049bd-179">String</span></span> | <span data-ttu-id="049bd-180">업데이트/업그레이드에 권장되는 버전</span><span class="sxs-lookup"><span data-stu-id="049bd-180">Recommended version to update/upgrade to</span></span>
<span data-ttu-id="049bd-181">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="049bd-181">relatedComponent</span></span> | <span data-ttu-id="049bd-182">String</span><span class="sxs-lookup"><span data-stu-id="049bd-182">String</span></span> | <span data-ttu-id="049bd-183">이 수정 작업의 관련 구성 요소(보안 권장에 대한 관련 구성 요소와 유사)</span><span class="sxs-lookup"><span data-stu-id="049bd-183">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span>
<span data-ttu-id="049bd-184">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="049bd-184">requesterEmail</span></span> | <span data-ttu-id="049bd-185">String</span><span class="sxs-lookup"><span data-stu-id="049bd-185">String</span></span> | <span data-ttu-id="049bd-186">작성자 전자 메일 주소</span><span class="sxs-lookup"><span data-stu-id="049bd-186">Creator email address</span></span>
<span data-ttu-id="049bd-187">requesterId</span><span class="sxs-lookup"><span data-stu-id="049bd-187">requesterId</span></span> | <span data-ttu-id="049bd-188">String</span><span class="sxs-lookup"><span data-stu-id="049bd-188">String</span></span> | <span data-ttu-id="049bd-189">Creator 개체 ID</span><span class="sxs-lookup"><span data-stu-id="049bd-189">Creator object id</span></span>
<span data-ttu-id="049bd-190">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="049bd-190">requesterNotes</span></span> | <span data-ttu-id="049bd-191">String</span><span class="sxs-lookup"><span data-stu-id="049bd-191">String</span></span> | <span data-ttu-id="049bd-192">이 수정 활동에 대해 작성자가 추가한 메모(무료 텍스트)</span><span class="sxs-lookup"><span data-stu-id="049bd-192">The notes (free text) the creator added for this remediation activity</span></span>
<span data-ttu-id="049bd-193">scid</span><span class="sxs-lookup"><span data-stu-id="049bd-193">scid</span></span> | <span data-ttu-id="049bd-194">String</span><span class="sxs-lookup"><span data-stu-id="049bd-194">String</span></span> | <span data-ttu-id="049bd-195">관련 보안 권장 정보의 SCID</span><span class="sxs-lookup"><span data-stu-id="049bd-195">SCID of the related security recommendation</span></span>
<span data-ttu-id="049bd-196">status</span><span class="sxs-lookup"><span data-stu-id="049bd-196">status</span></span> | <span data-ttu-id="049bd-197">String</span><span class="sxs-lookup"><span data-stu-id="049bd-197">String</span></span> | <span data-ttu-id="049bd-198">재구성 활동 상태(활성/완료)</span><span class="sxs-lookup"><span data-stu-id="049bd-198">Remediation activity status (Active/Completed)</span></span>
<span data-ttu-id="049bd-199">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="049bd-199">statusLastModifiedOn</span></span> | <span data-ttu-id="049bd-200">DateTime</span><span class="sxs-lookup"><span data-stu-id="049bd-200">DateTime</span></span> | <span data-ttu-id="049bd-201">상태 필드가 업데이트된 날짜</span><span class="sxs-lookup"><span data-stu-id="049bd-201">Date when the status field was updated</span></span>
<span data-ttu-id="049bd-202">targetDevices</span><span class="sxs-lookup"><span data-stu-id="049bd-202">targetDevices</span></span> | <span data-ttu-id="049bd-203">Long</span><span class="sxs-lookup"><span data-stu-id="049bd-203">Long</span></span> | <span data-ttu-id="049bd-204">이 수정을 적용할 수 있는 노출된 장치 수</span><span class="sxs-lookup"><span data-stu-id="049bd-204">Number of exposed devices that this remediation is applicable to</span></span>
<span data-ttu-id="049bd-205">title</span><span class="sxs-lookup"><span data-stu-id="049bd-205">title</span></span> | <span data-ttu-id="049bd-206">String</span><span class="sxs-lookup"><span data-stu-id="049bd-206">String</span></span> | <span data-ttu-id="049bd-207">이 수정 활동의 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="049bd-207">Title of this remediation activity</span></span>
<span data-ttu-id="049bd-208">type</span><span class="sxs-lookup"><span data-stu-id="049bd-208">type</span></span> | <span data-ttu-id="049bd-209">String</span><span class="sxs-lookup"><span data-stu-id="049bd-209">String</span></span> | <span data-ttu-id="049bd-210">수정 유형</span><span class="sxs-lookup"><span data-stu-id="049bd-210">Remediation type</span></span>
<span data-ttu-id="049bd-211">vendorId</span><span class="sxs-lookup"><span data-stu-id="049bd-211">vendorId</span></span> | <span data-ttu-id="049bd-212">String</span><span class="sxs-lookup"><span data-stu-id="049bd-212">String</span></span> | <span data-ttu-id="049bd-213">관련 공급업체 이름</span><span class="sxs-lookup"><span data-stu-id="049bd-213">Related vendor name</span></span>

## <a name="see-also"></a><span data-ttu-id="049bd-214">참고 항목</span><span class="sxs-lookup"><span data-stu-id="049bd-214">See also</span></span>

- [<span data-ttu-id="049bd-215">ID로 수정 작업 1개 가져오기</span><span class="sxs-lookup"><span data-stu-id="049bd-215">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="049bd-216">모든 수정 작업 나열s</span><span class="sxs-lookup"><span data-stu-id="049bd-216">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="049bd-217">한 번의 수정 작업이 있는 노출된 장치 목록</span><span class="sxs-lookup"><span data-stu-id="049bd-217">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="049bd-218">위험 기반 위협 & 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="049bd-218">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="049bd-219">조직의 취약성</span><span class="sxs-lookup"><span data-stu-id="049bd-219">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
