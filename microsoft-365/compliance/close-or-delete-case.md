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
description: 고급 eDiscovery 사례에서 지 원하는 조사 또는 법적 사례가 종료 되거나 삭제 된 경우 수행 되는 작업에 대해 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: be8d133a8215fc40c6d33025f9f4d1dee0f3b609
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412787"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="fe193-103">고급 eDiscovery 사례 닫기 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="fe193-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="fe193-104">고급 eDiscovery 사례에서 지 원하는 법적 사례 또는 조사가 완료 되 면 대/소문자를 닫거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="fe193-105">종료 된 케이스를 다시 열 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="fe193-106">사례 닫기</span><span class="sxs-lookup"><span data-stu-id="fe193-106">Close a case</span></span>

<span data-ttu-id="fe193-107">고급 eDiscovery 사례를 닫을 때 수행 되는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="fe193-108">대/소문자에 보류 중인 콘텐츠 위치가 포함 되어 있으면 해당 보류를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="fe193-109">보류를 해제 하면 보류 중인 콘텐츠 위치에 30 일 유예 기간 ( *지연 대기*)이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="fe193-110">이를 통해 콘텐츠가 즉시 삭제 되는 것을 방지 하 고 관리자에 게 지연 보존 기간이 만료 된 후 영구적으로 삭제 되는 콘텐츠를 검색 하거나 복구할 수 있는 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="fe193-111">자세한 내용은 [eDiscovery 보류에서 콘텐츠 위치 제거](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe193-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="fe193-112">사례를 닫으면 해당 사례와 연결 된 보류만 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="fe193-113">콘텐츠 위치 (예: 소송 보존, 코어 eDiscovery 보류, 다른 고급 eDiscovery 사례의 보류 등)에 다른 보류가 있는 경우 해당 보류는 계속 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="fe193-114">이 사례는 여전히 Microsoft 365 준수 센터의 eDiscovery 페이지에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fe193-115">닫힌 사례에 대 한 세부 정보, 보류, 검색 및 구성원은 그대로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="fe193-116">해당 사례가 닫힌 후에 대/소문자를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="fe193-117">예를 들어 고급 eDiscovery에서 구성원을 추가 하거나 제거 하 고, 검색을 만들고, 검색 결과를 내보내고, 검색 결과를 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="fe193-118">활성 사례와 닫힌 사례의 주요 차이점은 사례를 닫을 때 보류가 해제 된다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="fe193-119">사례를 닫으려면:</span><span class="sxs-lookup"><span data-stu-id="fe193-119">To close a case:</span></span>

1. <span data-ttu-id="fe193-120">**고급 eDiscovery** 페이지에서 닫으려는 사례를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="fe193-121">**설정** 탭의 **사례 정보**에서 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="fe193-122">**대/소문자 닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-122">Click **Close case**.</span></span>

   <span data-ttu-id="fe193-123">닫기 프로세스를 완료 하는 데 최대 60 분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-123">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="fe193-124">닫힌 사례 다시 열기</span><span class="sxs-lookup"><span data-stu-id="fe193-124">Reopen a closed case</span></span>

<span data-ttu-id="fe193-125">고급 eDiscovery 사례를 다시 열면 서비스 케이스가 종료 될 때 적용 된 모든 보류는 자동으로 복원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-125">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="fe193-126">사례를 다시 연 후에는 **보류** 탭으로 이동 하 여 이전 보류를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-126">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="fe193-127">보류를 설정 하려면이 옵션을 선택 하 여 플라이 아웃 페이지를 표시 하 고 **상태** 전환 설정을 **켜기**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-127">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="fe193-128">닫힌 사례를 다시 열려면:</span><span class="sxs-lookup"><span data-stu-id="fe193-128">To reopen a closed case:</span></span>

1. <span data-ttu-id="fe193-129">**고급 eDiscovery** 페이지에서 삭제할 사례를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-129">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="fe193-130">**설정** 탭의 **사례 정보**에서 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-130">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="fe193-131">**대/소문자 다시 열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-131">Click **Reopen case**.</span></span>

   <span data-ttu-id="fe193-132">다시 여는 프로세스를 완료 하는 데 최대 60 분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-132">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="fe193-133">사례 삭제</span><span class="sxs-lookup"><span data-stu-id="fe193-133">Delete a case</span></span>

<span data-ttu-id="fe193-134">활성 및 닫힌 Advanced eDiscovery 사례를 모두 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-134">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="fe193-135">사례를 삭제 하면 해당 사례와 관련 된 모든 구성 요소 (예: custodians, communications, 검색, 검토 집합 및 내보내기 작업)가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-135">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="fe193-136">Microsoft 365 준수 센터의 **고급 eDiscovery** 페이지에 있는 사례 목록에서 사례를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-136">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fe193-137">삭제 된 사례는 복구 하거나 다시 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-137">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="fe193-138">데이터 유출 시나리오에서 검토 집합의 항목을 제거 하는 유일한 방법은 Advanced eDiscovery 사례를 삭제 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-138">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="fe193-139">기타 "검색 및 제거" 방법은 검토 집합에서 항목을 제거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-139">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="fe193-140">사례 (활성 또는 마감 여부)를 삭제 하려면 먼저 사례와 연결 된 *모든* 보류를 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-140">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="fe193-141">이는 상태가 **Off**인 삭제 보류를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-141">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="fe193-142">사례와 연결 된 보류를 삭제 하려면:</span><span class="sxs-lookup"><span data-stu-id="fe193-142">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="fe193-143">삭제 하려는 고급 eDiscovery 사례의 **보류** 탭을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-143">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="fe193-144">삭제할 보류를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-144">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="fe193-145">플라이 아웃 페이지에서 **보류 삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-145">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="fe193-146">사례를 삭제 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-146">To delete a case:</span></span>

1. <span data-ttu-id="fe193-147">**고급 eDiscovery** 페이지에서 삭제할 사례를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-147">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="fe193-148">**설정** 탭의 **사례 정보**에서 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-148">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="fe193-149">**대/소문자 삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe193-149">Click **Delete case**.</span></span>
