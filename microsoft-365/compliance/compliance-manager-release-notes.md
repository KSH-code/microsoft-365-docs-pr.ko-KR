---
title: Microsoft 준수 관리자 릴리스 정보
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 준수 관리자는 Microsoft Service Trust Portal의 무료 워크플로 기반 위험 평가 도구입니다. 준수 관리자를 사용 하면 Microsoft 클라우드 서비스와 관련 된 규정 준수 활동을 추적, 할당 및 확인할 수 있습니다.
ms.openlocfilehash: c3d0efbfcf58eb001d2df5832439c22c7cc662aa
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595785"
---
# <a name="release-notes-for-compliance-manager-preview"></a><span data-ttu-id="ef517-104">준수 관리자를 위한 릴리스 정보 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="ef517-104">Release Notes for Compliance Manager (Preview)</span></span>

<span data-ttu-id="ef517-105">준수 관리자의 공개 미리 보기는 예정 된 기능과 업데이트에 빠르게 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-105">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="ef517-106">[서비스 트러스트 포털](https://servicetrust.microsoft.com) 에서 업데이트 된 [준수 관리자](https://servicetrust.microsoft.com/ComplianceManager) 도구를 사용 하 여 Microsoft 클라우드 서비스와 관련 된 규정 준수 활동을 추적, 할당 및 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-106">You can use the updated [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="whats-new-in-compliance-manager-preview"></a><span data-ttu-id="ef517-107">준수 관리자의 새로운 기능 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="ef517-107">What’s new in Compliance Manager (Preview)</span></span>

- <span data-ttu-id="ef517-108">**준수 관리자에 대 한 역할 기반 액세스:** 기본 **게스트 액세스** 역할이 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-108">**Role-based access to Compliance Manager:** The default **Guest access** role has been removed.</span></span> <span data-ttu-id="ef517-109">사용자가 준수 관리자에 액세스 하려면 전역 관리자가 각 사용자에 게 [권한을 할당](compliance-manager-overview.md#permissions)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-109">In order for a user to access Compliance Manager, the global admin must [assign each user a permission](compliance-manager-overview.md#permissions).</span></span>

- <span data-ttu-id="ef517-110">**업데이트 된 준수 점수**: 준수 점수가 이제 Microsoft 관리 작업에 대 한 점수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-110">**Updated Compliance Score**: Compliance Score now includes scores for Microsoft-managed actions.</span></span> <span data-ttu-id="ef517-111">결과적으로 점수가 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-111">Your score will increase as a result.</span></span>

- <span data-ttu-id="ef517-112">**작업 항목:** 작업 항목은 이제 개별 항목이 며 Microsoft 보안 점수 그래프 API의 많은 원격 분석 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-112">**Actions Items:** Action Items are now individual items and many include telemetry collection from the Microsoft Secure Score Graph API.</span></span> <span data-ttu-id="ef517-113">가능한 경우 기술 작업 권장 사항에는 이제 Office 365 서비스의 해당 구성 페이지에 대 한 링크가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-113">Where possible, technical action recommendations now have links to the applicable configuration page in the Office 365 service.</span></span>

- <span data-ttu-id="ef517-114">**테 넌 트 관리:** 준수 관리자의 새 데이터 요소를 관리 하기 위한 새 인터페이스 (미리 보기):</span><span class="sxs-lookup"><span data-stu-id="ef517-114">**Tenant Management:** New interface for managing new data elements in Compliance Manager (Preview):</span></span>
    - <span data-ttu-id="ef517-115">**차원:** 필터의 사용자 지정 피벗을 만들 수 있는 템플릿, 평가 및 작업 항목에 대 한 메타 데이터를 보고, 추가 하 고, 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-115">**Dimensions:** View, add and customize metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
    - <span data-ttu-id="ef517-116">**소유자:** 각 작업 항목의 소유자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-116">**Owners:** Specify an owner for each Action Item.</span></span>
    - <span data-ttu-id="ef517-117">**고객 작업:** 준수 관리자 (미리 보기)에 포함 된 작업 항목의 전체 목록과 보안 점수와 통합 된 작업 항목에 대 한 보안 점수 모니터링 사용/사용 안 함을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-117">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Action Items integrated with Secure Score.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="ef517-118">준수 관리자의 알려진 문제 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="ef517-118">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="ef517-119">다음 섹션에서는 이후의 준수 관리자 릴리스에서 해결 해야 할 알려진 문제에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-119">The following sections cover known issues to be resolved in upcoming releases of Compliance Manager.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="ef517-120">준수 점수</span><span class="sxs-lookup"><span data-stu-id="ef517-120">Compliance Score</span></span>

- <span data-ttu-id="ef517-121">**범위 내에 없는**것으로 표시 된 작업 항목의 경우에는 작업 항목에 할당 되는 점수가 준수 점수 계산에서 제외 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-121">For Action Items marked as **Not in Scope**, the score assigned to the Action Item isn't excluded from the compliance score calculation.</span></span> <span data-ttu-id="ef517-122">**범위에 없는** 것으로 표시 된 작업 항목은 준수 점수가 증가 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-122">Action Items marked **Not in Scope** don't increase your compliance score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="ef517-123">보안 점수</span><span class="sxs-lookup"><span data-stu-id="ef517-123">Secure Score</span></span>

- <span data-ttu-id="ef517-124">특정 Microsoft 365 및 Office 365 구독의 일부 작업 항목에는 보안 점수 결과를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-124">Secure Score results aren't available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="ef517-125">이러한 경우에는 보안 점수 결과를 **검색할** 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-125">The Secure Score result is **Could not be detected** in these cases.</span></span>
- <span data-ttu-id="ef517-126">경우에 따라 해당 정책에 대 한 보안 점수 결과가 반환 되 고 작업 항목이 완료 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-126">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>
- <span data-ttu-id="ef517-127">새 테 넌 트의 경우 모든 작업에 대 한 보안 점수 업데이트가 자동으로 켜 집니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-127">For new tenants, Secure Score updates for all actions is automatically turned on.</span></span> <span data-ttu-id="ef517-128">전역 관리자는 보안 점수 연속 업데이트 스위치를 off로 설정 하 여 모든 작업에 대 한 업데이트를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-128">The global administrator can set the Secure Score continuous update switch to off, which turns off updates for all actions.</span></span>
  - <span data-ttu-id="ef517-129">**참고**: 조직에서 Microsoft 365 또는 Office 365를 처음 배포 하는 경우 보안 점수가 약 7 일인 경우에만 데이터를 완벽 하 게 수집 하 고 해당 점수를 요소에 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-129">**Note**: when organizations first deploy Microsoft 365 or Office 365, it takes approximately seven days for Secure Score to fully collect data and factor it into your score.</span></span> <span data-ttu-id="ef517-130">이 시간 동안에는 보안 점수 연속 업데이트 스위치를 **Off** 로 설정 하 고, 수동으로 작업을 수행 하도록 **설정 하면 점수를 받을 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-130">During that time, setting the Secure Score continuous update switch to **Off** and manually setting an action to **implemented** will count that action toward your score.</span></span> <span data-ttu-id="ef517-131">초기 7 일이 지나면 보안 점수 연속 업데이트를 다시 설정 하면 해당 시점부터의 지속적인 모니터링이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-131">After the initial seven days, turning Secure Score continuous update back on will enable continuous monitoring from that point forward.</span></span>
- <span data-ttu-id="ef517-132">보안 점수 업데이트가 설정 되 면 작업의 테스트 날짜가 모니터링을 반영 하도록 업데이트 되지 않더라도 작업은 보안 점수에 의해 적극적으로 모니터링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-132">When Secure Score updates are turned on, actions are actively monitored by Secure Score, although the action’s test date won't be updated to reflect monitoring.</span></span>
- <span data-ttu-id="ef517-133">새 평가를 만들 때 점수에는 Microsoft가 관리 하는 제어 점수와 보안 점수 통합이 자동으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-133">When new assessments are created, scores automatically include Microsoft-managed control scores and Secure Score integration.</span></span>
- <span data-ttu-id="ef517-134">보안 점수 통합에서 지원 되지 않는 모든 작업은 수동으로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-134">Any actions that are not supported by Secure Score integration can be manually implemented.</span></span> <span data-ttu-id="ef517-135">수동 구현은 해당 작업 그룹의 점수를 발생 시키는 기능을 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-135">A manual implementation will factor into the score for that action's group.</span></span>

### <a name="microsoft-managed-controls"></a><span data-ttu-id="ef517-136">Microsoft 관리 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ef517-136">Microsoft-managed controls</span></span>

- <span data-ttu-id="ef517-137">Microsoft 관리 컨트롤에 대 한 테스트 날짜는 평가에 포함 된 경우에도 UI에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-137">The test date for Microsoft-managed controls isn't appearing in the UI, even when included in the Assessment.</span></span> <span data-ttu-id="ef517-138">테스트 날짜 정보를 보려면 평가를 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-138">To see test date information, you must export the Assessment.</span></span>

### <a name="customization"></a><span data-ttu-id="ef517-139">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ef517-139">Customization</span></span>

- <span data-ttu-id="ef517-140">사용자 지정 컨트롤을 추가 하면 기존 컨트롤 패밀리에 새 컨트롤을 추가할 수 있지만 새 컨트롤 패밀리를 추가할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-140">Adding custom Controls enables adding a new control to an existing control family, but it doesn't allow you to add a new Control Family.</span></span>
- <span data-ttu-id="ef517-141">이 릴리스는 작업 항목을 연결 하거나 평가에 작업 항목 또는 컨트롤을 추가 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-141">This release doesn't support linking Action Items or adding Actions Items or Controls to an Assessment.</span></span>
- <span data-ttu-id="ef517-142">사용자 지정 동작을 만드는 경우에는 편집 하거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-142">If you create a custom Action, you can't edit or delete it.</span></span>

### <a name="control-families-not-shown-in-assessments"></a><span data-ttu-id="ef517-143">평가에 표시 되지 않는 컨트롤 패밀리</span><span class="sxs-lookup"><span data-stu-id="ef517-143">Control Families Not Shown in Assessments</span></span>

- <span data-ttu-id="ef517-144">템플릿을 가져올 때 해당 서식 파일을 기반으로 하는 모든 평가는 서식 파일에 포함 된 모든 컨트롤 패밀리를 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-144">When you import a Template, all Assessments based on that Template reflect all Control Families that are part of the Template.</span></span> <span data-ttu-id="ef517-145">그러나 서식 파일에 새 컨트롤 패밀리를 추가 하는 경우 기존 평가에서 변경 내용이 반영 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-145">But if you add new Control Families to the Template, any existing Assessments won't reflect the changes.</span></span> <span data-ttu-id="ef517-146">업데이트 된 서식 파일에서 만든 새 평가에만 변경 내용이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-146">Only new Assessments created off the updated Template reflect the changes.</span></span>

### <a name="templates"></a><span data-ttu-id="ef517-147">템플릿</span><span class="sxs-lookup"><span data-stu-id="ef517-147">Templates</span></span>

- <span data-ttu-id="ef517-148">서식 파일을 만들 때는 **제품** 및 **인증** 에 대 한 차원을 모두 포함 하 여 서식 파일이 준수 점수에 표시 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-148">When creating a template, you must include Dimensions for both **Product** and **Certification** to ensure your template displays in Compliance Score.</span></span>
- <span data-ttu-id="ef517-149">보관 된 템플릿은 편집이 가능 하며 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-149">Archived templates are editable and they shouldn't be editable.</span></span>
- <span data-ttu-id="ef517-150">잠긴 템플릿을 사용 하면 평가할 때 평가를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-150">Locked templates allow for Assessment creation when they shouldn't.</span></span> <span data-ttu-id="ef517-151">템플릿을 잠그면 평가를 만드는 데 사용 되는 것을 방지 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-151">Locking a Template is meant to prevent it from being used to create Assessments.</span></span>

### <a name="export"></a><span data-ttu-id="ef517-152">내보내기</span><span class="sxs-lookup"><span data-stu-id="ef517-152">Export</span></span>

- <span data-ttu-id="ef517-153">서식 파일 내보내기가 **가져오기** 또는 **보류 중인 승인**으로 설정 된 경우 JSON으로 내보내기 작업이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-153">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="ef517-154">지원되는 브라우저</span><span class="sxs-lookup"><span data-stu-id="ef517-154">Supported browsers</span></span>

- <span data-ttu-id="ef517-155">최신 버전의 Microsoft Edge, Chrome 및 Safari가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-155">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="ef517-156">브라우저를 새로 고칠 때까지 업데이트 된 데이터가 표시 되지 않는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-156">There may be instances where updated data doesn't appear until your browser is refreshed.</span></span>
- <span data-ttu-id="ef517-157">Microsoft Edge의 미리 보기 버전은 지원 되지 않지만 알려진 문제는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-157">The preview version of Microsoft Edge isn't supported but has no known issues.</span></span>
- <span data-ttu-id="ef517-158">Internet Explorer가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-158">Internet Explorer isn't supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="ef517-159">세션 제한 시간</span><span class="sxs-lookup"><span data-stu-id="ef517-159">Session timeout</span></span>

- <span data-ttu-id="ef517-160">세션 시간이 초과 되 면 "문제가 발생 했습니다." 오류가 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-160">When a session times out, a “Something went wrong” error may appear.</span></span> <span data-ttu-id="ef517-161">문제를 해결 하려면 [준수 관리자로](https://servicetrust.microsoft.com/ComplianceManager) 이동 하 여 다시 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-161">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="ef517-162">언어 지원</span><span class="sxs-lookup"><span data-stu-id="ef517-162">Language support</span></span>

- <span data-ttu-id="ef517-163">모든 언어는 모든 웹 페이지에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-163">All languages aren't supported for all webpages.</span></span> <span data-ttu-id="ef517-164">로컬 언어가 지원 되지 않으면 영어 (미국)로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef517-164">If your local language is unsupported, view in US English.</span></span>