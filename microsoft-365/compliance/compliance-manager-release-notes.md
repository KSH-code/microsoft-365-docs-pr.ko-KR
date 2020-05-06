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
ms.custom:
- seo-marvel-mar2020
description: Microsoft 준수 관리자에서 새로운 기능과 알려진 문제에 대 한 정보가 포함 된 릴리스 정보를 확인 하십시오.
ms.openlocfilehash: fb462939ef1b1bf0c6f7f4552359d50645b528f3
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033708"
---
# <a name="microsoft-compliance-manager-preview-release-notes"></a><span data-ttu-id="d839d-103">Microsoft 준수 관리자 (미리 보기) 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="d839d-103">Microsoft Compliance Manager (preview) release notes</span></span>

<span data-ttu-id="d839d-104">준수 관리자의 공개 미리 보기는 예정 된 기능과 업데이트에 빠르게 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-104">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span> <span data-ttu-id="d839d-105">이 페이지에는 현재 릴리스에 대 한 새로운 기능, 향상 된 기능 및 알려진 문제에 대 한 업데이트가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-105">This page contains updates on new features, improved functionality, and known issues with the current release.</span></span>

<span data-ttu-id="d839d-106">[서비스 트러스트 포털](https://servicetrust.microsoft.com) 에서 [준수 관리자](https://servicetrust.microsoft.com/ComplianceManager) 도구를 사용 하 여 Microsoft 클라우드 서비스와 관련 된 규정 준수 활동을 추적, 할당 및 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-106">You can use the [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="improved-template-creation-and-update-process"></a><span data-ttu-id="d839d-107">향상 된 서식 파일 만들기 및 업데이트 프로세스</span><span class="sxs-lookup"><span data-stu-id="d839d-107">Improved template creation and update process</span></span>

<span data-ttu-id="d839d-108">평가를 위해 템플릿 가져오기, 내보내기 및 수정을 위한 프로세스를 업데이트 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-108">We've updated the process for importing, exporting, and modifying templates for assessments.</span></span> <span data-ttu-id="d839d-109">새로운 단순화 된 환경에서는 사용자의 평가를 쉽게 워크플로로 가져오고 업데이트를 유지 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-109">The new, simplified experience will make it easier for you to bring your own assessments into your workflow and keep them updated.</span></span>

### <a name="the-old-process"></a><span data-ttu-id="d839d-110">이전 프로세스</span><span class="sxs-lookup"><span data-stu-id="d839d-110">The old process</span></span>

<span data-ttu-id="d839d-111">준수 관리자에서 템플릿을 만드는 방법은 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-111">There were two ways of creating a template in Compliance Manager.</span></span> <span data-ttu-id="d839d-112">기존 서식 파일을 복사 하거나 Excel 스프레드시트의 템플릿 데이터를 새 서식 파일로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-112">You could copy an existing template, or import template data from an Excel spreadsheet into a new template.</span></span> <span data-ttu-id="d839d-113">**서식 파일** 페이지에서 **+ 서식 파일** 을 선택 하 여 새 서식 파일을 만들려면 이름을 입력 하 고, 차원을 선택 하 고, 특정 서식 및 스키마를 사용 하 여 Excel 파일을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-113">From your **Templates** page, you'd select **+ Add template** to create a brand new template by entering a name, selecting dimensions, and uploading an Excel file with a specific format and schema.</span></span> <span data-ttu-id="d839d-114">또는 **기존 서식 파일에서 복사본** 을 확인 하 고 복사할 서식 파일을 선택한 다음 차원을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-114">Or you could check the **Copy from an existing template** box, select a template to copy, and verify dimensions.</span></span> <span data-ttu-id="d839d-115">디자인 사용자 지정 서식 파일을 만든 후에 **사용자 지정 컨트롤 추가** 를 선택 하 여 시작한 여러 단계 프로세스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-115">Design customization your template required a multi-step process that began by selecting **Add custom control** after creating your template.</span></span>

### <a name="the-new-process"></a><span data-ttu-id="d839d-116">새 프로세스</span><span class="sxs-lookup"><span data-stu-id="d839d-116">The new process</span></span>

<span data-ttu-id="d839d-117">새 템플릿을 쉽게 만들 수 있도록 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-117">We made it easier for you to create new templates.</span></span> <span data-ttu-id="d839d-118">1 단계 **확장** 프로세스에서는 현재 Microsoft 서식 파일에 작업 및 컨트롤이 포함 된 스프레드시트를 추가 하 여 고유한 사용자 지정 버전을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-118">In a one-step **extension** process, you can add a spreadsheet with your actions and controls to an existing Microsoft template to make your own customized version.</span></span> <span data-ttu-id="d839d-119">준수 관리자의 **서식 파일** 페이지에서 **+ 서식 파일 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-119">At your **Templates** page in Compliance Manager, select **+ Add template**.</span></span> <span data-ttu-id="d839d-120">**서식 파일** 플라이 아웃 창에서 **전역 서식 파일에서 확장명 만들기** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-120">On the **Template** flyout pane, select the **Create extension from global template** checkbox.</span></span> <span data-ttu-id="d839d-121">이전 서식 보다 덜 복잡 한 새 Excel 형식으로 사용자 지정 항목을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-121">You can add customizations with a new Excel format that is less complex than the previous one.</span></span> <span data-ttu-id="d839d-122">이 새로운 프로세스는 **기존 서식 파일에서 이전 복사본** 을 교체 하 고 **사용자 지정 컨트롤** 함수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-122">This new process replaces the former **Copy from an existing template** and **Add custom control** functions.</span></span>

<span data-ttu-id="d839d-123">아래에 나와 있는 버전 관리 프로세스를 통해 원래 평가를 업데이트할 때마다 사용자 지정 된 평가는 이러한 업데이트를 상속 하 고 사용자 정의 컨트롤을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-123">Each time the original assessment is updated through the versioning process outlined below, your customized assessment will inherit those updates and keep your custom controls.</span></span>

<span data-ttu-id="d839d-124">또한 기존 서식 파일을 직접 수정 하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-124">It's also easier to modify your own existing templates.</span></span> <span data-ttu-id="d839d-125">서식 파일을 내보내고, 같은 통합 문서를 변경한 다음, 편집한 내용이 저장 된 상태로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-125">You can export your template, make changes in the same workbook, then import it with your edits saved.</span></span>

<span data-ttu-id="d839d-126">이 새 프로세스로 [서식 파일을 만드는](working-with-compliance-manager.md#templates) 방법에 대 한 자세한 지침을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-126">View detailed instructions on [creating templates](working-with-compliance-manager.md#templates) with this new process.</span></span>

## <a name="versioning-notice-and-control"></a><span data-ttu-id="d839d-127">버전 관리 알림 및 제어</span><span class="sxs-lookup"><span data-stu-id="d839d-127">Versioning notice and control</span></span>

<span data-ttu-id="d839d-128">조직은 준수 관리자의 4 월 2020 버전에서 업데이트 된 평가를 받아 인증 및 규정 업데이트를 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-128">Your organization received updated assessments in the April 2020 release of Compliance Manager to help you align with certification and regulation updates.</span></span> <span data-ttu-id="d839d-129">앞으로 이동 하면 **버전 관리 알림을**통해 향후의 모든 업데이트를 이해 하 고 수락할 수 있는 확실 한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-129">Moving forward, we'll provide a clear way for you to understand and accept all future updates through **versioning alerts**.</span></span>

<span data-ttu-id="d839d-130">평가의 템플릿이나 개선 작업에 대 한 업데이트를 사용할 수 있는 경우 알림 아이콘은 업데이트가 준비 되었음을 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-130">Whenever an update is available for an assessment's template or an improvement action, an alert icon notifies you that an update is ready.</span></span> <span data-ttu-id="d839d-131">해당 아이콘을 클릭 하면 팝업 창에서 업데이트에 대해 설명 하 고 사용자에 게 수락을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-131">When you click on that icon, a pop-up window explains the update and prompts you to accept.</span></span> <span data-ttu-id="d839d-132">알림 아이콘을 선택 하면 업데이트 및 수락 여부를 설명 하는 플라이 아웃 창이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-132">Selecting the alert icon reveals a flyout pane explaining the update and prompting you to accept.</span></span> <span data-ttu-id="d839d-133">[평가에 대 한 업데이트 수락](working-with-compliance-manager.md#versioning-alerts-for-assessment-updates)에 대해 더 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="d839d-133">Learn more about [accepting updates to assessments](working-with-compliance-manager.md#versioning-alerts-for-assessment-updates).</span></span>

## <a name="common-actions-will-synch-status-across-groups"></a><span data-ttu-id="d839d-134">일반 작업을 통해 여러 그룹의 상태가 동기화 됨</span><span class="sxs-lookup"><span data-stu-id="d839d-134">Common actions will synch status across groups</span></span>

<span data-ttu-id="d839d-135">조직에 여러 평가 그룹이 있는 경우 **기술** 작업의 동작 (즉, 전체 조직에 영향을 주는 작업)이 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-135">If your organization has multiple groups of assessments, the behavior of **Technical** actions (that is, actions affecting your entire organization) has changed.</span></span> <span data-ttu-id="d839d-136">그룹 간 중복 된 작업은 하나의 단일 작업으로 결합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-136">Any duplicate actions across groups have been combined into one single action.</span></span> <span data-ttu-id="d839d-137">이 단일 작업에는 중복 버전의 업로드 된 모든 메모 및 증거가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-137">That single action contains all uploaded notes and evidence from the duplicate versions.</span></span> <span data-ttu-id="d839d-138">이렇게 변경 하면 기술 작업은 이제 동일한 그룹에 속해 있는 것 처럼 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-138">With this change, technical actions will now behave as they did when they belonged to the same group.</span></span> <span data-ttu-id="d839d-139">이제 하나의 그룹 또는 평가에서 작업에 대 한 변경 내용이 모든 인스턴스에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-139">Any change made to the action in one group or assessment will now be reflected in all instances.</span></span> <span data-ttu-id="d839d-140">**구현 상태**, **구현 날짜**, **테스트 상태**및 **테스트 날짜** 에는 최신 업데이트가 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-140">The **Implementation Status**, **Implementation Date**, **Test Status**, and **Test Date** will reflect the most recent updates.</span></span>

## <a name="language-support"></a><span data-ttu-id="d839d-141">언어 지원</span><span class="sxs-lookup"><span data-stu-id="d839d-141">Language support</span></span>

<span data-ttu-id="d839d-142">현재 준수 관리자는 영어, 중국어 (간체), 중국어 (번체), 프랑스어, 독일어, 이탈리아어, 일본어, 한국어, 포르투갈어 (브라질), 러시아어 및 스페인어의 언어로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-142">Compliance Manager is now available in the following languages in addition to English: Chinese (Simplified), Chinese (Traditional), French, German, Italian, Japanese, Korean, Portuguese (Brazil), Russian, and Spanish.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="d839d-143">준수 관리자의 알려진 문제 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="d839d-143">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="d839d-144">다음 섹션에서는 현재 준수 관리자 릴리스의 알려진 문제에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-144">The following section covers known issues in the current release of Compliance Manager.</span></span>

### <a name="dimension-values"></a><span data-ttu-id="d839d-145">차원 값</span><span class="sxs-lookup"><span data-stu-id="d839d-145">Dimension values</span></span>

<span data-ttu-id="d839d-146">2020 년 4 월 데이터 마이그레이션의 결과로 일부 조직에서는 평가 및 템플릿에서 **제품** 또는 **인증** 값 "custom"을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-146">As a result of data migration during the April 2020 release, some organizations may see a **Product** or **Certification** value of "custom" in their assessments and templates.</span></span> <span data-ttu-id="d839d-147">**제품** 또는 **인증** 필드가 비어 있는 경우이 값은 자동으로 삽입 되며 데이터 워크플로에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-147">This value was inserted automatically if the **Product** or **Certification** fields were blank, and there won't be an effect on data workflows.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="d839d-148">준수 점수</span><span class="sxs-lookup"><span data-stu-id="d839d-148">Compliance Score</span></span>

- <span data-ttu-id="d839d-149">**범위 내에 없는**것으로 표시 된 작업 항목의 경우에는 작업 항목에 할당 되는 점수가 준수 점수 계산에서 제외 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-149">For Action Items marked as **Not in Scope**, the score assigned to the Action Item isn't excluded from the compliance score calculation.</span></span> <span data-ttu-id="d839d-150">**범위에 없는** 것으로 표시 된 작업 항목은 준수 점수가 증가 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-150">Action Items marked **Not in Scope** don't increase your compliance score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="d839d-151">보안 점수</span><span class="sxs-lookup"><span data-stu-id="d839d-151">Secure Score</span></span>

- <span data-ttu-id="d839d-152">특정 Microsoft 365 및 Office 365 구독의 일부 작업 항목에는 보안 점수 결과를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-152">Secure Score results aren't available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="d839d-153">이러한 경우에는 보안 점수 결과를 **검색할** 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-153">The Secure Score result is **Could not be detected** in these cases.</span></span>
- <span data-ttu-id="d839d-154">경우에 따라 해당 정책에 대 한 보안 점수 결과가 반환 되 고 작업 항목이 완료 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-154">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>
- <span data-ttu-id="d839d-155">새 테 넌 트의 경우 모든 작업에 대 한 보안 점수 업데이트가 자동으로 켜 집니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-155">For new tenants, Secure Score updates for all actions are automatically turned on.</span></span> <span data-ttu-id="d839d-156">전역 관리자는 보안 점수 연속 업데이트 스위치를 off로 설정 하 여 모든 작업에 대 한 업데이트를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-156">The global administrator can set the Secure Score continuous update switch to off, which turns off updates for all actions.</span></span>
  - <span data-ttu-id="d839d-157">**참고**: 조직에서 Microsoft 365 또는 Office 365를 처음 배포 하는 경우 보안 점수가 약 7 일인 경우에만 데이터를 완벽 하 게 수집 하 고 해당 점수를 요소에 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-157">**Note**: when organizations first deploy Microsoft 365 or Office 365, it takes approximately seven days for Secure Score to fully collect data and factor it into your score.</span></span> <span data-ttu-id="d839d-158">이 시간 동안에는 보안 점수 연속 업데이트 스위치를 **Off** 로 설정 하 고, 수동으로 작업을 수행 하도록 **설정 하면 점수를 받을 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-158">During that time, setting the Secure Score continuous update switch to **Off** and manually setting an action to **implemented** will count that action toward your score.</span></span> <span data-ttu-id="d839d-159">초기 7 일이 지나면 보안 점수 연속 업데이트를 다시 설정 하면 해당 시점부터의 지속적인 모니터링이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-159">After the initial seven days, turning Secure Score continuous update back on will enable continuous monitoring from that point forward.</span></span>
- <span data-ttu-id="d839d-160">보안 점수 업데이트가 설정 되 면 작업의 테스트 날짜가 모니터링을 반영 하도록 업데이트 되지 않더라도 작업은 보안 점수에 의해 적극적으로 모니터링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-160">When Secure Score updates are turned on, actions are actively monitored by Secure Score, although the action's test date won't be updated to reflect monitoring.</span></span>
- <span data-ttu-id="d839d-161">새 평가를 만들 때 점수에는 Microsoft가 관리 하는 제어 점수와 보안 점수 통합이 자동으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-161">When new assessments are created, scores automatically include Microsoft-managed control scores and Secure Score integration.</span></span>
- <span data-ttu-id="d839d-162">보안 점수 통합에서 지원 되지 않는 모든 작업은 수동으로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-162">Any actions that are not supported by Secure Score integration can be manually implemented.</span></span> <span data-ttu-id="d839d-163">수동 구현은 해당 작업 그룹의 점수를 발생 시키는 기능을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-163">A manual implementation will factor into the score for that action's group.</span></span>

### <a name="export"></a><span data-ttu-id="d839d-164">내보내기</span><span class="sxs-lookup"><span data-stu-id="d839d-164">Export</span></span>

- <span data-ttu-id="d839d-165">서식 파일 내보내기가 **가져오기** 또는 **보류 중인 승인**으로 설정 된 경우 JSON으로 내보내기 작업이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-165">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="d839d-166">지원되는 브라우저</span><span class="sxs-lookup"><span data-stu-id="d839d-166">Supported browsers</span></span>

- <span data-ttu-id="d839d-167">최신 버전의 Microsoft Edge, Chrome 및 Safari가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-167">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="d839d-168">브라우저를 새로 고칠 때까지 업데이트 된 데이터가 표시 되지 않는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-168">There may be instances where updated data doesn't appear until your browser is refreshed.</span></span>
- <span data-ttu-id="d839d-169">Microsoft Edge의 미리 보기 버전은 지원 되지 않지만 알려진 문제는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-169">The preview version of Microsoft Edge isn't supported but has no known issues.</span></span>
- <span data-ttu-id="d839d-170">Internet Explorer가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-170">Internet Explorer isn't supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="d839d-171">세션 제한 시간</span><span class="sxs-lookup"><span data-stu-id="d839d-171">Session timeout</span></span>

- <span data-ttu-id="d839d-172">세션 시간이 초과 되 면 "문제가 발생 했습니다." 오류가 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-172">When a session times out, a "Something went wrong" error may appear.</span></span> <span data-ttu-id="d839d-173">문제를 해결 하려면 [준수 관리자로](https://servicetrust.microsoft.com/ComplianceManager) 이동 하 여 다시 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d839d-173">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
