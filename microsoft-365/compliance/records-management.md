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
ms.collection:
- M365-security-compliance
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Microsoft 365의 레코드 관리를 사용하여 보존 일정을 파일 플랜에 적용하여 보존, 레코드 선언, 처리를 관리할 수 있습니다.
ms.openlocfilehash: 1af3ff5fac9a95afb15f680f8f46e8d0de0b4567
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226050"
---
# <a name="learn-about-records-management-in-microsoft-365"></a><span data-ttu-id="45cd8-103">Microsoft 365의 레코드 관리하기에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="45cd8-103">Learn about records management in Microsoft 365</span></span>

><span data-ttu-id="45cd8-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="45cd8-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="45cd8-p101">모든 유형의 조직에는 회사 데이터 전체의 규정, 법률 및 비즈니스에 중요한 레코드를 관리하기 위한 레코드 관리 솔루션이 필요합니다. Microsoft 365의 레코드 관리는 조직이 법적인 의무를 관리하는 데 도움이 되고, 규정 준수를 입증하는 기능을 제공하며, 비즈니스 목적에 대해 더 이상 보존할 필요가 없거나, 더 이상 가치가 없거나, 사용하지 않는 항목을 정기적으로 처리하여 효율성을 높입니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-p101">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data. Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="45cd8-107">Microsoft 365에서 다음 기능을 사용하여 레코드 관리 솔루션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-107">Use the following capabilities to support your records management solution in Microsoft 365:</span></span>

