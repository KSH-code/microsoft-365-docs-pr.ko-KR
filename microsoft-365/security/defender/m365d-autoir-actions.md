---
title: 관리 센터에서 작업 보기 및 관리
description: 관리 센터를 사용하여 수정 작업 보기 및 관리
keywords: 조치, 센터, 자동 공기, 자동화, 조사, 대응, 수정
search.appverid: met150
ms.prod: m365-security
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
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: e3e842f812c5675334cc25fa35544165129db2b4
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245891"
---
# <a name="view-and-manage-actions-in-the-action-center"></a><span data-ttu-id="41c6e-104">관리 센터에서 작업 보기 및 관리</span><span class="sxs-lookup"><span data-stu-id="41c6e-104">View and manage actions in the Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="41c6e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="41c6e-105">**Applies to:**</span></span>
- <span data-ttu-id="41c6e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41c6e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="41c6e-107">Defender의 위협 방지 Microsoft 365 특정 수정 작업이 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41c6e-107">Threat protection features in Microsoft 365 Defender can result in certain remediation actions.</span></span> <span data-ttu-id="41c6e-108">다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="41c6e-108">Here are some examples:</span></span>
- <span data-ttu-id="41c6e-109">[자동화된 조사를](m365d-autoir.md) 수행하면 자동으로 수행되거나 승인 대기하는 수정 작업이 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41c6e-109">[Automated investigations](m365d-autoir.md) can result in remediation actions that are taken automatically or await approval.</span></span>
- <span data-ttu-id="41c6e-110">바이러스 백신, 맬웨어 방지 및 기타 위협 방지 기능은 파일, URL 또는 프로세스를 차단하거나 아티팩트를 검역에 보내는 등의 수정 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41c6e-110">Antivirus, antimalware, and other threat protection features can result in remediation actions, such as blocking a file, URL, or process, or sending an artifact to quarantine.</span></span>
- <span data-ttu-id="41c6e-111">보안 운영 팀은 고급 헌팅 중이나 경고 [](advanced-hunting-overview.md) 또는 인시던트 [](investigate-alerts.md) 조사 중과 같은 수동으로 수정 작업을 수행할 [수 있습니다.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="41c6e-111">Your security operations team can take remediation actions manually, such as during [advanced hunting](advanced-hunting-overview.md) or while investigating [alerts](investigate-alerts.md) or [incidents](investigate-incidents.md).</span></span>

> [!NOTE]
> <span data-ttu-id="41c6e-112">수정 작업을 승인하거나 거부하려면 [적절한 사용 권한](m365d-action-center.md#required-permissions-for-action-center-tasks)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41c6e-112">You must have [appropriate permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="41c6e-113">자세한 내용은 Defender에서 자동화된 조사 및 대응을 위한 Microsoft 365 [참조하세요.](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="41c6e-113">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-pending-actions-in-the-action-center"></a><span data-ttu-id="41c6e-114">작업 센터에서 보류 중인 작업 검토</span><span class="sxs-lookup"><span data-stu-id="41c6e-114">Review pending actions in the Action center</span></span>

<span data-ttu-id="41c6e-115">자동화된 조사가 진행되고 적시에 완료될 수 있도록 가능한 한 빨리 보류 중인 작업을 승인하거나 거부하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="41c6e-115">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

![조치 승인 또는 거부](../../media/air-actioncenter-itemselected.png)

1. <span data-ttu-id="41c6e-117">[https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="41c6e-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="41c6e-118">탐색 창에서 **알림 센터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="41c6e-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="41c6e-119">알림 센터의 **보류 중인** 탭의 목록에서 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="41c6e-119">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> <span data-ttu-id="41c6e-120">플라이아웃 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="41c6e-120">Its flyout pane opens.</span></span>

4. <span data-ttu-id="41c6e-121">플라이아웃 창의 정보를 검토한 후 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="41c6e-121">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="41c6e-122">조사에 대한 자세한 내용을 **확인하려면** 조사 페이지 열기 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="41c6e-122">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="41c6e-123">**승인을** 선택하여 보류 중인 작업을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="41c6e-123">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="41c6e-124">보류 **중인** 작업이 수행되지 않도록 방지하려면 거부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="41c6e-124">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="41c6e-125">이동을 **선택하여** 고급 헌팅으로 [이동합니다.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="41c6e-125">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span> 

## <a name="undo-completed-actions"></a><span data-ttu-id="41c6e-126">완료된 작업 취소</span><span class="sxs-lookup"><span data-stu-id="41c6e-126">Undo completed actions</span></span>

<span data-ttu-id="41c6e-127">장치 또는 파일이 위협이 아닌 것으로 확인되면 해당 작업이 자동으로 또는 수동으로 수행된 경우 수행된 수정 작업을 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41c6e-127">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="41c6e-128">작업 센터의 사용 기록 **탭에서** 다음 작업을 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41c6e-128">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="41c6e-129">작업 원본</span><span class="sxs-lookup"><span data-stu-id="41c6e-129">Action source</span></span> | <span data-ttu-id="41c6e-130">지원되는 작업</span><span class="sxs-lookup"><span data-stu-id="41c6e-130">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="41c6e-131">- 자동화된 조사</span><span class="sxs-lookup"><span data-stu-id="41c6e-131">- Automated investigation</span></span> <br/><span data-ttu-id="41c6e-132">- Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="41c6e-132">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="41c6e-133">- 수동 응답 작업</span><span class="sxs-lookup"><span data-stu-id="41c6e-133">- Manual response actions</span></span> | <span data-ttu-id="41c6e-134">- 장치 격리</span><span class="sxs-lookup"><span data-stu-id="41c6e-134">- Isolate device</span></span> <br/><span data-ttu-id="41c6e-135">- 코드 실행 제한</span><span class="sxs-lookup"><span data-stu-id="41c6e-135">- Restrict code execution</span></span> <br/><span data-ttu-id="41c6e-136">- 파일 Quarantine a file</span><span class="sxs-lookup"><span data-stu-id="41c6e-136">- Quarantine a file</span></span> <br/><span data-ttu-id="41c6e-137">- 레지스트리 키 제거</span><span class="sxs-lookup"><span data-stu-id="41c6e-137">- Remove a registry key</span></span> <br/><span data-ttu-id="41c6e-138">- 서비스 중지</span><span class="sxs-lookup"><span data-stu-id="41c6e-138">- Stop a service</span></span> <br/><span data-ttu-id="41c6e-139">- 드라이버를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="41c6e-139">- Disable a driver</span></span> <br/><span data-ttu-id="41c6e-140">- 예약된 작업 제거</span><span class="sxs-lookup"><span data-stu-id="41c6e-140">- Remove a scheduled task</span></span> |

### <a name="undo-one-remediation-action"></a><span data-ttu-id="41c6e-141">한 가지 수정 작업 실행 취소</span><span class="sxs-lookup"><span data-stu-id="41c6e-141">Undo one remediation action</span></span>

1. <span data-ttu-id="41c6e-142">Go to the Action center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) and sign in.</span><span class="sxs-lookup"><span data-stu-id="41c6e-142">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="41c6e-143">사용 **기록 탭에서** 실행 취소할 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="41c6e-143">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="41c6e-144">화면 오른쪽 창에서 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="41c6e-144">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="41c6e-145">여러 수정 작업 취소</span><span class="sxs-lookup"><span data-stu-id="41c6e-145">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="41c6e-146">Go to the Action Center ( https://security.microsoft.com/action-center) and sign in.</span><span class="sxs-lookup"><span data-stu-id="41c6e-146">Go to the Action center (https://security.microsoft.com/action-center) and sign in.</span></span>

2. <span data-ttu-id="41c6e-147">사용 **기록 탭에서** 취소할 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="41c6e-147">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="41c6e-148">동일한 작업 유형이 있는 항목을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41c6e-148">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="41c6e-149">플라이아웃 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="41c6e-149">A flyout pane opens.</span></span>

3. <span data-ttu-id="41c6e-150">플라이아웃 창에서 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="41c6e-150">In the flyout pane, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="41c6e-151">여러 장치에서 파일을 검지에서 제거하려면</span><span class="sxs-lookup"><span data-stu-id="41c6e-151">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="41c6e-152">Go to the Action center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) and sign in.</span><span class="sxs-lookup"><span data-stu-id="41c6e-152">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="41c6e-153">사용 기록 **탭에서** 작업 유형이 **Quarantine** file인 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="41c6e-153">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="41c6e-154">화면 오른쪽 창에서 이 파일의 X **추가** 인스턴스에 적용을 선택한 다음 실행 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="41c6e-154">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="41c6e-155">다음 단계</span><span class="sxs-lookup"><span data-stu-id="41c6e-155">Next steps</span></span>

- [<span data-ttu-id="41c6e-156">자동화 조사 세부정보 및 결과 보기</span><span class="sxs-lookup"><span data-stu-id="41c6e-156">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="41c6e-157">가음성/음수 처리 방법 학습(가인 경우)</span><span class="sxs-lookup"><span data-stu-id="41c6e-157">Learn how to handle false positives/negatives (if you get one)</span></span>](m365d-autoir-report-false-positives-negatives.md)
