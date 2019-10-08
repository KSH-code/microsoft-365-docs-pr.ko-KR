---
title: Microsoft 준수 관리자 릴리스 정보
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
ms.openlocfilehash: 3646d86cd9edac95975958458eb52a44fe30d2f5
ms.sourcegitcommit: 15173ab87325b7d79bab683702b35d77a355cd6b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2019
ms.locfileid: "37417507"
---
# <a name="release-notes-for-compliance-manager-preview"></a><span data-ttu-id="e6e16-104">준수 관리자를 위한 릴리스 정보 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="e6e16-104">Release Notes for Compliance Manager (Preview)</span></span>

<span data-ttu-id="e6e16-105">준수 관리자의 공개 미리 보기는 예정 된 기능과 업데이트에 빠르게 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-105">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="e6e16-106">[서비스 트러스트 포털](https://servicetrust.microsoft.com) 에서 업데이트 된 [준수 관리자](https://servicetrust.microsoft.com/ComplianceManager) 도구를 사용 하 여 Microsoft 클라우드 서비스와 관련 된 규정 준수 활동을 추적, 할당 및 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-106">You can use the updated [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="whats-new-in-compliance-manager-preview"></a><span data-ttu-id="e6e16-107">준수 관리자의 새로운 기능 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="e6e16-107">What’s new in Compliance Manager (Preview)</span></span>

- <span data-ttu-id="e6e16-108">**준수 관리자에 대 한 역할 기반 액세스:** 기본 **추측 액세스** 역할이 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-108">**Role-based access to Compliance Manager:** The default **Guess access** role has been removed.</span></span> <span data-ttu-id="e6e16-109">사용자가 준수 관리자에 액세스 하려면 전역 관리자가 각 사용자에 게 [권한을 할당](compliance-manager-overview#permissions.md)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-109">In order for a user to access Compliance Manager, the global admin must [assign each user a permission](compliance-manager-overview#permissions.md).</span></span>

- <span data-ttu-id="e6e16-110">**Microsoft 보안 점수와의 통합:** 준수 관리자는 고객 관리 작업을 50 이상의 보안 점수 작업에 매핑하여 [Microsoft 보안 점수](../security/mtp/microsoft-secure-score.md) 와의 통합을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-110">**Integration with Microsoft Secure Score:** Compliance Manager supports integration with [Microsoft Secure Score](../security/mtp/microsoft-secure-score.md) by mapping customer-managed Actions to more than 50 Secure Score actions.</span></span> <span data-ttu-id="e6e16-111">보안 점수에서 매핑된 작업을 완료 하면 해당 준수 관리자 작업이 자동으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-111">When you complete a mapped action in Secure Score, the corresponding Compliance Manager Action automatically updates.</span></span>

- <span data-ttu-id="e6e16-112">**사용자 지정 평가 가져오기:** 이제 준수 관리자는 기본 제공 평가 외에 사용자 지정 서식 파일 가져오기를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-112">**Import custom Assessments:** In addition to built-in Assessments, Compliance Manager now supports importing custom Templates.</span></span> <span data-ttu-id="e6e16-113">모든 제품 또는 서비스에 대 한 사용자 지정 평가와 모든 표준/규제를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-113">You can create custom Assessments for any product or service and any standard or regulation.</span></span>

- <span data-ttu-id="e6e16-114">**작업 항목:** 작업 항목은 이제 개별 항목이 며 Microsoft 보안 점수 그래프 API의 많은 원격 분석 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-114">**Actions Items:** Action Items are now individual items and many include telemetry collection from the Microsoft Secure Score Graph API.</span></span> <span data-ttu-id="e6e16-115">가능한 경우 기술 작업 권장 사항에는 이제 Office 365 서비스의 해당 구성 페이지에 대 한 링크가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-115">Where possible, technical action recommendations now have links to the applicable configuration page in the Office 365 service.</span></span>

- <span data-ttu-id="e6e16-116">**테 넌 트 관리:** 준수 관리자의 새 데이터 요소를 관리 하기 위한 새 인터페이스 (미리 보기):</span><span class="sxs-lookup"><span data-stu-id="e6e16-116">**Tenant Management:** New interface for managing new data elements in Compliance Manager (Preview):</span></span>
    - <span data-ttu-id="e6e16-117">**차원:** 필터의 사용자 지정 피벗을 만들 수 있는 템플릿, 평가 및 작업 항목에 대 한 메타 데이터를 보고, 추가 하 고, 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-117">**Dimensions:** View, add and customize metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
    - <span data-ttu-id="e6e16-118">**소유자:** 각 작업 항목의 소유자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-118">**Owners:** Specify an owner for each Action Item.</span></span>
    - <span data-ttu-id="e6e16-119">**고객 작업:** 준수 관리자 (미리 보기)에 포함 된 작업 항목의 전체 목록과 보안 점수와 통합 된 작업 항목에 대 한 보안 점수 모니터링 사용/사용 안 함을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-119">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Action Items integrated with Secure Score.</span></span>

- <span data-ttu-id="e6e16-120">**업데이트 된 준수 점수**: 방법론은 Microsoft 보안 점수와의 동기화를 지원 하기 위해 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-120">**Updated Compliance Score**: The methodology has changed to support syncing with Microsoft Secure Score.</span></span> <span data-ttu-id="e6e16-121">점수는 Microsoft가 관리 하는 작업 점수 및 고객 관리 작업 점수를 기반으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-121">The score is calculated based on Microsoft-managed action scores and customer-managed action scores.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="e6e16-122">준수 관리자의 알려진 문제 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="e6e16-122">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="e6e16-123">다음 섹션에서는 이후의 준수 관리자 릴리스에서 해결 해야 할 알려진 문제에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-123">The following sections cover known issues to be resolved in upcoming releases of Compliance Manager.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="e6e16-124">준수 점수</span><span class="sxs-lookup"><span data-stu-id="e6e16-124">Compliance Score</span></span>

- <span data-ttu-id="e6e16-125">**범위 내에 없는**것으로 표시 된 작업 항목의 경우에는 작업 항목에 할당 되는 점수가 준수 점수 계산에서 제외 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-125">For Action Items marked as **Not in Scope**, the score assigned to the Action Item is not excluded from the Compliance Score calculation.</span></span> <span data-ttu-id="e6e16-126">**범위에 없는** 것으로 표시 된 작업 항목은 준수 점수가 증가 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-126">Action Items marked **Not in Scope** do not increase your Compliance Score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="e6e16-127">보안 점수</span><span class="sxs-lookup"><span data-stu-id="e6e16-127">Secure Score</span></span>

- <span data-ttu-id="e6e16-128">특정 Microsoft 365 및 Office 365 구독의 일부 작업 항목에는 보안 점수 결과를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-128">Secure Score results are not available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="e6e16-129">이러한 경우에는 보안 점수 결과를 ' 검색할 수 없습니다 ' 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-129">The Secure Score result is 'Could not be detected' in these cases.</span></span>
- <span data-ttu-id="e6e16-130">경우에 따라 해당 정책에 대 한 보안 점수 결과가 반환 되 고 작업 항목이 완료 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-130">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>

### <a name="microsoft-managed-controls"></a><span data-ttu-id="e6e16-131">Microsoft 관리 컨트롤</span><span class="sxs-lookup"><span data-stu-id="e6e16-131">Microsoft-managed Controls</span></span>

- <span data-ttu-id="e6e16-132">Microsoft 관리 컨트롤에 대 한 테스트 날짜는 평가에 포함 된 경우에도 UI에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-132">The test date for Microsoft-managed controls is not appearing in the UI, even when included in the Assessment.</span></span> <span data-ttu-id="e6e16-133">테스트 날짜 정보를 보려면 평가를 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-133">To see test date information, you must export the Assessment.</span></span>

### <a name="customization"></a><span data-ttu-id="e6e16-134">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="e6e16-134">Customization</span></span>

- <span data-ttu-id="e6e16-135">사용자 지정 컨트롤을 추가 하면 기존 컨트롤 패밀리에 새 컨트롤을 추가할 수 있지만 새 컨트롤 패밀리를 추가할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-135">Adding custom Controls enables adding a new control to an existing control family, but it does not allow you to add a new Control Family.</span></span>
- <span data-ttu-id="e6e16-136">이 릴리스는 작업 항목을 연결 하거나 평가에 작업 항목 또는 컨트롤을 추가 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-136">This release does not support linking Action Items or adding Actions Items or Controls to an Assessment.</span></span>
- <span data-ttu-id="e6e16-137">사용자 지정 동작을 만드는 경우에는 편집 하거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-137">If you create a custom Action, you cannot edit or delete it.</span></span>

### <a name="control-families-not-shown-in-assessments"></a><span data-ttu-id="e6e16-138">평가에 표시 되지 않는 컨트롤 패밀리</span><span class="sxs-lookup"><span data-stu-id="e6e16-138">Control Families Not Shown in Assessments</span></span>

- <span data-ttu-id="e6e16-139">템플릿을 가져올 때 해당 서식 파일을 기반으로 하는 모든 평가는 서식 파일에 포함 된 모든 컨트롤 패밀리를 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-139">When you import a Template, all Assessments based on that Template reflect all Control Families that are part of the Template.</span></span> <span data-ttu-id="e6e16-140">그러나 서식 파일에 새 컨트롤 패밀리를 추가 하는 경우 기존 평가에 변경 내용이 반영 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-140">But if you add new Control Families to the Template, any existing Assessments will not reflect the changes.</span></span> <span data-ttu-id="e6e16-141">업데이트 된 서식 파일에서 만든 새 평가에만 변경 내용이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-141">Only new Assessments created off the updated Template reflect the changes.</span></span>

### <a name="filters"></a><span data-ttu-id="e6e16-142">필터</span><span class="sxs-lookup"><span data-stu-id="e6e16-142">Filters</span></span>

- <span data-ttu-id="e6e16-143">작업 항목이 나 컨트롤을 필터링 하면 정확 하 게 올바른 결과가 생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-143">Filtering on Action Items or Controls does not consistently produce correct results.</span></span>

### <a name="templates"></a><span data-ttu-id="e6e16-144">템플릿</span><span class="sxs-lookup"><span data-stu-id="e6e16-144">Templates</span></span>

- <span data-ttu-id="e6e16-145">보관 된 템플릿은 편집이 가능 하 고 편집이 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-145">Archived templates are editable and they should not be editable.</span></span>
- <span data-ttu-id="e6e16-146">잠긴 템플릿을 사용 하면 평가를 수행 하지 않아야 할 때 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-146">Locked templates allow for Assessment creation when they should not.</span></span> <span data-ttu-id="e6e16-147">템플릿을 잠그면 평가를 만드는 데 사용 되는 것을 방지 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-147">Locking a Template is meant to prevent it from being used to create Assessments.</span></span>

### <a name="export"></a><span data-ttu-id="e6e16-148">내보내기</span><span class="sxs-lookup"><span data-stu-id="e6e16-148">Export</span></span>

- <span data-ttu-id="e6e16-149">서식 파일 내보내기가 **가져오기** 또는 **보류 중인 승인**으로 설정 된 경우 JSON으로 내보내기 작업이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-149">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="e6e16-150">지원되는 브라우저</span><span class="sxs-lookup"><span data-stu-id="e6e16-150">Supported browsers</span></span>

- <span data-ttu-id="e6e16-151">최신 버전의 Microsoft Edge, Chrome 및 Safari가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-151">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="e6e16-152">브라우저를 새로 고칠 때까지 업데이트 된 데이터가 표시 되지 않는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-152">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="e6e16-153">Microsoft Edge의 preview 버전은 지원 되지 않지만 알려진 문제는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-153">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="e6e16-154">Internet Explorer가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-154">Internet Explorer is not supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="e6e16-155">세션 제한 시간</span><span class="sxs-lookup"><span data-stu-id="e6e16-155">Session timeout</span></span>

- <span data-ttu-id="e6e16-156">세션 시간이 초과 되 면 "문제가 발생 했습니다." 오류가 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-156">When a session times out, a “Something went wrong” error may appear.</span></span> <span data-ttu-id="e6e16-157">문제를 해결 하려면 [준수 관리자로](https://servicetrust.microsoft.com/ComplianceManager) 이동 하 여 다시 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-157">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="e6e16-158">언어 지원</span><span class="sxs-lookup"><span data-stu-id="e6e16-158">Language support</span></span>

- <span data-ttu-id="e6e16-159">모든 언어는 일부 웹 페이지에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-159">All languages are not supported for all webpages.</span></span> <span data-ttu-id="e6e16-160">로컬 언어가 지원 되지 않으면 영어 (미국)로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e16-160">If your local language is unsupported, view in US English.</span></span>