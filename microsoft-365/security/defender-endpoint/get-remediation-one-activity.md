---
title: ID로 하나의 재구성 활동 얻기
description: 지정한 수정 활동에 대한 정보를 반환합니다.
keywords: api, 수정, 수정 api, get, 수정 작업, ID로 수정,
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
ms.openlocfilehash: c2b7afef2c090df709f9209f450d8d3aab0424bf
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772152"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="3b68b-104">ID로 하나의 재구성 활동 얻기</span><span class="sxs-lookup"><span data-stu-id="3b68b-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3b68b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="3b68b-105">**Applies to:**</span></span>

- [<span data-ttu-id="3b68b-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3b68b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3b68b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b68b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3b68b-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="3b68b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3b68b-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3b68b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="3b68b-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="3b68b-110">API description</span></span>

<span data-ttu-id="3b68b-111">지정한 수정 활동에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3b68b-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="3b68b-112">모든 재구성 활동 [](get-remediation-all-activities.md)"을(를) 반환하지만 지정된 수정 작업 중 하나에 대한 결과만 _반환합니다._</span><span class="sxs-lookup"><span data-stu-id="3b68b-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="3b68b-113">[재구성 활동에 대해 자세히 알아보시다.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="3b68b-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="3b68b-114">(id)에 대해 지정된 수정 활동 나열</span><span class="sxs-lookup"><span data-stu-id="3b68b-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="3b68b-115">**URL:** GET: /api/remediationTasks/ \{ id\}</span><span class="sxs-lookup"><span data-stu-id="3b68b-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

## <a name="permissions"></a><span data-ttu-id="3b68b-116">사용 권한</span><span class="sxs-lookup"><span data-stu-id="3b68b-116">Permissions</span></span>

<span data-ttu-id="3b68b-117">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3b68b-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3b68b-118">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API for details을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3b68b-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="3b68b-119">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="3b68b-119">Permission type</span></span> | <span data-ttu-id="3b68b-120">사용 권한</span><span class="sxs-lookup"><span data-stu-id="3b68b-120">Permission</span></span> | <span data-ttu-id="3b68b-121">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="3b68b-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3b68b-122">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="3b68b-122">Application</span></span> | <span data-ttu-id="3b68b-123">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="3b68b-123">RemediationTask.Read.All</span></span> | <span data-ttu-id="3b68b-124">\'위협 및 취약성 관리 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="3b68b-124">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="3b68b-125">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="3b68b-125">Delegated (work or school account)</span></span> | <span data-ttu-id="3b68b-126">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="3b68b-126">RemediationTask.Read.Read</span></span> | <span data-ttu-id="3b68b-127">\'위협 및 취약성 관리 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="3b68b-127">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="3b68b-128">특성</span><span class="sxs-lookup"><span data-stu-id="3b68b-128">Properties</span></span>

<span data-ttu-id="3b68b-129">속성(id)</span><span class="sxs-lookup"><span data-stu-id="3b68b-129">Property (id)</span></span> | <span data-ttu-id="3b68b-130">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3b68b-130">Data type</span></span> | <span data-ttu-id="3b68b-131">설명</span><span class="sxs-lookup"><span data-stu-id="3b68b-131">Description</span></span> | <span data-ttu-id="3b68b-132">반환된 값의 예</span><span class="sxs-lookup"><span data-stu-id="3b68b-132">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="3b68b-133">category</span><span class="sxs-lookup"><span data-stu-id="3b68b-133">category</span></span> | <span data-ttu-id="3b68b-134">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-134">String</span></span> | <span data-ttu-id="3b68b-135">재구성 활동 범주(소프트웨어/보안 구성)</span><span class="sxs-lookup"><span data-stu-id="3b68b-135">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="3b68b-136">소프트웨어</span><span class="sxs-lookup"><span data-stu-id="3b68b-136">Software</span></span>
<span data-ttu-id="3b68b-137">completerEmail</span><span class="sxs-lookup"><span data-stu-id="3b68b-137">completerEmail</span></span> | <span data-ttu-id="3b68b-138">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-138">String</span></span> | <span data-ttu-id="3b68b-139">누군가가 수정 작업을 수동으로 완료한 경우 이 열에 전자 메일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b68b-139">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="3b68b-140">null</span><span class="sxs-lookup"><span data-stu-id="3b68b-140">null</span></span>
<span data-ttu-id="3b68b-141">completerId</span><span class="sxs-lookup"><span data-stu-id="3b68b-141">completerId</span></span> | <span data-ttu-id="3b68b-142">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-142">String</span></span> | <span data-ttu-id="3b68b-143">누군가가 수정 작업을 수동으로 완료한 경우 이 열에는 해당 개체 ID가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b68b-143">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="3b68b-144">null</span><span class="sxs-lookup"><span data-stu-id="3b68b-144">null</span></span>
<span data-ttu-id="3b68b-145">completionMethod</span><span class="sxs-lookup"><span data-stu-id="3b68b-145">completionMethod</span></span> | <span data-ttu-id="3b68b-146">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-146">String</span></span> | <span data-ttu-id="3b68b-147">재구성 활동은 "자동으로"(모든 장치가 패치된 경우) 또는 "완료된 것으로 표시"를 선택한 사람이 "수동으로" 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b68b-147">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="3b68b-148">자동</span><span class="sxs-lookup"><span data-stu-id="3b68b-148">Automatic</span></span>
<span data-ttu-id="3b68b-149">createdOn</span><span class="sxs-lookup"><span data-stu-id="3b68b-149">createdOn</span></span> | <span data-ttu-id="3b68b-150">DateTime</span><span class="sxs-lookup"><span data-stu-id="3b68b-150">DateTime</span></span> | <span data-ttu-id="3b68b-151">이 수정 활동이 만들어진 시간</span><span class="sxs-lookup"><span data-stu-id="3b68b-151">Time this remediation activity was created</span></span> | <span data-ttu-id="3b68b-152">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="3b68b-152">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="3b68b-153">설명</span><span class="sxs-lookup"><span data-stu-id="3b68b-153">description</span></span> | <span data-ttu-id="3b68b-154">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-154">String</span></span> | <span data-ttu-id="3b68b-155">이 수정 활동에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="3b68b-155">Description of this remediation activity</span></span> | <span data-ttu-id="3b68b-156">장치에 영향을 주는 알려진 취약점을 완화하기 위해 Microsoft Silverlight를 이후 버전으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="3b68b-156">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="3b68b-157">dueOn</span><span class="sxs-lookup"><span data-stu-id="3b68b-157">dueOn</span></span> | <span data-ttu-id="3b68b-158">DateTime</span><span class="sxs-lookup"><span data-stu-id="3b68b-158">DateTime</span></span> | <span data-ttu-id="3b68b-159">이 수정 활동에 대한 작성자가 설정한 기한</span><span class="sxs-lookup"><span data-stu-id="3b68b-159">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="3b68b-160">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="3b68b-160">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="3b68b-161">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="3b68b-161">fixedDevices</span></span> |  | <span data-ttu-id="3b68b-162">고정된 장치 수</span><span class="sxs-lookup"><span data-stu-id="3b68b-162">The number of devices that have been fixed</span></span> | <span data-ttu-id="3b68b-163">2</span><span class="sxs-lookup"><span data-stu-id="3b68b-163">2</span></span>
<span data-ttu-id="3b68b-164">id</span><span class="sxs-lookup"><span data-stu-id="3b68b-164">id</span></span> | <span data-ttu-id="3b68b-165">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-165">String</span></span> | <span data-ttu-id="3b68b-166">이 수정 활동의 ID</span><span class="sxs-lookup"><span data-stu-id="3b68b-166">ID of this remediation activity</span></span> | <span data-ttu-id="3b68b-167">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="3b68b-167">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="3b68b-168">nameId</span><span class="sxs-lookup"><span data-stu-id="3b68b-168">nameId</span></span> | <span data-ttu-id="3b68b-169">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-169">String</span></span> | <span data-ttu-id="3b68b-170">관련 제품 이름</span><span class="sxs-lookup"><span data-stu-id="3b68b-170">Related product name</span></span> | <span data-ttu-id="3b68b-171">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="3b68b-171">Microsoft Silverlight</span></span>
<span data-ttu-id="3b68b-172">priority</span><span class="sxs-lookup"><span data-stu-id="3b68b-172">priority</span></span> | <span data-ttu-id="3b68b-173">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-173">String</span></span> | <span data-ttu-id="3b68b-174">이 수정 활동의 작성자 집합 우선 순위(높음\중간\낮음)</span><span class="sxs-lookup"><span data-stu-id="3b68b-174">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="3b68b-175">높음</span><span class="sxs-lookup"><span data-stu-id="3b68b-175">High</span></span>
<span data-ttu-id="3b68b-176">productId</span><span class="sxs-lookup"><span data-stu-id="3b68b-176">productId</span></span> | <span data-ttu-id="3b68b-177">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-177">String</span></span> | <span data-ttu-id="3b68b-178">관련 제품 ID</span><span class="sxs-lookup"><span data-stu-id="3b68b-178">Related product ID</span></span> | <span data-ttu-id="3b68b-179">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="3b68b-179">microsoft-_-silverlight</span></span>
<span data-ttu-id="3b68b-180">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="3b68b-180">productivityImpactRemediationType</span></span> | <span data-ttu-id="3b68b-181">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-181">String</span></span> | <span data-ttu-id="3b68b-182">사용자 영향이 없는 장치에만 몇 가지 구성 변경을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b68b-182">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="3b68b-183">이 값은 "노출된 모든 장치" 또는 "사용자 영향이 없는 장치만" 선택을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3b68b-183">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="3b68b-184">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="3b68b-184">AllExposedAssets</span></span>
<span data-ttu-id="3b68b-185">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="3b68b-185">rbacGroupNames</span></span> | <span data-ttu-id="3b68b-186">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-186">String</span></span> | <span data-ttu-id="3b68b-187">관련 장치 그룹 이름</span><span class="sxs-lookup"><span data-stu-id="3b68b-187">Related device group names</span></span> | <span data-ttu-id="3b68b-188">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="3b68b-188">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="3b68b-189">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="3b68b-189">recommendedProgram</span></span> | <span data-ttu-id="3b68b-190">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-190">String</span></span> | <span data-ttu-id="3b68b-191">업그레이드할 권장 프로그램</span><span class="sxs-lookup"><span data-stu-id="3b68b-191">Recommended program to upgrade to</span></span> | <span data-ttu-id="3b68b-192">null</span><span class="sxs-lookup"><span data-stu-id="3b68b-192">null</span></span>
<span data-ttu-id="3b68b-193">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="3b68b-193">recommendedVendor</span></span> | <span data-ttu-id="3b68b-194">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-194">String</span></span> | <span data-ttu-id="3b68b-195">업그레이드할 권장 공급업체</span><span class="sxs-lookup"><span data-stu-id="3b68b-195">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="3b68b-196">null</span><span class="sxs-lookup"><span data-stu-id="3b68b-196">null</span></span>
<span data-ttu-id="3b68b-197">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="3b68b-197">recommendedVersion</span></span> | <span data-ttu-id="3b68b-198">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-198">String</span></span> | <span data-ttu-id="3b68b-199">업데이트/업그레이드에 권장되는 버전</span><span class="sxs-lookup"><span data-stu-id="3b68b-199">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="3b68b-200">null</span><span class="sxs-lookup"><span data-stu-id="3b68b-200">null</span></span>
<span data-ttu-id="3b68b-201">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="3b68b-201">relatedComponent</span></span> | <span data-ttu-id="3b68b-202">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-202">String</span></span> | <span data-ttu-id="3b68b-203">이 수정 작업의 관련 구성 요소(보안 권장에 대한 관련 구성 요소와 유사)</span><span class="sxs-lookup"><span data-stu-id="3b68b-203">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="3b68b-204">Microsoft Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="3b68b-204">Microsoft Microsoft Silverlight</span></span>
<span data-ttu-id="3b68b-205">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="3b68b-205">requesterEmail</span></span> | <span data-ttu-id="3b68b-206">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-206">String</span></span> | <span data-ttu-id="3b68b-207">작성자 전자 메일 주소</span><span class="sxs-lookup"><span data-stu-id="3b68b-207">Creator email address</span></span> | <span data-ttu-id="3b68b-208">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b68b-208">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="3b68b-209">requesterId</span><span class="sxs-lookup"><span data-stu-id="3b68b-209">requesterId</span></span> | <span data-ttu-id="3b68b-210">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-210">String</span></span> | <span data-ttu-id="3b68b-211">Creator 개체 ID</span><span class="sxs-lookup"><span data-stu-id="3b68b-211">Creator object id</span></span> | <span data-ttu-id="3b68b-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="3b68b-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="3b68b-213">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="3b68b-213">requesterNotes</span></span> | <span data-ttu-id="3b68b-214">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-214">String</span></span> | <span data-ttu-id="3b68b-215">이 수정 활동에 대해 작성자가 추가한 메모(무료 텍스트)</span><span class="sxs-lookup"><span data-stu-id="3b68b-215">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="3b68b-216">null</span><span class="sxs-lookup"><span data-stu-id="3b68b-216">null</span></span>
<span data-ttu-id="3b68b-217">scid</span><span class="sxs-lookup"><span data-stu-id="3b68b-217">scid</span></span> | <span data-ttu-id="3b68b-218">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-218">String</span></span> | <span data-ttu-id="3b68b-219">관련 보안 권장 정보의 SCID</span><span class="sxs-lookup"><span data-stu-id="3b68b-219">SCID of the related security recommendation</span></span> | <span data-ttu-id="3b68b-220">null</span><span class="sxs-lookup"><span data-stu-id="3b68b-220">null</span></span>
<span data-ttu-id="3b68b-221">status</span><span class="sxs-lookup"><span data-stu-id="3b68b-221">status</span></span> | <span data-ttu-id="3b68b-222">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-222">String</span></span> | <span data-ttu-id="3b68b-223">재구성 활동 상태(활성/완료)</span><span class="sxs-lookup"><span data-stu-id="3b68b-223">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="3b68b-224">활성</span><span class="sxs-lookup"><span data-stu-id="3b68b-224">Active</span></span>
<span data-ttu-id="3b68b-225">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="3b68b-225">statusLastModifiedOn</span></span> | <span data-ttu-id="3b68b-226">DateTime</span><span class="sxs-lookup"><span data-stu-id="3b68b-226">DateTime</span></span> | <span data-ttu-id="3b68b-227">상태 필드가 업데이트된 날짜</span><span class="sxs-lookup"><span data-stu-id="3b68b-227">Date when the status field was updated</span></span> | <span data-ttu-id="3b68b-228">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="3b68b-228">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="3b68b-229">targetDevices</span><span class="sxs-lookup"><span data-stu-id="3b68b-229">targetDevices</span></span> | <span data-ttu-id="3b68b-230">Long</span><span class="sxs-lookup"><span data-stu-id="3b68b-230">Long</span></span> | <span data-ttu-id="3b68b-231">이 수정을 적용할 수 있는 노출된 장치 수</span><span class="sxs-lookup"><span data-stu-id="3b68b-231">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="3b68b-232">43</span><span class="sxs-lookup"><span data-stu-id="3b68b-232">43</span></span>
<span data-ttu-id="3b68b-233">title</span><span class="sxs-lookup"><span data-stu-id="3b68b-233">title</span></span> | <span data-ttu-id="3b68b-234">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-234">String</span></span> | <span data-ttu-id="3b68b-235">이 수정 활동의 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="3b68b-235">Title of this remediation activity</span></span> | <span data-ttu-id="3b68b-236">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="3b68b-236">Microsoft Silverlight</span></span>
<span data-ttu-id="3b68b-237">type</span><span class="sxs-lookup"><span data-stu-id="3b68b-237">type</span></span> | <span data-ttu-id="3b68b-238">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-238">String</span></span> | <span data-ttu-id="3b68b-239">수정 유형</span><span class="sxs-lookup"><span data-stu-id="3b68b-239">Remediation type</span></span> | <span data-ttu-id="3b68b-240">업데이트</span><span class="sxs-lookup"><span data-stu-id="3b68b-240">Update</span></span>
<span data-ttu-id="3b68b-241">vendorId</span><span class="sxs-lookup"><span data-stu-id="3b68b-241">vendorId</span></span> | <span data-ttu-id="3b68b-242">String</span><span class="sxs-lookup"><span data-stu-id="3b68b-242">String</span></span> | <span data-ttu-id="3b68b-243">관련 공급업체 이름</span><span class="sxs-lookup"><span data-stu-id="3b68b-243">Related vendor name</span></span> | <span data-ttu-id="3b68b-244">Microsoft</span><span class="sxs-lookup"><span data-stu-id="3b68b-244">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="3b68b-245">예시</span><span class="sxs-lookup"><span data-stu-id="3b68b-245">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="3b68b-246">요청 예제</span><span class="sxs-lookup"><span data-stu-id="3b68b-246">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

### <a name="response-example"></a><span data-ttu-id="3b68b-247">응답 예제</span><span class="sxs-lookup"><span data-stu-id="3b68b-247">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="3b68b-248">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b68b-248">See also</span></span>

- [<span data-ttu-id="3b68b-249">수정 방법 및 속성</span><span class="sxs-lookup"><span data-stu-id="3b68b-249">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="3b68b-250">모든 수정 작업 나열s</span><span class="sxs-lookup"><span data-stu-id="3b68b-250">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="3b68b-251">한 번의 수정 작업이 있는 노출된 장치 목록</span><span class="sxs-lookup"><span data-stu-id="3b68b-251">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="3b68b-252">위험 기반 위협 & 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="3b68b-252">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="3b68b-253">조직의 취약성</span><span class="sxs-lookup"><span data-stu-id="3b68b-253">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
