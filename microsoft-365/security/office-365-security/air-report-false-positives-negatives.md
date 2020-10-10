---
title: Microsoft Defender for Office 365에서 자동화 된 조사 후 가양성 또는 거짓 네거티브를 보고 하는 방법
description: Microsoft Defender for Office 365의 AIR에서 누락 되었거나 지워지는이 검색 되었습니까? 분석을 위해 Microsoft에 가양성 또는 거짓 네거티브를 전송 하는 방법을 알아봅니다.
keywords: 자동, 조사, 경고, 트리거, 작업, 재구성, 거짓 긍정, 거짓 음수
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
- m365-initiative-defender-office365
ms.topic: conceptual
ms.custom:
- autoir
ms.openlocfilehash: b9f037e3e6d798122b8d3c7ffd3476e34bd5a76b
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48411965"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="989c5-105">자동화 된 조사 및 응답 기능에서 가양성/네거티브를 보고 하는 방법</span><span class="sxs-lookup"><span data-stu-id="989c5-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="989c5-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="989c5-106">**Applies to:**</span></span>
- <span data-ttu-id="989c5-107">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="989c5-107">Microsoft Defender for Office 365</span></span>

<span data-ttu-id="989c5-108">Office 365 누락 또는 지워지는 [의 검색에 대 한 자동화 된 조사 및 응답 (AIR) 기능](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)</span><span class="sxs-lookup"><span data-stu-id="989c5-108">Did [automated investigation and response (AIR) capabilities in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) miss or wrongly detect something?</span></span> <span data-ttu-id="989c5-109">이 문제를 해결 하기 위해 수행할 수 있는 몇 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="989c5-110">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-110">You can:</span></span>
- <span data-ttu-id="989c5-111">[허위 긍정/음수를 Microsoft에 보고 합니다](#report-a-false-positivenegative-to-microsoft-for-analysis).</span><span class="sxs-lookup"><span data-stu-id="989c5-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="989c5-112">필요한 경우 [경고를 조정 합니다](#adjust-an-alert-to-prevent-false-positives-from-recurring) . 한</span><span class="sxs-lookup"><span data-stu-id="989c5-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="989c5-113">[수행한 수정 작업을 취소](#undo-a-remediation-action)합니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-113">[Undo remediation actions that were taken](#undo-a-remediation-action).</span></span> 

<span data-ttu-id="989c5-114">이 문서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="989c5-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="989c5-115">분석을 위해 Microsoft에 가양성/음수 보고</span><span class="sxs-lookup"><span data-stu-id="989c5-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="989c5-116">Microsoft Defender for Office 365에 전자 메일 메시지, 전자 메일 첨부 파일, 전자 메일 메시지의 url 또는 Office 파일의 URL이 누락 된 경우 [의심 스러운 스팸, 피싱, url 및 파일을 office 365 검색을 위해 Microsoft에 제출할](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-116">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span></span>

<span data-ttu-id="989c5-117">[맬웨어 분석을 위해 Microsoft에 파일을 제출할](https://www.microsoft.com/wdsi/filesubmission)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="989c5-118">경고를 조정 하 여 가양성이 되풀이 되지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="989c5-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="989c5-119">합법적인 사용을 통해 경고가 트리거된 경우 또는 경고가 부정확 한 경우 [Cloud App Security 포털에서 알림을 관리할](https://docs.microsoft.com/cloud-app-security/managing-alerts)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="989c5-120">조직에서 Office 365 외에도 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection) 를 사용 하는 경우, 파일, IP 주소, URL 또는 도메인은 안전 하지만 장치에 [대해 "허용" 작업을 사용 하 여 사용자 지정 표시기를 만들](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-120">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="989c5-121">수정 작업 실행 취소</span><span class="sxs-lookup"><span data-stu-id="989c5-121">Undo a remediation action</span></span>

<span data-ttu-id="989c5-122">대부분의 경우 전자 메일 메시지, 전자 메일 첨부 파일 또는 URL에 대해 수정 작업을 수행 했지만 해당 항목이 실제로 위협이 되지 않는 경우 보안 운영 팀에서 수정 작업을 실행 취소 하 고 가양성을 반복 하지 않도록 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="989c5-123">확인을 위해 [위협 탐색기나](#undo-an-action-using-threat-explorer) [작업 탭](#undo-an-action-using-the-actions-tab-for-an-investigation) 을 사용 하 여 작업을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-using-the-actions-tab-for-an-investigation) to undo an action.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="989c5-124">다음 작업을 수행 하기 전에 필요한 사용 권한이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="989c5-125">위협 탐색기를 사용 하 여 작업 실행 취소</span><span class="sxs-lookup"><span data-stu-id="989c5-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="989c5-126">위협 탐색기를 사용 하는 경우 보안 운영 팀은 작업의 영향을 받는 전자 메일을 찾아 작업을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

****

|<span data-ttu-id="989c5-127">시나리오</span><span class="sxs-lookup"><span data-stu-id="989c5-127">Scenario</span></span>|<span data-ttu-id="989c5-128">실행 취소 옵션</span><span class="sxs-lookup"><span data-stu-id="989c5-128">Undo Options</span></span>|<span data-ttu-id="989c5-129">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="989c5-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="989c5-130">전자 메일 메시지가 사용자의 정크 메일 폴더로 라우팅 됨</span><span class="sxs-lookup"><span data-stu-id="989c5-130">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="989c5-131">-메시지를 사용자의 지운 편지함 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="989c5-132">-사용자의 받은 편지 함으로 메시지를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-132">- Move the message to the user's Inbox</span></span> <br/><span data-ttu-id="989c5-133">-메시지 삭제</span><span class="sxs-lookup"><span data-stu-id="989c5-133">- Delete the message</span></span>|[<span data-ttu-id="989c5-134">Office 365에서 제공 된 악성 전자 메일 찾기 및 조사</span><span class="sxs-lookup"><span data-stu-id="989c5-134">Find and investigate malicious email that was delivered in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered)|
|<span data-ttu-id="989c5-135">전자 메일 메시지 또는 파일이 격리 됨</span><span class="sxs-lookup"><span data-stu-id="989c5-135">An email message or a file was quarantined</span></span>|<span data-ttu-id="989c5-136">-전자 메일 또는 파일을 릴리스 합니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-136">- Release the email or file</span></span> <br/><span data-ttu-id="989c5-137">-전자 메일 또는 파일 삭제</span><span class="sxs-lookup"><span data-stu-id="989c5-137">- Delete the email or file</span></span>|[<span data-ttu-id="989c5-138">Office 365에서 격리 된 메시지 및 파일을 관리자 권한으로 관리</span><span class="sxs-lookup"><span data-stu-id="989c5-138">Manage quarantined messages and files as an administrator in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files)|
|

### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a><span data-ttu-id="989c5-139">조사에 대 한 작업 탭을 사용 하 여 작업 실행 취소</span><span class="sxs-lookup"><span data-stu-id="989c5-139">Undo an action using the Actions tab for an investigation</span></span>

<span data-ttu-id="989c5-140">관리 센터에서 수행 된 재구성 작업을 확인 하 고 작업을 실행 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="989c5-141">[https://protection.office.com](https://protection.office.com)으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-141">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="989c5-142">그러면 보안 & 준수 센터로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-142">This takes you to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="989c5-143">**위협 관리**  >  **조사**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="989c5-144">조사 목록에서 항목 ID 옆에 **있는 새 창에서 열기** 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-144">In the list of investigations, select the **Open in new window** icon next to an item's ID.</span></span>

4. <span data-ttu-id="989c5-145">**작업** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-145">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="989c5-146">상태가 **완료**됨 인 항목을 선택 하 고 **의사 결정** 열에서 **승인**됨과 같은 링크를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-146">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decision** column.</span></span> <span data-ttu-id="989c5-147">그러면 작업에 대 한 자세한 정보가 포함 된 플라이 아웃이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-147">This opens a flyout with more details about the action.</span></span>

6. <span data-ttu-id="989c5-148">작업을 실행 취소 하려면 **수정 관리 삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="989c5-148">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="989c5-149">관련 문서</span><span class="sxs-lookup"><span data-stu-id="989c5-149">Related articles</span></span>

[<span data-ttu-id="989c5-150">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="989c5-150">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[<span data-ttu-id="989c5-151">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="989c5-151">AIR in Microsoft Defender for Office 365</span></span>](office-365-air.md)
