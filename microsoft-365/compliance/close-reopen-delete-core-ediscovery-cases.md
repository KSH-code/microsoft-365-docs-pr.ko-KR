---
title: 핵심 eDiscovery 사례 닫기, 다시 열기 및 삭제
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
description: 이 문서에서는 핵심 eDiscovery 사례를 관리 하는 방법을 설명 합니다. 여기에는 사례 종료, 닫힌 사례 다시 열기 및 사례 삭제 등이 포함 됩니다.
ms.openlocfilehash: 17b243a7207fd6927188b42e585101ff1d258b76
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412797"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="9b9a4-104">핵심 eDiscovery 사례 닫기, 다시 열기 및 삭제</span><span class="sxs-lookup"><span data-stu-id="9b9a4-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="9b9a4-105">이 문서에서는 Microsoft 365에서 핵심 eDiscovery 사례를 닫고, 다시 열고, 삭제 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="9b9a4-106">사례 닫기</span><span class="sxs-lookup"><span data-stu-id="9b9a4-106">Close a case</span></span>

<span data-ttu-id="9b9a4-107">핵심 eDiscovery 사례에서 지 원하는 법적 사례 또는 조사가 완료 되 면 사례를 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="9b9a4-108">사례를 닫을 때 수행 되는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="9b9a4-109">사례에 eDiscovery 보류의 콘텐츠 위치가 포함 되어 있는 경우 해당 보류는 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-109">If the case contains any content locations on eDiscovery hold, those holds will be turned off.</span></span> <span data-ttu-id="9b9a4-110">보류를 해제 하면 보류 중인 콘텐츠 위치에 30 일 유예 기간 ( *지연 대기*)이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="9b9a4-111">이를 통해 콘텐츠가 즉시 삭제 되는 것을 방지 하 고 관리자가 콘텐츠를 검색 하 고 복원 하는 기회를 제공 하 여 지연 보존 기간이 만료 된 후 영구적으로 삭제 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="9b9a4-112">자세한 내용은 [eDiscovery 보류에서 콘텐츠 위치 제거](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="9b9a4-113">사례를 닫으면 해당 사례와 연결 된 보류만 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="9b9a4-114">다른 보류가 콘텐츠 위치 (예: 소송 보류, 보존 정책 또는 다른 코어 eDiscovery 사례의 보류)에 배치 되 면 해당 보류는 계속 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="9b9a4-115">이 사례는 여전히 Microsoft 365 준수 센터의 핵심 eDiscovery 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="9b9a4-116">닫힌 사례에 대 한 세부 정보, 보류, 검색 및 구성원은 그대로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="9b9a4-117">해당 사례가 닫힌 후에 대/소문자를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="9b9a4-118">예를 들어 구성원을 추가 하거나 제거 하 고, 검색을 만들고, 검색 결과를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-118">For example, you can add or removing members, create searches, and export search results.</span></span> <span data-ttu-id="9b9a4-119">활성 사례와 닫힌 사례의 주요 차이점은 사례를 닫을 때 eDiscovery 보류가 해제 된다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="9b9a4-120">사례를 닫으려면:</span><span class="sxs-lookup"><span data-stu-id="9b9a4-120">To close a case:</span></span>
  
1. <span data-ttu-id="9b9a4-121">Microsoft 365 준수 센터에서 **eDiscovery**  >  **Core** 를 클릭 하 여 조직의 핵심 eDiscovery 사례 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="9b9a4-122">닫으려는 case의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-122">Click the name of the case that you want to close.</span></span>

    <span data-ttu-id="9b9a4-123">**이 사례** 플라이 아웃 관리 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-123">The **Manage this case** flyout page is displayed.</span></span>

3. <span data-ttu-id="9b9a4-124">**사례 관리 상태**에서 **대/소문자 닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-124">Under **Manage case status**, click **Close case**.</span></span>

    <span data-ttu-id="9b9a4-125">사례와 연결 된 보류가 해제 됨을 나타내는 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="9b9a4-126">**예** 를 클릭 하 여 사례를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="9b9a4-127">**이 사례** 플라이 아웃 관리 페이지의 상태가 **활성** 에서 **종료**로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-127">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="9b9a4-128">**이 사례 관리** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-128">Close the **Manage this case** page.</span></span>

