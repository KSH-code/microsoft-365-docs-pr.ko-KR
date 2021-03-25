---
title: Microsoft Defender ATP 장치 목록 보기 및 구성
description: 조사를 향상하기 위해 목록을 정렬, 필터링 및 내보내기와 같은 장치 목록에서 사용할 수 있는 사용 가능한 기능에 대해 자세히 알아보습니다.
keywords: 정렬, 필터, 내보내기, csv, 장치 이름, 도메인, 마지막으로 본, 내부 IP, 상태, 활성 경고, 활성 맬웨어 감지, 위협 범주, 경고 검토, 네트워크, 연결, 맬웨어, 유형, 암호 도용자, 랜섬웨어, 악용, 위협, 일반 맬웨어, 원치 않는 소프트웨어
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 01ad9f92299cd9d1b4a723bdec54f86f32ca8274
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076583"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="79989-104">끝점 장치용 Microsoft Defender 목록 보기 및 구성</span><span class="sxs-lookup"><span data-stu-id="79989-104">View and organize the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="79989-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="79989-105">**Applies to:**</span></span>
- [<span data-ttu-id="79989-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="79989-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="79989-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79989-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="79989-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="79989-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="79989-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="79989-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-machinesview-abovefoldlink)


<span data-ttu-id="79989-110">장치 **목록에는** 경고가 생성된 네트워크의 장치 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="79989-110">The **Devices list** shows a list of the devices in your network where alerts were generated.</span></span> <span data-ttu-id="79989-111">기본적으로 큐에는 지난 30일 동안의 장치가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="79989-111">By default, the queue displays devices seen in the last 30 days.</span></span>  

<span data-ttu-id="79989-112">도메인, 위험 수준, OS 플랫폼 등의 정보와 가장 위험한 장치를 쉽게 식별할 수 있는 기타 세부 정보를 한눈에 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79989-112">At a glance you'll see information such as domain, risk level, OS platform, and other details for easy identification of devices most at risk.</span></span>

<span data-ttu-id="79989-113">장치 목록 보기를 사용자 지정하기 위해 선택할 수 있는 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79989-113">There are several options you can choose from to customize the devices list view.</span></span> <span data-ttu-id="79989-114">위쪽 탐색에서 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79989-114">On the top navigation you can:</span></span>

- <span data-ttu-id="79989-115">열 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="79989-115">Add or remove columns</span></span>
- <span data-ttu-id="79989-116">전체 목록 내보내기(CSV 형식)</span><span class="sxs-lookup"><span data-stu-id="79989-116">Export the entire list in CSV format</span></span>
- <span data-ttu-id="79989-117">페이지당 표시해야 하는 항목 수 선택</span><span class="sxs-lookup"><span data-stu-id="79989-117">Select the number of items to show per page</span></span>
- <span data-ttu-id="79989-118">필터 적용</span><span class="sxs-lookup"><span data-stu-id="79989-118">Apply filters</span></span>

<span data-ttu-id="79989-119">온보더링 프로세스 중에  장치 목록은 센서 데이터 보고를 시작하면 디바이스로 점진적으로 채워지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79989-119">During the onboarding process, the **Devices list** is gradually populated with devices as they begin to report sensor data.</span></span> <span data-ttu-id="79989-120">이 보기를 사용하여 온보드 엔드포인트가 온라인 상태로 전환될 때 추적하거나, 전체 끝점 목록을 오프라인 분석을 위한 CSV 파일로 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="79989-120">Use this view to track your onboarded endpoints as they come online, or download the complete endpoint list as a CSV file for offline analysis.</span></span>

>[!NOTE]
> <span data-ttu-id="79989-121">장치 목록을 내보낼 경우 조직의 모든 장치가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79989-121">If you export the device list, it will contain every device in your organization.</span></span> <span data-ttu-id="79989-122">조직의 규모에 따라 다운로드하는 데 많은 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79989-122">It might take a significant amount of time to download, depending on how large your organization is.</span></span> <span data-ttu-id="79989-123">목록을 CSV 형식으로 내보내면 데이터가 필터되지 않은 방식으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="79989-123">Exporting the list in CSV format displays the data in an unfiltered manner.</span></span> <span data-ttu-id="79989-124">CSV 파일에는 보기 자체에 적용된 필터링에 관계없이 조직의 모든 장치가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="79989-124">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself.</span></span>

![장치 목록이 있는 장치 목록의 이미지](images/device-list.png)

## <a name="sort-and-filter-the-device-list"></a><span data-ttu-id="79989-126">장치 목록 정렬 및 필터링</span><span class="sxs-lookup"><span data-stu-id="79989-126">Sort and filter the device list</span></span>

<span data-ttu-id="79989-127">다음 필터를 적용하여 경고 목록을 제한하고 보다 집중적인 보기를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79989-127">You can apply the following filters to limit the list of alerts and get a more focused view.</span></span>

### <a name="risk-level"></a><span data-ttu-id="79989-128">위험 수준</span><span class="sxs-lookup"><span data-stu-id="79989-128">Risk level</span></span>

<span data-ttu-id="79989-129">위험 수준은 장치의 활성 경고 유형 및 심각도 등 여러 요인의 조합에 따라 장치의 전반적인 위험 평가를 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="79989-129">The risk level reflects the overall risk assessment of the device based on a combination of factors, including the types and severity of active alerts on the device.</span></span> <span data-ttu-id="79989-130">활성 경고를 해결하고, 재구성 활동을 인가하고, 후속 경고를 표시하지는하면 위험 수준이 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="79989-130">Resolving active alerts, approving remediation activities, and suppressing subsequent alerts can lower the risk level.</span></span>

### <a name="exposure-level"></a><span data-ttu-id="79989-131">노출 수준</span><span class="sxs-lookup"><span data-stu-id="79989-131">Exposure level</span></span>

<span data-ttu-id="79989-132">노출 수준은 보류 중인 보안 권장 사항의 누적 영향에 따라 장치의 현재 노출을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="79989-132">The exposure level reflects the current exposure of the device based on the cumulative impact of its pending security recommendations.</span></span> <span data-ttu-id="79989-133">가능한 수준은 낮음, 보통 및 높음입니다.</span><span class="sxs-lookup"><span data-stu-id="79989-133">The possible levels are low, medium, and high.</span></span> <span data-ttu-id="79989-134">노출이 낮을 경우 장치가 악용에 덜 취약하다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="79989-134">Low exposure means your devices are less vulnerable from exploitation.</span></span>

<span data-ttu-id="79989-135">노출 수준에 "데이터를 사용할 수 없음"이면 몇 가지 이유가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79989-135">If the exposure level says "No data available," there are a few reasons why this may be the case:</span></span>

- <span data-ttu-id="79989-136">장치가 30일 이상 보고를 중지했습니다. 이 경우 비활성으로 간주하고 노출이 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79989-136">Device stopped reporting for more than 30 days – in that case it is considered inactive, and the exposure isn't computed</span></span>
- <span data-ttu-id="79989-137">장치 OS가 지원되지 않습니다. [끝점용 Microsoft Defender에 대한 최소 요구 사항 참조](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="79989-137">Device OS not supported - see [minimum requirements for Microsoft Defender for Endpoint](minimum-requirements.md)</span></span>
- <span data-ttu-id="79989-138">부실 에이전트가 있는 장치(매우 가능성 낮음)</span><span class="sxs-lookup"><span data-stu-id="79989-138">Device with stale agent (very unlikely)</span></span>

### <a name="os-platform"></a><span data-ttu-id="79989-139">OS 플랫폼</span><span class="sxs-lookup"><span data-stu-id="79989-139">OS Platform</span></span>

<span data-ttu-id="79989-140">조사할 OS 플랫폼만 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79989-140">Select only the OS platforms you're interested in investigating.</span></span>

### <a name="health-state"></a><span data-ttu-id="79989-141">상태</span><span class="sxs-lookup"><span data-stu-id="79989-141">Health state</span></span>

<span data-ttu-id="79989-142">다음 장치 상태로 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="79989-142">Filter by the following device health states:</span></span>

- <span data-ttu-id="79989-143">**Active** – 서비스에 센서 데이터를 적극적으로 보고하는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="79989-143">**Active** – Devices that are actively reporting sensor data to the service.</span></span>
- <span data-ttu-id="79989-144">**비활성** - 7일 이상 신호 전송을 완전히 중지한 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="79989-144">**Inactive** – Devices that have completely stopped sending signals for more than 7 days.</span></span>
- <span data-ttu-id="79989-145">**잘못 구성되었습니다.** 서비스와의 통신이 손상되거나 센서 데이터를 보낼 수 없는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="79989-145">**Misconfigured** – Devices that have impaired communications with service or are unable to send sensor data.</span></span> <span data-ttu-id="79989-146">잘못 구성된 장치는 다음으로 더 분류될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79989-146">Misconfigured devices can further be classified to:</span></span>
  - <span data-ttu-id="79989-147">센서 데이터 없음</span><span class="sxs-lookup"><span data-stu-id="79989-147">No sensor data</span></span>
  - <span data-ttu-id="79989-148">통신 장애</span><span class="sxs-lookup"><span data-stu-id="79989-148">Impaired communications</span></span>

  <span data-ttu-id="79989-149">잘못 구성 된 장치에서 문제를 해결하는 방법에 대한 자세한 내용은 [Unhealthy sensors](fix-unhealthy-sensors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79989-149">For more information on how to address issues on misconfigured devices see, [Fix unhealthy sensors](fix-unhealthy-sensors.md).</span></span>

### <a name="antivirus-status"></a><span data-ttu-id="79989-150">바이러스 백신 상태</span><span class="sxs-lookup"><span data-stu-id="79989-150">Antivirus status</span></span>

<span data-ttu-id="79989-151">바이러스 백신 상태를 사용하여 장치를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="79989-151">Filter devices by antivirus status.</span></span> <span data-ttu-id="79989-152">활성 Windows 10 디바이스에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="79989-152">Applies to active Windows 10 devices only.</span></span>

- <span data-ttu-id="79989-153">**사용 안 하게** & 위협 방지가 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79989-153">**Disabled** - Virus & threat protection is turned off.</span></span>
- <span data-ttu-id="79989-154">**보고하지 않습니다.** 위협 & 바이러스 백신이 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79989-154">**Not reporting** - Virus & threat protection is not reporting.</span></span>
- <span data-ttu-id="79989-155">**업데이트되지** 않습니다. 위협 & 바이러스가 최신이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="79989-155">**Not updated** - Virus & threat protection is not up to date.</span></span>

<span data-ttu-id="79989-156">자세한 내용은 [View the Threat & Vulnerability Management dashboard를 참조하세요.](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="79989-156">For more information, see [View the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md).</span></span>

### <a name="threat-mitigation-status"></a><span data-ttu-id="79989-157">위협 완화 상태</span><span class="sxs-lookup"><span data-stu-id="79989-157">Threat mitigation status</span></span>

<span data-ttu-id="79989-158">특정 위협의 영향을 받을 수 있는 장치를 확인하려면 드롭다운 메뉴에서 위협을 선택한 다음 완화해야 하는 취약성 측면을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79989-158">To view devices that may be affected by a certain threat, select the threat from the dropdown menu, and then select what vulnerability aspect needs to be mitigated.</span></span>

<span data-ttu-id="79989-159">특정 위협에 대한 자세한 내용은 [위협 분석을 참조하세요.](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="79989-159">To learn more about certain threats, see [Threat analytics](threat-analytics.md).</span></span> <span data-ttu-id="79989-160">완화 정보는 위협 및 [& 관리를 참조하세요.](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="79989-160">For mitigation information, see [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span>

### <a name="windows-10-version"></a><span data-ttu-id="79989-161">Windows 10 버전</span><span class="sxs-lookup"><span data-stu-id="79989-161">Windows 10 version</span></span>

<span data-ttu-id="79989-162">조사할 Windows 10 버전만 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79989-162">Select only the Windows 10 versions you're interested in investigating.</span></span>

### <a name="tags--groups"></a><span data-ttu-id="79989-163">태그 & 그룹</span><span class="sxs-lookup"><span data-stu-id="79989-163">Tags & Groups</span></span>

<span data-ttu-id="79989-164">개별 장치에 추가한 그룹화 및 태그 지정에 따라 목록을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="79989-164">Filter the list based on the grouping and tagging that you've added to individual devices.</span></span> <span data-ttu-id="79989-165">디바이스 태그 만들기 [및 관리](machine-tags.md) 및 장치 그룹 만들기 및 관리를 [참조하세요.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="79989-165">See [Create and manage device tags](machine-tags.md) and [Create and manage device groups](machine-groups.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="79989-166">관련 항목</span><span class="sxs-lookup"><span data-stu-id="79989-166">Related topics</span></span>

- [<span data-ttu-id="79989-167">Microsoft Defender for Endpoint Devices 목록에서 장치 조사</span><span class="sxs-lookup"><span data-stu-id="79989-167">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
