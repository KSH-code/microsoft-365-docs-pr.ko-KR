---
title: Microsoft 365의 레코드 관리하기
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Microsoft 365의 레코드 관리를 사용하여 보존 일정을 파일 플랜에 적용하여 보존, 레코드 선언, 처리를 관리할 수 있습니다.
ms.openlocfilehash: d8ea68d8fbbf67928bae4f6d09712658f364e3ef
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868913"
---
# <a name="learn-about-records-management-in-microsoft-365"></a><span data-ttu-id="5bdca-103">Microsoft 365의 레코드 관리하기에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="5bdca-103">Learn about records management in Microsoft 365</span></span>

><span data-ttu-id="5bdca-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="5bdca-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="5bdca-105">모든 유형의 조직에는 레코드 관리 솔루션이 있어야 회사 데이터에서 규정, 법률 및 비즈니스에 중요한 레코드를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="5bdca-106">Microsoft 365의 레코드 관리는 조직이 법적인 의무를 관리하는 데 도움이 되고, 규정 준수를 입증하는 기능을 제공하며, 비즈니스 목적에 대해 더 이상 보존할 필요가 없거나, 더 이상 가치가 없거나, 사용하지 않는 항목을 정기적으로 처리하여 효율성을 높입니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="5bdca-107">Microsoft 365에서 다음 기능을 사용하여 레코드 관리 솔루션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-107">Use the following capabilities to support your records management solution in Microsoft 365:</span></span>

