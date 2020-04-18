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
ms.openlocfilehash: 41ba622a58b0abb5ce668e6d94d89b1694a328c9
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551425"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="71244-104">핵심 eDiscovery 사례 닫기, 다시 열기 및 삭제</span><span class="sxs-lookup"><span data-stu-id="71244-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="71244-105">이 문서에서는 Microsoft 365에서 핵심 eDiscovery 사례를 닫고, 다시 열고, 삭제 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="71244-106">사례 닫기</span><span class="sxs-lookup"><span data-stu-id="71244-106">Close a case</span></span>

<span data-ttu-id="71244-107">핵심 eDiscovery 사례에서 지 원하는 법적 사례 또는 조사가 완료 되 면 사례를 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71244-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="71244-108">사례를 닫을 때 수행 되는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="71244-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="71244-109">사례에 eDiscovery 보류의 콘텐츠 위치가 포함 되어 있는 경우 해당 보류는 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71244-109">If the case contains any content locations on eDiscovery hold, those holds will be turned off.</span></span> <span data-ttu-id="71244-110">이로 인해 사용자 또는 자동화 된 프로세스 (예: 삭제 정책)에 의해 콘텐츠가 영구적으로 삭제 되거나 제거 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71244-110">This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="71244-111">사례를 닫으면 해당 사례와 연결 된 보류만 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71244-111">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="71244-112">다른 보류가 콘텐츠 위치 (예: 소송 보류, 보존 정책 또는 다른 코어 eDiscovery 사례의 보류)에 배치 되 면 해당 보류는 계속 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71244-112">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="71244-113">이 사례는 여전히 Microsoft 365 준수 센터의 핵심 eDiscovery 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71244-113">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="71244-114">닫힌 사례에 대 한 세부 정보, 보류, 검색 및 구성원은 그대로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71244-114">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="71244-115">해당 사례가 닫힌 후에 대/소문자를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71244-115">You can edit a case after it's closed.</span></span> <span data-ttu-id="71244-116">예를 들어 구성원을 추가 하거나 제거 하 고, 검색을 만들고, 검색 결과를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71244-116">For example, you can add or removing members, create searches, and export search results.</span></span> <span data-ttu-id="71244-117">활성 사례와 닫힌 사례의 주요 차이점은 사례를 닫을 때 eDiscovery 보류가 해제 된다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="71244-117">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="71244-118">사례를 닫으려면:</span><span class="sxs-lookup"><span data-stu-id="71244-118">To close a case:</span></span>
  
1. <span data-ttu-id="71244-119">Microsoft 365 준수 서비스 입력에서 **eDiscovery** > **코어** 를 클릭 하 여 조직의 핵심 eDiscovery 사례 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-119">In the Microsoft 365 compliance enter, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="71244-120">닫으려는 case의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-120">Click the name of the case that you want to close.</span></span>

    <span data-ttu-id="71244-121">**이 사례** 플라이 아웃 관리 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71244-121">The **Manage this case** flyout page is displayed.</span></span>

3. <span data-ttu-id="71244-122">**사례 관리 상태**에서 **대/소문자 닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-122">Under **Manage case status**, click **Close case**.</span></span>

    <span data-ttu-id="71244-123">사례와 연결 된 보류가 해제 됨을 나타내는 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71244-123">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="71244-124">**예** 를 클릭 하 여 사례를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="71244-124">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="71244-125">**이 사례** 플라이 아웃 관리 페이지의 상태가 **활성** 에서 **종료**로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71244-125">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="71244-126">**이 사례 관리** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="71244-126">Close the **Manage this case** page.</span></span>

6. <span data-ttu-id="71244-127">**코어 eDiscovery** 페이지에서 **새로 고침** 을 클릭 하 여 종료 된 사례의 상태를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-127">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="71244-128">닫기 프로세스를 완료 하는 데 최대 60 분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71244-128">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="71244-129">프로세스가 완료 되 면 **핵심 eDiscovery** 페이지에서 사례 상태가 **닫힘으로** 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71244-129">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span> <span data-ttu-id="71244-130">케이스의 이름을 다시 클릭 하 여 사례를 닫은 사람과 닫은 사람에 대 한 정보가 포함 된 **이 사례** 플라이 아웃 관리 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-130">Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="71244-131">닫힌 사례 다시 열기</span><span class="sxs-lookup"><span data-stu-id="71244-131">Reopen a closed case</span></span>

