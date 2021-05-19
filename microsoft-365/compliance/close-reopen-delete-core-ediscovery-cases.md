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
description: 이 문서에서는 핵심 eDiscovery 사례를 관리하는 방법을 설명합니다. 여기에는 사례 닫기, 닫힌 사례 다시 열기 및 사례 삭제가 포함됩니다.
ms.openlocfilehash: 8a54d5c8f93d36351538bc235a6dbeaaa602c3e9
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52532449"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="4f730-104">Core eDiscovery 사례 닫기, 다시 열기 및 삭제</span><span class="sxs-lookup"><span data-stu-id="4f730-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="4f730-105">이 문서에서는 이 문서에서 핵심 eDiscovery 사례를 닫고, 다시 열고, 삭제하는 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4f730-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="4f730-106">사례 닫기</span><span class="sxs-lookup"><span data-stu-id="4f730-106">Close a case</span></span>

<span data-ttu-id="4f730-107">Core eDiscovery 사례에서 지원되는 법적 사례 또는 조사가 완료되면 사례를 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="4f730-108">사례를 닫을 때 발생하는 경우는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="4f730-109">사례에 eDiscovery 보류가 포함된 경우 해당 보류가 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-109">If the case contains any eDiscovery holds, they will be turned off.</span></span> <span data-ttu-id="4f730-110">보류가 해제된 후 30일의 유예 기간(지연 보류)이 보류된 콘텐츠 위치에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="4f730-111">이렇게 하면 콘텐츠가 즉시 삭제되는 것을 방지할 수 있으며, 관리자가 지연 보류 기간이 만료된 후 영구적으로 삭제되기 전에 콘텐츠를 검색하고 복원할 수 있는 기회를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="4f730-112">자세한 내용은 [eDiscovery 보류에서](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)콘텐츠 위치 제거를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f730-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="4f730-113">케이스를 닫으면 케이스와 연결된 보류 항목만 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="4f730-114">다른 보존이 콘텐츠 위치(예: 소송 보존, 보존 정책 또는 다른 Core eDiscovery 사례의 보류)에 배치된 경우에도 해당 보존은 유지 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="4f730-115">사례는 여전히 규정 준수 센터의 Core eDiscovery 페이지에 Microsoft 365 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="4f730-116">닫힌 케이스의 세부 정보, 보류, 검색 및 구성원은 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="4f730-117">사례를 닫은 후 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="4f730-118">예를 들어 구성원을 추가 또는 제거하고, 검색을 만들고, 검색 결과를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-118">For example, you can add or remove members, create searches, and export search results.</span></span> <span data-ttu-id="4f730-119">활성 사례와 닫힌 사례의 주요 차이점은 사례가 닫히면 eDiscovery 보류가 해제되어 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="4f730-120">케이스를 닫으려면</span><span class="sxs-lookup"><span data-stu-id="4f730-120">To close a case:</span></span>
  
1. <span data-ttu-id="4f730-121">조직 Microsoft 365 센터에서 **eDiscovery** Core를 클릭하여 조직의  >   핵심 eDiscovery 사례 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="4f730-122">닫을 사례의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-122">Click the name of the case that you want to close.</span></span>

   ![사례 홈 페이지에서 대소문자 닫기](../media/eDiscoveryCaseHomePage.png)

3. <span data-ttu-id="4f730-124">홈 페이지의 상태 **아래에서** **대소문자 닫기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f730-124">On the home page, under **Status**, click **Close case**.</span></span>

    <span data-ttu-id="4f730-125">사례와 연결된 보류가 해제될 것 같은 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="4f730-126">예를 **클릭하여** 사례를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="4f730-127">사례 홈 페이지의 상태가 활성에서 닫기 **로** **변경됩니다.**</span><span class="sxs-lookup"><span data-stu-id="4f730-127">The status on the case home page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="4f730-128">Core **eDiscovery** 페이지에서 새로  고침을 클릭하여 닫힌 사례의 상태를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-128">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="4f730-129">닫기 프로세스를 완료하는 데 최대 60분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-129">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="4f730-130">프로세스가 완료되면 Core **eDiscovery** 페이지에서  사례 상태가 Closed로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-130">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="4f730-131">닫힌 사례 다시 열기</span><span class="sxs-lookup"><span data-stu-id="4f730-131">Reopen a closed case</span></span>

