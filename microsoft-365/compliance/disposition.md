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
description: 처리 검토를 사용하든 콘텐츠가 구성한 설정에 따라 자동으로 삭제되는지, 콘텐츠의 처리를 모니터링하고 관리합니다.
ms.openlocfilehash: a0fd71aa1eb7c0a7eff97e783f4b0dfb8a50a915
ms.sourcegitcommit: 61d7284b412d0f7bbd8bbb2225c2e6324f86b717
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262241"
---
# <a name="disposition-of-content"></a><span data-ttu-id="4855f-103">콘텐츠의 처리</span><span class="sxs-lookup"><span data-stu-id="4855f-103">Disposition of content</span></span>

><span data-ttu-id="4855f-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="4855f-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="4855f-105">Microsoft 365 준수 센터의 **레코드 관리**에서 **처리** 탭을 사용하여 처리 검토를 관리하고 보존 기간이 끝날 때 자동으로 삭제된 [레코드](records-management.md#records)를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records-management.md#records) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="4855f-106">콘텐츠 처리를 보기 위한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4855f-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="4855f-107">처리 검토를 관리하고 레코드가 삭제되었는지 확인하려면 충분한 권한이 필요하고 감사를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="4855f-108">처리 권한</span><span class="sxs-lookup"><span data-stu-id="4855f-108">Permissions for disposition</span></span>

<span data-ttu-id="4855f-109">Microsoft 365 준수 센터의 **처리** 탭에 액세스하려면 사용자에게 **처리 관리** 관리자 역할이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** admin role.</span></span> <span data-ttu-id="4855f-110">이 역할은 기본 관리자 역할 그룹, **준수 관리자** 및 **준수 데이터 관리자**에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-110">This role is included in the default admin role groups, **Compliance Administrator** and **Compliance Data Administrator**.</span></span>

<span data-ttu-id="4855f-111">사용자에게 이 필수 처리 관리 역할을 부여하려면 이러한 기본 역할 그룹 중 하나에 추가하거나 혹은 사용자 지정 역할 그룹을 만들고(예: 명명된 "처리 검토자") 이 그룹에 처리 관리 역할을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-111">To grant users this required Disposition Management role, either add them to one of these default role groups, or create a custom role group (for example, named "Disposition Reviewers") and grant this group the Disposition Management role.</span></span>  

> [!NOTE]
> <span data-ttu-id="4855f-112">전역 관리자 조차도 **처리 관리** 역할이 부여되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-112">Even a global admin needs to be granted the **Disposition Management** role.</span></span> 

<span data-ttu-id="4855f-113">지침은 [사용자에게 Office 365 보안 및 준수 센터에 대한 액세스 권한 부여](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4855f-113">For instructions, see [Give users access to the Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="4855f-114">감사 사용</span><span class="sxs-lookup"><span data-stu-id="4855f-114">Enable auditing</span></span>

<span data-ttu-id="4855f-115">첫 처리 작업 최소 하루 이전에 감사를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-115">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="4855f-116">자세한 내용은 [Office 365 보안 &amp; 준수 센터에서 감사 로그 검색](search-the-audit-log-in-security-and-compliance.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4855f-116">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="4855f-117">처리 검토</span><span class="sxs-lookup"><span data-stu-id="4855f-117">Disposition reviews</span></span>

<span data-ttu-id="4855f-118">콘텐츠가 보존 기간 끝에 도달하면 해당 콘텐츠를 검토하여 안전하게 삭제할 수 있는지 여부를 결정하는 몇 가지 이유가 있습니다("처분").</span><span class="sxs-lookup"><span data-stu-id="4855f-118">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="4855f-119">예를 들어 다음을 수행해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-119">For example, you might need to:</span></span>
  
- <span data-ttu-id="4855f-120">소송 또는 감사의 경우에 관련 콘텐츠의 삭제를 일시 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-120">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="4855f-121">해당 콘텐츠에 연구 또는 기록적 가치가 있는 경우 처리 목록에서 콘텐츠를 제거하여 보관함에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-121">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="4855f-122">원래 보존 설정이 임시 혹은 잠정적 솔루션이어서 콘텐츠에 다른 보존 기간을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-122">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="4855f-123">콘텐츠를 클라이언트에게 반환하거나 다른 조직으로 이전합니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-123">Return the content to clients or transfer it to another organization.</span></span>

<span data-ttu-id="4855f-124">보존 기간이 끝날 때 처리 검토가 트리거되는 경우:</span><span class="sxs-lookup"><span data-stu-id="4855f-124">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="4855f-125">선택하는 사용자는 검토할 콘텐츠가 있다는 전자 메일 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-125">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="4855f-126">이러한 검토자는 개별 사용자 또는 메일 사용이 가능한 보안 그룹이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-126">These reviewers can be individual users or mail-enabled security groups.</span></span> <span data-ttu-id="4855f-127">알림은 주 단위로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-127">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="4855f-128">검토자는 Microsoft 365 준수 센터의 **처리** 탭으로 이동하여 콘텐츠를 검토하고 영구적으로 삭제하거나, 보존 기간을 연장하거나, 다른 보존 레이블을 적용할 것인지 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-128">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="4855f-129">처리 검토에는 Exchange 사서함, SharePoint 사이트, OneDrive 계정 및 Microsoft 365 그룹의 콘텐츠가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-129">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="4855f-130">해당 위치에서 처리 검토를 기다리는 콘텐츠는 검토자가 콘텐츠를 영구적으로 삭제하도록 선택한 후에만 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-130">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="4855f-131">처리 검토를 지원하려면 사서함에 10MB 이상의 데이터가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-131">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="4855f-132">**개요** 탭에서 보류 중인 모든 처리의 개요를 볼 수 있습니다. 예를 들면:</span><span class="sxs-lookup"><span data-stu-id="4855f-132">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![레코드 관리에서 보류 중인 처리 개요](../media/dispositions-overview.png)

<span data-ttu-id="4855f-134">**보류 중인 모든 처리 보기**를 선택하면 **처리** 페이지로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-134">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="4855f-135">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-135">For example:</span></span>

![Microsoft 365 규정 준수 센터의 처리 페이지](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="4855f-137">처리 검토를 위한 워크플로</span><span class="sxs-lookup"><span data-stu-id="4855f-137">Workflow for a disposition review</span></span>

<span data-ttu-id="4855f-138">다음 다이어그램에서는 보존 레이블을 게시한 다음 사용자가 수동으로 적용하는 경우 처리 검토에 대한 기본 워크플로를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-138">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="4855f-139">또는 처리 검토를 위해 구성한 보존 레이블을 콘텐츠에 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-139">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![처리 작업 진행 방식의 흐름을 보여 주는 차트](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="4855f-141">보존 기간이 끝날 때 처리 검토를 트리거하는 것은 보존 레이블과만 함께 제공되는 구성 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-141">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="4855f-142">보존 정책에는 이 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-142">This option is not available for a retention policy.</span></span> <span data-ttu-id="4855f-143">이 두 가지 보존 솔루션에 대한 자세한 내용은 [보존 정책과 보존 레이블에 대해 알아보기](retention.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4855f-143">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>

<span data-ttu-id="4855f-144">보존 레이블을 위한 **보존 설정 정의** 페이지에서:</span><span class="sxs-lookup"><span data-stu-id="4855f-144">From the **Define retention settings** page for a retention label:</span></span>

![레이블에 대한 보존 설정](../media/disposition-review-option.png)
 
<span data-ttu-id="4855f-146">이 **처리 검토 트리거** 옵션을 선택한 후, 마법사의 다음 페이지에서 처리 검토자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-146">After you select this **Trigger a disposition review** option, you specify the disposition reviewers on the next page of the wizard:</span></span>

![처리 검토자 지정](../media/disposition-reviewers.png)

<span data-ttu-id="4855f-148">검토자의 경우 사용자 또는 메일 사용이 가능한 보안 그룹을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-148">For the reviewers, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="4855f-149">이 옵션에 대해 Microsoft 365 그룹([이전 Office 365 그룹](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601))은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-149">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="4855f-150">콘텐츠 보기 및 처리</span><span class="sxs-lookup"><span data-stu-id="4855f-150">Viewing and disposing of content</span></span>

<span data-ttu-id="4855f-151">콘텐츠를 검토할 준비가 되었음을 검토자가 전자 메일로 알림을 받는 경우, Microsoft 365 준수 센터의 **레코드 관리**에서 **처리** 탭으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-151">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="4855f-152">검토자는 각 보존 레이블에 대해 얼마나 많은 항목이 처리를 대기 중인지 확인할 수 있고, 보존 레이블을 선택하여 해당 레이블이 있는 모든 콘텐츠를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-152">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="4855f-153">보존 레이블을 선택한 후, **보류 중인 처리** 탭에서 해당 레이블에 대해 보류 중인 모든 처리를 보게됩니다. 한 개 이상의 항목을 선택하여 작업을 선택하고 사유 메모를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-153">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![처리 옵션](../media/retention-disposition-options.png)

<span data-ttu-id="4855f-155">그림에서 볼 수 있듯이 지원되는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-155">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="4855f-156">항목을 영구적으로 삭제</span><span class="sxs-lookup"><span data-stu-id="4855f-156">Permanently delete the item</span></span>
- <span data-ttu-id="4855f-157">보존 기간 연장</span><span class="sxs-lookup"><span data-stu-id="4855f-157">Extend the retention period</span></span>
- <span data-ttu-id="4855f-158">다른 보존 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="4855f-158">Apply a different retention label</span></span>

<span data-ttu-id="4855f-159">위치와 콘텐츠에 대한 사용 권한을 보유하면 **위치** 열에 있는 링크를 사용하여 원래 위치에 있는 문서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-159">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="4855f-160">처리 검토를 진행하는 동안 콘텐츠는 원래 위치에서 이동할 수 없으며, 검토자가 그렇게 하도록 선택하기 전에는 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-160">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="4855f-161">전자 메일 알림은 주 단위로 자동으로 검토자에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-161">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="4855f-162">이 예약된 프로세스는 콘텐츠가 보존 기간의 끝에 도달하는 경우, 검토자자 콘텐츠가 처리를 기다리고 있다는 전자 메일 알림을 받는 데 최대 7일이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-162">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="4855f-163">모든 처리 작업은 감사되고 검토자가 입력한 사유 텍스트는 저장되어 **처리된 항목** 페이지의 **메모** 열에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-163">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="4855f-164">처리된 콘텐츠가 영구적으로 삭제될 때까지 걸리는 시간</span><span class="sxs-lookup"><span data-stu-id="4855f-164">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="4855f-165">처리 검토를 기다리는 콘텐츠는 검토자가 콘텐츠를 영구적으로 삭제하도록 선택한 후에만 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-165">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="4855f-166">검토자가 이 옵션을 선택하는 경우, SharePoint 사이트 또는 OneDrive 계정의 콘텐츠가 [보존 설정이 적소에 있는 콘텐츠와 작동하는 방법](retention.md#how-retention-settings-work-with-content-in-place)에 설명된 표준 정리 프로세스를 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-166">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="4855f-167">레코드 처리</span><span class="sxs-lookup"><span data-stu-id="4855f-167">Disposition of records</span></span>

<span data-ttu-id="4855f-168">**레코드 관리** 페이지의 **처리** 탭을 사용하여 자동으로 또는 처리 검토 후에 현재 삭제된 레코드를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-168">Use the **Disposition** tab from the **Records Management** page to identify records that are now deleted, either automatically or after a disposition review.</span></span> <span data-ttu-id="4855f-169">이러한 항목에는 **유형** 열에 **처리된 레코드**를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-169">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="4855f-170">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-170">For example:</span></span>

![처리 검토가 없이 처리된 항목](../media/records-disposed2.png)

<span data-ttu-id="4855f-172">레코드 레이블을 위해 **처리된 항목** 탭에 표시되는 항목은 항목이 처리된 후 최대 7년간 유지되고, 해당 기간에 대한 레코드 당 100만 항목의 제한을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-172">Items that are shown in the **Disposed Items** tab for record labels are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="4855f-173">**계산** 수가 이 100만의 제한에 근접하고 레코드에 대한 처리 증거가 필요한 경우, [Microsoft 지원](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="4855f-173">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="4855f-174">이 기능은 [통합 감사 로그](search-the-audit-log-in-security-and-compliance.md)의 정보를 기초로 하며, 따라서 해당 이벤트를 캡처할 수 있도록 감사를 [사용하도록 설정하고 검색 가능하도록](turn-audit-log-search-on-or-off.md) 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-174">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>
    
## <a name="filter-and-export-the-views"></a><span data-ttu-id="4855f-175">보기 필터링 및 내보내기</span><span class="sxs-lookup"><span data-stu-id="4855f-175">Filter and export the views</span></span>

<span data-ttu-id="4855f-176">**처리** 페이지에서 보존 레이블을 선택하는 경우, **보류 중인 처리** 탭(해당 하는 경우)과 **처리된 항목** 탭을 사용하여 보기를 필터링하여 항목을 보다 쉽게 찾을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-176">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="4855f-177">보류 중인 처리의 경우에는 시간 범위가 만료 날짜를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-177">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="4855f-178">처리된 항목의 경우에는 시간 범위가 삭제 날짜를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-178">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="4855f-179">아래의 항목에 대한 정보를 .csv 파일로 내보낼 수 있습니다. 그런 다음 Excel을 사용하여 정렬을 하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4855f-179">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![처리에 대한 내보내기 옵션](../media/retention-export-option.png)

