---
title: Microsoft 365에서 자동화 된 조사 결과 보기
keywords: AIR, autoIR, ATP, 자동화, 조사, 대응, 재구성, 위협, 고급, 위협, 보호
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
description: Microsoft 365에서 자동화 된 조사가 진행 되는 동안과 후에는 결과 및 주요 발견 사항을 볼 수 있습니다.
ms.date: 11/05/2020
ms.openlocfilehash: 4dc74987619c3f958c874927af6e4240b9d7e154
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357288"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a><span data-ttu-id="a574d-104">Microsoft 365의 자동화 된 조사에 대 한 세부 정보 및 결과</span><span class="sxs-lookup"><span data-stu-id="a574d-104">Details and results of an automated investigation in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a574d-105">[Microsoft Defender For Office 365](office-365-atp.md)에서 [자동 조사가](office-365-air.md) 발생 하면 자동화 된 조사 프로세스 중에 해당 조사에 대 한 세부 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-105">When an [automated investigation](office-365-air.md) occurs in [Microsoft Defender for Office 365](office-365-atp.md), details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="a574d-106">필요한 사용 권한이 있는 경우 Microsoft 365 보안 센터에서 해당 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-106">If you have the necessary permissions, you can view those details in the Microsoft 365 security center.</span></span> <span data-ttu-id="a574d-107">조사 세부 정보에는 최신 상태 및 보류 중인 모든 작업을 승인 하는 기능이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-107">Investigation details provide you with up-to-date status, and the ability to approve any pending actions.</span></span>

## <a name="investigation-status"></a><span data-ttu-id="a574d-108">조사 상태</span><span class="sxs-lookup"><span data-stu-id="a574d-108">Investigation status</span></span>

<span data-ttu-id="a574d-109">조사 상태는 분석 및 작업의 진행률을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-109">The investigation status indicates the progress of the analysis and actions.</span></span> <span data-ttu-id="a574d-110">조사가 실행 되 면 상태가 변경 되어 위협이 발견 되었는지 여부와 작업이 승인 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-110">As the investigation runs, status changes to indicate whether threats were found, and whether actions have been approved.</span></span>