<span data-ttu-id="4f730-132">사례를 다시 열면 사례가 닫혀 있을 때 실행되던 eDiscovery 보류가 자동으로 다시 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-132">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="4f730-133">사례가 다시 열리면 보류 페이지로 이동하여  이전 보류를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-133">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="4f730-134">보류를 설정하려면 해당 보류를 선택해 플라이아웃 페이지를 표시한 다음 **상태** 토글을 **켜기** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-134">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="4f730-135">조직 Microsoft 365 센터에서 **eDiscovery** Core를 클릭하여 조직의  >   핵심 eDiscovery 사례 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-135">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="4f730-136">다시 열 사례의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-136">Click the name of the case that you want to reopen.</span></span>

   ![닫힌 사례 다시 열기](../media/eDiscoveryCaseHomePageReopen.png)

3. <span data-ttu-id="4f730-138">홈 페이지의 상태 **아래에서** 사례 **다시 열기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f730-138">On the home page, under **Status**, click **Reopen case**.</span></span>

    <span data-ttu-id="4f730-139">사례가 닫히면 사례와 연결된 보류가 자동으로 설정되지 않는 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-139">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="4f730-140">**사례를** 다시 열려면 예를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-140">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="4f730-141">사례 홈 페이지 플라이아웃 페이지의 상태가 **닫힌** 상태에서 활성으로 **변경됩니다.**</span><span class="sxs-lookup"><span data-stu-id="4f730-141">The status on the case home page flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="4f730-142">Core **eDiscovery** 페이지에서 새로  고침을 클릭하여 다시 연 사례의 상태를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-142">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="4f730-143">다시 열기 프로세스를 완료하는 데 최대 60분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-143">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="4f730-144">프로세스가 완료되면 **Core eDiscovery** 페이지에서  사례 상태가 활성으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-144">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span>

6. <span data-ttu-id="4f730-145">(선택 사항) 다시 열린 사례와 연결된 보류를 설정하려면 보류 탭으로 이동하여 보류를 선택한 다음  보류 플라이아웃 페이지의 상태 아래에서 확인란을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="4f730-145">(Optional) To turn on any holds associated with the reopened case, go to **Holds** tab, select a hold, and then select the checkbox under **Status** on the hold flyout page.</span></span>
  
## <a name="delete-a-case"></a><span data-ttu-id="4f730-146">사례 삭제</span><span class="sxs-lookup"><span data-stu-id="4f730-146">Delete a case</span></span>

<span data-ttu-id="4f730-147">활성 및 닫힌 Core eDiscovery 사례를 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-147">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="4f730-148">사례를 삭제하면 사례의 모든 검색 및 내보내기 목록이 삭제되고, 사례는 Microsoft 365 준수 센터의 **Core eDiscovery** 페이지에 있는 사례 목록에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-148">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="4f730-149">삭제된 사례는 다시 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-149">You can't reopen a deleted case.</span></span>

<span data-ttu-id="4f730-150">사례를 삭제하려면 먼저 사례와 연결된 *모든* eDiscovery 보류를 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-150">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="4f730-151">여기에는 끄기 상태의 보류 삭제가 **포함됩니다.**</span><span class="sxs-lookup"><span data-stu-id="4f730-151">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="4f730-152">eDiscovery 보류를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="4f730-152">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="4f730-153">삭제하려는  경우 보류 탭으로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="4f730-153">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="4f730-154">삭제할 보류를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-154">Select the hold that you want to delete.</span></span>

3. <span data-ttu-id="4f730-155">플라이아웃 페이지에서 **삭제를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f730-155">On the flyout page, click **Delete**.</span></span>

      ![eDiscovery 보류 삭제](../media/DeleteeDiscoveryHold.png)

<span data-ttu-id="4f730-157">케이스를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="4f730-157">To delete a case:</span></span>

1. <span data-ttu-id="4f730-158">조직 Microsoft 365 센터에서 **eDiscovery** Core를 클릭하여 조직의  >   핵심 eDiscovery 사례 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-158">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="4f730-159">삭제할 사례의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-159">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="4f730-160">사례 홈 페이지의 상태 **아래에서** 사례 **삭제를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f730-160">On the case home page, under **Status**, click **Delete case**.</span></span>

      ![사례 삭제](../media/eDiscoveryCaseHomePageDelete.png)

<span data-ttu-id="4f730-162">삭제하려는 사례에 eDiscovery 보류가 계속 포함되어 있는 경우 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="4f730-163">사례와 연결된 모든 보류를 삭제한 다음 다시 시도하여 사례를 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f730-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
