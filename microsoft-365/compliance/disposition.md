---
title: 콘텐츠 처리
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 처리 검토를 사용 하 든, 구성 된 설정에 따라 콘텐츠를 자동으로 삭제할지 여부에 관계 없이 콘텐츠 삭제를 모니터링 하 고 관리 합니다.
ms.openlocfilehash: 5751857f8b3bf0a7f63df73e9bfaa244897bf429
ms.sourcegitcommit: 4ac96855d7c269a0055ca8943000b762a70ca4ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2020
ms.locfileid: "47321997"
---
# <a name="disposition-of-content"></a><span data-ttu-id="09fa4-103">콘텐츠 처리</span><span class="sxs-lookup"><span data-stu-id="09fa4-103">Disposition of content</span></span>

><span data-ttu-id="09fa4-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*</span><span class="sxs-lookup"><span data-stu-id="09fa4-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="09fa4-105">Microsoft 365 준수 센터의 **레코드 관리** 에서 **처리** 탭을 사용 하 여 처리 검토를 관리 하 고 보존 기간이 끝나면 자동으로 삭제 된 [레코드](records-management.md#records) 를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records-management.md#records) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="09fa4-106">콘텐츠 dispositions를 보기 위한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="09fa4-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="09fa4-107">처리 검토를 관리 하 고 레코드가 삭제 되었는지 확인 하려면 충분 한 사용 권한이 있어야 하 고 감사를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="09fa4-108">처리 권한</span><span class="sxs-lookup"><span data-stu-id="09fa4-108">Permissions for disposition</span></span>

<span data-ttu-id="09fa4-109">Microsoft 365 준수 센터의 **처리** 탭에 액세스 하려면 사용자에 게 **처리 관리** 관리자 역할이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** admin role.</span></span> <span data-ttu-id="09fa4-110">이 역할은 기본 관리자 역할 그룹, **준수 관리자** 및 **준수 데이터 관리자**에 게 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-110">This role is included in the default admin role groups, **Compliance Administrator** and **Compliance Data Administrator**.</span></span>

<span data-ttu-id="09fa4-111">사용자에 게이 필수 처리 관리 역할을 부여 하려면이를 기본 역할 그룹 중 하나에 추가 하거나 사용자 지정 역할 그룹 (예: "처리 검토자")을 만든 다음이 그룹에 처리 관리 역할을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-111">To grant users this required Disposition Management role, either add them to one of these default role groups, or create a custom role group (for example, named "Disposition Reviewers") and grant this group the Disposition Management role.</span></span>  

> [!NOTE]
> <span data-ttu-id="09fa4-112">전역 관리자 라도 **처리 관리** 역할을 부여 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-112">Even a global admin needs to be granted the **Disposition Management** role.</span></span> 

<span data-ttu-id="09fa4-113">[사용자에게 Office 365 보안 및 준수 센터에 대한 액세스 권한 부여](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09fa4-113">For instructions, see [Give users access to the Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="09fa4-114">감사 사용</span><span class="sxs-lookup"><span data-stu-id="09fa4-114">Enable auditing</span></span>

<span data-ttu-id="09fa4-115">감사 기능이 사용 하도록 설정 되어 있는지 확인 하 고 첫 번째 처리 작업 보다 하루 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-115">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="09fa4-116">자세한 내용은 [Office 365 보안 및 &amp; 준수 센터에서 감사 로그 검색](search-the-audit-log-in-security-and-compliance.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09fa4-116">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="09fa4-117">처리 검토</span><span class="sxs-lookup"><span data-stu-id="09fa4-117">Disposition reviews</span></span>

<span data-ttu-id="09fa4-118">콘텐츠가 보존 기간의 끝에 도달 하면 해당 콘텐츠를 검토 하 여 안전 하 게 삭제할 수 있는지 여부 ("삭제 된")를 결정 해야 하는 몇 가지 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-118">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="09fa4-119">예를 들어 다음을 수행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-119">For example, you might need to:</span></span>
  
- <span data-ttu-id="09fa4-120">소송 또는 감사의 경우 관련 콘텐츠 삭제를 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-120">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="09fa4-121">처리 목록에서 콘텐츠를 제거 하 여 해당 콘텐츠에 조사 또는 기록 값이 있는 경우 보관 사서함에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-121">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="09fa4-122">원래 보존 설정이 임시 또는 provisional 솔루션 이기 때문에 콘텐츠에 다른 보존 기간을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-122">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="09fa4-123">콘텐츠를 클라이언트에 반환 하거나 다른 조직으로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-123">Return the content to clients or transfer it to another organization.</span></span>

<span data-ttu-id="09fa4-124">처리 검토가 보존 기간이 끝날 때 트리거되는 경우:</span><span class="sxs-lookup"><span data-stu-id="09fa4-124">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="09fa4-125">선택한 사용자는 검토할 콘텐츠가 있는 전자 메일 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-125">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="09fa4-126">이러한 검토자는 개별 사용자 또는 메일 사용이 가능한 보안 그룹이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-126">These reviewers can be individual users or mail-enabled security groups.</span></span> <span data-ttu-id="09fa4-127">알림은 주 단위로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-127">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="09fa4-128">검토자가 Microsoft 365 준수 센터의 **처리** 탭으로 이동 하 여 콘텐츠를 검토 하 고이를 영구적으로 삭제할지, 보존 기간을 연장할 지 아니면 다른 보존 레이블을 적용할지를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-128">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="09fa4-129">처리 검토에는 Exchange 사서함, SharePoint 사이트, OneDrive 계정 및 Microsoft 365 그룹의 콘텐츠가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-129">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="09fa4-130">해당 위치에서 처리 검토를 대기 중인 콘텐츠는 검토자가 콘텐츠를 영구적으로 삭제 하도록 선택한 후에만 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-130">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="09fa4-131">처리 검토를 지원 하려면 사서함에 10mb 이상의 데이터가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-131">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="09fa4-132">**개요** 탭에서 모든 보류 중인 dispositions의 개요를 확인할 수 있습니다. 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="09fa4-132">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![레코드 관리 개요에서 보류 중인 dispositions](../media/dispositions-overview.png)

<span data-ttu-id="09fa4-134">**보류 중인 모든 Dispositions 보기**를 선택 하면 **처리** 페이지로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-134">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="09fa4-135">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="09fa4-135">For example:</span></span>

![Microsoft 365 준수 센터의 Dispositions 페이지](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="09fa4-137">처리 검토를 위한 워크플로</span><span class="sxs-lookup"><span data-stu-id="09fa4-137">Workflow for a disposition review</span></span>

<span data-ttu-id="09fa4-138">다음 다이어그램에서는 보존 레이블을 게시 한 다음 사용자가 수동으로 적용 하는 경우의 처리 검토에 대 한 기본 워크플로를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-138">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="09fa4-139">또한 처리 검토를 위해 구성 된 보존 레이블을 콘텐츠에 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-139">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![처리가 작동 하는 방식 흐름을 보여 주는 차트](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="09fa4-141">보존 기간이 끝날 때 처리 검토를 트리거하는 것은 보존 레이블과 함께 사용할 수 있는 구성 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-141">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="09fa4-142">보존 정책에는이 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-142">This option is not available for a retention policy.</span></span> <span data-ttu-id="09fa4-143">이러한 두 가지 보존 솔루션에 대 한 자세한 내용은 [보존 정책 및 보존 레이블에 대 한](retention.md)자세한 정보를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="09fa4-143">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>
  
![레이블에 대 한 보존 설정](../media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> <span data-ttu-id="09fa4-145">**검토할 준비가 된 항목이 있을 때 이러한 사용자에 게 알림**옵션을 선택 하면 사용자 또는 메일 사용이 가능한 보안 그룹을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-145">When you select the option **Notify these people when there are items ready to review**, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="09fa4-146">Microsoft 365 그룹 ([이전의 Office 365 그룹](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601))은이 옵션에 대해 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-146">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="09fa4-147">콘텐츠 보기 및 삭제</span><span class="sxs-lookup"><span data-stu-id="09fa4-147">Viewing and disposing of content</span></span>

<span data-ttu-id="09fa4-148">콘텐츠를 검토할 준비가 된 전자 메일로 검토자에 게 알림을 받으면 Microsoft 365 준수 센터의 **레코드 관리** 에서 **처리** 탭으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-148">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="09fa4-149">검토자는 처리를 위해 대기 중인 각 보존 레이블의 수를 확인 한 다음 보존 레이블을 선택 하 여 해당 레이블이 있는 모든 콘텐츠를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-149">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="09fa4-150">보존 레이블을 선택한 후에는 **보류 중인 처리** 탭에서 해당 레이블에 대 한 모든 보류 중인 dispositions을 볼 수 있습니다. 작업을 선택 하 고 사유 설명을 입력할 수 있는 항목을 하나 이상 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-150">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![처리 옵션](../media/retention-disposition-options.png)

<span data-ttu-id="09fa4-152">그림에서 볼 수 있듯이 지원 되는 동작은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-152">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="09fa4-153">항목을 영구적으로 삭제</span><span class="sxs-lookup"><span data-stu-id="09fa4-153">Permanently delete the item</span></span>
- <span data-ttu-id="09fa4-154">보존 기간 확장</span><span class="sxs-lookup"><span data-stu-id="09fa4-154">Extend the retention period</span></span>
- <span data-ttu-id="09fa4-155">다른 보존 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="09fa4-155">Apply a different retention label</span></span>

<span data-ttu-id="09fa4-156">위치 및 콘텐츠에 대 한 사용 권한을 부여 하면 **위치** 열의 링크를 사용 하 여 문서를 원래 위치에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-156">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="09fa4-157">처리 검토 중에는 콘텐츠가 원래 위치에서 이동 하지 않으며, 검토자가이를 선택 하기 전 까지는 삭제 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-157">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="09fa4-158">전자 메일 알림은 매주 검토자에 게 자동으로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-158">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="09fa4-159">이 일정 상의 프로세스는 콘텐츠가 보존 기간의 끝에 도달 하는 경우 검토자가 콘텐츠 처리를 기다리는 전자 메일 알림을 받는 데 최대 7 일이 걸릴 수 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-159">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="09fa4-160">모든 처리 작업을 감사 하 고 검토자가 입력 한 근거 텍스트를 저장 하 여 **삭제 된 항목** 페이지의 **메모** 열에 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-160">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="09fa4-161">삭제 된 콘텐츠가 영구적으로 삭제 될 때 까지의 기간</span><span class="sxs-lookup"><span data-stu-id="09fa4-161">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="09fa4-162">처리 검토를 기다리는 콘텐츠는 검토자가 콘텐츠를 영구적으로 삭제 하도록 선택한 후에만 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-162">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="09fa4-163">검토자가이 옵션을 선택 하면 SharePoint 사이트 또는 OneDrive 계정의 콘텐츠가 [보존 설정에서 콘텐츠 작업을 수행 하는 방식](retention.md#how-retention-settings-work-with-content-in-place)에 설명 된 표준 정리 프로세스를 수행할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-163">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="09fa4-164">콘텐츠 처분</span><span class="sxs-lookup"><span data-stu-id="09fa4-164">Disposition of records</span></span>

> [!NOTE]
> <span data-ttu-id="09fa4-165">SharePoint 및 OneDrive의 레코드에 대 한 삭제 증명 롤아웃이 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-165">The rollout for proof of disposal for records in SharePoint and OneDrive is complete.</span></span>
>
> <span data-ttu-id="09fa4-166">Exchange의 레코드에 대 한 삭제 증명은 방금 롤아웃을 시작 했습니다. 이 롤아웃이 완료 되 면이 노트가 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-166">Proof of disposal for records in Exchange has just started to roll out. When this rollout is complete, we will update this note.</span></span>

<span data-ttu-id="09fa4-167">**레코드 관리** 페이지의 **처리** 탭을 사용 하 여 자동으로 또는 처리 검토 후에 삭제 된 레코드를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-167">Use the **Disposition** tab from the **Records Management** page to identify records that are now deleted, either automatically or after a disposition review.</span></span> <span data-ttu-id="09fa4-168">이러한 항목은 **형식** 열에서 **삭제 된 레코드** 를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-168">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="09fa4-169">예를 들어,</span><span class="sxs-lookup"><span data-stu-id="09fa4-169">For example:</span></span>

![처리 검토 없이 삭제 된 항목](../media/records-disposed2.png)

<span data-ttu-id="09fa4-171">레코드 레이블에 대 한 삭제 된 **항목** 탭에 표시 되는 항목은 항목을 삭제 한 후 최대 7 년 동안 유지 되며 해당 기간에 대해 레코드 당 항목 제한은 100만 개입니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-171">Items that are shown in the **Disposed Items** tab for record labels are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="09fa4-172">이 100만에 도달 **하 고 레코드** 에 대 한 처리 증거를 요구 하는 경우에는 [Microsoft 지원](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)서비스에 문의 하십시오.</span><span class="sxs-lookup"><span data-stu-id="09fa4-172">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="09fa4-173">이 기능은 [통합 된 감사 로그](search-the-audit-log-in-security-and-compliance.md) 의 정보를 기반으로 하므로 해당 이벤트가 캡처될 수 있도록 감사를 [사용 하도록 설정 하 고 검색](turn-audit-log-search-on-or-off.md) 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-173">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>
    
## <a name="filter-and-export-the-views"></a><span data-ttu-id="09fa4-174">보기 필터링 및 내보내기</span><span class="sxs-lookup"><span data-stu-id="09fa4-174">Filter and export the views</span></span>

<span data-ttu-id="09fa4-175">**처리** 페이지에서 보존 레이블을 선택 하면 **보류 중인 처리** 탭 (해당 되는 경우) 및 **삭제 된 항목** 탭을 사용 하 여 보기를 필터링 하 여 항목을 보다 쉽게 찾을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-175">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="09fa4-176">보류 중인 dispositions의 경우 시간 범위는 만료 날짜를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-176">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="09fa4-177">삭제 된 항목의 경우에는 시간 범위가 삭제 날짜를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-177">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="09fa4-178">다음과 같이 보기의 항목에 대 한 정보를 .csv 파일로 내보낸 다음 Excel을 사용 하 여 정렬 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09fa4-178">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![폐기 옵션 내보내기](../media/retention-export-option.png)
  
![Excel에서 내보낸 처리 데이터](../media/08e3bc09-b132-47b4-a051-a590b697e725.png)


