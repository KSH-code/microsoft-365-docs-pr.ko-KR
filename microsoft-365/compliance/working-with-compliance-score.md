---
title: Microsoft 준수 점수를 사용 하 여 작업
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
description: Microsoft 준수 점수의 워크플로 도구를 사용 하 여 조직에 대 한 준수를 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 9dc3eb41b1ad686e1c9e1f0a4cf2df66ccb3ffbe
ms.sourcegitcommit: 544b10cc3abe04a47438085d51c4250c9238f76f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "38686992"
---
# <a name="working-with-microsoft-compliance-score-preview"></a><span data-ttu-id="47342-103">Microsoft 준수 점수를 사용한 작업 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="47342-103">Working with Microsoft Compliance Score (Preview)</span></span>

## <a name="managing-your-workflow-with-improvement-actions"></a><span data-ttu-id="47342-104">개선 작업을 사용 하 여 워크플로 관리</span><span class="sxs-lookup"><span data-stu-id="47342-104">Managing your workflow with improvement actions</span></span>

<span data-ttu-id="47342-105">준수 점수에 개선 작업을 사용 하 여 준수 워크플로를 중앙 집중화 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-105">Using improvement actions in Compliance Score centralizes your compliance workflows.</span></span> <span data-ttu-id="47342-106">향상 작업은 데이터 보호 규정 및 표준과 일치 하는 권장 작업을 제시 하 고 자세한 구현 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-106">Improvement actions suggest recommended actions to align with data protection regulations and standards, and provide detailed implementation guidance.</span></span> <span data-ttu-id="47342-107">사용자에 게 할당 하 여 필요한 구현 및 테스트 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-107">You can assign them to users to perform the necessary implementation and testing work.</span></span> <span data-ttu-id="47342-108">또한 향상 작업 자체에 문서 및 메모를 저장 하 고 상태 업데이트를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-108">You can also store documentation and notes, and record status updates right in the improvement action itself.</span></span>

## <a name="view-your-improvement-actions"></a><span data-ttu-id="47342-109">개선 작업 보기</span><span class="sxs-lookup"><span data-stu-id="47342-109">View your improvement actions</span></span>

<span data-ttu-id="47342-110">규정 준수 점수 대시보드에는 **주요 향상 작업**, 즉 가장 중요 한 문제를 해결 하는 가장 많은 지점을 제공 하는 작업이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47342-110">The Compliance Score dashboard shows your **key improvement actions**—the ones with the most available points which address the most important issues.</span></span>

<span data-ttu-id="47342-111">모든 개선 작업을 보려면 대시보드에서 **개선 작업** 탭을 선택 하거나 대시보드의 주요 향상 작업 목록 아래에 있는 **모든 개선 작업 보기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-111">To view all of your improvement actions, select the **Improvement actions** tab on your dashboard, or select **View all improvement actions** underneath the list of key improvement actions on your dashboard.</span></span> <span data-ttu-id="47342-112">그러면 조직의 모든 개선 작업을 볼 수 있는 **향상 작업** 페이지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="47342-112">This brings you to the the **Improvement actions** page, where you can see all of your organization’s improvement actions.</span></span>

<span data-ttu-id="47342-113">작업 목록이 길면 보기를 필터링 하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-113">If you have a long list of actions, it may be helpful to filter your view.</span></span> <span data-ttu-id="47342-114">이렇게 하려면 작업 목록의 오른쪽 위 모서리에서 **필터** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-114">To do this, select **Filter** at the upper-right corner of the actions list.</span></span> <span data-ttu-id="47342-115">**필터** 플라이 아웃 창이 나타나면 규정 및 표준, 솔루션, 그룹에 따라 원하는 기준을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-115">When the **Filters** flyout pane appears, then select your desired criteria based on regulations and standards, solution, and group.</span></span> <span data-ttu-id="47342-116">오른쪽 위 모서리에 있는 **그룹** 을 선택 하 고 드롭다운 메뉴에서 그룹, 솔루션, 범주, 작업 유형 또는 상태별로 보기를 선택 하 여 보기를 사용자 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-116">You can also customize your view by selecting **Group** in the upper-right corner and, from the drop-down menu, select to view by group, solution, category, action type, or status.</span></span>

<span data-ttu-id="47342-117">이 페이지의 기본 보기에는 **통과**테스트 상태의 개선 작업이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-117">The default view for this page does not show improvement actions with a test status of **Passed**.</span></span> <span data-ttu-id="47342-118">테스트에 통과 한 작업을 보려면 **필터** 플라이 아웃 창에서 **통과** 상자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-118">To view actions that have passed testing, check the **Passed** box in the **Filters** flyout pane.</span></span> <span data-ttu-id="47342-119">테스트 상태의 **합격** 한 작업만 점수에 대해 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47342-119">Only actions with a test status of **Passed** count toward your score.</span></span>

<span data-ttu-id="47342-120">향상 작업 페이지에는 각 향상 작업에 대 한 다음과 같은 데이터 요소가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47342-120">The improvement actions page shows the following data points for each improvement action:</span></span>

