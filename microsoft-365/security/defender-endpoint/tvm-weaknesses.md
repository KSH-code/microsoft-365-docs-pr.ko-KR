---
title: 조직의 취약성 - 위협 및 취약성 관리
description: 조직에서 실행되는 소프트웨어에서 발견되는 취약점의 일반적인 CVE(취약성 및 노출) ID를 나열합니다. Microsoft Defender for Endpoint 위협 및 취약성 관리 기능에 의해 검색됩니다.
keywords: Microsoft Defender for Endpoint threat & management, threat and vulnerability management, Microsoft Defender for Endpoint tvm vulnerabilites page, finding vulnerabilites through tvm, tvm vulnerability list, vulnerability details in tvm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a8039a06dc58c31158f90d39857ffbeba92138d5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933076"
---
# <a name="vulnerabilities-in-my-organization---threat-and-vulnerability-management"></a><span data-ttu-id="e5b8a-105">조직의 취약성 - 위협 및 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="e5b8a-105">Vulnerabilities in my organization - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e5b8a-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e5b8a-106">**Applies to:**</span></span>
- [<span data-ttu-id="e5b8a-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e5b8a-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="e5b8a-108">위협 및 취약점 관리</span><span class="sxs-lookup"><span data-stu-id="e5b8a-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="e5b8a-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5b8a-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e5b8a-110">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="e5b8a-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e5b8a-111">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="e5b8a-112">위협 및 취약성 관리는 끝점의 끝점 보호를 위해 Defender의 동일한 신호를 사용하여 취약점을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-112">Threat and vulnerability management uses the same signals in Defender for Endpoint's endpoint protection to scan and detect vulnerabilities.</span></span>

<span data-ttu-id="e5b8a-113">취약점 **페이지에는** CVE(Common Vulnerabilities and Exposures) ID를 나열하여 장치가 노출하는 소프트웨어 취약점이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-113">The **Weaknesses** page lists the software vulnerabilities your devices are exposed to by listing the Common Vulnerabilities and Exposures (CVE) ID.</span></span> <span data-ttu-id="e5b8a-114">또한 심각도, CVSS(Common Vulnerability Scoring System) 등급, 조직의 보급, 해당 위반, 위협 정보 등도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-114">You can also view the severity, Common Vulnerability Scoring System (CVSS) rating, prevalence in your organization, corresponding breach, threat insights, and more.</span></span>

>[!NOTE]
><span data-ttu-id="e5b8a-115">취약점에 공식 CVE-ID가 할당되지 않은 경우 취약성 이름은 위협 및 취약성 관리에 의해 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-115">If there is no official CVE-ID assigned to a vulnerability, the vulnerability name is assigned by threat and vulnerability management.</span></span>

>[!TIP]
><span data-ttu-id="e5b8a-116">새 취약성 이벤트에 대한 전자 메일을 얻습니다. [끝점용 Microsoft Defender에서 취약성](configure-vulnerability-email-notifications.md) 전자 메일 알림 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-weaknesses-page"></a><span data-ttu-id="e5b8a-117">약점 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-117">Navigate to the Weaknesses page</span></span>

<span data-ttu-id="e5b8a-118">몇 가지 다른 방법으로 취약점 페이지에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-118">Access the Weaknesses page a few different ways:</span></span>

- <span data-ttu-id="e5b8a-119">Microsoft  Defender 보안 센터의 위협 및 취약성 관리 탐색 메뉴에서 [약점 선택](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e5b8a-119">Selecting **Weaknesses** from the threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md)</span></span>
- <span data-ttu-id="e5b8a-120">전역 검색</span><span class="sxs-lookup"><span data-stu-id="e5b8a-120">Global search</span></span>

### <a name="navigation-menu"></a><span data-ttu-id="e5b8a-121">탐색 메뉴</span><span class="sxs-lookup"><span data-stu-id="e5b8a-121">Navigation menu</span></span>

<span data-ttu-id="e5b8a-122">위협 및 취약성 관리 탐색 메뉴로 이동하고 취약점을 선택하여 CV 목록을 열 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="e5b8a-122">Go to the threat and vulnerability management navigation menu and select **Weaknesses** to open the list of CVEs.</span></span>

### <a name="vulnerabilities-in-global-search"></a><span data-ttu-id="e5b8a-123">전역 검색의 취약성</span><span class="sxs-lookup"><span data-stu-id="e5b8a-123">Vulnerabilities in global search</span></span>

1. <span data-ttu-id="e5b8a-124">전역 검색 드롭다운 메뉴로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-124">Go to the global search drop-down menu.</span></span>
2. <span data-ttu-id="e5b8a-125">찾고 **있는** CVE(Common Vulnerabilities and Exposures) ID의 취약성 및 키-를 선택한 다음 검색 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-125">Select **Vulnerability** and key-in the Common Vulnerabilities and Exposures (CVE) ID that you're looking for, then select the search icon.</span></span> <span data-ttu-id="e5b8a-126">취약점 **페이지가** 원하는 CVE 정보로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-126">The **Weaknesses** page opens with the CVE information that you're looking for.</span></span>
<span data-ttu-id="e5b8a-127">![드롭다운 옵션 "취약성"이 선택되고 예제 CVE가 있는 전역 검색 상자입니다.](images/tvm-vuln-globalsearch.png)</span><span class="sxs-lookup"><span data-stu-id="e5b8a-127">![Global search box with the dropdown option "vulnerability" selected and an example CVE.](images/tvm-vuln-globalsearch.png)</span></span>
3. <span data-ttu-id="e5b8a-128">CVE를 선택하여 취약성 설명, 세부 정보, 위협 정보 및 노출된 장치를 비롯한 자세한 정보가 있는 플라이아웃 패널을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-128">Select the CVE to open a flyout panel with more information, including the vulnerability description, details, threat insights, and exposed devices.</span></span>

<span data-ttu-id="e5b8a-129">취약점 페이지에서 나머지 취약점을 **확인하려면** CVE를 입력한 다음 검색을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-129">To see the rest of the vulnerabilities in the **Weaknesses** page, type CVE, then select search.</span></span>

## <a name="weaknesses-overview"></a><span data-ttu-id="e5b8a-130">약점 개요</span><span class="sxs-lookup"><span data-stu-id="e5b8a-130">Weaknesses overview</span></span>

<span data-ttu-id="e5b8a-131">노출된 장치의 취약점을 수정하여 자산 및 조직에 대한 위험을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-131">Remediate the vulnerabilities in exposed devices to reduce the risk to your assets and organization.</span></span> <span data-ttu-id="e5b8a-132">노출된 **장치 열에** 0이 표시되면 위험에 노출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-132">If the **Exposed Devices** column shows 0, that means you aren't at risk.</span></span>

![약점 방문 페이지.](images/tvm-weaknesses-overview.png)

### <a name="breach-and-threat-insights"></a><span data-ttu-id="e5b8a-134">위반 및 위협 정보</span><span class="sxs-lookup"><span data-stu-id="e5b8a-134">Breach and threat insights</span></span>

<span data-ttu-id="e5b8a-135">아이콘이 빨간색으로 표시될 때  위협 열에서 관련 위반 및 위협 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-135">View any related breach and threat insights in the **Threat** column when the icons are colored red.</span></span>

 >[!NOTE]
 > <span data-ttu-id="e5b8a-136">항상 지속적인 위협과 관련된 권장 사항의 우선 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-136">Always prioritize recommendations that are associated with ongoing threats.</span></span> <span data-ttu-id="e5b8a-137">이러한 권장 사항은 위협 인사이트 아이콘 빨간색 버그의 ![ 간단한 그리기로 표시됩니다.](images/tvm_bug_icon.png)</span><span class="sxs-lookup"><span data-stu-id="e5b8a-137">These recommendations are marked with the threat insight icon ![Simple drawing of a red bug.](images/tvm_bug_icon.png)</span></span> <span data-ttu-id="e5b8a-138">및 위반 인사이트 아이콘 ![ 대상을 타격하는 화살표의 간단한 그리기입니다. ](images/tvm_alert_icon.png) .</span><span class="sxs-lookup"><span data-stu-id="e5b8a-138">and breach insight icon ![Simple drawing of an arrow hitting a target.](images/tvm_alert_icon.png).</span></span>  

<span data-ttu-id="e5b8a-139">조직에 취약점이 발견된 경우 위반 정보 아이콘이 강조 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-139">The breach insights icon is highlighted if there's a vulnerability found in your organization.</span></span>
<span data-ttu-id="e5b8a-140">![아이콘을 마우스로 찰 때 표시될 수 있는 위반 인사이트 텍스트의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-140">![Example of a breach insights text that could show up when hovering over icon.</span></span> <span data-ttu-id="e5b8a-141">"가능한 활성 경고가 이 권장과 연결됩니다.](images/tvm-breach-insights.png)</span><span class="sxs-lookup"><span data-stu-id="e5b8a-141">This one says "possible active alert is associated with this recommendation.](images/tvm-breach-insights.png)</span></span>

<span data-ttu-id="e5b8a-142">조직에서 발견된 취약점에 관련된 악용이 있는 경우 위협 정보 아이콘이 강조 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-142">The threat insights icon is highlighted if there are associated exploits in the vulnerability found in your organization.</span></span> <span data-ttu-id="e5b8a-143">아이콘 위에 마우스를 대면 위협이 악용 키트의 일부인지 또는 특정 고급 영구적 캠페인 또는 활동 그룹에 연결되어 있는지를 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-143">Hovering over the icon shows whether the threat is a part of an exploit kit, or connected to specific advanced persistent campaigns or activity groups.</span></span> <span data-ttu-id="e5b8a-144">사용 가능한 경우 제로 데이 악용 뉴스, 공개 또는 관련 보안 권고가 있는 Threat Analytics 보고서에 대한 링크가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-144">When available, there's a link to a Threat Analytics report with zero-day exploitation news, disclosures, or related security advisories.</span></span>  

![아이콘을 마우스로 찰 때 표시될 수 있는 위협 정보 텍스트입니다.](images/tvm-threat-insights.png)

### <a name="gain-vulnerability-insights"></a><span data-ttu-id="e5b8a-147">취약성 인사이트 얻기</span><span class="sxs-lookup"><span data-stu-id="e5b8a-147">Gain vulnerability insights</span></span>

<span data-ttu-id="e5b8a-148">CVE를 선택하면 취약성 설명, 세부 정보, 위협 정보 및 노출된 장치와 같은 추가 정보가 있는 플라이아웃 패널이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-148">If you select a CVE, a flyout panel will open with more information such as the vulnerability description, details, threat insights, and exposed devices.</span></span>

- <span data-ttu-id="e5b8a-149">관련 시나리오에 "OS 기능" 범주가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-149">The "OS Feature" category is shown in relevant scenarios</span></span>
- <span data-ttu-id="e5b8a-150">노출된 장치를 사용하여 모든 CVE에 대한 관련 보안 권장으로 이동하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-150">You can go to the related security recommendation for every CVE with exposed device</span></span>

 ![약점 플라이아웃 예](images/tvm-weakness-flyout400.png)

### <a name="software-that-isnt-supported"></a><span data-ttu-id="e5b8a-152">지원되지 않는 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="e5b8a-152">Software that isn't supported</span></span>

<span data-ttu-id="e5b8a-153">위협 요소 및 취약성 관리에 의해 현재 지원되지 & 소프트웨어의 CV는 취약점 페이지에 여전히 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-153">CVEs for software that isn't currently supported by threat & vulnerability management is still present in the Weaknesses page.</span></span> <span data-ttu-id="e5b8a-154">소프트웨어가 지원되지 않는 경우 제한된 데이터만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-154">Because the software is not supported, only limited data will be available.</span></span>

<span data-ttu-id="e5b8a-155">지원되지 않는 소프트웨어가 있는 CV에서는 노출된 장치 정보를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-155">Exposed device information will not be available for CVEs with unsupported software.</span></span> <span data-ttu-id="e5b8a-156">"노출된 장치" 섹션에서 "사용할 수 없습니다" 옵션을 선택하여 지원되지 않는 소프트웨어로 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-156">Filter by unsupported software by selecting the "Not available" option in the "Exposed devices" section.</span></span>

 ![노출된 장치 필터.](images/tvm-exposed-devices-filter.png)

## <a name="view-common-vulnerabilities-and-exposures-cve-entries-in-other-places"></a><span data-ttu-id="e5b8a-158">다른 위치의 CVE(공통 취약성 및 노출) 항목 보기</span><span class="sxs-lookup"><span data-stu-id="e5b8a-158">View Common Vulnerabilities and Exposures (CVE) entries in other places</span></span>

### <a name="top-vulnerable-software-in-the-dashboard"></a><span data-ttu-id="e5b8a-159">대시보드에서 가장 취약한 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="e5b8a-159">Top vulnerable software in the dashboard</span></span>

1. <span data-ttu-id="e5b8a-160">위협 및 [취약성](tvm-dashboard-insights.md) 관리 대시보드로 이동하여 취약한 최상위 소프트웨어 위젯으로 **아래로 스크롤합니다.**</span><span class="sxs-lookup"><span data-stu-id="e5b8a-160">Go to the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) and scroll down to the **Top vulnerable software** widget.</span></span> <span data-ttu-id="e5b8a-161">각 소프트웨어에서 발견되는 취약점의 수와 위협 정보 및 시간이 지날 때마다 디바이스 노출에 대한 높은 수준의 보기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-161">You will see the number of vulnerabilities found in each software, along with threat information and a high-level view of device exposure over time.</span></span>

    ![소프트웨어, 약점, 위협, 노출된 장치 등 네 개의 열로 가장 취약한 소프트웨어 카드입니다.](images/tvm-top-vulnerable-software500.png)

2. <span data-ttu-id="e5b8a-163">조사할 소프트웨어를 선택하여 드릴다운 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-163">Select the software you want to investigate to go to a drilldown page.</span></span>
3. <span data-ttu-id="e5b8a-164">검색된 **취약성 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-164">Select the **Discovered vulnerabilities** tab.</span></span>
4. <span data-ttu-id="e5b8a-165">취약점 세부 정보에 대한 자세한 내용을 조사할 취약점 선택</span><span class="sxs-lookup"><span data-stu-id="e5b8a-165">Select the vulnerability you want to investigate for more information on vulnerability details</span></span>

    ![Windows Server 2019 드릴다운 개요.](images/windows-server-drilldown.png)

### <a name="discover-vulnerabilities-in-the-device-page"></a><span data-ttu-id="e5b8a-167">디바이스 페이지에서 취약점 검색</span><span class="sxs-lookup"><span data-stu-id="e5b8a-167">Discover vulnerabilities in the device page</span></span>

<span data-ttu-id="e5b8a-168">장치 페이지에서 관련 약점 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-168">View related weaknesses information in the device page.</span></span>

1. <span data-ttu-id="e5b8a-169">Microsoft Defender 보안 센터 탐색 메뉴 모음으로 이동한 다음 장치 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-169">Go to the Microsoft Defender Security Center navigation menu bar, then select the device icon.</span></span> <span data-ttu-id="e5b8a-170">장치 **목록 페이지가** 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-170">The **Devices list** page opens.</span></span>
2. <span data-ttu-id="e5b8a-171">장치 **목록 페이지에서** 조사할 장치 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-171">In the **Devices list** page, select the device name that you want to investigate.</span></span>

    ![조사할 선택한 장치가 있는 장치 목록입니다.](images/tvm_machinetoinvestigate.png)

3. <span data-ttu-id="e5b8a-173">조사할 장치에 대한 세부 정보 및 응답 옵션이 있는 장치 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-173">The device page will open with details and response options for the device you want to investigate.</span></span>
4. <span data-ttu-id="e5b8a-174">검색된 **취약성을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e5b8a-174">Select **Discovered vulnerabilities**.</span></span>

    ![세부 정보 및 응답 옵션이 있는 장치 페이지입니다.](images/tvm-discovered-vulnerabilities.png)

5. <span data-ttu-id="e5b8a-176">조사할 취약점을 선택하여 CVE 세부 정보(예: 취약성 설명, 위협 정보 및 검색 논리)가 있는 플라이아웃 패널을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-176">Select the vulnerability that you want to investigate to open up a flyout panel with the CVE details, such as: vulnerability description, threat insights, and detection logic.</span></span>

#### <a name="cve-detection-logic"></a><span data-ttu-id="e5b8a-177">CVE 검색 논리</span><span class="sxs-lookup"><span data-stu-id="e5b8a-177">CVE Detection logic</span></span>

<span data-ttu-id="e5b8a-178">소프트웨어 증거와 마찬가지로, 이제 디바이스에 적용한 검색 논리를 표시하여 취약하다는 사실도 밝혔습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-178">Similar to the software evidence, we now show the detection logic we applied on a device in order to state that it's vulnerable.</span></span> <span data-ttu-id="e5b8a-179">새 섹션을 "검색 논리"(디바이스 페이지의 검색된 모든 취약성)라고 부르며 검색 논리 및 소스를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="e5b8a-179">The new section is called "Detection Logic" (in any discovered vulnerability in the device page) and shows the detection logic and source.</span></span>

<span data-ttu-id="e5b8a-180">관련 시나리오에서도 "OS 기능" 범주가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-180">The "OS Feature" category is also shown in relevant scenarios.</span></span> <span data-ttu-id="e5b8a-181">CVE는 특정 OS 구성 요소를 사용하는 경우 취약한 OS를 실행하는 장치에만 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-181">A CVE would affect devices that run a vulnerable OS only if a specific OS component is enabled.</span></span> <span data-ttu-id="e5b8a-182">Windows Server 2019의 DNS 구성 요소에 취약점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-182">Let's say Windows Server 2019 has vulnerability in its DNS component.</span></span> <span data-ttu-id="e5b8a-183">이 새로운 기능을 사용하여 OS에서 사용하도록 설정된 DNS 기능을 사용하여 이 CVE를 Windows Server 2019 장치에만 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-183">With this new capability, we’ll only attach this CVE to the Windows Server 2019 devices with the DNS capability enabled in their OS.</span></span>

![검색 논리 장치 및 KB에서 검색된 소프트웨어를 나열하는 예제입니다.](images/tvm-cve-detection-logic.png)

## <a name="report-inaccuracy"></a><span data-ttu-id="e5b8a-185">부정확성 보고</span><span class="sxs-lookup"><span data-stu-id="e5b8a-185">Report inaccuracy</span></span>

<span data-ttu-id="e5b8a-186">모호하거나 부정확하거나 불완전한 정보가 표시될 경우 가짓 긍정을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-186">Report a false positive when you see any vague, inaccurate, or incomplete information.</span></span> <span data-ttu-id="e5b8a-187">또한 이미 수정된 보안 권장 사항에 대한 보고를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-187">You can also report on security recommendations that have already been remediated.</span></span>

1. <span data-ttu-id="e5b8a-188">취약점 페이지에서 CVE를 여십시오.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-188">Open the CVE on the Weaknesses page.</span></span>
2. <span data-ttu-id="e5b8a-189">**부정확성** 보고를 선택하면 플라이아웃 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-189">Select **Report inaccuracy** and a flyout pane will open.</span></span>
3. <span data-ttu-id="e5b8a-190">드롭다운 메뉴에서 부정확성 범주를 선택하고 전자 메일 주소와 부정확한 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-190">Select the inaccuracy category from the drop-down menu and fill in your email address and inaccuracy details.</span></span>
4. <span data-ttu-id="e5b8a-191">**전송** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-191">Select **Submit**.</span></span> <span data-ttu-id="e5b8a-192">피드백은 위협 및 취약성 관리 전문가에게 즉시 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b8a-192">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e5b8a-193">관련 문서</span><span class="sxs-lookup"><span data-stu-id="e5b8a-193">Related articles</span></span>

- [<span data-ttu-id="e5b8a-194">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="e5b8a-194">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="e5b8a-195">보안 권장 사항</span><span class="sxs-lookup"><span data-stu-id="e5b8a-195">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="e5b8a-196">소프트웨어 인벤토리</span><span class="sxs-lookup"><span data-stu-id="e5b8a-196">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="e5b8a-197">대시보드 인사이트</span><span class="sxs-lookup"><span data-stu-id="e5b8a-197">Dashboard insights</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="e5b8a-198">끝점 장치용 Microsoft Defender 목록 보기 및 구성</span><span class="sxs-lookup"><span data-stu-id="e5b8a-198">View and organize the Microsoft Defender for Endpoint Devices list</span></span>](machines-view-overview.md)
