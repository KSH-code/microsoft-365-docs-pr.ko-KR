---
title: Microsoft Defender for Office 365
keywords: AIR, autoIR, Endpoint용 Microsoft Defender, 자동화, 조사, 대응, 수정, 위협, 고급, 위협, 보호
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft Defender for Office 365 계획의 자동화된 조사 및 대응 기능의 수정 조치에 대해 자세히 알아보습니다.
ms.technology: mdo
ms.prod: m365-security
ms.date: 06/10/2021
ms.openlocfilehash: 8fc01ab0dd5178032ea7b101f5361c25bb10bbea
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028934"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="aeccd-104">관리 센터에서 재구성 작업을 검토하고 Office 365</span><span class="sxs-lookup"><span data-stu-id="aeccd-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="aeccd-105">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="aeccd-105">**Applies to**</span></span>
- [<span data-ttu-id="aeccd-106">Office 365용 Microsoft Defender 플랜 2</span><span class="sxs-lookup"><span data-stu-id="aeccd-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="aeccd-107">전자 메일에 대한 자동화된 조사가 & 공동 작업 콘텐츠로  인해 악성 또는 의심스러운 등의 결과가 생성되면 특정 수정 작업이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-107">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="aeccd-108">Microsoft Defender for Office 365 수정 작업에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-108">In Microsoft Defender for Office 365, remediation actions can include:</span></span>

- <span data-ttu-id="aeccd-109">전자 메일 메시지 또는 클러스터 소프트 삭제</span><span class="sxs-lookup"><span data-stu-id="aeccd-109">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="aeccd-110">외부 메일 전달 끄기</span><span class="sxs-lookup"><span data-stu-id="aeccd-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="aeccd-111">이러한 수정 작업은 보안 운영 팀이 승인하지 않는 한 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="aeccd-112">자동화된 조사가 제시간에 완료될 수 있도록 가능한 한 빨리 보류 중인 작업을 검토하고 승인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="aeccd-113">경우에 따라 제출된 작업을 다시 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-113">In some cases, you can reconsider submitted actions.</span></span>  <span data-ttu-id="aeccd-114">작업을 수행하기 전에 역할 제거를 & 검색 역할의 일부가 되기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-114">You need to be part of Search & purge role before taking any actions.</span></span>


## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="aeccd-115">보류 중인 작업 승인(또는 거부)</span><span class="sxs-lookup"><span data-stu-id="aeccd-115">Approve (or reject) pending actions</span></span>
<span data-ttu-id="aeccd-116">자동 조사 작업을 찾아서 수행할 수 있는 네 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-116">There are four different ways to find and take auto investigation actions:</span></span>

- [<span data-ttu-id="aeccd-117">인시던트 큐</span><span class="sxs-lookup"><span data-stu-id="aeccd-117">Incident queue</span></span>](https://security.microsoft.com/incidents)
- [<span data-ttu-id="aeccd-118">작업 센터</span><span class="sxs-lookup"><span data-stu-id="aeccd-118">Action center</span></span>](https://security.microsoft.com/action-center/pending)
- <span data-ttu-id="aeccd-119">조사 자체(인시던트 또는 경고를 통해 액세스)</span><span class="sxs-lookup"><span data-stu-id="aeccd-119">Investigation itself (accessed via Incident or from an alert)</span></span>
- [<span data-ttu-id="aeccd-120">조사 및 재구성 조사 큐</span><span class="sxs-lookup"><span data-stu-id="aeccd-120">Investigation and remediation investigations queue</span></span>](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a><span data-ttu-id="aeccd-121">인시던트 큐</span><span class="sxs-lookup"><span data-stu-id="aeccd-121">Incident queue</span></span>
1. <span data-ttu-id="aeccd-122">보안 [센터로 Microsoft 365 로그인합니다.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="aeccd-122">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="aeccd-123">탐색 창에서 인시던트 및 **& 인시던트**> 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-123">In the navigation pane, select **Incidents & alerts > Incidents**.</span></span>
3. <span data-ttu-id="aeccd-124">문제 이름을 선택하여 요약 페이지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-124">Select an incident name to open its summary page.</span></span>
4. <span data-ttu-id="aeccd-125">증거 및 **응답 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-125">Select the **Evidence and Response** tab.</span></span>
5. <span data-ttu-id="aeccd-126">목록에서 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-126">Select an item in the list.</span></span> <span data-ttu-id="aeccd-127">왼쪽 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-127">Its side pane opens.</span></span>
6. <span data-ttu-id="aeccd-128">왼쪽 창에서 작업을 승인하거나 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-128">In the side pane, take approve or reject actions.</span></span>

## <a name="investigation-queue"></a><span data-ttu-id="aeccd-129">조사 큐</span><span class="sxs-lookup"><span data-stu-id="aeccd-129">Investigation queue</span></span> 
1. <span data-ttu-id="aeccd-130">보안 [센터로 Microsoft 365 로그인합니다.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="aeccd-130">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="aeccd-131">경고/인시던트 페이지에서 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-131">Navigate from the alerts/incident page.</span></span> 
3. <span data-ttu-id="aeccd-132">조사 페이지에서 보류 중인 작업 **탭으로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-132">On the Investigation page, go to the **pending actions** tab.</span></span> 
4. <span data-ttu-id="aeccd-133">목록에서 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-133">Select an item in the list.</span></span> <span data-ttu-id="aeccd-134">왼쪽 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-134">Its side pane opens.</span></span>  
5. <span data-ttu-id="aeccd-135">왼쪽 창에서 작업을 승인하거나 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-135">In the side pane, take approve or reject actions.</span></span>

## <a name="action-center"></a><span data-ttu-id="aeccd-136">작업 센터</span><span class="sxs-lookup"><span data-stu-id="aeccd-136">Action center</span></span>
1. <span data-ttu-id="aeccd-137">보안 [센터로 Microsoft 365 로그인합니다.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="aeccd-137">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="aeccd-138">탐색 창에서 작업 센터 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aeccd-138">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="aeccd-139">보류 **중인 탭에서** 승인을 대기 중인 작업 목록을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-139">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
   - <span data-ttu-id="aeccd-140">조사에 대한 자세한 내용을 **확인하려면** 조사 페이지 열기 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-140">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="aeccd-141">**승인을** 선택하여 보류 중인 작업을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-141">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="aeccd-142">보류 **중인** 작업이 수행되지 않도록 방지하려면 거부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-142">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="investigation-and-remediation-investigations-queue"></a><span data-ttu-id="aeccd-143">조사 및 재구성 조사 큐</span><span class="sxs-lookup"><span data-stu-id="aeccd-143">Investigation and remediation investigations queue</span></span>
1. <span data-ttu-id="aeccd-144">보안 [센터로 Microsoft 365 로그인합니다.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="aeccd-144">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="aeccd-145">보류 중인 조사를 개방합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-145">Open pending investigations.</span></span> 
3. <span data-ttu-id="aeccd-146">조사 페이지에서 보류 중인 작업 **탭으로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-146">On the Investigation page, go to the **pending actions** tab.</span></span>
4. <span data-ttu-id="aeccd-147">목록에서 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-147">Select an item in the list.</span></span> <span data-ttu-id="aeccd-148">왼쪽 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-148">Its side pane opens.</span></span>  
5. <span data-ttu-id="aeccd-149">왼쪽 창에서 작업을 승인하거나 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-149">In the side pane, take approve or reject actions.</span></span>

## <a name="change-or-undo-one-remediation-action"></a><span data-ttu-id="aeccd-150">한 가지 수정 작업 변경 또는 실행 취소</span><span class="sxs-lookup"><span data-stu-id="aeccd-150">Change or undo one remediation action</span></span>

<span data-ttu-id="aeccd-151">제출된 작업을 다시 검토하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-151">There are two different ways to reconsider submitted actions:</span></span>
   - <span data-ttu-id="aeccd-152">통합된 [작업 센터를 통해](https://security.microsoft.com/action-center)</span><span class="sxs-lookup"><span data-stu-id="aeccd-152">Through the [unified action center](https://security.microsoft.com/action-center).</span></span>
   - <span data-ttu-id="aeccd-153">그러나 [Office 센터입니다.](https://security.microsoft.com/threatincidents)</span><span class="sxs-lookup"><span data-stu-id="aeccd-153">Though the [Office action center](https://security.microsoft.com/threatincidents).</span></span>
   
## <a name="change-or-undo-through-the-unified-action-center"></a><span data-ttu-id="aeccd-154">통합된 작업 센터를 통해 변경 또는 실행 취소</span><span class="sxs-lookup"><span data-stu-id="aeccd-154">Change or undo through the unified action center</span></span>
1. <span data-ttu-id="aeccd-155">통합된 작업 [센터로 이동하여](https://security.microsoft.com/action-center) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-155">Go to the [unified action center](https://security.microsoft.com/action-center) and sign in.</span></span>
2. <span data-ttu-id="aeccd-156">사용 **기록 탭에서** 변경하거나 실행 취소할 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-156">On the **History** tab, select an action that you want to change or undo.</span></span>
3. <span data-ttu-id="aeccd-157">화면 오른쪽의 창에서 적절한 작업(받은 편지함으로 **이동,** 정크로 **이동,** 삭제된 항목으로 이동, \*\*소프트 삭제" 또는 영구 **삭제)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aeccd-157">In the pane on the right side of the screen, select the appropriate action (**move to inbox**, **move to junk**, **move to deleted items**, \*\*soft delete", or **hard delete**).</span></span>

 ## <a name="change-or-undo-through-the-office-action-center"></a><span data-ttu-id="aeccd-158">Office 센터를 통해 변경 또는 실행 취소</span><span class="sxs-lookup"><span data-stu-id="aeccd-158">Change or undo through the Office action center</span></span> 
1. <span data-ttu-id="aeccd-159">Office [센터로 이동하여](https://security.microsoft.com/threatincidents) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-159">Go to the [Office action center](https://security.microsoft.com/threatincidents) and sign in.</span></span>
2. <span data-ttu-id="aeccd-160">적절한 수정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-160">Select the appropriate remediation.</span></span>
3. <span data-ttu-id="aeccd-161">왼쪽 창에서 메일 제출 항목을 클릭하고 목록이 로드될 때까지 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-161">In the side pane, click on the mail submissions entry and wait for the list to load.</span></span> 
4. <span data-ttu-id="aeccd-162">맨 위에 있는 동작 단추가 활성화될 때까지 기다렸다가 동작 단추를 선택하여 작업 유형을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-162">Wait for the Action button at the top to enable and select the Action button to change the action type.</span></span> 
5. <span data-ttu-id="aeccd-163">그러면 적절한 작업이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="aeccd-163">This will create the appropriate actions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="aeccd-164">다음 단계</span><span class="sxs-lookup"><span data-stu-id="aeccd-164">Next steps</span></span>

- [<span data-ttu-id="aeccd-165">위협 탐색기 사용</span><span class="sxs-lookup"><span data-stu-id="aeccd-165">Use Threat Explorer</span></span>](threat-explorer.md) 
- [<span data-ttu-id="aeccd-166">관리자 /수동 작업</span><span class="sxs-lookup"><span data-stu-id="aeccd-166">Admin /Manual Actions</span></span>](remediate-malicious-email-delivered-office-365.md)
- [<span data-ttu-id="aeccd-167">자동화된 조사 및 응답 기능에서 가짓 긍정/부정을 보고하는 방법</span><span class="sxs-lookup"><span data-stu-id="aeccd-167">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="aeccd-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aeccd-168">See also</span></span>

- [<span data-ttu-id="aeccd-169">자동화된 조사의 세부 정보 및 결과를 Office 365</span><span class="sxs-lookup"><span data-stu-id="aeccd-169">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
