---
title: Microsoft 준수 관리자에서 개선 작업 할당 및 완료
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
description: Microsoft 준수 관리자에서 컨트롤을 구현 하 고 테스트를 수행 하는 방법에 대해 알아봅니다. 작업을 할당 하 고, 문서를 저장 하 고, 보고서를 내보냅니다.
ms.openlocfilehash: 4b7ece89752a2c3e54a0a69bade2f489feacd0c3
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376529"
---
# <a name="assign-and-complete-improvement-actions-in-compliance-manager"></a><span data-ttu-id="7e0c4-104">준수 관리자에서 개선 작업 할당 및 완료</span><span class="sxs-lookup"><span data-stu-id="7e0c4-104">Assign and complete improvement actions in Compliance Manager</span></span>

<span data-ttu-id="7e0c4-105">**이 문서의 내용** 이 문서에서는 개선 작업을 통해 **준수 워크플로를 관리** 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-105">**In this article:** This article explains how to **manage your compliance workflow** with improvement actions.</span></span> <span data-ttu-id="7e0c4-106">구현 및 테스트, **업데이트 관리**, **보고서** 내보내기에 대 한 **개선 작업을 할당** 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-106">Learn how to **assign improvement actions** for implementation and testing, **manage updates**, and export **reports**.</span></span>

## <a name="manage-compliance-workflows-with-improvement-actions"></a><span data-ttu-id="7e0c4-107">개선 작업으로 규정 준수 워크플로 관리</span><span class="sxs-lookup"><span data-stu-id="7e0c4-107">Manage compliance workflows with improvement actions</span></span>

<span data-ttu-id="7e0c4-108">향상 작업을 통해 준수 작업을 중앙에 집중 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-108">Improvement actions centralize your compliance activities.</span></span> <span data-ttu-id="7e0c4-109">각 향상 작업은 데이터 보호 규정 및 표준과의 맞춤을 지원 하기 위한 자세한 구현 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-109">Each improvement action gives detailed implementation guidance to help you align with data protection regulations and standards.</span></span> <span data-ttu-id="7e0c4-110">조직의 사용자에 게 작업을 할당 하 여 구현 및 테스트 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-110">Actions can be assigned to users in your organization to perform implementation and testing work.</span></span> <span data-ttu-id="7e0c4-111">작업 내에 설명서, 메모 및 레코드 상태 업데이트를 저장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-111">You can also store documentation, notes, and record status updates within the action.</span></span>