- <span data-ttu-id="47342-121">**점수 영향**: 작업 완료 시 전체 점수가 증가 하는 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="47342-121">**Score impact**: the points by which your overall score will increase when completing the action</span></span>
- <span data-ttu-id="47342-122">**규정**: 작업과 관련 된 규정 또는 표준</span><span class="sxs-lookup"><span data-stu-id="47342-122">**Regulations**: the regulation or standard pertaining to the action</span></span>
- <span data-ttu-id="47342-123">**그룹**: 작업을 할당 한 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="47342-123">**Group**: the group to which you assigned the action</span></span>
- <span data-ttu-id="47342-124">**해결**방법: 작업을 수행 하기 위해 이동할 수 있는 솔루션</span><span class="sxs-lookup"><span data-stu-id="47342-124">**Solutions**: the solution where you can go to perform the action</span></span>
- <span data-ttu-id="47342-125">**평가**: 작업이 상주 하는 평가 (특정 준수 목표를 충족 하도록 컨트롤을 구성)</span><span class="sxs-lookup"><span data-stu-id="47342-125">**Assessments**: the assessment  (which organizes controls to meet a certain compliance objective) in which the action resides</span></span>
- <span data-ttu-id="47342-126">**범주**: 관련 데이터 보호 범주 (즉, 정보를 보호 하 고, 장치를 관리 하는 등)</span><span class="sxs-lookup"><span data-stu-id="47342-126">**Categories**: the related data protection category (i.e., protect information, manage devices, etc.)</span></span>
- <span data-ttu-id="47342-127">**테스트 상태**:</span><span class="sxs-lookup"><span data-stu-id="47342-127">**Test status**:</span></span>
    - <span data-ttu-id="47342-128">**없음** -상태 업데이트가 기록 되지 않음</span><span class="sxs-lookup"><span data-stu-id="47342-128">**None** - no status update recorded</span></span>
    - <span data-ttu-id="47342-129">**평가 안** 됨-테스트가 시작 되지 않음</span><span class="sxs-lookup"><span data-stu-id="47342-129">**Not assessed** - testing has not started</span></span>
    - <span data-ttu-id="47342-130">**범위에 없음** -규정 준수 점수 계산에서 제외 되며 점수가 증가 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-130">**Not in scope** - is excluded from Compliance Score calculation and does not increase your score</span></span>
    - <span data-ttu-id="47342-131">**부분적으로 테스트** 됨-테스트가 아직 완료 되지 않음</span><span class="sxs-lookup"><span data-stu-id="47342-131">**Partially tested** - testing is not yet complete</span></span>
    - <span data-ttu-id="47342-132">**실패 한 높은 위험** -구현 테스트에 실패 했으며 해당 표준에 부합 하지 않는 위험이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-132">**Failed high risk** - testing of implementation has failed, and the risk of non-compliance with the applicable standard is high</span></span>
    - <span data-ttu-id="47342-133">**성공** -구현이 테스트 됨</span><span class="sxs-lookup"><span data-stu-id="47342-133">**Passed** - implementation successfully tested</span></span>
- <span data-ttu-id="47342-134">**달성**한 것: 진척 상황을 확인할 수 있는 최대 점수를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-134">**Pointed achieved**: shows points achieved out of the maximum that could be earned</span></span>

### <a name="improvement-actions-details"></a><span data-ttu-id="47342-135">향상 작업 세부 정보</span><span class="sxs-lookup"><span data-stu-id="47342-135">Improvement actions details</span></span>

<span data-ttu-id="47342-136">각 향상 작업에는 세부 정보 페이지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-136">Each improvement action has a details page.</span></span> <span data-ttu-id="47342-137">이 페이지에는 **간략 한** 머리글에 나열 된 관련 표준 및 규정 요구 사항을 해결 하기 위한 권장 조치를 수행 하는 방법을 설명 하는 자세한 구현 지침이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-137">This page contains detailed implementation instructions, which explain how to take the recommended actions to address the related standards and regulatory requirements listed under the **At a glance** header.</span></span>

<span data-ttu-id="47342-138">세부 정보 페이지에서 권장 작업을 시작 하거나 다른 사용자에 게 작업을 할당 하 고, 상태를 업데이트 하 고, 메모 및 문서를 첨부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-138">The details page is where you can launch the recommended action or assign the work to another user, update status, and attach notes and documentation.</span></span>

<span data-ttu-id="47342-139">개선 작업의 세부 정보 페이지를 보려면:</span><span class="sxs-lookup"><span data-stu-id="47342-139">To view an improvement action's details page:</span></span>

1. <span data-ttu-id="47342-140">개선 작업 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-140">Go to your improvement actions page.</span></span>
2. <span data-ttu-id="47342-141">원하는 향상 작업의 행에서 아무 곳 이나 클릭 하거나 탭 하 여 세부 정보 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="47342-141">Click or tap anywhere in the row of your intended improvement action, which opens its details page.</span></span>