6. <span data-ttu-id="9b9a4-129">**코어 eDiscovery** 페이지에서 **새로 고침** 을 클릭 하 여 종료 된 사례의 상태를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-129">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="9b9a4-130">닫기 프로세스를 완료 하는 데 최대 60 분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-130">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="9b9a4-131">프로세스가 완료 되 면 **핵심 eDiscovery** 페이지에서 사례 상태가 **닫힘으로** 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-131">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span> <span data-ttu-id="9b9a4-132">케이스의 이름을 다시 클릭 하 여 사례를 닫은 사람과 닫은 사람에 대 한 정보가 포함 된 **이 사례** 플라이 아웃 관리 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-132">Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="9b9a4-133">닫힌 사례 다시 열기</span><span class="sxs-lookup"><span data-stu-id="9b9a4-133">Reopen a closed case</span></span>

<span data-ttu-id="9b9a4-134">사례를 다시 열면 사례를 닫을 때 적용 되었던 eDiscovery 보류가 자동으로 복원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-134">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="9b9a4-135">사례를 다시 연 후에는 **보류** 페이지로 이동 하 여 이전 보류를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-135">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="9b9a4-136">보류를 설정 하려면이 옵션을 선택 하 여 플라이 아웃 페이지를 표시 하 고 **상태** 전환 설정을 **켜기**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-136">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="9b9a4-137">Microsoft 365 준수 센터에서 **eDiscovery**  >  **Core** 를 클릭 하 여 조직의 핵심 eDiscovery 사례 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-137">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="9b9a4-138">다시 열 사례 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-138">Click the name of the case that you want to reopen.</span></span>

    <span data-ttu-id="9b9a4-139">**이 사례** 플라이 아웃 관리 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-139">The **Manage this case** flyout page is displayed.</span></span> 

3. <span data-ttu-id="9b9a4-140">**사례 관리 상태**에서 **대/소문자 다시 열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-140">Under **Manage case status**, click **Reopen case**.</span></span>

    <span data-ttu-id="9b9a4-141">닫힌 경우 케이스와 연결 된 보류를 자동으로 설정 하지 않으면 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-141">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="9b9a4-142">**예** 를 클릭 하 여 사례를 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-142">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="9b9a4-143">**이 사례** 플라이 아웃 관리 페이지의 상태가 **닫힘** 에서 **활성**으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-143">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="9b9a4-144">**이 사례 관리** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-144">Close the **Manage this case** page.</span></span> 

6. <span data-ttu-id="9b9a4-145">**코어 eDiscovery** 페이지에서 **새로 고침** 을 클릭 하 여 다시 연 사례의 상태를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-145">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="9b9a4-146">다시 여는 프로세스를 완료 하는 데 최대 60 분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-146">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="9b9a4-147">프로세스가 완료 되 면 **핵심 eDiscovery** 페이지에서 사례 상태가 **활성** 으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-147">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span> 
  
## <a name="delete-a-case"></a><span data-ttu-id="9b9a4-148">사례 삭제</span><span class="sxs-lookup"><span data-stu-id="9b9a4-148">Delete a case</span></span>

<span data-ttu-id="9b9a4-149">활성 및 닫힌 코어 eDiscovery 사례를 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-149">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="9b9a4-150">사례를 삭제 하면 해당 케이스의 모든 검색 및 내보내기가 삭제 되 고 Microsoft 365 준수 센터의 **핵심 eDiscovery** 페이지에 있는 사례 목록에서 케이스가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-150">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="9b9a4-151">삭제 된 사례는 다시 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-151">You can't reopen a deleted case.</span></span>

<span data-ttu-id="9b9a4-152">사례 (활성 또는 마감 여부)를 삭제 하려면 먼저 사례와 연결 된 eDiscovery 보류를 *모두* 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-152">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="9b9a4-153">이는 상태가 **Off**인 삭제 보류를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-153">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="9b9a4-154">EDiscovery 보류를 삭제 하려면:</span><span class="sxs-lookup"><span data-stu-id="9b9a4-154">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="9b9a4-155">삭제 하려는 경우 **보류** 탭을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-155">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="9b9a4-156">삭제할 보류를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-156">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="9b9a4-157">플라이 아웃 페이지에서 **보류 삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-157">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="9b9a4-158">사례를 삭제 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-158">To delete a case:</span></span>

1. <span data-ttu-id="9b9a4-159">Microsoft 365 준수 센터에서 **eDiscovery**  >  **Core** 를 클릭 하 여 조직의 핵심 eDiscovery 사례 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-159">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="9b9a4-160">삭제 하려는 서비스 케이스의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-160">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="9b9a4-161">플라이 아웃 페이지의 **사례 상태 관리** 에서 **대/소문자 삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-161">Under **Manage case status** on the flyout page, click **Delete case**.</span></span>

<span data-ttu-id="9b9a4-162">삭제 하려는 사례에 아직 eDiscovery 보류가 포함 되어 있는 경우 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="9b9a4-163">사례와 연결 된 모든 보류를 삭제 한 후 사례를 삭제 하 고 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9a4-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
