---
title: Microsoft Defender에서 자동 조사를 통해 가짓 긍정 또는 거짓 부정을 보고하는 Office 365
description: Microsoft Defender에서 AIR에서 누락되거나 잘못 감지된 것이 Office 365? 분석을 위해 Microsoft에 가짓 긍정 또는 거짓 부정을 제출하는 방법을 배워야 합니다.
keywords: 자동화, 조사, 경고, 트리거, 작업, 수정, 가짓 긍정, 거짓 부정
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
ms.prod: m365-security
ms.date: 01/29/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 287bd9cd4dda6ccb152e93908a409e036eab9cc7
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878883"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="eda53-105">자동화된 조사 및 응답 기능에서 가짓 긍정/부정을 보고하는 방법</span><span class="sxs-lookup"><span data-stu-id="eda53-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="eda53-106">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="eda53-106">**Applies to**</span></span>
- [<span data-ttu-id="eda53-107">Office 365용 Microsoft Defender 플랜 2</span><span class="sxs-lookup"><span data-stu-id="eda53-107">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="eda53-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eda53-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="eda53-109">누락되거나 잘못된 Office 365 자동화된 조사 및 [대응(AIR)](automated-investigation-response-office.md) 기능이 있는 경우 보안 운영 팀에서 이를 해결하기 위해 취할 수 있는 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eda53-109">If [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) missed or wrongly detected something, there are steps your security operations team can take to fix it.</span></span> <span data-ttu-id="eda53-110">이러한 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eda53-110">Such actions include:</span></span>

- <span data-ttu-id="eda53-111">[Microsoft에 가짓 긍정/음수 보고](#report-a-false-positivenegative-to-microsoft-for-analysis)</span><span class="sxs-lookup"><span data-stu-id="eda53-111">[Reporting a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="eda53-112">[경고 조정(필요한](#adjust-an-alert-to-prevent-false-positives-from-recurring) 경우) 및</span><span class="sxs-lookup"><span data-stu-id="eda53-112">[Adjusting alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="eda53-113">[수행된](#undo-a-remediation-action)수정 작업 취소</span><span class="sxs-lookup"><span data-stu-id="eda53-113">[Undoing remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="eda53-114">이 문서를 가이드로 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="eda53-114">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="eda53-115">분석을 위해 Microsoft에 가짓 긍정/음수 보고</span><span class="sxs-lookup"><span data-stu-id="eda53-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="eda53-116">Microsoft Defender에서 전자 메일 Office 365, 전자 메일 첨부 파일, 전자 메일 메시지의 URL 또는 Office 파일의 URL이 누락된 경우 의심되는 [스팸, 피싱,](admin-submission.md)URL 및 파일을 Microsoft에 제출하여 검색을 Office 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eda53-116">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="eda53-117">맬웨어 분석을 위해 Microsoft에 파일을 [제출할 수 있습니다.](https://www.microsoft.com/wdsi/filesubmission)</span><span class="sxs-lookup"><span data-stu-id="eda53-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="eda53-118">가식이 재발하지 않도록 경고 조정</span><span class="sxs-lookup"><span data-stu-id="eda53-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="eda53-119">합법적인 사용으로 경고가 트리거되거나 경고가 부정확한 경우 알림 [포털에서 경고를 Cloud App Security 있습니다.](/cloud-app-security/managing-alerts)</span><span class="sxs-lookup"><span data-stu-id="eda53-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="eda53-120">조직에서 Office 365 외에도 [끝점용 Microsoft Defender를](/windows/security/threat-protection) 사용하며 파일, IP 주소, URL 또는 도메인이 장치에서 맬웨어로 처리되는 경우 안전한 경우에도 장치에 [대해 "허용"](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)작업이 있는 사용자 지정 표시기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eda53-120">If your organization is using [Microsoft Defender for Endpoint](/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="eda53-121">수정 작업 실행 취소</span><span class="sxs-lookup"><span data-stu-id="eda53-121">Undo a remediation action</span></span>

<span data-ttu-id="eda53-122">대부분의 경우 전자 메일 메시지, 전자 메일 첨부 파일 또는 URL에 대해 수정 작업을 수행한 경우 항목이 실제로 위협이 아닌 경우 보안 운영 팀은 수정 작업을 실행 취소하고 가짓 긍정이 재발하지 않도록 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eda53-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="eda53-123">조사를 위해 [위협](#undo-an-action-using-threat-explorer) 탐색기 또는 [작업](#undo-an-action-in-the-action-center) 탭을 사용하여 작업을 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eda53-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-in-the-action-center) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eda53-124">다음 작업을 수행하기 전에 필요한 사용 권한이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="eda53-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="eda53-125">위협 탐색기를 사용하여 작업 실행 취소</span><span class="sxs-lookup"><span data-stu-id="eda53-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="eda53-126">위협 탐색기를 사용하여 보안 운영 팀은 작업의 영향을 받는 전자 메일을 찾아 작업을 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eda53-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

<br>

****

|<span data-ttu-id="eda53-127">시나리오</span><span class="sxs-lookup"><span data-stu-id="eda53-127">Scenario</span></span>|<span data-ttu-id="eda53-128">옵션 취소</span><span class="sxs-lookup"><span data-stu-id="eda53-128">Undo Options</span></span>|<span data-ttu-id="eda53-129">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="eda53-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="eda53-130">전자 메일 메시지가 사용자의 정크 메일 폴더로 라우팅되었습니다.</span><span class="sxs-lookup"><span data-stu-id="eda53-130">An email message was routed to a user's Junk Email folder</span></span>|<ul><li><span data-ttu-id="eda53-131">메시지를 사용자의 지우기 항목 폴더로 이동</span><span class="sxs-lookup"><span data-stu-id="eda53-131">Move the message to the user's Deleted Items folder</span></span></li><li><span data-ttu-id="eda53-132">메시지를 사용자의 받은 편지함으로 이동</span><span class="sxs-lookup"><span data-stu-id="eda53-132">Move the message to the user's Inbox</span></span></li><li><span data-ttu-id="eda53-133">메시지 삭제</span><span class="sxs-lookup"><span data-stu-id="eda53-133">Delete the message</span></span></li></ul>|[<span data-ttu-id="eda53-134">전자 메일에서 배달된 악성 전자 메일을 찾아 Office 365</span><span class="sxs-lookup"><span data-stu-id="eda53-134">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="eda53-135">전자 메일 메시지 또는 파일이 고지된 경우</span><span class="sxs-lookup"><span data-stu-id="eda53-135">An email message or a file was quarantined</span></span>|<ul><li><span data-ttu-id="eda53-136">전자 메일 또는 파일 릴리스</span><span class="sxs-lookup"><span data-stu-id="eda53-136">Release the email or file</span></span></li><li> <span data-ttu-id="eda53-137">전자 메일 또는 파일 삭제</span><span class="sxs-lookup"><span data-stu-id="eda53-137">Delete the email or file</span></span></li></ul>|[<span data-ttu-id="eda53-138">관리자로 quarantined messages 관리</span><span class="sxs-lookup"><span data-stu-id="eda53-138">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a><span data-ttu-id="eda53-139">동작 센터에서 작업 실행 취소</span><span class="sxs-lookup"><span data-stu-id="eda53-139">Undo an action in the Action center</span></span>

<span data-ttu-id="eda53-140">관리 센터에서 수행된 수정 작업을 보고 작업을 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eda53-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="eda53-141">Defender Microsoft 365 ()로 <https://security.microsoft.com> 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="eda53-141">Go to the Microsoft 365 Defender portal (<https://security.microsoft.com>).</span></span>
2. <span data-ttu-id="eda53-142">탐색 창에서 작업 센터 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eda53-142">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="eda53-143">완료된 **작업 목록을** 표시하려면 사용 기록 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eda53-143">Select the **History** tab to view the list of completed actions.</span></span>
4. <span data-ttu-id="eda53-144">항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eda53-144">Select an item.</span></span> <span data-ttu-id="eda53-145">플라이아웃 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="eda53-145">Its flyout pane opens.</span></span>
5. <span data-ttu-id="eda53-146">플라이아웃 창에서 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eda53-146">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="eda53-147">(취소할 수 있는 작업만 취소 **단추가** 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="eda53-147">(Only actions that can be undone will have an **Undo** button.)</span></span>

## <a name="see-also"></a><span data-ttu-id="eda53-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eda53-148">See also</span></span>

- [<span data-ttu-id="eda53-149">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="eda53-149">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="eda53-150">Microsoft Defender에서 자동화된 조사를 Office 365</span><span class="sxs-lookup"><span data-stu-id="eda53-150">Automated investigations in Microsoft Defender for Office 365</span></span>](office-365-air.md)
