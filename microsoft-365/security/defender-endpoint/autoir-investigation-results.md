---
title: 자동화된 조사의 세부 정보 및 결과
description: '자동화 조사가 진행 되는 동한 혹은 진행 완료된 후 주요 사항 및 결과를 확인할 수 있습니다. '
keywords: 자동화, 조사, 결과, 분속, 세부정보, 재구성, 오토에어
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 02/02/2021
ms.openlocfilehash: c11d9cd1ce4c2ca49315ec62b51c23ef981555f4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075364"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="36842-104">자동화된 조사의 세부 정보 및 결과</span><span class="sxs-lookup"><span data-stu-id="36842-104">Details and results of an automated investigation</span></span>

<span data-ttu-id="36842-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="36842-105">**Applies to:**</span></span>
- <span data-ttu-id="36842-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="36842-106">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="36842-107">끝점용 Microsoft Defender를 [](automated-investigations.md) 통해 자동화된 조사가 실행되는 경우 자동화된 조사 프로세스 중 및 이후에 조사에 대한 세부 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36842-107">With Microsoft Defender for Endpoint, when an [automated investigation](automated-investigations.md) runs, details about that investigation are available both during and after the automated investigation process.</span></span> <span data-ttu-id="36842-108">필수 권한이있는 경우 조사 세부 정보 보기에서 해당 정보를 확인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="36842-108">If you have the necessary permissions, you can view those details in an investigation details view.</span></span> <span data-ttu-id="36842-109">조사 세부정부 보기에서 최신 상태를 확인하거나 보류중인 작업을 승인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36842-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

## <a name="new-unified-investigation-page"></a><span data-ttu-id="36842-110">(NEW!) 통합 조사 페이지</span><span class="sxs-lookup"><span data-stu-id="36842-110">(NEW!) Unified investigation page</span></span>

<span data-ttu-id="36842-111">조사 페이지가 최근에 장치, 전자 메일 및 공동 작업 콘텐츠에 대한 정보를 포함하기 위해 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="36842-111">The investigation page has recently been updated to include information across your devices, email, and collaboration content.</span></span> <span data-ttu-id="36842-112">새로운 통합 조사 페이지는 공통 언어를 정의하고 [끝점용 Microsoft Defender](microsoft-defender-advanced-threat-protection.md)  및 [Office 365용 Microsoft Defender에서](/microsoft-365/security/defender-365-security/office-365-atp)자동 조사를 위한 통합된 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="36842-112">The new, unified investigation page defines a common language and provides a unified experience for automatic investigations across [Microsoft Defender for Endpoint](microsoft-defender-advanced-threat-protection.md)  and [Microsoft Defender for Office 365](/microsoft-365/security/defender-365-security/office-365-atp).</span></span> 

> [!TIP]
> <span data-ttu-id="36842-113">변경에 대한 자세한 내용은 [(NEW!)를 참조하세요. 통합 조사 페이지.](/microsoft-365/security/mtp/mtp-autoir-results)</span><span class="sxs-lookup"><span data-stu-id="36842-113">To learn more about what's changing, see [(NEW!) Unified investigation page](/microsoft-365/security/mtp/mtp-autoir-results).</span></span>

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="36842-114">조사 세부정보 보기 열기 </span><span class="sxs-lookup"><span data-stu-id="36842-114">Open the investigation details view</span></span>

<span data-ttu-id="36842-115">다음 방법 중 하나를 사용 하여 조사 세부정보 보기를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36842-115">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="36842-116">작업 센터에서 항목 선택</span><span class="sxs-lookup"><span data-stu-id="36842-116">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="36842-117">문제 세부정보 페이지에서 조사 선택</span><span class="sxs-lookup"><span data-stu-id="36842-117">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="36842-118">작업 센터에서 항목 선택</span><span class="sxs-lookup"><span data-stu-id="36842-118">Select an item in the Action center</span></span>

