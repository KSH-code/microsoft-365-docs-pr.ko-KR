---
title: Core eDiscovery 사례 닫기, 다시 열기 및 삭제
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 Core eDiscovery 사례를 관리하는 방법을 설명합니다. 여기에는 사례 닫기, 닫힌 사례 다시 열기 및 사례 삭제가 포함됩니다.
ms.openlocfilehash: 17b243a7207fd6927188b42e585101ff1d258b76
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412797"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="eba52-104">Core eDiscovery 사례 닫기, 다시 열기 및 삭제</span><span class="sxs-lookup"><span data-stu-id="eba52-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="eba52-105">이 문서에서는 Microsoft 365에서 Core eDiscovery 사례를 닫고, 다시 열고, 삭제하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="eba52-106">사례 닫기</span><span class="sxs-lookup"><span data-stu-id="eba52-106">Close a case</span></span>

<span data-ttu-id="eba52-107">Core eDiscovery 사례에서 지원되는 법적 사례 또는 조사가 완료되면 사례를 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="eba52-108">사례를 닫을 때 발생하는 문제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="eba52-109">사례에 eDiscovery 보류의 콘텐츠 위치가 포함되어 있는 경우 해당 보류가 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-109">If the case contains any content locations on eDiscovery hold, those holds will be turned off.</span></span> <span data-ttu-id="eba52-110">보류가 해제된 후 30일의 유예 기간(지연 보류)이 보류된 콘텐츠 위치에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="eba52-111">이렇게 하면 콘텐츠가 즉시 삭제되는 것을 방지하고 관리자가 지연 보류 기간이 만료된 후 영구적으로 삭제되기 전에 콘텐츠를 검색하고 복원할 수 있는 기회를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="eba52-112">자세한 내용은 [eDiscovery](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)보류에서 콘텐츠 위치 제거를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eba52-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="eba52-113">사례를 닫을 경우 해당 사례와 연결된 보류만 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="eba52-114">다른 보존이 콘텐츠 위치(예: 소송 보존, 보존 정책 또는 다른 Core eDiscovery 사례의 보류)에 배치된 경우에도 해당 보류는 유지 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="eba52-115">이 사례는 Microsoft 365 규정 준수 센터의 Core eDiscovery 페이지에 계속 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="eba52-116">마감된 사례의 세부 정보, 보류, 검색 및 구성원은 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="eba52-117">사례를 닫은 후 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="eba52-118">예를 들어 구성원을 추가 또는 제거하고, 검색을 만들고, 검색 결과를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-118">For example, you can add or removing members, create searches, and export search results.</span></span> <span data-ttu-id="eba52-119">활성 및 닫힌 사례의 주요 차이점은 사례가 닫히면 eDiscovery 보류가 꺼져 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="eba52-120">사례를 닫는 경우:</span><span class="sxs-lookup"><span data-stu-id="eba52-120">To close a case:</span></span>
  
1. <span data-ttu-id="eba52-121">Microsoft 365 규정 준수 센터에서 **eDiscovery** Core를 클릭하여 조직의  >   Core eDiscovery 사례 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="eba52-122">닫을 사례의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-122">Click the name of the case that you want to close.</span></span>

    <span data-ttu-id="eba52-123">이 **사례 관리 플라이아웃** 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-123">The **Manage this case** flyout page is displayed.</span></span>

3. <span data-ttu-id="eba52-124">사례 **관리 상태 아래에서** 사례 **닫기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="eba52-124">Under **Manage case status**, click **Close case**.</span></span>

    <span data-ttu-id="eba52-125">사례와 연결된 보류가 해제될 것 같은 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="eba52-126">예를 **클릭하여** 사례를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="eba52-127">이 경우 **플라이아웃** 관리 페이지의 상태가 활성에서 **닫기로** **변경됩니다.**</span><span class="sxs-lookup"><span data-stu-id="eba52-127">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="eba52-128">이 사례 **관리 페이지를 닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="eba52-128">Close the **Manage this case** page.</span></span>

6. <span data-ttu-id="eba52-129">Core **eDiscovery 페이지에서** 새로  고침을 클릭하여 닫힌 사례의 상태를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-129">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="eba52-130">닫는 프로세스가 완료될 때 최대 60분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-130">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="eba52-131">프로세스가 완료되면 사례 상태가 **Core eDiscovery** 페이지에서 **Closed로** 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-131">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span> <span data-ttu-id="eba52-132">사례 이름을 다시 클릭하여 사례가  닫힌 경우 및 닫힌 사람에 대한 정보가 포함된 이 사례 플라이아웃 관리 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-132">Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="eba52-133">닫힌 사례 다시 열기</span><span class="sxs-lookup"><span data-stu-id="eba52-133">Reopen a closed case</span></span>

