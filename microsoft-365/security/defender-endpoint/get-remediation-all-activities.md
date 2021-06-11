---
title: 모든 수정 작업 나열s
description: 모든 수정 활동에 대한 정보를 반환합니다.
keywords: api, 수정, 수정 api, get, 수정 작업, 모든 수정,
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
ms.openlocfilehash: 60f80e78a5f5c7da44a218c30f4b0173d4ecc829
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845138"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="afa5c-104">모든 수정 작업 나열s</span><span class="sxs-lookup"><span data-stu-id="afa5c-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="afa5c-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="afa5c-105">**Applies to:**</span></span>

- [<span data-ttu-id="afa5c-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="afa5c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="afa5c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="afa5c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="afa5c-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="afa5c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="afa5c-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="afa5c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="afa5c-110">API 설명</span><span class="sxs-lookup"><span data-stu-id="afa5c-110">API description</span></span>

<span data-ttu-id="afa5c-111">모든 수정 활동에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="afa5c-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="afa5c-112">[재구성 활동에 대해 자세히 알아보시다.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="afa5c-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="afa5c-113">**URL:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="afa5c-113">**URL:** GET: /api/remediationTasks</span></span>

## <a name="permissions"></a><span data-ttu-id="afa5c-114">사용 권한</span><span class="sxs-lookup"><span data-stu-id="afa5c-114">Permissions</span></span>

<span data-ttu-id="afa5c-115">이 API를 호출하려면 다음 권한 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="afa5c-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="afa5c-116">사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API for details을 참조합니다.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="afa5c-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="afa5c-117">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="afa5c-117">Permission type</span></span> | <span data-ttu-id="afa5c-118">사용 권한</span><span class="sxs-lookup"><span data-stu-id="afa5c-118">Permission</span></span> | <span data-ttu-id="afa5c-119">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="afa5c-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="afa5c-120">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="afa5c-120">Application</span></span> | <span data-ttu-id="afa5c-121">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="afa5c-121">RemediationTask.Read.All</span></span> | <span data-ttu-id="afa5c-122">\'위협 및 취약성 관리 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="afa5c-122">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="afa5c-123">위임(직장 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="afa5c-123">Delegated (work or school account)</span></span> | <span data-ttu-id="afa5c-124">RemediationTask.Read</span><span class="sxs-lookup"><span data-stu-id="afa5c-124">RemediationTask.Read</span></span> | <span data-ttu-id="afa5c-125">\'위협 및 취약성 관리 취약성 정보 읽기\'</span><span class="sxs-lookup"><span data-stu-id="afa5c-125">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="afa5c-126">특성</span><span class="sxs-lookup"><span data-stu-id="afa5c-126">Properties</span></span>

<span data-ttu-id="afa5c-127">속성(id)</span><span class="sxs-lookup"><span data-stu-id="afa5c-127">Property (id)</span></span> | <span data-ttu-id="afa5c-128">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="afa5c-128">Data type</span></span> | <span data-ttu-id="afa5c-129">설명</span><span class="sxs-lookup"><span data-stu-id="afa5c-129">Description</span></span> | <span data-ttu-id="afa5c-130">반환된 값의 예</span><span class="sxs-lookup"><span data-stu-id="afa5c-130">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="afa5c-131">category</span><span class="sxs-lookup"><span data-stu-id="afa5c-131">category</span></span> | <span data-ttu-id="afa5c-132">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-132">String</span></span> | <span data-ttu-id="afa5c-133">재구성 활동 범주(소프트웨어/보안 구성)</span><span class="sxs-lookup"><span data-stu-id="afa5c-133">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="afa5c-134">소프트웨어</span><span class="sxs-lookup"><span data-stu-id="afa5c-134">Software</span></span>
<span data-ttu-id="afa5c-135">completerEmail</span><span class="sxs-lookup"><span data-stu-id="afa5c-135">completerEmail</span></span> | <span data-ttu-id="afa5c-136">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-136">String</span></span> | <span data-ttu-id="afa5c-137">누군가가 수정 작업을 수동으로 완료한 경우 이 열에 전자 메일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afa5c-137">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="afa5c-138">null</span><span class="sxs-lookup"><span data-stu-id="afa5c-138">null</span></span>
<span data-ttu-id="afa5c-139">completerId</span><span class="sxs-lookup"><span data-stu-id="afa5c-139">completerId</span></span> | <span data-ttu-id="afa5c-140">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-140">String</span></span> | <span data-ttu-id="afa5c-141">누군가가 수정 작업을 수동으로 완료한 경우 이 열에는 해당 개체 ID가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afa5c-141">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="afa5c-142">null</span><span class="sxs-lookup"><span data-stu-id="afa5c-142">null</span></span>
<span data-ttu-id="afa5c-143">completionMethod</span><span class="sxs-lookup"><span data-stu-id="afa5c-143">completionMethod</span></span> | <span data-ttu-id="afa5c-144">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-144">String</span></span> | <span data-ttu-id="afa5c-145">재구성 활동은 "자동으로"(모든 장치가 패치된 경우) 또는 "완료된 것으로 표시"를 선택한 사람이 "수동으로" 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afa5c-145">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="afa5c-146">자동</span><span class="sxs-lookup"><span data-stu-id="afa5c-146">Automatic</span></span>
<span data-ttu-id="afa5c-147">createdOn</span><span class="sxs-lookup"><span data-stu-id="afa5c-147">createdOn</span></span> | <span data-ttu-id="afa5c-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="afa5c-148">DateTime</span></span> | <span data-ttu-id="afa5c-149">이 수정 활동이 만들어진 시간</span><span class="sxs-lookup"><span data-stu-id="afa5c-149">Time this remediation activity was created</span></span> | <span data-ttu-id="afa5c-150">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="afa5c-150">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="afa5c-151">설명</span><span class="sxs-lookup"><span data-stu-id="afa5c-151">description</span></span> | <span data-ttu-id="afa5c-152">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-152">String</span></span> | <span data-ttu-id="afa5c-153">이 수정 활동에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="afa5c-153">Description of this remediation activity</span></span> | <span data-ttu-id="afa5c-154">장치에 영향을 주는 알려진 취약점을 완화하기 위해 Microsoft Silverlight를 이후 버전으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="afa5c-154">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="afa5c-155">dueOn</span><span class="sxs-lookup"><span data-stu-id="afa5c-155">dueOn</span></span> | <span data-ttu-id="afa5c-156">DateTime</span><span class="sxs-lookup"><span data-stu-id="afa5c-156">DateTime</span></span> | <span data-ttu-id="afa5c-157">이 수정 활동에 대한 작성자가 설정한 기한</span><span class="sxs-lookup"><span data-stu-id="afa5c-157">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="afa5c-158">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="afa5c-158">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="afa5c-159">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="afa5c-159">fixedDevices</span></span> | <span data-ttu-id="afa5c-160">.</span><span class="sxs-lookup"><span data-stu-id="afa5c-160">.</span></span> | <span data-ttu-id="afa5c-161">고정된 장치 수</span><span class="sxs-lookup"><span data-stu-id="afa5c-161">The number of devices that have been fixed</span></span> | <span data-ttu-id="afa5c-162">2</span><span class="sxs-lookup"><span data-stu-id="afa5c-162">2</span></span>
<span data-ttu-id="afa5c-163">id</span><span class="sxs-lookup"><span data-stu-id="afa5c-163">id</span></span> | <span data-ttu-id="afa5c-164">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-164">String</span></span> | <span data-ttu-id="afa5c-165">이 수정 활동의 ID</span><span class="sxs-lookup"><span data-stu-id="afa5c-165">ID of this remediation activity</span></span> | <span data-ttu-id="afa5c-166">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="afa5c-166">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="afa5c-167">nameId</span><span class="sxs-lookup"><span data-stu-id="afa5c-167">nameId</span></span> | <span data-ttu-id="afa5c-168">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-168">String</span></span> | <span data-ttu-id="afa5c-169">관련 제품 이름</span><span class="sxs-lookup"><span data-stu-id="afa5c-169">Related product name</span></span> | <span data-ttu-id="afa5c-170">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="afa5c-170">Microsoft Silverlight</span></span>
<span data-ttu-id="afa5c-171">priority</span><span class="sxs-lookup"><span data-stu-id="afa5c-171">priority</span></span> | <span data-ttu-id="afa5c-172">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-172">String</span></span> | <span data-ttu-id="afa5c-173">이 수정 활동의 작성자 집합 우선 순위(높음\중간\낮음)</span><span class="sxs-lookup"><span data-stu-id="afa5c-173">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="afa5c-174">높음</span><span class="sxs-lookup"><span data-stu-id="afa5c-174">High</span></span>
<span data-ttu-id="afa5c-175">productId</span><span class="sxs-lookup"><span data-stu-id="afa5c-175">productId</span></span> | <span data-ttu-id="afa5c-176">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-176">String</span></span> | <span data-ttu-id="afa5c-177">관련 제품 ID</span><span class="sxs-lookup"><span data-stu-id="afa5c-177">Related product ID</span></span> | <span data-ttu-id="afa5c-178">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="afa5c-178">microsoft-_-silverlight</span></span>
<span data-ttu-id="afa5c-179">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="afa5c-179">productivityImpactRemediationType</span></span> | <span data-ttu-id="afa5c-180">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-180">String</span></span> | <span data-ttu-id="afa5c-181">사용자 영향이 없는 장치에만 몇 가지 구성 변경을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afa5c-181">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="afa5c-182">이 값은 "노출된 모든 장치" 또는 "사용자 영향이 없는 장치만" 선택을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="afa5c-182">This value indicates the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="afa5c-183">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="afa5c-183">AllExposedAssets</span></span>
<span data-ttu-id="afa5c-184">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="afa5c-184">rbacGroupNames</span></span> | <span data-ttu-id="afa5c-185">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-185">String</span></span> | <span data-ttu-id="afa5c-186">관련 장치 그룹 이름</span><span class="sxs-lookup"><span data-stu-id="afa5c-186">Related device group names</span></span> | <span data-ttu-id="afa5c-187">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="afa5c-187">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="afa5c-188">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="afa5c-188">recommendedProgram</span></span> | <span data-ttu-id="afa5c-189">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-189">String</span></span> | <span data-ttu-id="afa5c-190">업그레이드할 권장 프로그램</span><span class="sxs-lookup"><span data-stu-id="afa5c-190">Recommended program to upgrade to</span></span> | <span data-ttu-id="afa5c-191">null</span><span class="sxs-lookup"><span data-stu-id="afa5c-191">null</span></span>
<span data-ttu-id="afa5c-192">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="afa5c-192">recommendedVendor</span></span> | <span data-ttu-id="afa5c-193">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-193">String</span></span> | <span data-ttu-id="afa5c-194">업그레이드할 권장 공급업체</span><span class="sxs-lookup"><span data-stu-id="afa5c-194">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="afa5c-195">null</span><span class="sxs-lookup"><span data-stu-id="afa5c-195">null</span></span>
<span data-ttu-id="afa5c-196">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="afa5c-196">recommendedVersion</span></span> | <span data-ttu-id="afa5c-197">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-197">String</span></span> | <span data-ttu-id="afa5c-198">업데이트/업그레이드에 권장되는 버전</span><span class="sxs-lookup"><span data-stu-id="afa5c-198">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="afa5c-199">null</span><span class="sxs-lookup"><span data-stu-id="afa5c-199">null</span></span>
<span data-ttu-id="afa5c-200">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="afa5c-200">relatedComponent</span></span> | <span data-ttu-id="afa5c-201">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-201">String</span></span> | <span data-ttu-id="afa5c-202">이 수정 작업의 관련 구성 요소(보안 권장에 대한 관련 구성 요소와 유사)</span><span class="sxs-lookup"><span data-stu-id="afa5c-202">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="afa5c-203">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="afa5c-203">Microsoft Silverlight</span></span>
<span data-ttu-id="afa5c-204">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="afa5c-204">requesterEmail</span></span> | <span data-ttu-id="afa5c-205">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-205">String</span></span> | <span data-ttu-id="afa5c-206">작성자 전자 메일 주소</span><span class="sxs-lookup"><span data-stu-id="afa5c-206">Creator email address</span></span> | <span data-ttu-id="afa5c-207">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="afa5c-207">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="afa5c-208">requesterId</span><span class="sxs-lookup"><span data-stu-id="afa5c-208">requesterId</span></span> | <span data-ttu-id="afa5c-209">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-209">String</span></span> | <span data-ttu-id="afa5c-210">Creator 개체 ID</span><span class="sxs-lookup"><span data-stu-id="afa5c-210">Creator object id</span></span> | <span data-ttu-id="afa5c-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="afa5c-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="afa5c-212">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="afa5c-212">requesterNotes</span></span> | <span data-ttu-id="afa5c-213">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-213">String</span></span> | <span data-ttu-id="afa5c-214">이 수정 활동에 대해 작성자가 추가한 메모(무료 텍스트)</span><span class="sxs-lookup"><span data-stu-id="afa5c-214">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="afa5c-215">null</span><span class="sxs-lookup"><span data-stu-id="afa5c-215">null</span></span>
<span data-ttu-id="afa5c-216">scid</span><span class="sxs-lookup"><span data-stu-id="afa5c-216">scid</span></span> | <span data-ttu-id="afa5c-217">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-217">String</span></span> | <span data-ttu-id="afa5c-218">관련 보안 권장 정보의 SCID</span><span class="sxs-lookup"><span data-stu-id="afa5c-218">SCID of the related security recommendation</span></span> | <span data-ttu-id="afa5c-219">null</span><span class="sxs-lookup"><span data-stu-id="afa5c-219">null</span></span>
<span data-ttu-id="afa5c-220">status</span><span class="sxs-lookup"><span data-stu-id="afa5c-220">status</span></span> | <span data-ttu-id="afa5c-221">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-221">String</span></span> | <span data-ttu-id="afa5c-222">재구성 활동 상태(활성/완료)</span><span class="sxs-lookup"><span data-stu-id="afa5c-222">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="afa5c-223">활성</span><span class="sxs-lookup"><span data-stu-id="afa5c-223">Active</span></span>
<span data-ttu-id="afa5c-224">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="afa5c-224">statusLastModifiedOn</span></span> | <span data-ttu-id="afa5c-225">DateTime</span><span class="sxs-lookup"><span data-stu-id="afa5c-225">DateTime</span></span> | <span data-ttu-id="afa5c-226">상태 필드가 업데이트된 날짜</span><span class="sxs-lookup"><span data-stu-id="afa5c-226">Date when the status field was updated</span></span> | <span data-ttu-id="afa5c-227">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="afa5c-227">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="afa5c-228">targetDevices</span><span class="sxs-lookup"><span data-stu-id="afa5c-228">targetDevices</span></span> | <span data-ttu-id="afa5c-229">Long</span><span class="sxs-lookup"><span data-stu-id="afa5c-229">Long</span></span> | <span data-ttu-id="afa5c-230">이 수정을 적용할 수 있는 노출된 장치 수</span><span class="sxs-lookup"><span data-stu-id="afa5c-230">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="afa5c-231">43</span><span class="sxs-lookup"><span data-stu-id="afa5c-231">43</span></span>
<span data-ttu-id="afa5c-232">title</span><span class="sxs-lookup"><span data-stu-id="afa5c-232">title</span></span> | <span data-ttu-id="afa5c-233">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-233">String</span></span> | <span data-ttu-id="afa5c-234">이 수정 활동의 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="afa5c-234">Title of this remediation activity</span></span> | <span data-ttu-id="afa5c-235">Microsoft Silverlight 업데이트</span><span class="sxs-lookup"><span data-stu-id="afa5c-235">Update Microsoft Silverlight</span></span>
<span data-ttu-id="afa5c-236">type</span><span class="sxs-lookup"><span data-stu-id="afa5c-236">type</span></span> | <span data-ttu-id="afa5c-237">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-237">String</span></span> | <span data-ttu-id="afa5c-238">수정 유형</span><span class="sxs-lookup"><span data-stu-id="afa5c-238">Remediation type</span></span> | <span data-ttu-id="afa5c-239">업데이트</span><span class="sxs-lookup"><span data-stu-id="afa5c-239">Update</span></span>
<span data-ttu-id="afa5c-240">vendorId</span><span class="sxs-lookup"><span data-stu-id="afa5c-240">vendorId</span></span> | <span data-ttu-id="afa5c-241">String</span><span class="sxs-lookup"><span data-stu-id="afa5c-241">String</span></span> | <span data-ttu-id="afa5c-242">관련 공급업체 이름</span><span class="sxs-lookup"><span data-stu-id="afa5c-242">Related vendor name</span></span> | <span data-ttu-id="afa5c-243">Microsoft</span><span class="sxs-lookup"><span data-stu-id="afa5c-243">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="afa5c-244">예시</span><span class="sxs-lookup"><span data-stu-id="afa5c-244">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="afa5c-245">요청 예제</span><span class="sxs-lookup"><span data-stu-id="afa5c-245">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a><span data-ttu-id="afa5c-246">응답 예제</span><span class="sxs-lookup"><span data-stu-id="afa5c-246">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="afa5c-247">참고 항목</span><span class="sxs-lookup"><span data-stu-id="afa5c-247">See also</span></span>

- [<span data-ttu-id="afa5c-248">수정 방법 및 속성</span><span class="sxs-lookup"><span data-stu-id="afa5c-248">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="afa5c-249">ID로 수정 작업 1개 가져오기</span><span class="sxs-lookup"><span data-stu-id="afa5c-249">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="afa5c-250">한 번의 수정 작업이 있는 노출된 장치 목록</span><span class="sxs-lookup"><span data-stu-id="afa5c-250">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="afa5c-251">위험 기반 위협 & 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="afa5c-251">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="afa5c-252">조직의 취약성</span><span class="sxs-lookup"><span data-stu-id="afa5c-252">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
