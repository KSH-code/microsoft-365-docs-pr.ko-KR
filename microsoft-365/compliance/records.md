---
title: 레코드에 대해 알아보기
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
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Microsoft 365에서 레코드 관리 솔루션을 구현하는 데 도움이 되는 레코드에 대해 알아봅니다.
ms.openlocfilehash: 6cdf29493a3fd95b060c52d9f9587ee34748edde
ms.sourcegitcommit: a53af7a228bb1f58cb8128a69a19da49f9e28700
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "45372523"
---
# <a name="learn-about-records"></a><span data-ttu-id="9b0f2-103">레코드에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="9b0f2-103">Learn about records</span></span>

><span data-ttu-id="9b0f2-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="9b0f2-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="9b0f2-105">Microsoft 365의 레코드 관리를 통해 조직은 회사 정책 및 법적 고지 사항 또는 규제 의무를 준수하는 동시에 위험과 법적 책임을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-105">Managing records in Microsoft 365 helps your organization comply with corporate policies and legal or regulatory obligations, while also reducing risk and legal liability.</span></span>

<span data-ttu-id="9b0f2-106">콘텐츠가 레코드로 표시되는 경우:</span><span class="sxs-lookup"><span data-stu-id="9b0f2-106">When content is marked as a record:</span></span>

