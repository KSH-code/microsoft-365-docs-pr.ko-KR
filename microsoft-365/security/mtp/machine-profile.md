---
title: Microsoft 365 보안 포털의 컴퓨터 프로필
description: 조직의 장치에 대 한 위험 및 노출 수준을 확인 합니다. 이전의 및 현재 위협을 분석 하 고 최신 업데이트로 컴퓨터를 보호 합니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, Microsoft 위협 보호, MTP, 보안 센터, Microsoft Defender ATP, Office 365 ATP, Azure ATP, 컴퓨터 페이지, 컴퓨터 목록, 컴퓨터 프로필
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 7ab3f63008c65fca1a99128cc6f11f83bc86b2b4
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857697"
---
# <a name="machine-profile-page"></a><span data-ttu-id="8cd08-105">컴퓨터 프로필 페이지</span><span class="sxs-lookup"><span data-stu-id="8cd08-105">Machine profile page</span></span>

<span data-ttu-id="8cd08-106">Microsoft 365 보안 포털은 컴퓨터 프로필 페이지를 제공 하므로 네트워크에서 장치의 상태를 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-106">The Microsoft 365 security portal provides you with Machine profile pages, so you can assess the health and status of devices on your network.</span></span> <span data-ttu-id="8cd08-107">각 컴퓨터 프로필 페이지에는 장치에 대 한 다양 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-107">Each Machine profile page contains a wealth of information about the device.</span></span>

<span data-ttu-id="8cd08-108">실행 중인 소프트웨어에 대 한 자세한 정보를 검토 하 고, 이전의 보안 이벤트 또는 경고를 제공 하 고, 관련 소프트웨어 패치에 대 한 링크를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-108">You can review in-depth information about what software it is running, any past and present security events or alerts, and find links to relevant software patches.</span></span>

<span data-ttu-id="8cd08-109">컴퓨터 프로필을 사용 하 여 일반적인 보안 관련 작업을 수행 하 고 장치에 대 한 기본 세부 정보를 신속 하 게 검토할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-109">You can also use the Machine profile to perform common security-related tasks, and quickly review basic details about the device.</span></span>

## <a name="navigating-the-machine-profile-page"></a><span data-ttu-id="8cd08-110">컴퓨터 프로필 페이지 탐색</span><span class="sxs-lookup"><span data-stu-id="8cd08-110">Navigating the Machine profile page</span></span>

<span data-ttu-id="8cd08-111">컴퓨터 프로필 페이지는 컴퓨터 목록에서 장치 이름을 직접 선택 하거나 컴퓨터 목록 플라이 아웃에서 **컴퓨터 열기 페이지** 를 선택 하 여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-111">The Machine profile page can be accessed by directly selecting a device name on the Machines list or by choosing **Open Machine page** on the Machines list flyout.</span></span>

<span data-ttu-id="8cd08-112">페이지를 연 후에는 세 섹션으로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-112">Once you have the page open, you'll find that it is broken up into three sections.</span></span>

![컴퓨터 프로필 페이지 이미지 (1) 탭 영역 (2) 보조 메뉴가 있고 (3) 작업이 빨간색으로 강조 표시 됨](../../media/mtp-machine-profile/mtp-machine-profile-all.png)

<span data-ttu-id="8cd08-114">기본 콘텐츠 영역 (1)에는 컴퓨터에 대 한 다양 한 종류의 정보를 보기 위해 전환할 수 있는 7 개의 탭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-114">The main content area (1) contains seven tabs that you can toggle through to view different kinds of information about the machine.</span></span>

<span data-ttu-id="8cd08-115">사이드바 (2)에는 컴퓨터에 대 한 기본 세부 정보가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-115">The sidebar (2) lists basic details about the machine.</span></span>

<span data-ttu-id="8cd08-116">또한 사이드바 및 주 콘텐츠 섹션 앞에 머리글 (3)을 사용 하 여 사용할 수 있는 응답 작업도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-116">There are also response actions available in a header (3) before the sidebar and main content sections.</span></span> <span data-ttu-id="8cd08-117">이 헤더의 작업을 사용 하 여 일반적인 보안 관련 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-117">You can use the actions in this header to perform common security-related tasks.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="8cd08-118">Tabs 섹션</span><span class="sxs-lookup"><span data-stu-id="8cd08-118">Tabs section</span></span>

