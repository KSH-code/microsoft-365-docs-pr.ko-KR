---
title: 자동화된 조사 후 보류 중인 작업 승인 또는 거부
description: 자동화된 조사 및 대응과 관련된 조치를 관리하는 작업 센터의 사용
keywords: 조치, 센터, 자동 공기, 자동화, 조사, 대응, 수정
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
ms.date: 12/09/2020
ms.technology: m365d
ms.openlocfilehash: 3776dea4a5a24f4695a5c617325af14f1f03494f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930381"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="aad4a-104">자동화된 조사 후 보류 중인 작업 승인 또는 거부</span><span class="sxs-lookup"><span data-stu-id="aad4a-104">Approve or reject pending actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="aad4a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="aad4a-105">**Applies to:**</span></span>
- <span data-ttu-id="aad4a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aad4a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="aad4a-107">자동화 조사가 실행되면 승인이 필요한 [수정 작업](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions)이 하나 이상 진행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad4a-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="aad4a-108">예를 들어 전자 메일 메시지의 클러스터를 삭제 하거나 격리된 파일을 제거해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad4a-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="aad4a-109">자동화된 조사가 진행되고 적시에 완료될 수 있도록 가능한 한 빨리 보류 중인 작업을 승인하거나 거부하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="aad4a-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="aad4a-110">Microsoft 365 Defender의 자동화된 조사 및 응답 기능으로 누락되거나 잘못 감지된 것으로 생각되면 알려주세요!</span><span class="sxs-lookup"><span data-stu-id="aad4a-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="aad4a-111">[Microsoft 365 Defender에서 자동화된](mtp-autoir-report-false-positives-negatives.md)조사 및 응답(AIR) 기능에서 가음성/부정을 보고하는 방법을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="aad4a-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="aad4a-112">보류 중인 작업은 작업 센터 또는 [](#review-a-pending-action-in-the-action-center) 조사 세부 정보 보기를 사용하여 검토하고 승인할 [수 있습니다.](#review-a-pending-action-in-the-investigation-details-view)</span><span class="sxs-lookup"><span data-stu-id="aad4a-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="aad4a-113">수정 작업을 승인하거나 거부하려면 [적절한 사용 권한](mtp-action-center.md#required-permissions-for-action-center-tasks)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad4a-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="aad4a-114">자세한 내용은 [Microsoft 365 Defender의](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)자동화된 조사 및 대응을 위한 선행 작업을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aad4a-114">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="aad4a-115">알림 센터에서 대기 중인 작업 검토</span><span class="sxs-lookup"><span data-stu-id="aad4a-115">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="aad4a-116">[https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="aad4a-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="aad4a-117">탐색 창에서 **알림 센터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aad4a-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="aad4a-118">알림 센터의 **보류 중인** 탭의 목록에서 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aad4a-118">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="aad4a-119">**조사 번호** 열에서 항목을 선택하면 조사 세부 정보 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="aad4a-119">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="aad4a-120">거기에서 조사 결과를 보고 권장 조치를 승인하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad4a-120">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="aad4a-121">목록에서 행을 선택하면 플라이 아웃이 열리면서 해당 항목에 대한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad4a-121">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![조치 승인 또는 거부](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="aad4a-123">링크를 사용하여 연결 된 경고나 확인을 보고 작업을 승인하거나 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="aad4a-123">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="aad4a-124">조사 세부 정보 보기에서 보류 중인 작업을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="aad4a-124">Review a pending action in the investigation details view</span></span>

![조사 세부 정보](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="aad4a-126">[조사 세부 정보](mtp-autoir-results.md) 페이지에서 **보류 중인 작업** (또는 **작업**) 탭을 선택합니다. 승인이 보류 중인 항목은 여기에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="aad4a-126">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="aad4a-127">목록에서 항목을 선택한 다음 **승인** 또는 **거부** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aad4a-127">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="undo-completed-actions"></a><span data-ttu-id="aad4a-128">완료된 작업 취소</span><span class="sxs-lookup"><span data-stu-id="aad4a-128">Undo completed actions</span></span>

<span data-ttu-id="aad4a-129">장치 또는 파일이 위협이 아닌 것으로 확인된 경우 수행된 수정 작업을 자동으로 수행하거나 수동으로 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad4a-129">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="aad4a-130">작업 센터의 사용 기록 **탭에서** 다음 작업을 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad4a-130">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="aad4a-131">작업 원본</span><span class="sxs-lookup"><span data-stu-id="aad4a-131">Action source</span></span> | <span data-ttu-id="aad4a-132">지원되는 작업</span><span class="sxs-lookup"><span data-stu-id="aad4a-132">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="aad4a-133">- 자동화된 조사</span><span class="sxs-lookup"><span data-stu-id="aad4a-133">- Automated investigation</span></span> <br/><span data-ttu-id="aad4a-134">- Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="aad4a-134">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="aad4a-135">- 수동 대응 작업</span><span class="sxs-lookup"><span data-stu-id="aad4a-135">- Manual response actions</span></span> | <span data-ttu-id="aad4a-136">- 장치 격리</span><span class="sxs-lookup"><span data-stu-id="aad4a-136">- Isolate device</span></span> <br/><span data-ttu-id="aad4a-137">- 코드 실행 제한</span><span class="sxs-lookup"><span data-stu-id="aad4a-137">- Restrict code execution</span></span> <br/><span data-ttu-id="aad4a-138">- 파일 Quarantine a file</span><span class="sxs-lookup"><span data-stu-id="aad4a-138">- Quarantine a file</span></span> <br/><span data-ttu-id="aad4a-139">- 레지스트리 키 제거</span><span class="sxs-lookup"><span data-stu-id="aad4a-139">- Remove a registry key</span></span> <br/><span data-ttu-id="aad4a-140">- 서비스 중지</span><span class="sxs-lookup"><span data-stu-id="aad4a-140">- Stop a service</span></span> <br/><span data-ttu-id="aad4a-141">- 드라이버를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="aad4a-141">- Disable a driver</span></span> <br/><span data-ttu-id="aad4a-142">- 예약된 작업 제거</span><span class="sxs-lookup"><span data-stu-id="aad4a-142">- Remove a scheduled task</span></span> |

### <a name="to-undo-a-remediation-action"></a><span data-ttu-id="aad4a-143">수정 작업을 실행 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="aad4a-143">To undo a remediation action</span></span>

1. <span data-ttu-id="aad4a-144">Go to the Action center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) and sign in.</span><span class="sxs-lookup"><span data-stu-id="aad4a-144">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="aad4a-145">사용 기록 **탭에서** 실행 취소할 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aad4a-145">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="aad4a-146">화면 오른쪽 창에서 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aad4a-146">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="aad4a-147">여러 장치에서 파일을 분리하려면</span><span class="sxs-lookup"><span data-stu-id="aad4a-147">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="aad4a-148">Go to the Action center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) and sign in.</span><span class="sxs-lookup"><span data-stu-id="aad4a-148">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="aad4a-149">사용 기록 **탭에서** 작업 유형이 **Quarantine** 파일이 있는 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aad4a-149">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="aad4a-150">화면 오른쪽 창에서 이 파일의 X **추가** 인스턴스에 적용을 선택한 다음 실행 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aad4a-150">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="aad4a-151">다음 단계</span><span class="sxs-lookup"><span data-stu-id="aad4a-151">Next steps</span></span>

- [<span data-ttu-id="aad4a-152">자동화 조사 세부정보 및 결과 보기</span><span class="sxs-lookup"><span data-stu-id="aad4a-152">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="aad4a-153">자동화된 조사 및 응답 기능에서 가짓 긍정/부정 처리</span><span class="sxs-lookup"><span data-stu-id="aad4a-153">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
