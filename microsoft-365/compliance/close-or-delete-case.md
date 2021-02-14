---
title: 사례 닫기 또는 삭제
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery 사례에서 지원되는 조사 또는 법적 사례가 닫히거나 삭제될 때 발생하는 일에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ffdd93351325be0c4b5d6d8cdfb78e55b710c0be
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419064"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="8323b-103">Advanced eDiscovery 사례 닫기 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="8323b-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="8323b-104">Advanced eDiscovery 사례에서 지원되는 법적 사례 또는 조사가 완료되면 사례를 닫거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="8323b-105">닫힌 사례를 다시 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="8323b-106">사례 닫기</span><span class="sxs-lookup"><span data-stu-id="8323b-106">Close a case</span></span>

<span data-ttu-id="8323b-107">Advanced eDiscovery 사례를 닫을 때 발생하는 문제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="8323b-108">사례에 보류된 콘텐츠 위치가 포함되어 있는 경우 해당 보류가 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="8323b-109">보류가 해제된 후 30일의 유예 기간(지연 보류)이 보류된 콘텐츠 위치에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="8323b-110">이렇게 하면 콘텐츠가 즉시 삭제되는 것을 방지하고 관리자는 지연 보류 기간이 만료된 후 영구적으로 삭제되는 콘텐츠를 검색하거나 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="8323b-111">자세한 내용은 [eDiscovery](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)보류에서 콘텐츠 위치 제거를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8323b-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="8323b-112">사례를 닫을 경우 해당 사례와 연결된 보류만 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="8323b-113">다른 보류가 콘텐츠 위치에 있는 경우(예: 소송 보유, Core eDiscovery 보류 또는 다른 Advanced eDiscovery 사례의 보류) 해당 보류는 계속 유지 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="8323b-114">사례는 Microsoft 365 규정 준수 센터의 eDiscovery 페이지에 계속 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="8323b-115">마감된 사례의 세부 정보, 보류, 검색 및 구성원은 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="8323b-116">사례를 닫은 후 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="8323b-117">예를 들어 고급 eDiscovery에서 구성원을 추가 또는 제거하고, 검색을 만들고, 검색 결과를 내보내고, 분석을 위해 검색 결과를 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="8323b-118">활성 사례와 닫힌 사례의 주요 차이점은 사례가 닫히면 보류가 해제되어 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="8323b-119">사례를 닫는 경우:</span><span class="sxs-lookup"><span data-stu-id="8323b-119">To close a case:</span></span>

1. <span data-ttu-id="8323b-120">Advanced **eDiscovery** 페이지에서 닫을 사례를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="8323b-121">설정 **탭의** **대소문자 정보에서** 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8323b-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="8323b-122">닫기 **사례를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8323b-122">Click **Close case**.</span></span>

   <span data-ttu-id="8323b-123">닫는 프로세스가 완료될 때 최대 60분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-123">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="8323b-124">닫힌 사례 다시 열기</span><span class="sxs-lookup"><span data-stu-id="8323b-124">Reopen a closed case</span></span>

<span data-ttu-id="8323b-125">Advanced eDiscovery 사례를 다시 열면 사례가 닫혀 있을 때 수행된 보류가 자동으로 다시 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-125">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="8323b-126">사례가 다시 열리면 보류 탭으로 이동하여  이전 보류를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-126">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="8323b-127">보류를 켜고 플라이아웃 페이지를 표시하려면 해당 페이지를  선택한 다음 상태 토글을 **켜기로 설정하십시오.**</span><span class="sxs-lookup"><span data-stu-id="8323b-127">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="8323b-128">닫힌 사례를 다시 열기 위해</span><span class="sxs-lookup"><span data-stu-id="8323b-128">To reopen a closed case:</span></span>

1. <span data-ttu-id="8323b-129">Advanced **eDiscovery** 페이지에서 다시 열 사례를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-129">On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id="8323b-130">설정 **탭의** **대소문자 정보에서** 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8323b-130">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="8323b-131">다시 **열기 사례를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8323b-131">Click **Reopen case**.</span></span>

   <span data-ttu-id="8323b-132">다시 열기 프로세스를 완료하는 데 최대 60분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-132">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="8323b-133">사례 삭제</span><span class="sxs-lookup"><span data-stu-id="8323b-133">Delete a case</span></span>

<span data-ttu-id="8323b-134">활성 및 닫힌 Advanced eDiscovery 사례를 모두 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-134">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="8323b-135">사례를 삭제하면 정보주 목록, 커뮤니케이션, 검색, 검토 집합 및 내보내기 작업과 같은 사례와 관련된 모든 구성 요소가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-135">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="8323b-136">사례는 Microsoft 365 규정 준수 센터의 **Advanced eDiscovery** 페이지에 있는 사례 목록에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-136">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="8323b-137">삭제된 사례는 복구하거나 다시 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-137">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="8323b-138">데이터 유출 시나리오에서 검토 집합의 항목을 제거하는 유일한 방법은 Advanced eDiscovery 사례를 삭제하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-138">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="8323b-139">다른 "검색 및 삭제" 메서드는 검토 집합에서 항목을 제거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-139">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="8323b-140">사례를 삭제하려면 먼저 사례와 연결된 모든 보류를  삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-140">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="8323b-141">여기에는 해제 상태의 보류 삭제가 **포함됩니다.**</span><span class="sxs-lookup"><span data-stu-id="8323b-141">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="8323b-142">사례와 연결된 보류를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="8323b-142">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="8323b-143">삭제할 **Advanced** eDiscovery 사례의 보류 탭으로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="8323b-143">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="8323b-144">삭제할 보류를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-144">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="8323b-145">플라이아웃 페이지에서 보류 **삭제를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8323b-145">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="8323b-146">사례를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="8323b-146">To delete a case:</span></span>

1. <span data-ttu-id="8323b-147">Advanced **eDiscovery** 페이지에서 삭제할 사례를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8323b-147">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="8323b-148">설정 **탭의** **대소문자 정보에서** 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8323b-148">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="8323b-149">사례 **삭제를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8323b-149">Click **Delete case**.</span></span>
