---
title: ID로 하나의 재구성 활동 얻기
description: 지정한 수정 활동에 대한 정보를 반환합니다.
keywords: api, 수정, 수정 api, get, 수정 작업, 목록
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
ms.openlocfilehash: 40a7102a8c7dbf63641daaf47bbd9aa9f2e54649
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061166"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="a84b0-104">ID로 하나의 재구성 활동 얻기</span><span class="sxs-lookup"><span data-stu-id="a84b0-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a84b0-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a84b0-105">**Applies to:**</span></span>

- [<span data-ttu-id="a84b0-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a84b0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a84b0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a84b0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a84b0-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="a84b0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a84b0-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="a84b0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="a84b0-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="a84b0-110">API description</span></span>

<span data-ttu-id="a84b0-111">지정한 수정 활동에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a84b0-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="a84b0-112">모든 재구성 활동 [](get-remediation-all-activities.md)"을(를) 반환하지만 지정된 수정 작업 중 하나에 대한 결과만 _반환합니다._</span><span class="sxs-lookup"><span data-stu-id="a84b0-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="a84b0-113">[재구성 활동에 대해 자세히 알아보시다.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="a84b0-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="a84b0-114">(id)에 대해 지정된 수정 활동 나열</span><span class="sxs-lookup"><span data-stu-id="a84b0-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="a84b0-115">**URL:** GET: /api/remediationTasks/ \{ id\}</span><span class="sxs-lookup"><span data-stu-id="a84b0-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

<span data-ttu-id="a84b0-116">**속성** 세부 정보</span><span class="sxs-lookup"><span data-stu-id="a84b0-116">**Properties** details</span></span>

<span data-ttu-id="a84b0-117">속성(id)</span><span class="sxs-lookup"><span data-stu-id="a84b0-117">Property (id)</span></span> | <span data-ttu-id="a84b0-118">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a84b0-118">Data type</span></span> | <span data-ttu-id="a84b0-119">설명</span><span class="sxs-lookup"><span data-stu-id="a84b0-119">Description</span></span> | <span data-ttu-id="a84b0-120">반환된 값의 예</span><span class="sxs-lookup"><span data-stu-id="a84b0-120">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="a84b0-121">category</span><span class="sxs-lookup"><span data-stu-id="a84b0-121">category</span></span> | <span data-ttu-id="a84b0-122">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-122">String</span></span> | <span data-ttu-id="a84b0-123">재구성 활동 범주(소프트웨어/보안 구성)</span><span class="sxs-lookup"><span data-stu-id="a84b0-123">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="a84b0-124">소프트웨어</span><span class="sxs-lookup"><span data-stu-id="a84b0-124">Software</span></span>
<span data-ttu-id="a84b0-125">completerEmail</span><span class="sxs-lookup"><span data-stu-id="a84b0-125">completerEmail</span></span> | <span data-ttu-id="a84b0-126">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-126">String</span></span> | <span data-ttu-id="a84b0-127">누군가가 수정 작업을 수동으로 완료한 경우 이 열에 전자 메일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a84b0-127">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="a84b0-128">null</span><span class="sxs-lookup"><span data-stu-id="a84b0-128">null</span></span>
<span data-ttu-id="a84b0-129">completerId</span><span class="sxs-lookup"><span data-stu-id="a84b0-129">completerId</span></span> | <span data-ttu-id="a84b0-130">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-130">String</span></span> | <span data-ttu-id="a84b0-131">누군가가 수정 작업을 수동으로 완료한 경우 이 열에는 해당 개체 ID가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a84b0-131">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="a84b0-132">null</span><span class="sxs-lookup"><span data-stu-id="a84b0-132">null</span></span>
<span data-ttu-id="a84b0-133">completionMethod</span><span class="sxs-lookup"><span data-stu-id="a84b0-133">completionMethod</span></span> | <span data-ttu-id="a84b0-134">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-134">String</span></span> | <span data-ttu-id="a84b0-135">재구성 활동은 "자동으로"(모든 장치가 패치된 경우) 또는 "완료된 것으로 표시"를 선택한 사람이 "수동으로" 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a84b0-135">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="a84b0-136">자동</span><span class="sxs-lookup"><span data-stu-id="a84b0-136">Automatic</span></span>
<span data-ttu-id="a84b0-137">createdOn</span><span class="sxs-lookup"><span data-stu-id="a84b0-137">createdOn</span></span> | <span data-ttu-id="a84b0-138">DateTime</span><span class="sxs-lookup"><span data-stu-id="a84b0-138">DateTime</span></span> | <span data-ttu-id="a84b0-139">이 수정 활동이 만들어진 시간</span><span class="sxs-lookup"><span data-stu-id="a84b0-139">Time this remediation activity was created</span></span> | <span data-ttu-id="a84b0-140">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="a84b0-140">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="a84b0-141">설명</span><span class="sxs-lookup"><span data-stu-id="a84b0-141">description</span></span> | <span data-ttu-id="a84b0-142">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-142">String</span></span> | <span data-ttu-id="a84b0-143">이 수정 활동에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="a84b0-143">Description of this remediation activity</span></span> | <span data-ttu-id="a84b0-144">장치에 영향을 주는 알려진 1248 취약점을 완화하기 위해 Chrome을 이후 버전으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="a84b0-144">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="a84b0-145">dueOn</span><span class="sxs-lookup"><span data-stu-id="a84b0-145">dueOn</span></span> | <span data-ttu-id="a84b0-146">DateTime</span><span class="sxs-lookup"><span data-stu-id="a84b0-146">DateTime</span></span> | <span data-ttu-id="a84b0-147">이 수정 활동에 대한 작성자가 설정한 기한</span><span class="sxs-lookup"><span data-stu-id="a84b0-147">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="a84b0-148">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="a84b0-148">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="a84b0-149">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="a84b0-149">fixedDevices</span></span> |  | <span data-ttu-id="a84b0-150">고정된 장치 수</span><span class="sxs-lookup"><span data-stu-id="a84b0-150">The number of devices that have been fixed</span></span> | <span data-ttu-id="a84b0-151">2</span><span class="sxs-lookup"><span data-stu-id="a84b0-151">2</span></span>
<span data-ttu-id="a84b0-152">id</span><span class="sxs-lookup"><span data-stu-id="a84b0-152">id</span></span> | <span data-ttu-id="a84b0-153">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-153">String</span></span> | <span data-ttu-id="a84b0-154">이 수정 활동의 ID</span><span class="sxs-lookup"><span data-stu-id="a84b0-154">ID of this remediation activity</span></span> | <span data-ttu-id="a84b0-155">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="a84b0-155">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="a84b0-156">nameId</span><span class="sxs-lookup"><span data-stu-id="a84b0-156">nameId</span></span> | <span data-ttu-id="a84b0-157">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-157">String</span></span> | <span data-ttu-id="a84b0-158">관련 제품 이름</span><span class="sxs-lookup"><span data-stu-id="a84b0-158">Related product name</span></span> | <span data-ttu-id="a84b0-159">chrome</span><span class="sxs-lookup"><span data-stu-id="a84b0-159">chrome</span></span>
<span data-ttu-id="a84b0-160">priority</span><span class="sxs-lookup"><span data-stu-id="a84b0-160">priority</span></span> | <span data-ttu-id="a84b0-161">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-161">String</span></span> | <span data-ttu-id="a84b0-162">이 수정 활동의 작성자 집합 우선 순위(높음\중간\낮음)</span><span class="sxs-lookup"><span data-stu-id="a84b0-162">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="a84b0-163">High</span><span class="sxs-lookup"><span data-stu-id="a84b0-163">High</span></span>
<span data-ttu-id="a84b0-164">productId</span><span class="sxs-lookup"><span data-stu-id="a84b0-164">productId</span></span> | <span data-ttu-id="a84b0-165">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-165">String</span></span> | <span data-ttu-id="a84b0-166">관련 제품 ID</span><span class="sxs-lookup"><span data-stu-id="a84b0-166">Related product ID</span></span> | <span data-ttu-id="a84b0-167">google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="a84b0-167">google-_-chrome</span></span>
<span data-ttu-id="a84b0-168">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="a84b0-168">productivityImpactRemediationType</span></span> | <span data-ttu-id="a84b0-169">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-169">String</span></span> | <span data-ttu-id="a84b0-170">사용자 영향이 없는 장치에만 몇 가지 구성 변경을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a84b0-170">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="a84b0-171">이 값은 "노출된 모든 장치" 또는 "사용자 영향이 없는 장치만" 선택을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a84b0-171">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="a84b0-172">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="a84b0-172">AllExposedAssets</span></span>
<span data-ttu-id="a84b0-173">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="a84b0-173">rbacGroupNames</span></span> | <span data-ttu-id="a84b0-174">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-174">String</span></span> | <span data-ttu-id="a84b0-175">관련 장치 그룹 이름</span><span class="sxs-lookup"><span data-stu-id="a84b0-175">Related device group names</span></span> | <span data-ttu-id="a84b0-176">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="a84b0-176">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="a84b0-177">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="a84b0-177">recommendedProgram</span></span> | <span data-ttu-id="a84b0-178">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-178">String</span></span> | <span data-ttu-id="a84b0-179">업그레이드할 권장 프로그램</span><span class="sxs-lookup"><span data-stu-id="a84b0-179">Recommended program to upgrade to</span></span> | <span data-ttu-id="a84b0-180">null</span><span class="sxs-lookup"><span data-stu-id="a84b0-180">null</span></span>
<span data-ttu-id="a84b0-181">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="a84b0-181">recommendedVendor</span></span> | <span data-ttu-id="a84b0-182">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-182">String</span></span> | <span data-ttu-id="a84b0-183">업그레이드할 권장 공급업체</span><span class="sxs-lookup"><span data-stu-id="a84b0-183">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="a84b0-184">null</span><span class="sxs-lookup"><span data-stu-id="a84b0-184">null</span></span>
<span data-ttu-id="a84b0-185">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="a84b0-185">recommendedVersion</span></span> | <span data-ttu-id="a84b0-186">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-186">String</span></span> | <span data-ttu-id="a84b0-187">업데이트/업그레이드에 권장되는 버전</span><span class="sxs-lookup"><span data-stu-id="a84b0-187">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="a84b0-188">null</span><span class="sxs-lookup"><span data-stu-id="a84b0-188">null</span></span>
<span data-ttu-id="a84b0-189">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="a84b0-189">relatedComponent</span></span> | <span data-ttu-id="a84b0-190">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-190">String</span></span> | <span data-ttu-id="a84b0-191">이 수정 작업의 관련 구성 요소(보안 권장에 대한 관련 구성 요소와 유사)</span><span class="sxs-lookup"><span data-stu-id="a84b0-191">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="a84b0-192">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="a84b0-192">Google Chrome</span></span>
<span data-ttu-id="a84b0-193">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="a84b0-193">requesterEmail</span></span> | <span data-ttu-id="a84b0-194">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-194">String</span></span> | <span data-ttu-id="a84b0-195">작성자 전자 메일 주소</span><span class="sxs-lookup"><span data-stu-id="a84b0-195">Creator email address</span></span> | <span data-ttu-id="a84b0-196">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a84b0-196">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="a84b0-197">requesterId</span><span class="sxs-lookup"><span data-stu-id="a84b0-197">requesterId</span></span> | <span data-ttu-id="a84b0-198">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-198">String</span></span> | <span data-ttu-id="a84b0-199">Creator 개체 ID</span><span class="sxs-lookup"><span data-stu-id="a84b0-199">Creator object id</span></span> | <span data-ttu-id="a84b0-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="a84b0-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="a84b0-201">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="a84b0-201">requesterNotes</span></span> | <span data-ttu-id="a84b0-202">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-202">String</span></span> | <span data-ttu-id="a84b0-203">이 수정 활동에 대해 작성자가 추가한 메모(무료 텍스트)</span><span class="sxs-lookup"><span data-stu-id="a84b0-203">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="a84b0-204">null</span><span class="sxs-lookup"><span data-stu-id="a84b0-204">null</span></span>
<span data-ttu-id="a84b0-205">scid</span><span class="sxs-lookup"><span data-stu-id="a84b0-205">scid</span></span> | <span data-ttu-id="a84b0-206">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-206">String</span></span> | <span data-ttu-id="a84b0-207">관련 보안 권장 정보의 SCID</span><span class="sxs-lookup"><span data-stu-id="a84b0-207">SCID of the related security recommendation</span></span> | <span data-ttu-id="a84b0-208">null</span><span class="sxs-lookup"><span data-stu-id="a84b0-208">null</span></span>
<span data-ttu-id="a84b0-209">status</span><span class="sxs-lookup"><span data-stu-id="a84b0-209">status</span></span> | <span data-ttu-id="a84b0-210">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-210">String</span></span> | <span data-ttu-id="a84b0-211">재구성 활동 상태(활성/완료)</span><span class="sxs-lookup"><span data-stu-id="a84b0-211">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="a84b0-212">활성</span><span class="sxs-lookup"><span data-stu-id="a84b0-212">Active</span></span>
<span data-ttu-id="a84b0-213">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="a84b0-213">statusLastModifiedOn</span></span> | <span data-ttu-id="a84b0-214">DateTime</span><span class="sxs-lookup"><span data-stu-id="a84b0-214">DateTime</span></span> | <span data-ttu-id="a84b0-215">상태 필드가 업데이트된 날짜</span><span class="sxs-lookup"><span data-stu-id="a84b0-215">Date when the status field was updated</span></span> | <span data-ttu-id="a84b0-216">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="a84b0-216">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="a84b0-217">targetDevices</span><span class="sxs-lookup"><span data-stu-id="a84b0-217">targetDevices</span></span> | <span data-ttu-id="a84b0-218">Long</span><span class="sxs-lookup"><span data-stu-id="a84b0-218">Long</span></span> | <span data-ttu-id="a84b0-219">이 수정을 적용할 수 있는 노출된 장치 수</span><span class="sxs-lookup"><span data-stu-id="a84b0-219">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="a84b0-220">43</span><span class="sxs-lookup"><span data-stu-id="a84b0-220">43</span></span>
<span data-ttu-id="a84b0-221">title</span><span class="sxs-lookup"><span data-stu-id="a84b0-221">title</span></span> | <span data-ttu-id="a84b0-222">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-222">String</span></span> | <span data-ttu-id="a84b0-223">이 수정 활동의 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="a84b0-223">Title of this remediation activity</span></span> | <span data-ttu-id="a84b0-224">Google Chrome 업데이트</span><span class="sxs-lookup"><span data-stu-id="a84b0-224">Update Google Chrome</span></span>
<span data-ttu-id="a84b0-225">type</span><span class="sxs-lookup"><span data-stu-id="a84b0-225">type</span></span> | <span data-ttu-id="a84b0-226">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-226">String</span></span> | <span data-ttu-id="a84b0-227">수정 유형</span><span class="sxs-lookup"><span data-stu-id="a84b0-227">Remediation type</span></span> | <span data-ttu-id="a84b0-228">업데이트</span><span class="sxs-lookup"><span data-stu-id="a84b0-228">Update</span></span>
<span data-ttu-id="a84b0-229">vendorId</span><span class="sxs-lookup"><span data-stu-id="a84b0-229">vendorId</span></span> | <span data-ttu-id="a84b0-230">문자열</span><span class="sxs-lookup"><span data-stu-id="a84b0-230">String</span></span> | <span data-ttu-id="a84b0-231">관련 공급업체 이름</span><span class="sxs-lookup"><span data-stu-id="a84b0-231">Related vendor name</span></span> | <span data-ttu-id="a84b0-232">google</span><span class="sxs-lookup"><span data-stu-id="a84b0-232">google</span></span>

## <a name="example"></a><span data-ttu-id="a84b0-233">예시</span><span class="sxs-lookup"><span data-stu-id="a84b0-233">Example</span></span>

<span data-ttu-id="a84b0-234">**요청** 예제</span><span class="sxs-lookup"><span data-stu-id="a84b0-234">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

<span data-ttu-id="a84b0-235">**응답** 예제</span><span class="sxs-lookup"><span data-stu-id="a84b0-235">**Response** example</span></span>

```json
{ 
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks/$entity", 
    "id": "03942ef5-aecb-4c6e-b555-d6a97013844c", 
    "title": "Update Microsoft Silverlight", 
    "createdOn": "2021-02-10T13:20:36.4718166Z", 
    "requesterId": "65548a1d-efo0-4a7a-8d19-1b967b5c36f4", 
    "requesterEmail": "user1@contoso.com", 
    "status": "Active", 
    "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z", 
    "description": "Update Silverlight to a later version to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ", 
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
```

## <a name="see-also"></a><span data-ttu-id="a84b0-236">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a84b0-236">See also</span></span>

- [<span data-ttu-id="a84b0-237">수정 방법 및 속성</span><span class="sxs-lookup"><span data-stu-id="a84b0-237">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="a84b0-238">모든 재구성 활동 나열</span><span class="sxs-lookup"><span data-stu-id="a84b0-238">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="a84b0-239">한 가지 수정 활동의 노출된 장치 나열</span><span class="sxs-lookup"><span data-stu-id="a84b0-239">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="a84b0-240">위험 기반 위협 & 관리</span><span class="sxs-lookup"><span data-stu-id="a84b0-240">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="a84b0-241">조직의 취약성</span><span class="sxs-lookup"><span data-stu-id="a84b0-241">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
