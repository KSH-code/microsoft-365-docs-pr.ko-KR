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
ms.date: 01/29/2021
ms.openlocfilehash: 525f6cf922f80067219f6c33a2c11559e9e58a39
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878775"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="f869a-104">관리 센터에서 재구성 작업을 검토하고 Office 365</span><span class="sxs-lookup"><span data-stu-id="f869a-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="f869a-105">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="f869a-105">**Applies to**</span></span>
- [<span data-ttu-id="f869a-106">Office 365용 Microsoft Defender 플랜 2</span><span class="sxs-lookup"><span data-stu-id="f869a-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f869a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f869a-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f869a-108">전자 메일에 대한 자동화된 조사가 & 공동 작업 콘텐츠로  인해 악성 또는 의심스러운 등의 결과가 생성되면 특정 수정 작업이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f869a-108">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="f869a-109">Microsoft Defender for Office 365 수정 작업에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f869a-109">In Microsoft Defender for Office 365, remediation actions can include:</span></span>

- <span data-ttu-id="f869a-110">URL 차단(클릭 시간)</span><span class="sxs-lookup"><span data-stu-id="f869a-110">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="f869a-111">전자 메일 메시지 또는 클러스터 소프트 삭제</span><span class="sxs-lookup"><span data-stu-id="f869a-111">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="f869a-112">전자 메일 또는 전자 메일 첨부 파일 Quarantining</span><span class="sxs-lookup"><span data-stu-id="f869a-112">Quarantining email or email attachments</span></span>
- <span data-ttu-id="f869a-113">외부 메일 전달 끄기</span><span class="sxs-lookup"><span data-stu-id="f869a-113">Turning off external mail forwarding</span></span>

<span data-ttu-id="f869a-114">이러한 수정 작업은 보안 운영 팀이 승인하지 않는 한 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f869a-114">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="f869a-115">자동화된 조사가 제시간에 완료될 수 있도록 가능한 한 빨리 보류 중인 작업을 검토하고 승인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f869a-115">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="f869a-116">경우에 따라 수정 작업을 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f869a-116">In some cases, you can undo a remediation action.</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="f869a-117">보류 중인 작업 승인(또는 거부)</span><span class="sxs-lookup"><span data-stu-id="f869a-117">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="f869a-118">Defender Microsoft 365 ()로 이동하여 <https://security.microsoft.com> 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="f869a-118">Go to the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="f869a-119">탐색 창에서 작업 센터 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f869a-119">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="f869a-120">보류 **중인 탭에서** 승인을 대기 중인 작업 목록을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="f869a-120">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="f869a-121">목록에서 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f869a-121">Select an item in the list.</span></span> <span data-ttu-id="f869a-122">플라이아웃 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="f869a-122">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="f869a-123">플라이아웃 창의 정보를 검토한 후 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f869a-123">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="f869a-124">조사에 대한 자세한 내용을 **확인하려면** 조사 페이지 열기 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f869a-124">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="f869a-125">**승인을** 선택하여 보류 중인 작업을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="f869a-125">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="f869a-126">보류 **중인** 작업이 수행되지 않도록 방지하려면 거부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f869a-126">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="f869a-127">한 가지 수정 작업 실행 취소</span><span class="sxs-lookup"><span data-stu-id="f869a-127">Undo one remediation action</span></span>

1. <span data-ttu-id="f869a-128">Go to the Action center ( <https://security.microsoft.com/action-center> ) and sign in.</span><span class="sxs-lookup"><span data-stu-id="f869a-128">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="f869a-129">사용 **기록 탭에서** 실행 취소할 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f869a-129">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="f869a-130">화면 오른쪽 창에서 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f869a-130">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="f869a-131">여러 수정 작업 취소</span><span class="sxs-lookup"><span data-stu-id="f869a-131">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="f869a-132">Go to the Action center ( <https://security.microsoft.com/action-center> ) and sign in.</span><span class="sxs-lookup"><span data-stu-id="f869a-132">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="f869a-133">사용 **기록 탭에서** 취소할 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f869a-133">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="f869a-134">동일한 작업 유형이 있는 항목을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f869a-134">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="f869a-135">플라이아웃 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="f869a-135">A flyout pane opens.</span></span>
3. <span data-ttu-id="f869a-136">플라이아웃 창에서 취소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f869a-136">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="f869a-137">여러 장치에서 파일을 검지에서 제거하려면</span><span class="sxs-lookup"><span data-stu-id="f869a-137">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="f869a-138">Go to the Action center ( <https://security.microsoft.com/action-center> ) and sign in.</span><span class="sxs-lookup"><span data-stu-id="f869a-138">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="f869a-139">사용 기록 **탭에서** 작업 유형이 **Quarantine** file인 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f869a-139">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="f869a-140">화면 오른쪽 창에서 이 파일의 X **추가** 인스턴스에 적용을 선택한 다음 실행 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f869a-140">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f869a-141">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f869a-141">Next steps</span></span>

- [<span data-ttu-id="f869a-142">위협 탐색기 사용</span><span class="sxs-lookup"><span data-stu-id="f869a-142">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="f869a-143">자동화된 조사 및 응답 기능에서 가짓 긍정/부정을 보고하는 방법</span><span class="sxs-lookup"><span data-stu-id="f869a-143">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="f869a-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f869a-144">See also</span></span>

- [<span data-ttu-id="f869a-145">자동화된 조사의 세부 정보 및 결과를 Office 365</span><span class="sxs-lookup"><span data-stu-id="f869a-145">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
