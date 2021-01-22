---
title: 자동화된 조사의 세부 정보 및 결과
description: '자동화 조사가 진행 되는 동한 혹은 진행 완료된 후 주요 사항 및 결과를 확인할 수 있습니다. '
keywords: 자동화, 조사, 결과, 분속, 세부정보, 재구성, 오토에어
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.technology: m365d
ms.openlocfilehash: c050683bb3ed052ae4752ffdee66fe51fb99b88b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930369"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="67724-104">자동화된 조사의 세부 정보 및 결과</span><span class="sxs-lookup"><span data-stu-id="67724-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="67724-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="67724-105">**Applies to:**</span></span>
- <span data-ttu-id="67724-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67724-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="67724-107">Microsoft 365 Defender에서 자동화된 조사가 발생하면 자동화된 조사 프로세스 중 및 이후에 조사에 대한 세부 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67724-107">When an automated investigation occurs in Microsoft 365 Defender, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="67724-108">[필수 권한이](mtp-action-center.md#required-permissions-for-action-center-tasks)있는 경우 조사 세부 정보 보기에서 해당 정보를 확인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="67724-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="67724-109">조사 세부정부 보기에서 최신 상태를 확인하거나 보류중인 작업을 승인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67724-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![조사 세부정보](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="67724-111">조사 세부정보 보기 열기 </span><span class="sxs-lookup"><span data-stu-id="67724-111">Open the investigation details view</span></span>

<span data-ttu-id="67724-112">다음 방법 중 하나를 사용 하여 조사 세부정보 보기를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67724-112">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="67724-113">작업 센터에서 항목 선택</span><span class="sxs-lookup"><span data-stu-id="67724-113">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="67724-114">문제 세부정보 페이지에서 조사 선택</span><span class="sxs-lookup"><span data-stu-id="67724-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="67724-115">작업 센터에서 항목 선택</span><span class="sxs-lookup"><span data-stu-id="67724-115">Select an item in the Action center</span></span>

<span data-ttu-id="67724-116">작업 센터를 사용하여 승인이 보류 중이거나 (**보류 중인** 탭에서) 기승인 된 (**기록** 탭에서) 작업을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67724-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="67724-117">[https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="67724-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="67724-118">탐색 창에서 **작업 센터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67724-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="67724-119">**보류 중인** 또는 **기록** 탭에서 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67724-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="67724-120">[필수 권한이](mtp-action-center.md#required-permissions-for-action-center-tasks)있는 경우 보류 중인 작업을 승인(또는 거부) 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67724-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="67724-121">문제 세부정보 페이지에서 조사 오픈 </span><span class="sxs-lookup"><span data-stu-id="67724-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="67724-122">세부정보 페이지를 통해 알람 원인 장치, 사용자, 사서함 등 사건에 대한 세부 정보를 확인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="67724-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="67724-123">[https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="67724-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="67724-124">탐색 창에서 **사건** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67724-124">In the navigation pane, choose **Incidents**.</span></span> 

3. <span data-ttu-id="67724-125">목록에서 항목을 선택 하여 사건 세부정보 보기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="67724-125">Select an item in the list to open the incident details view.</span></span><br/>![사건 세부 정보](../../media/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="67724-127">**조사** 탭의 목록에서 조사를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67724-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="67724-128">조사 세부정보</span><span class="sxs-lookup"><span data-stu-id="67724-128">Investigation details</span></span>

<span data-ttu-id="67724-129">조사 세부정보 보기를 사용 하여 과거, 현재 및 보류 중인 활동을 확인하고 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="67724-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="67724-130">조사 세부정보 보기는 다음 이미지와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="67724-130">The investigation details view resembles the following image:</span></span>

![조사 세부정보](../../media/mtp-air-investdetails.png)

<span data-ttu-id="67724-132">조사 세부정보 보기에서 아래 테이블에 설명되어 있는 것 처럼 **조사 그래프**, **알람**, **장치**, **항목**, **주요 발견 사항**, **대상**, **로그** 및 **보류 활동** 을 확인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="67724-132">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

| <span data-ttu-id="67724-133">Tab</span><span class="sxs-lookup"><span data-stu-id="67724-133">Tab</span></span> | <span data-ttu-id="67724-134">설명</span><span class="sxs-lookup"><span data-stu-id="67724-134">Description</span></span> |
|--------|--------|
| <span data-ttu-id="67724-135">**조사 그래프**</span><span class="sxs-lookup"><span data-stu-id="67724-135">**Investigation graph**</span></span>   | <span data-ttu-id="67724-136">조사 내용이 시각적으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67724-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="67724-137">위협 대상과 목록 알람과 현재 활동이나 보류중인 활동을 보여줍니다. </span><span class="sxs-lookup"><span data-stu-id="67724-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="67724-138">그래프에서 항목을 클릭 하면 세부정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67724-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="67724-139">예를들어, **찾은 위협** 아이콘을 클릭하면 **주요 발견 사항** 으로 이동합니다. </span><span class="sxs-lookup"><span data-stu-id="67724-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
| <span data-ttu-id="67724-140">**알람**</span><span class="sxs-lookup"><span data-stu-id="67724-140">**Alerts**</span></span>    | <span data-ttu-id="67724-141">조사와 관련 된 알람목록을 보여줍니다. </span><span class="sxs-lookup"><span data-stu-id="67724-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="67724-142">경고는 사용자 컴퓨터의 위협 방지 기능, Office 앱, Cloud App Security 및 기타 Microsoft 365 Defender 기능에서 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67724-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="67724-143">**장치**</span><span class="sxs-lookup"><span data-stu-id="67724-143">**Devices**</span></span> | <span data-ttu-id="67724-144">재구성 수준과 함께 조사에 포함된 기기 목록을 보여줍니다. </span><span class="sxs-lookup"><span data-stu-id="67724-144">Lists machines included in the investigation along with remediation level.</span></span>|
| <span data-ttu-id="67724-145">**주요 발견 사항**</span><span class="sxs-lookup"><span data-stu-id="67724-145">**Key findings**</span></span>  | <span data-ttu-id="67724-146">검사 결과 및 상황, 활동 중이거나 보류중인 작업 목록을 보여줍니다. </span><span class="sxs-lookup"><span data-stu-id="67724-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="67724-147">이 탭에서 장치 빛 식별 보류 작업을 승인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="67724-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
| <span data-ttu-id="67724-148">**항목**</span><span class="sxs-lookup"><span data-stu-id="67724-148">**Entities**</span></span>  | <span data-ttu-id="67724-149">조사에 관련된 사용자 활동, 파일, 프로세스, 서비스, 드라이버, IP 주소 및 유지 방법과 함께 수행된 활동과 상태 목록을 보여줍니다. </span><span class="sxs-lookup"><span data-stu-id="67724-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="67724-150">**로그**</span><span class="sxs-lookup"><span data-stu-id="67724-150">**Log**</span></span>    | <span data-ttu-id="67724-151">조사 중에 수행된 모든 단계의 세부정보와 상태를 보여줍니다. </span><span class="sxs-lookup"><span data-stu-id="67724-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
| <span data-ttu-id="67724-152">**보류 중인 작업**</span><span class="sxs-lookup"><span data-stu-id="67724-152">**Pending actions**</span></span> | <span data-ttu-id="67724-153">진행 하려면 승인이 필요한 항목을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="67724-153">Lists items that require approval to proceed.</span></span>|

## <a name="next-steps"></a><span data-ttu-id="67724-154">다음 단계</span><span class="sxs-lookup"><span data-stu-id="67724-154">Next steps</span></span>

- [<span data-ttu-id="67724-155">자동화된 조사 및 대응과 관련된 조치 승인 또는 거부</span><span class="sxs-lookup"><span data-stu-id="67724-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="67724-156">재구성 작업 검토</span><span class="sxs-lookup"><span data-stu-id="67724-156">Review remediation actions</span></span>](mtp-remediation-actions.md)