<span data-ttu-id="7e0c4-112">향상 된 모든 작업은 개선 작업 페이지에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-112">All of your improvement actions are listed on the improvement actions page.</span></span> <span data-ttu-id="7e0c4-113">[향상 작업 보기](compliance-manager-setup.md#improvement-actions-page)에 대해 더 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-113">Learn more about [viewing your improvement actions](compliance-manager-setup.md#improvement-actions-page).</span></span>

## <a name="improvement-actions-details-page"></a><span data-ttu-id="7e0c4-114">개선 작업 세부 정보 페이지</span><span class="sxs-lookup"><span data-stu-id="7e0c4-114">Improvement actions details page</span></span>

<span data-ttu-id="7e0c4-115">각 향상 작업에는 현재 상태, 관련 표준 및 규정 요구 사항 및 권장 구현 지침이 표시 되는 세부 정보 페이지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-115">Each improvement action has a details page showing its current status, the related standards and regulatory requirements, and recommended implementation guidance.</span></span> <span data-ttu-id="7e0c4-116">[기술 작업](compliance-score-calculation.md#technical-and-non-technical-actions) 에는 구현에 적합 한 솔루션으로 이동 하는 **지금 시작** 링크가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-116">[Technical actions](compliance-score-calculation.md#technical-and-non-technical-actions) include a **Launch now** link that takes you to the appropriate solution for implementation.</span></span> <span data-ttu-id="7e0c4-117">구현 및 테스트 설명서를 개선 작업의 세부 정보 페이지에 직접 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-117">You can attach implementation and testing documentation directly into an improvement action’s details page.</span></span>

<span data-ttu-id="7e0c4-118">개선 작업의 세부 정보 페이지를 보려면:</span><span class="sxs-lookup"><span data-stu-id="7e0c4-118">To view an improvement action’s details page:</span></span>

1. <span data-ttu-id="7e0c4-119">개선 작업 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-119">Go to your improvement actions page.</span></span>
2. <span data-ttu-id="7e0c4-120">계획 된 개선 작업의 행을 선택 하 여 세부 정보 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-120">Select the row of your intended improvement action, which opens its details page.</span></span>

<span data-ttu-id="7e0c4-121">화면 오른쪽 위 모서리에 있는 위쪽 또는 아래쪽 화살표를 선택 하 여 목록에서 다음 또는 이전 개선 작업을 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-121">You can easily view the next or previous improvement action in the list by selecting the up or down arrow in the upper-right corner of the screen.</span></span> <span data-ttu-id="7e0c4-122">개선 작업 페이지에서 목록을 필터링 한 경우 위쪽 또는 아래쪽으로 이동 하면 필터링 된 목록 내의 다음 항목을 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-122">If you filtered your list on the improvement actions page, moving up or down takes you to the next item within that filtered list.</span></span>

## <a name="assign-improvement-actions"></a><span data-ttu-id="7e0c4-123">개선 작업 할당</span><span class="sxs-lookup"><span data-stu-id="7e0c4-123">Assign improvement actions</span></span>

<span data-ttu-id="7e0c4-124">개선 작업에 대 한 구현 작업을 시작 하려면 직접 작업을 수행 하거나 다른 사용자에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-124">To begin implementation work on an improvement action, you can do the work yourself or assign it to another user.</span></span> <span data-ttu-id="7e0c4-125">배정 된 사용자는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-125">The assigned person could be:</span></span>

- <span data-ttu-id="7e0c4-126">비즈니스 정책 소유자</span><span class="sxs-lookup"><span data-stu-id="7e0c4-126">A business policy owner</span></span>
- <span data-ttu-id="7e0c4-127">IT 구현자</span><span class="sxs-lookup"><span data-stu-id="7e0c4-127">An IT implementer</span></span>
- <span data-ttu-id="7e0c4-128">작업 수행을 담당 하는 다른 직원</span><span class="sxs-lookup"><span data-stu-id="7e0c4-128">Another employee with responsibility to perform the task</span></span>

<span data-ttu-id="7e0c4-129">해당 담당자를 확인 한 후에는 작업을 수행할 수 있도록 충분 한 [준수 관리자 역할](compliance-manager-setup.md#set-user-permissions-and-assign-roles) 을 보유 하 고 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-129">Once you identify the appropriate assignee, be sure they hold a sufficient [Compliance Manager role](compliance-manager-setup.md#set-user-permissions-and-assign-roles) to perform the work.</span></span> <span data-ttu-id="7e0c4-130">그런 후에 다음 단계에 따라 개선 작업을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-130">Then follow the steps below to assign the improvement action:</span></span>

1. <span data-ttu-id="7e0c4-131">개선 작업 세부 정보 페이지에서 화면의 왼쪽 위 섹션 부근에 있는 **상태 편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-131">From the improvement actions details page, select **Edit status** near the upper-left section of the screen.</span></span>

2. <span data-ttu-id="7e0c4-132">상태 플라이 아웃 편집 창에서 **담당자** 상자를 선택 하 여 사용자의 **제안** 된 사용자 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-132">In the edit status flyout pane, select the **Assigned to** box to show a **Suggested people** list of users.</span></span> <span data-ttu-id="7e0c4-133">목록에서 사용자를 선택 하거나 자신을 할당 하려는 사용자의 전자 메일 주소를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-133">You can select the user from the list, or type the email address of the person you want to assign it to.</span></span>

3. <span data-ttu-id="7e0c4-134">**저장 후 닫기를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-134">Select **Save and close**.</span></span> <span data-ttu-id="7e0c4-135">할당 된 사용자는 개선 작업에 대 한 직접 링크와 함께 개선 작업이 할당 되었음을 설명 하는 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-135">The assigned user will receive an email explaining that the improvement action has been assigned to them, with a direct link to the improvement action.</span></span> <span data-ttu-id="7e0c4-136">(참고: 미국 정부 커뮤니티 (GCC) 높은 고객은 작업을 할당할 때 전자 메일을 받을 수 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="7e0c4-136">(Note: US Government Community (GCC) High customers won't receive an email when actions are assigned to them.)</span></span>

<span data-ttu-id="7e0c4-137">그러면 할당 된 사용자가 권장 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-137">The assigned user can then perform the recommended actions.</span></span>

## <a name="perform-work-and-store-documentation"></a><span data-ttu-id="7e0c4-138">작업 수행 및 문서 저장</span><span class="sxs-lookup"><span data-stu-id="7e0c4-138">Perform work and store documentation</span></span>

<span data-ttu-id="7e0c4-139">구현 및 테스트 작업과 관련 된 파일 및 메모를 직접 **메모 및 문서** 섹션에 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-139">You can upload files and notes related to implementation and testing work directly to the **Notes and documentation** section.</span></span> <span data-ttu-id="7e0c4-140">이 환경은 규정 준수 표준 및 규정을 충족 하기 위한 제어 만족도를 제공 하는 데 도움이 되는 안전 하 고 중앙화 된 리포지토리입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-140">This environment is a secure, centralized repository to help you demonstrate satisfaction of controls to meet compliance standards and regulations.</span></span> <span data-ttu-id="7e0c4-141">읽기 전용 권한이 있는 사용자는이 섹션의 콘텐츠를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-141">Any user with read-only access can read content in this section.</span></span> <span data-ttu-id="7e0c4-142">편집 권한이 있는 사용자만 파일을 업로드 및 다운로드 하 고 메모를 입력 하거나 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-142">Only users with editing rights can upload and download files and enter or edit notes.</span></span>

<span data-ttu-id="7e0c4-143">**Notes 및 문서** 섹션에는 업로드 된 문서, 구현 메모, 테스트 메모 및 추가 메모에 대 한 필드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-143">The **Notes and documentation** section contains fields for uploaded documents, implementation notes, test notes, and additional notes.</span></span>

#### <a name="uploaded-documents"></a><span data-ttu-id="7e0c4-144">업로드 된 문서</span><span class="sxs-lookup"><span data-stu-id="7e0c4-144">Uploaded documents</span></span>

- <span data-ttu-id="7e0c4-145">**문서 관리** 를 선택 하 여 관련 파일을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-145">Select **Manage documents** to upload any relevant files.</span></span>
- <span data-ttu-id="7e0c4-146">문서 플라이 아웃 관리 창이 열리면 **문서 추가** 를 선택한 다음 시스템에서 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-146">When the manage documents flyout pane opens, select **Add document**, then select your file from your system.</span></span> <span data-ttu-id="7e0c4-147">허용 되는 파일 형식:</span><span class="sxs-lookup"><span data-stu-id="7e0c4-147">Accepted file types:</span></span>
    - <span data-ttu-id="7e0c4-148">문서 (.doc, .xls, .ppt, .txt, .pdf)</span><span class="sxs-lookup"><span data-stu-id="7e0c4-148">Documents (.doc, .xls, .ppt, .txt, .pdf)</span></span>
    - <span data-ttu-id="7e0c4-149">이미지 (.jpg, .png)</span><span class="sxs-lookup"><span data-stu-id="7e0c4-149">Images (.jpg, .png)</span></span>
    - <span data-ttu-id="7e0c4-150">비디오 (mkv)</span><span class="sxs-lookup"><span data-stu-id="7e0c4-150">Video (.mkv)</span></span>
    - <span data-ttu-id="7e0c4-151">압축 된 파일 (.zip, rar)</span><span class="sxs-lookup"><span data-stu-id="7e0c4-151">Compressed files (.zip, .rar)</span></span>
- <span data-ttu-id="7e0c4-152">창에서 파일이 확인 되 면 **닫기를** 선택 하 여 첨부 파일을 자동으로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-152">Once your file resolves in the pane select **Close**, which automatically saves the file attachment.</span></span> <span data-ttu-id="7e0c4-153">**업로드 된 문서** 아래에 파일이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-153">You'll then see the file listed underneath **Uploaded documents**.</span></span>
- <span data-ttu-id="7e0c4-154">문서를 다운로드 하거나 삭제 하려면 문서 목록 아래에서 **문서 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-154">To download or delete the document, select **Manage documents** from underneath the list of documents.</span></span> <span data-ttu-id="7e0c4-155">플라이 아웃 창에서 문서 행을 선택 하 여 강조 표시 하 고 **다운로드** 또는 **삭제** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-155">On the flyout pane, select the document row to highlight it, then select **Download** or **Delete**.</span></span>

#### <a name="implementation-notes-test-notes-and-additional-notes"></a><span data-ttu-id="7e0c4-156">구현 참고 사항, 테스트 메모 및 추가 참고 사항</span><span class="sxs-lookup"><span data-stu-id="7e0c4-156">Implementation notes, test notes, and additional notes</span></span>

- <span data-ttu-id="7e0c4-157">이러한 세 필드 중 하나에 메모를 추가 하려면 이러한 필드 아래에서 **구현 노트 편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-157">To add notes in any of these three fields, select **Edit implementation notes** underneath any of these fields.</span></span>
- <span data-ttu-id="7e0c4-158">플라이 아웃 창이 열리면 텍스트 필드에 메모를 입력 한 다음 **저장 후 닫기를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-158">When the flyout pane opens, enter notes in the text field, then select **Save and close**.</span></span>
- <span data-ttu-id="7e0c4-159">메모를 편집 하려면 **구현 메모 편집** 을 선택 하 고 편집을 수행한 다음 **저장 후 닫기를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-159">To edit notes, select **Edit implementation notes**, make your edits, then select **Save and close**.</span></span>

<span data-ttu-id="7e0c4-160">메모 필드에는 문자 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-160">There's no character limit in the notes fields.</span></span> <span data-ttu-id="7e0c4-161">개선 작업 세부 정보 페이지에서 쉽게 보고 편집할 수 있도록 노트를 간략하게 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-161">We recommend keeping notes brief so that you can easily view and edit them from the improvement actions details page.</span></span>

## <a name="change-improvement-action-status"></a><span data-ttu-id="7e0c4-162">개선 작업 상태 변경</span><span class="sxs-lookup"><span data-stu-id="7e0c4-162">Change improvement action status</span></span>

<span data-ttu-id="7e0c4-163">각 향상 작업에 대해 구현 상태 및 날짜와 테스트 상태 및 날짜를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-163">You can record the implementation status and date, and the test status and date, for each improvement action.</span></span> <span data-ttu-id="7e0c4-164">**구현** 및 **테스트 상태** 필드는 할당 된 사용자 뿐만 아니라 편집 권한이 있는 모든 사용자가 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-164">The **implementation** and **test status** fields can be edited by any user with editing permissions, not just by the assigned person.</span></span>

<span data-ttu-id="7e0c4-165">향상 된 작업의 상태를 편집 하려면 세부 정보 페이지의 왼쪽 위 섹션에서 **상태 편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-165">To edit an improvement action’s status, select **Edit status** on the upper-left section of the details page.</span></span> <span data-ttu-id="7e0c4-166">사용 가능한 필드 및 상태 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-166">Below are the available fields and status options:</span></span>

- <span data-ttu-id="7e0c4-167">**구현 상태**</span><span class="sxs-lookup"><span data-stu-id="7e0c4-167">**Implementation status**</span></span>
    - <span data-ttu-id="7e0c4-168">**구현 되지 않음** -작업이 아직 구현 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-168">**Not implemented** - action not yet implemented</span></span>
    - <span data-ttu-id="7e0c4-169">**구현** 됨-작업 구현 됨</span><span class="sxs-lookup"><span data-stu-id="7e0c4-169">**Implemented** - action implemented</span></span>
    - <span data-ttu-id="7e0c4-170">**대체 구현** -타사 도구를 사용 하거나 Microsoft 권장 사항에 포함 되지 않은 다른 작업을 수행한 경우에이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-170">**Alternative implementation** - select this option if you used other third-party tools or took other actions not included in Microsoft recommendations</span></span>
    - <span data-ttu-id="7e0c4-171">**계획** 됨-구현을 위한 조치가 계획 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-171">**Planned** - action is planned for implementation</span></span>
    - <span data-ttu-id="7e0c4-172">**범위를 벗어남** -작업이 조직과 관련이 없으며 점수에 기여 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-172">**Out of scope** – action isn’t relevant to your organization and doesn’t contribute to your score</span></span>
- <span data-ttu-id="7e0c4-173">**구현 날짜**: 구현 상태가 "구현 됨" 또는 "대체 구현" 일 때 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-173">**Implementation date**: available to select when implementation status is "implemented" or "alternative implementation"</span></span>
- <span data-ttu-id="7e0c4-174">**테스트 상태**: 구현 상태가 "구현 됨" 또는 "대체 구현" 인 경우 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-174">**Test status**: available to select when implementation status is "implemented" or "alternative implementation":</span></span>
    - <span data-ttu-id="7e0c4-175">**평가 안** 됨-작업이 테스트 되지 않음</span><span class="sxs-lookup"><span data-stu-id="7e0c4-175">**Not assessed** – action hasn't been tested</span></span>
    - <span data-ttu-id="7e0c4-176">**통과** -평가자에서 구현 확인</span><span class="sxs-lookup"><span data-stu-id="7e0c4-176">**Passed** - implementation has been verified by an assessor</span></span>
    - <span data-ttu-id="7e0c4-177">**실패 한 낮은 위험** -테스트 실패, 낮은 위험</span><span class="sxs-lookup"><span data-stu-id="7e0c4-177">**Failed low risk** - testing failed, low risk</span></span>
    - <span data-ttu-id="7e0c4-178">**실패 한 중간 위험** -테스트 실패, 보통 위험</span><span class="sxs-lookup"><span data-stu-id="7e0c4-178">**Failed medium risk** - testing failed, medium risk</span></span>
    - <span data-ttu-id="7e0c4-179">**실패 한 높은 위험** -테스트 실패, 높은 위험</span><span class="sxs-lookup"><span data-stu-id="7e0c4-179">**Failed high risk** – testing failed, high risk</span></span>
    - <span data-ttu-id="7e0c4-180">**범위를 벗어남** -작업이 평가 범위를 벗어나지만 점수에 기여 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-180">**Out of scope** – the action is out of scope for the assessment and doesn’t contribute to your score</span></span>
- <span data-ttu-id="7e0c4-181">**테스트 날짜**: 달력 팝업을 전환 하 여 날짜를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-181">**Test date**: toggle through the calendar pop-up to select the date</span></span>

<span data-ttu-id="7e0c4-182">일반적인 작업은 여러 그룹에서 동기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-182">Common actions synch across groups.</span></span> <span data-ttu-id="7e0c4-183">같은 그룹에서 사용자가 관리 하는 다른 두 가지 평가를 공유 하는 경우 작업의 구현 세부 정보 또는 상태에 대 한 모든 업데이트는 그룹의 다른 평가에서 동일한 작업과 자동으로 동기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-183">When two different assessments in the same group share improvement actions that are managed by you, any updates you make to an action's implementation details or status will automatically synchronize to the same action in any other assessment in the group.</span></span> <span data-ttu-id="7e0c4-184">이러한 동기화를 통해 한 가지 향상 작업을 구현 하 고 여러 규정에 걸친 여러 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-184">This synchronization allows you to implement one improvement action and meet several requirements across multiple regulations.</span></span>

## <a name="assign-improvement-action-to-assessor-for-completion"></a><span data-ttu-id="7e0c4-185">평가자에 개선 작업을 할당 하 여 완료</span><span class="sxs-lookup"><span data-stu-id="7e0c4-185">Assign improvement action to assessor for completion</span></span>

<span data-ttu-id="7e0c4-186">작업을 완료 하 고 테스트를 수행한 후 증거를 업로드 한 후에는 유효성 검사를 위해 평가자에 게 개선 작업을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-186">After you complete the work, conduct testing, and upload evidence, the next step is to assign the improvement action to an assessor for validation.</span></span> <span data-ttu-id="7e0c4-187">평가자는 작업의 유효성을 검사 하 고 설명서를 검토 하 고 적절 한 테스트 상태를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-187">The assessor validates the work and examines the documentation, and selects the appropriate test status.</span></span>

<span data-ttu-id="7e0c4-188">**Test status가 "통과"로 설정 된 경우** 작업이 완료 되 고 달성 된 점수에는 달성 한 최대 점수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-188">**If test status is set to “Passed”**: the action is complete and the points achieved shows the maximum points achieved.</span></span> <span data-ttu-id="7e0c4-189">그러면 전체 준수 점수에 따라 점수가 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-189">The points are then counted toward your overall compliance score.</span></span>

<span data-ttu-id="7e0c4-190">**Test status가 "Failed"로 설정 된 경우** 동작이 요구 사항을 충족 하지 않으며 평가자에서 추가 작업을 위해 해당 사용자에 게 다시 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-190">**If test status is  set to “Failed”**: the action doesn't meet the requirements, and the assessor can assign it back to the appropriate user for additional work.</span></span>

## <a name="accepting-updates-to-improvement-actions"></a><span data-ttu-id="7e0c4-191">개선 작업에 대 한 업데이트 허용</span><span class="sxs-lookup"><span data-stu-id="7e0c4-191">Accepting updates to improvement actions</span></span>

<span data-ttu-id="7e0c4-192">개선 작업에 대 한 업데이트를 사용할 수 있는 경우 이름 옆에 알림이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-192">When an update is available for an improvement action, you’ll see a notification next to its name.</span></span> <span data-ttu-id="7e0c4-193">업데이트를 수락 하거나 나중에 연기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-193">You can either accept the update or defer it for a later time.</span></span>

#### <a name="what-causes-an-update"></a><span data-ttu-id="7e0c4-194">업데이트의 원인이 되는 작업</span><span class="sxs-lookup"><span data-stu-id="7e0c4-194">What causes an update</span></span>

<span data-ttu-id="7e0c4-195">점수 매기기, 자동화 또는 범위와 관련 된 변경 내용이 있으면 업데이트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-195">An update occurs when there are changes related to scoring, automation, or scope.</span></span> <span data-ttu-id="7e0c4-196">변경 사항에는 규정 변경에 따른 향상 작업에 대 한 새로운 지침 또는 제품 변경으로 인 한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-196">Changes may involve new guidance for improvement actions based on regulatory changes, or could be because of product changes.</span></span> <span data-ttu-id="7e0c4-197">조직에서 관리 하는 개선 작업만 업데이트 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-197">Only the improvement actions managed by your organizations receive update notifications.</span></span>

#### <a name="where-youll-see-assessment-update-notifications"></a><span data-ttu-id="7e0c4-198">평가 업데이트 알림이 표시 되는 위치</span><span class="sxs-lookup"><span data-stu-id="7e0c4-198">Where you’ll see assessment update notifications</span></span>

<span data-ttu-id="7e0c4-199">개선 작업을 업데이트 하면 개선 작업 페이지의 이름 옆에 **보류 중인 업데이트** 레이블과 관련 평가의 세부 정보 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-199">When an improvement action is updated, you’ll see a **Pending update** label next to its name on the improvement actions page, and on the details page of its related assessments.</span></span>

<span data-ttu-id="7e0c4-200">개선 작업의 세부 정보 페이지로 이동한 후 위쪽 배너에서 **업데이트 검토** 단추를 선택 하 여 변경 내용에 대 한 세부 정보를 검토 하 고 업데이트를 적용 하거나 연기 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-200">Go to the improvement action’s details page, and select the **Review update** button in the top banner to review details about the changes and accept or defer the update.</span></span>

#### <a name="review-update-to-accept-or-defer"></a><span data-ttu-id="7e0c4-201">수락 또는 연기할 업데이트 검토</span><span class="sxs-lookup"><span data-stu-id="7e0c4-201">Review update to accept or defer</span></span>

<span data-ttu-id="7e0c4-202">향상 된 작업 세부 정보 페이지에서 **업데이트 검토** 를 선택 하면 화면 오른쪽에 플라이 아웃 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-202">After selecting **Review update** from the improvement action details page, a flyout pane appears on the right side of your screen.</span></span> <span data-ttu-id="7e0c4-203">플라이 아웃 창에서는 영향을 받는 평가 및 성과 범위 변경과 같은 업데이트에 대 한 주요 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-203">The flyout pane provides key details about the update, such as the assessments impacted and changes in score and scope.</span></span>

<span data-ttu-id="7e0c4-204">**업데이트 수락** 을 선택 하 여 개선 작업에 대 한 모든 변경 내용을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-204">Select **Accept update** to accept all the changes to the improvement action.</span></span> <span data-ttu-id="7e0c4-205">**수락 된 변경 내용이 영구적** 입니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-205">**Accepted changes are permanent**.</span></span>

> [!NOTE]
> <span data-ttu-id="7e0c4-206">작업에 대 한 업데이트를 수락 하면이 작업의 다른 버전 또는 인스턴스에 대 한 업데이트도 수락 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-206">When you accept an update to an action, you’re also accepting updates to any other versions or instances of this action.</span></span> <span data-ttu-id="7e0c4-207">업데이트는 기술 작업에 대해 테 넌 트 전반에 전파 되며, 기술 외의 작업을 위해 그룹 전체를 전파 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-207">Updates will propagate tenant-wide for technical actions, and will propagate group-wide for non-technical actions.</span></span>

<span data-ttu-id="7e0c4-208">**취소** 를 선택 하면 개선 작업에 업데이트가 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-208">If you select **Cancel**, the update won’t be applied to the improvement action.</span></span> <span data-ttu-id="7e0c4-209">그러나 업데이트를 수락할 때까지 **보류 중인 업데이트** 알림을 계속 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-209">However, you’ll continue to see the **Pending update** notification until you accept the update.</span></span>

<span data-ttu-id="7e0c4-210">**업데이트를 적용 하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="7e0c4-210">**Why we recommend accepting updates**</span></span>

<span data-ttu-id="7e0c4-211">업데이트를 수락 하면 솔루션 사용에 대 한 지침이 가장 많이 제공 되 고, 직접 인증 요구 사항을 충족 하는 데 도움이 되는 적절 한 개선 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-211">Accepting updates helps ensure you have the most updated guidance on using solutions and taking appropriate improvement actions to help you meet the requirements of the certification at hand.</span></span>

<span data-ttu-id="7e0c4-212">**업데이트를 연기할 수 있는 이유**</span><span class="sxs-lookup"><span data-stu-id="7e0c4-212">**Why you might want to defer an update**</span></span>

<span data-ttu-id="7e0c4-213">개선 작업을 포함 하는 평가를 완료 한 경우에는 업데이트를 수락 하기 전에 작업을 완료 했는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-213">If you’re in the middle of completing an assessment that includes the improvement action, you may want to ensure you’ve finished work on it before you accept the update.</span></span> <span data-ttu-id="7e0c4-214">업데이트 플라이 아웃 검토 창에서 **취소** 를 선택 하 여 나중에 업데이트를 연기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-214">You can defer the update for a later time by selecting **Cancel** on the review update flyout pane.</span></span>

## <a name="export-a-report"></a><span data-ttu-id="7e0c4-215">보고서 내보내기</span><span class="sxs-lookup"><span data-stu-id="7e0c4-215">Export a report</span></span>

<span data-ttu-id="7e0c4-216">화면 왼쪽 위 모서리에서 **내보내기를** 선택 하 여 개선 작업 페이지에 표시 된 모든 개선 작업과 필터 범주가 포함 된 Excel 워크시트를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e0c4-216">Select **Export** in the upper-left corner of your screen to download an Excel worksheet containing all your improvement actions and the filter categories shown on the improvement actions page.</span></span>