<span data-ttu-id="36842-119">향상된 [알림](auto-investigation-action-center.md) 센터는 [](manage-auto-investigation.md#remediation-actions) 장치, 전자 메일 및 공동 작업 콘텐츠 및 & 수정 작업을 함께 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="36842-119">The improved [Action center](auto-investigation-action-center.md) brings together [remediation actions](manage-auto-investigation.md#remediation-actions) across your devices, email & collaboration content, and identities.</span></span> <span data-ttu-id="36842-120">나열된 작업에는 자동으로 또는 수동으로 수행된 수정 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="36842-120">Listed actions include remediation actions that were taken automatically or manually.</span></span> <span data-ttu-id="36842-121">작업 센터에서 승인을 대기하는 작업과 이미 승인되거나 완료된 작업을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36842-121">In the Action center, you can view actions that are awaiting approval and actions that were already approved or completed.</span></span> <span data-ttu-id="36842-122">조사 페이지와 같은 자세한 정보로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36842-122">You can also navigate to more details, such as an investigation page.</span></span>

1. <span data-ttu-id="36842-123">[https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="36842-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="36842-124">탐색 창에서 **작업 센터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="36842-124">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="36842-125">**보류 중인** 또는 **기록** 탭에서 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="36842-125">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="36842-126">플라이아웃 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="36842-126">Its flyout pane opens.</span></span>
4. <span data-ttu-id="36842-127">플라이아웃 창의 정보를 검토한 후 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="36842-127">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="36842-128">조사에 대한 자세한 내용을 **확인하려면** 조사 페이지 열기 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="36842-128">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="36842-129">**승인을** 선택하여 보류 중인 작업을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="36842-129">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="36842-130">보류 **중인** 작업이 수행되지 않도록 방지하려면 거부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="36842-130">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="36842-131">이동을 **선택하여** 고급 헌팅으로 [이동합니다.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="36842-131">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="36842-132">문제 세부정보 페이지에서 조사 오픈 </span><span class="sxs-lookup"><span data-stu-id="36842-132">Open an investigation from an incident details page</span></span>

<span data-ttu-id="36842-133">세부정보 페이지를 통해 알람 원인 장치, 사용자, 사서함 등 사건에 대한 세부 정보를 확인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="36842-133">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="36842-134">[https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="36842-134">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="36842-135">탐색 창에서 인시던트 및 **인시던트**&  >  **를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="36842-135">In the navigation pane, choose **Incidents & alerts** > **Incidents**.</span></span> 
3. <span data-ttu-id="36842-136">목록에서 항목을 선택한 다음 문제 페이지 **열기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="36842-136">Select an item in the list, and then choose **Open incident page**.</span></span>
4. <span data-ttu-id="36842-137">조사 **탭을** 선택한 다음 목록에서 조사를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="36842-137">Select the **Investigations** tab, and then select an investigation in the list.</span></span> <span data-ttu-id="36842-138">플라이아웃 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="36842-138">Its flyout pane opens.</span></span>
5. <span data-ttu-id="36842-139">조사 **페이지 열기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="36842-139">Select **Open investigation page**.</span></span> 

## <a name="investigation-details"></a><span data-ttu-id="36842-140">조사 세부정보</span><span class="sxs-lookup"><span data-stu-id="36842-140">Investigation details</span></span>

<span data-ttu-id="36842-141">조사 세부정보 보기를 사용 하여 과거, 현재 및 보류 중인 활동을 확인하고 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="36842-141">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="36842-142">조사 세부정보 보기는 다음 이미지와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="36842-142">The investigation details view resembles the following image:</span></span>

<span data-ttu-id="36842-143">조사 세부정보 보기에서 아래 테이블에 설명되어 있는 것 처럼 **조사 그래프**, **알람**, **장치**, **항목**, **주요 발견 사항**, **대상**, **로그** 및 **보류 활동** 을 확인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="36842-143">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="36842-144">조사 세부 정보 페이지에 볼 수 있는 특정 탭은 구독에 포함된 내용에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36842-144">The specific tabs you see in an investigation details page depends on what your subscription includes.</span></span> <span data-ttu-id="36842-145">예를 들어 구독에 Office 365 계획 2용 Microsoft Defender가 포함되어 있지 않은 경우 사서함 탭이 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="36842-145">For example, if your subscription does not include Microsoft Defender for Office 365 Plan 2, you won't see a **Mailboxes** tab.</span></span>

| <span data-ttu-id="36842-146">Tab</span><span class="sxs-lookup"><span data-stu-id="36842-146">Tab</span></span> | <span data-ttu-id="36842-147">설명</span><span class="sxs-lookup"><span data-stu-id="36842-147">Description</span></span> |
|:--------|:--------|
| <span data-ttu-id="36842-148">**조사 그래프**</span><span class="sxs-lookup"><span data-stu-id="36842-148">**Investigation graph**</span></span>   | <span data-ttu-id="36842-149">조사 내용이 시각적으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36842-149">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="36842-150">위협 대상과 목록 알람과 현재 활동이나 보류중인 활동을 보여줍니다. </span><span class="sxs-lookup"><span data-stu-id="36842-150">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="36842-151">그래프에서 항목을 선택하여 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36842-151">You can select an item on the graph to view more details.</span></span> <span data-ttu-id="36842-152">예를 들어 증거  아이콘을 선택하면 검색된 엔터티와 해당 판정을 볼 수 있는 증거 탭으로 이동됩니다. </span><span class="sxs-lookup"><span data-stu-id="36842-152">For example, selecting the **Evidence** icon takes you to the **Evidence** tab, where you can see detected entities and their verdicts.</span></span> |
| <span data-ttu-id="36842-153">**알람**</span><span class="sxs-lookup"><span data-stu-id="36842-153">**Alerts**</span></span>    | <span data-ttu-id="36842-154">조사와 관련 된 알람목록을 보여줍니다. </span><span class="sxs-lookup"><span data-stu-id="36842-154">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="36842-155">경고는 사용자 장치의 위협 방지 기능, Office 앱, Cloud App Security 및 기타 Microsoft 365 Defender 기능에서 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36842-155">Alerts can come from threat protection features on a user's device, in Office apps, Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="36842-156">**장치**</span><span class="sxs-lookup"><span data-stu-id="36842-156">**Devices**</span></span> | <span data-ttu-id="36842-157">조사에 포함된 장치를 수정 수준과 함께 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="36842-157">Lists devices included in the investigation along with their remediation level.</span></span> <span data-ttu-id="36842-158">재구성 수준은 장치 그룹의 [자동화 수준에 해당합니다.](automation-levels.md)</span><span class="sxs-lookup"><span data-stu-id="36842-158">(Remediation levels correspond to the [automation level for device groups](automation-levels.md).)</span></span> |
| <span data-ttu-id="36842-159">**사서함**</span><span class="sxs-lookup"><span data-stu-id="36842-159">**Mailboxes**</span></span> |<span data-ttu-id="36842-160">검색된 위협의 영향을 받는 사서함을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="36842-160">Lists mailboxes that are impacted by detected threats.</span></span>  |
| <span data-ttu-id="36842-161">**사용자**</span><span class="sxs-lookup"><span data-stu-id="36842-161">**Users**</span></span>  | <span data-ttu-id="36842-162">검색된 위협의 영향을 미치는 사용자 계정을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="36842-162">Lists user accounts that are impacted by detected threats.</span></span> |
| <span data-ttu-id="36842-163">**증거**</span><span class="sxs-lookup"><span data-stu-id="36842-163">**Evidence**</span></span> | <span data-ttu-id="36842-164">경고/조사에서 제기된 증거 조각을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="36842-164">Lists pieces of evidence raised by alerts/investigations.</span></span> <span data-ttu-id="36842-165">*판정(악성,* *의심스러운* 또는 위협 *없음)* 및 수정 상태를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="36842-165">Includes verdicts (*Malicious*, *Suspicious*, or *No threats found*) and remediation status.</span></span> |
| <span data-ttu-id="36842-166">**항목**</span><span class="sxs-lookup"><span data-stu-id="36842-166">**Entities**</span></span>  | <span data-ttu-id="36842-167">각 엔터티 유형(악성, 의심스러운 또는 위협이 없음)에 대한 판정을 포함하여 분석된 각 엔터티에 대한 세부 *정보를 제공합니다.* </span><span class="sxs-lookup"><span data-stu-id="36842-167">Provides details about each analyzed entity, including a verdict for each entity type (*Malicious*, *Suspicious*, or *No threats found*).</span></span>|
|<span data-ttu-id="36842-168">**로그**</span><span class="sxs-lookup"><span data-stu-id="36842-168">**Log**</span></span>    | <span data-ttu-id="36842-169">경고가 트리거된 후 수행된 모든 조사 작업을 연대적으로 상세하게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36842-169">Provides a chronological, detailed view of all the investigation actions taken after an alert was triggered.</span></span>|
| <span data-ttu-id="36842-170">**보류 중인 작업**</span><span class="sxs-lookup"><span data-stu-id="36842-170">**Pending actions**</span></span> | <span data-ttu-id="36842-171">진행 하려면 승인이 필요한 항목을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="36842-171">Lists items that require approval to proceed.</span></span> <span data-ttu-id="36842-172">작업 센터()로 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 이동하여 보류 중인 작업을 승인합니다.</span><span class="sxs-lookup"><span data-stu-id="36842-172">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) to approve pending actions.</span></span> |

## <a name="see-also"></a><span data-ttu-id="36842-173">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36842-173">See also</span></span>

- [<span data-ttu-id="36842-174">자동화된 조사 후 수정 작업 검토</span><span class="sxs-lookup"><span data-stu-id="36842-174">Review remediation actions following an automated investigation</span></span>](manage-auto-investigation.md)
- [<span data-ttu-id="36842-175">끝점 인시던트에 대한 Microsoft Defender 큐 보기 및 구성</span><span class="sxs-lookup"><span data-stu-id="36842-175">View and organize the Microsoft Defender for Endpoint Incidents queue</span></span>](view-incidents-queue.md)