<span data-ttu-id="8cd08-119">컴퓨터 프로필 탭을 사용 하 여 컴퓨터에 대 한 보안 세부 정보의 개요를 확인 하거나, 알림 목록, 일정, 보안 권장 사항 목록, 소프트웨어 인벤토리, 발견 된 취약점 목록 및 누락 된 정보를 포함 하는 테이블을 전환할 수 있습니다. Kb (보안 업데이트).</span><span class="sxs-lookup"><span data-stu-id="8cd08-119">The Machine profile tabs allow you to toggle through an overview of security details about the machine, and tables containing a list of alerts, a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="8cd08-120">개요 탭</span><span class="sxs-lookup"><span data-stu-id="8cd08-120">Overview tab</span></span>

<span data-ttu-id="8cd08-121">기본 탭은 **개요**입니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-121">The default tab is **Overview**.</span></span> <span data-ttu-id="8cd08-122">이를 통해 장치에 대 한 가장 중요 한 보안 팩트를 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-122">It provides a quick look at the most important security fact about the device.</span></span>

![컴퓨터 프로필에 대 한 개요 탭 이미지](../../media/mtp-machine-profile/overview.png)

<span data-ttu-id="8cd08-124">여기서는 장치의 위험 수준, 활성 알림, 현재 로그온 한 사용자, 가장 및 최소 사용자의 간략 한 목록, 그리고 장치에 대 한 노출 수준, 보안 권장 사항, 영향을 받는 소프트웨어를 자세히 설명 하는 보안 평가에 대 한 차트를 확인할 수 있습니다. 발견 된 취약점</span><span class="sxs-lookup"><span data-stu-id="8cd08-124">Here, you can find a chart of the device's risk level and active alerts, any currently logged on users, a brief list of most and least frequent users, and security assessments that detail the device's exposure level, security recommendations, affected software, and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="8cd08-125">알림 탭</span><span class="sxs-lookup"><span data-stu-id="8cd08-125">Alerts tab</span></span>

<span data-ttu-id="8cd08-126">**알림** 탭에는 장치에 보고 된 경고 목록이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-126">The **Alerts** tab contains a list of alerts that have been reported on the device.</span></span>

![컴퓨터 프로필에 대 한 알림 탭 이미지](../../media/mtp-machine-profile/alerts.png)

<span data-ttu-id="8cd08-128">표시 되는 항목 수와 각 항목에 표시 되는 열을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-128">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="8cd08-129">기본 동작은 페이지당 30 개의 항목을 나열 하 고 11 개의 열을 설정 하 여 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-129">The default behavior is to list 30 items per page, and have 11 columns toggled on to display.</span></span>

<span data-ttu-id="8cd08-130">이 탭의 열에는 경고를 트리거한 위협의 심각도에 대 한 정보 및 상태, 조사 상태, 그리고 경고가 할당 된 모든 사람에 대 한 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-130">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who if anyone the alert has been assigned to.</span></span>

<span data-ttu-id="8cd08-131">영향을 받는 *엔터티* 열은 현재 보고 있는 프로필의 컴퓨터 (엔터티)와 네트워크에 있는 다른 모든 컴퓨터를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-131">The *impacted entities* column refers to the machine (entity) whose profile you are currently viewing, plus any other machines in your network that are affected.</span></span>

<span data-ttu-id="8cd08-132">이 목록에서 항목을 선택 하면 선택한 경고에 대 한 링크가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-132">Selecting an item from this list will open a link to the selected alert.</span></span>

<span data-ttu-id="8cd08-133">이 목록은 심각도, 상태 또는 담당자를 기준으로 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-133">This list can be filtered by severity, status, or assignee.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="8cd08-134">시간 표시 막대 탭</span><span class="sxs-lookup"><span data-stu-id="8cd08-134">Timeline tab</span></span>

