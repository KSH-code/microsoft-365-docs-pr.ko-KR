---
title: Office 365용 Microsoft Defender에서 자동화된 조사 후 가짓 긍정 또는 거짓 부정을 보고하는 방법
description: Office 365용 Microsoft Defender에서 AIR에서 누락되거나 잘못 감지된 것이 있나요? 분석을 위해 Microsoft에 가짓 긍정 또는 거짓 부정을 제출하는 방법을 배워야 합니다.
keywords: 자동화, 조사, 경고, 트리거, 작업, 수정, 가짓 긍정, 거짓 부정
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.custom:
- autoir
ms.openlocfilehash: 0fe8891f5ea6af215791c5f4321a93667a9d58f0
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616179"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="ece46-105">자동화된 조사 및 응답 기능에서 가짓 긍정/부정을 보고하는 방법</span><span class="sxs-lookup"><span data-stu-id="ece46-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ece46-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ece46-106">**Applies to:**</span></span>
- <span data-ttu-id="ece46-107">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ece46-107">Microsoft Defender for Office 365</span></span>

<span data-ttu-id="ece46-108">[Office 365의 자동화된](automated-investigation-response-office.md) 조사 및 대응(AIR) 기능이 누락되거나 잘못된 것을 감지했습니까?</span><span class="sxs-lookup"><span data-stu-id="ece46-108">Did [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) miss or wrongly detect something?</span></span> <span data-ttu-id="ece46-109">이를 해결하기 위해 취할 수 있는 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ece46-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="ece46-110">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ece46-110">You can:</span></span>

