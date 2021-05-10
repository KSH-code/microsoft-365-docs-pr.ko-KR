---
title: Microsoft Defender for Microsoft Defender의 위협 탐색기에서 위협 Office 365
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
description: 보안 및 준수 센터의 위협 탐색기 또는 실시간 검색을 사용하여 위협을 효율적으로 조사하고 &amp; 대응합니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65fe67103d9a380c63a0362594c23290457ea3aa
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52295272"
---
# <a name="threat-hunting-in-threat-explorer-for-microsoft-defender-for-office-365"></a><span data-ttu-id="a688e-103">Microsoft Defender for Microsoft Defender의 위협 탐색기에서 위협 Office 365</span><span class="sxs-lookup"><span data-stu-id="a688e-103">Threat hunting in Threat Explorer for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="a688e-104">이 문서의 내용</span><span class="sxs-lookup"><span data-stu-id="a688e-104">In this article:</span></span>

- [<span data-ttu-id="a688e-105">위협 탐색기 Walk-through</span><span class="sxs-lookup"><span data-stu-id="a688e-105">Threat Explorer walk-through</span></span>](#threat-explorer-walk-through)
- [<span data-ttu-id="a688e-106">전자 메일 조사</span><span class="sxs-lookup"><span data-stu-id="a688e-106">Email investigation</span></span>](#email-investigation)
- [<span data-ttu-id="a688e-107">전자 메일 수정</span><span class="sxs-lookup"><span data-stu-id="a688e-107">Email remediation</span></span>](#email-remediation)
- [<span data-ttu-id="a688e-108">위협 헌팅 환경 개선</span><span class="sxs-lookup"><span data-stu-id="a688e-108">Improvements to threat hunting experience</span></span>](#improvements-to-threat-hunting-experience)

> [!NOTE]
> <span data-ttu-id="a688e-109">이 문서는 위협 탐색기(탐색기) **,** 전자 메일 보안 및 **탐색기** 및 실시간 검색 기본(예: 도구 간 차이점 및 작동에 필요한 사용 권한)에 대한 **3개** 문서 시리즈의 일부입니다. </span><span class="sxs-lookup"><span data-stu-id="a688e-109">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="a688e-110">이 시리즈의 다른 두 문서는 [위협](email-security-in-microsoft-defender.md) 탐색기를 사용하는 전자 메일 보안 및 위협 탐색기 및 실시간 검색 [기본입니다.](real-time-detections.md)</span><span class="sxs-lookup"><span data-stu-id="a688e-110">The other two articles in this series are [Email security with Threat Explorer](email-security-in-microsoft-defender.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span>


<span data-ttu-id="a688e-111">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="a688e-111">**Applies to**</span></span>
- [<span data-ttu-id="a688e-112">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="a688e-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a688e-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a688e-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a688e-114">조직에 microsoft [Defender for Office 365](defender-for-office-365.md)권한이 있는 경우 [](#required-licenses-and-permissions)탐색기 또는  실시간  검색을 사용하여 위협을 감지하고 치료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-114">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** or **Real-time detections** to detect and remediate threats.</span></span> 

<span data-ttu-id="a688e-115">보안 & 준수 센터에서 위협 **관리로** 이동한 다음   탐색기 또는 실시간 검색  **을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a688e-115">In the **Security & Compliance Center**, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<br>

****

|<span data-ttu-id="a688e-116">Microsoft Defender for Office 365 요금제 2를 사용하면 다음을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-116">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="a688e-117">Microsoft Defender for Office 365 요금제 1을 사용하면 다음을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-117">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![위협 탐색기](../../media/threatmgmt-explorer.png)|![실시간 탐지](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="a688e-120">다음 도구를 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-120">With these tools, you can:</span></span>

- <span data-ttu-id="a688e-121">보안 기능에서 검색된 맬웨어 Microsoft 365 참조</span><span class="sxs-lookup"><span data-stu-id="a688e-121">See malware detected by Microsoft 365 security features</span></span>
- <span data-ttu-id="a688e-122">피싱 URL 보기 및 판정 데이터 클릭</span><span class="sxs-lookup"><span data-stu-id="a688e-122">View phishing URL and click verdict data</span></span>
- <span data-ttu-id="a688e-123">탐색기 보기에서 자동화된 조사 및 응답 프로세스 시작</span><span class="sxs-lookup"><span data-stu-id="a688e-123">Start an automated investigation and response process from a view in Explorer</span></span>
- <span data-ttu-id="a688e-124">악성 전자 메일 조사 등</span><span class="sxs-lookup"><span data-stu-id="a688e-124">Investigate malicious email, and more</span></span>

<span data-ttu-id="a688e-125">자세한 내용은 [위협 탐색기를 사용하여 전자 메일 보안을 참조하세요.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="a688e-125">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span> 

## <a name="threat-explorer-walk-through"></a><span data-ttu-id="a688e-126">위협 탐색기 Walk-through</span><span class="sxs-lookup"><span data-stu-id="a688e-126">Threat Explorer walk-through</span></span>

<span data-ttu-id="a688e-127">Microsoft Defender for Office 365 요금제에는 플랜 1과 계획 2의 두 가지 구독 계획이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-127">In Microsoft Defender for Office 365, there are two subscription plans—Plan 1 and Plan 2.</span></span> <span data-ttu-id="a688e-128">수동으로 운영하는 위협 헌팅 도구는 각 계획에 있으며 이름과 기능이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-128">Manually operated Threat hunting tools exist in both plans, under different names and with different capabilities.</span></span>

<span data-ttu-id="a688e-129">Defender for Office 365 Plan 1은 계획 2의 위협 탐색기(탐색기라고도 하는 탐색기) 헌팅 도구의 하위 집합인 실시간 검색을 사용합니다.  </span><span class="sxs-lookup"><span data-stu-id="a688e-129">Defender for Office 365 Plan 1 uses *Real-time detections*, which is a subset of the *Threat Explorer* (also called *Explorer*) hunting tool in Plan 2.</span></span> <span data-ttu-id="a688e-130">이 문서 시리즈에서는 대부분의 예제가 전체 위협 탐색기를 사용하여 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-130">In this series of articles, most of the examples were created using the full Threat Explorer.</span></span> <span data-ttu-id="a688e-131">관리자는 실시간 검색의 모든 단계를 테스트하여 적용 위치를 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-131">Admins should test any steps in Real-time detections to see where they apply.</span></span>

<span data-ttu-id="a688e-132">탐색기 도구를 열기 위해 보안 및 준수 센터 위협 **&** 탐색기(또는 실시간 검색)로  >    >   **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="a688e-132">To open the Explorer tool, go to **Security & Compliance Center** > **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="a688e-133">기본적으로 맬웨어 페이지에 도착하지만 보기 드롭다운을 사용하여 옵션에 익숙해지게 됩니다.  </span><span class="sxs-lookup"><span data-stu-id="a688e-133">By default, you’ll arrive on the **Malware** page, but use the **View** drop down to get familiar with your options.</span></span> <span data-ttu-id="a688e-134">피싱을 헌팅하거나 위협 캠페인을 찾은 경우 해당 보기를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="a688e-134">If you’re hunting Phish, or digging into a threat campaign, choose those views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a688e-135">![위협 탐색기에서 보기 드롭다운](../../media/threat-explorer-view-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="a688e-135">![View drop down in Threat Explorer](../../media/threat-explorer-view-drop-down.png)</span></span>

<span data-ttu-id="a688e-136">보안 작업(초당 Ops) 사용자가 범위가 사용자 제출과 같은 좁은 보기인지 아니면 모든 전자 메일과 같은 더 넓은 보기인지에  따라 보낸 사람 단추를 사용하여 더 많은 필터링을 할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="a688e-136">Once a security operations (Sec Ops) person selects the data they want to see, whether the scope is narrow view like user **Submissions**, or a wider view, like **All email**, they can use the **Sender** button to further filter.</span></span> <span data-ttu-id="a688e-137">필터링 작업을 완료하려면 새로 고침을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-137">Remember to select Refresh to complete your filtering actions.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a688e-138">![위협 탐색기에서 보낸 사람 단추](../../media/threat-explorer-sender-button.png)</span><span class="sxs-lookup"><span data-stu-id="a688e-138">![Sender button in Threat Explorer](../../media/threat-explorer-sender-button.png)</span></span>

<span data-ttu-id="a688e-139">탐색기 또는 실시간 검색에서 포커스를 구체화하는 경우 계층에서 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-139">Refining focus in Explorer or Real-time detection can be thought of in layers.</span></span> <span data-ttu-id="a688e-140">첫 번째는 **보기입니다.**</span><span class="sxs-lookup"><span data-stu-id="a688e-140">The first is **View**.</span></span> <span data-ttu-id="a688e-141">두 번째는 필터링된 *포커스로 생각할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="a688e-141">The second can be thought of as a *filtered focus*.</span></span> <span data-ttu-id="a688e-142">예를 들어 다음과 같은 결정을 기록하여 위협을 찾는 데 수행한 단계를 다시 검색할 수 있습니다. 탐색기에서 문제를 찾으기 위해 받는 사람 필터 포커스가 있는 맬웨어 보기를 **선택했습니다.**</span><span class="sxs-lookup"><span data-stu-id="a688e-142">For example, you can retrace the steps you took in finding a threat by recording your decisions like this: To find the issue in Explorer, **I chose the Malware View with a Recipient filter focus**.</span></span> <span data-ttu-id="a688e-143">이렇게 하면 단계를 더 쉽게 방해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-143">This makes retracing your steps easier.</span></span>

> [!TIP]
> <span data-ttu-id="a688e-144">Sec Ops에서 **Tags를** 사용하여 높은 가치의 대상을 고려하는 계정을 표시하는 경우 태그 필터 포커스가 있는 피싱 보기(사용되는 경우 날짜 범위 *포함)와* 같은 선택을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-144">If Sec Ops uses **Tags** to mark accounts they consider high valued targets, they can make selections like *Phish View with a Tags filter focus (include a date range if used)*.</span></span> <span data-ttu-id="a688e-145">이렇게 하면 특정 피싱 공격이 해당 업계에서 많이 발생하고 있는 날짜와 같이 특정 기간 동안 높은 가치의 사용자 대상을 대상으로 하는 피싱 시도가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-145">This will show them any phishing attempts directed at their high value user targets during a time-range (like dates when certain phishing attacks are happening a lot for their industry).</span></span> 

<span data-ttu-id="a688e-146">날짜 범위 컨트롤을 사용하여 날짜 범위에 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-146">Refinements can be made on date ranges by using the date range controls.</span></span> <span data-ttu-id="a688e-147">검색 기술 필터 **포커스가** 있는 맬웨어 보기의 **탐색기를** 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-147">Here you can see Explorer in **Malware** view, with a **Detection Technology** filter focus.</span></span> <span data-ttu-id="a688e-148">그러나 Sec  Ops 팀이 깊이를 파고들 수 있는 고급 필터 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-148">But it’s the **Advanced filter** button that lets Sec Ops teams dig deep.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a688e-149">![위협 탐색기에서 고급 필터](../../media/threat-explorer-advanced-filter.png)</span><span class="sxs-lookup"><span data-stu-id="a688e-149">![Advanced filter in Threat Explorer](../../media/threat-explorer-advanced-filter.png)</span></span>

<span data-ttu-id="a688e-150">고급 **필터를 클릭하면** Sec Ops 헌터가 쿼리를 직접 작성하여 보는 데 필요한 정보를 포함하거나 제외할 수 있는 패널이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-150">Clicking the **Advanced filter** pops a panel that will let Sec Ops hunters build queries themselves, letting them include or exclude the information they need to see.</span></span> <span data-ttu-id="a688e-151">탐색기 페이지의 차트와 테이블에 결과가 모두 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-151">Both the chart and table on the Explorer page will reflect their results.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a688e-152">![쿼리 결과](../../media/threat-explorer-chart-table.png)</span><span class="sxs-lookup"><span data-stu-id="a688e-152">![Results from a query](../../media/threat-explorer-chart-table.png)</span></span>

<span data-ttu-id="a688e-153">열 옵션 **단추를 사용하여** 가장 유용한 표 정보의 종류를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-153">Use the **Column options** button to get the kind of information on the table that would be most helpful:</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a688e-154">![강조 표시된 열 옵션 단추](../../media/threat-explorer-column-options.png)</span><span class="sxs-lookup"><span data-stu-id="a688e-154">![Column options button highlighted](../../media/threat-explorer-column-options.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a688e-155">![열에서 사용 가능한 옵션](../../media/threat-explorer-column-options-details.png)</span><span class="sxs-lookup"><span data-stu-id="a688e-155">![Available options in Columns](../../media/threat-explorer-column-options-details.png)</span></span>

<span data-ttu-id="a688e-156">동일한 MIEN에서 디스플레이 옵션을 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-156">In the same mien, make sure to test your display options.</span></span> <span data-ttu-id="a688e-157">여러 대상이 동일한 데이터의 여러 프레젠테이션에 잘 반응합니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-157">Different audiences will react well to different presentations of the same data.</span></span> <span data-ttu-id="a688e-158">일부 뷰어의  경우 전자 메일 원본 맵은 위협이 바로 옆에 있는 캠페인  표시 옵션보다 광범위하거나 불연결하다는 메시지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-158">For some viewers, the **Email Origins** map can show that a threat is widespread or discreet more quickly than the **Campaign display** option right next to it.</span></span> <span data-ttu-id="a688e-159">Sec Ops는 이러한 디스플레이를 사용하여 보안 및 보호의 필요성을 가장 잘 설명하거나 나중에 비교하여 작업의 효과를 보여줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-159">Sec Ops can make use of these displays to best make points that underscore the need for security and protection, or for later comparison, to demonstrate the effectiveness of their actions.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a688e-160">![전자 메일 원본 지도](../../media/threat-explorer-email-origin-map.png)</span><span class="sxs-lookup"><span data-stu-id="a688e-160">![Email Origins map](../../media/threat-explorer-email-origin-map.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a688e-161">![캠페인 표시 옵션](../../media/threat-explorer-campaign-display.png)</span><span class="sxs-lookup"><span data-stu-id="a688e-161">![Campaign display options](../../media/threat-explorer-campaign-display.png)</span></span>

### <a name="email-investigation"></a><span data-ttu-id="a688e-162">전자 메일 조사</span><span class="sxs-lookup"><span data-stu-id="a688e-162">Email investigation</span></span>

<span data-ttu-id="a688e-163">의심스러운 전자 메일이 표시되고 이름을 클릭하여 오른쪽의 플라이아웃을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-163">When you see a suspicious email, click the name to expand the flyout on the right.</span></span> <span data-ttu-id="a688e-164">여기에서 Sec Ops에서 전자 메일 엔터티 페이지를 볼 수 있도록 하는 [배너를](mdo-email-entity-page.md) 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-164">Here, the banner that lets Sec Ops see the [email entity page](mdo-email-entity-page.md) is available.</span></span>

<span data-ttu-id="a688e-165">전자 메일 엔터티 페이지는 **세부** **정보,** 첨부 파일, 장치 아래에서 찾을 수 있는 콘텐츠를 끌어오지만 **보다** 체계적인 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-165">The email entity page pulls together contents that can be found under **Details**, **Attachments**, **Devices**, but includes more organized data.</span></span> <span data-ttu-id="a688e-166">여기에는 DMARC 결과, 복사 옵션을 사용하여 전자 메일 헤더의 일반 텍스트 표시, 안전하게 검색된 첨부 파일에 대한 결과 정보, 이러한 검색을 삭제한 파일(연락한 IP 주소, 페이지 또는 파일의 스크린샷 포함)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-166">This includes things like DMARC results, plain text display of the email header with a copy option, verdict information on attachments that were securely detonated, and files those detonations dropped (can include IP addresses that were contacted and screenshots of pages or files).</span></span> <span data-ttu-id="a688e-167">URL 및 해당 판정도 유사한 세부 정보 보고와 함께 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-167">URLs and their verdicts are also listed with similar details reported.</span></span> 

<span data-ttu-id="a688e-168">이 단계에 도달하면 전자 메일 엔터티 페이지가 최종 단계인 수정에 *중요합니다.*</span><span class="sxs-lookup"><span data-stu-id="a688e-168">When you reach this stage, the email entity page will be critical to the final step—*remediation*.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a688e-169">![전자 메일 엔터티 페이지](../../media/threat-explorer-email-entity-page.png)</span><span class="sxs-lookup"><span data-stu-id="a688e-169">![The email entity page](../../media/threat-explorer-email-entity-page.png)</span></span>

> [!TIP]
> <span data-ttu-id="a688e-170">검색된 첨부 파일 결과, 포함된 URL에  대한 결과 및 안전한 전자 메일 미리 보기의 결과를 포함하여 다양한 전자 메일 엔터티 페이지(분석 탭에서 아래 참조)에 대한 자세한 내용을 보려면 여기를 [클릭하세요.](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="a688e-170">To learn more about the rich email entity page (seen below on the **Analysis** tab), including the results of detonated Attachments, findings for included URLs, and safe Email preview, click [here](mdo-email-entity-page.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a688e-171">![전자 메일 엔터티 페이지의 분석 탭](../../media/threat-explorer-analysis-tab.png)</span><span class="sxs-lookup"><span data-stu-id="a688e-171">![Analysis tab of the email entity page](../../media/threat-explorer-analysis-tab.png)</span></span>

### <a name="email-remediation"></a><span data-ttu-id="a688e-172">전자 메일 수정</span><span class="sxs-lookup"><span data-stu-id="a688e-172">Email remediation</span></span>

<span data-ttu-id="a688e-173">초당 Ops 사용자가 전자 메일이 위협인지 확인하면 다음 탐색기 또는 실시간 검색 단계에서 위협을 처리하고 이를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-173">Once a Sec Ops person determines that an email is a threat, the next Explorer or Real-time detection step is dealing with the threat and remediating it.</span></span> <span data-ttu-id="a688e-174">위협 탐색기로 돌아가 문제 전자 메일의 확인란을 선택하고 작업 단추를 사용하여 이 작업을 **수행할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-174">This can be done by returning to Threat Explorer, selecting the checkbox for the problem email, and using the **Actions** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a688e-175">![위협 탐색기에서 동작 단추](../../media/threat-explorer-email-actions-button.png)</span><span class="sxs-lookup"><span data-stu-id="a688e-175">![Actions button in Threat Explorer](../../media/threat-explorer-email-actions-button.png)</span></span>

<span data-ttu-id="a688e-176">여기에서 분석가가 메일을 스팸, 피싱 또는 맬웨어로 보고하거나, 받는 사람에게 연락하거나, 계획 2가 있는 경우 자동화된 조사 및 대응(또는 AIR) 플레이북 트리거를 포함할 수 있는 추가 조사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-176">Here, the analyst can take actions like reporting the mail as Spam, Phishing, or Malware, contacting recipients, or further investigations that can include triggering Automated Investigation and Response (or AIR) playbooks (if you have Plan 2).</span></span> <span data-ttu-id="a688e-177">또는 메일을 정리된 것으로 보고할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-177">Or, the mail can also be reported as clean.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a688e-178">![동작 드롭다운](../../media/threat-explorer-email-actions-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="a688e-178">![The Actions drop down](../../media/threat-explorer-email-actions-drop-down.png)</span></span>

## <a name="improvements-to-threat-hunting-experience"></a><span data-ttu-id="a688e-179">위협 헌팅 환경 개선</span><span class="sxs-lookup"><span data-stu-id="a688e-179">Improvements to threat hunting experience</span></span>

### <a name="alert-id"></a><span data-ttu-id="a688e-180">경고 ID</span><span class="sxs-lookup"><span data-stu-id="a688e-180">Alert ID</span></span>

<span data-ttu-id="a688e-181">경고에서 위협 탐색기를 탐색할 때  보기는 경고 **ID로 필터링됩니다.**</span><span class="sxs-lookup"><span data-stu-id="a688e-181">When navigating from an alert into Threat Explorer, the **View** will be filtered by **Alert ID**.</span></span> <span data-ttu-id="a688e-182">이는 실시간 검색에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-182">This also applies in Real-time detection.</span></span> <span data-ttu-id="a688e-183">특정 경고와 관련된 메시지 및 전자 메일 합계(개수)가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-183">Messages relevant to the specific alert, and an email total (a count) are shown.</span></span> <span data-ttu-id="a688e-184">메시지가 경고의 일부이면 해당 메시지에서 관련 경고로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-184">You will be able to see if a message was part of an alert, as well as navigate from that message to the related alert.</span></span>

<span data-ttu-id="a688e-185">마지막으로 경고 ID가 URL에 포함됩니다. 예를 들면 다음과 같습니다. `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1`</span><span class="sxs-lookup"><span data-stu-id="a688e-185">Finally, alert ID is included in the URL, for example: `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1`</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a688e-186">![경고 ID 필터링](../../media/AlertID-Filter.png)</span><span class="sxs-lookup"><span data-stu-id="a688e-186">![Filtering for Alert ID](../../media/AlertID-Filter.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a688e-187">![경고 ID 세부 정보 플라이아웃](../../media/AlertID-DetailsFlyout.png)</span><span class="sxs-lookup"><span data-stu-id="a688e-187">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span></span>

### <a name="extending-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants"></a><span data-ttu-id="a688e-188">평가판 테넌트에 대한 탐색기(및 실시간 검색) 데이터 보존 및 검색 제한 확장</span><span class="sxs-lookup"><span data-stu-id="a688e-188">Extending Explorer (and Real-time detections) data retention and search limit for trial tenants</span></span> 

<span data-ttu-id="a688e-189">이러한 변경의 일환으로 분석가가 위협 탐색기에서 30일(7일에서 증가)에 걸쳐 전자 메일 데이터를 검색하고 필터링하고, Office P1 및 P2 평가판 테넌트에 대한 Defender에 대한 실시간 검색을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-189">As part of this change, analysts will be able to search for, and filter email data across 30 days (increased from seven days) in Threat Explorer and Real-time detections for both Defender for Office P1 and P2 trial tenants.</span></span> <span data-ttu-id="a688e-190">이는 보존 기본값이 이미 30일인 P1 및 P2 E5 고객의 프로덕션 테넌트에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-190">This doesn’t impact any production tenants for both P1 and P2 E5 customers, where the retention default is already 30 days.</span></span>

### <a name="updated-export-limit"></a><span data-ttu-id="a688e-191">업데이트된 내보내기 제한</span><span class="sxs-lookup"><span data-stu-id="a688e-191">Updated Export limit</span></span> 

<span data-ttu-id="a688e-192">위협 탐색기에서 내보낼 수 있는 전자 메일 레코드 수는 이제 200,000개(9990개)입니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-192">The number of Emails records that can be exported from Threat Explorer is now 200,000 (was 9990).</span></span> <span data-ttu-id="a688e-193">내보낼 수 있는 열 집합은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-193">The set of columns that can be exported is unchanged.</span></span> 

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="a688e-194">위협 탐색기에서 태그</span><span class="sxs-lookup"><span data-stu-id="a688e-194">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="a688e-195">사용자 태그 기능은 미리 보기에 있으며 모든 사용자가 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-195">The user tags feature is in Preview and may not be available to everyone.</span></span> <span data-ttu-id="a688e-196">또한 미리 보기는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-196">Also, Previews are subject to change.</span></span> <span data-ttu-id="a688e-197">릴리스 일정에 대한 자세한 내용은 Microsoft 365 로드맵을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a688e-197">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="a688e-198">사용자 태그는 Microsoft Defender에서 특정 사용자 그룹을 식별하여 Office 365.</span><span class="sxs-lookup"><span data-stu-id="a688e-198">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="a688e-199">라이선스 및 구성을 비롯한 태그에 대한 자세한 내용은 사용자 태그 [를 참조하세요.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="a688e-199">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="a688e-200">위협 탐색기에서 다음 환경의 사용자 태그에 대한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-200">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="a688e-201">전자 메일 그리드 보기</span><span class="sxs-lookup"><span data-stu-id="a688e-201">Email grid view</span></span>

<span data-ttu-id="a688e-202">분석가가 전자 메일 그리드의 **태그** 열을 보면 보낸 사람 또는 받는 사람 사서함에 적용된 모든 태그가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-202">When analysts look at the **Tags** column the email grid, they are seeing all tags that have been applied to sender or recipient mailboxes.</span></span> <span data-ttu-id="a688e-203">기본적으로 우선 순위 계정과 같은 *시스템 태그가* 먼저 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-203">By default, system tags like *priority accounts* are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a688e-204">![전자 메일 그리드 보기에서 태그 필터링](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="a688e-204">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="a688e-205">필터링</span><span class="sxs-lookup"><span data-stu-id="a688e-205">Filtering</span></span>

<span data-ttu-id="a688e-206">태그를 필터로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-206">Tags can be used as filters.</span></span> <span data-ttu-id="a688e-207">우선 순위 계정에서만 헌팅하거나 이러한 방식으로 특정 사용자 태그 시나리오를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-207">Hunt among priority accounts only, or use specific user tags scenarios this way.</span></span> <span data-ttu-id="a688e-208">특정 태그가 있는 결과를 제외할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-208">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="a688e-209">태그를 다른 필터 및 날짜 범위와 결합하여 조사 범위를 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-209">Combine Tags with other filters and date ranges to narrow your scope of investigation.</span></span> 

<span data-ttu-id="a688e-210">[![필터 태그](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="a688e-210">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a688e-211">![필터 태그 아미기](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="a688e-211">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="a688e-212">전자 메일 세부 정보 플라이아웃</span><span class="sxs-lookup"><span data-stu-id="a688e-212">Email detail flyout</span></span>

<span data-ttu-id="a688e-213">보낸 사람 및 받는 사람에 대한 개별 태그를 확인하려면 전자 메일을 선택하여 메시지 세부 정보 플라이아웃을 하세요.</span><span class="sxs-lookup"><span data-stu-id="a688e-213">To view the individual tags for sender and recipient, select an email to open the message details flyout.</span></span> <span data-ttu-id="a688e-214">요약 **탭에는** 보낸 사람 및 받는 사람 태그가 별도로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-214">On the **Summary** tab, the sender and recipient tags are shown separately.</span></span> <span data-ttu-id="a688e-215">보낸 사람 및 받는 사람에 대한 개별 태그에 대한 정보를 CSV 데이터로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-215">The information about individual tags for sender and recipient can be exported as CSV data.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a688e-216">![전자 메일 세부 정보 태그](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="a688e-216">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="a688e-217">태그 정보는 URL 클릭 플라이아웃에도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-217">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="a688e-218">Url 또는 URL 클릭 탭에서 피싱 또는 모든 **>** **보기로** 이동하세요. 해당 클릭과 연결된 태그를 포함하여 해당 URL의 클릭에 대한 추가 세부 정보를 보려면 개별 URL 플라이아웃을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-218">To see it, go to Phish or All Email view > **URLs** or **URL Clicks** tab. Select an individual URL flyout to see additional details about clicks for that URL, including any Tags associated with that click.</span></span>

### <a name="updated-timeline-view"></a><span data-ttu-id="a688e-219">업데이트된 시간 표시 막대 보기</span><span class="sxs-lookup"><span data-stu-id="a688e-219">Updated Timeline View</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a688e-220">![URL 태그](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="a688e-220">![URL tags](../../media/tags-urls.png)</span></span>
>
<span data-ttu-id="a688e-221">[이 비디오](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4)를 시청하여 자세히 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a688e-221">Learn more by watching [this video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span></span>

## <a name="extended-capabilities"></a><span data-ttu-id="a688e-222">확장된 기능</span><span class="sxs-lookup"><span data-stu-id="a688e-222">Extended capabilities</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="a688e-223">상위 대상 사용자</span><span class="sxs-lookup"><span data-stu-id="a688e-223">Top targeted users</span></span>

<span data-ttu-id="a688e-224">상위 맬웨어 패밀리는 맬웨어 섹션에서 대상이 가장 **많은** 사용자를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-224">Top Malware Families shows the **top targeted users** in the Malware section.</span></span> <span data-ttu-id="a688e-225">상위 대상 사용자도 피싱 및 모든 전자 메일 보기를 통해 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-225">Top targeted users will be extended through Phish and All Email views too.</span></span> <span data-ttu-id="a688e-226">분석가가 상위 5명을 대상으로 하는 사용자와 각 보기에서 각 사용자에 대한 시도 횟수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-226">Analysts will be able to see the top-five targeted users, along with the number of attempts for each user in each view.</span></span> 

<span data-ttu-id="a688e-227">보안 작업 사용자가 각 전자 메일 보기에 대한 오프라인 분석을 위해 시도 횟수와 함께 대상 사용자 목록을 최대 3,000개까지 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-227">Security operations people be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts made, for offline analysis for each email view.</span></span> <span data-ttu-id="a688e-228">또한 시도 횟수(예: 아래 이미지에서 13회 시도)를 선택하면 위협 탐색기에서 필터링된 보기가 열리기 때문에 전자 메일에서 더 많은 세부 정보 및 해당 사용자에 대한 위협을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-228">Also, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails, and threats for that user.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a688e-229">![상위 대상 사용자](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="a688e-229">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="a688e-230">Exchange 전송 규칙</span><span class="sxs-lookup"><span data-stu-id="a688e-230">Exchange transport rules</span></span>

<span data-ttu-id="a688e-231">보안 운영 팀은 전자 메일 그리드 보기에서 메시지에 적용되는 모든 Exchange 전송 규칙(또는 메일 흐름 규칙)을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-231">The security operations team will be able to see all the Exchange transport rules (or Mail flow rules) applied to a message, in the Email grid view.</span></span> <span data-ttu-id="a688e-232">표에서 **열** 옵션을 선택한 다음 열 **옵션에서** Exchange 전송 규칙 추가를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-232">Select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="a688e-233">전송 Exchange 옵션도 전자 메일의 **세부** 정보 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-233">The Exchange transport rules option is also visible on the **Details** flyout in the email.</span></span> 

<span data-ttu-id="a688e-234">메시지에 적용된 전송 규칙의 이름과 GUID가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-234">Names and GUIDs of the transport rules applied to the message appear.</span></span> <span data-ttu-id="a688e-235">분석가가 전송 규칙의 이름을 사용하여 메시지를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-235">Analysts will be able to search for messages by using the name of the transport rule.</span></span> <span data-ttu-id="a688e-236">이는 포함 검색으로, 부분 검색도 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-236">This is a CONTAINS search, which means you can do partial searches as well.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="a688e-237">Exchange 규칙 검색 및 이름 사용 가능 여부는 사용자에게 할당된 특정 역할에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-237">Exchange transport rule search and name availability depend on the specific role assigned to you.</span></span> <span data-ttu-id="a688e-238">전송 규칙 이름을 보고 검색하려면 다음 역할 또는 사용 권한 중 하나를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-238">You need to have one of the following roles or permissions to view the transport rule names and search.</span></span> <span data-ttu-id="a688e-239">그러나 아래의 역할이나 사용 권한이 없는 경우에도 분석가가 전자 메일 세부 정보에서 전송 규칙 레이블 및 GUID 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-239">However, even without the roles or permissions below, an analyst may see the transport rule label and GUID information in the Email Details.</span></span> <span data-ttu-id="a688e-240">전자 메일 그리드, 전자 메일 플라이아웃, 필터 및 내보내기의 기타 레코드 보기 환경은 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-240">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>
>
> - <span data-ttu-id="a688e-241">Exchange Online Only - 데이터 손실 방지: 모두</span><span class="sxs-lookup"><span data-stu-id="a688e-241">Exchange Online Only - Data Loss Prevention: All</span></span>
> - <span data-ttu-id="a688e-242">Exchange Online Only - O365SupportViewConfig: All</span><span class="sxs-lookup"><span data-stu-id="a688e-242">Exchange Online Only - O365SupportViewConfig: All</span></span>
> - <span data-ttu-id="a688e-243">Microsoft Azure Active Directory 또는 Exchange Online - 보안 관리자: 모두</span><span class="sxs-lookup"><span data-stu-id="a688e-243">Microsoft Azure Active Directory or Exchange Online - Security Admin: All</span></span>
> - <span data-ttu-id="a688e-244">Azure Active Directory 또는 Exchange Online - 보안 판독기: 모두</span><span class="sxs-lookup"><span data-stu-id="a688e-244">Azure Active Directory or Exchange Online - Security Reader: All</span></span>
> - <span data-ttu-id="a688e-245">Exchange Online Only - 전송 규칙: 모두</span><span class="sxs-lookup"><span data-stu-id="a688e-245">Exchange Online Only - Transport Rules: All</span></span>
> - <span data-ttu-id="a688e-246">Exchange Online Only - View-Only 구성: 모두</span><span class="sxs-lookup"><span data-stu-id="a688e-246">Exchange Online Only - View-Only Configuration: All</span></span>
>
> <span data-ttu-id="a688e-247">전자 메일 그리드, 세부 정보 플라이아웃 및 내보내는 CSV 내에서 ETRS에는 아래 표시된 이름/GUID가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-247">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>
>
> > [!div class="mx-imgBorder"]
> > <span data-ttu-id="a688e-248">![Exchange 전송 규칙](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="a688e-248">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="a688e-249">인바운드 커넥터</span><span class="sxs-lookup"><span data-stu-id="a688e-249">Inbound connectors</span></span>

<span data-ttu-id="a688e-250">커넥터는 조직 또는 조직에서 전자 메일이 전송되는 방법을 사용자 지정하는 Microsoft 365 Office 365 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-250">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="a688e-251">보안 제한 또는 제어를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-251">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="a688e-252">위협 탐색기에서 전자 메일과 관련된 커넥터를 보고 커넥터 이름을 사용하여 전자 메일을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-252">In Threat Explorer, you can view the connectors that are related to an email and search for emails using connector names.</span></span> 

<span data-ttu-id="a688e-253">커넥터 검색은 포함 쿼리로, 부분 키워드 검색이 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-253">The search for connectors is a CONTAINS query, which means partial keyword searches can work:</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a688e-254">![커넥터 세부 정보](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="a688e-254">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="a688e-255">필수 라이선스 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="a688e-255">Required licenses and permissions</span></span>

<span data-ttu-id="a688e-256">탐색기 또는 실시간 Office 365 사용하려면 [Microsoft Defender가](defender-for-office-365.md) 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-256">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="a688e-257">Explorer는 Plan 2용 Defender에 Office 365 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-257">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="a688e-258">실시간 검색 보고서는 Plan 1의 Defender에 Office 365 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-258">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="a688e-259">Defender에서 보호해야 하는 모든 사용자에 대해 라이선스를 할당할 Office 365.</span><span class="sxs-lookup"><span data-stu-id="a688e-259">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="a688e-260">탐색기 및 실시간 검색은 사용이 허가된 사용자에 대한 검색 데이터를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="a688e-260">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="a688e-261">탐색기 또는 실시간 검색을 보고 사용하려면 다음이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-261">To view and use Explorer or Real-time detections, you must have the following:</span></span>

- <span data-ttu-id="a688e-262">보안 및 준수 &:</span><span class="sxs-lookup"><span data-stu-id="a688e-262">For the Security & Compliance Center:</span></span>

  - <span data-ttu-id="a688e-263">조직 관리</span><span class="sxs-lookup"><span data-stu-id="a688e-263">Organization Management</span></span>
  - <span data-ttu-id="a688e-264">보안 관리자(Azure Active Directory 관리 센터에서 할당할 수 있습니다. <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="a688e-264">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="a688e-265">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="a688e-265">Security Reader</span></span>

- <span data-ttu-id="a688e-266">다음 Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="a688e-266">For Exchange Online:</span></span>

  - <span data-ttu-id="a688e-267">조직 관리</span><span class="sxs-lookup"><span data-stu-id="a688e-267">Organization Management</span></span>
  - <span data-ttu-id="a688e-268">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="a688e-268">View-Only Organization Management</span></span>
  - <span data-ttu-id="a688e-269">보기 전용 받는 사람</span><span class="sxs-lookup"><span data-stu-id="a688e-269">View-Only Recipients</span></span>
  - <span data-ttu-id="a688e-270">준수 관리</span><span class="sxs-lookup"><span data-stu-id="a688e-270">Compliance Management</span></span>

<span data-ttu-id="a688e-271">역할 및 사용 권한에 대한 자세한 내용은 다음 리소스를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-271">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="a688e-272">보안 및 준수 센터의 사용 권한</span><span class="sxs-lookup"><span data-stu-id="a688e-272">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="a688e-273">Exchange Online의 기능 사용 권한</span><span class="sxs-lookup"><span data-stu-id="a688e-273">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="a688e-274">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="a688e-274">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="a688e-275">추가 정보</span><span class="sxs-lookup"><span data-stu-id="a688e-275">More information</span></span>

- [<span data-ttu-id="a688e-276">배달된 악성 전자 메일 찾기 및 조사</span><span class="sxs-lookup"><span data-stu-id="a688e-276">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md) 
- [<span data-ttu-id="a688e-277">SharePoint Online, OneDrive 및 파일에서 검색된 악성 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a688e-277">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md) 
- [<span data-ttu-id="a688e-278">위협 탐색기(및 실시간 검색)에서 보기에 대한 개요를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="a688e-278">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md) 
- [<span data-ttu-id="a688e-279">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="a688e-279">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report) 
- [<span data-ttu-id="a688e-280">Microsoft Threat Protection의 자동화된 조사 및 대응</span><span class="sxs-lookup"><span data-stu-id="a688e-280">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md) 
- [<span data-ttu-id="a688e-281">전자 메일 엔터티 페이지를 통해 전자 메일 조사</span><span class="sxs-lookup"><span data-stu-id="a688e-281">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)