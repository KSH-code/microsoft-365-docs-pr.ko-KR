---
title: 콘텐츠의 처리
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 처리 검토를 사용하거나 사용자가 구성한 설정에 따라 레코드로 표시된 항목이 자동으로 삭제되는 경우에 대한 콘텐츠 폐기 작업을 모니터링하고 관리합니다.
ms.openlocfilehash: 13310eca369949e2b66163907be4268120aa0ed0
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52344966"
---
# <a name="disposition-of-content"></a><span data-ttu-id="45f12-103">콘텐츠의 처리</span><span class="sxs-lookup"><span data-stu-id="45f12-103">Disposition of content</span></span>

><span data-ttu-id="45f12-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="45f12-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="45f12-105">Microsoft 365 준수 센터의 **레코드 관리** 에서 **처리** 페이지을 사용하여 처리 검토를 관리하고 보존 기간이 끝날 때 자동으로 삭제된 [레코드](records-management.md#records)의 메타데이터를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-105">Use the **Disposition** page from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view the metadata of [records](records-management.md#records) that have been automatically deleted at the end of their retention period.</span></span>

> [!NOTE]
> <span data-ttu-id="45f12-106">미리 보기에서 원격 설치: **다중 스테이지 처리 검토**</span><span class="sxs-lookup"><span data-stu-id="45f12-106">Rolling out in preview: **multi-stage disposition review**</span></span>
> 
> <span data-ttu-id="45f12-107">관리자는 이제 보존 레이블에 최대 5단계의 연속적인 처리 검토 스테이지를 추가할 수 있으며, 검토자는 다른 사용자를 처리 검토 단계에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-107">An administrator can now add up to five consecutive stages of disposition review in a retention label, and reviewers can add others users to their disposition review stage.</span></span> <span data-ttu-id="45f12-108">또한 전자 메일 알림 및 미리 알림을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-108">You can also customize the email notifications and reminders.</span></span> <span data-ttu-id="45f12-109">다음 섹션에는 이 미리 보기의 변경사항에 대한 자세한 정보가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-109">The following sections have more information about the changes in this preview.</span></span>

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="45f12-110">콘텐츠 처리를 보기 위한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="45f12-110">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="45f12-111">처리 검토를 관리하고 레코드가 삭제되었는지 확인하려면 충분한 권한이 필요하고 감사를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-111">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="45f12-112">처리 권한</span><span class="sxs-lookup"><span data-stu-id="45f12-112">Permissions for disposition</span></span>

<span data-ttu-id="45f12-113">Microsoft 365 준수 센터의 **처리** 탭에 액세스하려면 사용자에게 **처리 관리** 역할이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-113">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** role.</span></span> <span data-ttu-id="45f12-114">2020년 12월부터 이 역할이 **역할 그룹** 에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-114">From December 2020, this role is now included in the **Records Management** default role group.</span></span>

> [!NOTE]
> <span data-ttu-id="45f12-115">기본적으로 전역 관리자에게 **처리 관리** 역할이 부여되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-115">By default, a global admin isn't granted the **Disposition Management** role.</span></span> 

<span data-ttu-id="45f12-116">사용자에게 보존 및 레코드 관리를 위한 다른 기능을 보고 구성할 수 있는 권한을 부여하지 않고 처리 검토에 필요한 권한만 부여하려면 사용자 지정 역할 그룹(예: "처리 검토자")을 만들고 이 그룹에 **처분 관리** 역할을 부여하세요.</span><span class="sxs-lookup"><span data-stu-id="45f12-116">To grant users just the permissions they need for disposition reviews without granting them permissions to view and configure other features for retention and records management, create a custom role group (for example, named "Disposition Reviewers") and grant this group the **Disposition Management** role.</span></span>

<span data-ttu-id="45f12-117">이 권한을 구성할 수 있는 지침은 [사용자에게 Office 365 보안 및 준수 센터의 액세스 권한 부여하기](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45f12-117">For instructions to configure these permissions, see [Give users access to the Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="45f12-118">추가 사항:</span><span class="sxs-lookup"><span data-stu-id="45f12-118">Additionally:</span></span>

- <span data-ttu-id="45f12-119">처리 프로세스 중에 항목의 콘텐츠를 보려면 사용자를 **콘텐츠 탐색기 콘텐츠 뷰어** 역할 그룹에 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="45f12-119">To view the contents of items during the disposition process, add users to the **Content Explorer Content Viewer** role group.</span></span> <span data-ttu-id="45f12-120">사용자가 이 역할 그룹의 권한을 가지고 있지 않은 경우에도 처리 검토 작업을 선택하여 처리 검토를 완료할 수 있지만, 규정 준수 센터의 미니 미리 보기 창에서 항목의 콘텐츠를 볼 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-120">If users don't have the permissions from this role group, they can still select a disposition review action to complete the disposition review, but must do so without being able to view the item's contents from the mini-preview pane in the compliance center.</span></span>

- <span data-ttu-id="45f12-121">미리 보기: 기본적으로 **처리** 페이지에 액세스하는 각 사용자는 검토하도록 할당된 항목만 봅니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-121">In preview: By default, each person that accesses the **Disposition** page sees only items that they are assigned to review.</span></span> <span data-ttu-id="45f12-122">레코드 관리 관리자가 모든 사용자에게 할당된 모든 항목과 처리 검토를 위해 구성된 모든 보존 레이블을 보려면: **레코드 관리 설정** > **일반** > **레코드 관리자 보안 그룹** 으로 이동하여 관리자 계정이 포함된 메일 사용 가능 보안 그룹을 선택한 다음 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-122">For a records management administrator to see all items assigned to all users, and all retention labels that are configured for disposition review: Navigate to **Records management settings** > **General** > **Record Manager Security Group** to select and then enable a mail-enabled security group that contains the administrator accounts.</span></span>
    
    <span data-ttu-id="45f12-123">메일을 사용할 수 없는 Microsoft 365 그룹 및 보안 그룹은 이 기능을 지원하지 않으므로 선택할 목록에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-123">Microsoft 365 groups and security groups that aren't mail-enabled doesn't support this feature and wouldn't be displayed in the list to select.</span></span> <span data-ttu-id="45f12-124">새 메일 사용 보안 그룹을 만들어야 하는 경우 Microsoft 365 관리 센터에 대한 링크를 사용하여 새 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-124">If you need to create a new mail-enabled security group, use the link to the Microsoft 365 admin center to create the new group.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="45f12-125">규정 준수 센터에서 이 권한을 실행 중지하거나 실행한 그룹을 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-125">You can't disable this permission or replace the group that you enabled from the compliance center.</span></span> <span data-ttu-id="45f12-126">그러나 [Enable-ComplianceTagStorage](/powershell/module/exchange/enable-compliancetagstorage) cmdlet을 사용하여 다른 메일 사용 보안 그룹을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-126">However, you can enable another mail-enabled security group by using the [Enable-ComplianceTagStorage](/powershell/module/exchange/enable-compliancetagstorage) cmdlet.</span></span>
    > 
    > <span data-ttu-id="45f12-127">예: `Enable-ComplianceTagStorage -RecordsManagementSecurityGroupEmail dispositionreviewers@contosoi.com`</span><span class="sxs-lookup"><span data-stu-id="45f12-127">For example: `Enable-ComplianceTagStorage -RecordsManagementSecurityGroupEmail dispositionreviewers@contosoi.com`</span></span>

- <span data-ttu-id="45f12-128">미리 보기에서 **레코드 관리 설정** 옵션은 레코드 관리 관리자에게만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-128">In preview: The **Records management settings** option is visible only to record management administrators.</span></span> 

### <a name="enable-auditing"></a><span data-ttu-id="45f12-129">감사 사용</span><span class="sxs-lookup"><span data-stu-id="45f12-129">Enable auditing</span></span>

<span data-ttu-id="45f12-130">첫 처리 작업 최소 하루 이전에 감사를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-130">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="45f12-131">자세한 내용은 [Office 365 보안 &amp; 준수 센터에서 감사 로그 검색](search-the-audit-log-in-security-and-compliance.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45f12-131">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="45f12-132">처리 검토</span><span class="sxs-lookup"><span data-stu-id="45f12-132">Disposition reviews</span></span>

<span data-ttu-id="45f12-p108">콘텐츠의 보존 기간이 만료되면 해당 콘텐츠를 검토하고 영구적으로 삭제할 수 있는지 여부를 확인하는 몇 가지 이유가 있습니다(폐기). 예를 들어 콘텐츠를 삭제하는 대신 다음 작업을 수행해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-p108">When content reaches the end of its retention period, there are several reasons why you might want to review that content and confirm whether it can be permanently deleted ("disposed"). For example, instead of deleting the content, you might need to:</span></span>
  
- <span data-ttu-id="45f12-135">소송 또는 감사를 위해 관련 콘텐츠의 지우기 일시 중단</span><span class="sxs-lookup"><span data-stu-id="45f12-135">Suspend the deletion of relevant content for litigation or an audit.</span></span>

- <span data-ttu-id="45f12-136">원래 보존 설정이 임시 혹은 잠정적 솔루션이어서 콘텐츠에 다른 보존 기간을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-136">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>

- <span data-ttu-id="45f12-137">예를 들어, 기존 위치에서 보관 위치로 콘텐츠를 이동합니다(예: 해당 내용이 연구 또는 과거 가치가 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="45f12-137">Move the content from its existing location to an archive location, for example, if that content has research or historical value.</span></span>

<span data-ttu-id="45f12-138">보존 기간이 끝날 때 처리 검토가 트리거되는 경우:</span><span class="sxs-lookup"><span data-stu-id="45f12-138">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="45f12-139">선택한 검토자는 검토할 콘텐츠가 있다는 전자 메일 통보를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-139">The reviewers you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="45f12-140">이러한 검토자는 개별 사용자 또는 메일 사용 보안 그룹일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-140">These reviewers can be individual users or mail-enabled security groups.</span></span> <span data-ttu-id="45f12-141">미리 보기의 새로운 기능:</span><span class="sxs-lookup"><span data-stu-id="45f12-141">New in preview:</span></span>
   - <span data-ttu-id="45f12-142">다른 언어의 지시사항을 포함하여 수신하는 전자 메일을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-142">You can customize the email that they receive, including instructions in different languages.</span></span> <span data-ttu-id="45f12-143">다국어 지원을 받으려면 변환을 직접 지정해야 하며 이 사용자 지정 텍스트는 해당 로캘에 관계없이 모든 검토자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-143">For multi-language support, you must specify the translations yourself and this custom text is displayed to all reviewers irrespective of their locale.</span></span>
   - <span data-ttu-id="45f12-144">사용자는 항목의 보존 기간이 끝나면 레이블당 초기 전자 메일 알림을 받고, 레이블당 1주일에 한 번씩 할당된 모든 처리 검토에 대한 알림 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-144">Users receive an initial email notification per label at the end of the item's retention period, with a reminder per label once a week of all disposition reviews that they are assigned.</span></span> <span data-ttu-id="45f12-145">알림 및 알림 전자 메일의 링크를 클릭하여 Microsoft 365 규정 준수 센터의 **처리** 페이지로 이동하여 콘텐츠를 검토하고 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-145">They can click the link in the notification and reminder emails to go to the **Disposition** page in the Microsoft 365 compliance center to review the content and take an action.</span></span> <span data-ttu-id="45f12-146">또는 검토자가 규정 준수 센터의 **처리** 페이지로 직접 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-146">Alternately, the reviewers can go directly to the **Disposition** page in the compliance center.</span></span>
   - <span data-ttu-id="45f12-147">검토자는 자신에게 할당된 처리 검토만 보는 반면, 선택한 기록 관리자 보안 그룹에 추가된 관리자는 모든 처리 검토를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-147">Reviewers see only the disposition reviews that are assigned to them, whereas administrators who are added to the selected Record Manager Security Group see all disposition reviews.</span></span>
   - <span data-ttu-id="45f12-148">검토자는 동일한 처리 검토에 새 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-148">Reviewers can add new users to the same disposition review.</span></span> <span data-ttu-id="45f12-149">현재 이 작업은 추가된 사용자에게 필요한 [사용 권한](#permissions-for-disposition)을 자동으로 부여하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-149">Currently, this action doesn't automatically grant these added users the [required permissions](#permissions-for-disposition).</span></span>
   - <span data-ttu-id="45f12-150">처리 검토 프로세스의 경우, 볼 수 있는 권한이 있다면 각 항목에 대한 미니 검토 창에 콘텐츠의 미리 보기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-150">For the disposition review process, a mini-review pane for each item shows a preview of the content if they have permissions to see it.</span></span> <span data-ttu-id="45f12-151">권한이 없는 경우 콘텐츠 링크를 선택하고 권한을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-151">If they don't have permissions, they can select the content link and request permissions.</span></span> <span data-ttu-id="45f12-152">이 미니 검토 창에는 콘텐츠에 대한 추가 정보 탭도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-152">This mini-review pane also has tabs for additional information about the content:</span></span>
       - <span data-ttu-id="45f12-153">인덱싱된 속성, 해당 속성이 있는 위치, 해당 속성을 생성한 사용자 및 시기, 마지막으로 수정한 사용자 및 시기를 표시하는 **세부 정보** 입니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-153">**Details** to display indexed properties, where it's located, who created it and when, and who last modified it and when.</span></span>
       - <span data-ttu-id="45f12-154">사용 가능한 경우 검토자 설명과 함께 현재까지 모든 처리 검토 작업의 기록을 보여 주는 **기록** 입니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-154">**History** that shows the history of any disposition review actions to date, with reviewer comments if available.</span></span>

<span data-ttu-id="45f12-155">처리 검토에는 Exchange 편지함, SharePoint 사이트 및 OneDrive 계정의 콘텐츠가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-155">A disposition review can include content in Exchange mailboxes, SharePoint sites, and OneDrive accounts.</span></span> <span data-ttu-id="45f12-156">해당 위치에서 처리 검토 대기 중인 콘텐츠는 처리 최종 스테이지에 대한 검토자가 콘텐츠 영구 삭제를 선택한 후에만 영구히 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-156">Content pending a disposition review in those locations is permanently deleted only after a reviewer for the final stage of disposition chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="45f12-157">처리 검토를 지원하려면 사서함에 10MB 이상의 데이터가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-157">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="45f12-158">관리자는 보류 중인 모든 배치에 대한 개요를 **개요** 탭에서 볼 수 있습니다. 검토자는 처리 보류 중인 항목만 봅니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-158">Administrators can see an overview of all pending dispositions in the **Overview** tab. Reviewers see only their items pending disposition.</span></span> <span data-ttu-id="45f12-159">예:</span><span class="sxs-lookup"><span data-stu-id="45f12-159">For example:</span></span>

![레코드 관리에서 보류 중인 처리 개요](../media/dispositions-overview.png)

<span data-ttu-id="45f12-161">**보류 중인 모든 처리 보기** 를 선택하면 **처리** 페이지로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-161">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="45f12-162">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-162">For example:</span></span>

![Microsoft 365 규정 준수 센터의 처리 페이지](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="45f12-164">처리 검토를 위한 워크플로</span><span class="sxs-lookup"><span data-stu-id="45f12-164">Workflow for a disposition review</span></span>

<span data-ttu-id="45f12-165">다음 다이어그램에서는 보존 레이블을 게시한 다음 사용자가 수동으로 적용하는 경우 처리 검토에 대한 기본 워크플로를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-165">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="45f12-166">또는 처리 검토를 위해 구성된 보존 레이블을 콘텐츠에 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-166">Alternatively, a retention label configured for a disposition review can be automatically applied to content.</span></span>
  
![처리 작업 진행 방식의 흐름을 보여 주는 차트](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)

### <a name="how-to-configure-a-retention-label-for-disposition-review"></a><span data-ttu-id="45f12-168">처리 검토를 위해 보존 레이블을 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="45f12-168">How to configure a retention label for disposition review</span></span>

<span data-ttu-id="45f12-169">보존 기간이 끝날 때 처리 검토를 트리거하는 것은 보존 레이블과만 함께 제공되는 구성 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-169">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="45f12-170">보존 정책에 대해 처리 검토를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-170">Disposition review is not available for a retention policy.</span></span> <span data-ttu-id="45f12-171">이 두 가지 보존 솔루션에 대한 자세한 내용은 [보존 정책과 보존 레이블에 대해 알아보기](retention.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45f12-171">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>

<span data-ttu-id="45f12-172">보존 레이블을 위한 **보존 설정 정의** 페이지에서:</span><span class="sxs-lookup"><span data-stu-id="45f12-172">From the **Define retention settings** page for a retention label:</span></span>

![레이블에 대한 보존 설정](../media/disposition-review-option.png)
 
<span data-ttu-id="45f12-174">이 **처리 검토 트리거** 옵션을 선택한 후 마법사의 다음 페이지에서 원하는 연속 처리 스테이지 수와 각 스테이지에 대한 처리 검토자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-174">After you select this **Trigger a disposition review** option, on the next page of the wizard, you specify how many consecutive stages of disposition you want and the disposition reviewers for each stage:</span></span>

![처리 검토자 지정](../media/disposition-reviewers.png) 

<span data-ttu-id="45f12-176">**스테이지 추가** 를 선택하고 식별을 위해 스테이지 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-176">Select **Add a stage**, and name your stage for identification purposes.</span></span> <span data-ttu-id="45f12-177">그런 다음 해당 스테이지에 대한 검토자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-177">Then specify the reviewers for that stage.</span></span>

<span data-ttu-id="45f12-178">검토자의 경우 사용자 또는 메일 사용이 가능한 보안 그룹을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-178">For the reviewers, specify a user or a mail-enabled security group.</span></span> <span data-ttu-id="45f12-179">이 옵션에 대해 Microsoft 365 그룹([이전 Office 365 그룹](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601))은 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-179">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are currently not supported for this option.</span></span>

<span data-ttu-id="45f12-180">보존 기간이 끝날 때 항목을 검토하는 데 둘 이상의 사용자가 필요한 경우 **스테이지 추가** 를 다시 선택하고 필요한 스테이지 수에 대해 구성 프로세스를 최대 5개의 스테이지까지 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-180">If you need more than one person to review an item at the end of its retention period, select **Add a stage** again and repeat the configuration process for the number of stages that you need, with a maximum of five stages.</span></span> 

<span data-ttu-id="45f12-181">각 개별 처리 스테이지 내에서, 해당 스테이지에 대해 지정한 사용자는 보존 기간이 끝날 때 항목에 대해 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-181">Within each individual stage of disposition, any of the users you specify for that stage are authorized to take the next action for the item at the end of its retention period.</span></span> <span data-ttu-id="45f12-182">이러한 사용자는 처리 검토 스테이지에 다른 사용자를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-182">These users can also add other users to their disposition review stage.</span></span>

> [!NOTE]
> <span data-ttu-id="45f12-183">처리 검토를 위해 구성된 기존 보존 레이블은 레이블을 구성하여 다중 스테이지 처리 검토를 사용하도록 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-183">Existing retention labels that are configured for disposition review can be upgraded to use multi-staged disposition review by configuring the label.</span></span> <span data-ttu-id="45f12-184">레이블 마법사에서 **스테이지 추가** 를 선택하거나 기존 검토자 편집 또는 새 검토자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-184">In the label wizard, select **Add a stage**, or edit the existing reviewers or add new reviewers.</span></span>

<span data-ttu-id="45f12-185">구성 단계에서 지정된 각 스테이지에 대해 스테이작업 옵션(**...**)을 선택하여 이름을 변경하거나 순서를 변경하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-185">During the configuration phase, for each stage specified, you can rename it, reorder it, or remove it by selecting the Stage actions option (**...**):</span></span> 

![처리 검토를 위한 스테이지 작업](../media/stage-actions-disposition-review.png)

<span data-ttu-id="45f12-187">그러나 보존 레이블을 만든 후에는 스테이지를 다시 정렬하거나 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-187">However, you can't reorder or remove a stage after you have created the retention label.</span></span>

<span data-ttu-id="45f12-188">검토자를 지정한 후에는 **처리 관리** 역할 사용 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-188">After you have specified your reviewers, remember to grant them the **Disposition Management** role permission.</span></span> <span data-ttu-id="45f12-189">자세한 콘텐츠는 이 페이지의 [처리 권한](#permissions-for-disposition) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45f12-189">For more information, see the [Permissions for disposition](#permissions-for-disposition) section on this page.</span></span>

### <a name="how-to-customize-email-messages-for-disposition-review"></a><span data-ttu-id="45f12-190">처리 검토를 위해 전자 메일 메시지를 사용자 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="45f12-190">How to customize email messages for disposition review</span></span>

<span data-ttu-id="45f12-191">또한 미리 보기에서 초기 알림 및 미리 알림에 대해 처리 검토자에게 보내는 전자 메일 메시지를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-191">Also in preview, you can customize the email messages that are sent to disposition reviewers for the initial notification and then reminders.</span></span>

<span data-ttu-id="45f12-192">규정 준수 센터의 모든 처리 페이지에서 **기록 관리 설정** 을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="45f12-192">From any of the Disposition pages in the compliance center, select **Record management settings**:</span></span>  

![기록 관리 설정](../media/record-management-settings.png)

<span data-ttu-id="45f12-194">그런 다음 **전자 메일 템플릿** 탭을 선택하고 기본 전자 메일 템플릿만 사용할지 아니면 기본 템플릿에 사용자 고유의 텍스트를 추가할지 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="45f12-194">Then select the **Email templates** tab, and specify whether you want to use just the default email templates, or add your own text to the default template.</span></span> <span data-ttu-id="45f12-195">사용자 지정 텍스트는 보존 레이블에 대한 정보 뒤와 다음 단계 지침 전에 전자 메일 지침에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-195">Your custom text is added to the email instructions after the information about the retention label and before the next steps instructions.</span></span>

<span data-ttu-id="45f12-196">모든 언어에 대한 텍스트를 추가할 수 있지만 형식과 이미지는 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-196">Text for all languages can be added, but formatting and images are currently unsupported.</span></span> <span data-ttu-id="45f12-197">URL 및 전자 메일 주소는 텍스트로 입력할 수 있으며, 전자 메일 클라이언트에 따라 사용자 지정된 전자 메일에 하이퍼링크 또는 포맷되지 않은 텍스트로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-197">URLs and email addresses can be entered as text and depending on the email client, display as hyperlinks or unformatted text in the customized email.</span></span>

<span data-ttu-id="45f12-198">추가할 예제 텍스트:</span><span class="sxs-lookup"><span data-stu-id="45f12-198">Example text to append:</span></span>

```console
If you need additional information, visit the helpdesk website (https://support.contoso.com) or send them an email (helpdesk@contoso.com).
```

<span data-ttu-id="45f12-199">변경 사항을 저장하려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-199">Select **Save** to save any changes.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="45f12-200">콘텐츠 보기 및 처리</span><span class="sxs-lookup"><span data-stu-id="45f12-200">Viewing and disposing of content</span></span>

<span data-ttu-id="45f12-201">콘텐츠를 검토할 준비가 되었음을 검토자가 전자 메일로 알림을 받는 경우, Microsoft 365 준수 센터의 **레코드 관리** 에서 **처리** 탭으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-201">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="45f12-202">검토자는 **유형** 이 **처리 보류** 로 표시되어 처리를 기다리고 있는 각 보존 레이블의 항목 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-202">The reviewers can see how many items for each retention label are awaiting disposition with the **Type** displaying **Pending disposition**.</span></span> <span data-ttu-id="45f12-203">그런 다음 보존 레이블을 선택하고 **새 창에서 열기** 를 선택하여 해당 레이블의 모든 콘텐츠를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-203">They then select a retention label, and **Open in new window** to see all content with that label:</span></span>

![처리 검토를 위해 새 창에서 열기](../media/open-in-new-window.png)

<span data-ttu-id="45f12-205">**보류 중인 처리** 페이지에 해당 레이블에 대해 보류 중인 모든 처리가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-205">From the **Pending dispositions** page, they see all pending dispositions for that label.</span></span> <span data-ttu-id="45f12-206">하나 이상의 항목을 선택하면 미니 미리 보기 창과 **원본**, **세부 정보** 및 **기록** 탭을 사용하여 콘텐츠를 검사한 후 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-206">When one or more items are selected, they can use the mini-preview pane and the **Source**, **Details**, and **History** tab to inspect the content before taking action on it:</span></span>

![처리 옵션](../media/retention-disposition-options.png)

<span data-ttu-id="45f12-208">수평 스크롤 막대를 사용하거나 최소 검토 창을 닫으면 만료 날짜 및 처리 검토 스테이지의 이름이 포함된 열이 추가로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-208">If you use the horizontal scroll bar, or close the min-review pane, you see more columns that include the expiry date and the name of the disposition review stage.</span></span>

<span data-ttu-id="45f12-209">표시된 예에서 볼 수 있듯이 지원되는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-209">As you can see from the example shown, the actions supported are:</span></span> 
  
- <span data-ttu-id="45f12-210">**폐기 승인**:</span><span class="sxs-lookup"><span data-stu-id="45f12-210">**Approve disposal**:</span></span>
    - <span data-ttu-id="45f12-211">이 작업을 임시 처리 검토 스테이지로 선택한 경우(여러 스테이지를 구성함), 항목이 다음 처리 스테이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-211">When this action is selected for an interim stage of disposition review (you have configured multiple stages): The item moves to the next disposition stage.</span></span>
    - <span data-ttu-id="45f12-212">이 작업이 처리 검토의 최종 스테이지에 선택되거나 처리 스테이지가 하나만 있는 경우: 항목은 영구 삭제 대상으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-212">When this action is selected for the final stage of disposition review, or there is only one stage of disposition: The item is marked as eligible for permanent deletion.</span></span> <span data-ttu-id="45f12-213">정확한 삭제 시기는 워크로드에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-213">The exact timing for that deletion depends on the workload.</span></span> <span data-ttu-id="45f12-214">자세한 콘텐츠는 [보존 설정이 콘텐츠와 함께 작동하는 방법](retention.md#how-retention-settings-work-with-content-in-place)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45f12-214">For more information, see [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>
- <span data-ttu-id="45f12-215">**레이블 변경**:</span><span class="sxs-lookup"><span data-stu-id="45f12-215">**Relabel**:</span></span>
    - <span data-ttu-id="45f12-216">이 작업을 선택하면 항목이 원래 레이블에 대한 처리 검토 프로세스를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-216">When this action is selected, the item exits the disposition review process for the original label.</span></span> <span data-ttu-id="45f12-217">그런 다음 항목은 새로 선택한 보존 레이블의 보존 설정을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-217">The item is then subject to the retention settings of the newly selected retention label.</span></span>
- <span data-ttu-id="45f12-218">**확장**:</span><span class="sxs-lookup"><span data-stu-id="45f12-218">**Extend**:</span></span>
    - <span data-ttu-id="45f12-219">이 작업을 선택하면 처리 검토가 연장 기간이 끝날 때까지 사실상 중단되었다가 첫 번째 스테이지부터 처리 검토가 다시 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-219">When this action is selected, disposition review is effectively suspended until the end of the extended period and then disposition review is triggered again from the first stage.</span></span>
- <span data-ttu-id="45f12-220">**검토자 추가**:</span><span class="sxs-lookup"><span data-stu-id="45f12-220">**Add reviewers**:</span></span>
    - <span data-ttu-id="45f12-221">이 작업을 선택하면 검토를 위해 다른 사용자를 지정하고 추가하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-221">When this action is selected, the user is prompted to specify and add other users for review.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="45f12-222">이 작업은 추가된 사용자에게 [필수 사용 권한](#permissions-for-disposition)을 자동으로 부여하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-222">This action doesn't automatically grant the [required permissions](#permissions-for-disposition) to the users who are added.</span></span> <span data-ttu-id="45f12-223">해당 사용자에게 이러한 사용 권한이 없으면 사용자가 처리 검토에 참여할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-223">If they don't have these permissions, they won't be able to participate in the disposition review.</span></span>

<span data-ttu-id="45f12-224">각 작업은 아직 감사 로그에서 검색할 수 없는 경우에도 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-224">Each action taken is saved and stored although you can't yet search for them in the audit log.</span></span>

<span data-ttu-id="45f12-225">처리 검토 중에는 콘텐츠가 원래 위치에서 이동하지 않으며, 최종 또는 유일한 처리 스테이지에서 검토자가 이 작업을 선택할 때까지 영구 삭제로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-225">During a disposition review, the content never moves from its original location, and it's not marked for permanent deletion until this action is selected by a reviewer for the final or only disposition stage.</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="45f12-226">레코드 처리</span><span class="sxs-lookup"><span data-stu-id="45f12-226">Disposition of records</span></span>

<span data-ttu-id="45f12-227">**레코드 관리** 페이지의 **처리** 탭을 사용하여 다음을 식별하세요.</span><span class="sxs-lookup"><span data-stu-id="45f12-227">Use the **Disposition** tab from the **Records Management** page to identify:</span></span>

- <span data-ttu-id="45f12-228">처리 검토 결과로 삭제된 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-228">Items deleted as a result of a disposition review.</span></span>
- <span data-ttu-id="45f12-229">보관 기간이 끝날 때 자동으로 삭제된 레코드 또는 규제 레코드로 표시된 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-229">Items marked as a record or regulatory record that were automatically deleted at the end of their retention period.</span></span>

<span data-ttu-id="45f12-230">이러한 항목에는 **유형** 열에 **처리된 레코드** 를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-230">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="45f12-231">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-231">For example:</span></span>

![처리 검토가 없이 처리된 항목](../media/records-disposed2.png)

<span data-ttu-id="45f12-233">**처리된 항목** 탭에 표시되는 항목은 항목이 처리된 후 최대 7년간 유지되고, 해당 기간에 대한 레코드 당 100만 항목의 제한을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-233">Items that are shown in the **Disposed Items** tab are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="45f12-234">**계산** 수가 이 100만의 제한에 근접하고 레코드에 대한 처리 증거가 필요한 경우, [Microsoft 지원](../business-video/get-help-support.md)에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="45f12-234">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](../business-video/get-help-support.md).</span></span>

> [!NOTE]
> <span data-ttu-id="45f12-235">이 기능은 [통합 감사 로그](search-the-audit-log-in-security-and-compliance.md)의 정보를 사용하며, 따라서 해당 이벤트를 캡처할 수 있도록 감사를 [사용하도록 설정하고 검색 가능하도록](turn-audit-log-search-on-or-off.md) 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-235">This functionality uses information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>

<span data-ttu-id="45f12-236">레코드 또는 규제 레코드로 표시된 삭제된 항목을 감사하려면 **파일 및 페이지 활동** 카테고리에서 **레코드로 표시된 삭제된 파일** 을 검색하세요.</span><span class="sxs-lookup"><span data-stu-id="45f12-236">For auditing of deleted items that were marked as records or regulatory records, search for **Deleted file marked as a record** in the **File and page activities** category.</span></span> <span data-ttu-id="45f12-237">이 감사 이벤트는 문서 및 이일에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-237">This audit event is applicable to documents and emails.</span></span>

## <a name="filter-and-export-the-views"></a><span data-ttu-id="45f12-238">보기 필터링 및 내보내기</span><span class="sxs-lookup"><span data-stu-id="45f12-238">Filter and export the views</span></span>

<span data-ttu-id="45f12-239">**처리** 페이지에서 보존 레이블을 선택하는 경우, **보류 중인 처리** 탭(해당 하는 경우)과 **처리된 항목** 탭을 사용하여 보기를 필터링하여 항목을 보다 쉽게 찾을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-239">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span>

<span data-ttu-id="45f12-240">보류 중인 처리의 경우에는 시간 범위가 만료 날짜를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-240">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="45f12-241">처리된 항목의 경우에는 시간 범위가 삭제 날짜를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-241">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="45f12-242">아래의 항목에 대한 정보를 .csv 파일로 내보낼 수 있습니다. 그런 다음 Excel을 사용하여 정렬을 하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f12-242">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel.</span></span>
