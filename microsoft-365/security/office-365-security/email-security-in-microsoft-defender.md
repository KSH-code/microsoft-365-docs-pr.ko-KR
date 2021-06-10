---
title: Microsoft Defender for Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 맬웨어 피싱 시도를 보고 조사합니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0326a51f14b402b9a579e8668ef2c026f9de789
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52877899"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a><span data-ttu-id="492ee-103">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="492ee-103">Email security with Threat Explorer in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="492ee-104">이 문서의 내용</span><span class="sxs-lookup"><span data-stu-id="492ee-104">In this article:</span></span>

- [<span data-ttu-id="492ee-105">전자 메일에서 검색된 맬웨어 보기</span><span class="sxs-lookup"><span data-stu-id="492ee-105">View malware detected in email</span></span>](#view-malware-detected-in-email)
- [<span data-ttu-id="492ee-106">피싱 URL 보기 및 판정 데이터 클릭</span><span class="sxs-lookup"><span data-stu-id="492ee-106">View phishing URL and click verdict data</span></span>](#view-phishing-url-and-click-verdict-data)
- [<span data-ttu-id="492ee-107">자동화된 조사 및 대응 시작</span><span class="sxs-lookup"><span data-stu-id="492ee-107">Start automated investigation and response</span></span>](#start-automated-investigation-and-response)

> [!NOTE]
> <span data-ttu-id="492ee-108">이 문서는 위협 탐색기(탐색기) **,** 전자 메일 보안 및 **탐색기** 및 실시간 검색 기본(예: 도구 간 차이점 및 작동에 필요한 사용 권한)에 대한 **3개** 문서 시리즈의 일부입니다. </span><span class="sxs-lookup"><span data-stu-id="492ee-108">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="492ee-109">이 시리즈의 다른 두 문서는 위협 탐색기 및 [위협](threat-hunting-in-threat-explorer.md) 탐색기에서 위협 헌팅 및 실시간 검색 기본 [입니다.](real-time-detections.md)</span><span class="sxs-lookup"><span data-stu-id="492ee-109">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span> 

<span data-ttu-id="492ee-110">이 문서에서는 보안 기능을 통해 전자 메일에서 감지된 맬웨어 및 피싱 시도를 보고 Microsoft 365 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-110">This article explains how to view and investigate malware and phishing attempts that are detected in email by Microsoft 365 security features.</span></span> 

<span data-ttu-id="492ee-111">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="492ee-111">**Applies to**</span></span>

- [<span data-ttu-id="492ee-112">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="492ee-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="492ee-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="492ee-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a><span data-ttu-id="492ee-114">전자 메일에서 검색된 맬웨어 보기</span><span class="sxs-lookup"><span data-stu-id="492ee-114">View malware detected in email</span></span>

<span data-ttu-id="492ee-115">전자 메일에서 검색된 맬웨어를 Microsoft 365 탐색기(또는 실시간 검색)의 전자 메일 > 맬웨어 보기를 사용합니다. [](threat-explorer-views.md#email--malware)</span><span class="sxs-lookup"><span data-stu-id="492ee-115">To see malware detected in email sorted by Microsoft 365 technology, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span> <span data-ttu-id="492ee-116">맬웨어는 기본 보기이기 때문에 탐색기를 여는 즉시 선택될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-116">Malware is the default view, so it may be selected as soon as you open Explorer.</span></span>

1. <span data-ttu-id="492ee-117">In the Security & Compliance Center ( <https://protection.office.com> ), choose Threat **management** \> **Explorer** (or **Real-time detections**).</span><span class="sxs-lookup"><span data-stu-id="492ee-117">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="492ee-118">(이 예제에서는 Explorer를 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="492ee-118">(This example uses Explorer.)</span></span>

   <span data-ttu-id="492ee-119">수렴된 Defender 포털에 있는 Microsoft 365 전자 메일 & <https://security.microsoft.com> **탐색기 로**  >  **스크롤합니다.**</span><span class="sxs-lookup"><span data-stu-id="492ee-119">If you're in the converged Microsoft 365 Defender portal (<https://security.microsoft.com>) scroll to **Email & collaboration** > **Explorer**.</span></span>

   <span data-ttu-id="492ee-120">여기에서 보기에서 시작하여 조사할 특정 시간 프레임(필요한 경우)을 선택하고 탐색기에서 진행하는 에 따라 필터에 [집중합니다.](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)</span><span class="sxs-lookup"><span data-stu-id="492ee-120">From here, start at the View, choose a particular frame of time to investigate (if needed), and focus your filters, as per the [Explorer walk- through](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through).</span></span>

2. <span data-ttu-id="492ee-121">보기 **메뉴에서** 전자 메일 **맬웨어** \> **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="492ee-121">In the **View** menu, choose **Email** \> **Malware**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="492ee-122">![탐색기용 보기 메뉴](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="492ee-122">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span>

3. <span data-ttu-id="492ee-123">보낸 **사람 을** 클릭한 다음 **기본** 검색 기술을 \> **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="492ee-123">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   <span data-ttu-id="492ee-124">이제 검색 기술을 보고서의 필터로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-124">Your detection technologies are now available as filters for the report.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="492ee-125">![맬웨어 감지 기술](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="492ee-125">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span>

4. <span data-ttu-id="492ee-126">옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-126">Choose an option.</span></span> <span data-ttu-id="492ee-127">그런 다음 새로 **고침 단추를** 선택하여 해당 필터를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-127">Then select the **Refresh** button to apply that filter.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="492ee-128">![선택한 검색 기술](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="492ee-128">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span>

   <span data-ttu-id="492ee-129">보고서가 새로 고쳐서 선택한 기술 옵션을 사용하여 전자 메일에서 맬웨어가 검색된 결과를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="492ee-129">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="492ee-130">여기에서 추가 분석을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-130">From here, you can conduct further analysis.</span></span> 

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="492ee-131">피싱 URL 보기 및 판정 데이터 클릭</span><span class="sxs-lookup"><span data-stu-id="492ee-131">View phishing URL and click verdict data</span></span>

<span data-ttu-id="492ee-132">허용, 차단 및 재지정된 URL 목록을 포함하여 전자 메일의 URL을 통해 피싱 시도를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-132">You can view phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="492ee-133">클릭한 URL을 식별하려면 안전한 [](safe-links.md) 링크를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-133">To identify URLs that were clicked, [Safe Links](safe-links.md) must be configured.</span></span> <span data-ttu-id="492ee-134">클릭 시간 보호 [](set-up-safe-links-policies.md) 및 안전한 링크로 클릭 판정 로깅에 대해 안전한 링크 정책을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-134">Make sure that you set up [Safe Links policies](set-up-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="492ee-135">메시지의 피싱 URL을 검토하고 피싱 메시지의 URL을 클릭하려면 탐색기 또는 실시간 검색의 전자 메일 [   >  **피싱**](threat-explorer-views.md#email--phish) 보기를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-135">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="492ee-136">In the Security & Compliance Center ( <https://protection.office.com> ), choose Threat **management** \> **Explorer** (or **Real-time detections**).</span><span class="sxs-lookup"><span data-stu-id="492ee-136">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="492ee-137">(이 예제에서는 Explorer를 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="492ee-137">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="492ee-138">보기 **메뉴에서** 전자 **메일** \> **피싱 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="492ee-138">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="492ee-139">![피싱 컨텍스트에서 탐색기 메뉴 보기](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="492ee-139">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="492ee-140">보낸 **사람 을**  클릭한 다음 URL 확인 \> **클릭 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="492ee-140">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="492ee-141">차단 및 다시 설정 차단과 같은 하나 이상의 옵션을 선택한  다음 해당 필터를 적용할 옵션과 같은 줄에서 새로 고침 단추를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="492ee-141">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="492ee-142">(브라우저 창을 새로 고치지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="492ee-142">(Don't refresh your browser window.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="492ee-143">![URL 및 클릭 판정](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="492ee-143">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span>

   <span data-ttu-id="492ee-144">보고서가 새로 고쳐지며 보고서 아래에 있는 URL 탭에 두 개의 서로 다른 URL 테이블이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-144">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="492ee-145">**상위 URL은** 필터링한 메시지의 URL과 각 URL에 대한 전자 메일 배달 작업 수입니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-145">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="492ee-146">피싱 전자 메일 보기에서 이 목록에는 일반적으로 합법적인 URL이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-146">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="492ee-147">공격자는 메시지에 좋은 URL과 잘못된 URL을 혼합하여 배달하려고 시도하지만 악의적인 링크가 더 흥미로워 보이게 합니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-147">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="492ee-148">URL 표는 총 전자 메일 수를 통해 정렬되지만 보기를 단순화하기 위해 이 열은 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-148">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="492ee-149">**위쪽 클릭은** 총 클릭 수별로 정렬된 클릭한 안전한 링크로 래핑된 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-149">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="492ee-150">보기를 단순화하기 위해 이 열도 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-150">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="492ee-151">열당 총 개수는 클릭한 각 URL에 대한 안전한 링크 클릭 결과 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-151">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="492ee-152">피싱 전자 메일 보기에서 이러한 URL은 일반적으로 의심스러우거나 악의적인 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-152">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="492ee-153">그러나 보기에는 위협이 아닌 피싱 메시지에 있는 URL이 포함되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-153">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="492ee-154">Url clicks on unwrapped links don't show up here.</span><span class="sxs-lookup"><span data-stu-id="492ee-154">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="492ee-155">두 URL 테이블에는 배달 작업 및 위치로 피싱 전자 메일 메시지의 상위 URL이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-155">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="492ee-156">표에는 경고에도 불구하고 차단되거나 방문한 URL 클릭이 표시 있으므로 사용자에게 제공된 잠재적인 잘못된 링크와 사용자가 클릭한 잠재적인 링크를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-156">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the users clicked.</span></span> <span data-ttu-id="492ee-157">여기에서 추가 분석을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-157">From here, you can conduct further analysis.</span></span> <span data-ttu-id="492ee-158">예를 들어 차트 아래에서 조직의 환경에서 차단된 전자 메일 메시지의 상위 URL을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-158">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="492ee-159">![차단된 탐색기 URL](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="492ee-159">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="492ee-160">자세한 정보를 확인하려면 URL을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-160">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="492ee-161">URL 플라이아웃 대화 상자에서 전자 메일 메시지에 대한 필터링이 제거되어 작업 환경에서 URL 노출에 대한 전체 보기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-161">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="492ee-162">이렇게 하면 탐색기에서 우려하는 전자 메일 메시지를 필터링하고, 잠재적 위협이 될 수 있는 특정 URL을 찾은 다음 탐색기 보기 자체에 URL 필터를 추가하지 않고도 URL 세부 정보 대화 상자를 통해 환경의 URL 노출에 대한 이해를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-162">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="492ee-163">클릭 판정 해석</span><span class="sxs-lookup"><span data-stu-id="492ee-163">Interpretation of click verdicts</span></span>

<span data-ttu-id="492ee-164">전자 메일 또는 URL 플라이아웃, Top Clicks 및 필터링 환경의 다양한 클릭 판정 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-164">In the Email or URL flyouts, Top Clicks, and in our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="492ee-165">**없음:** URL에 대한 판정을 캡처할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-165">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="492ee-166">사용자가 URL을 클릭한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-166">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="492ee-167">**허용:** 사용자가 URL로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-167">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="492ee-168">**차단된:** 사용자가 URL로 이동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-168">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="492ee-169">**보류 중인 판정:** 사용자에게 확인 대기 중인 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-169">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="492ee-170">**차단된 은(는)** 사용자가 URL로 직접 이동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-170">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="492ee-171">그러나 사용자가 URL로 이동하기 위해 차단을 어버렸다.</span><span class="sxs-lookup"><span data-stu-id="492ee-171">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="492ee-172">**보류 중인 판정이 무시됩니다.** 사용자에게 데토톤 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-172">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="492ee-173">그러나 사용자가 URL에 액세스하기 위해 메시지를 오버라이드합니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-173">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="492ee-174">**오류:** 사용자에게 오류 페이지가 표시되거나 판정을 캡처하는 중 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-174">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="492ee-175">**실패:** 판정을 캡처하는 동안 알 수 없는 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-175">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="492ee-176">사용자가 URL을 클릭한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-176">The user might have clicked through the URL.</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="492ee-177">자동화된 조사 및 대응 시작</span><span class="sxs-lookup"><span data-stu-id="492ee-177">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="492ee-178">자동화된 조사 및 대응 기능은 *Microsoft Defender for Office 365 Plan 2* 및 Office 365 *E5에서 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="492ee-178">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="492ee-179">[자동화된 조사 및 대응은](automated-investigation-response-office.md) 사이버 공격을 조사하고 완화하는 데 소요된 보안 운영 팀의 시간과 노력을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-179">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="492ee-180">보안 플레이북을 트리거할 수 있는 경고를 구성하는 것 외에도 탐색기 보기에서 자동화된 조사 및 응답 프로세스를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492ee-180">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="492ee-181">자세한 내용은 예제: 보안 관리자가 Explorer에서 [조사를 트리거합니다.를 참조합니다.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)</span><span class="sxs-lookup"><span data-stu-id="492ee-181">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="other-articles"></a><span data-ttu-id="492ee-182">기타 문서</span><span class="sxs-lookup"><span data-stu-id="492ee-182">Other articles</span></span>

[<span data-ttu-id="492ee-183">전자 메일 엔터티 페이지를 통해 전자 메일 조사</span><span class="sxs-lookup"><span data-stu-id="492ee-183">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)
