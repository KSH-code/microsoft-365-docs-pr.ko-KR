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
ms.openlocfilehash: 917ad3caf96a982df8b88058ff1c394b3d21dd75
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028559"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a><span data-ttu-id="6bd5d-103">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="6bd5d-103">Email security with Threat Explorer in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="6bd5d-104">이 문서의 내용</span><span class="sxs-lookup"><span data-stu-id="6bd5d-104">In this article:</span></span>

- [<span data-ttu-id="6bd5d-105">전자 메일에서 검색된 맬웨어 보기</span><span class="sxs-lookup"><span data-stu-id="6bd5d-105">View malware detected in email</span></span>](#view-malware-detected-in-email)
- [<span data-ttu-id="6bd5d-106">피싱 URL 보기 및 판정 데이터 클릭</span><span class="sxs-lookup"><span data-stu-id="6bd5d-106">View phishing URL and click verdict data</span></span>](#view-phishing-url-and-click-verdict-data)
- [<span data-ttu-id="6bd5d-107">자동화된 조사 및 대응 시작</span><span class="sxs-lookup"><span data-stu-id="6bd5d-107">Start automated investigation and response</span></span>](#start-automated-investigation-and-response)

> [!NOTE]
> <span data-ttu-id="6bd5d-108">이 문서는 위협 탐색기(탐색기) **,** 전자 메일 보안 및 **탐색기** 및 실시간 검색 기본(예: 도구 간 차이점 및 작동에 필요한 사용 권한)에 대한 **3개** 문서 시리즈의 일부입니다. </span><span class="sxs-lookup"><span data-stu-id="6bd5d-108">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="6bd5d-109">이 시리즈의 다른 두 문서는 위협 탐색기 및 [위협](threat-hunting-in-threat-explorer.md) 탐색기에서 위협 헌팅 및 실시간 검색 기본 [입니다.](real-time-detections.md)</span><span class="sxs-lookup"><span data-stu-id="6bd5d-109">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span> 

<span data-ttu-id="6bd5d-110">이 문서에서는 보안 기능을 통해 전자 메일에서 감지된 맬웨어 및 피싱 시도를 보고 Microsoft 365 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-110">This article explains how to view and investigate malware and phishing attempts that are detected in email by Microsoft 365 security features.</span></span> 

<span data-ttu-id="6bd5d-111">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="6bd5d-111">**Applies to**</span></span>

- [<span data-ttu-id="6bd5d-112">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="6bd5d-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6bd5d-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6bd5d-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a><span data-ttu-id="6bd5d-114">전자 메일에서 검색된 맬웨어 보기</span><span class="sxs-lookup"><span data-stu-id="6bd5d-114">View malware detected in email</span></span>

<span data-ttu-id="6bd5d-115">전자 메일에서 검색된 맬웨어를 Microsoft 365 탐색기(또는 실시간 검색)의 전자 메일 > 맬웨어 보기를 사용합니다. [](threat-explorer-views.md#email--malware)</span><span class="sxs-lookup"><span data-stu-id="6bd5d-115">To see malware detected in email sorted by Microsoft 365 technology, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span> <span data-ttu-id="6bd5d-116">맬웨어는 기본 보기이기 때문에 탐색기를 여는 즉시 선택될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-116">Malware is the default view, so it may be selected as soon as you open Explorer.</span></span>

1. <span data-ttu-id="6bd5d-117">in the Microsoft 365 Defender portal ( <https://security.microsoft.com> ), choose Email & **collaboration** \> **Explorer** (or **Real-time detections**).</span><span class="sxs-lookup"><span data-stu-id="6bd5d-117">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), choose **Email & collaboration** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="6bd5d-118">(이 예제에서는 Explorer를 사용합니다.) 수렴형 Microsoft 365 Defender 포털에 있는 경우 전자 메일 & https://security.microsoft.com/) **탐색기 로**  >  **스크롤합니다.**</span><span class="sxs-lookup"><span data-stu-id="6bd5d-118">(This example uses Explorer.) If you're in the converged Microsoft 365 Defender portal (https://security.microsoft.com/) scroll to **Email & collaboration** > **Explorer**.</span></span>

   <span data-ttu-id="6bd5d-119">여기에서 보기에서 시작하여 조사할 특정 시간 프레임(필요한 경우)을 선택하고 탐색기에서 진행하는 에 따라 필터에 [집중합니다.](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)</span><span class="sxs-lookup"><span data-stu-id="6bd5d-119">From here, start at the View, choose a particular frame of time to investigate (if needed), and focus your filters, as per the [Explorer walk- through](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through).</span></span>

2. <span data-ttu-id="6bd5d-120">보기 **메뉴에서** 전자 **메일에서 맬웨어를** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6bd5d-120">In the **View** menu, choose **Malware** under **Email**.</span></span>

3. <span data-ttu-id="6bd5d-121">보낸 **사람 을** 클릭한 다음 **기본** 검색 기술을 \> **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6bd5d-121">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   
   :::image type="content" source="../../media/exploreremailmalwaredetectiontech-newimg.png" alt-text="맬웨어 감지 기술":::

   <span data-ttu-id="6bd5d-123">이제 검색 기술을 보고서의 필터로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-123">Your detection technologies are now available as filters for the report.</span></span>

4. <span data-ttu-id="6bd5d-124">옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-124">Choose an option.</span></span> <span data-ttu-id="6bd5d-125">그런 다음 새로 **고침 단추를** 선택하여 해당 필터를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-125">Then select the **Refresh** button to apply that filter.</span></span>

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech2-new.png" alt-text="선택한 검색 기술"::: 

   <span data-ttu-id="6bd5d-127">보고서가 새로 고쳐서 선택한 기술 옵션을 사용하여 전자 메일에서 맬웨어가 검색된 결과를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="6bd5d-127">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="6bd5d-128">여기에서 추가 분석을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-128">From here, you can conduct further analysis.</span></span> 

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="6bd5d-129">피싱 URL 보기 및 판정 데이터 클릭</span><span class="sxs-lookup"><span data-stu-id="6bd5d-129">View phishing URL and click verdict data</span></span>

<span data-ttu-id="6bd5d-130">허용, 차단 및 재지정된 URL 목록을 포함하여 전자 메일의 URL을 통해 피싱 시도를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-130">You can view phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="6bd5d-131">클릭한 URL을 식별하려면 링크 Safe [구성해야](safe-links.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-131">To identify URLs that were clicked, [Safe Links](safe-links.md) must be configured.</span></span> <span data-ttu-id="6bd5d-132">클릭 시간 보호 [](set-up-safe-links-policies.md) 및 Safe 링크로 클릭 판정 로깅에 대한 링크 정책을 Safe 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-132">Make sure that you set up [Safe Links policies](set-up-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="6bd5d-133">메시지의 피싱 URL을 검토하고 피싱 메시지의 URL을 클릭하려면 탐색기 또는 실시간 검색의 전자 메일 [   >  **피싱**](threat-explorer-views.md#email--phish) 보기를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-133">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="6bd5d-134">in the Microsoft 365 Defender portal ( <https://security.microsoft.com> ), choose Email & **collaboration** \> **Explorer** (or **Real-time detections**).</span><span class="sxs-lookup"><span data-stu-id="6bd5d-134">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), choose **Email & collaboration** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="6bd5d-135">(이 예제에서는 Explorer를 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="6bd5d-135">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="6bd5d-136">보기 **메뉴에서** 전자 **메일** \> **피싱 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6bd5d-136">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6bd5d-137">![피싱 컨텍스트에서 탐색기 메뉴 보기](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="6bd5d-137">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="6bd5d-138">보낸 **사람 을**  클릭한 다음 URL 확인 \> **클릭 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6bd5d-138">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="6bd5d-139">차단 및 다시 설정 차단과 같은 하나 이상의 옵션을 선택한  다음 해당 필터를 적용할 옵션과 같은 줄에서 새로 고침 단추를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="6bd5d-139">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="6bd5d-140">(브라우저 창을 새로 고치지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="6bd5d-140">(Don't refresh your browser window.)</span></span>

    :::image type="content" source="../../media/threatexploreremailphishclickverdict-new.png" alt-text="URL 및 클릭 판정":::

   <span data-ttu-id="6bd5d-142">보고서가 새로 고쳐지며 보고서 아래에 있는 URL 탭에 두 개의 서로 다른 URL 테이블이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-142">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="6bd5d-143">**상위 URL은** 필터링한 메시지의 URL과 각 URL에 대한 전자 메일 배달 작업 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-143">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="6bd5d-144">피싱 전자 메일 보기에서 이 목록에는 일반적으로 합법적인 URL이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-144">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="6bd5d-145">공격자는 메시지에 좋은 URL과 잘못된 URL을 혼합하여 배달하려고 시도하지만 악의적인 링크가 더 흥미로워 보이게 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-145">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="6bd5d-146">URL 표는 총 전자 메일 수를 통해 정렬되지만 보기를 단순화하기 위해 이 열은 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-146">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="6bd5d-147">**위쪽 클릭은** Safe 총 클릭 수별로 정렬된 링크로 래핑된 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-147">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="6bd5d-148">보기를 단순화하기 위해 이 열도 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-148">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="6bd5d-149">열당 총 개수는 클릭한 각 URL에 Safe 링크 클릭 결과 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-149">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="6bd5d-150">피싱 전자 메일 보기에서 이러한 URL은 일반적으로 의심스러우거나 악의적인 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-150">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="6bd5d-151">그러나 보기에는 위협이 아닌 피싱 메시지에 있는 URL이 포함되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-151">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="6bd5d-152">Url clicks on unwrapped links don't show up here.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-152">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="6bd5d-153">두 URL 테이블에는 배달 작업 및 위치로 피싱 전자 메일 메시지의 상위 URL이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-153">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="6bd5d-154">표에는 경고에도 불구하고 차단되거나 방문한 URL 클릭이 표시 있으므로 사용자에게 제공된 잠재적인 잘못된 링크와 사용자가 클릭한 잠재적인 링크를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-154">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the users clicked.</span></span> <span data-ttu-id="6bd5d-155">여기에서 추가 분석을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-155">From here, you can conduct further analysis.</span></span> <span data-ttu-id="6bd5d-156">예를 들어 차트 아래에서 조직의 환경에서 차단된 전자 메일 메시지의 상위 URL을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-156">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6bd5d-157">![차단된 탐색기 URL](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="6bd5d-157">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="6bd5d-158">자세한 정보를 확인하려면 URL을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-158">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6bd5d-159">URL 플라이아웃 대화 상자에서 전자 메일 메시지에 대한 필터링이 제거되어 작업 환경에서 URL 노출에 대한 전체 보기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-159">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="6bd5d-160">이렇게 하면 탐색기에서 우려하는 전자 메일 메시지를 필터링하고, 잠재적 위협이 될 수 있는 특정 URL을 찾은 다음 탐색기 보기 자체에 URL 필터를 추가하지 않고도 URL 세부 정보 대화 상자를 통해 환경의 URL 노출에 대한 이해를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-160">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="6bd5d-161">클릭 판정 해석</span><span class="sxs-lookup"><span data-stu-id="6bd5d-161">Interpretation of click verdicts</span></span>

<span data-ttu-id="6bd5d-162">전자 메일 또는 URL 플라이아웃, Top Clicks 및 필터링 환경의 다양한 클릭 판정 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-162">In the Email or URL flyouts, Top Clicks, and in our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="6bd5d-163">**없음:** URL에 대한 판정을 캡처할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-163">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="6bd5d-164">사용자가 URL을 클릭한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-164">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="6bd5d-165">**허용:** 사용자가 URL로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-165">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="6bd5d-166">**차단된:** 사용자가 URL로 이동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-166">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="6bd5d-167">**보류 중인 판정:** 사용자에게 확인 대기 중인 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-167">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="6bd5d-168">**차단된 은(는)** 사용자가 URL로 직접 이동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-168">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="6bd5d-169">그러나 사용자가 URL로 이동하기 위해 차단을 어버렸다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-169">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="6bd5d-170">**보류 중인 판정이 무시됩니다.** 사용자에게 데토톤 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-170">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="6bd5d-171">그러나 사용자가 URL에 액세스하기 위해 메시지를 오버라이드합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-171">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="6bd5d-172">**오류:** 사용자에게 오류 페이지가 표시되거나 판정을 캡처하는 중 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-172">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="6bd5d-173">**실패:** 판정을 캡처하는 동안 알 수 없는 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-173">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="6bd5d-174">사용자가 URL을 클릭한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-174">The user might have clicked through the URL.</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="6bd5d-175">자동화된 조사 및 대응 시작</span><span class="sxs-lookup"><span data-stu-id="6bd5d-175">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="6bd5d-176">자동화된 조사 및 대응 기능은 *Microsoft Defender for Office 365 Plan 2* *및* Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-176">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="6bd5d-177">[자동화된 조사 및 대응은](automated-investigation-response-office.md) 사이버 공격을 조사하고 완화하는 데 소요된 보안 운영 팀의 시간과 노력을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-177">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="6bd5d-178">보안 플레이북을 트리거할 수 있는 경고를 구성하는 것 외에도 탐색기 보기에서 자동화된 조사 및 응답 프로세스를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-178">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="6bd5d-179">자세한 내용은 예제: 보안 관리자가 Explorer에서 [조사를 트리거합니다.를 참조합니다.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)</span><span class="sxs-lookup"><span data-stu-id="6bd5d-179">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="other-articles"></a><span data-ttu-id="6bd5d-180">기타 문서</span><span class="sxs-lookup"><span data-stu-id="6bd5d-180">Other articles</span></span>

[<span data-ttu-id="6bd5d-181">전자 메일 엔터티 페이지를 통해 전자 메일 조사</span><span class="sxs-lookup"><span data-stu-id="6bd5d-181">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)