<span data-ttu-id="47342-142">화면 오른쪽 위 모서리에 있는 위쪽 또는 아래쪽 화살표를 선택 하 여 목록에서 다음 또는 이전 개선 작업을 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-142">You can easily view the next or previous improvement action in the list by selecting the up or down arrow in the upper-right corner of the screen.</span></span> <span data-ttu-id="47342-143">개선 작업 페이지에서 목록을 필터링 한 경우 위 또는 아래로 이동 하면 필터링 된 목록 내의 다음 항목으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-143">If you filtered your list on the improvement actions page, moving up or down will take you to the next item within that filtered list.</span></span>

## <a name="assign-improvement-actions"></a><span data-ttu-id="47342-144">개선 작업 할당</span><span class="sxs-lookup"><span data-stu-id="47342-144">Assign improvement actions</span></span>

<span data-ttu-id="47342-145">개선 작업에 대 한 구현 작업을 시작 하려면 직접 작업을 수행 하거나 다른 사용자에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-145">To begin implementation work on an improvement action, you can do the work yourself or assign it to another user.</span></span> <span data-ttu-id="47342-146">배정 된 사용자는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-146">The assigned person could be:</span></span>

- <span data-ttu-id="47342-147">비즈니스 정책 소유자</span><span class="sxs-lookup"><span data-stu-id="47342-147">A business policy owner</span></span>
- <span data-ttu-id="47342-148">IT 구현자</span><span class="sxs-lookup"><span data-stu-id="47342-148">An IT implementer</span></span>
- <span data-ttu-id="47342-149">작업 수행을 담당 하는 다른 직원</span><span class="sxs-lookup"><span data-stu-id="47342-149">Another employee with responsibility to perform the task</span></span> 