- <span data-ttu-id="45cd8-108">**콘텐츠를 레코드로 레이블**</span><span class="sxs-lookup"><span data-stu-id="45cd8-108">**Label content as a record**.</span></span> <span data-ttu-id="45cd8-109">콘텐츠를 사용자가 적용하거나 중요한 정보, 키워드 또는 콘텐츠 유형을 식별하여 자동으로 적용할 수 있는 [레코드](#records)로 표시하는 보존 레이블을 작성하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-109">Create and configure retention labels to mark content as a [record](#records) that can then be applied by users or automatically applied by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="45cd8-110">**파일 계획을 사용하여 보존 요구 사항을 마이그레이션하고 관리합니다**.</span><span class="sxs-lookup"><span data-stu-id="45cd8-110">**Migrate and manage your retention requirements with file plan**.</span></span> <span data-ttu-id="45cd8-111">[파일 계획](file-plan-manager.md)을 사용하여 기존 보존 계획을 Microsoft 365으로 가져오거나 개선된 관리 기능을 위해 새 계획을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-111">By using a [file plan](file-plan-manager.md), you can bring in an existing retention plan to Microsoft 365, or build a new one for enhanced management capabilities.</span></span>

- <span data-ttu-id="45cd8-112">**보존 레이블을 사용하여 보존 및 삭제 설정을 구성합니다.**</span><span class="sxs-lookup"><span data-stu-id="45cd8-112">**Configure retention and deletion settings with retention labels**.</span></span> <span data-ttu-id="45cd8-113">마지막으로 수정 또는 생성된 날짜를 포함하는 다양한 요소를 기반으로 보존 기간 및 작업을 사용하여 [보존 레이블](retention.md#retention-labels)을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-113">Configure [retention labels](retention.md#retention-labels) with the retention periods and actions based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="45cd8-114">[이벤트 기반 보존 **을 사용하여** 이벤트가 발생하는 경우 다른 보존 기간을 시작](event-driven-retention.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-114">**Start different retention periods when an event occurs** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="45cd8-115">[처리 검토](disposition.md#disposition-reviews) 및 [레코드 삭제](disposition.md#disposition-of-records) 검사를 통해 **처리를 검토하고 확인** 합니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-115">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="45cd8-116">[내보내기 옵션](disposition.md#filter-and-export-the-views)으로 **모든 처리된 항목에 대한 정보를 내보냅니다**.</span><span class="sxs-lookup"><span data-stu-id="45cd8-116">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="45cd8-117">조직 레코드 관리자 기능의 **특정 권한을 설정** 하여 [올바른 액세스 권한을 보유](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-117">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="45cd8-118">해당 기능을 사용하면 조직의 보존 일정 및 요구 사항을 보존, 레코드 선언 및 처리를 관리하여 콘텐츠의 전체 라이프 사이클을 지원하는 레코드 관리 솔루션에 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-118">Using these capabilities, you can incorporate your organization's retention schedules and requirements into a records management solution that manages retention, records declaration, and disposition, to support the full lifecycle of your content.</span></span>

<span data-ttu-id="45cd8-119">온라인 설명서 외에도 레코드 관리를 위해 [웨비나 레코드](https://aka.ms/MIPC/Video-RecordsManagementWebinar)를 청취하고 [FAQ와 함께 제공되는 데크](https://aka.ms/MIPC/Blog-RecordsManagementWebinar)를 다운로드하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-119">In addition to the online documentation, you might find it useful to listen to the [webinar recording](https://aka.ms/MIPC/Video-RecordsManagementWebinar) for records management, and download the accompanying [deck with FAQs](https://aka.ms/MIPC/Blog-RecordsManagementWebinar).</span></span>

## <a name="records"></a><span data-ttu-id="45cd8-120">레코드</span><span class="sxs-lookup"><span data-stu-id="45cd8-120">Records</span></span>

<span data-ttu-id="45cd8-121">콘텐츠가 레코드로 선언된 경우:</span><span class="sxs-lookup"><span data-stu-id="45cd8-121">When content is declared a record:</span></span>

- <span data-ttu-id="45cd8-122">항목에는 [허용 또는 차단되는 작업](#compare-restrictions-for-what-actions-are-allowed-or-blocked)에 대한 제한 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-122">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="45cd8-123">항목에 대한 추가 활동이 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-123">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="45cd8-124">보존 기간 종료 시에 항목이 삭제되는 경우 처리 증명을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-124">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="45cd8-125">[보존 레이블](retention.md#retention-labels)을 사용하여 콘텐츠를 **레코드** 혹은 **규제 레코드** 로 표시</span><span class="sxs-lookup"><span data-stu-id="45cd8-125">You use [retention labels](retention.md#retention-labels) to mark content as a **record**, or a **regulatory record**.</span></span> <span data-ttu-id="45cd8-126">이 두 개의 차이점은 다음 섹션에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-126">The difference between these two are explained in the next section.</span></span> <span data-ttu-id="45cd8-127">사용자 및 관리자가 콘텐츠에 직접 적용할 수 있도록 해당 레이블을 게시하거나 레코드 혹은 규제 레코드로 표시하기를 원하는 콘텐츠에 해당 레이블을 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-127">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record or a regulatory record.</span></span>

<span data-ttu-id="45cd8-128">보존 레이블을 사용하여 레코드를 선언하면 Microsoft 365 환경에서 일관된 단일 레코드 관리 전략을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-128">By using retention labels to declare records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

### <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="45cd8-129">허용 또는 차단되는 작업에 대한 제한 사항 비교</span><span class="sxs-lookup"><span data-stu-id="45cd8-129">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="45cd8-130">다음 표를 사용하여 표준 보존 레이블을 적용한 결과로 콘텐츠에 가해지는 제한 사항과 콘텐츠를 레코드 혹은 규제 레코드로 표시하는 보존 레이블에 가해지는 제한 사항을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-130">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record or regulatory record.</span></span>

<span data-ttu-id="45cd8-131">표준 보존 레이블에는 보존 설정 및 작업이 포함되나 콘텐츠를 레코드 혹은 규제 레코드로 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-131">A standard retention label has retention settings and actions but doesn't mark content as a record or a regulatory record.</span></span>

> [!NOTE]
> <span data-ttu-id="45cd8-132">자세한 내용을 제공하기 위해 표에는 SharePoint 및 OneDrive에는 적용되지만 Exchange에는 적용되지 않는 잠긴 레코드와 잠금이 해제된 레코드에 대한 열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-132">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="45cd8-133">레코드를 잠그거나 잠금 해제하는 기능은 Exchange 항목에서는 지원되지 않는 [레코드 버전 관리](record-versioning.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-133">The ability to lock and unlock a record uses [record versioning](record-versioning.md) that isn't supported for Exchange items.</span></span> <span data-ttu-id="45cd8-134">따라서 레코드로 표시되는 모든 Exchange 항목의 경우 해당 동작이 **레코드 - 잠금** 열에는 해당되지만 **레코드 - 잠금 해제됨** 열은 해당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-134">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="45cd8-135">작업</span><span class="sxs-lookup"><span data-stu-id="45cd8-135">Action</span></span>| <span data-ttu-id="45cd8-136">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="45cd8-136">Retention label</span></span> |<span data-ttu-id="45cd8-137">레코드 - 잠금</span><span class="sxs-lookup"><span data-stu-id="45cd8-137">Record - locked</span></span>| <span data-ttu-id="45cd8-138">레코드 - 잠금 해제됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-138">Record - unlocked</span></span>| <span data-ttu-id="45cd8-139">규제 레코드</span><span class="sxs-lookup"><span data-stu-id="45cd8-139">Regulatory record</span></span> |
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="45cd8-140">콘텐츠 편집</span><span class="sxs-lookup"><span data-stu-id="45cd8-140">Edit contents</span></span>|<span data-ttu-id="45cd8-141">허용됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-141">Allowed</span></span> | <span data-ttu-id="45cd8-142">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="45cd8-142">**Blocked**</span></span> | <span data-ttu-id="45cd8-143">허용됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-143">Allowed</span></span> | <span data-ttu-id="45cd8-144">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="45cd8-144">**Blocked**</span></span>|
|<span data-ttu-id="45cd8-145">속성 편집(이름 바꾸기 포함)</span><span class="sxs-lookup"><span data-stu-id="45cd8-145">Edit properties, including rename</span></span>|<span data-ttu-id="45cd8-146">허용됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-146">Allowed</span></span> |<span data-ttu-id="45cd8-147">허용됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-147">Allowed</span></span> | <span data-ttu-id="45cd8-148">허용됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-148">Allowed</span></span>| <span data-ttu-id="45cd8-149">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="45cd8-149">**Blocked**</span></span>|
|<span data-ttu-id="45cd8-150">삭제</span><span class="sxs-lookup"><span data-stu-id="45cd8-150">Delete</span></span>|<span data-ttu-id="45cd8-151">허용됨<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="45cd8-151">Allowed <sup>1</sup></span></span> |<span data-ttu-id="45cd8-152">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="45cd8-152">**Blocked**</span></span> |<span data-ttu-id="45cd8-153">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="45cd8-153">**Blocked**</span></span>| <span data-ttu-id="45cd8-154">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="45cd8-154">**Blocked**</span></span>|
|<span data-ttu-id="45cd8-155">복사</span><span class="sxs-lookup"><span data-stu-id="45cd8-155">Copy</span></span>|<span data-ttu-id="45cd8-156">허용됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-156">Allowed</span></span> |<span data-ttu-id="45cd8-157">허용됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-157">Allowed</span></span> | <span data-ttu-id="45cd8-158">허용됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-158">Allowed</span></span>| <span data-ttu-id="45cd8-159">허용됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-159">Allowed</span></span>|
|<span data-ttu-id="45cd8-160">컨테이너 내에서 이동<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="45cd8-160">Move within container <sup>2</sup></span></span>|<span data-ttu-id="45cd8-161">허용됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-161">Allowed</span></span> |<span data-ttu-id="45cd8-162">허용됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-162">Allowed</span></span> | <span data-ttu-id="45cd8-163">허용됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-163">Allowed</span></span>| <span data-ttu-id="45cd8-164">허용됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-164">Allowed</span></span>|
|<span data-ttu-id="45cd8-165">컨테이너 간에 이동<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="45cd8-165">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="45cd8-166">허용됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-166">Allowed</span></span> |<span data-ttu-id="45cd8-167">잠금이 해제되지 않은 경우 허용됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-167">Allowed if never unlocked</span></span> | <span data-ttu-id="45cd8-168">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="45cd8-168">**Blocked**</span></span> | <span data-ttu-id="45cd8-169">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="45cd8-169">**Blocked**</span></span>|
|<span data-ttu-id="45cd8-170">열기/읽기</span><span class="sxs-lookup"><span data-stu-id="45cd8-170">Open/Read</span></span>|<span data-ttu-id="45cd8-171">허용됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-171">Allowed</span></span> |<span data-ttu-id="45cd8-172">허용됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-172">Allowed</span></span> | <span data-ttu-id="45cd8-173">허용됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-173">Allowed</span></span>| <span data-ttu-id="45cd8-174">허용됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-174">Allowed</span></span>|
|<span data-ttu-id="45cd8-175">레이블 변경</span><span class="sxs-lookup"><span data-stu-id="45cd8-175">Change label</span></span>|<span data-ttu-id="45cd8-176">허용됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-176">Allowed</span></span> |<span data-ttu-id="45cd8-177">허용됨 - 컨테이너 관리자 전용</span><span class="sxs-lookup"><span data-stu-id="45cd8-177">Allowed - container admin only</span></span> | <span data-ttu-id="45cd8-178">허용됨 - 컨테이너 관리자 전용</span><span class="sxs-lookup"><span data-stu-id="45cd8-178">Allowed - container admin only</span></span>| <span data-ttu-id="45cd8-179">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="45cd8-179">**Blocked**</span></span>
|<span data-ttu-id="45cd8-180">레이블 제거</span><span class="sxs-lookup"><span data-stu-id="45cd8-180">Remove label</span></span>|<span data-ttu-id="45cd8-181">허용됨</span><span class="sxs-lookup"><span data-stu-id="45cd8-181">Allowed</span></span> |<span data-ttu-id="45cd8-182">허용됨 - 컨테이너 관리자 전용</span><span class="sxs-lookup"><span data-stu-id="45cd8-182">Allowed - container admin only</span></span> | <span data-ttu-id="45cd8-183">허용됨 - 컨테이너 관리자 전용</span><span class="sxs-lookup"><span data-stu-id="45cd8-183">Allowed - container admin only</span></span>| <span data-ttu-id="45cd8-184">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="45cd8-184">**Blocked**</span></span>

<span data-ttu-id="45cd8-185">각주:</span><span class="sxs-lookup"><span data-stu-id="45cd8-185">Footnotes:</span></span>

<span data-ttu-id="45cd8-186"><sup>1</sup> 복사본이 안전한 위치에 유지되지만 SharePoint에 의해 차단되므로 OneDrive 및 Exchange에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-186"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="45cd8-187">문서 첨부 파일이 있는 목록 항목에 보존 레이블을 적용하면 해당 문서는 보존 설정을 상속하지 않으므로 목록 항목에서 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-187">When you apply a retention label to a list item that has a document attachment, that document doesn't inherit the retention settings and can be deleted from the list item.</span></span> <span data-ttu-id="45cd8-188">이와 비교하여 해당 목록 항목이 보존 레이블과 함께 레코드로 선언된 경우, 문서 첨부파일은 보존 설정을 상속하므로 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-188">In comparison, if that list item was declared a record with a retention label, the document attachment would inherit the retention settings and couldn't be deleted.</span></span>

<span data-ttu-id="45cd8-189"><sup>2</sup> 컨테이너에는 SharePoint 문서 라이브러리, OneDrive계정과 Exchange 사서함이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-189"><sup>2</sup> Containers include SharePoint document libraries, OneDrive accounts, and Exchange mailboxes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="45cd8-190">규제 기록에서 가장 중요한 차이는 콘텐츠에 적용한 후에는 이를 아무도, 심지어 전역 관리자도 레이블을 제거할 수 없다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-190">The most important difference for a regulatory record is that after it is applied to content, nobody, not even a global administrator, can remove the label.</span></span>
>
> <span data-ttu-id="45cd8-191">규정 레코드에 대해 구성된 보존 레이블에는 다음과 같은 관리자 제한 사항도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-191">Retention labels configured for regulatory records also have the following admin restrictions:</span></span>
>
> - <span data-ttu-id="45cd8-192">레이블을 저장한 후 보존 기간을 단축 하는 작업은 할 수 없고 확장만 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-192">The retention period can't be made shorter after the label is saved, only extended.</span></span>
> - <span data-ttu-id="45cd8-193">이러한 레이블은 자동 레이블 지정 정책에서 지원되지 않으며 [보존 레이블 정책](create-apply-retention-labels.md)을 사용하여 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-193">These labels aren't supported by auto-labeling policies, and must be applied by using [retention label policies](create-apply-retention-labels.md).</span></span>
>
> <span data-ttu-id="45cd8-194">또한 SharePoint에서 체크 아웃된 문서에는 규정 레이블을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-194">In addition, a regulatory label can't be applied to a document that's checked out in SharePoint.</span></span>
>
> <span data-ttu-id="45cd8-195">이러한 제한 사항 및 취소할 수 없는 작업으로 인해 보존 레이블에 대해 이 옵션을 선택하기 전에 반드시 규정 레코드를 사용해야 하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-195">Because of the restrictions and irreversible actions, make sure you really do need to use regulatory records before you select this option for your retention labels.</span></span> <span data-ttu-id="45cd8-196">실수로 인한 구성을 방지하기 위해 이 옵션은 기본적으로 사용할 수 없지만 먼저 PowerShell을 사용하여 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-196">To help prevent accidental configuration, this option is not available by default but must first be enabled by using PowerShell.</span></span> <span data-ttu-id="45cd8-197">[보존 레이블을 사용하여 레코드를 선언](declare-records.md)에 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-197">Instructions are included in [Declare records by using retention labels](declare-records.md).</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="45cd8-198">구성 지침</span><span class="sxs-lookup"><span data-stu-id="45cd8-198">Configuration guidance</span></span>

<span data-ttu-id="45cd8-199">[레코드 관리 시작](get-started-with-records-management.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45cd8-199">See [Get started with records management](get-started-with-records-management.md).</span></span> <span data-ttu-id="45cd8-200">이 문서에는 레코드 관리 시나리오에 대한 구독, 사용 권한 및 종단 내 구성 지침에 대한 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45cd8-200">This article has information about subscriptions, permissions, and links to end-to-end configuration guidance for records management scenarios.</span></span>