<span data-ttu-id="8cd08-135">**시간 표시 막대** 탭에는 장치에서 발생 한 이벤트에 대 한 대화형 시간 차트가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-135">The **Timeline** tab includes a interactive, chronological chart of events raised on the device.</span></span> <span data-ttu-id="8cd08-136">차트의 강조 표시 된 영역을 이동 하 여 다양 한 시간대 별 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-136">By moving the highlighted area of the chart, you can view events over different ranges of time.</span></span> <span data-ttu-id="8cd08-137">사용자 지정 날짜 범위를 입력할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-137">You can also type in a custom range of dates.</span></span>

<span data-ttu-id="8cd08-138">차트 아래에는 선택한 날짜 범위에 대 한 이벤트 목록이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-138">Below the chart is a list of events for the selected range of dates.</span></span>

![컴퓨터 프로필에 대 한 시간 표시 막대 탭 이미지](../../media/mtp-machine-profile/timeline.png)

<span data-ttu-id="8cd08-140">표시 되는 항목 수와 목록에 있는 열을 모두 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-140">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="8cd08-141">기본 열에는 이벤트 시간, 활성 사용자, 작업 유형, 엔터티 (프로세스) 및 이벤트에 대 한 추가 정보가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-141">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="8cd08-142">목록에서 항목을 선택 하면 이벤트 엔터티 그래프가 표시 된 플라이 아웃이 열리며이 프로세스를 트리거한 부모 및 자식 프로세스가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-142">Selecting an item from the list will open a flyout displaying an Event entities graph, showing the parent and child processes that triggered the event.</span></span>

<span data-ttu-id="8cd08-143">이 목록은 특정 유형의 이벤트로 필터링 될 수 있습니다. 예를 들면 레지스트리 이벤트 또는 스마트 스크린 이벤트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-143">This list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="8cd08-144">보안 권장 사항 탭</span><span class="sxs-lookup"><span data-stu-id="8cd08-144">Security recommendations tab</span></span>

<span data-ttu-id="8cd08-145">**보안 권장 사항** 탭에는 장치를 보호 하기 위해 수행할 수 있는 작업이 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-145">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="8cd08-146">이 목록에서 항목을 선택 하면 권장 사항을 적용 하는 방법에 대 한 지침을 얻을 수 있는 플라이 아웃이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-146">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![컴퓨터 프로필에 대 한 보안 권장 사항 탭 이미지](../../media/mtp-machine-profile/security-recs.png)

<span data-ttu-id="8cd08-148">이전 탭과 마찬가지로, 페이지당 표시 되는 항목 수와 표시 되는 열은 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-148">As with the previous tabs, the number of items displayed per page and which columns are visible can be customized.</span></span>

<span data-ttu-id="8cd08-149">기본 보기에는 보안 약점, 관련 위협, 위협에 영향을 받는 구성 요소 또는 소프트웨어를 자세히 설명 하는 열이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-149">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="8cd08-150">추천 상태를 기준으로 항목을 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-150">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="8cd08-151">소프트웨어 인벤토리</span><span class="sxs-lookup"><span data-stu-id="8cd08-151">Software inventory</span></span>

<span data-ttu-id="8cd08-152">**소프트웨어 인벤토리** 탭에는 장치에 설치 된 소프트웨어가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-152">The **Software inventory** tab lists software installed on the device.</span></span>

![컴퓨터 프로필에 대 한 소프트웨어 인벤토리 탭 이미지](../../media/mtp-machine-profile/software-inventory.png)

