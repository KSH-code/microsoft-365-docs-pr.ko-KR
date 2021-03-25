---
title: 자동화된 조사의 세부 정보 및 결과
description: '자동화 조사가 진행 되는 동한 혹은 진행 완료된 후 주요 사항 및 결과를 확인할 수 있습니다. '
keywords: 자동화, 조사, 결과, 분속, 세부정보, 재구성, 오토에어
search.appverid: met150
ms.prod: m365-security
ms.technology: m365d
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
ms.date: 02/08/2021
ms.openlocfilehash: 05208dd8ba893d65db50430861ad5dd5ad9d34fb
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198972"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="429fe-104">자동화된 조사의 세부 정보 및 결과</span><span class="sxs-lookup"><span data-stu-id="429fe-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="429fe-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="429fe-105">**Applies to:**</span></span>
- <span data-ttu-id="429fe-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="429fe-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="429fe-107">Microsoft 365 Defender를 [](m365d-autoir.md) 통해 자동화된 조사가 실행되는 경우 자동화된 조사 프로세스 중 및 이후에 조사에 대한 세부 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-107">With Microsoft 365 Defender, when an [automated investigation](m365d-autoir.md) runs, details about that investigation are available both during and after the automated investigation process.</span></span> <span data-ttu-id="429fe-108">[필수 권한이](m365d-action-center.md#required-permissions-for-action-center-tasks)있는 경우 조사 세부 정보 보기에서 해당 정보를 확인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="429fe-108">If you have the [necessary permissions](m365d-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="429fe-109">조사 세부정부 보기에서 최신 상태를 확인하거나 보류중인 작업을 승인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![조사 세부정보](../../media/mtp-air-investdetails.png)

## <a name="new-unified-investigation-page"></a><span data-ttu-id="429fe-111">(NEW!) 통합 조사 페이지</span><span class="sxs-lookup"><span data-stu-id="429fe-111">(NEW!) Unified investigation page</span></span>