|<span data-ttu-id="a574d-111">상태</span><span class="sxs-lookup"><span data-stu-id="a574d-111">Status</span></span>|<span data-ttu-id="a574d-112">설명</span><span class="sxs-lookup"><span data-stu-id="a574d-112">Description</span></span>|
|---|---|
|<span data-ttu-id="a574d-113">**시작 중**</span><span class="sxs-lookup"><span data-stu-id="a574d-113">**Starting**</span></span>|<span data-ttu-id="a574d-114">조사가 트리거된 후 실행이 시작 될 때까지 기다리는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-114">The investigation has been triggered and waiting to start running.</span></span>|
|<span data-ttu-id="a574d-115">**실행 중**</span><span class="sxs-lookup"><span data-stu-id="a574d-115">**Running**</span></span>|<span data-ttu-id="a574d-116">조사 프로세스가 시작 되어 진행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-116">The investigation process has started and is underway.</span></span> <span data-ttu-id="a574d-117">이 상태는 [보류 중인 작업이](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) 승인 된 경우에도 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-117">This state also occurs when [pending actions](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) are approved.</span></span>|
|<span data-ttu-id="a574d-118">**발견 된 위협 없음**</span><span class="sxs-lookup"><span data-stu-id="a574d-118">**No Threats Found**</span></span>|<span data-ttu-id="a574d-119">조사가 완료 되었으며 위협 (사용자 계정, 전자 메일 메시지, URL 또는 파일)이 식별 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-119">The investigation has finished and no threats (user account, email message, URL, or file) were identified.</span></span> <p> <span data-ttu-id="a574d-120">**팁**: 잘못 된 것으로 의심 되는 경우 (예를 들어 가양성)에는 [Threat Explorer](threat-explorer.md)를 사용 하 여 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-120">**TIP**: If you suspect something was missed (such as a false negative), you can take action using [Threat Explorer](threat-explorer.md).</span></span>|
|<span data-ttu-id="a574d-121">**발견 된 위협**</span><span class="sxs-lookup"><span data-stu-id="a574d-121">**Threats Found**</span></span>|<span data-ttu-id="a574d-122">자동 조사에서 문제가 발견 되었지만 해당 문제를 해결 하기 위한 특정 수정 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-122">The automated investigation found issues, but there are no specific remediation actions to resolve those issues.</span></span> <p> <span data-ttu-id="a574d-123">어떤 유형의 사용자 활동이 식별 되었지만 정리 작업을 사용할 수 없는 경우 발견 되는 **위협이** 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-123">The **Threats Found** status can occur when some type of user activity was identified but no cleanup actions are available.</span></span> <span data-ttu-id="a574d-124">예를 들면 다음과 같은 사용자 작업을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-124">Examples include any of the following user activities:</span></span> <ul><li><span data-ttu-id="a574d-125">DLP ( [데이터 손실 방지](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) ) 이벤트</span><span class="sxs-lookup"><span data-stu-id="a574d-125">A [data loss prevention](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) (DLP) event</span></span></li><li><span data-ttu-id="a574d-126">메일을 보내는 변칙</span><span class="sxs-lookup"><span data-stu-id="a574d-126">An email sending anomaly</span></span></li><li><span data-ttu-id="a574d-127">보낸 맬웨어</span><span class="sxs-lookup"><span data-stu-id="a574d-127">Sent malware</span></span></li><li><span data-ttu-id="a574d-128">보낸 피싱</span><span class="sxs-lookup"><span data-stu-id="a574d-128">Sent phish</span></span></li></ul> <p> <span data-ttu-id="a574d-129">검토를 통해 수정할 수 있는 악성 Url, 파일 또는 전자 메일 메시지와 수정할 사서함 활동 (예: 전달 규칙 또는 위임 해제)이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-129">The investigation found no malicious URLs, files, or email messages to remediate, and no mailbox activity to fix, such as turning off forwarding rules or delegation.</span></span> <p> <span data-ttu-id="a574d-130">**팁**: 잘못 된 것으로 의심 되는 경우 (예를 들어 가양성)에는 [위협 탐색기](threat-explorer.md)를 사용 하 여 검토 하 고 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-130">**TIP**: If you suspect something was missed (such as a false negative), you can investigate and take action using [Threat Explorer](threat-explorer.md).</span></span>|
|<span data-ttu-id="a574d-131">**시스템 종료**</span><span class="sxs-lookup"><span data-stu-id="a574d-131">**Terminated By System**</span></span>|<span data-ttu-id="a574d-132">조사가 중지 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-132">The investigation stopped.</span></span> <span data-ttu-id="a574d-133">다음과 같은 여러 가지 이유로 인해 조사가 중단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-133">An investigation can stop for several reasons:</span></span> <ul><li><span data-ttu-id="a574d-134">조사에 대 한 보류 중인 작업이 만료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-134">The investigation's pending actions expired.</span></span> <span data-ttu-id="a574d-135">1 주일 동안 승인 대기 한 후 보류 중인 작업 시간이 초과 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-135">Pending actions time out after awaiting approval for one week.</span></span></li><li><span data-ttu-id="a574d-136">작업이 너무 많습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-136">There are too many actions.</span></span> <span data-ttu-id="a574d-137">예를 들어 너무 많은 사용자가 악성 Url을 클릭 하는 경우 조사 기능이 모든 분석기를 실행 하는 것을 초과할 수 있으므로 조사가 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-137">For example, if there are too many users clicking on malicious URLs, it can exceed the investigation's ability to run all the analyzers, so the investigation halts.</span></span></li></ul> <p> <span data-ttu-id="a574d-138">**팁**: 작업을 수행 하기 전에 조사가 중단 되는 경우 [Threat Explorer](threat-explorer.md) 를 사용 하 여 위협을 찾아서 해결 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="a574d-138">**TIP**: If an investigation halts before actions were taken, try using [Threat Explorer](threat-explorer.md) to find and address threats.</span></span>|
|<span data-ttu-id="a574d-139">**보류 중인 작업**</span><span class="sxs-lookup"><span data-stu-id="a574d-139">**Pending Action**</span></span>|<span data-ttu-id="a574d-140">조사 결과 악성 전자 메일, 악의적인 URL 또는 위험한 사서함 설정과 같은 위협을 발견 하 고 해당 위협이 [승인을 기다리는](air-review-approve-pending-completed-actions.md)작업을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-140">The investigation has found a threat, such as a malicious email, a malicious URL, or a risky mailbox setting, and an action to remediate that threat is [awaiting approval](air-review-approve-pending-completed-actions.md).</span></span> <p> <span data-ttu-id="a574d-141">해당 하는 작업을 수행 하는 모든 위협이 발견 되 면 **보류 중인 작업** 상태가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-141">The **Pending Action** state is triggered when any threat with a corresponding action is found.</span></span> <span data-ttu-id="a574d-142">그러나 조사가 실행 됨에 따라 보류 중인 작업의 목록이 늘어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-142">However, the list of pending actions can increase as an investigation runs.</span></span> <span data-ttu-id="a574d-143">[조사 로그](#playbook-log) 를 확인 하 여 다른 항목의 완료가 아직 보류 중인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-143">Check the [investigation log](#playbook-log) to see if other items are still pending completion.</span></span>|
|<span data-ttu-id="a574d-144">**수정**</span><span class="sxs-lookup"><span data-stu-id="a574d-144">**Remediated**</span></span>|<span data-ttu-id="a574d-145">조사가 완료 되 고 모든 재구성 작업이 승인 되었습니다 (완전히 재구성 된 것으로 표시 됨).</span><span class="sxs-lookup"><span data-stu-id="a574d-145">The investigation finished and all remediation actions were approved (this is noted as fully remediated).</span></span> <p> <span data-ttu-id="a574d-146">**참고**: 승인 된 재구성 작업은 작업이 수행 되지 않도록 하는 오류를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-146">**NOTE**: Approved remediation actions can have errors that prevent the actions from being taken.</span></span> <span data-ttu-id="a574d-147">재구성 작업이 성공적으로 완료 되었는지 여부에 관계 없이 조사 상태는 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-147">Regardless of whether remediation actions are successfully completed, the investigation status does not change.</span></span> <span data-ttu-id="a574d-148">자세한 결과는 [조사 로그](#playbook-log) 를 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a574d-148">Check the [investigation log](#playbook-log) for detailed results.</span></span>|
|<span data-ttu-id="a574d-149">**부분 재구성**</span><span class="sxs-lookup"><span data-stu-id="a574d-149">**Partially Remediated**</span></span>|<span data-ttu-id="a574d-150">조사 결과 재구성 작업이 수행 되 고 일부는 승인 및 완료 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-150">The investigation resulted in remediation actions, and some were approved and completed.</span></span> <span data-ttu-id="a574d-151">다른 작업은 여전히 [보류 중](air-review-approve-pending-completed-actions.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-151">Other actions are still [pending](air-review-approve-pending-completed-actions.md).</span></span>|
|<span data-ttu-id="a574d-152">**실패**</span><span class="sxs-lookup"><span data-stu-id="a574d-152">**Failed**</span></span>|<span data-ttu-id="a574d-153">하나 이상의 조사 분석기에서 제대로 완료 되지 못한 문제가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-153">At least one investigation analyzer ran into a problem where it could not complete properly.</span></span> <p> <span data-ttu-id="a574d-154">**참고**: 재구성 작업이 승인 된 후 조사가 실패 하면 재구성 작업은 여전히 성공적으로 수행 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-154">**NOTE**: If an investigation fails after remediation actions were approved, the remediation actions might still have succeeded.</span></span> <span data-ttu-id="a574d-155">자세한 결과는 [조사 로그](#playbook-log) 를 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a574d-155">Check the [investigation log](#playbook-log) for detailed results.</span></span>|
|<span data-ttu-id="a574d-156">**제한에 의해 대기**</span><span class="sxs-lookup"><span data-stu-id="a574d-156">**Queued By Throttling**</span></span>|<span data-ttu-id="a574d-157">조사가 큐에 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-157">An investigation is being held in a queue.</span></span> <span data-ttu-id="a574d-158">다른 조사가 완료 되 면 대기 중인 조사가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-158">When other investigations complete, queued investigations begin.</span></span> <span data-ttu-id="a574d-159">제한을 사용 하면 서비스 성능이 저하 되는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-159">Throttling helps avoid poor service performance.</span></span>  <p> <span data-ttu-id="a574d-160">**팁**: 보류 중인 작업은 새로 실행할 수 있는 조사 횟수를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-160">**TIP**: Pending actions can limit how many new investigations can run.</span></span> <span data-ttu-id="a574d-161">[보류 중인 작업을 승인 하거나 거부](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-161">Make sure to [approve (or reject) pending actions](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions).</span></span>|
|<span data-ttu-id="a574d-162">**제한에 의해 종료 됨**</span><span class="sxs-lookup"><span data-stu-id="a574d-162">**Terminated By Throttling**</span></span>|<span data-ttu-id="a574d-163">큐에 너무 오래 된 조사가 대기 중인 경우 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-163">If an investigation is held in the queue too long, it stops.</span></span> <p> <span data-ttu-id="a574d-164">**팁**: [위협 탐색기에서 조사를 시작할](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-164">**TIP**: You can [start an investigation from Threat Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>|
|

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="a574d-165">조사 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="a574d-165">View details of an investigation</span></span>

1. <span data-ttu-id="a574d-166">보안 & 준수 센터 ()로 이동 [https://protection.office.com](https://protection.office.com) 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-166">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="a574d-167">다음 작업 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-167">Do one of the following actions:</span></span>

    - <span data-ttu-id="a574d-168">**위협 관리** \> **대시보드로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-168">Go to **Threat management** \> **Dashboard**.</span></span> <span data-ttu-id="a574d-169">그러면 [보안 대시보드가](security-dashboard.md)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-169">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="a574d-170">[보안 대시보드](security-dashboard.md)위쪽에 AIR widget이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-170">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="a574d-171">**조사 요약과** 같은 위젯을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-171">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="a574d-172">**위협 관리** \> **조사** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-172">Go to **Threat management** \> **Investigations**.</span></span>

    <span data-ttu-id="a574d-173">어느 방법을 사용 하 든 조사 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-173">Either method takes you to a list of investigations.</span></span>

    ![AIR의 주 조사 페이지](../../media/air-maininvestigationpage.png)

3. <span data-ttu-id="a574d-175">조사 목록에서 **ID** 열의 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-175">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="a574d-176">그러면 보기의 조사 그래프부터 시작 하 여 조사 세부 정보 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-176">This opens investigation details page, starting with the investigation graph in view.</span></span>

    ![AIR 조사 그래프 페이지](../../media/air-investigationgraphpage.png)

   <span data-ttu-id="a574d-178">여러 탭을 사용 하 여 조사에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="a574d-178">Use the various tabs to learn more about the investigation.</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="a574d-179">조사와 관련 된 경고에 대 한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="a574d-179">View details about an alert related to an investigation</span></span>

<span data-ttu-id="a574d-180">특정 유형의 경고는 Microsoft 365에서 자동화 된 조사를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-180">Certain kinds of alerts trigger automated investigation in Microsoft 365.</span></span> <span data-ttu-id="a574d-181">자세한 내용은 [자동화 된 조사를 트리거하는 경고 정책](office-365-air.md#which-alert-policies-trigger-automated-investigations)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a574d-181">To learn more, see [alert policies that trigger automated investigations](office-365-air.md#which-alert-policies-trigger-automated-investigations).</span></span>

<span data-ttu-id="a574d-182">다음 절차에 따라 자동화 된 조사에 연결 된 경고에 대 한 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-182">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="a574d-183">보안 & 준수 센터 ()로 이동 [https://protection.office.com](https://protection.office.com) 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-183">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="a574d-184">**위협 관리** \> **조사** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-184">Go to **Threat management** \> **Investigations**.</span></span>

3. <span data-ttu-id="a574d-185">조사 목록에서 **ID** 열의 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-185">In the list of investigations, select an item in the **ID** column.</span></span>

4. <span data-ttu-id="a574d-186">조사에 대 한 세부 정보를 연 상태에서 **알림** 탭을 선택 합니다. 조사를 트리거한 모든 경고가 여기에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-186">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="a574d-187">목록에서 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-187">Select an item in the list.</span></span> <span data-ttu-id="a574d-188">플라이 아웃이 열리고 경고에 대 한 세부 정보와 추가 정보 및 작업에 대 한 링크가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-188">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="a574d-189">플라이 아웃에 대 한 정보를 검토 하 고, 특정 경고에 따라 사용자에 대 한 **해결**, **억제** 또는 **알림** 등의 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-189">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span>

    - <span data-ttu-id="a574d-190">**확인** 은 경고를 닫는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-190">**Resolve** is equivalent to closing an alert</span></span>

    - <span data-ttu-id="a574d-191">정책이 지정 된 기간에 대해 알림을 트리거하지 **않도록 설정 합니다** .</span><span class="sxs-lookup"><span data-stu-id="a574d-191">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>

    - <span data-ttu-id="a574d-192">**사용자에** 게 사용자의 전자 메일 주소가 이미 입력 된 전자 메일을 시작 하 고, 보안 운영 팀에서 해당 사용자에 게 메시지를 입력할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-192">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="a574d-193">이는 [위협 탐색기](threat-explorer.md)를 사용 하 여 받는 사람에 게 메시지를 보내는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-193">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>

## <a name="how-to-use-the-various-tabs"></a><span data-ttu-id="a574d-194">다양 한 탭을 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="a574d-194">How to use the various tabs</span></span>

<span data-ttu-id="a574d-195">다음 섹션에서는 자동화 된 조사 페이지의 다양 한 탭과 정보 사용 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-195">The following sections walk you through the various tabs on the automated investigations page and how you can use the information.</span></span>

### <a name="automated-investigations-page"></a><span data-ttu-id="a574d-196">자동화 된 조사 페이지</span><span class="sxs-lookup"><span data-stu-id="a574d-196">Automated investigations page</span></span>

<span data-ttu-id="a574d-197">자동화 된 조사 페이지에 조직의 조사 및 현재 상태가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-197">The automated investigations page shows your organization's investigations and their current states.</span></span>

![AIR의 주 조사 페이지](../../media/air-maininvestigationpage.png)

<span data-ttu-id="a574d-199">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-199">You can:</span></span>

- <span data-ttu-id="a574d-200">조사로 직접 이동 합니다 ( **조사 ID** 선택).</span><span class="sxs-lookup"><span data-stu-id="a574d-200">Navigate directly to an investigation (select an **Investigation ID**).</span></span>

- <span data-ttu-id="a574d-201">필터를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-201">Apply filters.</span></span> <span data-ttu-id="a574d-202">**조사 유형**, **시간 범위**, **상태** 또는 이들의 조합 중에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-202">Choose from **Investigation Type**, **Time range**, **Status**, or a combination of these.</span></span>

- <span data-ttu-id="a574d-203">데이터를 .csv 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-203">Export the data to a .csv file.</span></span>

### <a name="investigation-graph"></a><span data-ttu-id="a574d-204">조사 그래프</span><span class="sxs-lookup"><span data-stu-id="a574d-204">Investigation graph</span></span>

<span data-ttu-id="a574d-205">특정 조사를 열면 조사 그래프 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-205">When you open a specific investigation, you see the investigation graph page.</span></span> <span data-ttu-id="a574d-206">이 페이지에는 전자 메일 메시지, 사용자 (및 해당 활동), 트리거된 알림의 일부로 자동 조사 되는 장치 등의 다양 한 엔터티가 모두 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-206">This page shows all the different entities: email messages, users (and their activities), and devices that were automatically investigated as part of the alert that was triggered.</span></span>

![AIR 조사 그래프 페이지](../../media/air-investigationgraphpage.png)

<span data-ttu-id="a574d-208">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-208">You can:</span></span>

- <span data-ttu-id="a574d-209">현재 조사에 대 한 시각적 개요를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-209">Get a visual overview of the current investigation.</span></span>
- <span data-ttu-id="a574d-210">조사 기간에 대 한 요약을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-210">View a summary of the investigation duration.</span></span>
- <span data-ttu-id="a574d-211">시각화에서 노드를 선택 하 여 해당 노드의 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-211">Select a node in the visualization to view details for that node.</span></span>
- <span data-ttu-id="a574d-212">위쪽에서 탭을 선택 하 여 해당 탭의 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-212">Select a tab across the top to view details for that tab.</span></span>

### <a name="alert-investigation"></a><span data-ttu-id="a574d-213">경고 조사</span><span class="sxs-lookup"><span data-stu-id="a574d-213">Alert investigation</span></span>

<span data-ttu-id="a574d-214">조사에 대 한 **알림** 탭에서 조사와 관련 된 경고를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-214">On the **Alerts** tab for an investigation, you can see alerts relevant to the investigation.</span></span> <span data-ttu-id="a574d-215">세부 정보에는 조사를 트리거한 경고 및 확인에 상관 된 위험한 로그인, [DLP 정책](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) 위반 등의 상호 관련 된 경고가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-215">Details include the alert that triggered the investigation and other correlated alerts, such as risky sign-in, [DLP policy](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) violations, etc., that are correlated to the investigation.</span></span> <span data-ttu-id="a574d-216">이 페이지에서는 보안 분석가가 개별 경고에 대 한 추가 세부 정보를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-216">From this page, a security analyst can also view additional details on individual alerts.</span></span>

![AIR 알림 페이지](../../media/air-investigationalertspage.png)

<span data-ttu-id="a574d-218">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-218">You can:</span></span>

- <span data-ttu-id="a574d-219">현재 트리거하는 경고 및 관련 경고에 대 한 시각적 개요를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-219">Get a visual overview of the current triggering alert and any associated alerts.</span></span>
- <span data-ttu-id="a574d-220">목록에서 알림을 선택 하 여 전체 알림 세부 정보를 표시 하는 플라이 아웃 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-220">Select an alert in the list to open a fly-out page that shows full alert details.</span></span>

### <a name="email-investigation"></a><span data-ttu-id="a574d-221">전자 메일 조사</span><span class="sxs-lookup"><span data-stu-id="a574d-221">Email investigation</span></span>

<span data-ttu-id="a574d-222">조사를 위해 **전자 메일** 탭에서 원본 전자 메일과 조사 과정에서 확인 된 유사 전자 메일의 클러스터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-222">On the **Email** tab for an investigation, you can see the original emails and the clusters of similar email identified as part of the investigation.</span></span> <span data-ttu-id="a574d-223">**전자 메일** 탭에는 사용자가 보고 한 전자 메일 세부 정보, 보고 된 원래 전자 메일, 맬웨어/피싱로 인 한 전자 메일 메시지 등 조사와 관련 된 전자 메일 항목도 표시 됩니다 zapped.</span><span class="sxs-lookup"><span data-stu-id="a574d-223">The **Email** tab also shows email items related to the investigation, such as the user-reported email details, the original email reported, the email message(s) zapped due to malware/phish, etc.</span></span>

![AIR 전자 메일 조사 페이지](../../media/air-investigationemailpage.png)

<span data-ttu-id="a574d-225">전자 메일 조사를 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-225">With email investigation, you can:</span></span>

- <span data-ttu-id="a574d-226">현재 클러스터링 결과 및 발견 된 위협에 대 한 시각적 개요를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-226">Get a visual overview of the current clustering results and threats found.</span></span>
- <span data-ttu-id="a574d-227">클러스터 엔터티 또는 위협 목록을 클릭 하 여 전체 알림 세부 정보를 표시 하는 플라이 아웃 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-227">Click a cluster entity or a threat list to open a fly-out page that shows the full alert details.</span></span>
- <span data-ttu-id="a574d-228">전자 메일 클러스터 **세부 정보** 탭 위쪽의 **탐색기에서 열기** 링크를 클릭 하 여 전자 메일 클러스터를 자세히 조사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-228">Further investigate the email cluster by clicking the **Open in Explorer** link at the top of the **Email cluster details** tab</span></span>

![플라이 아웃 세부 정보를 사용한 AIR 조사 전자 메일](../../media/air-investigationemailpageflyoutdetails.png)

<span data-ttu-id="a574d-230">조직의 사용자가 주고 받으며 전자 메일 통신 및 공격에 대 한 다중 사용자 특성을 포함 하는 전자 메일의 양이 주어 지 면 다음 프로세스에 상당한 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-230">Given the sheer volume of email that users in an organization send and receive, plus the multi-user nature of email communications and attacks, the following process can take a significant amount of time:</span></span>

1. <span data-ttu-id="a574d-231">메시지 헤더, 본문, URL 및 첨부 파일의 비슷한 특성을 기반으로 전자 메일 메시지를 클러스터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-231">Clustering email messages based on similar attributes from a message header, body, URL, and attachments.</span></span>
2. <span data-ttu-id="a574d-232">악성 전자 메일을 좋은 전자 메일과 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-232">Separating malicious email from the good email.</span></span>
3. <span data-ttu-id="a574d-233">악성 전자 메일 메시지에 대 한 작업 수행</span><span class="sxs-lookup"><span data-stu-id="a574d-233">Taking action on malicious email messages.</span></span>

<span data-ttu-id="a574d-234">AIR에서는이 프로세스를 자동화 하 여 조직의 보안 팀 시간과 노력을 절약 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-234">AIR automates this process, saving your organization's security team time and effort.</span></span>

#### <a name="types-of-email-clusters"></a><span data-ttu-id="a574d-235">전자 메일 클러스터의 유형</span><span class="sxs-lookup"><span data-stu-id="a574d-235">Types of email clusters</span></span>

<span data-ttu-id="a574d-236">전자 메일 분석 단계에서 서로 다른 세 가지 유형의 전자 메일 클러스터 (모든 조사), 지표 클러스터 (모든 조사) 및 사서함/사용자 클러스터를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-236">Three different types of email clusters can be identified during the email analysis step: similarity clusters (all investigations), indicator clusters (all investigations), and mailbox/user clusters.</span></span> <span data-ttu-id="a574d-237">다음 표에서는 이러한 유형의 전자 메일 클러스터에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-237">The following table describes these types of email clusters.</span></span>

|<span data-ttu-id="a574d-238">전자 메일 클러스터</span><span class="sxs-lookup"><span data-stu-id="a574d-238">Email cluster</span></span>|<span data-ttu-id="a574d-239">설명</span><span class="sxs-lookup"><span data-stu-id="a574d-239">Description</span></span>|
|---|---|
|<span data-ttu-id="a574d-240">유사성 클러스터</span><span class="sxs-lookup"><span data-stu-id="a574d-240">Similarity clusters</span></span>|<span data-ttu-id="a574d-241">비슷한 보낸 사람 및 콘텐츠 특성이 있는 전자 메일에 대해 사냥으로 식별 되는 전자 메일 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-241">Email messages identified by hunting for emails with similar sender and content attributes.</span></span> <span data-ttu-id="a574d-242">이러한 클러스터는 원래 검색 결과를 기반으로 악의적인 콘텐츠를 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-242">These clusters are evaluated for malicious content based on the original detection findings.</span></span> <span data-ttu-id="a574d-243">악의적인 전자 메일 검색이 충분히 포함 된 전자 메일 클러스터가 악성으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-243">Email clusters that contain enough malicious email detections are considered malicious.</span></span>|
|<span data-ttu-id="a574d-244">지표 클러스터</span><span class="sxs-lookup"><span data-stu-id="a574d-244">Indicator clusters</span></span>|<span data-ttu-id="a574d-245">원본 전자 메일에서 동일한 지표 엔티티 (파일 해시 또는 URL)에 대해 사냥을 통해 식별 된 전자 메일 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-245">Email messages that are identified by hunting for the same indicator entity (file hash or URL) from the original email.</span></span> <span data-ttu-id="a574d-246">원본 파일/URL 엔터티가 악성으로 식별 되 면이 엔터티가 포함 된 전자 메일 메시지의 전체 클러스터에 결과 표시기가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-246">When the original file/URL entity is identified as malicious, AIR applies the indicator verdict to the entire cluster of email messages containing that entity.</span></span> <span data-ttu-id="a574d-247">맬웨어로 식별 된 파일은 해당 파일을 포함 하는 전자 메일 메시지의 클러스터가 맬웨어 전자 메일 메시지로 취급 됨을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-247">A file identified as malware means that the cluster of email messages containing that file are treated as malware email messages.</span></span>|
|<span data-ttu-id="a574d-248">사서함/사용자 클러스터</span><span class="sxs-lookup"><span data-stu-id="a574d-248">Mailbox/user clusters</span></span>|<span data-ttu-id="a574d-249">사용자 손상 조사에 참여 한 사용자와 관련 된 전자 메일 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-249">Email messages related to the user involved in a user compromise investigation.</span></span> <span data-ttu-id="a574d-250">이러한 전자 메일 클러스터는 보안 운영 팀의 추가 분석을 위한 것으로, 전자 메일 재구성 작업을 생성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-250">These email clusters are for further analysis by the security operations team and will not generate email remediation actions.</span></span> <p> <span data-ttu-id="a574d-251">손상 된 사용자 보안 playbook는 사서함에서 보내는 전자 메일의 잠재적 영향을 이해 하기 위해 분석 중인 사용자가 보내는 전자 메일을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-251">The compromised user security playbook  reviews the emails being sent by the user being analyzed in order to understand the potential impact of the emails being sent from the mailbox.</span></span>|

> [!NOTE]
> <span data-ttu-id="a574d-252">클러스터링의 목표는 공격이 나 캠페인의 일부로 동일한 보낸 사람이 보낸 다른 관련 전자 메일 메시지를 찾아서 찾는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-252">The goal of clustering is to hunt and find other related email messages that are sent by the same sender as part of an attack or a campaign.</span></span>  <span data-ttu-id="a574d-253">경우에 따라 합법적인 전자 메일이 조사를 트리거할 수도 있습니다 (예: 사용자가 마케팅 전자 메일을 보고 함).</span><span class="sxs-lookup"><span data-stu-id="a574d-253">In some cases, legitimate email might trigger an investigation (for example, a user reports a marketing email).</span></span>  <span data-ttu-id="a574d-254">이 시나리오에서 전자 메일 클러스터링은 전자 메일 클러스터가 악성이 아닌 것을 식별 하며 적절 하 게 수행 되 면 위협을 나타내거나 전자 메일을 제거할 것을 권장 **하지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-254">In these scenarios, the email clustering should identify that email clusters are not malicious – when it appropriately does so, it will **not** indicate a threat, nor will it recommend email removal.</span></span>

#### <a name="email-classifications"></a><span data-ttu-id="a574d-255">전자 메일 분류</span><span class="sxs-lookup"><span data-stu-id="a574d-255">Email classifications</span></span>

<span data-ttu-id="a574d-256">전자 메일 메시지가 분석 되 면 *악성*, *의심* 또는 *치료* ( *위협으로 식별 되지 않음*)로 분류 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-256">As email messages are analyzed, they are classified as *malicious*, *suspicious*, or *clean* (as in, *not identified as a threat*):</span></span>

- <span data-ttu-id="a574d-257">사서함/사용자가 보낸 *악성 전자 메일* 은 사서함/계정의 잠재적 손상을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-257">*Malicious emails* sent from the mailbox/user  indicate potential compromise of the mailbox/account.</span></span> <span data-ttu-id="a574d-258">손상의 일환으로 악성 전자 메일에 의해 영향을 받을 수 있는 다른 사용자/사서함이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-258">Other users/mailboxes that are potentially impacted by malicious email as part of a compromise are shown.</span></span>

- <span data-ttu-id="a574d-259">사서함/사용자가 보낸 *의심 스러운 전자 메일* 은 손상 된 계정 또는 원치 않는 전자 메일 활동의 가능성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-259">*Suspicious emails* sent by the mailbox/user indicate the potential for a compromised account or unwanted email activity.</span></span> <span data-ttu-id="a574d-260">이러한 메시지에는 사서함에서 전송 된 모든 스팸/대량 전자 메일이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-260">These messages include any spam/bulk email sent from the mailbox.</span></span>

- <span data-ttu-id="a574d-261">사서함/사용자가 위협에 대 한 것으로 간주 되는 전자 *메일을 제거* 하면 보안 운영 팀에 게 전송 된 합법적인 사용자 전자 메일의 보기를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-261">*Clean emails* (emails that are considered not a threat) sent by the mailbox/user can provide your security operations team with a view of legitimate user emails sent.</span></span> <span data-ttu-id="a574d-262">그러나 전자 메일 계정이 손상 된 경우에도 이러한 전자 메일에는 데이터 exfiltration이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-262">However, these emails can also include data exfiltration if the email account is compromised.</span></span>

#### <a name="more-about-email-counts"></a><span data-ttu-id="a574d-263">전자 메일 개수에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="a574d-263">More about email counts</span></span>

<span data-ttu-id="a574d-264">전자 메일 탭에 식별 된 전자 메일 개수는 현재 **전자 메일** 탭에 표시 되는 모든 전자 메일 메시지의 총 합계를 나타냅니다. 전자 메일 메시지는 여러 클러스터에 존재 하기 때문에, 확인 되 고 수정 작업의 영향을 받는 전자 메일 메시지의 실제 총 수는 모든 클러스터 및 원래 받는 사람의 전자 메일 메시지에 있는 고유한 전자 메일 메시지의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-264">The email count identified on the email tab currently represents the sum total of all email messages that shown on the **Email** tab. Because email messages are present in multiple clusters, the actual total count of email messages identified (and affected by remediation actions) is the count of unique email messages present across all of the clusters and original recipients' email messages.</span></span>

<span data-ttu-id="a574d-265">보안 verdicts, 작업 및 배달 위치는 받는 사람 기준에 따라 다르므로 각 받는 사람에 [대 한 전자](threat-explorer.md) 메일 메시지의 수를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-265">Both [Explorer](threat-explorer.md) and AIR count email messages on a per-recipient basis, because the security verdicts, actions, and delivery locations vary on a per-recipient basis.</span></span> <span data-ttu-id="a574d-266">따라서 세 명의 사용자에 게 전송 되는 원래 전자 메일은 전자 메일 하나가 아닌 총 3 개의 전자 메일 메시지를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-266">Thus, an original email sent to three users counts as a total of three email messages instead of one email.</span></span>

<span data-ttu-id="a574d-267">전자 메일이 여러 작업을 포함 하는 경우 또는 모든 작업을 수행할 때 전자 메일 복사본이 여러 개 있는 경우 처럼 전자 메일을 두 번 이상 계산 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-267">There might be cases where an email gets counted two or more times, such as when an email has multiple actions on it, or when there are multiple copies of the email when all the actions occur.</span></span>

<span data-ttu-id="a574d-268">예를 들어 배달 시 감지 되는 맬웨어 전자 메일은 차단 된 (격리 된) 전자 메일과 바뀐 전자 메일 (위협 파일을 경고 파일로 교체 하 고 사용자의 사서함으로 전달)을 모두 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-268">For example, a malware email that is detected at delivery can result in both a blocked (quarantined) email and a replaced email (threat file replaced with a warning file, then delivered to user's mailbox).</span></span> <span data-ttu-id="a574d-269">시스템에 전자 메일의 복사본이 두 개 있으므로 둘 다 클러스터 수로 계산 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-269">Because there are literally two copies of the email in the system, both might be counted in cluster counts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a574d-270">다음은 주의 해야 할 몇 가지 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-270">Here are a few points to keep in mind:</span></span>
>
> - <span data-ttu-id="a574d-271">전자 메일 개수는 조사 시 계산 되며, 기본 쿼리를 기반으로 하 여 조사 flyouts를 열면 몇 가지 개수가 다시 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-271">Email counts are calculated at the time of the investigation, and some counts are recalculated when you open investigation flyouts (based on an underlying query).</span></span>
>
> - <span data-ttu-id="a574d-272">**전자 메일** 탭의 전자 메일 클러스터에 대해 표시 되는 전자 메일 수와 클러스터 플라이 아웃에 표시 된 전자 메일 수량 값은 조사 시 계산 되며 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-272">The email counts shown for the email clusters on the **Email** tab and the email quantity value shown on cluster flyout are calculated at the time of investigation, and do not change.</span></span>
>
> - <span data-ttu-id="a574d-273">전자 메일 클러스터 플라이 아웃의 **전자 메일** 탭 아래쪽에 표시 되는 전자 메일 수와 탐색기에 표시 되는 전자 메일 메시지의 수에는 조사 초기 분석 후에 받은 전자 메일 메시지가 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-273">The email count shown at the bottom of the **Email** tab of the email cluster flyout and the count of email messages shown in Explorer reflect email messages received after the investigation's initial analysis.</span></span>

<span data-ttu-id="a574d-274">따라서 조사 분석 단계와 관리자가 확인을 검토 하는 시간 사이에 도착 하는 전자 메일 메시지가 5 번 더 표시 되 면 전자 메일 메시지의 원래 수량이 10 개를 보여주는 전자 메일 클러스터가 총 15가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-274">Thus, an email cluster that shows an original quantity of 10 email messages would show an email list total of 15 when five more email messages arrive between the investigation analysis phase and when the admin reviews the investigation.</span></span> <span data-ttu-id="a574d-275">마찬가지로 Microsoft Defender for Office 365 계획 2는 평가판의 경우 7 일 후에 만료 되 고 유료 라이선스의 경우 30 일 후에도 유효 하므로 이전 조사는 탐색기 쿼리 보다 더 높은 개수를 표시 하기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-275">Likewise, old investigations might start showing higher counts than Explorer queries show, because data in Microsoft Defender for Office 365 Plan 2 expires after 7 days for trials and after 30 days for paid licenses.</span></span>

<span data-ttu-id="a574d-276">두 가지 보기의 개수 내역 및 현재 횟수를 모두 보여 주는 것은 조사 당시에 전자 메일 영향을 나타내고 수정이 실행 될 때까지 현재 영향을 나타내도록 하기 위해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-276">Showing both count historical and current counts in different views is done to indicate the email impact at the time of investigation and the current impact up until the time that remediation is run.</span></span>

> [!NOTE]
> <span data-ttu-id="a574d-277">전자 메일 컨텍스트에서 조사를 진행 하는 동안 볼륨 변칙 위협 표면을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-277">In the context of email, you might see a volume anomaly threat surface as part of the investigation.</span></span> <span data-ttu-id="a574d-278">볼륨 변칙은 이전 기간에 비해 조사 이벤트에 대 한 유사한 전자 메일 메시지의 스파이크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-278">A volume anomaly indicates a spike in similar email messages around the investigation event time compared to earlier timeframes.</span></span> <span data-ttu-id="a574d-279">전자 메일 트래픽 (예: 제목 및 보낸 사람 도메인, 본문 유사성 및 보낸 사람 IP)이 비슷한 방식으로 전자 메일을 사용 하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-279">This spike in email traffic with similar characteristics (e.g. subject and sender domain, body similarity and sender IP) is typical of the start of email campaigns or attacks.</span></span>
> <span data-ttu-id="a574d-280">그러나 일반적으로 대량, 스팸 및 합법적인 전자 메일 캠페인은 이러한 특성을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-280">However, bulk, spam, and legitimate email campaigns commonly share these characteristics.</span></span>
>
> <span data-ttu-id="a574d-281">볼륨 예외는 잠재적 위협을 나타내므로, 바이러스 백신 엔진, 샌드 박싱 또는 악의적인 평판을 사용 하 여 식별 된 맬웨어 또는 피싱 위협과 비교 하는 것이 더 심각 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-281">Volume anomalies represent a potential threat, and accordingly could be less severe compared to malware or phish threats that are identified using anti-virus engines, detonation or malicious reputation.</span></span>

### <a name="user-investigation"></a><span data-ttu-id="a574d-282">사용자 조사</span><span class="sxs-lookup"><span data-stu-id="a574d-282">User investigation</span></span>

<span data-ttu-id="a574d-283">**사용자** 탭에서는 조사의 일부로 식별 된 모든 사용자를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-283">On the **Users** tab, you can see all the users identified as part of the investigation.</span></span> <span data-ttu-id="a574d-284">사용자 계정은 이벤트가 발생 하거나 해당 사용자 계정에 영향을 줄 수도 있고 해당 계정이 손상 되었을 수 있음을 나타내는 경우 조사에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-284">User accounts appear in the investigation when there is an event or indication that those user accounts might be affected or compromised.</span></span>

<span data-ttu-id="a574d-285">예를 들어 다음 이미지에서 AIR은 생성 된 새 받은 편지함 규칙을 기반으로 하는 손상 및 예외 표시등을 식별 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-285">For example, in the following image, AIR has identified indicators of compromise and anomalies based on a new inbox rule that was created.</span></span> <span data-ttu-id="a574d-286">조사에 대 한 자세한 내용은이 탭 내의 자세한 보기를 통해 확인할 수 있습니다. 손상 및 변칙에 대 한 표시기에는 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)의 변칙 검색이 포함 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-286">Additional details (evidence) of the investigation are available through detailed views within this tab. Indicators of compromise and anomalies might also include anomaly detections from [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span>

![AIR 조사 사용자 페이지](../../media/air-investigationuserspage.png)

<span data-ttu-id="a574d-288">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-288">You can:</span></span>

- <span data-ttu-id="a574d-289">발견 된 사용자 결과 및 위험에 대 한 시각적 개요를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="a574d-289">Get a visual overview of identified user results and risks found.</span></span>

- <span data-ttu-id="a574d-290">전체 알림 세부 정보를 표시 하는 플라이 아웃 페이지를 열 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-290">Select a user to open a fly-out page that shows the full alert details.</span></span>

### <a name="machine-investigation"></a><span data-ttu-id="a574d-291">컴퓨터 조사</span><span class="sxs-lookup"><span data-stu-id="a574d-291">Machine investigation</span></span>

<span data-ttu-id="a574d-292">**컴퓨터** 탭에서 조사 과정으로 식별 된 모든 컴퓨터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-292">On the **Machines** tab, you can see all the machines identified as part of the investigation.</span></span>

![AIR 조사 컴퓨터 페이지](../../media/air-investigationmachinepage.png)

<span data-ttu-id="a574d-294">일부 playbooks 일부로, AIR에서는 전자 메일 위협을 장치 (예: Zapped 맬웨어)와 연관 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-294">As part of some playbooks, AIR correlates email threats to devices (for example, Zapped malware).</span></span> <span data-ttu-id="a574d-295">예를 들어 조사를 통해 [Microsoft Defender에 대 한](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) 악성 파일 해시를 전달 하 여 끝점을 조사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-295">For example, an investigation passes a malicious file hash across to [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) to investigate.</span></span> <span data-ttu-id="a574d-296">이렇게 하면 사용자에 대 한 관련 시스템을 자동으로 조사 하 여 위협이 클라우드 및 끝점에서 모두 해결 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-296">This allows for automated investigation of relevant machines for your users, to help ensure that threats are addressed both in the cloud and across your endpoints.</span></span>

<span data-ttu-id="a574d-297">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-297">You can:</span></span>

- <span data-ttu-id="a574d-298">발견 된 현재 컴퓨터 및 위협에 대 한 시각적 개요를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-298">Get a visual overview of the current machines and threats found.</span></span>

- <span data-ttu-id="a574d-299">Microsoft Defender 보안 센터에서 [끝점 조사를 위해 관련 Microsoft Defender에 대 한](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) 뷰를 열 컴퓨터를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-299">Select a machine to open a view that into the related [Microsoft Defender for Endpoint investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) in the Microsoft Defender Security Center.</span></span>

### <a name="entity-investigation"></a><span data-ttu-id="a574d-300">엔터티 조사</span><span class="sxs-lookup"><span data-stu-id="a574d-300">Entity investigation</span></span>

<span data-ttu-id="a574d-301">조사 과정의 일부로 확인 및 분석 된 엔터티가 **엔터티** 탭에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-301">On the **Entities** tab, you can see the entities identified and analyzed as part of the investigation.</span></span>

<span data-ttu-id="a574d-302">여기서는 전자 메일 메시지, 클러스터, IP 주소, 사용자 등의 엔터티 유형에 대 한 조사 된 엔터티 및 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-302">Here, you can see the investigated entities and details of the types of entities, such as email messages, clusters, IP addresses, users, and more.</span></span> <span data-ttu-id="a574d-303">또한 분석 된 엔터티 수와 각 엔터티가 연결 된 위협을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-303">You can also see how many entities were analyzed, and the threats that were associated with each.</span></span>

![AIR 조사 엔터티 페이지](../../media/air-investigationentitiespage.png)

<span data-ttu-id="a574d-305">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-305">You can:</span></span>

- <span data-ttu-id="a574d-306">발견 된 조사 엔터티 및 위협에 대 한 시각적 개요를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="a574d-306">Get a visual overview of the investigation entities and threats found.</span></span>

- <span data-ttu-id="a574d-307">엔터티를 선택 하 여 관련 엔터티 세부 정보를 표시 하는 플라이 아웃 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-307">Select an entity to open a fly-out page that shows the related entity details.</span></span>

![AIR 조사 엔터티 세부 정보](../../media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a><span data-ttu-id="a574d-309">Playbook 로그</span><span class="sxs-lookup"><span data-stu-id="a574d-309">Playbook log</span></span>

<span data-ttu-id="a574d-310">**로그** 탭에서는 조사 중에 발생 한 모든 playbook 단계를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-310">On the **Log** tab, you can see all the playbook steps that have occurred during the investigation.</span></span> <span data-ttu-id="a574d-311">이 로그는 AIR의 일부로 서 Office 365 자동 조사 기능을 통해 완료 된 모든 분석기 및 작업의 전체 인벤토리를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-311">The log captures a complete inventory of all analyzers and actions completed by Office 365 auto-investigation capabilities as part of AIR.</span></span> <span data-ttu-id="a574d-312">작업 자체, 설명, 실제 시작 날짜를 포함 하 여 수행 된 모든 단계를 명확 하 게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-312">It provides a clear view of all the steps taken, including the action itself, a description, and the duration of the actual from start to finish.</span></span>

![AIR 조사 로그 페이지](../../media/air-investigationlogpage.png)

<span data-ttu-id="a574d-314">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-314">You can:</span></span>

- <span data-ttu-id="a574d-315">Playbook 수행 된 단계에 대 한 시각적 개요를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a574d-315">Get see a visual overview of the playbook steps taken.</span></span>
- <span data-ttu-id="a574d-316">결과를 CSV 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-316">Export the results to a CSV file.</span></span>
- <span data-ttu-id="a574d-317">보기를 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-317">Filter the view.</span></span>

### <a name="recommended-actions"></a><span data-ttu-id="a574d-318">권장 작업</span><span class="sxs-lookup"><span data-stu-id="a574d-318">Recommended actions</span></span>

<span data-ttu-id="a574d-319">조사가 완료 된 후에 수정이 권장 되는 모든 playbook 작업을 **작업** 탭에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-319">On the **Actions** tab, you can see all the playbook actions that are recommended for remediation after the investigation has completed.</span></span> <span data-ttu-id="a574d-320">작업은 조사 종료 시에 Microsoft에서 권장 하는 단계를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-320">Actions capture the steps Microsoft recommends you take at the end of an investigation.</span></span> <span data-ttu-id="a574d-321">하나 이상의 작업을 선택 하 여 여기에서 수정 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-321">You can take remediation actions here by selecting one or more actions.</span></span>

<span data-ttu-id="a574d-322">**승인을** 선택 하면 재구성을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-322">Selecting **Approve** allows remediation to begin.</span></span> <span data-ttu-id="a574d-323">(적절 한 사용 권한이 필요 함-탐색기 및 AIR에서 작업을 실행 하려면 **검색 및 비우기** 역할이 필요 합니다.)</span><span class="sxs-lookup"><span data-stu-id="a574d-323">(Appropriate permissions are needed - the **Search And Purge** role is required to run actions from Explorer and AIR).</span></span>

<span data-ttu-id="a574d-324">예를 들어 보안 독자는 작업을 볼 수 있지만 승인 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-324">For example, a Security Reader can view actions, but not approve them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a574d-325">모든 작업을 승인할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-325">You do not have to approve every action.</span></span> <span data-ttu-id="a574d-326">권장 작업에 동의 하지 않거나 조직에서 특정 유형의 작업을 선택 하지 않는 경우에는 작업을 **거부** 하거나 무시 하 고 작업을 수행 하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-326">If you do not agree with the recommended action or your organization does not choose certain types of actions, then you can choose to **Reject** the actions or simply ignore them and take no action.</span></span>
> <span data-ttu-id="a574d-327">모든 작업을 승인 및/또는 거부 하면 조사 완전히 닫기 (상태가 재구성 됨)를 제외 하 고, 일부 작업을 완료 하지 않고 조사 상태가 부분 재구성 됨 상태로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-327">Approving and/or rejecting all actions lets the investigation fully close (status becomes remediated), while leaving some actions incomplete results in the investigation status changing to a partially remediated state.</span></span>

![AIR 조사 작업 페이지](../../media/air-investigationactionspage.png)

<span data-ttu-id="a574d-329">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-329">You can:</span></span>

- <span data-ttu-id="a574d-330">Playbook 권장 작업에 대 한 시각적 개요를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-330">Get a visual overview of the playbook-recommended actions.</span></span>
- <span data-ttu-id="a574d-331">단일 작업 또는 여러 작업을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-331">Select a single action or multiple actions.</span></span>
- <span data-ttu-id="a574d-332">설명으로 권장 작업을 승인 하거나 거부 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-332">Approve or reject recommended actions with comments.</span></span>
- <span data-ttu-id="a574d-333">결과를 CSV 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-333">Export the results to a CSV file.</span></span>
- <span data-ttu-id="a574d-334">보기를 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="a574d-334">Filter the view.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a574d-335">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a574d-335">Next steps</span></span>

- [<span data-ttu-id="a574d-336">보류 중인 작업 검토 및 승인</span><span class="sxs-lookup"><span data-stu-id="a574d-336">Review and approve pending actions</span></span>](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