<span data-ttu-id="8cd08-154">기본 보기에는 소프트웨어 공급 업체, 설치 된 버전 번호, 알려진 소프트웨어 약점 수, 위협 정보, 제품 코드 및 태그가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-154">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="8cd08-155">표시 되는 항목 수와 표시 되는 열이 모두 사용자 지정 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-155">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="8cd08-156">이 목록에서 항목을 선택 하면 선택한 소프트웨어에 대 한 세부 정보를 포함 하는 플라이 아웃이 열리고, 소프트웨어를 마지막으로 찾은 시간에 대 한 경로 및 타임 스탬프가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-156">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="8cd08-157">이 목록은 제품 코드를 기준으로 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-157">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="8cd08-158">검색 된 취약성 탭</span><span class="sxs-lookup"><span data-stu-id="8cd08-158">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="8cd08-159">**검색 된 취약성** 탭에는 장치에 영향을 줄 수 있는 모든 일반 취약성 및 악용 (cves)이 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-159">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![컴퓨터 프로필에 대 한 검색 된 취약성 탭의 이미지](../../media/mtp-machine-profile/discovered-vulnerabilities.png)

<span data-ttu-id="8cd08-161">기본 보기에는 CVE, 일반적인 취약성 점수 (CVS), cve와 관련 된 소프트웨어, cve가 마지막으로 업데이트 된 날짜, CVE와 관련 된 위협 등이 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-161">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="8cd08-162">이전 탭과 마찬가지로 표시 되는 항목의 수와 표시할 수 있는 열이 사용자 지정 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-162">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="8cd08-163">이 목록에서 항목을 선택 하면 CVE를 설명 하는 플라이 아웃이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-163">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="8cd08-164">누락 된 Kb</span><span class="sxs-lookup"><span data-stu-id="8cd08-164">Missing KBs</span></span>

<span data-ttu-id="8cd08-165">**누락 된 kb** 탭에는 컴퓨터에 아직 적용 되지 않은 Microsoft 업데이트 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-165">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the machine.</span></span> <span data-ttu-id="8cd08-166">"Kb"는 이러한 업데이트를 설명 하는 [기술 자료 문서](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) 입니다. 예: [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="8cd08-166">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![컴퓨터 프로필에 대 한 누락 된 kb 탭 이미지](../../media/mtp-machine-profile/missing-kbs.PNG)

<span data-ttu-id="8cd08-168">기본 보기에는 업데이트, OS 버전, 영향을 받는 제품, CVEs 주소, 수 및 태그가 포함 된 게시판이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-168">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="8cd08-169">페이지당 표시 되는 항목 수와 표시 되는 열을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-169">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="8cd08-170">항목을 선택 하면 업데이트에 연결 되는 플라이 아웃이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-170">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="sidebar"></a><span data-ttu-id="8cd08-171">기사의</span><span class="sxs-lookup"><span data-stu-id="8cd08-171">Sidebar</span></span>

<span data-ttu-id="8cd08-172">컴퓨터 프로필 페이지의 기본 콘텐츠 영역 옆에는 사이드바가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-172">Beside the main content area of the Machine profile page is the sidebar.</span></span>

![컴퓨터 프로필에 대 한 사이드바 탭 이미지](../../media/mtp-machine-profile/sidebar.png)

<span data-ttu-id="8cd08-174">사이드바에서는 열리거나 닫힐 수 있는 작은 하위 섹션의 몇 가지 중요 한 기본 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-174">The sidebar provides some important basic information in small subsections which can be toggled open or closed:</span></span>

* <span data-ttu-id="8cd08-175">**Tags** -장치에 연결 된 모든 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-175">**Tags** - Any tags associated with the device</span></span>
* <span data-ttu-id="8cd08-176">**보안 정보** -열린 인시던트, 활성 경고, 노출 수준 및 위험 수준</span><span class="sxs-lookup"><span data-stu-id="8cd08-176">**Security info** - Open incidents, active alerts, exposure level and risk level</span></span>
* <span data-ttu-id="8cd08-177">**장치 정보** -도메인, OS, 자산 그룹, 상태, 데이터 민감도 및 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8cd08-177">**Device details** - Domain, OS, Asset group, health state, data sensitivity, and IP addresses</span></span>
* <span data-ttu-id="8cd08-178">**네트워크 활동** -네트워크에서 장치를 마지막으로 본 시간에 대 한 타임 스탬프</span><span class="sxs-lookup"><span data-stu-id="8cd08-178">**Network activity** - Timestamps for the first time and last time the device was seen on the network</span></span>