- <span data-ttu-id="ece46-111">[Microsoft에 가짓 긍정/거짓 보고](#report-a-false-positivenegative-to-microsoft-for-analysis)</span><span class="sxs-lookup"><span data-stu-id="ece46-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="ece46-112">[경고 조정(필요한](#adjust-an-alert-to-prevent-false-positives-from-recurring) 경우) 및</span><span class="sxs-lookup"><span data-stu-id="ece46-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="ece46-113">[수행된 수정 작업을 취소합니다.](#undo-a-remediation-action)</span><span class="sxs-lookup"><span data-stu-id="ece46-113">[Undo remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="ece46-114">이 문서를 가이드로 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ece46-114">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="ece46-115">분석을 위해 Microsoft에 가짓 긍정/부정 보고</span><span class="sxs-lookup"><span data-stu-id="ece46-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="ece46-116">Office 365용 Microsoft Defender에서 전자 메일 메시지, 전자 메일 첨부 파일, 전자 메일 메시지의 URL 또는 Office 파일의 URL이 누락된 경우 의심되는 스팸, 피싱, URL 및 파일을 [Office 365](admin-submission.md)검색을 위해 Microsoft에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ece46-116">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="ece46-117">맬웨어 분석을 위해 Microsoft에 파일을 [제출할 수 있습니다.](https://www.microsoft.com/wdsi/filesubmission)</span><span class="sxs-lookup"><span data-stu-id="ece46-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="ece46-118">가식이 재발하지 않도록 경고 조정</span><span class="sxs-lookup"><span data-stu-id="ece46-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="ece46-119">합법적인 사용으로 경고가 트리거되거나 경고가 부정확한 경우 Cloud App Security 포털에서 경고를 관리할 [수 있습니다.](https://docs.microsoft.com/cloud-app-security/managing-alerts)</span><span class="sxs-lookup"><span data-stu-id="ece46-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="ece46-120">조직에서 Office 365 외에 [끝점용 Microsoft Defender를](https://docs.microsoft.com/windows/security/threat-protection) 사용하고 파일, IP 주소, URL 또는 도메인이 안전한 경우에도 장치에서 맬웨어로 처리되는 경우 장치에 [대해 "허용"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)작업이 있는 사용자 지정 표시기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ece46-120">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="ece46-121">수정 작업 실행 취소</span><span class="sxs-lookup"><span data-stu-id="ece46-121">Undo a remediation action</span></span>

<span data-ttu-id="ece46-122">대부분의 경우 전자 메일 메시지, 전자 메일 첨부 파일 또는 URL에 대해 수정 작업을 수행한 경우 항목이 실제로 위협이 아닌 경우 보안 운영 팀은 수정 작업을 실행 취소하고 가짓 긍정이 재발하지 않도록 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ece46-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="ece46-123">조사에 [위협](#undo-an-action-using-threat-explorer) 탐색기 또는 [](#undo-an-action-using-the-actions-tab-for-an-investigation) 작업 탭을 사용하여 작업을 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ece46-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-using-the-actions-tab-for-an-investigation) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ece46-124">다음 작업을 수행하기 전에 필요한 권한이 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="ece46-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="ece46-125">위협 탐색기를 사용하여 작업 실행 취소</span><span class="sxs-lookup"><span data-stu-id="ece46-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="ece46-126">위협 탐색기를 사용하여 보안 운영 팀은 작업의 영향을 받는 전자 메일을 찾아 작업을 잠재적으로 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ece46-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

****

|<span data-ttu-id="ece46-127">시나리오</span><span class="sxs-lookup"><span data-stu-id="ece46-127">Scenario</span></span>|<span data-ttu-id="ece46-128">취소 옵션</span><span class="sxs-lookup"><span data-stu-id="ece46-128">Undo Options</span></span>|<span data-ttu-id="ece46-129">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="ece46-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="ece46-130">전자 메일 메시지가 사용자의 정크 메일 폴더로 라우팅되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ece46-130">An email message was routed to a user's Junk Email folder</span></span>|<ul><li><span data-ttu-id="ece46-131">메시지를 사용자의 지우기 항목 폴더로 이동</span><span class="sxs-lookup"><span data-stu-id="ece46-131">Move the message to the user's Deleted Items folder</span></span></li><li><span data-ttu-id="ece46-132">메시지를 사용자의 받은 편지함으로 이동</span><span class="sxs-lookup"><span data-stu-id="ece46-132">Move the message to the user's Inbox</span></span></li><li><span data-ttu-id="ece46-133">메시지 삭제</span><span class="sxs-lookup"><span data-stu-id="ece46-133">Delete the message</span></span></li></ul>|[<span data-ttu-id="ece46-134">Office 365에서 배달된 악성 전자 메일 찾기 및 조사</span><span class="sxs-lookup"><span data-stu-id="ece46-134">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="ece46-135">전자 메일 메시지 또는 파일이 고지된 경우</span><span class="sxs-lookup"><span data-stu-id="ece46-135">An email message or a file was quarantined</span></span>|<ul><li><span data-ttu-id="ece46-136">전자 메일 또는 파일 해제</span><span class="sxs-lookup"><span data-stu-id="ece46-136">Release the email or file</span></span></li><li><span data-ttu-id="ece46-137">전자 메일 또는 파일 삭제</span><span class="sxs-lookup"><span data-stu-id="ece46-137">Delete the email or file</span></span></li></ul>|[<span data-ttu-id="ece46-138">관리자로 quarantined messages 관리</span><span class="sxs-lookup"><span data-stu-id="ece46-138">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a><span data-ttu-id="ece46-139">조사를 위해 작업 탭을 사용하여 작업 실행 취소</span><span class="sxs-lookup"><span data-stu-id="ece46-139">Undo an action using the Actions tab for an investigation</span></span>

<span data-ttu-id="ece46-140">관리 센터에서 수행된 수정 작업을 보고 작업을 잠재적으로 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ece46-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="ece46-141"><https://protection.office.com>으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ece46-141">Go to <https://protection.office.com> and sign in.</span></span> <span data-ttu-id="ece46-142">이렇게하면 보안 및 준수 & 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ece46-142">This takes you to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="ece46-143">위협  관리 \> **조사로 이동.**</span><span class="sxs-lookup"><span data-stu-id="ece46-143">Go to **Threat management** \> **Investigations**.</span></span>

3. <span data-ttu-id="ece46-144">조사 목록에서 항목 ID  옆에 있는 새 창에서 열기 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ece46-144">In the list of investigations, select the **Open in new window** icon next to an item's ID.</span></span>

4. <span data-ttu-id="ece46-145">작업 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ece46-145">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="ece46-146">완료됨 상태가 있는 항목을 선택하고 결정 열에서 승인됨과 같은 링크를 **검색합니다.** </span><span class="sxs-lookup"><span data-stu-id="ece46-146">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decision** column.</span></span> <span data-ttu-id="ece46-147">그러면 동작에 대한 자세한 정보가 있는 플라이아웃이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="ece46-147">This opens a flyout with more details about the action.</span></span>

6. <span data-ttu-id="ece46-148">작업을 실행 취소하려면 수정 **삭제를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ece46-148">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ece46-149">관련 문서</span><span class="sxs-lookup"><span data-stu-id="ece46-149">Related articles</span></span>

[<span data-ttu-id="ece46-150">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ece46-150">Microsoft Defender for Office 365</span></span>](office-365-atp.md)

[<span data-ttu-id="ece46-151">Microsoft Defender for Office 365의 AIR</span><span class="sxs-lookup"><span data-stu-id="ece46-151">AIR in Microsoft Defender for Office 365</span></span>](office-365-air.md)
