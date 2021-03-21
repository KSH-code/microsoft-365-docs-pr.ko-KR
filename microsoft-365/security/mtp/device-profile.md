---
title: Microsoft 365 보안 포털의 장치 프로필
description: 조직에서 장치에 대한 위험 및 노출 수준을 확인합니다. 과거 및 현재 위협을 분석하고 최신 업데이트로 장치를 보호합니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, Microsoft Threat Protection, MTP, 보안 센터, Microsoft Defender ATP, Office 365 ATP, Azure ATP, 장치 페이지, 장치 프로필, 컴퓨터 페이지, 컴퓨터 프로필
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 3c540066a7425c5688ce246ceec1793de87549f5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928907"
---
# <a name="device-profile-page"></a><span data-ttu-id="5ae2c-105">디바이스 프로필 페이지</span><span class="sxs-lookup"><span data-stu-id="5ae2c-105">Device profile page</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5ae2c-106">Microsoft 365 보안 포털은 장치 프로필 페이지를 제공 하여 네트워크에서 디바이스의 상태를 빠르게 평가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ae2c-107">디바이스 프로필 페이지는 장치가 Endpoint용 Microsoft Defender, ID용 Microsoft Defender 또는 둘 다에 등록된지 여부에 따라 약간 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender for Endpoint, Microsoft Defender for Identity, or both.</span></span>

<span data-ttu-id="5ae2c-108">장치가 끝점용 Microsoft Defender에 등록된 경우 장치 프로필 페이지를 사용하여 몇 가지 일반적인 보안 작업을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-108">If the device is enrolled in Microsoft Defender for Endpoint, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="5ae2c-109">장치 프로필 페이지 이동</span><span class="sxs-lookup"><span data-stu-id="5ae2c-109">Navigating the device profile page</span></span>

<span data-ttu-id="5ae2c-110">프로필 페이지는 여러 광범위한 섹션으로 나됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-110">The profile page is broken up into several broad sections.</span></span>

