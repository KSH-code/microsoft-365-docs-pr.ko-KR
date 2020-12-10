---
title: Microsoft 365에서 자동화된 조사 결과 보기
keywords: AIR, autoIR, ATP, 자동화된, 조사, 대응, 수정, 위협, 고급, 위협, 보호
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365에서 자동화된 조사가 진행되는 동안 및 이후에 결과 및 주요 결과를 볼 수 있습니다.
ms.date: 11/05/2020
ms.openlocfilehash: 2018f008e043f36cd41047185f305209fcb725d7
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615147"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a><span data-ttu-id="392f3-104">Microsoft 365의 자동화된 조사 세부 정보 및 결과</span><span class="sxs-lookup"><span data-stu-id="392f3-104">Details and results of an automated investigation in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="392f3-105">Microsoft [](office-365-air.md) [Defender for Office 365에서](office-365-atp.md)자동화된 조사가 발생하면 자동화된 조사 프로세스 중 및 이후에 조사에 대한 세부 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-105">When an [automated investigation](office-365-air.md) occurs in [Microsoft Defender for Office 365](office-365-atp.md), details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="392f3-106">필요한 권한이 있는 경우 Microsoft 365 보안 센터에서 해당 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-106">If you have the necessary permissions, you can view those details in the Microsoft 365 security center.</span></span> <span data-ttu-id="392f3-107">조사 세부 정보는 최신 상태를 제공하고 보류 중인 작업을 승인할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-107">Investigation details provide you with up-to-date status, and the ability to approve any pending actions.</span></span>

## <a name="investigation-status"></a><span data-ttu-id="392f3-108">조사 상태</span><span class="sxs-lookup"><span data-stu-id="392f3-108">Investigation status</span></span>

<span data-ttu-id="392f3-109">조사 상태는 분석 및 작업의 진행률을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-109">The investigation status indicates the progress of the analysis and actions.</span></span> <span data-ttu-id="392f3-110">조사가 실행되면 위협이 발견된지 여부와 작업이 승인된지 여부를 나타내기 위해 상태가 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-110">As the investigation runs, status changes to indicate whether threats were found, and whether actions have been approved.</span></span>

