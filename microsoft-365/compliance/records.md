---
title: 레코드 개요
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
description: Office 365 또는 Microsoft 조직에서 레코드 관리 전략을 구현하려면 콘텐츠를 레코드로 선언하는 보존 레이블을 사용합니다. 그런 다음 보존 레코드 레이블을 게시하거나 자동으로 적용합니다.
ms.openlocfilehash: 87bed90f4c9bf27eb960a2018b6a641ff3e06993
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081704"
---
# <a name="overview-of-records"></a><span data-ttu-id="c3de0-104">레코드 개요</span><span class="sxs-lookup"><span data-stu-id="c3de0-104">Overview of records</span></span>

<span data-ttu-id="c3de0-105">Microsoft 365에서 레코드 관리를 사용하면 조직은 회사 정책, 법적 고지 사항 및 규제 의무를 준수하는 동시에 위험과 법적 책임을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-105">Managing records in Microsoft 365 helps an organization comply with their corporate policies, legal and regulatory obligations while reducing risk and legal liability.</span></span>

<span data-ttu-id="c3de0-106">높은 수준에서 콘텐츠를 레코드로 선언하는 것은 다음과 같은 의미를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-106">At a high level, declaring content as a record means that:</span></span>

- <span data-ttu-id="c3de0-107">항목이 변경할 수 없게 됩니다(레코드를 수정하거나 삭제할 수 없음).</span><span class="sxs-lookup"><span data-stu-id="c3de0-107">The item becomes immutable (a record can't be modified or deleted)</span></span>

- <span data-ttu-id="c3de0-108">항목에 대한 추가 활동이 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-108">Additional activities about the item are logged</span></span>

- <span data-ttu-id="c3de0-109">레코드는 명시된 보존 기간이 지나면 폐기됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-109">Records are disposed of after their stated retention period is past</span></span>

<span data-ttu-id="c3de0-110">[보존 레이블](labels.md)을 사용하여 콘텐츠를 레코드로 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-110">You can use [retention labels](labels.md) to classify content as a record.</span></span> <span data-ttu-id="c3de0-111">레코드를 선언하는 보존 레이블을 만든 후 사용자가 콘텐츠를 레코드로 분류하는 데 사용할 수 있도록 해당 레이블을 [게시](labels.md#how-retention-labels-work-with-retention-label-policies)하거나 사용자가 레코드로 분류하기 원하는 콘텐츠에 [해당 레이블을 자동 적용](labels.md#applying-a-retention-label-automatically-based-on-conditions)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-111">After you create retention labels that declare records, you can either [publish](labels.md#how-retention-labels-work-with-retention-label-policies) those labels (so that users can use them to classify content as records) or [auto-apply those labels](labels.md#applying-a-retention-label-automatically-based-on-conditions) to content that you want to classify as a record.</span></span> <span data-ttu-id="c3de0-112">사용자는 레코드를 선언하기 위한 보존 레이블을 사용하여 Office 365에서 일관된 단일 레코드 관리 전략을 구현할 수 있지만 레코드 센터와 같은 다른 레코드 관리 기능은 SharePoint Online의 콘텐츠에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-112">By using retention labels to declare records, you can implement a single, consistent records-management strategy across all of Office 365, whereas other records-management features such as the Record Center apply only to content in SharePoint Online.</span></span>

<span data-ttu-id="c3de0-113">레코드에 대해 다음의 사항에 유의하십시오.</span><span class="sxs-lookup"><span data-stu-id="c3de0-113">Keep the following things in mind about records:</span></span>

  - <span data-ttu-id="c3de0-114">**레코드는 변경할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="c3de0-114">**Records are immutable.**</span></span> <span data-ttu-id="c3de0-115">콘텐츠를 레코드로 선언하는 보존 레이블은 SharePoint 및 비즈니스용 OneDrive 뿐만 아니라 Exchange의 콘텐츠에 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-115">A retention label that declares content as a record can be applied to content in Exchange, in addition to SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="c3de0-116">그러나 [레코드 버전 관리](#record-versioning)는 Exchange가 아닌 SharePoint 및 OneDrive에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-116">However, [record versioning](#record-versioning) is available only in SharePoint and OneDrive, and not for Exchange.</span></span>

    <span data-ttu-id="c3de0-117">Exchange에서 레코드로 레이블이 지정된 콘텐츠는 최종 삭제될 때까지 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-117">In Exchange, content labeled as a record is immutable until its final deletion.</span></span> <span data-ttu-id="c3de0-118">Exchange 항목에 레코드로 레이블이 지정되면 다음 네 가지 사항이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-118">When an Exchange item is labeled as a record, four things happen:</span></span>

    - <span data-ttu-id="c3de0-119">항목을 영구적으로 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-119">The item can't be permanently deleted.</span></span>

    - <span data-ttu-id="c3de0-120">항목을 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-120">The item can't be edited.</span></span>

    - <span data-ttu-id="c3de0-121">레이블을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-121">The label can't be changed.</span></span>

    - <span data-ttu-id="c3de0-122">레이블을 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-122">The label can't be removed.</span></span>

  - <span data-ttu-id="c3de0-123">**레코드 및 폴더**</span><span class="sxs-lookup"><span data-stu-id="c3de0-123">**Records and folders.**</span></span> <span data-ttu-id="c3de0-124">Exchange, SharePoint 및 OneDrive의 폴더에 보존 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-124">You can apply a retention label to a folder in Exchange, SharePoint, and OneDrive.</span></span> <span data-ttu-id="c3de0-125">폴더가 레코드로 레이블이 지정되고 항목을 해당 폴더로 이동하면 항목이 레코드로 레이블이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-125">If a folder is labeled as a record, and you move an item into the folder, the item is labeled as a record.</span></span> <span data-ttu-id="c3de0-126">항목을 폴더 밖으로 이동시켜도 항목은 계속 레코드로 레이블이 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-126">When you move the item out of the folder, the item remains labeled as a record.</span></span>

    <span data-ttu-id="c3de0-127">또한 폴더 (SharePoint 및 OneDrive)에 적용되는 레코드 레이블을 콘텐츠를 레코드로 선언하지 않는 보존 레이블로 변경하면 해당 폴더의 항목에는 기존 레코드 레이블이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-127">Also, if you change the record label that's applied to a folder (in SharePoint and OneDrive) to a retention label that does not declare content as a record, then items in the folder keep their existing  record label.</span></span>

    <span data-ttu-id="c3de0-128">SharePoint 및 OneDrive 폴더에 보존 레이블을 적용하는 방법에 대한 자세한 내용은 [ SharePoint 라이브러리, 폴더 또는 문서 집합의 모든 콘텐츠에 기본 보존 레이블 적용](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3de0-128">For more information about applying retention labels to SharePoint and OneDrive folders, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>

  - <span data-ttu-id="c3de0-129">**레코드는 삭제될 수 없습니다**.</span><span class="sxs-lookup"><span data-stu-id="c3de0-129">**Records can't be deleted**.</span></span> <span data-ttu-id="c3de0-130">사용자가 Exchange에서 기록을 삭제하려고 하면 [보존 정책이 원본 위치의 콘텐츠에 작동하는 방식](retention-policies.md#content-in-mailboxes-and-public-folders)에 설명된 것처럼 항목이 복구 가능한 항목 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-130">If a user attempts to delete a record in Exchange, the item is moved to the Recoverable Items folder as described in [How a retention policy works with content in place](retention-policies.md#content-in-mailboxes-and-public-folders).</span></span>

    <span data-ttu-id="c3de0-131">SharePoint에서 레코드를 삭제하려고 하면 항목이 삭제되지 않았다는 오류 메시지가 표시되고 항목은 라이브러리에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-131">If a user attempts to delete a record in a SharePoint, an error is displayed say that the item wasn't deleted, and remains in the library.</span></span>

    ![SharePoint에서 항목이 삭제되지 않았다는 메시지](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)

    <span data-ttu-id="c3de0-133">OneDrive에서 레코드를 삭제하려고 하면 [보존 정책이 원본 위치의 콘텐츠에 작동하는 방식](retention-policies.md#content-in-onedrive-accounts-and-sharepoint-sites)에 설명된 것처럼 항목이 자료 보존 라이브러리로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-133">If a user attempts to delete a record in OneDrive, the item is moved to the Preservation Hold library as described in [How a retention policy works with content in place](retention-policies.md#content-in-onedrive-accounts-and-sharepoint-sites).</span></span>

  - <span data-ttu-id="c3de0-134">**레코드 레이블은 제거할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="c3de0-134">**Records labels can't be removed.**</span></span> <span data-ttu-id="c3de0-135">레코드 레이블이 항목에 적용되면 해당 위치의 관리자만(예: SharePoint 사이트의 사이트 모음 관리자) 해당 레코드 레이블을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-135">Once a record label has been applied to an item, only the admin of that location (for example, a site collection admin of a SharePoint site) can remove that record label.</span></span>

## <a name="using-retention-labels-to-declare-records"></a><span data-ttu-id="c3de0-136">보존 레이블을 사용하여 레코드 선언</span><span class="sxs-lookup"><span data-stu-id="c3de0-136">Using retention labels to declare records</span></span>

<span data-ttu-id="c3de0-137">보존 레이블을 만들 때 보존 레이블을 사용하여 콘텐츠를 레코드로 분류하는 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-137">When you create a retention label, you have the option to use the retention label to classify the content as a record.</span></span> <span data-ttu-id="c3de0-138">콘텐츠를 레코드로 선언하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-138">To declare content as a record, you need to do the following:</span></span>

1. <span data-ttu-id="c3de0-139">보존 레이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-139">Create a retention label.</span></span> <span data-ttu-id="c3de0-140">Microsoft 365 준수 센터에서 **레코드 관리** \> **파일 계획**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-140">In the Microsoft 365 compliance center, go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="c3de0-141">**파일 계획** 페이지에서 **레이블 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-141">On the **File plan** page, click  **Create a label**.</span></span>

2. <span data-ttu-id="c3de0-142">마법사의 **레이블 설정** 페이지에서 콘텐츠를 레코드로 선언하는 보존 레이블 설정 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-142">On the **Label settings** page in the wizard, choose the option to set the retention label to declare content as a record.</span></span><br/>

   ![레이블을 사용하여 콘텐츠를 레코드로 분류 확인란을 클릭합니다.](../media/recordversioning6.png)

3. <span data-ttu-id="c3de0-144">SharePoint 사이트 및/또는 OneDrive 계정에 대한 보존 레이블을 [게시](labels.md#how-retention-labels-work-with-retention-label-policies)하거나 [자동 적용](labels.md#applying-a-retention-label-automatically-based-on-conditions)합니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-144">[Publish](labels.md#how-retention-labels-work-with-retention-label-policies) or [auto-apply](labels.md#applying-a-retention-label-automatically-based-on-conditions) the retention label to SharePoint sites and/or OneDrive accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="c3de0-145">[보존 레이블](labels.md)를 사용하여 항목을 레코드로 선언하는 경우에는 이 위치에서 콘텐츠를 편집할 수 있는 권한이 있는 각 사용자에 대해 Office 365 Enterprise E5 라이선스 또는 동등한 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-145">Declaring an item as a record using [retention labels](labels.md) requires an Office 365 Enterprise E5 license or equivalent for each user who has permissions to edit content in this location.</span></span> <span data-ttu-id="c3de0-146">읽기 전용 권한이 있는 사용자는 라이선스가 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-146">Users who have read-only access don't require a license.</span></span>


### <a name="applying-a-retention-label-to-content"></a><span data-ttu-id="c3de0-147">콘텐츠에 보존 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="c3de0-147">Applying a retention label to content</span></span>

<span data-ttu-id="c3de0-148">Exchange의 경우 사서함에 대한 쓰기 권한이 있는 사용자는 전자 메일 메시지에 레코드 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-148">For Exchange, any user with write-access to the mailbox can apply a record label to an email message.</span></span> <span data-ttu-id="c3de0-149">SharePoint 및 OneDrive 콘텐츠의 경우 기본 구성원 그룹에 있는 모든 사용자(참가 권한 수준)는 콘텐츠에 레코드 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-149">For content in SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply a record label to content.</span></span> <span data-ttu-id="c3de0-150">레코드 레이블이 적용된 후에 사이트 모음 관리자만 해당 레코드 레이블을 제거하거나 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-150">Only a site collection admin can remove or change that record label after it's been applied.</span></span> <span data-ttu-id="c3de0-151">앞서 설명한 것처럼 콘텐츠를 레코드로 분류하는 보존 레이블을 콘텐츠에 자동 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-151">As previously explained, a retention label that classifies content as a record can be auto-applied to content.</span></span>

<span data-ttu-id="c3de0-152">SharePoint 사이트 또는 OneDrive 계정에서 문서에 레코드 레이블이 적용되는 경우의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-152">Here's what this looks like when a record label is applied to a document on a SharePoint site or OneDrive account.</span></span>
<br/><br/>

![레코드로 태그가 지정된 문서에 대한 세부 정보 창](../media/recordversioning7.png)

## <a name="record-versioning"></a><span data-ttu-id="c3de0-154">레코드 버전 관리</span><span class="sxs-lookup"><span data-stu-id="c3de0-154">Record versioning</span></span>

<span data-ttu-id="c3de0-155">레코드 관리의 중요한 역할은 문서를 레코드로 선언하여 해당 레코드를 변경할 수 없도록 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-155">An essential part of records management is the ability to declare a document as a record and have that record be immutable.</span></span> <span data-ttu-id="c3de0-156">이와 동시에 레코드의 불변성은 사용자가 이후 버전을 만들어야 하는 경우 문서에서 공동 작업을 할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-156">At the same time, record immutability prevents collaboration on the document if people need to create subsequent versions.</span></span> <span data-ttu-id="c3de0-157">예를 들어 영업 계약을 레코드로 선언한 경우 새 사용 약관으로 계약을 업데이트하고 최신 버전을 새 레코드로 선언해야 합니다. 반면 이전 버전의 레코드는 계속 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-157">For example, you might declare a sales contract as a record, but then need to update the contract with new terms and declare the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="c3de0-158">이러한 유형의 시나리오에서는 SharePoint Online 및 비즈니스용 OneDrive가 현재 *레코드 버전 관리*를 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-158">For these types of scenarios, SharePoint Online and OneDrive for Business now support *record versioning*.</span></span> <span data-ttu-id="c3de0-159">OneNote 전자 필기장 폴더는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-159">OneNote notebook folders are not supported.</span></span>

<span data-ttu-id="c3de0-160">레코드 버전 관리를 사용하려면 첫 번째 단계로 Microsoft 365 준수 센터를 사용하여 모든 SharePoint 사이트 및/또는 OneDrive 계정에 레코드를 선언하는 보존 레이블을 만들어 게시하거나 특정 SharePoint 사이트 및/또는 OneDrive 계정에 보존 레이블을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-160">To use record versioning, the first step is to use the Microsoft 365 compliance center to create and publish retention labels that declare records to all SharePoint sites and/or OneDrive accounts, or publish them to specific SharePoint sites and/or OneDrive accounts.</span></span> <span data-ttu-id="c3de0-161">다음 단계는 게시된 보존 레코드 레이블을 문서에 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-161">The next step is to apply a published retention record label to a document.</span></span> <span data-ttu-id="c3de0-162">이 작업이 완료되면 *레코드 상태*라고 하는 문서 속성이 보존 레이블 옆에 표시되고 초기 레코드 상태는 **잠금 상태**가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-162">When this is done, a document property, called *Record status* is displayed next to the retention label, and the initial record status will be **Locked**.</span></span> <span data-ttu-id="c3de0-163">이때 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-163">At this point, you can do the following things:</span></span>

  - <span data-ttu-id="c3de0-164">**레코드 상태 속성을 잠금 및 잠금 해제하여 문서의 개별 버전을 레코드로 계속 편집하고 선언할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="c3de0-164">**Continually edit and declare individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="c3de0-165">**레코드 상태** 속성이 **잠금 상태**로 설정된 경우 레코드로 선언된 버전만 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-165">Only the versions declared as records are retained when the **Record status** property is set to **Locked**.</span></span> <span data-ttu-id="c3de0-166">따라서 문서의 불필요한 버전 및 복사본을 보존하는 위험을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-166">This reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="c3de0-167">**레코드를 사이트 모음에 있는 현재 위치 레코드 리포지토리에 자동으로 저장합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3de0-167">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="c3de0-168">SharePoint 및 OneDrive의 각 사이트 모음은 자료 보존 라이브러리의 콘텐츠를 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-168">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="c3de0-169">레코드 버전은 이 라이브러리의 레코드 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-169">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="c3de0-170">**모든 버전을 포함하는 에버그린 문서를 유지합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3de0-170">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="c3de0-171">기본적으로 각 SharePoint 및 OneDrive 문서는 항목 메뉴에서 사용할 수 있는 버전 기록을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-171">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="c3de0-172">이 버전 기록에서 사용자는 어떤 버전이 레코드인지 쉽게 알 수 있고 그러한 문서들을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-172">In this version history, you can easily see which versions are records and view those documents.</span></span>

<span data-ttu-id="c3de0-173">레코드 버전 관리는 레코드로 항목을 선언하는 보존 레이블이 있는 모든 문서에 대해 자동으로 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-173">Record versioning is automatically available for any document that has a retention label that declares the item as a record.</span></span> <span data-ttu-id="c3de0-174">사용자가 세부 정보 창을 통해 문서 속성을 확인하는 경우 문서 속성의 **레코드 상태**가 **잠금 상태**에서 **잠금 해제 상태**로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-174">When a user views the document properties through the details pane, they toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="c3de0-175">한 번 클릭으로 자료 보존 라이브러리의 보존 폴더에서 레코드를 만들고 레코드는 보존 기간의 나머지 기간 동안 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-175">This single click creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> <span data-ttu-id="c3de0-176">문서가 잠금 해제되는 동안 사용 권한이 있는 모든 사용자는 파일을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-176">While the document is unlocked, any user with permissions can edit the file.</span></span> <span data-ttu-id="c3de0-177">그러나 사용자는 파일을 삭제할 수 없습니다. 이는 선언된 레코드로 간주되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-177">However, users can't delete the file, because it's considered a declared record.</span></span> <span data-ttu-id="c3de0-178">필요한 변경 내용이 적용된 후 사용자는 **레코드 상태**를 **잠금 해제 상태**에서 **잠금 상태**로 전환하여 문서를 다시 레코드로 선언하고 편집할 수 없도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-178">After the necessary changes are made, the user can then toggle the **Record status** from **Unlocked** to **Locked**, so that the document is again declared a record and can't be edited.</span></span>
<br/><br/>

![레코드로 태그가 지정된 문서의 레코드 상태 속성](../media/recordversioning8.png)

> [!NOTE]
> <span data-ttu-id="c3de0-180">레코드 버전 관리를 사용하려면 SharePoint 사이트 또는 OneDrive 계정에서 레코드로 선언된 콘텐츠를 편집할 수 있는 권한이 있는 각 사용자에 대해 Office 365 Enterprise E5 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-180">Record versioning requires an Office 365 Enterprise E5 license for each user who has permissions to edit content that's been declared a record in a SharePoint site or OneDrive account.</span></span> <span data-ttu-id="c3de0-181">읽기 전용 권한이 있는 사용자는 이 라이선스가 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-181">Users who have read-only access don't require this license.</span></span>

### <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="c3de0-182">레코드 잠금 및 잠금 해제</span><span class="sxs-lookup"><span data-stu-id="c3de0-182">Locking and unlocking a record</span></span>

<span data-ttu-id="c3de0-183">문서에 레코드 레이블을 할당한 후 기본 구성원 그룹에 있는 모든 사용자(참가 권한 수준)는 레코드를 잠금 해제하거나 잠금 해제된 레코드를 잠글 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-183">After a record label is assigned to a document, any user in the default Members group (the Contribute permission level) can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![레코드 문서가 잠금 해제됨을 표시하는 레코드 상태](../media/recordversioning9.png)

<span data-ttu-id="c3de0-185">사용자가 레코드를 잠금 해제하면 다음 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-185">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="c3de0-186">현재 사이트 모음에 자료 보존 라이브러리가 없는 경우에는 하나만 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-186">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="c3de0-187">자료 보존 라이브러리에 레코드 폴더가 없는 경우에는 하나만 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-187">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="c3de0-188">**복사** 작업은 문서의 최신 버전을 레코드 폴더로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-188">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="c3de0-189">**복사** 작업은 최신 버전만 포함하고 이전 버전은 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-189">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="c3de0-190">이 복사된 문서는 이제 문서의 레코드 버전으로 간주되며 해당 파일 이름은 다음 형식으로 되어 있습니다. \[제목 GUID 버전\#\]</span><span class="sxs-lookup"><span data-stu-id="c3de0-190">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="c3de0-191">레코드 폴더에 만들어진 복사본은 원본 문서의 버전 기록에 추가되고 이 버전은 설명 필드에 **레코드**로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-191">The copy created in the Records folder added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="c3de0-192">원본 문서는 편집할 수는 있지만 삭제할 수 없는 새 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-192">The original document is a new version that can be edited (but not deleted).</span></span> <span data-ttu-id="c3de0-193">문서가 현재 편집될 수 있더라도 여전히 레코드로 고려되기 때문에 문서 라이브러리의 **레코드 항목임**열에서는 **예** 값으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-193">The document library column **Item is a Record** still shows the **Yes** value because the document is still considered a record, even if it can now be edited.</span></span>

<span data-ttu-id="c3de0-194">사용자가 레코드를 잠그면 원본 문서는 다시 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-194">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="c3de0-195">그러나 이는 자료 보존 라이브러리의 레코드 폴더에 버전을 복사하는 레코드를 잠금 해제하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-195">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

### <a name="record-versions"></a><span data-ttu-id="c3de0-196">레코드 버전</span><span class="sxs-lookup"><span data-stu-id="c3de0-196">Record versions</span></span>

<span data-ttu-id="c3de0-197">사용자가 레코드의 잠금을 해제할 때마다 최신 버전은 자료 보존 라이브러리의 레코드 폴더에 복사되고 해당 버전에는 버전 기록의 **설명** 필드에 **레코드** 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-197">Each time a user unlocks a record, the latest version is copied to the Records folder in the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![자료 보존 라이브러리에 표시된 레코드](../media/recordversioning10.png)

<span data-ttu-id="c3de0-199">버전 기록을 보려면 문서 라이브러리에서 문서를 선택하고 항목 메뉴에서 **버전 기록**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-199">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

### <a name="where-records-are-stored"></a><span data-ttu-id="c3de0-200">레코드 저장 위치</span><span class="sxs-lookup"><span data-stu-id="c3de0-200">Where records are stored</span></span>

<span data-ttu-id="c3de0-201">레코드는 사이트 모음의 최상위 사이트에 있는 자료 보존 라이브러리의 레코드 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-201">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="c3de0-202">최상위 사이트의 왼쪽 탐색 창에서 **사이트 콘텐츠** \> **자료 보존 라이브러리**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-202">In the left nav on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![자료 보존 라이브러리](../media/recordversioning11.png)

<br/><br/>

![자료 보존 라이브러리의 레코드 폴더](../media/recordversioning12.png)

<span data-ttu-id="c3de0-205">자료 보존 라이브러리는 사이트 모음 관리자에게만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-205">The Preservation Hold library is visible only to site collection admins.</span></span> <span data-ttu-id="c3de0-206">또한 자료 보존 라이브러리는 기본적으로 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-206">Also, the Preservation Hold library doesn't exist by default.</span></span> <span data-ttu-id="c3de0-207">이는 보존 레이블이나 보존 정책에 해당하는 콘텐츠가 사이트 모음에서 처음 삭제된 경우에만 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-207">It's created only when content subject to a retention label or retention policy is deleted for the first time in the site collection.</span></span>

### <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="c3de0-208">기록 버전 관리 이벤트에 대한 감사 로그 검색</span><span class="sxs-lookup"><span data-stu-id="c3de0-208">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="c3de0-209">레코드 잠금 및 잠금 해제 작업이 Office 365 감사 로그에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-209">The actions of locking and unlocking records are logged in the Office 365 audit log.</span></span> <span data-ttu-id="c3de0-210">사용자는 특정 작업인 **레코드 상태가 잠김으로 변경** 및 **레코드 상태가 잠김 상태로 변경**을 검색할 수 있습니다. 이 작업은 보안 및 준수 센터의 **감사 로그 검색** 페이지에 있는 **활동** 드롭다운 목록의 **파일 및 페이지 활동** 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3de0-210">You can search for the specific activities **Changed record status to locked** and **Changed record status to unlocked**, which are located in the **File and page activities** section in the **Activities** dropdown list on the **Audit log search** page in the security and compliance center.</span></span>
<br/><br/>

![기록 버전 관리 이벤트에 대한 감사 로그 검색](../media/recordversioning13.png)

<span data-ttu-id="c3de0-212">이러한 이벤트를 검색하는 방법에 대한 자세한 내용은 [보안 & 준수 센터에서 감사 로그를 검색](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities)의 "파일 및 페이지 활동" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3de0-212">For more information about searching for these events, see the "File and page activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>