![(1) 탭 영역 (2) 사이드바 및 (3) 작업이 빨간색으로 강조 표시된 장치 프로필 페이지의 이미지](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="5ae2c-112">사이드바(1)에는 장치에 대한 기본 세부 정보가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="5ae2c-113">기본 콘텐츠 영역(2)에는 디바이스에 대한 다양한 종류의 정보를 보기 위해 전환할 수 있는 탭이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="5ae2c-114">장치가 끝점용 Microsoft Defender에 등록된 경우 응답 작업 목록(3)도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-114">If the device is enrolled in Microsoft Defender for Endpoint, you will also see a list of response actions (3).</span></span> <span data-ttu-id="5ae2c-115">응답 작업을 사용하면 일반적인 보안 관련 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="5ae2c-116">사이드바</span><span class="sxs-lookup"><span data-stu-id="5ae2c-116">Sidebar</span></span>

<span data-ttu-id="5ae2c-117">디바이스 프로필 페이지의 기본 콘텐츠 영역 옆에 사이드바가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![장치 프로필에 대한 사이드바 탭 이미지](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="5ae2c-119">사이드바에는 장치의 전체 이름 및 노출 수준이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="5ae2c-120">또한 다음과 같이 열리거나 닫을 수 있는 소규모 하위Ection에서 몇 가지 중요한 기본 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="5ae2c-121">**태그** - 끝점용 Microsoft Defender, ID용 Microsoft Defender 또는 장치와 연결된 사용자 지정 태그.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-121">**Tags** - Any Microsoft Defender for Endpoint, Microsoft Defender for Identity, or custom tags associated with the device.</span></span> <span data-ttu-id="5ae2c-122">Microsoft Defender for Identity의 태그는 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-122">Tags from Microsoft Defender for Identity are not editable.</span></span>
* <span data-ttu-id="5ae2c-123">**보안 정보** - 인시던트 및 활성 경고 열기.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="5ae2c-124">끝점용 Microsoft Defender에 등록된 디바이스에는 노출 수준 및 위험 수준도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-124">Devices enrolled in Microsoft Defender for Endpoint will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="5ae2c-125">노출 수준은 장치가 보안 권장 사항을 준수하는 정도와 관련이 있으며 위험 수준은 활성 경고의 유형 및 심각도 등 다양한 요인에 따라 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="5ae2c-126">**장치 세부 정보** - 장치를 처음 본 시기에 대한 도메인, OS, 타임스탬프, IP 주소, 리소스.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="5ae2c-127">끝점용 Microsoft Defender에 등록된 장치도 상태 표시</span><span class="sxs-lookup"><span data-stu-id="5ae2c-127">Devices enrolled in Microsoft Defender for Endpoint also display health state.</span></span> <span data-ttu-id="5ae2c-128">Id용 Microsoft Defender에 등록된 장치에는 장치를 처음 만든 시기에 대한 SAM 이름과 타임스탬프가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-128">Devices enrolled in Microsoft Defender for Identity will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="5ae2c-129">**네트워크 활동** - 디바이스를 처음 및 마지막으로 네트워크에 본 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="5ae2c-130">**디렉터리** 데이터(ID용 *Microsoft Defender에* 등록된 장치만 해당) - [UAC](/windows/security/identity-protection/user-account-control/user-account-control-overview) 플래그, [SPNs](/windows/win32/ad/service-principal-names)및 그룹 구성원 자격.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-130">**Directory data** (*only for devices enrolled in Microsoft Defender for Identity*) - [UAC](/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="5ae2c-131">응답 작업</span><span class="sxs-lookup"><span data-stu-id="5ae2c-131">Response actions</span></span>

<span data-ttu-id="5ae2c-132">대응 조치는 위협을 신속하게 방어하고 분석하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![장치 프로필에 대한 작업 표시줄의 이미지](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="5ae2c-134">[응답 작업은](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) 장치가 끝점용 Microsoft Defender에 등록된 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-134">[Response actions](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender for Endpoint.</span></span>
> * <span data-ttu-id="5ae2c-135">끝점용 Microsoft Defender에 등록된 디바이스는 장치의 OS 및 버전 번호에 따라 다른 수의 응답 작업을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-135">Devices that are enrolled in Microsoft Defender for Endpoint may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="5ae2c-136">장치 프로필 페이지에서 사용할 수 있는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="5ae2c-137">**태그 관리** - 이 장치에 적용한 사용자 지정 태그를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="5ae2c-138">**장치 격리** - 디바이스를 끝점용 Microsoft Defender에 계속 연결하면서 조직의 네트워크에서 격리합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="5ae2c-139">디바이스가 격리된 동안 통신을 위해 Outlook, Teams 및 비즈니스용 Skype가 실행될 수 있도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="5ae2c-140">**작업 센터** - 제출된 작업의 상태를 시청합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="5ae2c-141">다른 작업이 이미 선택된 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="5ae2c-142">**앱 실행 제한** - Microsoft에서 서명하지 않은 응용 프로그램을 실행하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="5ae2c-143">**바이러스 백신 검사** 실행 - 바이러스 Windows Defender 업데이트하고 즉시 바이러스 백신 검색을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="5ae2c-144">빠른 검사 또는 전체 검사 중 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="5ae2c-145">**조사 패키지 수집** - 장치에 대한 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="5ae2c-146">조사가 완료되면 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="5ae2c-147">**라이브 응답** 세션 시작 - 심층 보안 조사를 위해 디바이스에 원격 [셸을 로드합니다.](/windows/security/threat-protection/microsoft-defender-atp/live-response)</span><span class="sxs-lookup"><span data-stu-id="5ae2c-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="5ae2c-148">**자동화된 조사 시작** - 위협을 자동으로 [조사하고 수정합니다.](../office-365-security/office-365-air.md)</span><span class="sxs-lookup"><span data-stu-id="5ae2c-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](../office-365-security/office-365-air.md).</span></span> <span data-ttu-id="5ae2c-149">이 페이지에서 자동화된 조사를 수동으로 트리거할 수 있지만 [특정](../../compliance/alert-policies.md?view=o365-worldwide#default-alert-policies) 경고 정책은 자체적인 자동 조사를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](../../compliance/alert-policies.md?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="5ae2c-150">**작업 센터** - 현재 실행 중인 모든 응답 작업에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="5ae2c-151">Tabs 섹션</span><span class="sxs-lookup"><span data-stu-id="5ae2c-151">Tabs section</span></span>

<span data-ttu-id="5ae2c-152">장치 프로필 탭을 사용하면 장치에 대한 보안 세부 정보 개요와 경고 목록이 포함된 테이블을 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="5ae2c-153">끝점용 Microsoft Defender에 등록된 장치에는 타임라인, 보안 권장 사항 목록, 소프트웨어 인벤토리, 검색된 취약성 목록 및 누락된 KB(보안 업데이트)가 있는 탭도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-153">Devices enrolled in Microsoft Defender for Endpoint will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="5ae2c-154">개요 탭</span><span class="sxs-lookup"><span data-stu-id="5ae2c-154">Overview tab</span></span>

<span data-ttu-id="5ae2c-155">기본 탭은 **개요입니다.**</span><span class="sxs-lookup"><span data-stu-id="5ae2c-155">The default tab is **Overview**.</span></span> <span data-ttu-id="5ae2c-156">디바이스에 대한 가장 중요한 보안 팩트에 대한 빠른 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-156">It provides a quick look at the most important security fact about the device.</span></span>

![장치 프로필에 대한 개요 탭 이미지](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="5ae2c-158">여기서 장치의 활성 경고 및 현재 로그온한 모든 사용자를 빠르게 살펴 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="5ae2c-159">장치가 끝점용 Microsoft Defender에 등록된 경우 장치의 위험 수준과 보안 평가에 대한 사용 가능한 데이터도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-159">If the device is enrolled in Microsoft Defender for Endpoint, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="5ae2c-160">보안 평가는 장치의 노출 수준을 설명하고, 보안 권장 사항을 제공하고, 영향을 받는 소프트웨어 및 발견된 취약점을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="5ae2c-161">경고 탭</span><span class="sxs-lookup"><span data-stu-id="5ae2c-161">Alerts tab</span></span>

<span data-ttu-id="5ae2c-162">경고 **탭에는** Id용 Microsoft Defender와 끝점용 Microsoft Defender 모두에서 장치에서 발생된 경고 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span>

![장치 프로필에 대한 경고 탭 이미지](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="5ae2c-164">표시되는 항목 수와 각 항목에 대해 표시되는 열을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="5ae2c-165">기본 동작은 페이지당 30개 항목을 나열하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="5ae2c-166">이 탭의 열에는 경고를 트리거한 위협의 심각도, 상태, 조사 상태 및 경고가 할당된 사용자에 대한 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="5ae2c-167">영향을 *받는* 엔터티 열은 현재 보고 있는 프로필의 장치(엔터티)와 영향을 받는 네트워크의 다른 장치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="5ae2c-168">이 목록에서 항목을 선택하면 선택한 경고에 대한 추가 정보가 포함된 플라이아웃이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="5ae2c-169">이 목록은 심각도, 상태 또는 경고가 할당된 사용자에 따라 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="5ae2c-170">시간 표시 막대 탭</span><span class="sxs-lookup"><span data-stu-id="5ae2c-170">Timeline tab</span></span>

<span data-ttu-id="5ae2c-171">시간 **표시 막대** 탭에는 디바이스에서 발생된 모든 이벤트의 대화형 시간 표시 막대형 차트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="5ae2c-172">차트의 강조된 영역을 왼쪽 또는 오른쪽으로 이동하면 다양한 기간의 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="5ae2c-173">대화형 차트와 이벤트 목록 사이에 있는 드롭다운 메뉴에서 날짜의 사용자 지정 범위를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="5ae2c-174">차트 아래에는 선택한 날짜 범위에 대한 이벤트 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-174">Below the chart is a list of events for the selected range of dates.</span></span>

![장치 프로필의 타임라인 탭 이미지](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="5ae2c-176">표시되는 항목 수와 목록의 열을 모두 사용자 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="5ae2c-177">기본 열에는 이벤트 시간, 활성 사용자, 작업 유형, 엔터티(프로세스) 및 이벤트에 대한 추가 정보가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="5ae2c-178">이 목록에서 항목을 선택하면 이벤트에 관련된 상위 및 자식 프로세스가 표시하는 이벤트 엔터티 그래프를 표시하는 플라이아웃이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="5ae2c-179">목록을 특정 종류의 이벤트로 필터링할 수 있습니다. 예를 들어 레지스트리 이벤트 또는 Smart Screen 이벤트와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="5ae2c-180">목록을 다운로드하기 위해 CSV 파일로 내보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="5ae2c-181">파일이 이벤트 수로 제한되지는는 하지만 내보낼 수 있는 최대 시간 범위는 7일입니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="5ae2c-182">보안 권장 사항 탭</span><span class="sxs-lookup"><span data-stu-id="5ae2c-182">Security recommendations tab</span></span>

<span data-ttu-id="5ae2c-183">보안 **권장 사항** 탭에는 장치를 보호하기 위해 수행할 수 있는 작업이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="5ae2c-184">이 목록에서 항목을 선택하면 추천을 적용하는 방법에 대한 지침을 얻을 수 있는 플라이아웃이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![장치 프로필에 대한 보안 권장 탭 이미지](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="5ae2c-186">이전 탭과 동일하게 페이지당 표시되는 항목 수와 표시되는 열을 사용자 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="5ae2c-187">기본 보기에는 해결된 보안 약점, 관련된 위협, 위협의 영향을 받는 관련 구성 요소 또는 소프트웨어 등 자세한 열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="5ae2c-188">추천의 상태에 따라 항목을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="5ae2c-189">소프트웨어 인벤토리</span><span class="sxs-lookup"><span data-stu-id="5ae2c-189">Software inventory</span></span>

<span data-ttu-id="5ae2c-190">소프트웨어 **인벤토리** 탭에는 장치에 설치된 소프트웨어가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-190">The **Software inventory** tab lists software installed on the device.</span></span>

![장치 프로필에 대한 소프트웨어 인벤토리 탭의 이미지](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="5ae2c-192">기본 보기에는 소프트웨어 공급업체, 설치된 버전 번호, 알려진 소프트웨어 약점 수, 위협 정보, 제품 코드 및 태그가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="5ae2c-193">표시되는 항목 수와 표시되는 열을 모두 사용자 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="5ae2c-194">이 목록에서 항목을 선택하면 선택한 소프트웨어에 대한 자세한 내용과 마지막으로 소프트웨어를 찾은 시간의 경로 및 타임스탬프가 포함된 플라이아웃이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="5ae2c-195">이 목록은 제품 코드로 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="5ae2c-196">발견된 취약성 탭</span><span class="sxs-lookup"><span data-stu-id="5ae2c-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="5ae2c-197">검색된 **취약성** 탭에는 장치에 영향을 줄 수 있는 일반 취약성 및 CV(Exploits)가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![장치 프로필에 대해 검색된 취약성 탭의 이미지](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="5ae2c-199">기본 보기에는 CVE의 심각도, CVS(Common Vulnerability Score), CVE 관련 소프트웨어, CVE가 게시된 때, CVE가 마지막으로 업데이트된 때 및 CVE와 관련된 위협이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="5ae2c-200">이전 탭과 동일하게 표시되는 항목 수와 표시되는 열을 사용자 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="5ae2c-201">이 목록에서 항목을 선택하면 CVE를 설명하는 플라이아웃이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="5ae2c-202">KB 누락</span><span class="sxs-lookup"><span data-stu-id="5ae2c-202">Missing KBs</span></span>

<span data-ttu-id="5ae2c-203">누락된 **KB 탭에는** 장치에 아직 적용되지 않은 모든 Microsoft 업데이트가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="5ae2c-204">해당 "KB"는 이러한 업데이트를 [설명하는 기술](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) 자료 문서입니다. 예를 들어 [KB4551762와 같습니다.](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762)</span><span class="sxs-lookup"><span data-stu-id="5ae2c-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![장치 프로필에 대한 kbs 탭이 누락된 이미지](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="5ae2c-206">기본 보기에는 업데이트, OS 버전, 영향을 받는 제품, 주소가 지정되는 CV, KB 번호 및 태그가 포함된 공지가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="5ae2c-207">페이지당 표시되는 항목 수와 표시할 열을 사용자 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="5ae2c-208">항목을 선택하면 업데이트에 연결되는 플라이아웃이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2c-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5ae2c-209">관련 주제</span><span class="sxs-lookup"><span data-stu-id="5ae2c-209">Related topics</span></span>

* [<span data-ttu-id="5ae2c-210">Microsoft 365 Defender 개요</span><span class="sxs-lookup"><span data-stu-id="5ae2c-210">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="5ae2c-211">Microsoft 365 Defender 켜기</span><span class="sxs-lookup"><span data-stu-id="5ae2c-211">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
* [<span data-ttu-id="5ae2c-212">라이브 응답을 사용하여 디바이스에서 엔터티 조사</span><span class="sxs-lookup"><span data-stu-id="5ae2c-212">Investigate entities on devices, using live response</span></span>](/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="5ae2c-213">Office 365의 자동화된 조사 및 대응(AIR)</span><span class="sxs-lookup"><span data-stu-id="5ae2c-213">Automated investigation and response (AIR) in Office 365</span></span>](../office-365-security/office-365-air.md)