<span data-ttu-id="47342-150">적절 한 사용자가 식별 되 면 해당 작업을 수행 하기 위해 준수 점수 (준수 관리자, 준수 데이터 관리자, 보안 관리자 또는 전역 관리자)에 충분 한 [역할](compliance-score-setup.md#set-user-permissions-and-assign-roles) 을 보유 하 고 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-150">Once the proper person is identified, be sure they hold a sufficient [role](compliance-score-setup.md#set-user-permissions-and-assign-roles) in Compliance Score (compliance administrator, compliance data administrator, security administrator, or global administrator) to perform the work, then take the following steps:</span></span> 

1. <span data-ttu-id="47342-151">개선 작업 세부 정보 페이지에서 화면의 왼쪽 위 섹션 부근에 있는 **상태 편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-151">From the improvement actions details page, select **Edit status** near the upper-left section of the screen.</span></span> 

2. <span data-ttu-id="47342-152">상태 플라이 아웃 편집 창에서 **할당 대상** 상자를 클릭 하거나 탭 하 여 사용자의 제안 된 **사용자** 목록을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="47342-152">In the edit status flyout pane, click or tap in the **Assigned to** box, which populates a **Suggested people** list of users.</span></span> <span data-ttu-id="47342-153">목록에서 사용자를 선택 하거나 작업을 할당 하려는 사용자의 전자 메일 주소를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-153">You can select the user from the list, or type the email address of the person to whom you want to assign the action.</span></span>

3. <span data-ttu-id="47342-154">**저장 후 닫기를** 선택 하 여 할당을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-154">Select **Save and close** to complete the assignment.</span></span> <span data-ttu-id="47342-155">할당 된 사용자에 게는 개선 작업이 할당 된 전자 메일을 받게 되며, 그런 다음 해당 대시보드에서 개선 작업을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-155">The assigned user will receive an email that the improvement action has been assigned to them, and they can then open the improvement action from their dashboard.</span></span>

<span data-ttu-id="47342-156">할당 된 사용자는 구현 지침에 나와 있는 권장 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-156">The assigned user can then perform the recommended actions outlined in the implementation instructions.</span></span>

## <a name="perform-work-and-store-documentation"></a><span data-ttu-id="47342-157">작업 수행 및 문서 저장</span><span class="sxs-lookup"><span data-stu-id="47342-157">Perform work and store documentation</span></span>

<span data-ttu-id="47342-158">구현 작업을 수행 하는 경우 **메모 및 설명서** 섹션의 향상 작업에 파일 및 메모를 직접 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-158">When you perform implementation work, you can upload files and notes directly to the improvement action in the **Notes and documentation** section.</span></span> <span data-ttu-id="47342-159">이를 통해 규정 준수 표준 및 규정을 충족 하는 제어 만족도를 제공 하는 데 도움이 되는 안전 하 고 중앙화 된 리포지토리</span><span class="sxs-lookup"><span data-stu-id="47342-159">This provides a secure, centralized repository to help you demonstrate satisfaction of controls to meet compliance standards and regulations.</span></span> <span data-ttu-id="47342-160">읽기 전용 권한이 있는 사용자는이 섹션의 콘텐츠를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-160">Any user with read-only access can read content in this section.</span></span> <span data-ttu-id="47342-161">필드를 업로드, 다운로드 또는 삭제 하거나 메모를 입력 하거나 편집 하는 기능은 편집 권한이 있는 역할로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47342-161">The ability to upload, download, or delete fields, or to enter or edit notes, is restricted to roles with editing rights.</span></span>

<span data-ttu-id="47342-162">**Notes 및 문서** 섹션의 필드에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47342-162">Fields in the **Notes and documentation** section include:</span></span>

<span data-ttu-id="47342-163">**업로드 된 문서**</span><span class="sxs-lookup"><span data-stu-id="47342-163">**Uploaded documents**</span></span>

- <span data-ttu-id="47342-164">**문서 관리** 를 선택 하 여 관련 파일을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-164">Select **Manage documents** to upload any relevant files.</span></span>
- <span data-ttu-id="47342-165">문서 플라이 아웃 관리 창이 열리면 **문서 추가**를 선택한 다음 시스템에서 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-165">When the manage documents flyout pane opens, select **Add document**, then select your file from your system.</span></span> <span data-ttu-id="47342-166">허용 되는 파일 형식:</span><span class="sxs-lookup"><span data-stu-id="47342-166">Accepted file types:</span></span> 
  - <span data-ttu-id="47342-167">문서 (.doc, .xls, .ppt, .txt, .pdf)</span><span class="sxs-lookup"><span data-stu-id="47342-167">Documents (.doc, .xls, .ppt, .txt, .pdf)</span></span>
  - <span data-ttu-id="47342-168">이미지 (.jpg, .png)</span><span class="sxs-lookup"><span data-stu-id="47342-168">Images (.jpg, .png)</span></span>
  - <span data-ttu-id="47342-169">비디오 (mkv)</span><span class="sxs-lookup"><span data-stu-id="47342-169">Video (.mkv)</span></span>
  - <span data-ttu-id="47342-170">압축 된 파일 (.zip, rar)</span><span class="sxs-lookup"><span data-stu-id="47342-170">Compressed files (.zip, .rar)</span></span>
- <span data-ttu-id="47342-171">창에서 파일이 확인 되 면 **닫기를** 선택 하 여 첨부 파일을 자동으로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-171">Once your file resolves in the pane, select **Close,** which automatically saves the file attachment.</span></span> <span data-ttu-id="47342-172">업로드 된 문서 아래에 파일이 표시 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="47342-172">You will then see the file listed underneath **Uploaded documents.**</span></span> 
- <span data-ttu-id="47342-173">문서를 다운로드 하거나 삭제 하려면 문서 목록 아래에서 **문서 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-173">To download or delete the document, select **Manage documents** from  underneath the list of documents.</span></span> <span data-ttu-id="47342-174">플라이 아웃 창에서 문서 행을 클릭 하거나 탭 하 여 강조 표시 한 후 **다운로드** 또는 삭제를 선택 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="47342-174">On the flyout pane, click or tap on the document row to highlight it, then select **Download** or **Delete.**</span></span>

<span data-ttu-id="47342-175">**구현, 테스트 및 추가 참고 사항**</span><span class="sxs-lookup"><span data-stu-id="47342-175">**Implementation, Test, and Additional notes**</span></span>

- <span data-ttu-id="47342-176">이러한 세 필드 중 하나에 메모를 추가 하려면 thse 필드 아래에서 **구현 노트 편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-176">To add notes in any of these three fields, select **Edit implementation notes** underneath any of thse fields.</span></span>
- <span data-ttu-id="47342-177">플라이 아웃 창이 열리면 텍스트 필드에 메모를 입력 한 다음 **저장 후 닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-177">When the flyout pane opens, enter notes in the text field, then select **Save and close**.</span></span>
- <span data-ttu-id="47342-178">메모를 편집 하려면 **구현 메모 편집**을 선택 하 고 편집을 수행한 다음 **저장 후 닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-178">To edit notes, select **Edit implementation notes**, make your edits, then select **Save and close**.</span></span>

<span data-ttu-id="47342-179">메모 필드에는 문자 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-179">There is no character limit in the notes fields.</span></span> <span data-ttu-id="47342-180">개선 작업 세부 정보 페이지에서 쉽게 보고 편집할 수 있도록 노트를 간략하게 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-180">We recommend keeping notes brief so that you can easily view and edit them from the improvement actions details page.</span></span>

## <a name="change-improvement-action-status"></a><span data-ttu-id="47342-181">개선 작업 상태 변경</span><span class="sxs-lookup"><span data-stu-id="47342-181">Change improvement action status</span></span>

<span data-ttu-id="47342-182">각 향상 작업에 대해 구현 상태 및 날짜와 테스트 상태 및 날짜를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-182">You can record the implementation status and date, and the test status and date, for each improvement action.</span></span> <span data-ttu-id="47342-183">사용 가능한 필드 및 상태 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-183">Below are the available fields and status options:</span></span>

- <span data-ttu-id="47342-184">**구현 상태**: 다음 상태 옵션 중에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-184">**Implementation status**: select from these status options:</span></span>
    - <span data-ttu-id="47342-185">**구현 되지 않음** -작업이 아직 구현 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-185">**Not implemented** - action not yet implemented</span></span>
    - <span data-ttu-id="47342-186">**구현** 됨-작업 구현 됨</span><span class="sxs-lookup"><span data-stu-id="47342-186">**Implemented** - action implemented</span></span>
    - <span data-ttu-id="47342-187">**대체 구현** -타사 도구를 사용 하거나 Microsoft 권장 사항에 포함 되지 않은 다른 작업을 수행한 경우에이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-187">**Alternative implementation** - select this option if you used other third-party tools or took other actions not included in Microsoft recommendations</span></span>
    - <span data-ttu-id="47342-188">**계획** 됨-구현을 위한 조치가 계획 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47342-188">**Planned** - action is planned for implementation</span></span>
    - <span data-ttu-id="47342-189">**범위에 없음** -조직에 해당 하지 않는 작업에 대 한 옵션입니다. 이 상태를 선택 하면 작업의 점수 매기기에서 제외 됩니다. 작업을 점수 매기기에 포함 하 여 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-189">**Not in scope** - an option for actions not relevant to your organization; selecting this status excludes the action from scoring; unselecting it will include the action in scoring</span></span>
- <span data-ttu-id="47342-190">**구현 날짜**: 구현 상태가 **구현** 됨 또는 **대체 구현**으로 설정 된 경우 사용할 수 있는 필드입니다. 달력 팝업을 전환 하 여 날짜 선택</span><span class="sxs-lookup"><span data-stu-id="47342-190">**Implementation date**: available field when implementation status is set to **Implemented** or **Alternative implementation**; toggle through the calendar pop-up to select the date</span></span>
- <span data-ttu-id="47342-191">**테스트 상태**: 다음 옵션 중에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-191">**Test status**: select from these options:</span></span>
    - <span data-ttu-id="47342-192">**평가 안** 됨-테스트가 시작 되지 않음</span><span class="sxs-lookup"><span data-stu-id="47342-192">**Not assessed** - testing has not started</span></span>
    - <span data-ttu-id="47342-193">**성공**-구현이 테스트 됨</span><span class="sxs-lookup"><span data-stu-id="47342-193">**Passed**- implementation successfully tested</span></span>
    - <span data-ttu-id="47342-194">**실패 한 낮은 위험** -테스트 실패, 낮은 위험</span><span class="sxs-lookup"><span data-stu-id="47342-194">**Failed low risk** - testing failed, low risk</span></span>
    - <span data-ttu-id="47342-195">**실패 한 중간 위험** -테스트 실패, 보통 위험</span><span class="sxs-lookup"><span data-stu-id="47342-195">**Failed medium risk** - testing failed, medium risk</span></span>
    - <span data-ttu-id="47342-196">**실패 한 높은 위험** -테스트 실패, 높은 위험</span><span class="sxs-lookup"><span data-stu-id="47342-196">**Failed high risk** - testing failed, high risk</span></span>
- <span data-ttu-id="47342-197">**테스트 날짜**: 달력 팝업을 전환 하 여 날짜를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-197">**Test date**: toggle through the calendar pop-up to select the date</span></span>

> [!NOTE]
> <span data-ttu-id="47342-198">구현 및 테스트 상태 필드는 사용자 **에게만 할당** 되는 것이 아니라 편집 권한이 있는 모든 사용자가 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-198">Implementation and test status fields can be edited by any user with editing permissions, not just the **Assigned to** user.</span></span>

## <a name="assign-improvement-action-to-assessor-for-completion"></a><span data-ttu-id="47342-199">평가자에 개선 작업을 할당 하 여 완료</span><span class="sxs-lookup"><span data-stu-id="47342-199">Assign improvement action to assessor for completion</span></span>

<span data-ttu-id="47342-200">작업을 완료 하 고 증거를 업로드 한 후에는 구현 상태와 날짜를 설정 하 고, 유효성 검사를 위해 평가자에 게 개선 작업을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-200">After you complete the work and upload evidence, the next step is to set the implementation status and date, and assign the improvement action to an assessor for validation.</span></span>

<span data-ttu-id="47342-201">평가자의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-201">Types of assessors include:</span></span>

- <span data-ttu-id="47342-202">조직 내에서 컨트롤의 유효성 검사를 수행 하는 내부 평가자</span><span class="sxs-lookup"><span data-stu-id="47342-202">Internal assessors who perform validation of controls within your organization</span></span>
- <span data-ttu-id="47342-203">Microsoft 클라우드 서비스를 감사 하는 타사 독립적인 조직과 같이 준수를 조사, 확인 및 인증 하는 외부 평가자</span><span class="sxs-lookup"><span data-stu-id="47342-203">External assessors who examine, verify, and certify compliance—such as third-party independent organizations that audit Microsoft cloud services</span></span>

<span data-ttu-id="47342-204">평가자는 작업의 유효성을 검사 하 고 설명서를 검토 하 고 적절 한 테스트 상태를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-204">The assessor validates the work and examines the documentation, and selects the appropriate test status.</span></span>

<span data-ttu-id="47342-205">**테스트 상태가 "통과" 인 경우**작업이 완료 되 고 예상 되는 **점수** 에 전체 준수 점수에 따라 달성 되 고 계산 되는 최대 점수를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-205">**If the test status is "Passed"**: the action is complete, and the **points achieved** shows the full number of possible points achieved and counted toward your overall compliance score.</span></span>

<span data-ttu-id="47342-206">**테스트 상태가 "실패" 인 경우**: 동작이 요구 사항을 충족 하지 않으며 평가자가 추가 작업을 위해 해당 사용자에 게 다시 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-206">**If the test status is any degree of "Failed"**: the action does not meet the requirements, and the assessor can assign it back to the appropriate user for additional work.</span></span>

## <a name="solutions-page"></a><span data-ttu-id="47342-207">솔루션 페이지</span><span class="sxs-lookup"><span data-stu-id="47342-207">Solutions page</span></span>

<span data-ttu-id="47342-208">향상 작업을 통해 점수를 높일 수 있는 **솔루션 페이지** 는 다른 시작 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="47342-208">The **Solutions page** is another starting point for working on improvement actions to increase your score.</span></span> 

<span data-ttu-id="47342-209">솔루션 페이지로 이동 하려면 대시보드에서 **솔루션** 탭을 선택 하거나 대시보드의 오른쪽 위 섹션에서 **점수에 영향을 주는 솔루션** 아래의 **모든 솔루션 보기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-209">To get to your solutions page, select the **Solutions** tab on your dashboard, or select **View all solutions** underneath **Solutions that affect your score** in the upper-right section of your dashboard.</span></span>

<span data-ttu-id="47342-210">솔루션 페이지에는 솔루션 별로 구성 된 획득 및 잠재 점수 공유가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47342-210">The solutions page shows the share of earned and potential points as organized by solution.</span></span> <span data-ttu-id="47342-211">이 보기에서 남은 점과 향상 작업을 보면 즉각적인 주의가 필요한 솔루션을 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-211">Viewing your remaining points and improvement actions from this view helps you understand which solutions need more immediate attention.</span></span>

### <a name="filtering-your-solutions-view"></a><span data-ttu-id="47342-212">솔루션 보기 필터링</span><span class="sxs-lookup"><span data-stu-id="47342-212">Filtering your solutions view</span></span>

<span data-ttu-id="47342-213">솔루션 보기를 필터링 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-213">To filter you view of solutions:</span></span> 

1. <span data-ttu-id="47342-214">평가 목록의 왼쪽 위 모서리에서 **필터** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-214">Select **Filter** at the top left corner of your assessments list.</span></span>
2. <span data-ttu-id="47342-215">플라이 아웃 **필터** 창에서 원하는 조건 (표준 및 규정, 솔루션, 작업 유형, 준수 관리자 그룹, 범주) 옆에 확인을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-215">On the flyout **Filters** pane, place a check next to the desired criteria (standards and regulations, solution, action type, Compliance Manager group, category).</span></span>
3. <span data-ttu-id="47342-216">**적용** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-216">Select the **Apply** button.</span></span> <span data-ttu-id="47342-217">필터 창이 닫히고 필터링 된 보기가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47342-217">The filter pane will close and you will see your filtered view.</span></span>

<span data-ttu-id="47342-218">평가 목록 위의 **그룹** 드롭다운 메뉴에서 그룹화 유형을 선택 하 여 그룹, 제품 또는 규정 별로 평가를 확인 하도록 보기를 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-218">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="taking-actions-from-the-solutions-page"></a><span data-ttu-id="47342-219">솔루션 페이지에서 작업 수행</span><span class="sxs-lookup"><span data-stu-id="47342-219">Taking actions from the solutions page</span></span>

<span data-ttu-id="47342-220">솔루션 페이지에는 개선 작업에 연결 된 조직의 솔루션이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47342-220">The solutions page displays your organization’s solutions that are connected to improvement actions.</span></span> <span data-ttu-id="47342-221">이 표에서는 각 솔루션의 전체 점수, 해당 솔루션 내에서 달성 하 고 가능한 점수 및 해당 솔루션에 그룹화 되어 있으며 점수를 높일 수 있는 남은 개선 작업 수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="47342-221">The table lists each solution's contribution to your overall score, the score-enhancing points achieved and possible within that solution, and the remaining number of improvement actions grouped in that solution that can increase your score.</span></span> 

<span data-ttu-id="47342-222">다음 두 가지 방법으로이 화면에서 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-222">There are two ways you can take action from this screen:</span></span>

1. <span data-ttu-id="47342-223">원하는 솔루션 행의 **남은 작업** 열에서 하이퍼링크 된 번호를 클릭 하거나 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-223">On the row of your intended solution, under the **Remaining actions** column, click or tap on the hyperlinked number.</span></span> <span data-ttu-id="47342-224">이를 통해 해당 솔루션에 대 한 테스트 되지 않은 개선 작업을 보여 주는 개선 작업 화면의 필터링 된 보기로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-224">This takes you to a filtered view of the improvement actions screen showing untested improvement actions for that solution.</span></span>

2. <span data-ttu-id="47342-225">원하는 솔루션의 행에서 **솔루션 열기** 열 아래에 있는 **열기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-225">On the row of your intended solution, under the **Open solution** column, select **Open**.</span></span> <span data-ttu-id="47342-226">이를 통해 Microsoft 365 및 Office 365 보안 및 준수 센터의 솔루션 또는 위치로 이동 하 여 권장 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-226">This takes you to the solution or location in the Microsoft 365 and Office 365 security and compliance centers where you can take the recommended action.</span></span>

## <a name="assessments-page"></a><span data-ttu-id="47342-227">평가 페이지</span><span class="sxs-lookup"><span data-stu-id="47342-227">Assessments page</span></span>

<span data-ttu-id="47342-228">평가 페이지에는 조직에 대해 추적 하기 위해 선택한 평가가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47342-228">The assessments page lists the assessments you select to track for your organization.</span></span> <span data-ttu-id="47342-229">준수 점수 분모는 추적 된 모든 평가에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47342-229">Your Compliance Score denominator is determined by all your tracked assessments.</span></span> <span data-ttu-id="47342-230">더 많은 평가가 추가 되 고, 개선 작업 페이지에 더 많은 향상 작업이 발생 하며, 점수 분모가 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-230">The more assessments you add, the more improvement actions you see on your improvement actions page, and the higher your score denominator is.</span></span>

<span data-ttu-id="47342-231">평가 페이지에 액세스 하려면 대시보드에서 **평가** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-231">To get to your assessments page, select the **Assessments** tab on your dashboard.</span></span>

<span data-ttu-id="47342-232">이 페이지에서는 각 평가에 대 한 중요 한 정보를 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-232">On this page you can quickly view important information about each assessment:</span></span>

- <span data-ttu-id="47342-233">**상태**: 평가의 모든 개선 작업을 완료 하기 위한 상태는 다음 중 하나로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47342-233">**Status**: the status toward completion of all the improvement actions in the assessment will be listed as either:</span></span>
    - <span data-ttu-id="47342-234">**비호환**: 평가의 개선 작업이 구현 되지 않았으며 올바르게 테스트 되지 않았습니다. 작업이 아직 시작 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-234">**Non-compliant**: the improvement actions in the assessment have not been implemented and successfully tested; work has not yet begun</span></span>
    - <span data-ttu-id="47342-235">**진행**중: 개선 작업을 구현 하거나 테스트 하는 중에 작업이 진행 되 고 있습니다. 예를 들어, 평가의 향상 작업이 작업에 할당 되어 구현 및 테스트 중인 프로세스 라는 것을 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-235">**In progress**: work is underway in implementing or testing the improvement actions; this could mean, for example, that an improvement action in the assessment has been assigned for work, is in the process of being implemented and tested</span></span>
- <span data-ttu-id="47342-236">**평가 진행률**: 성공적으로 테스트를 거친 컨트롤 수에 따라 측정 된 평가의 최종 완료를 향해 수행 된 작업의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="47342-236">**Assessment progress**: the percentage of the work done towards final completion of the assessment, as measured by the number of controls successfully tested.</span></span>
- <span data-ttu-id="47342-237">**고객 관리 작업**: 고객 관리 컨트롤 구현을 충족 하기 위해 완료 된 작업의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="47342-237">**Customer-managed actions**: the number of completed actions to satisfy implementation of  your customer-managed controls</span></span>
- <span data-ttu-id="47342-238">**Microsoft 관리 작업**: microsoft 관리 컨트롤의 구현을 충족 하기 위해 완료 된 작업의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="47342-238">**Microsoft-managed actions**: the number of completed actions to satisfy implementation of Microsoft-managed controls</span></span>
- <span data-ttu-id="47342-239">**평가 그룹**: 만든 그룹의 이름으로, 평가가 상주 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-239">**Assessment group**: name of the group you created, in which the assessment resides</span></span>
- <span data-ttu-id="47342-240">**관련 서비스**: 연결 된 Microsoft 365 서비스</span><span class="sxs-lookup"><span data-stu-id="47342-240">**Related services**: associated Microsoft 365 service</span></span>
- <span data-ttu-id="47342-241">**관련 규정**: 평가에서 충족 해야 하는 규정 표준, 정책 또는 법률입니다.</span><span class="sxs-lookup"><span data-stu-id="47342-241">**Related regulations**: the regulatory standard, policy, or law which the assessment seeks to satisfy</span></span>

### <a name="default-assessments"></a><span data-ttu-id="47342-242">기본 평가</span><span class="sxs-lookup"><span data-stu-id="47342-242">Default assessments</span></span>

<span data-ttu-id="47342-243">기본적으로 평가 페이지에는 Microsoft 365 데이터 보호 기준 평가가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47342-243">By default, you will see the Microsoft 365 data protection baseline assessment on the assessments page.</span></span> <span data-ttu-id="47342-244">다른 규정 및 표준을 다루는 평가를 더 추가 하려는 경우 준수 관리자에서 평가를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-244">If you want to add more assessments to cover other regulations and standards, you can manage assessments in Compliance Manager.</span></span> <span data-ttu-id="47342-245">규정 준수 점수는 GDPR, CCPA, ISO 27001, ISO 27018, NIST 800-53, NIST 800-171, NIST CSF, CSA CCM, FFIEC, HIPAA/HITECH 및 FedRAMP를 포함 하 여 기본 평가를 10 개 이상 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-245">Compliance Score provides more than ten out-of-box assessments,  including ones for GDPR, CCPA, ISO 27001, ISO 27018, NIST 800-53, NIST 800-171, NIST CSF, CSA CCM, FFIEC, HIPAA/HITECH, and FedRAMP.</span></span>

### <a name="managing-assessments"></a><span data-ttu-id="47342-246">평가 관리</span><span class="sxs-lookup"><span data-stu-id="47342-246">Managing assessments</span></span>

<span data-ttu-id="47342-247">공개 미리 보기를 수행 하는 동안 평가를 확인, 생성, 내보내기 및 보관 하는 기능이 준수 관리자 도구에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-247">During public preview, functionality for viewing, creating, exporting, and archiving assessments remains in the Compliance Manager tool.</span></span> 

<span data-ttu-id="47342-248">평가를 관리 하려면 평가 목록 위쪽의 **준수 관리자에서 평가 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-248">To manage your assessments, select **Manage Assessments in Compliance Manager** at the top of the assessments list.</span></span>

<span data-ttu-id="47342-249">평가 목록 맨 위에 있는 다른 링크로, **준수 관리자의 microsoft 작업**에서는 준수 점수에 기여 하는 microsoft 컨트롤을 표시 하는 준수 관리자의 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-249">The other link at the top of the assessments list, **Microsoft actions in Compliance Manager**, takes you to the page in Compliance Manager showing Microsoft controls that contribute to your compliance score.</span></span>

### <a name="filtering-your-assessments-view"></a><span data-ttu-id="47342-250">평가 보기 필터링</span><span class="sxs-lookup"><span data-stu-id="47342-250">Filtering your assessments view</span></span>

<span data-ttu-id="47342-251">평가 보기를 필터링 하려면:</span><span class="sxs-lookup"><span data-stu-id="47342-251">To filter you view of assessments:</span></span>

1. <span data-ttu-id="47342-252">평가 목록의 왼쪽 위 모서리에서 **필터** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-252">Select **Filter** at the top left corner of your assessments list.</span></span>
2. <span data-ttu-id="47342-253">플라이 아웃 **필터** 창에서 원하는 조건 (표준 및 규정, 준수 관리자 그룹) 옆에 확인을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-253">On the flyout **Filters** pane, place a check next to the desired criteria (standards and regulations, Compliance Manager group).</span></span>
3. <span data-ttu-id="47342-254">**적용** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-254">Select the **Apply** button.</span></span> <span data-ttu-id="47342-255">필터 창이 닫히고 필터링 된 보기가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47342-255">The filter pane will close and you will see your filtered view.</span></span>

<span data-ttu-id="47342-256">평가 목록 위의 **그룹** 드롭다운 메뉴에서 그룹화 유형을 선택 하 여 그룹, 제품 또는 규정 별로 평가를 확인 하도록 보기를 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-256">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="managing-improvement-actions-within-an-assessment"></a><span data-ttu-id="47342-257">평가 내의 개선 작업 관리</span><span class="sxs-lookup"><span data-stu-id="47342-257">Managing improvement actions within an assessment</span></span>

<span data-ttu-id="47342-258">평가 목록의 **고객 관리 작업** 열에서 원하는 평가의 행에 있는 연결 된 텍스트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-258">From the assessment list, under the **Customer-managed actions** column, select the linked text on the row of the intended assessment.</span></span> <span data-ttu-id="47342-259">이 작업을 수행 하면 해당 평가 내의 작업을 보여 주는 향상 된 기능 페이지의 필터링 된 보기가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47342-259">This takes you a filtered view of the improvement actions page showing the actions within that assessment.</span></span>

## <a name="reporting"></a><span data-ttu-id="47342-260">Reporting</span><span class="sxs-lookup"><span data-stu-id="47342-260">Reporting</span></span>

<span data-ttu-id="47342-261">모든 개선 작업의 보고서를 준수 점수에 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-261">You can export a report of all your improvement actions in Compliance Score.</span></span> <span data-ttu-id="47342-262">**개선 작업** 페이지에서 화면 왼쪽 위 모서리에 있는 작업 목록 위에 **Export** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-262">From the **Improvement actions** page, select **Export** in the upper-left corner of your screen, above your list of actions.</span></span> <span data-ttu-id="47342-263">이렇게 하면 향상 작업 및 **향상 작업** 페이지에 표시 되는 필터 범주가 포함 된 Excel 워크시트가 생성 되며, 로컬 컴퓨터에서 보고 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-263">This will produce an Excel worksheet with all your improvement actions and the filter categories shown on the **Improvement actions** page, which you can view and save to your local machine.</span></span>

<span data-ttu-id="47342-264">준수 관리자에서 보고서를 내보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47342-264">You can also export a report from Compliance Manager.</span></span> <span data-ttu-id="47342-265">준수 관리자에서 **컨트롤 정보** 탭으로 이동 하 여 화면의 오른쪽 위 섹션에서 **내보내기를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47342-265">In Compliance Manager, go to the **Controls Info** tab and select **Export** in the upper-right section of the screen.</span></span> <span data-ttu-id="47342-266">이렇게 하면 보고 저장할 수 있는 Excel 워크시트가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47342-266">This produces an Excel worksheet you can view and save.</span></span>
