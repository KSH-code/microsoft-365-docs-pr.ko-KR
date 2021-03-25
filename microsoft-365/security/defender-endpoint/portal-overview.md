---
title: 끝점용 Microsoft Defender 포털 개요
description: Microsoft Defender 보안 센터는 엔터프라이즈 네트워크를 모니터링하고 잠재적인 APT(고급 영구 위협) 또는 데이터 위반에 대응할 수 있습니다.
keywords: Microsoft Defender 보안 센터, 포털, 사이버 보안 위협 인텔리전스, 대시보드, 경고 큐, 장치 목록, 설정, 장치 관리, 고급 공격
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aa7f2df1f0164f24c7f4698e8aa0b699f4884c09
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186224"
---
# <a name="microsoft-defender-security-center-portal-overview"></a><span data-ttu-id="e0df8-104">Microsoft Defender 보안 센터 포털 개요</span><span class="sxs-lookup"><span data-stu-id="e0df8-104">Microsoft Defender Security Center portal overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e0df8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e0df8-105">**Applies to:**</span></span>
- [<span data-ttu-id="e0df8-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e0df8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e0df8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0df8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="e0df8-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="e0df8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e0df8-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink) 

<span data-ttu-id="e0df8-110">엔터프라이즈 보안 팀은 Microsoft Defender 보안 센터를 사용하여 잠재적인 고급 영구 위협 활동 또는 데이터 위반 경고에 대한 대응을 모니터링하고 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-110">Enterprise security teams can use Microsoft Defender Security Center to monitor and assist in responding to alerts of potential advanced persistent threat activity or data breaches.</span></span>

<span data-ttu-id="e0df8-111">[Microsoft Defender 보안 센터를 사용하여 다음을 할 수](https://securitycenter.windows.com/) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-111">You can use [Microsoft Defender Security Center](https://securitycenter.windows.com/) to:</span></span>

- <span data-ttu-id="e0df8-112">끝점에서 경고 보기, 정렬 및 분류</span><span class="sxs-lookup"><span data-stu-id="e0df8-112">View, sort, and triage alerts from your endpoints</span></span>
- <span data-ttu-id="e0df8-113">파일 및 IP 주소와 같은 관찰된 지표에 대한 자세한 정보 검색</span><span class="sxs-lookup"><span data-stu-id="e0df8-113">Search for more information on observed indicators such as files and IP Addresses</span></span>
- <span data-ttu-id="e0df8-114">표준 시간대를 포함하여 끝점 설정에 대한 Microsoft Defender 변경 및 라이선스 정보 검토</span><span class="sxs-lookup"><span data-stu-id="e0df8-114">Change Microsoft Defender for Endpoint settings, including time zone and review licensing information</span></span>

## <a name="microsoft-defender-security-center"></a><span data-ttu-id="e0df8-115">Microsoft Defender 보안 센터</span><span class="sxs-lookup"><span data-stu-id="e0df8-115">Microsoft Defender Security Center</span></span>

<span data-ttu-id="e0df8-116">포털을 열면 다음이 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-116">When you open the portal, you'll see:</span></span>

- <span data-ttu-id="e0df8-117">(1) 탐색 창(탐색 창 위쪽의 가로줄을 선택하여 표시하거나 숨기기)</span><span class="sxs-lookup"><span data-stu-id="e0df8-117">(1) Navigation pane (select the horizontal lines at the top of the navigation pane to show or hide it)</span></span>
- <span data-ttu-id="e0df8-118">(2) 검색, 커뮤니티 센터, 지역화, 도움말 및 지원, 피드백</span><span class="sxs-lookup"><span data-stu-id="e0df8-118">(2) Search, Community center, Localization, Help and support, Feedback</span></span>

 ![끝점 포털용 Microsoft Defender](images/mdatp-portal-overview.png)

> [!NOTE]
> <span data-ttu-id="e0df8-120">맬웨어 관련 검색은 장치가 Microsoft Defender 바이러스 백신을 실시간 보호 기본 맬웨어 방지 제품으로 사용하는 경우만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-120">Malware related detections will only appear if your devices are using Microsoft Defender Antivirus as the default real-time protection antimalware product.</span></span>

<span data-ttu-id="e0df8-121">모든 섹션에서 사용할 수 있는 메뉴 옵션을 사용하여 포털을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-121">You can navigate through the portal using the menu options available in all sections.</span></span> <span data-ttu-id="e0df8-122">각 섹션에 대한 설명은 다음 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0df8-122">Refer to the following table for a description of each section.</span></span>

<span data-ttu-id="e0df8-123">영역</span><span class="sxs-lookup"><span data-stu-id="e0df8-123">Area</span></span> | <span data-ttu-id="e0df8-124">설명</span><span class="sxs-lookup"><span data-stu-id="e0df8-124">Description</span></span>
:---|:---
<span data-ttu-id="e0df8-125">**(1) 탐색 창**</span><span class="sxs-lookup"><span data-stu-id="e0df8-125">**(1) Navigation pane**</span></span> | <span data-ttu-id="e0df8-126">탐색 창을 사용하여 대시보드, 인시던트, 장치 **목록,** 경고 **큐,** **자동화된** 조사, 고급     **헌팅,** **보고서,** 파트너 & **API,** 위협 & **취약성** 관리, 평가 및 **자습서,** 서비스 **상태,** 구성 관리 및 설정 사이를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-126">Use the navigation pane to move between **Dashboards**, **Incidents**, **Devices list**, **Alerts queue**, **Automated investigations**, **Advanced hunting**, **Reports**, **Partners & APIs**, **Threat & Vulnerability Management**, **Evaluation and tutorials**, **Service health**, **Configuration management**, and **Settings**.</span></span> <span data-ttu-id="e0df8-127">탐색 창 위쪽의 가로줄을 선택하여 표시하거나 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-127">Select the horizontal lines at the top of the navigation pane to show or hide it.</span></span>
<span data-ttu-id="e0df8-128">**대시보드**</span><span class="sxs-lookup"><span data-stu-id="e0df8-128">**Dashboards**</span></span> | <span data-ttu-id="e0df8-129">활성 자동화된 조사, 활성 경고, 자동화된 조사 통계, 위험 상태의 장치, 위험 상태의 사용자, 센서 문제가 있는 장치, 서비스 상태, 검색 원본 및 대시보드를 보고하는 일일 장치에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-129">Access the active automated investigations, active alerts, automated investigations statistics, devices at risk, users at risk, devices with sensor issues, service health, detection sources, and daily devices reporting dashboards.</span></span>
<span data-ttu-id="e0df8-130">**인시던트**</span><span class="sxs-lookup"><span data-stu-id="e0df8-130">**Incidents**</span></span> | <span data-ttu-id="e0df8-131">인시던트로 집계된 경고를 시청합니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-131">View alerts that have been aggregated as incidents.</span></span>
<span data-ttu-id="e0df8-132">**장치 목록**</span><span class="sxs-lookup"><span data-stu-id="e0df8-132">**Devices list**</span></span> | <span data-ttu-id="e0df8-133">Endpoint용 Defender에 온보딩된 장치 목록, 장치에 대한 일부 정보 및 노출 및 위험 수준을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-133">Displays the list of devices that are onboarded to Defender for Endpoint, some information about them, and their exposure and risk levels.</span></span>
<span data-ttu-id="e0df8-134">**경고 큐**</span><span class="sxs-lookup"><span data-stu-id="e0df8-134">**Alerts queue**</span></span> | <span data-ttu-id="e0df8-135">조직의 장치에서 생성된 경고를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-135">View alerts generated from devices in your organizations.</span></span>
<span data-ttu-id="e0df8-136">**자동화된 조사**</span><span class="sxs-lookup"><span data-stu-id="e0df8-136">**Automated investigations**</span></span> | <span data-ttu-id="e0df8-137">네트워크에서 수행된 자동화된 조사를 표시하여 경고, 각 조사의 상태 및 기타 세부 정보(예: 조사 시작 시간 및 조사 기간)를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-137">Displays automated investigations that have been conducted in the network, triggering alert, the status of each investigation and other details such as when the investigation started and the duration of the investigation.</span></span>
<span data-ttu-id="e0df8-138">**고급 헌팅**</span><span class="sxs-lookup"><span data-stu-id="e0df8-138">**Advanced hunting**</span></span> | <span data-ttu-id="e0df8-139">고급 헌팅을 사용하면 강력한 검색 및 쿼리 도구를 사용하여 조직 전체를 사전 예방적으로 헌팅하고 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-139">Advanced hunting allows you to proactively hunt and investigate across your organization using a powerful search and query tool.</span></span>
<span data-ttu-id="e0df8-140">**보고서**</span><span class="sxs-lookup"><span data-stu-id="e0df8-140">**Reports**</span></span> | <span data-ttu-id="e0df8-141">위협 방지, 장치 상태 및 규정 준수, 웹 보호 및 취약성을 자세히 설명하는 그래프를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-141">View graphs detailing threat protection, device health and compliance, web protection, and vulnerability.</span></span>
<span data-ttu-id="e0df8-142">**파트너 & API**</span><span class="sxs-lookup"><span data-stu-id="e0df8-142">**Partners & APIs**</span></span> | <span data-ttu-id="e0df8-143">플랫폼의 검색, 조사 및 위협 인텔리전스 기능을 향상시키는 지원되는 파트너 연결을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-143">View supported partner connections, which enhance the detection, investigation, and threat intelligence capabilities of the platform.</span></span> <span data-ttu-id="e0df8-144">연결된 응용 프로그램, API 탐색기, API 사용 개요 및 데이터 내보내기 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-144">You can also view connected applications, the API explorer, API usage overview, and data export settings.</span></span>
<span data-ttu-id="e0df8-145">**위협 & 취약성 관리**</span><span class="sxs-lookup"><span data-stu-id="e0df8-145">**Threat & Vulnerability management**</span></span> | <span data-ttu-id="e0df8-146">장치에 대한 Microsoft 보안 점수, 노출 점수, 노출된 장치, 취약한 소프트웨어를 보고 주요 보안 권장 사항에 대해 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-146">View your Microsoft Secure Score for Devices, exposure score, exposed devices, vulnerable software, and take action on top security recommendations.</span></span>
<span data-ttu-id="e0df8-147">**평가 및 자습서**</span><span class="sxs-lookup"><span data-stu-id="e0df8-147">**Evaluation and tutorials**</span></span> | <span data-ttu-id="e0df8-148">테스트 장치, 공격 시뮬레이션 및 보고서를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-148">Manage test devices, attack simulations, and reports.</span></span> <span data-ttu-id="e0df8-149">평가판 환경에서 안내된 안내를 통해 끝점용 Defender 기능을 알아보고 경험하세요.</span><span class="sxs-lookup"><span data-stu-id="e0df8-149">Learn and experience the Defender for Endpoint capabilities through a guided walk-through in a trial environment.</span></span>
<span data-ttu-id="e0df8-150">**서비스 상태**</span><span class="sxs-lookup"><span data-stu-id="e0df8-150">**Service health**</span></span> | <span data-ttu-id="e0df8-151">Endpoint용 Defender 서비스의 현재 상태에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-151">Provides information on the current status of the Defender for Endpoint service.</span></span> <span data-ttu-id="e0df8-152">서비스 상태 또는 현재 문제가 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-152">You'll be able to verify that the service health is healthy or if there are current issues.</span></span>
<span data-ttu-id="e0df8-153">**구성 관리**</span><span class="sxs-lookup"><span data-stu-id="e0df8-153">**Configuration management**</span></span> | <span data-ttu-id="e0df8-154">보드된 장치, 조직의 보안 기준, 예측 분석, 웹 보호 범위를 표시하며 장치에서 공격 표면 관리를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-154">Displays on-boarded devices, your organizations' security baseline, predictive analysis, web protection coverage, and allows you to perform attack surface management on your devices.</span></span>
<span data-ttu-id="e0df8-155">**설정**</span><span class="sxs-lookup"><span data-stu-id="e0df8-155">**Settings**</span></span> | <span data-ttu-id="e0df8-156">온보드 중에 선택한 설정을 표시하고 산업 기본 설정 및 보존 정책 기간을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-156">Shows the settings you selected during onboarding and lets you update your industry preferences and retention policy period.</span></span> <span data-ttu-id="e0df8-157">사용 권한, API, 규칙, 장치 관리, IT 서비스 관리 및 네트워크 평가와 같은 다른 구성 설정을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-157">You can also set other configuration settings such as permissions, APIs, rules, device management, IT service management, and network assessments.</span></span>
<span data-ttu-id="e0df8-158">**(2) 검색, 커뮤니티 센터, 지역화, 도움말 및 지원, 피드백**</span><span class="sxs-lookup"><span data-stu-id="e0df8-158">**(2) Search, Community center, Localization,  Help and support, Feedback**</span></span> | <span data-ttu-id="e0df8-159">**검색** - 장치, 파일, 사용자, URL, IP, 취약성, 소프트웨어 및 권장을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-159">**Search** - search by device, file, user, URL, IP, vulnerability, software, and recommendation.</span></span> </br></br> <span data-ttu-id="e0df8-160">**커뮤니티 센터** - 커뮤니티 센터에 액세스하여 제품에 대한 정보를 알아보고, 공동 작업하고, 경험을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-160">**Community center** - Access the Community center to learn, collaborate, and share experiences about the product.</span></span> </br></br>  <span data-ttu-id="e0df8-161">**지역화** - 표준 시간대를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-161">**Localization** - Set time zones.</span></span> </br></br>  <span data-ttu-id="e0df8-162">**도움말 및** 지원 - 끝점용 Defender 가이드, Microsoft 및 Microsoft 프리미어 지원, 라이선스 정보, 시뮬레이션& 자습서, Endpoint용 Defender 평가 랩, 위협 전문가에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="e0df8-162">**Help and support** - Access the Defender for Endpoint guide, Microsoft and Microsoft Premier support, license information, simulations & tutorials, Defender for Endpoint evaluation lab, consult a threat expert.</span></span></br></br> <span data-ttu-id="e0df8-163">**피드백** - 사용자가 좋아하는 것 또는 더 나은 작업을 위한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-163">**Feedback** - Provide comments about what you like or what we can do better.</span></span>

> [!NOTE]
> <span data-ttu-id="e0df8-164">고해상도 DPI 배율 문제가 있는 장치의 경우 가능한 해결 방법을 확인한 후 고 [DPI](https://support.microsoft.com/help/3025083/windows-scaling-issues-for-high-dpi-devices) 장치에 대한 Windows 크기 조정 문제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0df8-164">For devices with high resolution DPI scaling issues, please see [Windows scaling issues for high-DPI devices](https://support.microsoft.com/help/3025083/windows-scaling-issues-for-high-dpi-devices) for possible solutions.</span></span>

## <a name="microsoft-defender-for-endpoint-icons"></a><span data-ttu-id="e0df8-165">끝점용 Microsoft Defender 아이콘</span><span class="sxs-lookup"><span data-stu-id="e0df8-165">Microsoft Defender for Endpoint icons</span></span>

<span data-ttu-id="e0df8-166">다음 표에서는 포털 전체에서 사용되는 아이콘에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-166">The following table provides information on the icons used all throughout the portal:</span></span>

<span data-ttu-id="e0df8-167">아이콘</span><span class="sxs-lookup"><span data-stu-id="e0df8-167">Icon</span></span> | <span data-ttu-id="e0df8-168">설명</span><span class="sxs-lookup"><span data-stu-id="e0df8-168">Description</span></span>
:---|:---
![ATP 로고 아이콘](images/atp-logo-icon.png)| <span data-ttu-id="e0df8-170">끝점용 Microsoft Defender 로고</span><span class="sxs-lookup"><span data-stu-id="e0df8-170">Microsoft Defender for Endpoint logo</span></span>
![경고 아이콘](images/alert-icon.png)| <span data-ttu-id="e0df8-172">경고 – 고급 공격과 상호 관련이 있는 활동 표시</span><span class="sxs-lookup"><span data-stu-id="e0df8-172">Alert – Indication of an activity correlated with advanced attacks.</span></span>
![검색 아이콘](images/detection-icon.png)| <span data-ttu-id="e0df8-174">검색 - 맬웨어 위협 감지 표시</span><span class="sxs-lookup"><span data-stu-id="e0df8-174">Detection – Indication of a malware threat detection.</span></span>
![활성 위협 아이콘](images/active-threat-icon.png)| <span data-ttu-id="e0df8-176">활성 위협 - 감지 시 적극적으로 실행되는 위협.</span><span class="sxs-lookup"><span data-stu-id="e0df8-176">Active threat – Threats actively executing at the time of detection.</span></span>
![수정된 아이콘1](images/remediated-icon.png)| <span data-ttu-id="e0df8-178">수정됨 - 장치에서 위협이 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-178">Remediated – Threat removed from the device.</span></span>
![수정되지 않은 아이콘](images/not-remediated-icon.png)| <span data-ttu-id="e0df8-180">수정되지 않습니다. 장치에서 위협이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0df8-180">Not remediated – Threat not removed from the device.</span></span>
![Thunderbolt 아이콘](images/atp-thunderbolt-icon.png)| <span data-ttu-id="e0df8-182">경고 프로세스 트리에서 경고를 트리거한 **이벤트를 나타냅니다.**</span><span class="sxs-lookup"><span data-stu-id="e0df8-182">Indicates events that triggered an alert in the **Alert process tree**.</span></span>
![장치 아이콘](images/atp-machine-icon.png)| <span data-ttu-id="e0df8-184">장치 아이콘</span><span class="sxs-lookup"><span data-stu-id="e0df8-184">Device icon</span></span>
![Microsoft Defender AV 이벤트 아이콘](images/atp-windows-defender-av-events-icon.png)| <span data-ttu-id="e0df8-186">Microsoft Defender 바이러스 백신 이벤트</span><span class="sxs-lookup"><span data-stu-id="e0df8-186">Microsoft Defender Antivirus events</span></span>
![Application Guard 이벤트 아이콘](images/atp-Application-Guard-events-icon.png)| <span data-ttu-id="e0df8-188">Windows Defender Application Guard 이벤트</span><span class="sxs-lookup"><span data-stu-id="e0df8-188">Windows Defender Application Guard events</span></span>
![Device Guard 이벤트 아이콘](images/atp-Device-Guard-events-icon.png)| <span data-ttu-id="e0df8-190">Windows Defender Device Guard 이벤트</span><span class="sxs-lookup"><span data-stu-id="e0df8-190">Windows Defender Device Guard events</span></span>
![Exploit Guard 이벤트 아이콘](images/atp-Exploit-Guard-events-icon.png)| <span data-ttu-id="e0df8-192">Windows Defender Exploit Guard 이벤트</span><span class="sxs-lookup"><span data-stu-id="e0df8-192">Windows Defender Exploit Guard events</span></span>
![SmartScreen 이벤트 아이콘](images/atp-Smart-Screen-events-icon.png)| <span data-ttu-id="e0df8-194">Windows Defender SmartScreen 이벤트</span><span class="sxs-lookup"><span data-stu-id="e0df8-194">Windows Defender SmartScreen events</span></span>
![방화벽 이벤트 아이콘](images/atp-Firewall-events-icon.png)| <span data-ttu-id="e0df8-196">Windows 방화벽 이벤트</span><span class="sxs-lookup"><span data-stu-id="e0df8-196">Windows Firewall events</span></span>
![응답 작업 아이콘](images/atp-respond-action-icon.png)| <span data-ttu-id="e0df8-198">응답 작업</span><span class="sxs-lookup"><span data-stu-id="e0df8-198">Response action</span></span>
![프로세스 이벤트 아이콘](images/atp-process-event-icon.png)| <span data-ttu-id="e0df8-200">이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="e0df8-200">Process events</span></span>
![네트워크 통신 이벤트 아이콘](images/atp-network-communications-icon.png)| <span data-ttu-id="e0df8-202">네트워크 이벤트</span><span class="sxs-lookup"><span data-stu-id="e0df8-202">Network events</span></span>
![파일 관찰 이벤트 아이콘](images/atp-file-observed-icon.png)| <span data-ttu-id="e0df8-204">파일 이벤트</span><span class="sxs-lookup"><span data-stu-id="e0df8-204">File  events</span></span>
![레지스트리 이벤트 아이콘](images/atp-registry-event-icon.png)| <span data-ttu-id="e0df8-206">레지스트리 이벤트</span><span class="sxs-lookup"><span data-stu-id="e0df8-206">Registry events</span></span>
![모듈 로드 DLL 이벤트 아이콘](images/atp-module-load-icon.png)| <span data-ttu-id="e0df8-208">DLL 이벤트 로드</span><span class="sxs-lookup"><span data-stu-id="e0df8-208">Load DLL events</span></span>
![기타 이벤트 아이콘](images/atp-Other-events-icon.png)| <span data-ttu-id="e0df8-210">기타 이벤트</span><span class="sxs-lookup"><span data-stu-id="e0df8-210">Other events</span></span>
![액세스 토큰 수정 아이콘](images/atp-access-token-modification-icon.png)| <span data-ttu-id="e0df8-212">액세스 토큰 수정</span><span class="sxs-lookup"><span data-stu-id="e0df8-212">Access token modification</span></span>
![파일 만들기 아이콘](images/atp-file-creation-icon.png)| <span data-ttu-id="e0df8-214">파일 만들기</span><span class="sxs-lookup"><span data-stu-id="e0df8-214">File creation</span></span>
![서명자 아이콘](images/atp-signer-icon.png)| <span data-ttu-id="e0df8-216">서명자</span><span class="sxs-lookup"><span data-stu-id="e0df8-216">Signer</span></span>
![파일 경로 아이콘](images/atp-File-path-icon.png)| <span data-ttu-id="e0df8-218">파일 경로</span><span class="sxs-lookup"><span data-stu-id="e0df8-218">File path</span></span>
![명령줄 아이콘](images/atp-command-line-icon.png)| <span data-ttu-id="e0df8-220">명령줄</span><span class="sxs-lookup"><span data-stu-id="e0df8-220">Command line</span></span>
![부호 없는 파일 아이콘](images/atp-unsigned-file-icon.png)| <span data-ttu-id="e0df8-222">부호 없는 파일</span><span class="sxs-lookup"><span data-stu-id="e0df8-222">Unsigned file</span></span>
![프로세스 트리 아이콘](images/atp-process-tree.png)| <span data-ttu-id="e0df8-224">프로세스 트리</span><span class="sxs-lookup"><span data-stu-id="e0df8-224">Process tree</span></span>
![메모리 할당 아이콘](images/atp-memory-allocation-icon.png)| <span data-ttu-id="e0df8-226">메모리 할당</span><span class="sxs-lookup"><span data-stu-id="e0df8-226">Memory allocation</span></span>
![프로세스 삽입 아이콘](images/atp-process-injection.png)| <span data-ttu-id="e0df8-228">프로세스 삽입</span><span class="sxs-lookup"><span data-stu-id="e0df8-228">Process injection</span></span>
![Powershell 명령 실행 아이콘](images/atp-powershell-command-run-icon.png)| <span data-ttu-id="e0df8-230">Powershell 명령 실행</span><span class="sxs-lookup"><span data-stu-id="e0df8-230">Powershell command run</span></span>
![커뮤니티 센터 아이콘](images/atp-community-center.png) | <span data-ttu-id="e0df8-232">커뮤니티 센터</span><span class="sxs-lookup"><span data-stu-id="e0df8-232">Community center</span></span>
![알림 아이콘](images/atp-notifications.png) | <span data-ttu-id="e0df8-234">알림</span><span class="sxs-lookup"><span data-stu-id="e0df8-234">Notifications</span></span>
![위협을 찾을 수 없음](images/no-threats-found.png) | <span data-ttu-id="e0df8-236">자동화된 조사 - 위협이 발견 없음</span><span class="sxs-lookup"><span data-stu-id="e0df8-236">Automated investigation - no threats found</span></span>
![실패한 아이콘](images/failed.png) | <span data-ttu-id="e0df8-238">자동화된 조사 - 실패</span><span class="sxs-lookup"><span data-stu-id="e0df8-238">Automated investigation - failed</span></span>
![부분적으로 수정된 아이콘](images/partially-investigated.png) | <span data-ttu-id="e0df8-240">자동화된 조사 - 부분적으로 조사</span><span class="sxs-lookup"><span data-stu-id="e0df8-240">Automated investigation - partially investigated</span></span>
![시스템에 의해 종료됩니다.](images/terminated-by-system.png) | <span data-ttu-id="e0df8-242">자동화된 조사 - 시스템에서 종료</span><span class="sxs-lookup"><span data-stu-id="e0df8-242">Automated investigation - terminated by system</span></span>
![보류 중인 아이콘](images/pending.png) | <span data-ttu-id="e0df8-244">자동화된 조사 - 보류 중</span><span class="sxs-lookup"><span data-stu-id="e0df8-244">Automated investigation - pending</span></span>
![실행 중인 아이콘](images/running.png) | <span data-ttu-id="e0df8-246">자동화된 조사 - 실행</span><span class="sxs-lookup"><span data-stu-id="e0df8-246">Automated investigation - running</span></span>
![수정된 아이콘2](images/remediated.png) | <span data-ttu-id="e0df8-248">자동화된 조사 - 수정</span><span class="sxs-lookup"><span data-stu-id="e0df8-248">Automated investigation - remediated</span></span>
![부분적으로 조사된 아이콘](images/partially_remediated.png) | <span data-ttu-id="e0df8-250">자동화된 조사 - 부분적으로 수정</span><span class="sxs-lookup"><span data-stu-id="e0df8-250">Automated investigation - partially remediated</span></span>
![위협 정보 아이콘](images/tvm_bug_icon.png) | <span data-ttu-id="e0df8-252">위협 & 취약성 관리 - 위협 정보</span><span class="sxs-lookup"><span data-stu-id="e0df8-252">Threat & Vulnerability Management - threat insights</span></span>
![가능한 활성 경고 아이콘](images/tvm_alert_icon.png) | <span data-ttu-id="e0df8-254">위협 & 취약성 관리 - 가능한 활성 경고</span><span class="sxs-lookup"><span data-stu-id="e0df8-254">Threat & Vulnerability Management - possible active alert</span></span>
![추천 인사이트 아이콘](images/tvm_insight_icon.png) | <span data-ttu-id="e0df8-256">위협 & 취약성 관리 - 권장 정보</span><span class="sxs-lookup"><span data-stu-id="e0df8-256">Threat & Vulnerability Management - recommendation insights</span></span>

## <a name="related-topics"></a><span data-ttu-id="e0df8-257">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e0df8-257">Related topics</span></span>

- [<span data-ttu-id="e0df8-258">Microsoft Defender 보안 센터 개요</span><span class="sxs-lookup"><span data-stu-id="e0df8-258">Overview of Microsoft Defender Security Center</span></span>](use.md)
- [<span data-ttu-id="e0df8-259">보안 작업 대시보드 보기</span><span class="sxs-lookup"><span data-stu-id="e0df8-259">View the Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="e0df8-260">위협 요소 & 관리 대시보드 보기</span><span class="sxs-lookup"><span data-stu-id="e0df8-260">View the Threat & Vulnerability Management dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="e0df8-261">위협 분석 대시보드 보기 및 권장 완화 작업 수행</span><span class="sxs-lookup"><span data-stu-id="e0df8-261">View the Threat analytics dashboard and take recommended mitigation actions</span></span>](threat-analytics.md)