|<span data-ttu-id="392f3-111">상태</span><span class="sxs-lookup"><span data-stu-id="392f3-111">Status</span></span>|<span data-ttu-id="392f3-112">설명</span><span class="sxs-lookup"><span data-stu-id="392f3-112">Description</span></span>|
|---|---|
|<span data-ttu-id="392f3-113">**시작 중**</span><span class="sxs-lookup"><span data-stu-id="392f3-113">**Starting**</span></span>|<span data-ttu-id="392f3-114">조사가 트리거되고 실행을 기다리는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-114">The investigation has been triggered and waiting to start running.</span></span>|
|<span data-ttu-id="392f3-115">**실행 중**</span><span class="sxs-lookup"><span data-stu-id="392f3-115">**Running**</span></span>|<span data-ttu-id="392f3-116">조사 프로세스가 시작된 후 진행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-116">The investigation process has started and is underway.</span></span> <span data-ttu-id="392f3-117">이 상태는 보류 중인 작업이 [승인된](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) 경우도 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-117">This state also occurs when [pending actions](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) are approved.</span></span>|
|<span data-ttu-id="392f3-118">**위협 없음**</span><span class="sxs-lookup"><span data-stu-id="392f3-118">**No Threats Found**</span></span>|<span data-ttu-id="392f3-119">조사가 완료된 후 위협(사용자 계정, 전자 메일 메시지, URL 또는 파일)이 식별되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-119">The investigation has finished and no threats (user account, email message, URL, or file) were identified.</span></span> <p> <span data-ttu-id="392f3-120">**팁**: 누락된 것으로 의심되는 경우(예: 거짓 부정) 위협 탐색기를 사용하여 조치를 [취할 수 있습니다.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="392f3-120">**TIP**: If you suspect something was missed (such as a false negative), you can take action using [Threat Explorer](threat-explorer.md).</span></span>|
|<span data-ttu-id="392f3-121">**위협 발견**</span><span class="sxs-lookup"><span data-stu-id="392f3-121">**Threats Found**</span></span>|<span data-ttu-id="392f3-122">자동화된 조사에서 문제가 발견되지만 이러한 문제를 해결하기 위한 구체적인 수정 작업은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-122">The automated investigation found issues, but there are no specific remediation actions to resolve those issues.</span></span> <p> <span data-ttu-id="392f3-123">위협 **발견** 상태는 특정 유형의 사용자 활동을 식별했지만 정리 작업을 사용할 수 없는 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-123">The **Threats Found** status can occur when some type of user activity was identified but no cleanup actions are available.</span></span> <span data-ttu-id="392f3-124">예를 들어 다음과 같은 사용자 활동이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-124">Examples include any of the following user activities:</span></span> <ul><li><span data-ttu-id="392f3-125">[DLP(데이터](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) 손실 방지) 이벤트</span><span class="sxs-lookup"><span data-stu-id="392f3-125">A [data loss prevention](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) (DLP) event</span></span></li><li><span data-ttu-id="392f3-126">이상을 보내는 전자 메일</span><span class="sxs-lookup"><span data-stu-id="392f3-126">An email sending anomaly</span></span></li><li><span data-ttu-id="392f3-127">보낸 맬웨어</span><span class="sxs-lookup"><span data-stu-id="392f3-127">Sent malware</span></span></li><li><span data-ttu-id="392f3-128">보낸 피싱</span><span class="sxs-lookup"><span data-stu-id="392f3-128">Sent phish</span></span></li></ul> <p> <span data-ttu-id="392f3-129">조사에서 수정할 악의적인 URL, 파일 또는 전자 메일 메시지가 없음을 발견하고 전달 규칙이나 위임 해제와 같은 수정할 사서함 활동이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-129">The investigation found no malicious URLs, files, or email messages to remediate, and no mailbox activity to fix, such as turning off forwarding rules or delegation.</span></span> <p> <span data-ttu-id="392f3-130">**팁**: 누락된 것으로 의심되는 경우(예: 거짓 부정) 위협 탐색기를 사용하여 조사하고 조치를 [취할 수 있습니다.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="392f3-130">**TIP**: If you suspect something was missed (such as a false negative), you can investigate and take action using [Threat Explorer](threat-explorer.md).</span></span>|
|<span data-ttu-id="392f3-131">**시스템으로 종료**</span><span class="sxs-lookup"><span data-stu-id="392f3-131">**Terminated By System**</span></span>|<span data-ttu-id="392f3-132">조사가 중지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-132">The investigation stopped.</span></span> <span data-ttu-id="392f3-133">조사는 몇 가지 이유로 중지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-133">An investigation can stop for several reasons:</span></span> <ul><li><span data-ttu-id="392f3-134">조사의 보류 중인 작업이 만료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-134">The investigation's pending actions expired.</span></span> <span data-ttu-id="392f3-135">보류 중인 작업은 1주일 동안 승인을 기다린 후 시간적이 지났습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-135">Pending actions time out after awaiting approval for one week.</span></span></li><li><span data-ttu-id="392f3-136">작업이 너무 많이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-136">There are too many actions.</span></span> <span data-ttu-id="392f3-137">예를 들어 악의적인 URL을 클릭하는 사용자가 너무 많은 경우 조사에서 모든 분석기를 실행할 수 있는 기능을 초과할 수 있으므로 조사가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-137">For example, if there are too many users clicking on malicious URLs, it can exceed the investigation's ability to run all the analyzers, so the investigation halts.</span></span></li></ul> <p> <span data-ttu-id="392f3-138">**팁:** 작업이 수행되기 전에 조사가 중단된 경우 [위협](threat-explorer.md) 탐색기를 사용하여 위협을 찾아 해결해 하세요.</span><span class="sxs-lookup"><span data-stu-id="392f3-138">**TIP**: If an investigation halts before actions were taken, try using [Threat Explorer](threat-explorer.md) to find and address threats.</span></span>|
|<span data-ttu-id="392f3-139">**보류 중인 작업**</span><span class="sxs-lookup"><span data-stu-id="392f3-139">**Pending Action**</span></span>|<span data-ttu-id="392f3-140">조사에서 악성 전자 메일, 악의적인 URL 또는 위험한 사서함 설정과 위협이 승인 대기하고 있는 수정 작업을 [발견했습니다.](air-review-approve-pending-completed-actions.md)</span><span class="sxs-lookup"><span data-stu-id="392f3-140">The investigation has found a threat, such as a malicious email, a malicious URL, or a risky mailbox setting, and an action to remediate that threat is [awaiting approval](air-review-approve-pending-completed-actions.md).</span></span> <p> <span data-ttu-id="392f3-141">보류 **중인 작업** 상태는 해당 작업이 있는 위협이 발견되면 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-141">The **Pending Action** state is triggered when any threat with a corresponding action is found.</span></span> <span data-ttu-id="392f3-142">그러나 조사가 실행될 때 보류 중인 작업 목록이 늘어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-142">However, the list of pending actions can increase as an investigation runs.</span></span> <span data-ttu-id="392f3-143">조사 [로그에서](#playbook-log) 다른 항목이 아직 완료 보류 중인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-143">Check the [investigation log](#playbook-log) to see if other items are still pending completion.</span></span>|
|<span data-ttu-id="392f3-144">**수정**</span><span class="sxs-lookup"><span data-stu-id="392f3-144">**Remediated**</span></span>|<span data-ttu-id="392f3-145">조사가 끝났고 모든 수정 작업이 승인되었습니다(완전히 수정된 것으로 알려됨).</span><span class="sxs-lookup"><span data-stu-id="392f3-145">The investigation finished and all remediation actions were approved (this is noted as fully remediated).</span></span> <p> <span data-ttu-id="392f3-146">**참고:** 승인된 수정 작업에는 작업이 수행되지 않도록 하는 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-146">**NOTE**: Approved remediation actions can have errors that prevent the actions from being taken.</span></span> <span data-ttu-id="392f3-147">재구성 작업이 성공적으로 완료된지 여부에 관계없이 조사 상태는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-147">Regardless of whether remediation actions are successfully completed, the investigation status does not change.</span></span> <span data-ttu-id="392f3-148">조사 [로그에서](#playbook-log) 자세한 결과를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-148">Check the [investigation log](#playbook-log) for detailed results.</span></span>|
|<span data-ttu-id="392f3-149">**부분적으로 수정**</span><span class="sxs-lookup"><span data-stu-id="392f3-149">**Partially Remediated**</span></span>|<span data-ttu-id="392f3-150">조사 결과 수정 작업이 수행되었습니다. 일부는 승인 및 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-150">The investigation resulted in remediation actions, and some were approved and completed.</span></span> <span data-ttu-id="392f3-151">다른 작업은 여전히 [보류 중입니다.](air-review-approve-pending-completed-actions.md)</span><span class="sxs-lookup"><span data-stu-id="392f3-151">Other actions are still [pending](air-review-approve-pending-completed-actions.md).</span></span>|
|<span data-ttu-id="392f3-152">**실패**</span><span class="sxs-lookup"><span data-stu-id="392f3-152">**Failed**</span></span>|<span data-ttu-id="392f3-153">하나 이상의 조사 분석기가 제대로 완료되지 않는 문제가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-153">At least one investigation analyzer ran into a problem where it could not complete properly.</span></span> <p> <span data-ttu-id="392f3-154">**참고:** 재구성 작업이 승인된 후 조사가 실패하면 수정 작업이 성공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-154">**NOTE**: If an investigation fails after remediation actions were approved, the remediation actions might still have succeeded.</span></span> <span data-ttu-id="392f3-155">조사 [로그에서](#playbook-log) 자세한 결과를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-155">Check the [investigation log](#playbook-log) for detailed results.</span></span>|
|<span data-ttu-id="392f3-156">**스로틀링에 의해 대기**</span><span class="sxs-lookup"><span data-stu-id="392f3-156">**Queued By Throttling**</span></span>|<span data-ttu-id="392f3-157">조사가 큐에 대기 중입니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-157">An investigation is being held in a queue.</span></span> <span data-ttu-id="392f3-158">다른 조사가 완료되면 대기 중인 조사가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-158">When other investigations complete, queued investigations begin.</span></span> <span data-ttu-id="392f3-159">스로틀은 서비스 성능이 좋지 않은 것을 방지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-159">Throttling helps avoid poor service performance.</span></span>  <p> <span data-ttu-id="392f3-160">**팁**: 보류 중인 작업은 새 조사를 실행할 수 있는 수를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-160">**TIP**: Pending actions can limit how many new investigations can run.</span></span> <span data-ttu-id="392f3-161">보류 중인 [작업을 승인(또는 거부)해야 합니다.](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)</span><span class="sxs-lookup"><span data-stu-id="392f3-161">Make sure to [approve (or reject) pending actions](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions).</span></span>|
|<span data-ttu-id="392f3-162">**스로틀에 의해 종료**</span><span class="sxs-lookup"><span data-stu-id="392f3-162">**Terminated By Throttling**</span></span>|<span data-ttu-id="392f3-163">조사가 너무 긴 큐에 있는 경우 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-163">If an investigation is held in the queue too long, it stops.</span></span> <p> <span data-ttu-id="392f3-164">**팁**: [위협 탐색기에서 조사를 시작할 수 있습니다.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)</span><span class="sxs-lookup"><span data-stu-id="392f3-164">**TIP**: You can [start an investigation from Threat Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>|
|

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="392f3-165">조사 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="392f3-165">View details of an investigation</span></span>

1. <span data-ttu-id="392f3-166">보안 & 준수 <https://protection.office.com> 센터()로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-166">Go to the Security & Compliance Center (<https://protection.office.com>) and sign in.</span></span>

2. <span data-ttu-id="392f3-167">다음 작업 중 하나를 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="392f3-167">Do one of the following actions:</span></span>

    - <span data-ttu-id="392f3-168">위협 관리 **대시보드로** \> **이동**</span><span class="sxs-lookup"><span data-stu-id="392f3-168">Go to **Threat management** \> **Dashboard**.</span></span> <span data-ttu-id="392f3-169">그러면 보안 [대시보드로 진행됩니다.](security-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="392f3-169">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="392f3-170">AIR 위젯이 보안 대시보드의 맨 [위에 표시됩니다.](security-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="392f3-170">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="392f3-171">조사 요약과 같은 **위젯을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="392f3-171">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="392f3-172">위협  관리 \> **조사로 이동.**</span><span class="sxs-lookup"><span data-stu-id="392f3-172">Go to **Threat management** \> **Investigations**.</span></span>

    <span data-ttu-id="392f3-173">두 방법 중 하나를 사용하면 조사 목록으로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-173">Either method takes you to a list of investigations.</span></span>

    ![AIR에 대한 기본 조사 페이지](../../media/air-maininvestigationpage.png)

3. <span data-ttu-id="392f3-175">조사 목록에서 ID 열의 **항목을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-175">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="392f3-176">그러면 조사 그래프부터 조사 세부 정보 페이지가 보기로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-176">This opens investigation details page, starting with the investigation graph in view.</span></span>

    ![AIR 조사 그래프 페이지](../../media/air-investigationgraphpage.png)

   <span data-ttu-id="392f3-178">다양한 탭을 사용하여 조사에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-178">Use the various tabs to learn more about the investigation.</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="392f3-179">조사와 관련된 경고에 대한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="392f3-179">View details about an alert related to an investigation</span></span>

<span data-ttu-id="392f3-180">특정 종류의 경고는 Microsoft 365에서 자동화된 조사를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-180">Certain kinds of alerts trigger automated investigation in Microsoft 365.</span></span> <span data-ttu-id="392f3-181">자세한 내용은 자동화된 [조사를 트리거하는 경고 정책을 참조합니다.](office-365-air.md#which-alert-policies-trigger-automated-investigations)</span><span class="sxs-lookup"><span data-stu-id="392f3-181">To learn more, see [alert policies that trigger automated investigations](office-365-air.md#which-alert-policies-trigger-automated-investigations).</span></span>

<span data-ttu-id="392f3-182">다음 절차에 따라 자동화된 조사와 연결된 경고에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-182">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="392f3-183">보안 & 준수 <https://protection.office.com> 센터()로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-183">Go to the Security & Compliance Center (<https://protection.office.com>) and sign in.</span></span>

2. <span data-ttu-id="392f3-184">위협  관리 \> **조사로 이동.**</span><span class="sxs-lookup"><span data-stu-id="392f3-184">Go to **Threat management** \> **Investigations**.</span></span>

3. <span data-ttu-id="392f3-185">조사 목록에서 ID 열의 **항목을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-185">In the list of investigations, select an item in the **ID** column.</span></span>

4. <span data-ttu-id="392f3-186">조사 세부 정보가 열리면 경고 **탭을** 선택합니다. 조사를 트리거한 모든 알림이 여기에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-186">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="392f3-187">목록에서 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-187">Select an item in the list.</span></span> <span data-ttu-id="392f3-188">경고에 대한 세부 정보와 추가 정보 및 작업에 대한 링크가 있는 플라이아웃이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-188">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="392f3-189">플라이아웃에 대한 정보를 검토하고, 특정 경고에 따라 **해결,** 표시 안 되거나 사용자에게 알림과 같은 작업을 **실행합니다.**</span><span class="sxs-lookup"><span data-stu-id="392f3-189">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span>

    - <span data-ttu-id="392f3-190">**해결은** 경고를 닫는 데 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-190">**Resolve** is equivalent to closing an alert</span></span>

    - <span data-ttu-id="392f3-191">**표시** 안 하여 정책이 지정된 기간 동안 경고를 트리거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-191">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>

    - <span data-ttu-id="392f3-192">**사용자에게 사용자의** 전자 메일 주소가 이미 입력된 전자 메일을 시작하고 보안 운영 팀에서 해당 사용자에게 메시지를 입력할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-192">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="392f3-193">이 메시지는 위협 탐색기를 사용하여 받는 사람에게 메시지를 보내는 [경우와 비슷합니다.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="392f3-193">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>

## <a name="how-to-use-the-various-tabs"></a><span data-ttu-id="392f3-194">다양한 탭을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="392f3-194">How to use the various tabs</span></span>

<span data-ttu-id="392f3-195">다음 섹션에서는 자동화된 조사 페이지의 다양한 탭과 정보를 사용하는 방법을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-195">The following sections walk you through the various tabs on the automated investigations page and how you can use the information.</span></span>

### <a name="automated-investigations-page"></a><span data-ttu-id="392f3-196">자동화된 조사 페이지</span><span class="sxs-lookup"><span data-stu-id="392f3-196">Automated investigations page</span></span>

<span data-ttu-id="392f3-197">자동화된 조사 페이지에는 조직의 조사와 해당 현재 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-197">The automated investigations page shows your organization's investigations and their current states.</span></span>

![AIR에 대한 기본 조사 페이지](../../media/air-maininvestigationpage.png)

<span data-ttu-id="392f3-199">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-199">You can:</span></span>

- <span data-ttu-id="392f3-200">조사로 바로 **이동합니다(조사 ID 선택).**</span><span class="sxs-lookup"><span data-stu-id="392f3-200">Navigate directly to an investigation (select an **Investigation ID**).</span></span>

- <span data-ttu-id="392f3-201">필터를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-201">Apply filters.</span></span> <span data-ttu-id="392f3-202">조사 **유형,** **시간 범위,** **상태** 또는 이들의 조합에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-202">Choose from **Investigation Type**, **Time range**, **Status**, or a combination of these.</span></span>

- <span data-ttu-id="392f3-203">데이터를 .csv 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-203">Export the data to a .csv file.</span></span>

### <a name="investigation-graph"></a><span data-ttu-id="392f3-204">조사 그래프</span><span class="sxs-lookup"><span data-stu-id="392f3-204">Investigation graph</span></span>

<span data-ttu-id="392f3-205">특정 조사를 열면 조사 그래프 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-205">When you open a specific investigation, you see the investigation graph page.</span></span> <span data-ttu-id="392f3-206">이 페이지에는 전자 메일 메시지, 사용자(및 해당 활동) 및 트리거된 경고의 일부로 자동으로 조사된 장치 등 다양한 엔터티가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-206">This page shows all the different entities: email messages, users (and their activities), and devices that were automatically investigated as part of the alert that was triggered.</span></span>

![AIR 조사 그래프 페이지](../../media/air-investigationgraphpage.png)

<span data-ttu-id="392f3-208">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-208">You can:</span></span>

- <span data-ttu-id="392f3-209">현재 조사에 대한 시각적 개요를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-209">Get a visual overview of the current investigation.</span></span>
- <span data-ttu-id="392f3-210">조사 기간의 요약을 시청합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-210">View a summary of the investigation duration.</span></span>
- <span data-ttu-id="392f3-211">시각화에서 노드를 선택하여 해당 노드에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-211">Select a node in the visualization to view details for that node.</span></span>
- <span data-ttu-id="392f3-212">위쪽에서 탭을 선택하여 해당 탭에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-212">Select a tab across the top to view details for that tab.</span></span>

### <a name="alert-investigation"></a><span data-ttu-id="392f3-213">경고 조사</span><span class="sxs-lookup"><span data-stu-id="392f3-213">Alert investigation</span></span>

<span data-ttu-id="392f3-214">조사를 **위한** 알림 탭에서 조사와 관련된 경고를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-214">On the **Alerts** tab for an investigation, you can see alerts relevant to the investigation.</span></span> <span data-ttu-id="392f3-215">세부 정보에는 조사를 트리거한 경고 및 위험한 로그인, [DLP](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) 정책 위반 등 조사와 상호 관련이 있는 기타 관련 경고가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-215">Details include the alert that triggered the investigation and other correlated alerts, such as risky sign-in, [DLP policy](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) violations, etc., that are correlated to the investigation.</span></span> <span data-ttu-id="392f3-216">이 페이지에서 보안 분석가가 개별 경고에 대한 추가 세부 정보를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-216">From this page, a security analyst can also view additional details on individual alerts.</span></span>

![AIR 경고 페이지](../../media/air-investigationalertspage.png)

<span data-ttu-id="392f3-218">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-218">You can:</span></span>

- <span data-ttu-id="392f3-219">현재 트리거되는 경고 및 모든 관련 경고에 대한 시각적 개요를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-219">Get a visual overview of the current triggering alert and any associated alerts.</span></span>
- <span data-ttu-id="392f3-220">목록에서 경고를 선택하여 전체 경고 세부 정보를 표시하는 플라이아웃 페이지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-220">Select an alert in the list to open a fly-out page that shows full alert details.</span></span>

### <a name="email-investigation"></a><span data-ttu-id="392f3-221">전자 메일 조사</span><span class="sxs-lookup"><span data-stu-id="392f3-221">Email investigation</span></span>

<span data-ttu-id="392f3-222">조사를 **위해 전자** 메일 탭에서 조사의 일부로 식별된 유사한 전자 메일의 원본 전자 메일 및 클러스터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-222">On the **Email** tab for an investigation, you can see the original emails and the clusters of similar email identified as part of the investigation.</span></span> <span data-ttu-id="392f3-223">또한 **전자 메일** 탭에는 사용자가 보고한 전자 메일 세부 정보, 보고된 원본 전자 메일, 맬웨어/피싱으로 인해 잠기던 전자 메일 메시지 등 조사와 관련된 전자 메일 항목도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-223">The **Email** tab also shows email items related to the investigation, such as the user-reported email details, the original email reported, the email message(s) zapped due to malware/phish, etc.</span></span>

![AIR 전자 메일 조사 페이지](../../media/air-investigationemailpage.png)

<span data-ttu-id="392f3-225">전자 메일 조사를 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-225">With email investigation, you can:</span></span>

- <span data-ttu-id="392f3-226">발견된 현재 클러스터링 결과 및 위협에 대한 시각적 개요를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-226">Get a visual overview of the current clustering results and threats found.</span></span>
- <span data-ttu-id="392f3-227">클러스터 엔터티 또는 위협 목록을 클릭하여 전체 경고 세부 정보를 표시하는 플라이아웃 페이지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-227">Click a cluster entity or a threat list to open a fly-out page that shows the full alert details.</span></span>
- <span data-ttu-id="392f3-228">전자 메일 클러스터 세부 정보  탭의 맨 위에 있는 탐색기에서 열기 링크를 클릭하여 전자 메일 클러스터를 추가로 **조사합니다.**</span><span class="sxs-lookup"><span data-stu-id="392f3-228">Further investigate the email cluster by clicking the **Open in Explorer** link at the top of the **Email cluster details** tab</span></span>

![플라이아웃 세부 정보가 있는 AIR 조사 전자 메일](../../media/air-investigationemailpageflyoutdetails.png)

<span data-ttu-id="392f3-230">조직의 사용자가 보내고 받는 전자 메일의 양과 전자 메일 통신 및 공격의 다중 사용자 특성에 따라 다음 프로세스에 많은 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-230">Given the sheer volume of email that users in an organization send and receive, plus the multi-user nature of email communications and attacks, the following process can take a significant amount of time:</span></span>

1. <span data-ttu-id="392f3-231">메시지 헤더, 본문, URL 및 첨부 파일에서 유사한 특성을 기반으로 전자 메일 메시지를 클러스터링합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-231">Clustering email messages based on similar attributes from a message header, body, URL, and attachments.</span></span>
2. <span data-ttu-id="392f3-232">악성 전자 메일과 좋은 전자 메일 분리</span><span class="sxs-lookup"><span data-stu-id="392f3-232">Separating malicious email from the good email.</span></span>
3. <span data-ttu-id="392f3-233">악의적인 전자 메일 메시지에 대한 작업 수행</span><span class="sxs-lookup"><span data-stu-id="392f3-233">Taking action on malicious email messages.</span></span>

<span data-ttu-id="392f3-234">AIR은 이 프로세스를 자동화하여 조직의 보안 팀과 노력을 절약합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-234">AIR automates this process, saving your organization's security team time and effort.</span></span>

#### <a name="types-of-email-clusters"></a><span data-ttu-id="392f3-235">전자 메일 클러스터 유형</span><span class="sxs-lookup"><span data-stu-id="392f3-235">Types of email clusters</span></span>

<span data-ttu-id="392f3-236">전자 메일 분석 단계에서 유사성 클러스터(모든 조사), 지표 클러스터(모든 조사) 및 사서함/사용자 클러스터의 세 가지 유형의 전자 메일 클러스터를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-236">Three different types of email clusters can be identified during the email analysis step: similarity clusters (all investigations), indicator clusters (all investigations), and mailbox/user clusters.</span></span> <span data-ttu-id="392f3-237">다음 표에서는 이러한 유형의 전자 메일 클러스터에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-237">The following table describes these types of email clusters.</span></span>

|<span data-ttu-id="392f3-238">전자 메일 클러스터</span><span class="sxs-lookup"><span data-stu-id="392f3-238">Email cluster</span></span>|<span data-ttu-id="392f3-239">설명</span><span class="sxs-lookup"><span data-stu-id="392f3-239">Description</span></span>|
|---|---|
|<span data-ttu-id="392f3-240">유사성 클러스터</span><span class="sxs-lookup"><span data-stu-id="392f3-240">Similarity clusters</span></span>|<span data-ttu-id="392f3-241">보낸 사람 및 콘텐츠 특성이 비슷한 전자 메일을 헌팅하여 식별된 전자 메일 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-241">Email messages identified by hunting for emails with similar sender and content attributes.</span></span> <span data-ttu-id="392f3-242">이러한 클러스터는 원래 검색 결과를 기반으로 악성 콘텐츠가 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-242">These clusters are evaluated for malicious content based on the original detection findings.</span></span> <span data-ttu-id="392f3-243">악의적인 전자 메일 검색을 충분히 포함하는 전자 메일 클러스터는 악의적인 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-243">Email clusters that contain enough malicious email detections are considered malicious.</span></span>|
|<span data-ttu-id="392f3-244">표시기 클러스터</span><span class="sxs-lookup"><span data-stu-id="392f3-244">Indicator clusters</span></span>|<span data-ttu-id="392f3-245">원본 전자 메일에서 동일한 표시기 엔터티(파일 해시 또는 URL)를 헌팅하여 식별된 전자 메일 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-245">Email messages that are identified by hunting for the same indicator entity (file hash or URL) from the original email.</span></span> <span data-ttu-id="392f3-246">원래 파일/URL 엔터티가 악성으로 식별되면 AIR은 해당 엔터티가 포함된 전자 메일 메시지의 전체 클러스터에 표시기 판정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-246">When the original file/URL entity is identified as malicious, AIR applies the indicator verdict to the entire cluster of email messages containing that entity.</span></span> <span data-ttu-id="392f3-247">맬웨어로 식별된 파일은 해당 파일을 포함하는 전자 메일 메시지 클러스터가 맬웨어 전자 메일 메시지로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-247">A file identified as malware means that the cluster of email messages containing that file are treated as malware email messages.</span></span>|
|<span data-ttu-id="392f3-248">사서함/사용자 클러스터</span><span class="sxs-lookup"><span data-stu-id="392f3-248">Mailbox/user clusters</span></span>|<span data-ttu-id="392f3-249">사용자 손상 조사에 관련된 사용자와 관련된 전자 메일 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-249">Email messages related to the user involved in a user compromise investigation.</span></span> <span data-ttu-id="392f3-250">이러한 전자 메일 클러스터는 보안 운영 팀의 추가 분석용으로, 전자 메일 수정 작업을 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-250">These email clusters are for further analysis by the security operations team and will not generate email remediation actions.</span></span> <p> <span data-ttu-id="392f3-251">손상된 사용자 보안 플레이북은 사서함에서 전송되는 전자 메일이 미칠 수 있는 영향을 이해하기 위해 분석되는 사용자가 전송하는 전자 메일을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-251">The compromised user security playbook  reviews the emails being sent by the user being analyzed in order to understand the potential impact of the emails being sent from the mailbox.</span></span>|

> [!NOTE]
> <span data-ttu-id="392f3-252">클러스터링의 목표는 공격 또는 캠페인의 일부로 동일한 보낸 사람이 보낸 다른 관련 전자 메일 메시지를 헌팅하고 찾는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-252">The goal of clustering is to hunt and find other related email messages that are sent by the same sender as part of an attack or a campaign.</span></span>  <span data-ttu-id="392f3-253">경우에 따라 합법적인 전자 메일이 조사를 트리거할 수 있습니다(예: 사용자가 마케팅 전자 메일을 보고).</span><span class="sxs-lookup"><span data-stu-id="392f3-253">In some cases, legitimate email might trigger an investigation (for example, a user reports a marketing email).</span></span>  <span data-ttu-id="392f3-254">이러한 시나리오에서 전자 메일 클러스터링은 전자 메일 클러스터가 악성이 아니라는 것을  식별해야 합니다. 적절한 경우 위협을 나타내지 않으며 전자 메일 제거를 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-254">In these scenarios, the email clustering should identify that email clusters are not malicious – when it appropriately does so, it will **not** indicate a threat, nor will it recommend email removal.</span></span>

#### <a name="email-classifications"></a><span data-ttu-id="392f3-255">전자 메일 분류</span><span class="sxs-lookup"><span data-stu-id="392f3-255">Email classifications</span></span>

<span data-ttu-id="392f3-256">전자 메일 메시지를 분석할 때 악의적, 의심스러운 메시지  또는 정리된 메시지로 분류됩니다(위협으로 식별되지는 *않은* 경우).  </span><span class="sxs-lookup"><span data-stu-id="392f3-256">As email messages are analyzed, they are classified as *malicious*, *suspicious*, or *clean* (as in, *not identified as a threat*):</span></span>

- <span data-ttu-id="392f3-257">*사서함/사용자가* 보낸 악의적인 전자 메일은 사서함/계정의 잠재적 손상을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-257">*Malicious emails* sent from the mailbox/user  indicate potential compromise of the mailbox/account.</span></span> <span data-ttu-id="392f3-258">손상의 일부로 악의적인 전자 메일의 영향을 받는 다른 사용자/사서함이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-258">Other users/mailboxes that are potentially impacted by malicious email as part of a compromise are shown.</span></span>

- <span data-ttu-id="392f3-259">*사서함/사용자가* 보낸 의심스러운 전자 메일은 손상된 계정 또는 원치 않는 전자 메일 활동이 발생할 수 있는 가능성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-259">*Suspicious emails* sent by the mailbox/user indicate the potential for a compromised account or unwanted email activity.</span></span> <span data-ttu-id="392f3-260">이러한 메시지에는 사서함에서 보낸 스팸/대량 전자 메일이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-260">These messages include any spam/bulk email sent from the mailbox.</span></span>

- <span data-ttu-id="392f3-261">*사서함/사용자가* 보낸 클린 전자 메일(위협이 아닌 것으로 간주되는 전자 메일)은 보안 운영 팀에 전송된 합법적인 사용자 전자 메일 보기를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-261">*Clean emails* (emails that are considered not a threat) sent by the mailbox/user can provide your security operations team with a view of legitimate user emails sent.</span></span> <span data-ttu-id="392f3-262">그러나 이러한 전자 메일은 전자 메일 계정이 손상된 경우 데이터 유출을 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-262">However, these emails can also include data exfiltration if the email account is compromised.</span></span>

#### <a name="more-about-email-counts"></a><span data-ttu-id="392f3-263">전자 메일 수에 대한 자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="392f3-263">More about email counts</span></span>

<span data-ttu-id="392f3-264">전자 메일 탭에 식별된 전자 메일 수는 현재 전자 메일 탭에 표시된 모든 전자 메일 메시지의 합계를 **나타내고** 있습니다. 전자 메일 메시지는 여러 클러스터에 존재하기 때문에 식별된(수정 작업의 영향을 받는) 전자 메일 메시지의 실제 총 수는 모든 클러스터 및 원래 받는 사람의 전자 메일 메시지에 걸쳐 있는 고유한 전자 메일 메시지의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-264">The email count identified on the email tab currently represents the sum total of all email messages that shown on the **Email** tab. Because email messages are present in multiple clusters, the actual total count of email messages identified (and affected by remediation actions) is the count of unique email messages present across all of the clusters and original recipients' email messages.</span></span>

<span data-ttu-id="392f3-265">보안 [판정,](threat-explorer.md) 작업 및 배달 위치는 받는 사람별로 다르기 때문에 탐색기 및 AIR 개수 전자 메일 메시지는 받는 사람별로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-265">Both [Explorer](threat-explorer.md) and AIR count email messages on a per-recipient basis, because the security verdicts, actions, and delivery locations vary on a per-recipient basis.</span></span> <span data-ttu-id="392f3-266">따라서 세 사용자에게 전송된 원래 전자 메일은 전자 메일이 아닌 총 3개의 전자 메일 메시지로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-266">Thus, an original email sent to three users counts as a total of three email messages instead of one email.</span></span>

<span data-ttu-id="392f3-267">전자 메일에 여러 작업이 있는 경우나 모든 작업이 발생할 때 전자 메일 복사본이 여러 개 있는 경우와 같이 전자 메일이 두 번 이상 계산되는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-267">There might be cases where an email gets counted two or more times, such as when an email has multiple actions on it, or when there are multiple copies of the email when all the actions occur.</span></span>

<span data-ttu-id="392f3-268">예를 들어 배달 시 감지된 맬웨어 전자 메일은 차단(고지된) 전자 메일과 대체된 전자 메일(경고 파일로 대체된 위협 파일을 사용자 사서함으로 배달)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-268">For example, a malware email that is detected at delivery can result in both a blocked (quarantined) email and a replaced email (threat file replaced with a warning file, then delivered to user's mailbox).</span></span> <span data-ttu-id="392f3-269">시스템에 전자 메일의 복사본이 문자 그대로 두 개 있기 때문에 둘 다 클러스터 수에서 계산될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-269">Because there are literally two copies of the email in the system, both might be counted in cluster counts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="392f3-270">다음은 유의해야 할 몇 가지 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-270">Here are a few points to keep in mind:</span></span>
>
> - <span data-ttu-id="392f3-271">전자 메일 개수는 조사 시에 계산하며, 일부 개수는 조사 플라이아웃을 열 때(기초 쿼리를 기반으로) 다시 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-271">Email counts are calculated at the time of the investigation, and some counts are recalculated when you open investigation flyouts (based on an underlying query).</span></span>
>
> - <span data-ttu-id="392f3-272">전자 메일 탭의 전자 메일 클러스터에 대해 표시되는 전자 메일 수와 클러스터 플라이아웃에 표시된 전자 메일 수량 값은 조사 시 계산하며 변경되지 않습니다. </span><span class="sxs-lookup"><span data-stu-id="392f3-272">The email counts shown for the email clusters on the **Email** tab and the email quantity value shown on cluster flyout are calculated at the time of investigation, and do not change.</span></span>
>
> - <span data-ttu-id="392f3-273">전자 메일 클러스터 플라이아웃의 전자 메일 탭 아래쪽에 표시되는 전자 메일 수와 탐색기에 표시된 전자 메일 메시지 수에는 조사 초기 분석 후 받은 전자 메일 메시지가 반영됩니다. </span><span class="sxs-lookup"><span data-stu-id="392f3-273">The email count shown at the bottom of the **Email** tab of the email cluster flyout and the count of email messages shown in Explorer reflect email messages received after the investigation's initial analysis.</span></span>

<span data-ttu-id="392f3-274">따라서 조사 분석 단계 사이에 5개의 전자 메일 메시지가 도착하고 관리자가 조사를 검토할 때 원래 수량인 10개의 전자 메일 메시지를 표시하는 전자 메일 클러스터에는 총 15개의 전자 메일 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-274">Thus, an email cluster that shows an original quantity of 10 email messages would show an email list total of 15 when five more email messages arrive between the investigation analysis phase and when the admin reviews the investigation.</span></span> <span data-ttu-id="392f3-275">마찬가지로, Office 365 요금제 2용 Microsoft Defender의 데이터는 평가판을 위해 7일 후에 그리고 유료 라이선스에 대해 30일 후에 만료하기 때문에 이전 조사는 탐색기 쿼리에 표시하는 것보다 더 높은 수를 표시하기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-275">Likewise, old investigations might start showing higher counts than Explorer queries show, because data in Microsoft Defender for Office 365 Plan 2 expires after 7 days for trials and after 30 days for paid licenses.</span></span>

<span data-ttu-id="392f3-276">조사 시 전자 메일에 미치는 영향과 수정이 실행될 때까지 현재의 영향을 나타내기 위해 다양한 보기에서 수 기록 및 현재 수를 모두 표시하는 것이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-276">Showing both count historical and current counts in different views is done to indicate the email impact at the time of investigation and the current impact up until the time that remediation is run.</span></span>

> [!NOTE]
> <span data-ttu-id="392f3-277">전자 메일 컨텍스트에서 조사의 일부로 볼륨 이상 위협 표면이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-277">In the context of email, you might see a volume anomaly threat surface as part of the investigation.</span></span> <span data-ttu-id="392f3-278">볼륨 이상은 이전 기간과 비교하여 조사 이벤트 시간과 비슷한 전자 메일 메시지의 스파이크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-278">A volume anomaly indicates a spike in similar email messages around the investigation event time compared to earlier timeframes.</span></span> <span data-ttu-id="392f3-279">이와 같은 특성이 비슷한 전자 메일 트래픽(예: 제목 및 보낸 사람 도메인, 본문 유사성 및 보낸 사람 IP)이 전자 메일 캠페인 또는 공격 시작의 일반적인 예입니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-279">This spike in email traffic with similar characteristics (e.g. subject and sender domain, body similarity and sender IP) is typical of the start of email campaigns or attacks.</span></span>
> <span data-ttu-id="392f3-280">그러나 대량, 스팸 및 합법적인 전자 메일 캠페인은 일반적으로 이러한 특성을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-280">However, bulk, spam, and legitimate email campaigns commonly share these characteristics.</span></span>
>
> <span data-ttu-id="392f3-281">볼륨 이상은 잠재적인 위협을 나타내며, 그에 따라 바이러스 백신 엔진, 탐지 또는 악의적인 신뢰도로 식별된 맬웨어 또는 피싱 위협에 비해 심각하지 않은 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-281">Volume anomalies represent a potential threat, and accordingly could be less severe compared to malware or phish threats that are identified using anti-virus engines, detonation or malicious reputation.</span></span>

### <a name="user-investigation"></a><span data-ttu-id="392f3-282">사용자 조사</span><span class="sxs-lookup"><span data-stu-id="392f3-282">User investigation</span></span>

<span data-ttu-id="392f3-283">사용자 **탭에서** 조사의 일부로 식별된 모든 사용자를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-283">On the **Users** tab, you can see all the users identified as part of the investigation.</span></span> <span data-ttu-id="392f3-284">사용자 계정은 해당 사용자 계정이 영향을 받거나 손상될 수 있는 이벤트가 있는 경우 조사에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-284">User accounts appear in the investigation when there is an event or indication that those user accounts might be affected or compromised.</span></span>

<span data-ttu-id="392f3-285">예를 들어 다음 이미지에서 AIR은 생성된 새 받은 편지함 규칙을 기반으로 손상 및 예외를 식별했습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-285">For example, in the following image, AIR has identified indicators of compromise and anomalies based on a new inbox rule that was created.</span></span> <span data-ttu-id="392f3-286">조사에 대한 추가 세부 정보(증거)는 이 탭 내의 자세한 보기를 통해 사용할 수 있습니다. 손상 표시기 및 이상은 [Microsoft Cloud App Security의](https://docs.microsoft.com/cloud-app-security)이상 검색도 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-286">Additional details (evidence) of the investigation are available through detailed views within this tab. Indicators of compromise and anomalies might also include anomaly detections from [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span>

![AIR 조사 사용자 페이지](../../media/air-investigationuserspage.png)

<span data-ttu-id="392f3-288">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-288">You can:</span></span>

- <span data-ttu-id="392f3-289">식별된 사용자 결과 및 위험 발견에 대한 시각적 개요를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-289">Get a visual overview of identified user results and risks found.</span></span>

- <span data-ttu-id="392f3-290">전체 경고 세부 정보를 표시하는 플라이아웃 페이지를 열 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-290">Select a user to open a fly-out page that shows the full alert details.</span></span>

### <a name="machine-investigation"></a><span data-ttu-id="392f3-291">컴퓨터 조사</span><span class="sxs-lookup"><span data-stu-id="392f3-291">Machine investigation</span></span>

<span data-ttu-id="392f3-292">컴퓨터 **탭에서** 조사의 일부로 식별된 모든 컴퓨터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-292">On the **Machines** tab, you can see all the machines identified as part of the investigation.</span></span>

![AIR 조사 컴퓨터 페이지](../../media/air-investigationmachinepage.png)

<span data-ttu-id="392f3-294">일부 플레이북의 일부로 AIR은 전자 메일 위협을 장치(예: Zapped 맬웨어)에 상관 관계화합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-294">As part of some playbooks, AIR correlates email threats to devices (for example, Zapped malware).</span></span> <span data-ttu-id="392f3-295">예를 들어 조사는 악성 파일 해시를 [끝점용 Microsoft Defender로](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) 전달하여 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-295">For example, an investigation passes a malicious file hash across to [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) to investigate.</span></span> <span data-ttu-id="392f3-296">이렇게 하면 사용자에 대한 관련 컴퓨터를 자동화된 조사를 통해 클라우드와 끝점에서 위협이 모두 해결되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-296">This allows for automated investigation of relevant machines for your users, to help ensure that threats are addressed both in the cloud and across your endpoints.</span></span>

<span data-ttu-id="392f3-297">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-297">You can:</span></span>

- <span data-ttu-id="392f3-298">발견된 현재 컴퓨터 및 위협에 대한 시각적 개요를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-298">Get a visual overview of the current machines and threats found.</span></span>

- <span data-ttu-id="392f3-299">Microsoft Defender 보안 센터에서 끝점 조사를 위한 [관련 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) 조사에 해당 보기를 열기 위한 컴퓨터 선택</span><span class="sxs-lookup"><span data-stu-id="392f3-299">Select a machine to open a view that into the related [Microsoft Defender for Endpoint investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) in the Microsoft Defender Security Center.</span></span>

### <a name="entity-investigation"></a><span data-ttu-id="392f3-300">엔터티 조사</span><span class="sxs-lookup"><span data-stu-id="392f3-300">Entity investigation</span></span>

<span data-ttu-id="392f3-301">엔터티 **탭에서** 조사의 일부로 식별 및 분석된 엔터티를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-301">On the **Entities** tab, you can see the entities identified and analyzed as part of the investigation.</span></span>

<span data-ttu-id="392f3-302">여기에서 조사된 엔터티와 엔터티 유형(예: 전자 메일 메시지, 클러스터, IP 주소, 사용자 등)의 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-302">Here, you can see the investigated entities and details of the types of entities, such as email messages, clusters, IP addresses, users, and more.</span></span> <span data-ttu-id="392f3-303">또한 분석된 엔터티 수와 각 엔터티와 연관된 위협도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-303">You can also see how many entities were analyzed, and the threats that were associated with each.</span></span>

![AIR 조사 엔터티 페이지](../../media/air-investigationentitiespage.png)

<span data-ttu-id="392f3-305">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-305">You can:</span></span>

- <span data-ttu-id="392f3-306">발견된 조사 엔터티 및 위협에 대한 시각적 개요를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-306">Get a visual overview of the investigation entities and threats found.</span></span>

- <span data-ttu-id="392f3-307">관련 엔터티 세부 정보를 표시하는 플라이아웃 페이지를 열 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-307">Select an entity to open a fly-out page that shows the related entity details.</span></span>

![AIR 조사 엔터티 세부 정보](../../media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a><span data-ttu-id="392f3-309">Playbook 로그</span><span class="sxs-lookup"><span data-stu-id="392f3-309">Playbook log</span></span>

<span data-ttu-id="392f3-310">로그 **탭에서** 조사 중에 발생한 모든 플레이북 단계를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-310">On the **Log** tab, you can see all the playbook steps that have occurred during the investigation.</span></span> <span data-ttu-id="392f3-311">로그는 AIR의 일부로 Office 365 자동 조사 기능에 의해 완료된 모든 분석기 및 작업의 전체 인벤토리를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-311">The log captures a complete inventory of all analyzers and actions completed by Office 365 auto-investigation capabilities as part of AIR.</span></span> <span data-ttu-id="392f3-312">작업 자체, 설명 및 실제 시작부터 완료까지의 기간을 포함하여 수행되는 모든 단계를 명확하게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-312">It provides a clear view of all the steps taken, including the action itself, a description, and the duration of the actual from start to finish.</span></span>

![AIR 조사 로그 페이지](../../media/air-investigationlogpage.png)

<span data-ttu-id="392f3-314">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-314">You can:</span></span>

- <span data-ttu-id="392f3-315">수행한 플레이북 단계에 대한 시각적 개요를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-315">Get see a visual overview of the playbook steps taken.</span></span>
- <span data-ttu-id="392f3-316">결과를 CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-316">Export the results to a CSV file.</span></span>
- <span data-ttu-id="392f3-317">보기를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-317">Filter the view.</span></span>

### <a name="recommended-actions"></a><span data-ttu-id="392f3-318">권장 작업</span><span class="sxs-lookup"><span data-stu-id="392f3-318">Recommended actions</span></span>

<span data-ttu-id="392f3-319">작업 **탭에서** 조사가 완료된 후 수정에 권장되는 모든 플레이북 작업을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-319">On the **Actions** tab, you can see all the playbook actions that are recommended for remediation after the investigation has completed.</span></span> <span data-ttu-id="392f3-320">작업은 조사가 끝날 때 Microsoft에서 권장하는 단계를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-320">Actions capture the steps Microsoft recommends you take at the end of an investigation.</span></span> <span data-ttu-id="392f3-321">여기서 하나 이상의 작업을 선택하여 수정 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-321">You can take remediation actions here by selecting one or more actions.</span></span>

<span data-ttu-id="392f3-322">승인을 **선택하면** 수정을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-322">Selecting **Approve** allows remediation to begin.</span></span> <span data-ttu-id="392f3-323">적절한 사용 권한이 필요합니다.  탐색기 및 AIR에서 작업을 실행하려면 검색 및 제거 역할이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-323">(Appropriate permissions are needed - the **Search And Purge** role is required to run actions from Explorer and AIR).</span></span>

<span data-ttu-id="392f3-324">예를 들어 보안 읽기는 작업을 볼 수 있지만 승인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-324">For example, a Security Reader can view actions, but not approve them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="392f3-325">모든 작업을 승인할 것은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-325">You do not have to approve every action.</span></span> <span data-ttu-id="392f3-326">권장 작업에 동의하지 않는 경우 또는 조직에서 특정 유형의 작업을 선택하지  않는 경우 작업을 거부하거나 무시하고 아무 작업도 수행하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-326">If you do not agree with the recommended action or your organization does not choose certain types of actions, then you can choose to **Reject** the actions or simply ignore them and take no action.</span></span>
> <span data-ttu-id="392f3-327">모든 작업을 수락 및/또는 거부하면 조사가 완전히 닫히고(상태가 수정됩니다) 일부 작업이 불완전해진 상태로 두면 조사 상태가 부분적으로 수정된 상태로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-327">Approving and/or rejecting all actions lets the investigation fully close (status becomes remediated), while leaving some actions incomplete results in the investigation status changing to a partially remediated state.</span></span>

![AIR 조사 작업 페이지](../../media/air-investigationactionspage.png)

<span data-ttu-id="392f3-329">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-329">You can:</span></span>

- <span data-ttu-id="392f3-330">플레이북 권장 작업에 대한 시각적 개요를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-330">Get a visual overview of the playbook-recommended actions.</span></span>
- <span data-ttu-id="392f3-331">단일 작업 또는 여러 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-331">Select a single action or multiple actions.</span></span>
- <span data-ttu-id="392f3-332">설명을 통해 권장 작업을 승인하거나 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-332">Approve or reject recommended actions with comments.</span></span>
- <span data-ttu-id="392f3-333">결과를 CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-333">Export the results to a CSV file.</span></span>
- <span data-ttu-id="392f3-334">보기를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="392f3-334">Filter the view.</span></span>

## <a name="next-steps"></a><span data-ttu-id="392f3-335">다음 단계</span><span class="sxs-lookup"><span data-stu-id="392f3-335">Next steps</span></span>

- [<span data-ttu-id="392f3-336">보류 중인 작업 검토 및 승인</span><span class="sxs-lookup"><span data-stu-id="392f3-336">Review and approve pending actions</span></span>](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
