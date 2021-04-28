---
title: 모든 재구성 활동 나열
description: 모든 수정 활동에 대한 정보를 반환합니다.
keywords: api, 수정, 수정 api, get, 수정 작업,
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
ms.technology: mde
ms.openlocfilehash: ac4a777136dcdfc5d7ab61ddc8d496b7452f69e2
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061162"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="7bac5-104">모든 재구성 활동 나열</span><span class="sxs-lookup"><span data-stu-id="7bac5-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7bac5-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7bac5-105">**Applies to:**</span></span>

- [<span data-ttu-id="7bac5-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7bac5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7bac5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7bac5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7bac5-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="7bac5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7bac5-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="7bac5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="7bac5-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="7bac5-110">API description</span></span>

<span data-ttu-id="7bac5-111">모든 수정 활동에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7bac5-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="7bac5-112">[재구성 활동에 대해 자세히 알아보시다.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="7bac5-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="7bac5-113">**URL:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="7bac5-113">**URL:** GET: /api/remediationTasks</span></span>

<span data-ttu-id="7bac5-114">**속성** 세부 정보</span><span class="sxs-lookup"><span data-stu-id="7bac5-114">**Properties** details</span></span>

<span data-ttu-id="7bac5-115">속성(id)</span><span class="sxs-lookup"><span data-stu-id="7bac5-115">Property (id)</span></span> | <span data-ttu-id="7bac5-116">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7bac5-116">Data type</span></span> | <span data-ttu-id="7bac5-117">설명</span><span class="sxs-lookup"><span data-stu-id="7bac5-117">Description</span></span> | <span data-ttu-id="7bac5-118">반환된 값의 예</span><span class="sxs-lookup"><span data-stu-id="7bac5-118">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="7bac5-119">category</span><span class="sxs-lookup"><span data-stu-id="7bac5-119">category</span></span> | <span data-ttu-id="7bac5-120">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-120">String</span></span> | <span data-ttu-id="7bac5-121">재구성 활동 범주(소프트웨어/보안 구성)</span><span class="sxs-lookup"><span data-stu-id="7bac5-121">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="7bac5-122">소프트웨어</span><span class="sxs-lookup"><span data-stu-id="7bac5-122">Software</span></span>
<span data-ttu-id="7bac5-123">completerEmail</span><span class="sxs-lookup"><span data-stu-id="7bac5-123">completerEmail</span></span> | <span data-ttu-id="7bac5-124">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-124">String</span></span> | <span data-ttu-id="7bac5-125">누군가가 수정 작업을 수동으로 완료한 경우 이 열에 전자 메일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bac5-125">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="7bac5-126">null</span><span class="sxs-lookup"><span data-stu-id="7bac5-126">null</span></span>
<span data-ttu-id="7bac5-127">completerId</span><span class="sxs-lookup"><span data-stu-id="7bac5-127">completerId</span></span> | <span data-ttu-id="7bac5-128">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-128">String</span></span> | <span data-ttu-id="7bac5-129">누군가가 수정 작업을 수동으로 완료한 경우 이 열에는 해당 개체 ID가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bac5-129">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="7bac5-130">null</span><span class="sxs-lookup"><span data-stu-id="7bac5-130">null</span></span>
<span data-ttu-id="7bac5-131">completionMethod</span><span class="sxs-lookup"><span data-stu-id="7bac5-131">completionMethod</span></span> | <span data-ttu-id="7bac5-132">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-132">String</span></span> | <span data-ttu-id="7bac5-133">재구성 활동은 "자동으로"(모든 장치가 패치된 경우) 또는 "완료된 것으로 표시"를 선택한 사람이 "수동으로" 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bac5-133">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="7bac5-134">자동</span><span class="sxs-lookup"><span data-stu-id="7bac5-134">Automatic</span></span>
<span data-ttu-id="7bac5-135">createdOn</span><span class="sxs-lookup"><span data-stu-id="7bac5-135">createdOn</span></span> | <span data-ttu-id="7bac5-136">DateTime</span><span class="sxs-lookup"><span data-stu-id="7bac5-136">DateTime</span></span> | <span data-ttu-id="7bac5-137">이 수정 활동이 만들어진 시간</span><span class="sxs-lookup"><span data-stu-id="7bac5-137">Time this remediation activity was created</span></span> | <span data-ttu-id="7bac5-138">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="7bac5-138">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="7bac5-139">설명</span><span class="sxs-lookup"><span data-stu-id="7bac5-139">description</span></span> | <span data-ttu-id="7bac5-140">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-140">String</span></span> | <span data-ttu-id="7bac5-141">이 수정 활동에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="7bac5-141">Description of this remediation activity</span></span> | <span data-ttu-id="7bac5-142">장치에 영향을 주는 알려진 1248 취약점을 완화하기 위해 Chrome을 이후 버전으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="7bac5-142">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="7bac5-143">dueOn</span><span class="sxs-lookup"><span data-stu-id="7bac5-143">dueOn</span></span> | <span data-ttu-id="7bac5-144">DateTime</span><span class="sxs-lookup"><span data-stu-id="7bac5-144">DateTime</span></span> | <span data-ttu-id="7bac5-145">이 수정 활동에 대한 작성자가 설정한 기한</span><span class="sxs-lookup"><span data-stu-id="7bac5-145">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="7bac5-146">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="7bac5-146">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="7bac5-147">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="7bac5-147">fixedDevices</span></span> | <span data-ttu-id="7bac5-148">.</span><span class="sxs-lookup"><span data-stu-id="7bac5-148">.</span></span> | <span data-ttu-id="7bac5-149">고정된 장치 수</span><span class="sxs-lookup"><span data-stu-id="7bac5-149">The number of devices that have been fixed</span></span> | <span data-ttu-id="7bac5-150">2</span><span class="sxs-lookup"><span data-stu-id="7bac5-150">2</span></span>
<span data-ttu-id="7bac5-151">id</span><span class="sxs-lookup"><span data-stu-id="7bac5-151">id</span></span> | <span data-ttu-id="7bac5-152">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-152">String</span></span> | <span data-ttu-id="7bac5-153">이 수정 활동의 ID</span><span class="sxs-lookup"><span data-stu-id="7bac5-153">ID of this remediation activity</span></span> | <span data-ttu-id="7bac5-154">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="7bac5-154">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="7bac5-155">nameId</span><span class="sxs-lookup"><span data-stu-id="7bac5-155">nameId</span></span> | <span data-ttu-id="7bac5-156">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-156">String</span></span> | <span data-ttu-id="7bac5-157">관련 제품 이름</span><span class="sxs-lookup"><span data-stu-id="7bac5-157">Related product name</span></span> | <span data-ttu-id="7bac5-158">chrome</span><span class="sxs-lookup"><span data-stu-id="7bac5-158">chrome</span></span>
<span data-ttu-id="7bac5-159">priority</span><span class="sxs-lookup"><span data-stu-id="7bac5-159">priority</span></span> | <span data-ttu-id="7bac5-160">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-160">String</span></span> | <span data-ttu-id="7bac5-161">이 수정 활동의 작성자 집합 우선 순위(높음\중간\낮음)</span><span class="sxs-lookup"><span data-stu-id="7bac5-161">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="7bac5-162">High</span><span class="sxs-lookup"><span data-stu-id="7bac5-162">High</span></span>
<span data-ttu-id="7bac5-163">productId</span><span class="sxs-lookup"><span data-stu-id="7bac5-163">productId</span></span> | <span data-ttu-id="7bac5-164">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-164">String</span></span> | <span data-ttu-id="7bac5-165">관련 제품 ID</span><span class="sxs-lookup"><span data-stu-id="7bac5-165">Related product ID</span></span> | <span data-ttu-id="7bac5-166">google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="7bac5-166">google-_-chrome</span></span>
<span data-ttu-id="7bac5-167">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="7bac5-167">productivityImpactRemediationType</span></span> | <span data-ttu-id="7bac5-168">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-168">String</span></span> | <span data-ttu-id="7bac5-169">사용자 영향이 없는 장치에만 몇 가지 구성 변경을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bac5-169">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="7bac5-170">이 값은 "노출된 모든 장치" 또는 "사용자 영향이 없는 장치만" 선택을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7bac5-170">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="7bac5-171">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="7bac5-171">AllExposedAssets</span></span>
<span data-ttu-id="7bac5-172">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="7bac5-172">rbacGroupNames</span></span> | <span data-ttu-id="7bac5-173">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-173">String</span></span> | <span data-ttu-id="7bac5-174">관련 장치 그룹 이름</span><span class="sxs-lookup"><span data-stu-id="7bac5-174">Related device group names</span></span> | <span data-ttu-id="7bac5-175">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="7bac5-175">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="7bac5-176">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="7bac5-176">recommendedProgram</span></span> | <span data-ttu-id="7bac5-177">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-177">String</span></span> | <span data-ttu-id="7bac5-178">업그레이드할 권장 프로그램</span><span class="sxs-lookup"><span data-stu-id="7bac5-178">Recommended program to upgrade to</span></span> | <span data-ttu-id="7bac5-179">null</span><span class="sxs-lookup"><span data-stu-id="7bac5-179">null</span></span>
<span data-ttu-id="7bac5-180">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="7bac5-180">recommendedVendor</span></span> | <span data-ttu-id="7bac5-181">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-181">String</span></span> | <span data-ttu-id="7bac5-182">업그레이드할 권장 공급업체</span><span class="sxs-lookup"><span data-stu-id="7bac5-182">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="7bac5-183">null</span><span class="sxs-lookup"><span data-stu-id="7bac5-183">null</span></span>
<span data-ttu-id="7bac5-184">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="7bac5-184">recommendedVersion</span></span> | <span data-ttu-id="7bac5-185">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-185">String</span></span> | <span data-ttu-id="7bac5-186">업데이트/업그레이드에 권장되는 버전</span><span class="sxs-lookup"><span data-stu-id="7bac5-186">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="7bac5-187">null</span><span class="sxs-lookup"><span data-stu-id="7bac5-187">null</span></span>
<span data-ttu-id="7bac5-188">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="7bac5-188">relatedComponent</span></span> | <span data-ttu-id="7bac5-189">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-189">String</span></span> | <span data-ttu-id="7bac5-190">이 수정 작업의 관련 구성 요소(보안 권장에 대한 관련 구성 요소와 유사)</span><span class="sxs-lookup"><span data-stu-id="7bac5-190">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="7bac5-191">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="7bac5-191">Google Chrome</span></span>
<span data-ttu-id="7bac5-192">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="7bac5-192">requesterEmail</span></span> | <span data-ttu-id="7bac5-193">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-193">String</span></span> | <span data-ttu-id="7bac5-194">작성자 전자 메일 주소</span><span class="sxs-lookup"><span data-stu-id="7bac5-194">Creator email address</span></span> | <span data-ttu-id="7bac5-195">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7bac5-195">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="7bac5-196">requesterId</span><span class="sxs-lookup"><span data-stu-id="7bac5-196">requesterId</span></span> | <span data-ttu-id="7bac5-197">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-197">String</span></span> | <span data-ttu-id="7bac5-198">Creator 개체 ID</span><span class="sxs-lookup"><span data-stu-id="7bac5-198">Creator object id</span></span> | <span data-ttu-id="7bac5-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="7bac5-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="7bac5-200">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="7bac5-200">requesterNotes</span></span> | <span data-ttu-id="7bac5-201">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-201">String</span></span> | <span data-ttu-id="7bac5-202">이 수정 활동에 대해 작성자가 추가한 메모(무료 텍스트)</span><span class="sxs-lookup"><span data-stu-id="7bac5-202">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="7bac5-203">null</span><span class="sxs-lookup"><span data-stu-id="7bac5-203">null</span></span>
<span data-ttu-id="7bac5-204">scid</span><span class="sxs-lookup"><span data-stu-id="7bac5-204">scid</span></span> | <span data-ttu-id="7bac5-205">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-205">String</span></span> | <span data-ttu-id="7bac5-206">관련 보안 권장 정보의 SCID</span><span class="sxs-lookup"><span data-stu-id="7bac5-206">SCID of the related security recommendation</span></span> | <span data-ttu-id="7bac5-207">null</span><span class="sxs-lookup"><span data-stu-id="7bac5-207">null</span></span>
<span data-ttu-id="7bac5-208">status</span><span class="sxs-lookup"><span data-stu-id="7bac5-208">status</span></span> | <span data-ttu-id="7bac5-209">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-209">String</span></span> | <span data-ttu-id="7bac5-210">재구성 활동 상태(활성/완료)</span><span class="sxs-lookup"><span data-stu-id="7bac5-210">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="7bac5-211">활성</span><span class="sxs-lookup"><span data-stu-id="7bac5-211">Active</span></span>
<span data-ttu-id="7bac5-212">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="7bac5-212">statusLastModifiedOn</span></span> | <span data-ttu-id="7bac5-213">DateTime</span><span class="sxs-lookup"><span data-stu-id="7bac5-213">DateTime</span></span> | <span data-ttu-id="7bac5-214">상태 필드가 업데이트된 날짜</span><span class="sxs-lookup"><span data-stu-id="7bac5-214">Date when the status field was updated</span></span> | <span data-ttu-id="7bac5-215">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="7bac5-215">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="7bac5-216">targetDevices</span><span class="sxs-lookup"><span data-stu-id="7bac5-216">targetDevices</span></span> | <span data-ttu-id="7bac5-217">Long</span><span class="sxs-lookup"><span data-stu-id="7bac5-217">Long</span></span> | <span data-ttu-id="7bac5-218">이 수정을 적용할 수 있는 노출된 장치 수</span><span class="sxs-lookup"><span data-stu-id="7bac5-218">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="7bac5-219">43</span><span class="sxs-lookup"><span data-stu-id="7bac5-219">43</span></span>
<span data-ttu-id="7bac5-220">title</span><span class="sxs-lookup"><span data-stu-id="7bac5-220">title</span></span> | <span data-ttu-id="7bac5-221">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-221">String</span></span> | <span data-ttu-id="7bac5-222">이 수정 활동의 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="7bac5-222">Title of this remediation activity</span></span> | <span data-ttu-id="7bac5-223">Google Chrome 업데이트</span><span class="sxs-lookup"><span data-stu-id="7bac5-223">Update Google Chrome</span></span>
<span data-ttu-id="7bac5-224">type</span><span class="sxs-lookup"><span data-stu-id="7bac5-224">type</span></span> | <span data-ttu-id="7bac5-225">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-225">String</span></span> | <span data-ttu-id="7bac5-226">수정 유형</span><span class="sxs-lookup"><span data-stu-id="7bac5-226">Remediation type</span></span> | <span data-ttu-id="7bac5-227">업데이트</span><span class="sxs-lookup"><span data-stu-id="7bac5-227">Update</span></span>
<span data-ttu-id="7bac5-228">vendorId</span><span class="sxs-lookup"><span data-stu-id="7bac5-228">vendorId</span></span> | <span data-ttu-id="7bac5-229">문자열</span><span class="sxs-lookup"><span data-stu-id="7bac5-229">String</span></span> | <span data-ttu-id="7bac5-230">관련 공급업체 이름</span><span class="sxs-lookup"><span data-stu-id="7bac5-230">Related vendor name</span></span> | <span data-ttu-id="7bac5-231">google</span><span class="sxs-lookup"><span data-stu-id="7bac5-231">google</span></span>

## <a name="example"></a><span data-ttu-id="7bac5-232">예시</span><span class="sxs-lookup"><span data-stu-id="7bac5-232">Example</span></span>

<span data-ttu-id="7bac5-233">**요청** 예제</span><span class="sxs-lookup"><span data-stu-id="7bac5-233">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

<span data-ttu-id="7bac5-234">**응답** 예제</span><span class="sxs-lookup"><span data-stu-id="7bac5-234">**Response** example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks",
    "value": [
        {
            "id": "03942ef5-aewb-4w6e-b555-d6a97013844w",
            "title": "Update Microsoft Silverlight",
            "createdOn": "2021-02-10T13:20:36.4718166Z",
            "requesterId": "65548a1d-ef00-4a7a-8d19-1b967b5c36f4",
            "requesterEmail": "user1@contoso.com",
            "status": "Active",
            "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z",
            "description": "Update Silverlight to a later version  to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ",
            "relatedComponent": "Microsoft Silverlight",
            "targetDevices": 18511,
            "rbacGroupNames": [
                "UnassignedGroup",
                "hhh"
            ],
            "fixedDevices": 2866,
            "requesterNotes": "test",
            "dueOn": "2021-02-11T00:00:00Z",
            "category": "Software",
            "productivityImpactRemediationType": null,
            "priority": "Medium",
            "completionMethod": null,
            "completerId": null,
            "completerEmail": null,
            "scid": null,
            "type": "Update",
            "productId": "microsoft-_-silverlight",
            "vendorId": "microsoft",
            "nameId": "silverlight",
            "recommendedVersion": null,
            "recommendedVendor": null,
            "recommendedProgram": null
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="7bac5-235">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bac5-235">See also</span></span>

- [<span data-ttu-id="7bac5-236">수정 방법 및 속성</span><span class="sxs-lookup"><span data-stu-id="7bac5-236">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="7bac5-237">ID로 하나의 재구성 활동 얻기</span><span class="sxs-lookup"><span data-stu-id="7bac5-237">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="7bac5-238">한 가지 수정 활동의 노출된 장치 나열</span><span class="sxs-lookup"><span data-stu-id="7bac5-238">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="7bac5-239">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="7bac5-239">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="7bac5-240">조직의 취약성</span><span class="sxs-lookup"><span data-stu-id="7bac5-240">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
