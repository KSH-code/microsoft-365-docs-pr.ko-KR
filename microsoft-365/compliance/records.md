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
description: 마이크로소프트 365에서 레코드 관리 솔루션을 구현하는 데 도움이 되는 레코드에 대해 알아봅니다.
ms.openlocfilehash: e64e91aeef307d05f23c47987a84baaf386324df
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685444"
---
# <a name="learn-about-records"></a><span data-ttu-id="fac3c-103">레코드에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="fac3c-103">Learn about records</span></span>

><span data-ttu-id="fac3c-104">*[보안 및 규정 준수에 대한 Microsoft 365 라이센스 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="fac3c-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="fac3c-105">Microsoft 365의 레코드 관리를 통해 조직은 회사 정책 및 법적 고지 사항 또는 규제 의무를 준수하는 동시에 위험과 법적 책임을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fac3c-105">Managing records in Microsoft 365 helps your organization comply with corporate policies and legal or regulatory obligations, while also reducing risk and legal liability.</span></span>

<span data-ttu-id="fac3c-106">콘텐츠가 레코드로 표시되는 경우:</span><span class="sxs-lookup"><span data-stu-id="fac3c-106">When content is marked as a record:</span></span>

- <span data-ttu-id="fac3c-107">항목에는 [허용 또는 차단되는 작업](#compare-restrictions-for-what-actions-are-allowed-or-blocked)에 대한 제한 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fac3c-107">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="fac3c-108">항목에 대한 추가 활동이 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="fac3c-108">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="fac3c-109">보존 기간 종료 시에 항목이 삭제되는 경우 처리 증명을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="fac3c-109">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="fac3c-110">[보존 레이블](retention.md#retention-labels)을 사용하여 콘텐츠를 레코드로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fac3c-110">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="fac3c-111">사용자 및 관리자가 콘텐츠에 직접 적용할 수 있도록 해당 레이블을 게시하거나 레코드로 표시하기를 원하는 콘텐츠에 해당 레이블을 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fac3c-111">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="fac3c-112">보존 레이블을 사용하여 레코드를 콘텐츠로 표시하면 Microsoft 365 환경에서 일관된 단일 레코드 관리 전략을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fac3c-112">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="fac3c-113">허용 또는 차단되는 작업에 대한 제한 사항 비교</span><span class="sxs-lookup"><span data-stu-id="fac3c-113">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="fac3c-114">다음 표를 사용하여 표준 보존 레이블을 적용한 결과로 콘텐츠를 표시되는 제한 사항과 콘텐츠를 레코드로 표시하는 보존 레이블을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fac3c-114">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="fac3c-115">표준 보존 레이블에는 콘텐츠를 레코드로 표시하지 않고 데이터를 보존하는 구성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fac3c-115">A standard retention label has the configuration to retain data without marking content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="fac3c-116">자세한 내용을 제공하기 위해 표에는 SharePoint 및 OneDrive에는 적용되지만 Exchange에는 적용되지 않는 잠긴 레코드와 잠금이 해제된 레코드에 대한 열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fac3c-116">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="fac3c-117">레코드를 잠그거나 잠금 해제하는 기능은 Exchange 항목에서는 지원되지 않는 [레코드 버전 관리](record-versioning.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fac3c-117">The ability to lock and unlock a record uses [record versioning](record-versioning.md) that isn't supported for Exchange items.</span></span> <span data-ttu-id="fac3c-118">따라서 레코드로 표시되는 모든 Exchange 항목의 경우 해당 동작이 **레코드 - 잠금** 열에는 해당되지만 **레코드 - 잠금 해제됨** 열은 해당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fac3c-118">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="fac3c-119">작업</span><span class="sxs-lookup"><span data-stu-id="fac3c-119">Action</span></span>| <span data-ttu-id="fac3c-120">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="fac3c-120">Retention label</span></span> |<span data-ttu-id="fac3c-121">레코드 - 잠금</span><span class="sxs-lookup"><span data-stu-id="fac3c-121">Record - locked</span></span>| <span data-ttu-id="fac3c-122">레코드 - 잠금 해제됨</span><span class="sxs-lookup"><span data-stu-id="fac3c-122">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fac3c-123">콘텐츠 편집</span><span class="sxs-lookup"><span data-stu-id="fac3c-123">Edit contents</span></span>|<span data-ttu-id="fac3c-124">허용됨</span><span class="sxs-lookup"><span data-stu-id="fac3c-124">Allowed</span></span> | <span data-ttu-id="fac3c-125">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="fac3c-125">**Blocked**</span></span> | <span data-ttu-id="fac3c-126">허용됨</span><span class="sxs-lookup"><span data-stu-id="fac3c-126">Allowed</span></span>|
|<span data-ttu-id="fac3c-127">속성 편집(이름 바꾸기 포함)</span><span class="sxs-lookup"><span data-stu-id="fac3c-127">Edit properties, including rename</span></span>|<span data-ttu-id="fac3c-128">허용됨</span><span class="sxs-lookup"><span data-stu-id="fac3c-128">Allowed</span></span> |<span data-ttu-id="fac3c-129">허용됨</span><span class="sxs-lookup"><span data-stu-id="fac3c-129">Allowed</span></span> | <span data-ttu-id="fac3c-130">허용됨</span><span class="sxs-lookup"><span data-stu-id="fac3c-130">Allowed</span></span>|
|<span data-ttu-id="fac3c-131">삭제</span><span class="sxs-lookup"><span data-stu-id="fac3c-131">Delete</span></span>|<span data-ttu-id="fac3c-132">허용됨<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fac3c-132">Allowed <sup>1</sup></span></span> |<span data-ttu-id="fac3c-133">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="fac3c-133">**Blocked**</span></span> | <span data-ttu-id="fac3c-134">**차단됨**</span><span class="sxs-lookup"><span data-stu-id="fac3c-134">**Blocked**</span></span>|
|<span data-ttu-id="fac3c-135">복사</span><span class="sxs-lookup"><span data-stu-id="fac3c-135">Copy</span></span>|<span data-ttu-id="fac3c-136">허용됨</span><span class="sxs-lookup"><span data-stu-id="fac3c-136">Allowed</span></span> |<span data-ttu-id="fac3c-137">허용됨</span><span class="sxs-lookup"><span data-stu-id="fac3c-137">Allowed</span></span> | <span data-ttu-id="fac3c-138">허용됨</span><span class="sxs-lookup"><span data-stu-id="fac3c-138">Allowed</span></span>|
|<span data-ttu-id="fac3c-139">컨테이너 내에서 이동<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="fac3c-139">Move within container <sup>2</sup></span></span>|<span data-ttu-id="fac3c-140">허용됨</span><span class="sxs-lookup"><span data-stu-id="fac3c-140">Allowed</span></span> |<span data-ttu-id="fac3c-141">허용됨</span><span class="sxs-lookup"><span data-stu-id="fac3c-141">Allowed</span></span> | <span data-ttu-id="fac3c-142">허용됨</span><span class="sxs-lookup"><span data-stu-id="fac3c-142">Allowed</span></span>|
|<span data-ttu-id="fac3c-143">컨테이너 간에 이동<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="fac3c-143">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="fac3c-144">허용됨</span><span class="sxs-lookup"><span data-stu-id="fac3c-144">Allowed</span></span> |<span data-ttu-id="fac3c-145">잠금이 해제되지 않은 경우 허용됨</span><span class="sxs-lookup"><span data-stu-id="fac3c-145">Allowed if never unlocked</span></span> | <span data-ttu-id="fac3c-146">허용됨</span><span class="sxs-lookup"><span data-stu-id="fac3c-146">Allowed</span></span>|
|<span data-ttu-id="fac3c-147">열기/읽기</span><span class="sxs-lookup"><span data-stu-id="fac3c-147">Open/Read</span></span>|<span data-ttu-id="fac3c-148">허용됨</span><span class="sxs-lookup"><span data-stu-id="fac3c-148">Allowed</span></span> |<span data-ttu-id="fac3c-149">허용됨</span><span class="sxs-lookup"><span data-stu-id="fac3c-149">Allowed</span></span> | <span data-ttu-id="fac3c-150">허용됨</span><span class="sxs-lookup"><span data-stu-id="fac3c-150">Allowed</span></span>|
|<span data-ttu-id="fac3c-151">레이블 변경</span><span class="sxs-lookup"><span data-stu-id="fac3c-151">Change label</span></span>|<span data-ttu-id="fac3c-152">허용됨</span><span class="sxs-lookup"><span data-stu-id="fac3c-152">Allowed</span></span> |<span data-ttu-id="fac3c-153">허용됨 - 컨테이너 관리자 전용</span><span class="sxs-lookup"><span data-stu-id="fac3c-153">Allowed - container admin only</span></span> | <span data-ttu-id="fac3c-154">허용됨 - 컨테이너 관리자 전용</span><span class="sxs-lookup"><span data-stu-id="fac3c-154">Allowed - container admin only</span></span>|
|<span data-ttu-id="fac3c-155">레이블 제거</span><span class="sxs-lookup"><span data-stu-id="fac3c-155">Remove label</span></span>|<span data-ttu-id="fac3c-156">허용됨</span><span class="sxs-lookup"><span data-stu-id="fac3c-156">Allowed</span></span> |<span data-ttu-id="fac3c-157">허용됨 - 컨테이너 관리자 전용</span><span class="sxs-lookup"><span data-stu-id="fac3c-157">Allowed - container admin only</span></span> | <span data-ttu-id="fac3c-158">허용됨 - 컨테이너 관리자 전용</span><span class="sxs-lookup"><span data-stu-id="fac3c-158">Allowed - container admin only</span></span>|

<span data-ttu-id="fac3c-159">각주:</span><span class="sxs-lookup"><span data-stu-id="fac3c-159">Footnotes:</span></span>

<span data-ttu-id="fac3c-160"><sup>1</sup> 복사본이 안전한 위치에 유지되지만 SharePoint에 의해 차단되므로 OneDrive 및 Exchange에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fac3c-160"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="fac3c-161">사용자가 SharePoint에서 레이블이 지정된 문서를 삭제하려고 할 때 표시되는 메시지:</span><span class="sxs-lookup"><span data-stu-id="fac3c-161">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![SharePoint에서 항목이 삭제되지 않았다는 메시지](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="fac3c-163"><sup>2</sup> 컨테이너에는 SharePoint 문서 라이브러리와 Exchange 사서함이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fac3c-163"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fac3c-164">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fac3c-164">Next steps</span></span>

<span data-ttu-id="fac3c-165">아직 레코드 관리에 사용할 보존 레이블이 아직 없는 경우 [보존 정책 및 보존 레이블 시작하기](get-started-with-retention.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fac3c-165">If you don't yet have retention labels to use for records management, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="fac3c-166">콘텐츠를 레코드로 표시하려면 [보존 레이블을 사용하여 레코드 삭제](declare-records.md)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="fac3c-166">To mark content as a record, see [Declare records by using retention labels](declare-records.md).</span></span>