- <span data-ttu-id="9b0f2-107">항목에는 [허용 또는 차단되는 작업](#compare-restrictions-for-what-actions-are-allowed-or-blocked)에 대한 제한 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-107">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="9b0f2-108">항목에 대한 추가 활동이 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-108">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="9b0f2-109">보존 기간 종료 시에 항목이 삭제되는 경우 처리 증명을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-109">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="9b0f2-110">[보존 레이블](retention.md#retention-labels)을 사용하여 콘텐츠를 레코드로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-110">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="9b0f2-111">사용자 및 관리자가 콘텐츠에 직접 적용할 수 있도록 해당 레이블을 게시하거나 레코드로 표시하기를 원하는 콘텐츠에 해당 레이블을 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-111">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="9b0f2-112">보존 레이블을 사용하여 레코드를 콘텐츠로 표시하면 Microsoft 365 환경에서 일관된 단일 레코드 관리 전략을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-112">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="9b0f2-113">허용 또는 차단되는 작업에 대한 제한 사항 비교</span><span class="sxs-lookup"><span data-stu-id="9b0f2-113">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="9b0f2-114">다음 표를 사용하여 표준 보존 레이블을 적용한 결과로 콘텐츠를 표시되는 제한 사항과 콘텐츠를 레코드로 표시하는 보존 레이블을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-114">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="9b0f2-115">표준 보존 레이블에는 콘텐츠를 레코드로 표시하지 않고 데이터를 보존하는 구성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-115">A standard retention label has the configuration to retain data without marking content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="9b0f2-116">자세한 내용을 제공하기 위해 표에는 SharePoint 및 OneDrive에는 적용되지만 Exchange에는 적용되지 않는 잠긴 레코드와 잠금이 해제된 레코드에 대한 열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-116">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="9b0f2-117">레코드를 잠그거나 잠금 해제하는 기능은 Exchange 항목에서는 지원되지 않는 [레코드 버전 관리](#record-versioning)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-117">The ability to lock and unlock a record uses [record versioning](#record-versioning) that isn't supported for Exchange items.</span></span> <span data-ttu-id="9b0f2-118">따라서 레코드로 표시되는 모든 Exchange 항목의 경우 해당 동작이 **레코드 - 잠금** 열에는 해당되지만 **레코드 - 잠금 해제됨** 열은 해당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-118">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="9b0f2-119">작업</span><span class="sxs-lookup"><span data-stu-id="9b0f2-119">Action</span></span>| <span data-ttu-id="9b0f2-120">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="9b0f2-120">Retention label</span></span> |<span data-ttu-id="9b0f2-121">레코드 - 잠금</span><span class="sxs-lookup"><span data-stu-id="9b0f2-121">Record - locked</span></span>| <span data-ttu-id="9b0f2-122">레코드 - 잠금 해제됨</span><span class="sxs-lookup"><span data-stu-id="9b0f2-122">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9b0f2-123">콘텐츠 편집</span><span class="sxs-lookup"><span data-stu-id="9b0f2-123">Edit contents</span></span>|<span data-ttu-id="9b0f2-124">허용됨</span><span class="sxs-lookup"><span data-stu-id="9b0f2-124">Allowed</span></span> | <span data-ttu-id="9b0f2-125">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="9b0f2-125">**Blocked**</span></span> | <span data-ttu-id="9b0f2-126">허용됨</span><span class="sxs-lookup"><span data-stu-id="9b0f2-126">Allowed</span></span>|
|<span data-ttu-id="9b0f2-127">속성 편집(이름 바꾸기 포함)</span><span class="sxs-lookup"><span data-stu-id="9b0f2-127">Edit properties, including rename</span></span>|<span data-ttu-id="9b0f2-128">허용됨</span><span class="sxs-lookup"><span data-stu-id="9b0f2-128">Allowed</span></span> |<span data-ttu-id="9b0f2-129">허용됨</span><span class="sxs-lookup"><span data-stu-id="9b0f2-129">Allowed</span></span> | <span data-ttu-id="9b0f2-130">허용됨</span><span class="sxs-lookup"><span data-stu-id="9b0f2-130">Allowed</span></span>|
|<span data-ttu-id="9b0f2-131">삭제</span><span class="sxs-lookup"><span data-stu-id="9b0f2-131">Delete</span></span>|<span data-ttu-id="9b0f2-132">허용됨<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9b0f2-132">Allowed <sup>1</sup></span></span> |<span data-ttu-id="9b0f2-133">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="9b0f2-133">**Blocked**</span></span> | <span data-ttu-id="9b0f2-134">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="9b0f2-134">**Blocked**</span></span>|
|<span data-ttu-id="9b0f2-135">복사</span><span class="sxs-lookup"><span data-stu-id="9b0f2-135">Copy</span></span>|<span data-ttu-id="9b0f2-136">허용됨</span><span class="sxs-lookup"><span data-stu-id="9b0f2-136">Allowed</span></span> |<span data-ttu-id="9b0f2-137">허용됨</span><span class="sxs-lookup"><span data-stu-id="9b0f2-137">Allowed</span></span> | <span data-ttu-id="9b0f2-138">허용됨</span><span class="sxs-lookup"><span data-stu-id="9b0f2-138">Allowed</span></span>|
|<span data-ttu-id="9b0f2-139">컨테이너 내에서 이동<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9b0f2-139">Move within container <sup>2</sup></span></span>|<span data-ttu-id="9b0f2-140">허용됨</span><span class="sxs-lookup"><span data-stu-id="9b0f2-140">Allowed</span></span> |<span data-ttu-id="9b0f2-141">허용됨</span><span class="sxs-lookup"><span data-stu-id="9b0f2-141">Allowed</span></span> | <span data-ttu-id="9b0f2-142">허용됨</span><span class="sxs-lookup"><span data-stu-id="9b0f2-142">Allowed</span></span>|
|<span data-ttu-id="9b0f2-143">컨테이너 간에 이동<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9b0f2-143">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="9b0f2-144">허용됨</span><span class="sxs-lookup"><span data-stu-id="9b0f2-144">Allowed</span></span> |<span data-ttu-id="9b0f2-145">잠금이 해제되지 않은 경우 허용됨</span><span class="sxs-lookup"><span data-stu-id="9b0f2-145">Allowed if never unlocked</span></span> | <span data-ttu-id="9b0f2-146">허용됨</span><span class="sxs-lookup"><span data-stu-id="9b0f2-146">Allowed</span></span>|
|<span data-ttu-id="9b0f2-147">열기/읽기</span><span class="sxs-lookup"><span data-stu-id="9b0f2-147">Open/Read</span></span>|<span data-ttu-id="9b0f2-148">허용됨</span><span class="sxs-lookup"><span data-stu-id="9b0f2-148">Allowed</span></span> |<span data-ttu-id="9b0f2-149">허용됨</span><span class="sxs-lookup"><span data-stu-id="9b0f2-149">Allowed</span></span> | <span data-ttu-id="9b0f2-150">허용됨</span><span class="sxs-lookup"><span data-stu-id="9b0f2-150">Allowed</span></span>|
|<span data-ttu-id="9b0f2-151">레이블 변경</span><span class="sxs-lookup"><span data-stu-id="9b0f2-151">Change label</span></span>|<span data-ttu-id="9b0f2-152">허용됨</span><span class="sxs-lookup"><span data-stu-id="9b0f2-152">Allowed</span></span> |<span data-ttu-id="9b0f2-153">허용됨 - 컨테이너 관리자 전용</span><span class="sxs-lookup"><span data-stu-id="9b0f2-153">Allowed - container admin only</span></span> | <span data-ttu-id="9b0f2-154">허용됨 - 컨테이너 관리자 전용</span><span class="sxs-lookup"><span data-stu-id="9b0f2-154">Allowed - container admin only</span></span>|
|<span data-ttu-id="9b0f2-155">레이블 제거</span><span class="sxs-lookup"><span data-stu-id="9b0f2-155">Remove label</span></span>|<span data-ttu-id="9b0f2-156">허용됨</span><span class="sxs-lookup"><span data-stu-id="9b0f2-156">Allowed</span></span> |<span data-ttu-id="9b0f2-157">허용됨 - 컨테이너 관리자 전용</span><span class="sxs-lookup"><span data-stu-id="9b0f2-157">Allowed - container admin only</span></span> | <span data-ttu-id="9b0f2-158">허용됨 - 컨테이너 관리자 전용</span><span class="sxs-lookup"><span data-stu-id="9b0f2-158">Allowed - container admin only</span></span>|

<span data-ttu-id="9b0f2-159">각주:</span><span class="sxs-lookup"><span data-stu-id="9b0f2-159">Footnotes:</span></span>

<span data-ttu-id="9b0f2-160"><sup>1</sup> 복사본이 안전한 위치에 유지되지만 SharePoint에 의해 차단되므로 OneDrive 및 Exchange에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-160"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="9b0f2-161">사용자가 SharePoint에서 레이블이 지정된 문서를 삭제하려고 할 때 표시되는 메시지:</span><span class="sxs-lookup"><span data-stu-id="9b0f2-161">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![SharePoint에서 항목이 삭제되지 않았다는 메시지](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="9b0f2-163"><sup>2</sup> 컨테이너에는 SharePoint 문서 라이브러리와 Exchange 사서함이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-163"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>


## <a name="using-retention-labels-to-declare-records"></a><span data-ttu-id="9b0f2-164">보존 레이블을 사용하여 레코드 선언</span><span class="sxs-lookup"><span data-stu-id="9b0f2-164">Using retention labels to declare records</span></span>

<span data-ttu-id="9b0f2-165">보존 레이블을 만들 때 보존 레이블을 사용하여 콘텐츠를 레코드로 표시하는 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-165">When you create a retention label, you have the option to use the retention label to mark the content as a record:</span></span>

1. <span data-ttu-id="9b0f2-166">Microsoft 365 준수 센터에서 **레코드 관리** \> **파일 계획**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-166">In the Microsoft 365 compliance center, go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="9b0f2-167">**파일 계획** 페이지에서 **레이블 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-167">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="9b0f2-168">마법사의 **레이블 설정** 페이지에서 콘텐츠를 레코드로 분류하는 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-168">On the **Label settings** page in the wizard, choose the option to classify content as a record.</span></span>
    
   ![레이블을 사용하여 콘텐츠를 레코드로 분류 확인란을 클릭합니다.](../media/recordversioning6.png)

3. <span data-ttu-id="9b0f2-170">필요에 따라 SharePoint 또는 OneDrive 문서와 Exchange 전자 메일에 보존 레이블을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-170">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="9b0f2-171">해당 지침은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-171">For instructions:</span></span>
    
    - [<span data-ttu-id="9b0f2-172">보존 레이블을 만들고 앱에 적용하기</span><span class="sxs-lookup"><span data-stu-id="9b0f2-172">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="9b0f2-173">보존 레이블을 콘텐츠에 자동으로 적용하기</span><span class="sxs-lookup"><span data-stu-id="9b0f2-173">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

### <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="9b0f2-174">콘텐츠에 구성된 보존 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="9b0f2-174">Applying the configured retention label to content</span></span>

<span data-ttu-id="9b0f2-175">콘텐츠를 레코드로 표시하는 보존 레이블을 사용자가 앱에 적용할 수 있도록 설정한 경우:</span><span class="sxs-lookup"><span data-stu-id="9b0f2-175">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="9b0f2-176">Exchange의 경우 사서함에 대한 쓰기 권한이 있는 사용자는 이러한 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-176">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="9b0f2-177">SharePoint 및 OneDrive의 경우 기본 구성원 그룹에 있는 모든 사용자(참가 권한 수준)는 이러한 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-177">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="9b0f2-178">보존 레이블을 사용하여 레코드로 표시된 문서 예제:</span><span class="sxs-lookup"><span data-stu-id="9b0f2-178">Example of a document marked as record by using a retention label:</span></span>

![레코드로 태그가 지정된 문서에 대한 세부 정보 창](../media/recordversioning7.png)

## <a name="record-versioning"></a><span data-ttu-id="9b0f2-180">레코드 버전 관리</span><span class="sxs-lookup"><span data-stu-id="9b0f2-180">Record versioning</span></span>

<span data-ttu-id="9b0f2-181">문서를 레코드로 표시하고 레코드에 대해 수행할 수 있는 작업을 제한하는 기능은 모든 레코드 관리 솔루션의 필수 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-181">The ability to mark a document as a record and restrict actions that can be performed on the record is an essential goal for any records management solution.</span></span> <span data-ttu-id="9b0f2-182">그러나 후속 버전을 만들어야 하는 경우 공동으로 작업할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-182">However, collaboration might also be needed for people to create subsequent versions.</span></span>

<span data-ttu-id="9b0f2-183">예를 들어 영업 계약을 레코드로 표시한 경우 새 사용 약관으로 계약을 업데이트하고 최신 버전을 새 레코드로 표시해야 합니다. 반면 이전 버전의 레코드는 계속 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-183">For example, you might mark a sales contract as a record, but then need to update the contract with new terms and mark the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="9b0f2-184">해당 유형의 시나리오에서는 SharePoint 및 OneDrive가 *레코드 버전 관리*를 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-184">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="9b0f2-185">OneNote 전자 필기장 폴더는 레코드 버전 관리를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-185">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="9b0f2-186">레코드 버전 관리를 사용하려면 먼저 문서에 레이블을 지정하고 레코드로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-186">To use record versioning, first label the document and mark it as a record.</span></span> <span data-ttu-id="9b0f2-187">이때 *레코드 상태*라고 하는 문서 속성이 보존 레이블 옆에 표시되고 초기 레코드 상태는 **잠금 상태**가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-187">At this point, a document property, called *Record status* is displayed next to the retention label, and the initial record status is **Locked**.</span></span> 

<span data-ttu-id="9b0f2-188">이제 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-188">You can now do the following things:</span></span>

  - <span data-ttu-id="9b0f2-189">**레코드 상태 속성을 잠금 및 잠금 해제하여 문서의 개별 버전을 레코드로 계속 편집하고 유지할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="9b0f2-189">**Continually edit and retain individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="9b0f2-190">**레코드 상태** 속성이 **잠금**으로 설정된 경우에만 해당 레코드의 새 버전이 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-190">Only when the **Record status** property is set to **Locked** is a new version of the record retained.</span></span> <span data-ttu-id="9b0f2-191">이와 같이 잠금 및 잠금 해제를 전환하면 문서의 불필요한 버전 및 복사본이 보존될 위험을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-191">This toggle of locked and unlocked reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="9b0f2-192">**레코드를 사이트 모음에 있는 현재 위치 레코드 리포지토리에 자동으로 저장합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b0f2-192">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="9b0f2-193">SharePoint 및 OneDrive의 각 사이트 모음은 자료 보존 라이브러리의 콘텐츠를 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-193">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="9b0f2-194">레코드 버전은 이 라이브러리의 레코드 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-194">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="9b0f2-195">**모든 버전을 포함하는 에버그린 문서를 유지합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b0f2-195">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="9b0f2-196">기본적으로 각 SharePoint 및 OneDrive 문서는 항목 메뉴에서 사용할 수 있는 버전 기록을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-196">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="9b0f2-197">이 버전 기록에서 사용자는 어떤 버전이 레코드인지 쉽게 알 수 있고 그러한 문서들을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-197">In this version history, you can easily see which versions are records and view those documents.</span></span>

<span data-ttu-id="9b0f2-198">레코드 버전 관리는 레코드로 항목을 표시하는 보존 레이블이 있는 모든 문서에 대해 자동으로 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-198">Record versioning is automatically available for any document that has a retention label that marks the item as a record.</span></span> <span data-ttu-id="9b0f2-199">사용자가 세부 정보 창을 통해 문서 속성을 확인하는 경우 문서 속성의 **레코드 상태**를 **잠금 상태**에서 **잠금 해제 상태**로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-199">When a user views the document properties by using the details pane, they can toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="9b0f2-200">이 작업으로 자료 보존 라이브러리의 보존 폴더에서 레코드를 만들고 레코드는 보존 기간의 나머지 기간 동안 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-200">This action creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> 

<span data-ttu-id="9b0f2-201">문서가 잠금 해제되는 동안 표준 편집 권한이 있는 모든 사용자는 파일을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-201">While the document is unlocked, any user with standard edit permissions can edit the file.</span></span> <span data-ttu-id="9b0f2-202">그러나 사용자는 파일을 삭제할 수 없습니다. 여전히 레코드이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-202">However, users can't delete the file, because it's still a record.</span></span> <span data-ttu-id="9b0f2-203">편집이 완료되면 **레코드 상태**를 **잠금 해제**에서 **잠금**으로 전환하여 이 상태에서 추가로 편집이 진행되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-203">When editing is complete, a  user can then toggle the **Record status** from **Unlocked** to **Locked**, which prevents further edits while in this status.</span></span>
<br/><br/>

![레코드로 태그가 지정된 문서의 레코드 상태 속성](../media/recordversioning8.png)

### <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="9b0f2-205">레코드 잠금 및 잠금 해제</span><span class="sxs-lookup"><span data-stu-id="9b0f2-205">Locking and unlocking a record</span></span>

<span data-ttu-id="9b0f2-206">콘텐츠를 레코드로 표시하는 보존 레이블을 문서에 적용한 후 참가 권한 또는 더 적은 권한 수준을 사용하는 모든 사용자가 레코드를 잠금 해제하거나 잠금 해제된 레코드를 잠글 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-206">After a retention label that marks content as a record is applied to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![레코드 문서가 잠금 해제됨을 표시하는 레코드 상태](../media/recordversioning9.png)

<span data-ttu-id="9b0f2-208">사용자가 레코드를 잠금 해제하면 다음 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-208">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="9b0f2-209">현재 사이트 모음에 자료 보존 라이브러리가 없는 경우에는 하나만 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-209">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="9b0f2-210">자료 보존 라이브러리에 레코드 폴더가 없는 경우에는 하나만 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-210">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="9b0f2-211">**복사** 작업은 문서의 최신 버전을 레코드 폴더로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-211">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="9b0f2-212">**복사** 작업은 최신 버전만 포함하고 이전 버전은 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-212">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="9b0f2-213">이 복사된 문서는 이제 문서의 레코드 버전으로 간주되며 해당 파일 이름은 다음 형식으로 되어 있습니다. \[제목 GUID 버전\#\]</span><span class="sxs-lookup"><span data-stu-id="9b0f2-213">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="9b0f2-214">레코드 폴더에 만들어진 복사본은 원본 문서의 버전 기록에 추가되고 이 버전은 설명 필드에 **레코드**로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-214">The copy created in the Records folder is added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="9b0f2-215">원본 문서는 편집할 수는 있지만 삭제할 수 없는 새 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-215">The original document is a new version that can be edited, but not deleted.</span></span> <span data-ttu-id="9b0f2-216">문서가 현재 편집될 수 있더라도 여전히 레코드이므로 문서 라이브러리의 **레코드 항목임**열에서는 **예** 값으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-216">The document library column **Item is a Record** still shows the **Yes** value because the document is still a record, even if it can now be edited.</span></span>

<span data-ttu-id="9b0f2-217">사용자가 레코드를 잠그면 원본 문서는 다시 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-217">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="9b0f2-218">그러나 이는 자료 보존 라이브러리의 레코드 폴더에 버전을 복사하는 레코드를 잠금 해제하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-218">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

### <a name="record-versions"></a><span data-ttu-id="9b0f2-219">레코드 버전</span><span class="sxs-lookup"><span data-stu-id="9b0f2-219">Record versions</span></span>

<span data-ttu-id="9b0f2-220">사용자가 레코드의 잠금을 해제할 때마다 최신 버전은 자료 보존 라이브러리의 레코드 폴더에 복사되고 해당 버전에는 버전 기록의 **설명** 필드에 **레코드** 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-220">Each time a user unlocks a record, the latest version is copied to the Records folder in the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![자료 보존 라이브러리에 표시된 레코드](../media/recordversioning10.png)

<span data-ttu-id="9b0f2-222">버전 기록을 보려면 문서 라이브러리에서 문서를 선택하고 항목 메뉴에서 **버전 기록**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-222">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

### <a name="where-records-are-stored"></a><span data-ttu-id="9b0f2-223">레코드 저장 위치</span><span class="sxs-lookup"><span data-stu-id="9b0f2-223">Where records are stored</span></span>

<span data-ttu-id="9b0f2-224">레코드는 사이트 모음의 최상위 사이트에 있는 자료 보존 라이브러리의 레코드 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-224">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="9b0f2-225">최상위 사이트의 왼쪽 탐색 창에서 **사이트 콘텐츠** \> **자료 보존 라이브러리**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-225">In the left navigation on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![자료 보존 라이브러리](../media/recordversioning11.png)

<br/><br/>

![자료 보존 라이브러리의 레코드 폴더](../media/recordversioning12.png)

<span data-ttu-id="9b0f2-228">자료 보존 라이브러리는 사이트 모음 관리자에게만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-228">The Preservation Hold library is visible only to site collection admins.</span></span> <span data-ttu-id="9b0f2-229">또한 자료 보존 라이브러리는 기본적으로 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-229">Also, the Preservation Hold library doesn't exist by default.</span></span> <span data-ttu-id="9b0f2-230">이는 보존 레이블이나 보존 정책에 해당하는 콘텐츠가 사이트 모음에서 처음 삭제된 경우에만 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-230">It's created only when content subject to a retention label or retention policy is deleted for the first time in the site collection.</span></span>

### <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="9b0f2-231">기록 버전 관리 이벤트에 대한 감사 로그 검색</span><span class="sxs-lookup"><span data-stu-id="9b0f2-231">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="9b0f2-232">레코드 잠금 및 잠금 해제 작업이 감사 로그에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-232">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="9b0f2-233">사용자는 특정 작업인 **레코드 상태가 잠김으로 변경** 및 **레코드 상태가 잠김 상태로 변경**을 검색할 수 있습니다. 이 작업은 보안 및 준수 센터의 **감사 로그 검색** 페이지에 있는 **활동** 드롭다운 목록의 **파일 및 페이지 활동** 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-233">You can search for the specific activities **Changed record status to locked** and **Changed record status to unlocked**, which are located in the **File and page activities** section in the **Activities** dropdown list on the **Audit log search** page in the security and compliance center.</span></span>
<br/><br/>

![기록 버전 관리 이벤트에 대한 감사 로그 검색](../media/recordversioning13.png)

<span data-ttu-id="9b0f2-235">이러한 이벤트를 검색하는 방법에 대한 자세한 내용은 [보안 & 준수 센터에서 감사 로그를 검색](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities)의 "파일 및 페이지 활동" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-235">For more information about searching for these events, see the "File and page activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9b0f2-236">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9b0f2-236">Next steps</span></span>

<span data-ttu-id="9b0f2-237">아직 레코드 관리에 사용할 보존 레이블이 아직 없는 경우 [보존 정책 및 보존 레이블 시작하기](get-started-with-retention.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-237">If you don't yet have retention labels to use for records management, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="9b0f2-238">레코드 처리에 대한 자세한 내용은 [콘텐츠 삭제](disposition.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b0f2-238">To learn about disposition of records, see [Disposing of content](disposition.md).</span></span>