<span data-ttu-id="8cd08-179">또한이 섹션에는 장치의 이름 및 노출 수준 및 네트워크에서 현재 활성 상태인 경우를 나타내는 아이콘이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-179">This section also includes the name and exposure level of the device, and an icon to indicate if it is currently active on the network.</span></span>

## <a name="response-actions"></a><span data-ttu-id="8cd08-180">응답 작업</span><span class="sxs-lookup"><span data-stu-id="8cd08-180">Response actions</span></span>

<span data-ttu-id="8cd08-181">응답 동작은 위협을 보호 하 고 분석 하는 빠른 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-181">Response actions offer a quick way to defend against and analyze threats.</span></span>

![컴퓨터 프로필에 대 한 사이드바 탭 이미지](../../media/mtp-machine-profile/actions.PNG)

<span data-ttu-id="8cd08-183">여기에 제공 되는 응답 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-183">The response actions available to you here include:</span></span>

* <span data-ttu-id="8cd08-184">**Manage tags** -이 장치에 적용 한 사용자 지정 태그를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-184">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="8cd08-185">**컴퓨터 격리** -Microsoft Defender Advanced Threat Protection에 연결 된 상태로 컴퓨터를 조직의 네트워크에서 격리 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-185">**Isolate machine** - Isolates the machine from your organization's network while keeping it connected to Microsoft Defender Advanced Threat Protection.</span></span> <span data-ttu-id="8cd08-186">통신 목적으로, 컴퓨터가 격리 된 상태에서 Outlook, 팀 및 비즈니스용 Skype가 실행 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-186">You can choose to allow Outlook, Teams, and Skype for Business to run while the machine is isolated, for communication purposes.</span></span>
* <span data-ttu-id="8cd08-187">**앱 실행 제한** -Microsoft에서 서명 하지 않은 응용 프로그램이 실행 되지 않음</span><span class="sxs-lookup"><span data-stu-id="8cd08-187">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running</span></span>
* <span data-ttu-id="8cd08-188">**바이러스** 검사 프로그램 실행-Windows Defender 바이러스 백신 정의를 업데이트 하 고 바이러스 백신 검사를 즉시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-188">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="8cd08-189">빠른 검색 또는 전체 검사 중에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-189">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="8cd08-190">**Collect 조사 패키지** -컴퓨터에 대 한 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-190">**Collect investigation package** - Gathers information about the machine.</span></span> <span data-ttu-id="8cd08-191">조사가 완료 되 면이를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-191">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="8cd08-192">**Initiate Live Response session** - [심층 보안 조사](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)를 위해 컴퓨터에서 원격 셸을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-192">**Initiate Live Response session** - Loads a remote shell on the machine for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="8cd08-193">**자동화 된 조사 시작** - [위협 자동 조사 및 remediates](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)</span><span class="sxs-lookup"><span data-stu-id="8cd08-193">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="8cd08-194">자동 조사를 수동으로 트리거하여이 페이지에서 실행할 수는 있지만 [특정 경고 정책이](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) 자동 조사를 자체적으로 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-194">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="8cd08-195">**동작 센터** -전송 된 작업의 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-195">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="8cd08-196">이미 다른 작업을 선택한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cd08-196">Only available if another action has already been selected.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8cd08-197">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8cd08-197">Related topics</span></span>

* [<span data-ttu-id="8cd08-198">Microsoft 위협 방지 개요</span><span class="sxs-lookup"><span data-stu-id="8cd08-198">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="8cd08-199">Microsoft 위협 방지 설정</span><span class="sxs-lookup"><span data-stu-id="8cd08-199">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
* [<span data-ttu-id="8cd08-200">라이브 응답을 사용 하 여 컴퓨터의 엔터티 조사</span><span class="sxs-lookup"><span data-stu-id="8cd08-200">Investigate entities on machines using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="8cd08-201">Office 365의 자동화 된 조사 및 응답 (AIR)</span><span class="sxs-lookup"><span data-stu-id="8cd08-201">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