- <span data-ttu-id="5bdca-108">**콘텐츠를 레코드로 레이블**</span><span class="sxs-lookup"><span data-stu-id="5bdca-108">**Label content as a record**.</span></span> <span data-ttu-id="5bdca-109">콘텐츠를 사용자가 적용하거나 중요한 정보, 키워드 또는 콘텐츠 유형을 식별하여 자동으로 적용할 수 있는 [레코드](#records)로 표시하는 보존 레이블을 작성하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-109">Create and configure retention labels to mark content as a [record](#records) that can then be applied by users or automatically applied by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="5bdca-110">**파일 계획을 사용하여 보존 요구 사항을 마이그레이션하고 관리합니다**.</span><span class="sxs-lookup"><span data-stu-id="5bdca-110">**Migrate and manage your retention requirements with file plan**.</span></span> <span data-ttu-id="5bdca-111">[파일 계획](file-plan-manager.md)을 사용하여 기존 보존 계획을 Microsoft 365으로 가져오거나 개선된 관리 기능을 위해 새 계획을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-111">By using a [file plan](file-plan-manager.md), you can bring in an existing retention plan to Microsoft 365, or build a new one for enhanced management capabilities.</span></span>

- <span data-ttu-id="5bdca-112">**보존 레이블을 사용하여 보존 및 삭제 설정을 구성합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bdca-112">**Configure retention and deletion settings with retention labels**.</span></span> <span data-ttu-id="5bdca-113">마지막으로 수정 또는 생성된 날짜를 포함하는 다양한 요소를 기반으로 보존 기간 및 작업을 사용하여 [보존 레이블](retention.md#retention-labels)을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-113">Configure [retention labels](retention.md#retention-labels) with the retention periods and actions based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="5bdca-114">[이벤트 기반 보존\*\*을 사용하여 \*\*이벤트가 발생하는 경우 다른 보존 기간을 시작](event-driven-retention.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-114">**Start different retention periods when an event occurs** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="5bdca-115">[처리 검토](disposition.md#disposition-reviews) 및 [레코드 삭제](disposition.md#disposition-of-records) 검사를 통해 **처리를 검토하고 확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-115">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="5bdca-116">[내보내기 옵션](disposition.md#filter-and-export-the-views)으로 **모든 처리된 항목에 대한 정보를 내보냅니다**.</span><span class="sxs-lookup"><span data-stu-id="5bdca-116">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="5bdca-117">조직 레코드 관리자 기능의 **특정 권한을 설정**하여 [올바른 액세스 권한을 보유](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-117">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="5bdca-118">해당 기능을 사용하면 조직의 보존 일정 및 요구 사항을 보존, 레코드 선언 및 처리를 관리하여 콘텐츠의 전체 라이프 사이클을 지원하는 레코드 관리 솔루션에 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-118">Using these capabilities, you can incorporate your organization's retention schedules and requirements into a records management solution that manages retention, records declaration, and disposition, to support the full lifecycle of your content.</span></span>

<span data-ttu-id="5bdca-119">온라인 설명서 외에도 레코드 관리를 위해 [웨비나 레코드](https://aka.ms/MIPC/Video-RecordsManagementWebinar)를 청취하고 [FAQ와 함께 제공되는 데크](https://aka.ms/MIPC/Blog-RecordsManagementWebinar)를 다운로드하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-119">In addition to the online documentation, you might find it useful to listen to the [webinar recording](https://aka.ms/MIPC/Video-RecordsManagementWebinar) for records management, and download the accompanying [deck with FAQs](https://aka.ms/MIPC/Blog-RecordsManagementWebinar).</span></span>

## <a name="records"></a><span data-ttu-id="5bdca-120">레코드</span><span class="sxs-lookup"><span data-stu-id="5bdca-120">Records</span></span>

<span data-ttu-id="5bdca-121">콘텐츠가 레코드로 표시되는 경우:</span><span class="sxs-lookup"><span data-stu-id="5bdca-121">When content is marked as a record:</span></span>

- <span data-ttu-id="5bdca-122">항목에는 [허용 또는 차단되는 작업](#compare-restrictions-for-what-actions-are-allowed-or-blocked)에 대한 제한 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-122">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="5bdca-123">항목에 대한 추가 활동이 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-123">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="5bdca-124">보존 기간 종료 시에 항목이 삭제되는 경우 처리 증명을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-124">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="5bdca-125">[보존 레이블](retention.md#retention-labels)을 사용하여 콘텐츠를 레코드로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-125">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="5bdca-126">사용자 및 관리자가 콘텐츠에 직접 적용할 수 있도록 해당 레이블을 게시하거나 레코드로 표시하기를 원하는 콘텐츠에 해당 레이블을 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-126">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="5bdca-127">보존 레이블을 사용하여 레코드를 콘텐츠로 표시하면 Microsoft 365 환경에서 일관된 단일 레코드 관리 전략을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-127">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

### <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="5bdca-128">허용 또는 차단되는 작업에 대한 제한 사항 비교</span><span class="sxs-lookup"><span data-stu-id="5bdca-128">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="5bdca-129">다음 표를 사용하여 표준 보존 레이블을 적용한 결과로 콘텐츠를 표시되는 제한 사항과 콘텐츠를 레코드로 표시하는 보존 레이블을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-129">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="5bdca-130">표준 보존 레이블에는 보존 설정 및 작업이 포함되나 콘텐츠를 레코드로 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-130">A standard retention label has retention settings and actions but doesn't mark content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="5bdca-131">자세한 내용을 제공하기 위해 표에는 SharePoint 및 OneDrive에는 적용되지만 Exchange에는 적용되지 않는 잠긴 레코드와 잠금이 해제된 레코드에 대한 열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-131">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="5bdca-132">레코드를 잠그거나 잠금 해제하는 기능은 Exchange 항목에서는 지원되지 않는 [레코드 버전 관리](record-versioning.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-132">The ability to lock and unlock a record uses [record versioning](record-versioning.md) that isn't supported for Exchange items.</span></span> <span data-ttu-id="5bdca-133">따라서 레코드로 표시되는 모든 Exchange 항목의 경우 해당 동작이 **레코드 - 잠금** 열에는 해당되지만 **레코드 - 잠금 해제됨** 열은 해당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-133">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="5bdca-134">작업</span><span class="sxs-lookup"><span data-stu-id="5bdca-134">Action</span></span>| <span data-ttu-id="5bdca-135">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="5bdca-135">Retention label</span></span> |<span data-ttu-id="5bdca-136">레코드 - 잠금</span><span class="sxs-lookup"><span data-stu-id="5bdca-136">Record - locked</span></span>| <span data-ttu-id="5bdca-137">레코드 - 잠금 해제됨</span><span class="sxs-lookup"><span data-stu-id="5bdca-137">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5bdca-138">콘텐츠 편집</span><span class="sxs-lookup"><span data-stu-id="5bdca-138">Edit contents</span></span>|<span data-ttu-id="5bdca-139">허용됨</span><span class="sxs-lookup"><span data-stu-id="5bdca-139">Allowed</span></span> | <span data-ttu-id="5bdca-140">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="5bdca-140">**Blocked**</span></span> | <span data-ttu-id="5bdca-141">허용됨</span><span class="sxs-lookup"><span data-stu-id="5bdca-141">Allowed</span></span>|
|<span data-ttu-id="5bdca-142">속성 편집(이름 바꾸기 포함)</span><span class="sxs-lookup"><span data-stu-id="5bdca-142">Edit properties, including rename</span></span>|<span data-ttu-id="5bdca-143">허용됨</span><span class="sxs-lookup"><span data-stu-id="5bdca-143">Allowed</span></span> |<span data-ttu-id="5bdca-144">허용됨</span><span class="sxs-lookup"><span data-stu-id="5bdca-144">Allowed</span></span> | <span data-ttu-id="5bdca-145">허용됨</span><span class="sxs-lookup"><span data-stu-id="5bdca-145">Allowed</span></span>|
|<span data-ttu-id="5bdca-146">삭제</span><span class="sxs-lookup"><span data-stu-id="5bdca-146">Delete</span></span>|<span data-ttu-id="5bdca-147">허용됨<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5bdca-147">Allowed <sup>1</sup></span></span> |<span data-ttu-id="5bdca-148">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="5bdca-148">**Blocked**</span></span> | <span data-ttu-id="5bdca-149">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="5bdca-149">**Blocked**</span></span>|
|<span data-ttu-id="5bdca-150">복사</span><span class="sxs-lookup"><span data-stu-id="5bdca-150">Copy</span></span>|<span data-ttu-id="5bdca-151">허용됨</span><span class="sxs-lookup"><span data-stu-id="5bdca-151">Allowed</span></span> |<span data-ttu-id="5bdca-152">허용됨</span><span class="sxs-lookup"><span data-stu-id="5bdca-152">Allowed</span></span> | <span data-ttu-id="5bdca-153">허용됨</span><span class="sxs-lookup"><span data-stu-id="5bdca-153">Allowed</span></span>|
|<span data-ttu-id="5bdca-154">컨테이너 내에서 이동<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="5bdca-154">Move within container <sup>2</sup></span></span>|<span data-ttu-id="5bdca-155">허용됨</span><span class="sxs-lookup"><span data-stu-id="5bdca-155">Allowed</span></span> |<span data-ttu-id="5bdca-156">허용됨</span><span class="sxs-lookup"><span data-stu-id="5bdca-156">Allowed</span></span> | <span data-ttu-id="5bdca-157">허용됨</span><span class="sxs-lookup"><span data-stu-id="5bdca-157">Allowed</span></span>|
|<span data-ttu-id="5bdca-158">컨테이너 간에 이동<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="5bdca-158">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="5bdca-159">허용됨</span><span class="sxs-lookup"><span data-stu-id="5bdca-159">Allowed</span></span> |<span data-ttu-id="5bdca-160">잠금이 해제되지 않은 경우 허용됨</span><span class="sxs-lookup"><span data-stu-id="5bdca-160">Allowed if never unlocked</span></span> | <span data-ttu-id="5bdca-161">허용됨</span><span class="sxs-lookup"><span data-stu-id="5bdca-161">Allowed</span></span>|
|<span data-ttu-id="5bdca-162">열기/읽기</span><span class="sxs-lookup"><span data-stu-id="5bdca-162">Open/Read</span></span>|<span data-ttu-id="5bdca-163">허용됨</span><span class="sxs-lookup"><span data-stu-id="5bdca-163">Allowed</span></span> |<span data-ttu-id="5bdca-164">허용됨</span><span class="sxs-lookup"><span data-stu-id="5bdca-164">Allowed</span></span> | <span data-ttu-id="5bdca-165">허용됨</span><span class="sxs-lookup"><span data-stu-id="5bdca-165">Allowed</span></span>|
|<span data-ttu-id="5bdca-166">레이블 변경</span><span class="sxs-lookup"><span data-stu-id="5bdca-166">Change label</span></span>|<span data-ttu-id="5bdca-167">허용됨</span><span class="sxs-lookup"><span data-stu-id="5bdca-167">Allowed</span></span> |<span data-ttu-id="5bdca-168">허용됨 - 컨테이너 관리자 전용</span><span class="sxs-lookup"><span data-stu-id="5bdca-168">Allowed - container admin only</span></span> | <span data-ttu-id="5bdca-169">허용됨 - 컨테이너 관리자 전용</span><span class="sxs-lookup"><span data-stu-id="5bdca-169">Allowed - container admin only</span></span>|
|<span data-ttu-id="5bdca-170">레이블 제거</span><span class="sxs-lookup"><span data-stu-id="5bdca-170">Remove label</span></span>|<span data-ttu-id="5bdca-171">허용됨</span><span class="sxs-lookup"><span data-stu-id="5bdca-171">Allowed</span></span> |<span data-ttu-id="5bdca-172">허용됨 - 컨테이너 관리자 전용</span><span class="sxs-lookup"><span data-stu-id="5bdca-172">Allowed - container admin only</span></span> | <span data-ttu-id="5bdca-173">허용됨 - 컨테이너 관리자 전용</span><span class="sxs-lookup"><span data-stu-id="5bdca-173">Allowed - container admin only</span></span>|

<span data-ttu-id="5bdca-174">각주:</span><span class="sxs-lookup"><span data-stu-id="5bdca-174">Footnotes:</span></span>

<span data-ttu-id="5bdca-175"><sup>1</sup> 복사본이 안전한 위치에 유지되지만 SharePoint에 의해 차단되므로 OneDrive 및 Exchange에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-175"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="5bdca-176">사용자가 SharePoint에서 레이블이 지정된 문서를 삭제하려고 할 때 표시되는 메시지:</span><span class="sxs-lookup"><span data-stu-id="5bdca-176">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![SharePoint에서 항목이 삭제되지 않았다는 메시지](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="5bdca-178"><sup>2</sup> 컨테이너에는 SharePoint 문서 라이브러리와 Exchange 사서함이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-178"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5bdca-179">다음 단계</span><span class="sxs-lookup"><span data-stu-id="5bdca-179">Next steps</span></span>

<span data-ttu-id="5bdca-180">[레코드 관리 시작](get-started-with-records-management.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5bdca-180">See [Get started with records management](get-started-with-records-management.md).</span></span>

<span data-ttu-id="5bdca-181">콘텐츠를 레코드로 표시하려면 [보존 레이블을 사용하여 레코드 삭제](declare-records.md)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="5bdca-181">To mark content as a record, see [Declare records by using retention labels](declare-records.md).</span></span>
