---
title: Endpoint 장치용 Defender 목록에서 장치 조사
description: 경고, 네트워크 연결 정보를 검토하고, 장치 태그 및 그룹을 추가하고, 서비스 상태 확인을 통해 영향을 받는 장치를 조사합니다.
keywords: 장치, 태그, 그룹, 끝점, 경고 큐, 경고, 장치 이름, 도메인, 마지막으로 본 내부 IP, 활성 경고, 위협 범주, 필터, 정렬, 경고 검토, 네트워크, 연결, 유형, 암호 도용자, 랜섬웨어, 악용, 위협, 낮은 심각도, 서비스 상태
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c1e572910ad311daba18a8b0f5eeb546ffe36956
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51929112"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="8ac6f-104">Microsoft Defender for Endpoint Devices 목록에서 장치 조사</span><span class="sxs-lookup"><span data-stu-id="8ac6f-104">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8ac6f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8ac6f-105">**Applies to:**</span></span>
- [<span data-ttu-id="8ac6f-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8ac6f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8ac6f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8ac6f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8ac6f-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="8ac6f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8ac6f-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="8ac6f-110">특정 장치에서 발생한 경고의 세부 정보를 조사하여 경고 또는 잠재적인 위반 범위와 관련이 있을 수 있는 다른 동작 또는 이벤트를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-110">Investigate the details of an alert raised on a specific device to identify other behaviors or events that might be related to the alert or the potential scope of the breach.</span></span>

> [!NOTE]
> <span data-ttu-id="8ac6f-111">조사 또는 응답 프로세스의 일부로 장치에서 조사 패키지를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-111">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="8ac6f-112">방법: 장치에서 [조사 패키지를 수집합니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices)</span><span class="sxs-lookup"><span data-stu-id="8ac6f-112">Here's how: [Collect investigation package from devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="8ac6f-113">포털에서 영향을 받는 장치를 볼 때마다 해당 장치를 클릭하여 해당 장치에 대한 자세한 보고서를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-113">You can click on affected devices whenever you see them in the portal to open a detailed report about that device.</span></span> <span data-ttu-id="8ac6f-114">영향을 받는 장치는 다음 영역에서 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-114">Affected devices are identified in the following areas:</span></span>

- [<span data-ttu-id="8ac6f-115">장치 목록</span><span class="sxs-lookup"><span data-stu-id="8ac6f-115">Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="8ac6f-116">경고 큐</span><span class="sxs-lookup"><span data-stu-id="8ac6f-116">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="8ac6f-117">보안 운영 대시보드</span><span class="sxs-lookup"><span data-stu-id="8ac6f-117">Security operations dashboard</span></span>](security-operations-dashboard.md)
- <span data-ttu-id="8ac6f-118">개별 경고</span><span class="sxs-lookup"><span data-stu-id="8ac6f-118">Any individual alert</span></span>
- <span data-ttu-id="8ac6f-119">개별 파일 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="8ac6f-119">Any individual file details view</span></span>
- <span data-ttu-id="8ac6f-120">모든 IP 주소 또는 도메인 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="8ac6f-120">Any IP address or domain details view</span></span>

<span data-ttu-id="8ac6f-121">특정 장치를 조사할 때 다음이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-121">When you investigate a specific device, you'll see:</span></span>

- <span data-ttu-id="8ac6f-122">장치 세부 정보</span><span class="sxs-lookup"><span data-stu-id="8ac6f-122">Device details</span></span>
- <span data-ttu-id="8ac6f-123">응답 작업</span><span class="sxs-lookup"><span data-stu-id="8ac6f-123">Response actions</span></span>
- <span data-ttu-id="8ac6f-124">탭(개요, 경고, 타임라인, 보안 권장 사항, 소프트웨어 인벤토리, 발견된 취약성, KB 누락)</span><span class="sxs-lookup"><span data-stu-id="8ac6f-124">Tabs (overview, alerts, timeline, security recommendations, software inventory, discovered vulnerabilities, missing KBs)</span></span>
- <span data-ttu-id="8ac6f-125">카드(활성 경고, 로그온한 사용자, 보안 평가)</span><span class="sxs-lookup"><span data-stu-id="8ac6f-125">Cards (active alerts, logged on users, security assessment)</span></span>

![장치 보기의 이미지](images/specific-device.png)

## <a name="device-details"></a><span data-ttu-id="8ac6f-127">장치 세부 정보</span><span class="sxs-lookup"><span data-stu-id="8ac6f-127">Device details</span></span>

<span data-ttu-id="8ac6f-128">장치 세부 정보 섹션에서는 디바이스의 도메인, OS 및 상태와 같은 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-128">The device details section provides information such as the domain, OS, and health state of the device.</span></span> <span data-ttu-id="8ac6f-129">디바이스에서 사용 가능한 조사 패키지가 있는 경우 패키지를 다운로드할 수 있는 링크가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-129">If there's an investigation package available on the device, you'll see a link that allows you to download the package.</span></span>

## <a name="response-actions"></a><span data-ttu-id="8ac6f-130">응답 작업</span><span class="sxs-lookup"><span data-stu-id="8ac6f-130">Response actions</span></span>

<span data-ttu-id="8ac6f-131">응답 작업은 특정 장치 페이지의 위쪽을 따라 실행하고 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-131">Response actions run along the top of a specific device page and include:</span></span>

- <span data-ttu-id="8ac6f-132">태그 관리</span><span class="sxs-lookup"><span data-stu-id="8ac6f-132">Manage tags</span></span>
- <span data-ttu-id="8ac6f-133">장치 격리</span><span class="sxs-lookup"><span data-stu-id="8ac6f-133">Isolate device</span></span>
- <span data-ttu-id="8ac6f-134">앱 실행 제한</span><span class="sxs-lookup"><span data-stu-id="8ac6f-134">Restrict app execution</span></span>
- <span data-ttu-id="8ac6f-135">바이러스 백신 검사 실행</span><span class="sxs-lookup"><span data-stu-id="8ac6f-135">Run antivirus scan</span></span>
- <span data-ttu-id="8ac6f-136">조사 패키지 수집</span><span class="sxs-lookup"><span data-stu-id="8ac6f-136">Collect investigation package</span></span>
- <span data-ttu-id="8ac6f-137">실시간 응답 세션 시작</span><span class="sxs-lookup"><span data-stu-id="8ac6f-137">Initiate Live Response Session</span></span>
- <span data-ttu-id="8ac6f-138">자동화된 조사 시작</span><span class="sxs-lookup"><span data-stu-id="8ac6f-138">Initiate automated investigation</span></span>
- <span data-ttu-id="8ac6f-139">위협 전문가에게 문의</span><span class="sxs-lookup"><span data-stu-id="8ac6f-139">Consult a threat expert</span></span>
- <span data-ttu-id="8ac6f-140">작업 센터</span><span class="sxs-lookup"><span data-stu-id="8ac6f-140">Action center</span></span>

<span data-ttu-id="8ac6f-141">작업 센터, 특정 장치 페이지 또는 특정 파일 페이지에서 응답 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-141">You can take response actions in the Action center, in a specific device page, or in a specific file page.</span></span>

<span data-ttu-id="8ac6f-142">디바이스에서 조치를 취하는 방법에 대한 자세한 내용은 디바이스에서 응답 [작업 수행을 참조하세요.](respond-machine-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="8ac6f-142">For more information on how to take action on a device, see [Take response action on a device](respond-machine-alerts.md).</span></span>

<span data-ttu-id="8ac6f-143">자세한 내용은 사용자 엔터티 [조사를 참조하세요.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="8ac6f-143">For more information, see [Investigate user entities](investigate-user.md).</span></span>

## <a name="tabs"></a><span data-ttu-id="8ac6f-144">탭</span><span class="sxs-lookup"><span data-stu-id="8ac6f-144">Tabs</span></span>

<span data-ttu-id="8ac6f-145">탭은 장치와 관련된 관련 보안 및 위협 방지 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-145">The tabs provide relevant security and threat prevention information related to the device.</span></span> <span data-ttu-id="8ac6f-146">각 탭에서 열 머리줄 위의 막대에서 열  사용자 지정을 선택하여 표시되는 열을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-146">In each tab, you can customize the columns that are shown by selecting **Customize columns** from the bar above the column headers.</span></span>

### <a name="overview"></a><span data-ttu-id="8ac6f-147">개요</span><span class="sxs-lookup"><span data-stu-id="8ac6f-147">Overview</span></span>
<span data-ttu-id="8ac6f-148">개요 **탭에는** [](#cards) 활성 경고, 로그온한 사용자 및 보안 평가에 대한 카드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-148">The **Overview** tab displays the [cards](#cards) for active alerts, logged on users, and security assessment.</span></span>

![디바이스 페이지의 개요 탭 이미지](images/overview-device.png)

### <a name="alerts"></a><span data-ttu-id="8ac6f-150">경고</span><span class="sxs-lookup"><span data-stu-id="8ac6f-150">Alerts</span></span>

<span data-ttu-id="8ac6f-151">경고 **탭은** 장치와 연결된 경고 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-151">The **Alerts** tab provides a list of alerts that are associated with the device.</span></span> <span data-ttu-id="8ac6f-152">이 목록은 필터링된 경고 [](alerts-queue.md)큐 버전으로, 경고, 심각도(높음, 중간, 낮음, 정보), 큐의 상태(신규, 진행 중, 해결), 분류(설정되지 않은, 거짓 경고, 참 경고), 조사 상태, 경고를 처리 중인 경고 범주 및 마지막 활동에 대한 간단한 설명을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-152">This list is a filtered version of the [Alerts queue](alerts-queue.md), and shows a short description of the alert, severity (high, medium, low, informational), status in the queue (new, in progress, resolved), classification (not set, false alert, true alert), investigation state, category of alert, who is addressing the alert, and last activity.</span></span> <span data-ttu-id="8ac6f-153">경고를 필터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-153">You can also filter the alerts.</span></span>

![장치와 관련된 경고 이미지](images/alerts-device.png)

<span data-ttu-id="8ac6f-155">경고 왼쪽에 있는 원 아이콘을 선택하면 플라이아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-155">When the circle icon to the left of an alert is selected, a fly-out appears.</span></span> <span data-ttu-id="8ac6f-156">이 패널에서 경고를 관리하고 인시던트 번호 및 관련 장치와 같은 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-156">From this panel you can manage the alert and view more details such as incident number and related devices.</span></span> <span data-ttu-id="8ac6f-157">경고는 한 번만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-157">Multiple alerts can be selected at a time.</span></span>

<span data-ttu-id="8ac6f-158">인시던트 그래프 및 프로세스 트리를 포함하여 경고의 전체 페이지 보기를 확인하려면 경고의 제목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-158">To see a full page view of an alert including incident graph and process tree, select the title of the alert.</span></span>

### <a name="timeline"></a><span data-ttu-id="8ac6f-159">시간 표시 막대</span><span class="sxs-lookup"><span data-stu-id="8ac6f-159">Timeline</span></span>

<span data-ttu-id="8ac6f-160">시간 **표시 막대** 탭에서는 장치에서 관찰된 이벤트 및 관련 경고를 시간 표시 막대 보기로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-160">The **Timeline** tab provides a chronological view of the events and associated alerts that have been observed on the device.</span></span> <span data-ttu-id="8ac6f-161">이렇게하면 장치와 관련한 이벤트, 파일 및 IP 주소의 상관 관계를 설정하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-161">This can help you correlate any events, files, and IP addresses in relation to the device.</span></span>

<span data-ttu-id="8ac6f-162">타임라인을 사용하면 특정 기간 내에 발생한 이벤트로 선택적으로 드릴다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-162">The timeline also enables you to selectively drill down into events that occurred within a given time period.</span></span> <span data-ttu-id="8ac6f-163">선택한 기간 동안 디바이스에서 발생한 이벤트의 임시 순서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-163">You can view the temporal sequence of events that occurred on a device over a selected time period.</span></span> <span data-ttu-id="8ac6f-164">보기를 추가로 제어하기 위해 이벤트 그룹을 필터링하거나 열을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-164">To further control your view, you can filter by event groups or customize the columns.</span></span>

>[!NOTE]
> <span data-ttu-id="8ac6f-165">방화벽 이벤트를 표시하려면 감사 정책을 사용하도록 설정해야 합니다. 필터링 플랫폼 연결 [감사를 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-filtering-platform-connection)</span><span class="sxs-lookup"><span data-stu-id="8ac6f-165">For firewall events to be displayed, you'll need to enable the audit policy, see [Audit Filtering Platform connection](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-filtering-platform-connection).</span></span>
><span data-ttu-id="8ac6f-166">방화벽이 다음 이벤트를 다루는 경우</span><span class="sxs-lookup"><span data-stu-id="8ac6f-166">Firewall covers the following events</span></span>
>
>- <span data-ttu-id="8ac6f-167">[5025](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5025) - 방화벽 서비스가 중지됨</span><span class="sxs-lookup"><span data-stu-id="8ac6f-167">[5025](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5025) - firewall service stopped</span></span>
>- <span data-ttu-id="8ac6f-168">[5031](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5031) - 응용 프로그램이 네트워크에서 들어오는 연결을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-168">[5031](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5031) - application blocked from accepting incoming connections on the network</span></span>
>- <span data-ttu-id="8ac6f-169">[5157](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5157) - 차단된 연결</span><span class="sxs-lookup"><span data-stu-id="8ac6f-169">[5157](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5157) - blocked connection</span></span>

![이벤트가 있는 디바이스 타임라인의 이미지](images/timeline-device.png)

<span data-ttu-id="8ac6f-171&quot;>일부 기능은 다음과 같습니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8ac6f-171&quot;>Some of the functionality includes:</span></span>

- <span data-ttu-id=&quot;8ac6f-172&quot;>특정 이벤트 검색</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8ac6f-172&quot;>Search for specific events</span></span>
  - <span data-ttu-id=&quot;8ac6f-173&quot;>검색 표시줄을 사용하여 특정 타임라인 이벤트를 검색합니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8ac6f-173&quot;>Use the search bar to look for specific timeline events.</span></span>
- <span data-ttu-id=&quot;8ac6f-174&quot;>특정 날짜의 이벤트 필터링</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8ac6f-174&quot;>Filter events from a specific date</span></span>
  - <span data-ttu-id=&quot;8ac6f-175&quot;>지난 일, 주, 30일 또는 사용자 지정 범위의 이벤트를 표시하려면 표 왼쪽 상단에서 달력 아이콘을 선택합니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8ac6f-175&quot;>Select the calendar icon in the upper left of the table to display events in the past day, week, 30 days, or custom range.</span></span> <span data-ttu-id=&quot;8ac6f-176&quot;>기본적으로 지난 30일 동안의 이벤트를 표시하기 위해 장치 타임라인이 설정됩니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8ac6f-176&quot;>By default, the device timeline is set to display the events from the past 30 days.</span></span>
  - <span data-ttu-id=&quot;8ac6f-177&quot;>시간 표시 막대를 사용하여 섹션을 강조 표시하여 특정 시간으로 이동합니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8ac6f-177&quot;>Use the timeline to jump to a specific moment in time by highlighting the section.</span></span> <span data-ttu-id=&quot;8ac6f-178&quot;>시간 표시 막대의 화살표는 자동화된 조사를 고정합니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8ac6f-178&quot;>The arrows on the timeline pinpoint automated investigations</span></span>
- <span data-ttu-id=&quot;8ac6f-179&quot;>자세한 장치 타임라인 이벤트 내보내기</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8ac6f-179&quot;>Export detailed device timeline events</span></span>
  - <span data-ttu-id=&quot;8ac6f-180&quot;>현재 날짜 또는 지정된 날짜 범위에 대한 장치 타임라인을 최대 7일까지 내보낼 수 있습니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8ac6f-180&quot;>Export the device timeline for the current date or a specified date range up to seven days.</span></span>

<span data-ttu-id=&quot;8ac6f-181&quot;>특정 이벤트에 대한 자세한 내용은 추가 정보 **섹션에 제공됩니다.**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8ac6f-181&quot;>More details about certain events are provided in the **Additional information** section.</span></span> <span data-ttu-id=&quot;8ac6f-182&quot;>이러한 세부 정보는 이벤트 유형에 따라 다릅니다. 예를 들면 다음과 같습니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8ac6f-182&quot;>These details vary depending on the type of event, for example:</span></span> 

- <span data-ttu-id=&quot;8ac6f-183&quot;>Application Guard에 포함된 - 웹 브라우저 이벤트가 격리된 컨테이너에 의해 제한됨</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8ac6f-183&quot;>Contained by Application Guard - the web browser event was restricted by an isolated container</span></span>
- <span data-ttu-id=&quot;8ac6f-184&quot;>활성 위협 감지 - 위협이 실행되는 동안 위협 감지가 발생했습니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8ac6f-184&quot;>Active threat detected - the threat detection occurred while the threat was running</span></span>
- <span data-ttu-id=&quot;8ac6f-185&quot;>재구성 실패 - 감지된 위협을 수정하려고 시도했지만 실패했습니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8ac6f-185&quot;>Remediation unsuccessful - an attempt to remediate the detected threat was invoked but failed</span></span>
- <span data-ttu-id=&quot;8ac6f-186&quot;>수정 성공 - 감지된 위협이 중지되고 해결됨</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8ac6f-186&quot;>Remediation successful - the detected threat was stopped and cleaned</span></span>
- <span data-ttu-id=&quot;8ac6f-187&quot;>사용자가 무시한 경고 - Windows Defender SmartScreen 경고가 무시 및 무시됩니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8ac6f-187&quot;>Warning bypassed by user - the Windows Defender SmartScreen warning was dismissed and overridden by a user</span></span>
- <span data-ttu-id=&quot;8ac6f-188&quot;>의심스러운 스크립트가 검색되었습니다. 실행 중인 악성 스크립트가 발견되었습니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8ac6f-188&quot;>Suspicious script detected - a potentially malicious script was found running</span></span>
- <span data-ttu-id=&quot;8ac6f-189&quot;>경고 범주 - 이벤트가 경고 생성을 주도한 경우 경고 범주(예: &quot;측면 이동")가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-189">The alert category - if the event led to the generation of an alert, the alert category  ("Lateral Movement", for example) is provided</span></span>

#### <a name="event-details"></a><span data-ttu-id="8ac6f-190">이벤트 세부 정보</span><span class="sxs-lookup"><span data-stu-id="8ac6f-190">Event details</span></span>
<span data-ttu-id="8ac6f-191">이벤트를 선택하여 해당 이벤트에 대한 관련 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-191">Select an event to view relevant details about that event.</span></span> <span data-ttu-id="8ac6f-192">일반 이벤트 정보를 표시하는 패널이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-192">A panel displays to show general event information.</span></span> <span data-ttu-id="8ac6f-193">해당되는 데이터와 데이터를 사용할 수 있는 경우 관련 엔터티 및 해당 관계가 표시된 그래프도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-193">When applicable and data is available, a graph showing related entities and their relationships are also shown.</span></span>

<span data-ttu-id="8ac6f-194">이벤트 및 관련 이벤트를 추가로 검사하려면 관련 [](advanced-hunting-overview.md) 이벤트에 대한 헌트 를 선택하여 고급 헌팅 **쿼리를 빠르게 실행할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="8ac6f-194">To further inspect the event and related events, you can quickly run an [advanced hunting](advanced-hunting-overview.md) query by selecting **Hunt for related events**.</span></span> <span data-ttu-id="8ac6f-195">쿼리는 선택한 이벤트와 같은 끝점에서 동시에 발생한 다른 이벤트 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-195">The query will return the selected event and the list of other events that occurred around the same time on the same endpoint.</span></span>

![이벤트 세부 정보 패널의 이미지](images/event-details.png)

### <a name="security-recommendations"></a><span data-ttu-id="8ac6f-197">보안 권장 사항</span><span class="sxs-lookup"><span data-stu-id="8ac6f-197">Security recommendations</span></span>

<span data-ttu-id="8ac6f-198">**보안 권장** 사항은 Endpoint의 위협 및 [취약성 & Microsoft Defender에서](tvm-dashboard-insights.md) 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-198">**Security recommendations** are generated from Microsoft Defender for Endpoint's [Threat & Vulnerability Management](tvm-dashboard-insights.md) capability.</span></span> <span data-ttu-id="8ac6f-199">권장 사항을 선택하면 권장 사항 설명 및 권장 사항의 제정되지 않은 잠재적 위험과 같은 관련 세부 정보를 볼 수 있는 패널이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-199">Selecting a recommendation will show a panel where you can view relevant details such as description of the recommendation and the potential risks associated with not enacting it.</span></span> <span data-ttu-id="8ac6f-200">자세한 [내용은 보안](tvm-security-recommendation.md) 권장 사항을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-200">See [Security recommendation](tvm-security-recommendation.md) for details.</span></span>

![보안 권장 사항 탭의 이미지](images/security-recommendations-device.png)

### <a name="software-inventory"></a><span data-ttu-id="8ac6f-202">소프트웨어 인벤토리</span><span class="sxs-lookup"><span data-stu-id="8ac6f-202">Software inventory</span></span>

<span data-ttu-id="8ac6f-203">소프트웨어 **인벤토리** 탭을 사용하면 장치에서 약점이나 위협과 함께 소프트웨어를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-203">The **Software inventory** tab lets you view software on the device, along with any weaknesses or threats.</span></span> <span data-ttu-id="8ac6f-204">소프트웨어 이름을 선택하면 보안 권장 사항, 발견된 취약성, 설치된 장치 및 버전 배포를 볼 수 있는 소프트웨어 세부 정보 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-204">Selecting the name of the software will take you to the software details page where you can view security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span> <span data-ttu-id="8ac6f-205">자세한 [내용은 소프트웨어](tvm-software-inventory.md) 인벤토리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-205">See [Software inventory](tvm-software-inventory.md) for details</span></span>

![소프트웨어 인벤토리 탭의 이미지](images/software-inventory-device.png)

### <a name="discovered-vulnerabilities"></a><span data-ttu-id="8ac6f-207">발견된 취약성</span><span class="sxs-lookup"><span data-stu-id="8ac6f-207">Discovered vulnerabilities</span></span>

<span data-ttu-id="8ac6f-208">검색된 **취약성** 탭에는 장치에서 검색된 취약성의 이름, 심각도 및 위협 인사이트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-208">The **Discovered vulnerabilities** tab shows the name, severity, and threat insights of discovered vulnerabilities on the device.</span></span> <span data-ttu-id="8ac6f-209">특정 취약점을 선택하면 설명과 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-209">Selecting specific vulnerabilities will show a description and details.</span></span>

![검색된 취약성 탭의 이미지](images/discovered-vulnerabilities-device.png)

### <a name="missing-kbs"></a><span data-ttu-id="8ac6f-211">KB 누락</span><span class="sxs-lookup"><span data-stu-id="8ac6f-211">Missing KBs</span></span>
<span data-ttu-id="8ac6f-212">누락된 **KB 탭에는** 장치에 대한 누락된 보안 업데이트가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-212">The **Missing KBs** tab lists the missing security updates for the device.</span></span>

![누락된 kbs 탭의 이미지](images/missing-kbs-device.png)

## <a name="cards"></a><span data-ttu-id="8ac6f-214">카드</span><span class="sxs-lookup"><span data-stu-id="8ac6f-214">Cards</span></span>

### <a name="active-alerts"></a><span data-ttu-id="8ac6f-215">활성 경고</span><span class="sxs-lookup"><span data-stu-id="8ac6f-215">Active alerts</span></span>

<span data-ttu-id="8ac6f-216">**Azure Advanced Threat Protection** 카드는 ID에 대한 Microsoft Defender 기능을 활성화한 경우 활성 경고가 있는 경우 장치 및 해당 위험 수준과 관련된 경고에 대한 간략한 개요를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-216">The **Azure Advanced Threat Protection** card will display a high-level overview of alerts related to the device and their risk level, if you have enabled the Microsoft Defender for Identity feature, and there are any active alerts.</span></span> <span data-ttu-id="8ac6f-217">자세한 내용은 "경고" 드릴다운에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-217">More information is available in the "Alerts" drill down.</span></span>

![활성 경고 카드의 이미지](images/risk-level-small.png)

>[!NOTE]
><span data-ttu-id="8ac6f-219">이 기능을 사용하려면 ID용 Microsoft Defender 및 Endpoint용 Defender에서 통합을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-219">You'll need to enable the integration on both Microsoft Defender for Identity and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="8ac6f-220">Endpoint용 Defender에서 고급 기능에서 이 기능을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-220">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="8ac6f-221">고급 기능을 사용하도록 설정하는 방법에 대한 자세한 내용은 고급 기능 [켜기 를 참조하세요.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="8ac6f-221">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

### <a name="logged-on-users"></a><span data-ttu-id="8ac6f-222">로그온한 사용자</span><span class="sxs-lookup"><span data-stu-id="8ac6f-222">Logged on users</span></span>

<span data-ttu-id="8ac6f-223">**로그온한** 사용자 카드에는 지난 30일 동안 로그온한 사용자 수와 가장 자주 또는 가장 자주 로그온한 사용자 수가 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-223">The **Logged on users** card shows how many users have logged on in the past 30 days, along with the most and least frequent users.</span></span> <span data-ttu-id="8ac6f-224">"모든 사용자 보기" 링크를 선택하면 세부 정보 창이 열리며, 세부 정보 창에는 사용자 유형, 로그온 유형, 사용자가 처음 및 마지막으로 본 때와 같은 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-224">Selecting the "See all users" link opens the details pane, which displays information such as user type, log on type, and when the user was first and last seen.</span></span> <span data-ttu-id="8ac6f-225">자세한 내용은 사용자 엔터티 [조사를 참조하세요.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="8ac6f-225">For more information, see [Investigate user entities](investigate-user.md).</span></span>

![사용자 세부 정보 창의 이미지](images/logged-on-users.png)

### <a name="security-assessments"></a><span data-ttu-id="8ac6f-227">보안 평가</span><span class="sxs-lookup"><span data-stu-id="8ac6f-227">Security assessments</span></span>

<span data-ttu-id="8ac6f-228">보안 **평가** 카드는 전체 노출 수준, 보안 권장 사항, 설치된 소프트웨어 및 발견된 취약점을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="8ac6f-228">The **Security assessments** card shows the overall exposure level, security recommendations, installed software, and discovered vulnerabilities.</span></span> <span data-ttu-id="8ac6f-229">장치의 노출 수준은 보류 중인 보안 권장 사항의 누적 영향에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ac6f-229">A device's exposure level is determined by the cumulative impact of its pending security recommendations.</span></span>

![보안 평가 카드의 이미지](images/security-assessments.png)

## <a name="related-topics"></a><span data-ttu-id="8ac6f-231">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8ac6f-231">Related topics</span></span>

- [<span data-ttu-id="8ac6f-232">끝점 경고 큐에 대한 Microsoft Defender 보기 및 구성</span><span class="sxs-lookup"><span data-stu-id="8ac6f-232">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="8ac6f-233">끝점 경고에 대한 Microsoft Defender 관리</span><span class="sxs-lookup"><span data-stu-id="8ac6f-233">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="8ac6f-234">끝점 경고에 대한 Microsoft Defender 조사</span><span class="sxs-lookup"><span data-stu-id="8ac6f-234">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="8ac6f-235">끝점 경고에 대한 Defender와 관련된 파일 조사</span><span class="sxs-lookup"><span data-stu-id="8ac6f-235">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="8ac6f-236">끝점 경고에 대한 Defender와 연결된 IP 주소 조사</span><span class="sxs-lookup"><span data-stu-id="8ac6f-236">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="8ac6f-237">끝점 경고에 대한 Defender와 연결된 도메인 조사</span><span class="sxs-lookup"><span data-stu-id="8ac6f-237">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="8ac6f-238">Defender에서 끝점에 대한 사용자 계정 조사</span><span class="sxs-lookup"><span data-stu-id="8ac6f-238">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="8ac6f-239">보안 권장</span><span class="sxs-lookup"><span data-stu-id="8ac6f-239">Security recommendation</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="8ac6f-240">소프트웨어 인벤토리</span><span class="sxs-lookup"><span data-stu-id="8ac6f-240">Software inventory</span></span>](tvm-software-inventory.md)