<span data-ttu-id="429fe-112">조사 페이지가 최근에 장치, 전자 메일 및 공동 작업 콘텐츠에 대한 정보를 포함하기 위해 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-112">The investigation page has recently been updated to include information across your devices, email, and collaboration content.</span></span> <span data-ttu-id="429fe-113">새로운 통합 조사 페이지는 공통 언어를 정의하고 [끝점용 Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 및 [Office 365용 Microsoft Defender에서](../office-365-security/defender-for-office-365.md)자동 조사를 위한 통합된 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-113">The new, unified investigation page defines a common language and provides a unified experience for automatic investigations across [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) and [Microsoft Defender for Office 365](../office-365-security/defender-for-office-365.md).</span></span> <span data-ttu-id="429fe-114">통합 조사 페이지에 액세스하려면 노란색 배너의 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-114">To access the unified investigation page, select the link in the yellow banner you'll see on:</span></span>
- <span data-ttu-id="429fe-115">Office 365 보안 및 준수 센터의 & 페이지( [https://protection.office.com](https://protection.office.com) )</span><span class="sxs-lookup"><span data-stu-id="429fe-115">Any investigation page in the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span>
- <span data-ttu-id="429fe-116">Microsoft Defender 보안 센터의 모든 조사 페이지( [https://securitycenter.windows.com](https://securitycenter.windows.com) )</span><span class="sxs-lookup"><span data-stu-id="429fe-116">Any investigation page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com))</span></span>
- <span data-ttu-id="429fe-117">개선된 Microsoft 365 보안 센터의 인시던트 또는 관리 센터 환경( [https://security.microsoft.com](https://security.microsoft.com) )</span><span class="sxs-lookup"><span data-stu-id="429fe-117">Any incident or Action center experience in the improved Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com))</span></span>

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="429fe-118">조사 세부정보 보기 열기 </span><span class="sxs-lookup"><span data-stu-id="429fe-118">Open the investigation details view</span></span>

<span data-ttu-id="429fe-119">다음 방법 중 하나를 사용 하여 조사 세부정보 보기를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-119">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="429fe-120">작업 센터에서 항목 선택</span><span class="sxs-lookup"><span data-stu-id="429fe-120">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="429fe-121">문제 세부정보 페이지에서 조사 선택</span><span class="sxs-lookup"><span data-stu-id="429fe-121">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="429fe-122">작업 센터에서 항목 선택</span><span class="sxs-lookup"><span data-stu-id="429fe-122">Select an item in the Action center</span></span>

<span data-ttu-id="429fe-123">향상된 [알림](m365d-action-center.md) 센터( )는 장치, 전자 메일 및 공동 작업 콘텐츠 및 id에 & 조치를 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 제공합니다. [](m365d-remediation-actions.md)</span><span class="sxs-lookup"><span data-stu-id="429fe-123">The improved [Action center](m365d-action-center.md) ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) brings together [remediation actions](m365d-remediation-actions.md) across your devices, email & collaboration content, and identities.</span></span> <span data-ttu-id="429fe-124">나열된 작업에는 자동으로 또는 수동으로 수행된 수정 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-124">Listed actions include remediation actions that were taken automatically or manually.</span></span> <span data-ttu-id="429fe-125">작업 센터에서 승인을 대기하는 작업과 이미 승인되거나 완료된 작업을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-125">In the Action center, you can view actions that are awaiting approval and actions that were already approved or completed.</span></span> <span data-ttu-id="429fe-126">조사 페이지와 같은 자세한 정보로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-126">You can also navigate to more details, such as an investigation page.</span></span>

> [!TIP]
> <span data-ttu-id="429fe-127">작업을 [승인,](m365d-action-center.md#required-permissions-for-action-center-tasks) 거부 또는 취소하려면 특정 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-127">You must have [certain permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve, reject, or undo actions.</span></span>

1. <span data-ttu-id="429fe-128">[https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-128">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="429fe-129">탐색 창에서 **작업 센터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-129">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="429fe-130">**보류 중인** 또는 **기록** 탭에서 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-130">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="429fe-131">플라이아웃 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-131">Its flyout pane opens.</span></span>
4. <span data-ttu-id="429fe-132">플라이아웃 창의 정보를 검토한 후 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-132">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="429fe-133">조사에 대한 자세한 내용을 **확인하려면** 조사 페이지 열기 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-133">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="429fe-134">**승인을** 선택하여 보류 중인 작업을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-134">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="429fe-135">보류 **중인** 작업이 수행되지 않도록 방지하려면 거부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-135">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="429fe-136">이동을 **선택하여** 고급 헌팅으로 [이동합니다.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="429fe-136">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="429fe-137">문제 세부정보 페이지에서 조사 오픈 </span><span class="sxs-lookup"><span data-stu-id="429fe-137">Open an investigation from an incident details page</span></span>

<span data-ttu-id="429fe-138">세부정보 페이지를 통해 알람 원인 장치, 사용자, 사서함 등 사건에 대한 세부 정보를 확인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="429fe-138">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

![사건 세부 정보](../../media/mtp-incidentdetails-tabs.png)

1. <span data-ttu-id="429fe-140">[https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-140">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="429fe-141">탐색 창에서 인시던트 및 **인시던트**&  >  **를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="429fe-141">In the navigation pane, choose **Incidents & alerts** > **Incidents**.</span></span> 
3. <span data-ttu-id="429fe-142">목록에서 항목을 선택한 다음 문제 페이지 **열기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="429fe-142">Select an item in the list, and then choose **Open incident page**.</span></span>
4. <span data-ttu-id="429fe-143">조사 **탭을** 선택한 다음 목록에서 조사를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-143">Select the **Investigations** tab, and then select an investigation in the list.</span></span> <span data-ttu-id="429fe-144">플라이아웃 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-144">Its flyout pane opens.</span></span>
5. <span data-ttu-id="429fe-145">조사 **페이지 열기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="429fe-145">Select **Open investigation page**.</span></span> 

## <a name="investigation-details"></a><span data-ttu-id="429fe-146">조사 세부정보</span><span class="sxs-lookup"><span data-stu-id="429fe-146">Investigation details</span></span>

<span data-ttu-id="429fe-147">조사 세부정보 보기를 사용 하여 과거, 현재 및 보류 중인 활동을 확인하고 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-147">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="429fe-148">조사 세부정보 보기는 다음 이미지와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-148">The investigation details view resembles the following image:</span></span>

![조사 세부정보](../../media/mtp-air-investdetails.png)

<span data-ttu-id="429fe-150">조사 세부정보 보기에서 아래 테이블에 설명되어 있는 것 처럼 **조사 그래프**, **알람**, **장치**, **항목**, **주요 발견 사항**, **대상**, **로그** 및 **보류 활동** 을 확인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="429fe-150">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="429fe-151">조사 세부 정보 페이지에 볼 수 있는 특정 탭은 구독에 포함된 내용에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-151">The specific tabs you see in an investigation details page depends on what your subscription includes.</span></span> <span data-ttu-id="429fe-152">예를 들어 구독에 Office 365 계획 2용 Microsoft Defender가 포함되어 있지 않은 경우 사서함 탭이 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="429fe-152">For example, if your subscription does not include Microsoft Defender for Office 365 Plan 2, you won't see a **Mailboxes** tab.</span></span>

| <span data-ttu-id="429fe-153">Tab</span><span class="sxs-lookup"><span data-stu-id="429fe-153">Tab</span></span> | <span data-ttu-id="429fe-154">설명</span><span class="sxs-lookup"><span data-stu-id="429fe-154">Description</span></span> |
|:--------|:--------|
| <span data-ttu-id="429fe-155">**조사 그래프**</span><span class="sxs-lookup"><span data-stu-id="429fe-155">**Investigation graph**</span></span>   | <span data-ttu-id="429fe-156">조사 내용이 시각적으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-156">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="429fe-157">위협 대상과 목록 알람과 현재 활동이나 보류중인 활동을 보여줍니다. </span><span class="sxs-lookup"><span data-stu-id="429fe-157">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="429fe-158">그래프에서 항목을 선택하여 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-158">You can select an item on the graph to view more details.</span></span> <span data-ttu-id="429fe-159">예를 들어 증거  아이콘을 선택하면 검색된 엔터티와 해당 판정을 볼 수 있는 증거 탭으로 이동됩니다. </span><span class="sxs-lookup"><span data-stu-id="429fe-159">For example, selecting the **Evidence** icon takes you to the **Evidence** tab, where you can see detected entities and their verdicts.</span></span> |
| <span data-ttu-id="429fe-160">**알람**</span><span class="sxs-lookup"><span data-stu-id="429fe-160">**Alerts**</span></span>    | <span data-ttu-id="429fe-161">조사와 관련 된 알람목록을 보여줍니다. </span><span class="sxs-lookup"><span data-stu-id="429fe-161">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="429fe-162">경고는 사용자 장치의 위협 방지 기능, Office 앱, Cloud App Security 및 기타 Microsoft 365 Defender 기능에서 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-162">Alerts can come from threat protection features on a user's device, in Office apps, Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="429fe-163">**장치**</span><span class="sxs-lookup"><span data-stu-id="429fe-163">**Devices**</span></span> | <span data-ttu-id="429fe-164">조사에 포함된 장치를 수정 수준과 함께 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-164">Lists devices included in the investigation along with their remediation level.</span></span> <span data-ttu-id="429fe-165">재구성 수준은 장치 그룹의 [자동화 수준에 해당합니다.](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)</span><span class="sxs-lookup"><span data-stu-id="429fe-165">(Remediation levels correspond to [the automation level for device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups).)</span></span> |
| <span data-ttu-id="429fe-166">**사서함**</span><span class="sxs-lookup"><span data-stu-id="429fe-166">**Mailboxes**</span></span> |<span data-ttu-id="429fe-167">검색된 위협의 영향을 받는 사서함을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-167">Lists mailboxes that are impacted by detected threats.</span></span>  |
| <span data-ttu-id="429fe-168">**사용자**</span><span class="sxs-lookup"><span data-stu-id="429fe-168">**Users**</span></span>  | <span data-ttu-id="429fe-169">검색된 위협의 영향을 미치는 사용자 계정을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-169">Lists user accounts that are impacted by detected threats.</span></span> |
| <span data-ttu-id="429fe-170">**증거**</span><span class="sxs-lookup"><span data-stu-id="429fe-170">**Evidence**</span></span> | <span data-ttu-id="429fe-171">경고/조사에서 제기된 증거 조각을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-171">Lists pieces of evidence raised by alerts/investigations.</span></span> <span data-ttu-id="429fe-172">*판정(악성,* *의심스러운* 또는 위협 *없음)* 및 수정 상태를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-172">Includes verdicts (*Malicious*, *Suspicious*, or *No threats found*) and remediation status.</span></span> |
| <span data-ttu-id="429fe-173">**항목**</span><span class="sxs-lookup"><span data-stu-id="429fe-173">**Entities**</span></span>  | <span data-ttu-id="429fe-174">각 엔터티 유형(악성, 의심스러운 또는 위협이 없음)에 대한 판정을 포함하여 분석된 각 엔터티에 대한 세부 *정보를 제공합니다.* </span><span class="sxs-lookup"><span data-stu-id="429fe-174">Provides details about each analyzed entity, including a verdict for each entity type (*Malicious*, *Suspicious*, or *No threats found*).</span></span>|
|<span data-ttu-id="429fe-175">**로그**</span><span class="sxs-lookup"><span data-stu-id="429fe-175">**Log**</span></span>    | <span data-ttu-id="429fe-176">경고가 트리거된 후 수행된 모든 조사 작업을 연대적으로 상세하게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-176">Provides a chronological, detailed view of all the investigation actions taken after an alert was triggered.</span></span>|
| <span data-ttu-id="429fe-177">**보류 중인 작업**</span><span class="sxs-lookup"><span data-stu-id="429fe-177">**Pending actions**</span></span> | <span data-ttu-id="429fe-178">진행 하려면 승인이 필요한 항목을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-178">Lists items that require approval to proceed.</span></span> <span data-ttu-id="429fe-179">작업 센터()로 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 이동하여 보류 중인 작업을 승인합니다.</span><span class="sxs-lookup"><span data-stu-id="429fe-179">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) to approve pending actions.</span></span> |

## <a name="next-steps"></a><span data-ttu-id="429fe-180">다음 단계</span><span class="sxs-lookup"><span data-stu-id="429fe-180">Next steps</span></span>

- [<span data-ttu-id="429fe-181">자동화된 조사 후 수정 작업 승인 또는 거부</span><span class="sxs-lookup"><span data-stu-id="429fe-181">Approve or reject remediation actions following an automated investigation</span></span>](m365d-autoir-actions.md)
- [<span data-ttu-id="429fe-182">수정 작업에 대해 자세히 알아보시다</span><span class="sxs-lookup"><span data-stu-id="429fe-182">Learn more about remediation actions</span></span>](m365d-remediation-actions.md)
