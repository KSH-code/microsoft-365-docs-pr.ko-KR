---
title: 자동화된 조사의 세부 정보 및 결과
description: 2013에서 자동화된 조사의 결과와 주요 결과를 Microsoft 365 Defender
keywords: 자동화, 조사, 결과, 분속, 세부정보, 재구성, 오토에어
search.appverid: met150
ms.prod: m365-security
ms.technology: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: 2cc83e24d4dd81c9d2e972fa274b48fc3946532a
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289730"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="9af29-104">자동화된 조사의 세부 정보 및 결과</span><span class="sxs-lookup"><span data-stu-id="9af29-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="9af29-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="9af29-105">**Applies to:**</span></span>
- <span data-ttu-id="9af29-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9af29-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9af29-107">이 Microsoft 365 Defender 자동화된 조사가 실행되는 경우 자동화된 조사 프로세스 중 및 이후에 조사에 대한 세부 정보를 사용할 수 있습니다. [](m365d-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="9af29-107">With Microsoft 365 Defender, when an [automated investigation](m365d-autoir.md) runs, details about that investigation are available both during and after the automated investigation process.</span></span> <span data-ttu-id="9af29-108">[필수 권한이](m365d-action-center.md#required-permissions-for-action-center-tasks)있는 경우 조사 세부 정보 보기에서 해당 정보를 확인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="9af29-108">If you have the [necessary permissions](m365d-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="9af29-109">이 보기는 최신 상태 및 보류 중인 작업을 승인하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-109">This view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

:::image type="content" source="../../media/mtp-air-investdetails.png" alt-text="조사 세부정보":::

## <a name="new-unified-investigation-page"></a><span data-ttu-id="9af29-111">(NEW!) 통합 조사 페이지</span><span class="sxs-lookup"><span data-stu-id="9af29-111">(NEW!) Unified investigation page</span></span>

<span data-ttu-id="9af29-112">조사 페이지가 최근에 장치, 전자 메일 및 공동 작업 콘텐츠에 대한 정보를 포함하기 위해 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-112">The investigation page has recently been updated to include information across your devices, email, and collaboration content.</span></span> <span data-ttu-id="9af29-113">새로운 통합 조사 페이지는 공통 언어를 정의하고 끝점용 [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 및 Microsoft [Defender](../office-365-security/defender-for-office-365.md)for Office 365.</span><span class="sxs-lookup"><span data-stu-id="9af29-113">The new, unified investigation page defines a common language and provides a unified experience for automatic investigations across [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) and [Microsoft Defender for Office 365](../office-365-security/defender-for-office-365.md).</span></span> <span data-ttu-id="9af29-114">통합 조사 페이지에 액세스하려면 노란색 배너의 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-114">To access the unified investigation page, select the link in the yellow banner you'll see on:</span></span>

- <span data-ttu-id="9af29-115">Office 365 보안 및 준수 센터의 & 페이지( [https://protection.office.com](https://protection.office.com) )</span><span class="sxs-lookup"><span data-stu-id="9af29-115">Any investigation page in the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span>
- <span data-ttu-id="9af29-116">2016의 모든 조사 Microsoft Defender 보안 센터( [https://securitycenter.windows.com](https://securitycenter.windows.com) )</span><span class="sxs-lookup"><span data-stu-id="9af29-116">Any investigation page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com))</span></span>
- <span data-ttu-id="9af29-117">Microsoft 365 Defender 포털의 모든 인시던트 또는 Microsoft 365 Defender 센터 [https://security.microsoft.com](https://security.microsoft.com) 환경( )</span><span class="sxs-lookup"><span data-stu-id="9af29-117">Any incident or Action center experience in the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com))</span></span>

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="9af29-118">조사 세부정보 보기 열기 </span><span class="sxs-lookup"><span data-stu-id="9af29-118">Open the investigation details view</span></span>

<span data-ttu-id="9af29-119">다음 방법 중 하나를 사용 하여 조사 세부정보 보기를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-119">You can open the investigation details view by using one of the following methods:</span></span>

- [<span data-ttu-id="9af29-120">작업 센터에서 항목 선택</span><span class="sxs-lookup"><span data-stu-id="9af29-120">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="9af29-121">문제 세부정보 페이지에서 조사 선택</span><span class="sxs-lookup"><span data-stu-id="9af29-121">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="9af29-122">작업 센터에서 항목 선택</span><span class="sxs-lookup"><span data-stu-id="9af29-122">Select an item in the Action center</span></span>

<span data-ttu-id="9af29-123">향상된 [알림](m365d-action-center.md) 센터( )는 장치, 전자 메일 및 공동 작업 콘텐츠 및 id에 & 조치를 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 제공합니다. [](m365d-remediation-actions.md)</span><span class="sxs-lookup"><span data-stu-id="9af29-123">The improved [Action center](m365d-action-center.md) ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) brings together [remediation actions](m365d-remediation-actions.md) across your devices, email & collaboration content, and identities.</span></span> <span data-ttu-id="9af29-124">나열된 작업에는 자동으로 또는 수동으로 수행된 수정 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-124">Listed actions include remediation actions that were taken automatically or manually.</span></span> <span data-ttu-id="9af29-125">작업 센터에서 승인을 대기하는 작업과 이미 승인되거나 완료된 작업을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-125">In the Action center, you can view actions that are awaiting approval and actions that were already approved or completed.</span></span> <span data-ttu-id="9af29-126">조사 페이지와 같은 자세한 정보로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-126">You can also navigate to more details, such as an investigation page.</span></span>

> [!TIP]
> <span data-ttu-id="9af29-127">작업을 [승인,](m365d-action-center.md#required-permissions-for-action-center-tasks) 거부 또는 취소하려면 특정 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-127">You must have [certain permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve, reject, or undo actions.</span></span>

1. <span data-ttu-id="9af29-128">[https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-128">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="9af29-129">탐색 창에서 **작업 센터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-129">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="9af29-130">**보류 중인** 또는 **기록** 탭에서 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-130">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="9af29-131">플라이아웃 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-131">Its flyout pane opens.</span></span>

4. <span data-ttu-id="9af29-132">플라이아웃 창의 정보를 검토한 후 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-132">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="9af29-133">조사에 대한 자세한 내용을 **확인하려면** 조사 페이지 열기 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-133">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="9af29-134">**승인을** 선택하여 보류 중인 작업을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-134">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="9af29-135">보류 **중인** 작업이 수행되지 않도록 방지하려면 거부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-135">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="9af29-136">이동을 **선택하여** 고급 헌팅으로 [이동합니다.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9af29-136">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="9af29-137">문제 세부정보 페이지에서 조사 오픈 </span><span class="sxs-lookup"><span data-stu-id="9af29-137">Open an investigation from an incident details page</span></span>

<span data-ttu-id="9af29-138">세부정보 페이지를 통해 알람 원인 장치, 사용자, 사서함 등 사건에 대한 세부 정보를 확인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="9af29-138">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="9af29-139">[https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-139">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="9af29-140">탐색 창에서 인시던트 및 **인시던트**&  >  **를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="9af29-140">In the navigation pane, choose **Incidents & alerts** > **Incidents**.</span></span> 

3. <span data-ttu-id="9af29-141">목록에서 항목을 선택한 다음 문제 페이지 **열기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9af29-141">Select an item in the list, and then choose **Open incident page**.</span></span>

4. <span data-ttu-id="9af29-142">조사 **탭을** 선택한 다음 목록에서 조사를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-142">Select the **Investigations** tab, and then select an investigation in the list.</span></span> <span data-ttu-id="9af29-143">플라이아웃 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-143">Its flyout pane opens.</span></span>

5. <span data-ttu-id="9af29-144">조사 **페이지 열기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9af29-144">Select **Open investigation page**.</span></span> 

<span data-ttu-id="9af29-145">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-145">Here's an example.</span></span>

:::image type="content" source="../../media/mtp-incidentdetails-tabs.png" alt-text="사건 세부 정보":::

## <a name="investigation-details"></a><span data-ttu-id="9af29-147">조사 세부정보</span><span class="sxs-lookup"><span data-stu-id="9af29-147">Investigation details</span></span>

<span data-ttu-id="9af29-148">조사 세부정보 보기를 사용 하여 과거, 현재 및 보류 중인 활동을 확인하고 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-148">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="9af29-149">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-149">Here's an example.</span></span>

:::image type="content" source="../../media/mtp-air-investdetails.png" alt-text="조사 세부정보":::

<span data-ttu-id="9af29-151">조사 세부정보 보기에서 아래 테이블에 설명되어 있는 것 처럼 **조사 그래프**, **알람**, **장치**, **항목**, **주요 발견 사항**, **대상**, **로그** 및 **보류 활동** 을 확인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="9af29-151">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="9af29-152">조사 세부 정보 페이지에 볼 수 있는 특정 탭은 구독에 포함된 내용에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-152">The specific tabs you see in an investigation details page depends on what your subscription includes.</span></span> <span data-ttu-id="9af29-153">예를 들어 구독에 Office 365 요금제 2에 대한 Microsoft Defender가 포함되어 있지 않은 경우 사서함 탭이 **표시되지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-153">For example, if your subscription does not include Microsoft Defender for Office 365 Plan 2, you won't see a **Mailboxes** tab.</span></span>

| <span data-ttu-id="9af29-154">Tab</span><span class="sxs-lookup"><span data-stu-id="9af29-154">Tab</span></span> | <span data-ttu-id="9af29-155">설명</span><span class="sxs-lookup"><span data-stu-id="9af29-155">Description</span></span> |
|:--------|:--------|
| <span data-ttu-id="9af29-156">**조사 그래프**</span><span class="sxs-lookup"><span data-stu-id="9af29-156">**Investigation graph**</span></span> | <span data-ttu-id="9af29-157">조사 내용이 시각적으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-157">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="9af29-158">위협 대상과 목록 알람과 현재 활동이나 보류중인 활동을 보여줍니다. </span><span class="sxs-lookup"><span data-stu-id="9af29-158">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="9af29-159">그래프에서 항목을 선택하여 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-159">You can select an item on the graph to view more details.</span></span> <span data-ttu-id="9af29-160">예를 들어 증거  아이콘을 선택하면 검색된 엔터티와 해당 판정을 볼 수 있는 증거 탭으로 이동됩니다. </span><span class="sxs-lookup"><span data-stu-id="9af29-160">For example, selecting the **Evidence** icon takes you to the **Evidence** tab, where you can see detected entities and their verdicts.</span></span> |
| <span data-ttu-id="9af29-161">**알람**</span><span class="sxs-lookup"><span data-stu-id="9af29-161">**Alerts**</span></span> | <span data-ttu-id="9af29-162">조사와 관련 된 알람목록을 보여줍니다. </span><span class="sxs-lookup"><span data-stu-id="9af29-162">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="9af29-163">경고는 사용자 장치의 위협 방지 기능, Office, 앱 및 기타 Microsoft Cloud App Security 기능에서 Microsoft 365 Defender 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-163">Alerts can come from threat protection features on a user's device, in Office apps, Microsoft Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="9af29-164">**장치**</span><span class="sxs-lookup"><span data-stu-id="9af29-164">**Devices**</span></span> | <span data-ttu-id="9af29-165">조사에 포함된 장치를 수정 수준과 함께 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-165">Lists devices included in the investigation along with their remediation level.</span></span> <span data-ttu-id="9af29-166">재구성 수준은 장치 그룹의 [자동화 수준에 해당합니다.](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)</span><span class="sxs-lookup"><span data-stu-id="9af29-166">(Remediation levels correspond to [the automation level for device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups).)</span></span> |
| <span data-ttu-id="9af29-167">**사서함**</span><span class="sxs-lookup"><span data-stu-id="9af29-167">**Mailboxes**</span></span> |<span data-ttu-id="9af29-168">검색된 위협의 영향을 받는 사서함을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-168">Lists mailboxes that are impacted by detected threats.</span></span>  |
| <span data-ttu-id="9af29-169">**사용자**</span><span class="sxs-lookup"><span data-stu-id="9af29-169">**Users**</span></span>  | <span data-ttu-id="9af29-170">검색된 위협의 영향을 미치는 사용자 계정을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-170">Lists user accounts that are impacted by detected threats.</span></span> |
| <span data-ttu-id="9af29-171">**증거**</span><span class="sxs-lookup"><span data-stu-id="9af29-171">**Evidence**</span></span> | <span data-ttu-id="9af29-172">경고 또는 조사에서 제기된 증거 조각을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-172">Lists pieces of evidence raised by alerts or investigations.</span></span> <span data-ttu-id="9af29-173">*판정(악성,* *의심스러운,* 알 수 없음 또는 위협 *없음)* 및 수정 상태를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-173">Includes verdicts (*Malicious*, *Suspicious*, *Unknown*, or *No threats found*) and remediation status.</span></span> |
| <span data-ttu-id="9af29-174">**항목**</span><span class="sxs-lookup"><span data-stu-id="9af29-174">**Entities**</span></span> | <span data-ttu-id="9af29-175">각 엔터티 유형(악성, 의심스러운 또는 위협이 없음)에 대한 판정을 포함하여 분석된 각 엔터티에 대한 세부 *정보를 제공합니다.* </span><span class="sxs-lookup"><span data-stu-id="9af29-175">Provides details about each analyzed entity, including a verdict for each entity type (*Malicious*, *Suspicious*, or *No threats found*).</span></span>|
|<span data-ttu-id="9af29-176">**로그**</span><span class="sxs-lookup"><span data-stu-id="9af29-176">**Log**</span></span> | <span data-ttu-id="9af29-177">경고가 트리거된 후 수행된 모든 조사 작업을 연대적으로 상세하게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-177">Provides a chronological, detailed view of all the investigation actions taken after an alert was triggered.</span></span>|
| <span data-ttu-id="9af29-178">**보류 중인 작업 기록**</span><span class="sxs-lookup"><span data-stu-id="9af29-178">**Pending actions history**</span></span> | <span data-ttu-id="9af29-179">진행 하려면 승인이 필요한 항목을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-179">Lists items that require approval to proceed.</span></span> <span data-ttu-id="9af29-180">작업 센터()로 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 이동하여 보류 중인 작업을 승인합니다.</span><span class="sxs-lookup"><span data-stu-id="9af29-180">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) to approve pending actions.</span></span> |

## <a name="next-steps"></a><span data-ttu-id="9af29-181">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9af29-181">Next steps</span></span>

- [<span data-ttu-id="9af29-182">수정 작업 보기 및 관리</span><span class="sxs-lookup"><span data-stu-id="9af29-182">View and manage remediation actions</span></span>](m365d-autoir-actions.md)
- [<span data-ttu-id="9af29-183">수정 작업에 대해 자세히 알아보시다</span><span class="sxs-lookup"><span data-stu-id="9af29-183">Learn more about remediation actions</span></span>](m365d-remediation-actions.md)
