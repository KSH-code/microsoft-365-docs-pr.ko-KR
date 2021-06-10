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
ms.openlocfilehash: 95c82f815c794662f7eb0ffaabcfb5f81df3e828
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782996"
---
# <a name="view-and-manage-actions-in-the-action-center"></a><span data-ttu-id="dcf3b-104">관리 센터에서 작업 보기 및 관리</span><span class="sxs-lookup"><span data-stu-id="dcf3b-104">View and manage actions in the Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="dcf3b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="dcf3b-105">**Applies to:**</span></span>
- <span data-ttu-id="dcf3b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dcf3b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="dcf3b-107">Defender의 위협 방지 Microsoft 365 특정 수정 작업이 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-107">Threat protection features in Microsoft 365 Defender can result in certain remediation actions.</span></span> <span data-ttu-id="dcf3b-108">다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-108">Here are some examples:</span></span>

- <span data-ttu-id="dcf3b-109">[자동화된 조사를](m365d-autoir.md) 수행하면 수정 작업이 자동으로 수행되거나 승인을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-109">[Automated investigations](m365d-autoir.md) can result in remediation actions that are taken automatically or await your approval.</span></span>
- <span data-ttu-id="dcf3b-110">바이러스 백신, 맬웨어 방지 및 기타 위협 방지 기능은 파일, URL 또는 프로세스를 차단하거나 아티팩트를 검역에 보내는 등의 수정 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-110">Antivirus, antimalware, and other threat protection features can result in remediation actions, such as blocking a file, URL, or process, or sending an artifact to quarantine.</span></span>
- <span data-ttu-id="dcf3b-111">보안 운영 팀은 고급 헌팅 중이나 경고 [](advanced-hunting-overview.md) 또는 인시던트 [](investigate-alerts.md) 조사 중과 같은 수동으로 수정 작업을 수행할 [수 있습니다.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="dcf3b-111">Your security operations team can take remediation actions manually, such as during [advanced hunting](advanced-hunting-overview.md) or while investigating [alerts](investigate-alerts.md) or [incidents](investigate-incidents.md).</span></span>

> [!NOTE]
> <span data-ttu-id="dcf3b-112">수정 작업을 승인하거나 거부하려면 [적절한 사용 권한](m365d-action-center.md#required-permissions-for-action-center-tasks)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-112">You must have [appropriate permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="dcf3b-113">자세한 내용은 선행 [준비를 참조하세요.](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="dcf3b-113">For more information, see the [prerequisites](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-pending-actions-in-the-action-center"></a><span data-ttu-id="dcf3b-114">작업 센터에서 보류 중인 작업 검토</span><span class="sxs-lookup"><span data-stu-id="dcf3b-114">Review pending actions in the Action center</span></span>

<span data-ttu-id="dcf3b-115">자동화된 조사가 진행되고 적시에 완료될 수 있도록 가능한 한 빨리 보류 중인 작업을 승인하거나 거부하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-115">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

1. <span data-ttu-id="dcf3b-116">[https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="dcf3b-117">탐색 창에서 **작업 센터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="dcf3b-118">작업 센터의 보류 중인 **탭에서** 목록의 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-118">In the Action center, on the **Pending** tab, select an item in the list.</span></span> <span data-ttu-id="dcf3b-119">플라이아웃 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-119">Its flyout pane opens.</span></span> <span data-ttu-id="dcf3b-120">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-120">Here's an example.</span></span>

   ![조치 승인 또는 거부](../../media/air-actioncenter-itemselected.png)

4. <span data-ttu-id="dcf3b-122">플라이아웃 창의 정보를 검토한 후 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-122">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="dcf3b-123">조사에 대한 자세한 내용을 **확인하려면** 조사 페이지 열기 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-123">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="dcf3b-124">**승인을** 선택하여 보류 중인 작업을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-124">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="dcf3b-125">보류 **중인** 작업이 수행되지 않도록 방지하려면 거부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-125">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="dcf3b-126">이동을 **선택하여** 고급 헌팅으로 [이동합니다.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="dcf3b-126">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span> 

## <a name="undo-completed-actions"></a><span data-ttu-id="dcf3b-127">완료된 작업 취소</span><span class="sxs-lookup"><span data-stu-id="dcf3b-127">Undo completed actions</span></span>

<span data-ttu-id="dcf3b-128">장치 또는 파일이 위협이 아닌 것으로 확인되면 해당 작업이 자동으로 또는 수동으로 수행된 경우 수행된 수정 작업을 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-128">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="dcf3b-129">작업 센터의 사용 기록 **탭에서** 다음 작업을 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-129">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="dcf3b-130">작업 원본</span><span class="sxs-lookup"><span data-stu-id="dcf3b-130">Action source</span></span> | <span data-ttu-id="dcf3b-131">지원되는 작업</span><span class="sxs-lookup"><span data-stu-id="dcf3b-131">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="dcf3b-132">- 자동화된 조사</span><span class="sxs-lookup"><span data-stu-id="dcf3b-132">- Automated investigation</span></span> <br/><span data-ttu-id="dcf3b-133">- Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="dcf3b-133">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="dcf3b-134">- 수동 응답 작업</span><span class="sxs-lookup"><span data-stu-id="dcf3b-134">- Manual response actions</span></span> | <span data-ttu-id="dcf3b-135">- 장치 격리</span><span class="sxs-lookup"><span data-stu-id="dcf3b-135">- Isolate device</span></span> <br/><span data-ttu-id="dcf3b-136">- 코드 실행 제한</span><span class="sxs-lookup"><span data-stu-id="dcf3b-136">- Restrict code execution</span></span> <br/><span data-ttu-id="dcf3b-137">- 파일 Quarantine a file</span><span class="sxs-lookup"><span data-stu-id="dcf3b-137">- Quarantine a file</span></span> <br/><span data-ttu-id="dcf3b-138">- 레지스트리 키 제거</span><span class="sxs-lookup"><span data-stu-id="dcf3b-138">- Remove a registry key</span></span> <br/><span data-ttu-id="dcf3b-139">- 서비스 중지</span><span class="sxs-lookup"><span data-stu-id="dcf3b-139">- Stop a service</span></span> <br/><span data-ttu-id="dcf3b-140">- 드라이버를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="dcf3b-140">- Disable a driver</span></span> <br/><span data-ttu-id="dcf3b-141">- 예약된 작업 제거</span><span class="sxs-lookup"><span data-stu-id="dcf3b-141">- Remove a scheduled task</span></span> |

### <a name="undo-one-remediation-action"></a><span data-ttu-id="dcf3b-142">한 가지 수정 작업 실행 취소</span><span class="sxs-lookup"><span data-stu-id="dcf3b-142">Undo one remediation action</span></span>

1. <span data-ttu-id="dcf3b-143">Go to the Action center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) and sign in.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-143">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="dcf3b-144">사용 **기록 탭에서** 실행 취소할 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-144">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="dcf3b-145">화면 오른쪽 창에서 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dcf3b-145">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="dcf3b-146">여러 수정 작업 취소</span><span class="sxs-lookup"><span data-stu-id="dcf3b-146">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="dcf3b-147">Go to the Action Center ( https://security.microsoft.com/action-center) and sign in.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-147">Go to the Action center (https://security.microsoft.com/action-center) and sign in.</span></span>

2. <span data-ttu-id="dcf3b-148">사용 **기록 탭에서** 취소할 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-148">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="dcf3b-149">동일한 작업 유형이 있는 항목을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-149">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="dcf3b-150">플라이아웃 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-150">A flyout pane opens.</span></span>

3. <span data-ttu-id="dcf3b-151">플라이아웃 창에서 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dcf3b-151">In the flyout pane, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="dcf3b-152">여러 장치에서 파일을 검지에서 제거하려면</span><span class="sxs-lookup"><span data-stu-id="dcf3b-152">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="dcf3b-153">Go to the Action center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) and sign in.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-153">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="dcf3b-154">기록 **탭에서** 파일 **Quarantine file** Action 형식이 있는 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf3b-154">On the **History** tab, select a file that has a **Quarantine file** Action type.</span></span>

3. <span data-ttu-id="dcf3b-155">화면 오른쪽 창에서 이 파일의 X **추가** 인스턴스에 적용을 선택한 다음 실행 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="dcf3b-155">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dcf3b-156">다음 단계</span><span class="sxs-lookup"><span data-stu-id="dcf3b-156">Next steps</span></span>

- [<span data-ttu-id="dcf3b-157">자동화 조사 세부정보 및 결과 보기</span><span class="sxs-lookup"><span data-stu-id="dcf3b-157">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="dcf3b-158">가짓 긍정 또는 거짓 부정 해결</span><span class="sxs-lookup"><span data-stu-id="dcf3b-158">Address false positives or false negatives</span></span>](m365d-autoir-report-false-positives-negatives.md)