<span data-ttu-id="eba52-134">사례를 다시 열면 사례가 닫혀 있을 때 수행된 eDiscovery 보류가 자동으로 다시 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-134">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="eba52-135">사례가 다시 열리면 보류 페이지로 이동하여  이전 보류를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-135">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="eba52-136">보류를 켜고 플라이아웃 페이지를 표시하려면 해당 페이지를  선택한 다음 상태 토글을 **켜기로 설정하십시오.**</span><span class="sxs-lookup"><span data-stu-id="eba52-136">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="eba52-137">Microsoft 365 규정 준수 센터에서 **eDiscovery** Core를 클릭하여 조직의  >   Core eDiscovery 사례 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-137">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="eba52-138">다시 열 사례의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-138">Click the name of the case that you want to reopen.</span></span>

    <span data-ttu-id="eba52-139">이 **사례 관리 플라이아웃** 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-139">The **Manage this case** flyout page is displayed.</span></span> 

3. <span data-ttu-id="eba52-140">사례 **관리 상태 아래에서** 사례 다시 **열기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="eba52-140">Under **Manage case status**, click **Reopen case**.</span></span>

    <span data-ttu-id="eba52-141">사례가 닫힌 경우와 연결된 보류가 자동으로 켜져 있을 수 없다고 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-141">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="eba52-142">**예를** 클릭하여 사례를 다시 하세요.</span><span class="sxs-lookup"><span data-stu-id="eba52-142">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="eba52-143">이 경우 **플라이아웃** 관리 페이지의 상태가 **Closed에서** 활성으로 **변경됩니다.**</span><span class="sxs-lookup"><span data-stu-id="eba52-143">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="eba52-144">이 사례 **관리 페이지를 닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="eba52-144">Close the **Manage this case** page.</span></span> 

6. <span data-ttu-id="eba52-145">Core **eDiscovery** 페이지에서 새로  고침을 클릭하여 다시 연 사례의 상태를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-145">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="eba52-146">다시 열기 프로세스를 완료하는 데 최대 60분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-146">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="eba52-147">프로세스가 완료되면 **Core eDiscovery** 페이지에서 사례 상태가 **활성으로** 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-147">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span> 
  
## <a name="delete-a-case"></a><span data-ttu-id="eba52-148">사례 삭제</span><span class="sxs-lookup"><span data-stu-id="eba52-148">Delete a case</span></span>

<span data-ttu-id="eba52-149">활성 및 닫힌 Core eDiscovery 사례를 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-149">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="eba52-150">사례를 삭제하면 사례의 모든 검색 및 내보내기가 삭제되고 Microsoft 365 규정 준수 센터의 **Core eDiscovery** 페이지의 사례 목록에서 사례가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-150">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="eba52-151">삭제된 사례는 다시 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-151">You can't reopen a deleted case.</span></span>

<span data-ttu-id="eba52-152">사례를 삭제하려면 먼저 사례와 연결된 *모든* eDiscovery 보류를 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-152">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="eba52-153">여기에는 해제 상태의 보류 삭제가 **포함됩니다.**</span><span class="sxs-lookup"><span data-stu-id="eba52-153">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="eba52-154">eDiscovery 보류를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="eba52-154">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="eba52-155">삭제하려는  경우 보류 탭으로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="eba52-155">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="eba52-156">삭제할 보류를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-156">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="eba52-157">플라이아웃 페이지에서 보류 **삭제를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="eba52-157">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="eba52-158">사례를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="eba52-158">To delete a case:</span></span>

1. <span data-ttu-id="eba52-159">Microsoft 365 규정 준수 센터에서 **eDiscovery** Core를 클릭하여 조직의  >   Core eDiscovery 사례 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-159">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="eba52-160">삭제할 사례의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-160">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="eba52-161">**플라이아웃 페이지에서 사례** 관리 상태 아래에서 사례 **삭제를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="eba52-161">Under **Manage case status** on the flyout page, click **Delete case**.</span></span>

<span data-ttu-id="eba52-162">삭제하려는 사례에 eDiscovery 보류가 여전히 포함되어 있는 경우 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="eba52-163">사례와 연결된 모든 보류를 삭제한 다음 사례를 다시 삭제해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba52-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
