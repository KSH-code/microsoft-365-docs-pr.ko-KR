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
description: Advanced eDiscovery 사례에서 지원되는 조사 또는 법률 사례가 닫히거나 삭제될 때 발생하는 일에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7b11faa2ccdb44fca916b2f602d5120adadf1739
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657654"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="56803-103">사례 닫기 또는 Advanced eDiscovery 삭제</span><span class="sxs-lookup"><span data-stu-id="56803-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="56803-104">Advanced eDiscovery 지원되는 법률 사례 또는 조사가 완료되면 사례를 닫거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56803-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="56803-105">닫힌 사례를 다시 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56803-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="56803-106">사례 닫기</span><span class="sxs-lookup"><span data-stu-id="56803-106">Close a case</span></span>

<span data-ttu-id="56803-107">다음은 사례를 닫을 때 Advanced eDiscovery 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="56803-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="56803-108">케이스에 보류된 콘텐츠 위치가 포함되어 있는 경우 해당 보류는 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="56803-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="56803-109">보류가 해제된 후 30일의 유예 기간(지연 보류)이 보류된 콘텐츠 위치에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="56803-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="56803-110">이렇게 하면 콘텐츠가 즉시 삭제되는 것을 방지할 수 있으며, 관리자는 지연 보류 기간이 만료된 후 영구적으로 삭제되는 콘텐츠를 검색하거나 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56803-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="56803-111">자세한 내용은 [eDiscovery 보류에서](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)콘텐츠 위치 제거를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56803-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="56803-112">케이스를 닫으면 케이스와 연결된 보류 항목만 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="56803-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="56803-113">다른 보류가 콘텐츠 위치(예: 소송 보류, Core eDiscovery 보류 또는 다른 Advanced eDiscovery 사례의 보류)에 있는 경우에도 해당 보류는 계속 유지 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="56803-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="56803-114">사례는 여전히 규정 준수 센터의 eDiscovery 페이지에 Microsoft 365 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="56803-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="56803-115">닫힌 케이스의 세부 정보, 보류, 검색 및 구성원은 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="56803-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="56803-116">사례를 닫은 후 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56803-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="56803-117">예를 들어 구성원을 추가 또는 제거하고, 검색을 만들고, 검색 결과를 내보내고, 검색 결과에서 분석을 위해 검색 결과를 준비할 Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="56803-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="56803-118">활성 케이스와 닫힌 케이스의 주요 차이점은 케이스를 닫을 때 보류가 해제된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="56803-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="56803-119">케이스를 닫으려면</span><span class="sxs-lookup"><span data-stu-id="56803-119">To close a case:</span></span>

1. <span data-ttu-id="56803-120">**Advanced eDiscovery** 페이지에서 닫을 케이스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="56803-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="56803-121">**설정** 탭의 **케이스 정보** 에서 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="56803-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="56803-122">사례 정보 플라이아웃 페이지의 맨 아래에서 ( ... )**를 클릭합니다.**  **추가 옵션** 을 클릭한 다음 대소문자 **닫기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="56803-122">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Close case**.</span></span>

   ![다른 옵션 메뉴의 옵션에서 추가 Advanced eDiscovery 닫기](..\Media\CloseAdvancedeDiscoveryCase.png)

   <span data-ttu-id="56803-124">닫기 프로세스를 완료하는 데 최대 60분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56803-124">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="56803-125">닫힌 사례 다시 열기</span><span class="sxs-lookup"><span data-stu-id="56803-125">Reopen a closed case</span></span>

<span data-ttu-id="56803-126">Advanced eDiscovery 사례를 다시 열면 사례를 닫을 때 수행되던 보류가 자동으로 다시 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56803-126">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="56803-127">사례가 다시 열리면 보류 탭으로 이동하여  이전 보류를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56803-127">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="56803-128">보류를 설정하려면 해당 보류를 선택해 플라이아웃 페이지를 표시한 다음 **상태** 토글을 **켜기** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="56803-128">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="56803-129">닫힌 사례를 다시 열기 위해</span><span class="sxs-lookup"><span data-stu-id="56803-129">To reopen a closed case:</span></span>

1. <span data-ttu-id="56803-130">**Advanced eDiscovery** 페이지에서 다시 열 케이스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="56803-130">On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id="56803-131">**설정** 탭의 **케이스 정보** 에서 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="56803-131">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="56803-132">사례 정보 플라이아웃 페이지의 맨 아래에서 ( ... )**를 클릭합니다.**  **추가 옵션** 을 클릭한 다음 사례 다시 **열기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="56803-132">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Reopen case**.</span></span>

   ![다른 옵션 메뉴의 옵션에서 사례를 다시 Advanced eDiscovery 옵션](..\Media\ReopenAdvancedeDiscoveryCase.png)

   <span data-ttu-id="56803-134">다시 열기 프로세스를 완료하는 데 최대 60분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56803-134">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="56803-135">사례 삭제</span><span class="sxs-lookup"><span data-stu-id="56803-135">Delete a case</span></span>

<span data-ttu-id="56803-136">활성 및 닫힌 사례를 모두 삭제할 Advanced eDiscovery 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56803-136">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="56803-137">케이스를 삭제하면 보유자, 통신, 검색, 검토 집합 및 내보내기 작업의 목록과 같은 케이스와 연결된 모든 구성 요소가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="56803-137">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="56803-138">사례는 규정 준수 센터의 Advanced eDiscovery **사례** 목록에서 Microsoft 365 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="56803-138">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="56803-139">삭제된 사례는 복구하거나 다시 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56803-139">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="56803-140">데이터 유출 시나리오에서 검토 집합의 항목을 제거하는 유일한 방법은 사례를 삭제하는 Advanced eDiscovery 것입니다.</span><span class="sxs-lookup"><span data-stu-id="56803-140">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="56803-141">다른 "검색 및 삭제" 메서드는 검토 집합에서 항목을 제거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56803-141">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="56803-142">사례를 삭제하려면 먼저 사례와 연결된 모든 보류를  삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56803-142">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="56803-143">여기에는 끄기 상태의 보류 삭제가 **포함됩니다.**</span><span class="sxs-lookup"><span data-stu-id="56803-143">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="56803-144">사례와 연결된 보류를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="56803-144">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="56803-145">삭제할 **Advanced eDiscovery** 보류 탭으로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="56803-145">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="56803-146">삭제할 보류를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="56803-146">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="56803-147">플라이아웃 페이지에서 보류 **삭제를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="56803-147">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="56803-148">케이스를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="56803-148">To delete a case:</span></span>

1. <span data-ttu-id="56803-149">**Advanced eDiscovery** 페이지에서 삭제할 케이스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="56803-149">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="56803-150">**설정** 탭의 **케이스 정보** 에서 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="56803-150">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="56803-151">사례 정보 플라이아웃 페이지의 맨 아래에서 ( ... )**를 클릭합니다.**  **추가 옵션** 을 클릭한 다음 대소문자 **삭제를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="56803-151">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Delete case**.</span></span>

   ![다른 옵션 메뉴의 옵션에서 사례를 삭제하는 Advanced eDiscovery](..\Media\DeleteAdvancedeDiscoveryCase.png)