<span data-ttu-id="71244-132">사례를 다시 열면 사례를 닫을 때 적용 되었던 eDiscovery 보류가 자동으로 복원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71244-132">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="71244-133">사례를 다시 연 후에는 **보류** 페이지로 이동 하 여 이전 보류를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-133">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="71244-134">보류를 설정 하려면이 옵션을 선택 하 여 플라이 아웃 페이지를 표시 하 고 **상태** 전환 설정을 **켜기**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-134">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="71244-135">Microsoft 365 준수 서비스 입력에서 **eDiscovery** > **코어** 를 클릭 하 여 조직의 핵심 eDiscovery 사례 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-135">In the Microsoft 365 compliance enter, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="71244-136">다시 열 사례 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-136">Click the name of the case that you want to reopen.</span></span>

    <span data-ttu-id="71244-137">**이 사례** 플라이 아웃 관리 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71244-137">The **Manage this case** flyout page is displayed.</span></span> 

3. <span data-ttu-id="71244-138">**사례 관리 상태**에서 **대/소문자 다시 열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-138">Under **Manage case status**, click **Reopen case**.</span></span>

    <span data-ttu-id="71244-139">닫힌 경우 케이스와 연결 된 보류를 자동으로 설정 하지 않으면 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71244-139">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="71244-140">**예** 를 클릭 하 여 사례를 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="71244-140">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="71244-141">**이 사례** 플라이 아웃 관리 페이지의 상태가 **닫힘** 에서 **활성**으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71244-141">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="71244-142">**이 사례 관리** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="71244-142">Close the **Manage this case** page.</span></span> 

6. <span data-ttu-id="71244-143">**코어 eDiscovery** 페이지에서 **새로 고침** 을 클릭 하 여 다시 연 사례의 상태를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-143">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="71244-144">다시 여는 프로세스를 완료 하는 데 최대 60 분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71244-144">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="71244-145">프로세스가 완료 되 면 **핵심 eDiscovery** 페이지에서 사례 상태가 **활성** 으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71244-145">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span> 
  
## <a name="delete-a-case"></a><span data-ttu-id="71244-146">사례 삭제</span><span class="sxs-lookup"><span data-stu-id="71244-146">Delete a case</span></span>

<span data-ttu-id="71244-147">활성 및 닫힌 코어 eDiscovery 사례를 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71244-147">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="71244-148">사례를 삭제 하면 해당 케이스의 모든 검색 및 내보내기가 삭제 되 고 Microsoft 365 준수 센터의 **핵심 eDiscovery** 페이지에 있는 사례 목록에서 케이스가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71244-148">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="71244-149">삭제 된 사례는 다시 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71244-149">You can't reopen a deleted case.</span></span>

<span data-ttu-id="71244-150">사례 (활성 또는 마감 여부)를 삭제 하려면 먼저 사례와 연결 된 eDiscovery 보류를 *모두* 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-150">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="71244-151">이는 상태가 **Off**인 삭제 보류를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-151">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="71244-152">EDiscovery 보류를 삭제 하려면:</span><span class="sxs-lookup"><span data-stu-id="71244-152">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="71244-153">삭제 하려는 경우 **보류** 탭을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-153">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="71244-154">삭제할 보류를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-154">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="71244-155">플라이 아웃 페이지에서 **보류 삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-155">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="71244-156">사례를 삭제 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-156">To delete a case:</span></span>

1. <span data-ttu-id="71244-157">Microsoft 365 준수 서비스 입력에서 **eDiscovery** > **코어** 를 클릭 하 여 조직의 핵심 eDiscovery 사례 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-157">In the Microsoft 365 compliance enter, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="71244-158">삭제 하려는 서비스 케이스의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-158">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="71244-159">플라이 아웃 페이지의 **사례 상태 관리** 에서 **대/소문자 삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-159">Under **Manage case status** on the flyout page, click **Delete case**.</span></span>

<span data-ttu-id="71244-160">삭제 하려는 사례에 아직 eDiscovery 보류가 포함 되어 있는 경우 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71244-160">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="71244-161">사례와 연결 된 모든 보류를 삭제 한 후 사례를 삭제 하 고 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="71244-161">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
