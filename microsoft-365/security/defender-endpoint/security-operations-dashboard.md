---
title: Microsoft Defender 보안 센터 보안 작업 대시보드
description: 대시보드를 사용하여 위험이 있는 장치를 식별하고, 서비스의 상태를 추적하고, 장치 및 경고에 대한 통계 및 정보를 볼 수 있습니다.
keywords: 대시보드, 경고, 새, 진행 중, 해결된, 위험, 위험 상태의 장치, 감염, 보고, 통계, 차트, 그래프, 상태, 활성 맬웨어 감지, 위협 범주, 범주, 암호 도용자, 랜섬웨어, 악용, 위협, 낮은 심각도, 활성 맬웨어
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
ms.openlocfilehash: bfa23138b1bab4abcdfa0b4b9d689a4a4cfc7fc1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072951"
---
# <a name="microsoft-defender-security-center-security-operations-dashboard"></a><span data-ttu-id="ed874-104">Microsoft Defender 보안 센터 보안 작업 대시보드</span><span class="sxs-lookup"><span data-stu-id="ed874-104">Microsoft Defender Security Center Security operations dashboard</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ed874-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ed874-105">**Applies to:**</span></span>
- [<span data-ttu-id="ed874-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ed874-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="ed874-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="ed874-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ed874-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 

<span data-ttu-id="ed874-109">보안 **작업 대시보드는** 끝점 검색 및 응답 기능이 표시되어 있는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-109">The **Security operations dashboard** is where the endpoint detection and response capabilities are surfaced.</span></span> <span data-ttu-id="ed874-110">검색된 위치를 간략하게 개요하고 대응 조치가 필요한 위치를 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-110">It provides a high level overview of where detections were seen and highlights where response actions are needed.</span></span> 

<span data-ttu-id="ed874-111">대시보드에 다음 스냅숏이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-111">The dashboard displays a snapshot of:</span></span>

- <span data-ttu-id="ed874-112">활성 경고</span><span class="sxs-lookup"><span data-stu-id="ed874-112">Active alerts</span></span>
- <span data-ttu-id="ed874-113">위험에 노출된 장치</span><span class="sxs-lookup"><span data-stu-id="ed874-113">Devices at risk</span></span>
- <span data-ttu-id="ed874-114">센서 상태</span><span class="sxs-lookup"><span data-stu-id="ed874-114">Sensor health</span></span>
- <span data-ttu-id="ed874-115">서비스 상태</span><span class="sxs-lookup"><span data-stu-id="ed874-115">Service health</span></span>
- <span data-ttu-id="ed874-116">매일 보고하는 장치</span><span class="sxs-lookup"><span data-stu-id="ed874-116">Daily devices reporting</span></span>
- <span data-ttu-id="ed874-117">활성 자동화 조사</span><span class="sxs-lookup"><span data-stu-id="ed874-117">Active automated investigations</span></span>
- <span data-ttu-id="ed874-118">자동화된 조사 통계</span><span class="sxs-lookup"><span data-stu-id="ed874-118">Automated investigations statistics</span></span>
- <span data-ttu-id="ed874-119">위험에 노출된 사용자</span><span class="sxs-lookup"><span data-stu-id="ed874-119">Users at risk</span></span>
- <span data-ttu-id="ed874-120">의심스러운 활동</span><span class="sxs-lookup"><span data-stu-id="ed874-120">Suspicious activities</span></span>


![보안 작업 대시보드의 이미지](images/atp-sec-ops-dashboard.png)

<span data-ttu-id="ed874-122">경고 및 장치를 탐색하고 조사하여 의심스러운 활동이 네트워크에서 발생된 경우 해당 컨텍스트를 이해하는 데 도움이 될 수 있도록 신속하게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-122">You can explore and investigate alerts and devices to quickly determine if, where, and when suspicious activities occurred in your network to help you understand the context they appeared in.</span></span>

<span data-ttu-id="ed874-123">보안 **작업 대시보드에서는** 장치에서 중요한 이벤트 또는 동작을 쉽게 식별할 수 있도록 집계된 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-123">From the **Security operations dashboard** you will see aggregated events to facilitate the identification of significant events or behaviors on a device.</span></span> <span data-ttu-id="ed874-124">또한 세부적인 이벤트와 낮은 수준의 표시기를 드릴다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-124">You can also drill down into granular events and low-level indicators.</span></span>

<span data-ttu-id="ed874-125">또한 조직의 전반적인 상태를 시각적으로 확인할 수 있는 클릭 가능한 타일도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-125">It also has clickable tiles that give visual cues on the overall health state of your organization.</span></span> <span data-ttu-id="ed874-126">각 타일에는 해당 개요에 대한 자세한 보기가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-126">Each tile opens a detailed view of the corresponding overview.</span></span>

## <a name="active-alerts"></a><span data-ttu-id="ed874-127">활성 경고</span><span class="sxs-lookup"><span data-stu-id="ed874-127">Active alerts</span></span>
<span data-ttu-id="ed874-128">타일에서 네트워크에서 지난 30일 동안의 전체 활성 경고 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-128">You can view the overall number of active alerts from the last 30 days in your network from the tile.</span></span> <span data-ttu-id="ed874-129">경고는 신규 및 진행 **중으로** **그룹화됩니다.**</span><span class="sxs-lookup"><span data-stu-id="ed874-129">Alerts are grouped into **New** and **In progress**.</span></span>

![지난 30일 동안의 경고 목록을 보려면 각 조각 또는 심각도 클릭](images/active-alerts-tile.png)

<span data-ttu-id="ed874-131">각 그룹은 해당 경고 심각도 수준으로 더 하위 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-131">Each group is further sub-categorized into their corresponding alert severity levels.</span></span> <span data-ttu-id="ed874-132">각 경고 링 내부의 경고 수를 클릭하여 해당 범주 큐의 정렬된 보기(신규 또는 진행 **중)를 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="ed874-132">Click the number of alerts inside each alert ring to see a sorted view of that category's queue (**New** or **In progress**).</span></span>

<span data-ttu-id="ed874-133">자세한 내용은 [경고 개요를 참조하세요.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="ed874-133">For more information see, [Alerts overview](alerts-queue.md).</span></span>

<span data-ttu-id="ed874-134">각 행에는 경고 심각도 범주와 경고에 대한 간단한 설명이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-134">Each row includes an alert severity category and a short description of the alert.</span></span> <span data-ttu-id="ed874-135">경고를 클릭하여 자세한 보기를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-135">You can click an alert to see its detailed view.</span></span> <span data-ttu-id="ed874-136">자세한 내용은 [Endpoint 경고에 대한 Microsoft Defender](investigate-alerts.md) 조사 및 경고 [개요를 참조하세요.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="ed874-136">For more information see,  [Investigate Microsoft Defender for Endpoint alerts](investigate-alerts.md) and [Alerts overview](alerts-queue.md).</span></span>


## <a name="devices-at-risk"></a><span data-ttu-id="ed874-137">위험에 노출된 장치</span><span class="sxs-lookup"><span data-stu-id="ed874-137">Devices at risk</span></span>
<span data-ttu-id="ed874-138">이 타일은 활성 경고가 가장 많은 장치 목록을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-138">This tile shows you a list of devices with the highest number of active alerts.</span></span> <span data-ttu-id="ed874-139">각 디바이스에 대한 총 경고 수는 장치 이름 옆에 있는 원으로 표시되고 타일의 맨 끝에 심각도 수준별로 추가 분류됩니다(각 심각도 표시줄 위에 마우스를 다가 레이블을 확인합니다).</span><span class="sxs-lookup"><span data-stu-id="ed874-139">The total number of alerts for each device is shown in a circle next to the device name, and then further categorized by severity levels at the far end of the tile (hover over each severity bar to see its label).</span></span>

![위험에 노출된 장치 타일은 경고 수가 가장 많은 장치 목록과 경고 심각도 분석이 표시됩니다.](images/devices-at-risk-tile.png)

<span data-ttu-id="ed874-141">디바이스의 이름을 클릭하여 해당 장치에 대한 세부 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-141">Click the name of the device to see details about that device.</span></span> <span data-ttu-id="ed874-142">자세한 내용은 Microsoft Defender for Endpoint Devices 목록에서 장치 [조사를 참조하세요.](investigate-machines.md)</span><span class="sxs-lookup"><span data-stu-id="ed874-142">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

<span data-ttu-id="ed874-143">타일 맨  위에 있는 장치 목록을 클릭하여 활성 경고 수별로 정렬된 장치 목록으로 바로 이동하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-143">You can also click **Devices list** at the top of the tile to go directly to the **Devices list**, sorted by the number of active alerts.</span></span> <span data-ttu-id="ed874-144">자세한 내용은 Microsoft Defender for Endpoint Devices 목록에서 장치 [조사를 참조하세요.](investigate-machines.md)</span><span class="sxs-lookup"><span data-stu-id="ed874-144">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

## <a name="devices-with-sensor-issues"></a><span data-ttu-id="ed874-145">센서 문제가 있는 장치</span><span class="sxs-lookup"><span data-stu-id="ed874-145">Devices with sensor issues</span></span>
<span data-ttu-id="ed874-146">센서 **문제가 있는 장치** 타일은 끝점용 Microsoft Defender 서비스에 센서 데이터를 제공하는 개별 장치의 능력에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-146">The **Devices with sensor issues** tile provides information on the individual device’s ability to provide sensor data to the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="ed874-147">주의가 필요한 장치 수를 보고하고 문제가 있는 장치를 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-147">It reports how many devices require attention and helps you identify problematic devices.</span></span>

![센서 문제가 있는 디바이스 타일](images/atp-tile-sensor-health.png)

<span data-ttu-id="ed874-149">서비스에 올바르게 보고하지 않는 장치 수에 대한 정보를 제공하는 두 가지 상태 표시기가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-149">There are two status indicators that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="ed874-150">**잘못 구성되었습니다.** 이러한 장치는 센서 데이터를 부분적으로 끝점용 Microsoft Defender 서비스에 보고할 수 있으며 수정해야 하는 구성 오류가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-150">**Misconfigured** – These devices might partially be reporting sensor data to the Microsoft Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="ed874-151">**비활성** - 지난 달에 7일 이상 끝점용 Microsoft Defender 서비스에 보고를 중지한 장치.</span><span class="sxs-lookup"><span data-stu-id="ed874-151">**Inactive** - Devices that have stopped reporting to the Microsoft Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="ed874-152">그룹을 클릭하면 선택에 따라 필터링된 장치 목록으로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-152">When you click any of the groups, you’ll be directed to devices list, filtered according to your choice.</span></span> <span data-ttu-id="ed874-153">자세한 내용은 센서 상태 확인 [및](check-sensor-status.md) 장치 [조사를 참조하세요.](investigate-machines.md)</span><span class="sxs-lookup"><span data-stu-id="ed874-153">For more information, see [Check sensor state](check-sensor-status.md) and [Investigate devices](investigate-machines.md).</span></span>

## <a name="service-health"></a><span data-ttu-id="ed874-154">서비스 상태</span><span class="sxs-lookup"><span data-stu-id="ed874-154">Service health</span></span>
<span data-ttu-id="ed874-155">서비스 **상태 타일은** 서비스가 활성화되어 있는지 또는 문제가 있는지 알려합니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-155">The **Service health** tile informs you if the service is active or if there are issues.</span></span>

![서비스 상태 타일은 서비스의 전체 지표를 보여 주며,](images/status-tile.png)

<span data-ttu-id="ed874-157">서비스 상태의 자세한 내용은 Endpoint 서비스 상태 [확인을 참조하세요.](service-status.md)</span><span class="sxs-lookup"><span data-stu-id="ed874-157">For more information on the service health, see [Check the Microsoft Defender for Endpoint service health](service-status.md).</span></span>


## <a name="daily-devices-reporting"></a><span data-ttu-id="ed874-158">매일 보고하는 장치</span><span class="sxs-lookup"><span data-stu-id="ed874-158">Daily devices reporting</span></span>
<span data-ttu-id="ed874-159">일별 장치 **보고 타일은** 지난 30일 동안 매일 보고되는 장치 수를 나타내는 막대 그래프를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-159">The **Daily devices reporting** tile shows a bar graph that represents the number of devices reporting daily in the last 30 days.</span></span> <span data-ttu-id="ed874-160">그래프의 개별 막대 위에 마우스를 대면 매일 보고하는 장치의 정확한 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-160">Hover over individual bars on the graph to see the exact number of devices reporting in each day.</span></span>

![보고 타일을 보고하는 일별 장치의 이미지](images/atp-daily-devices-reporting.png)


## <a name="active-automated-investigations"></a><span data-ttu-id="ed874-162">활성 자동화 조사</span><span class="sxs-lookup"><span data-stu-id="ed874-162">Active automated investigations</span></span>
<span data-ttu-id="ed874-163">활성 자동화 조사 타일에서 네트워크에서 지난 30일 동안의 전체 자동화된 조사 수를 볼 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-163">You can view the overall number of automated investigations from the last 30 days in your network from the **Active automated investigations** tile.</span></span> <span data-ttu-id="ed874-164">조사는 보류 중인 **작업,** 장치 대기 및 실행 중으로 **그룹화됩니다.** </span><span class="sxs-lookup"><span data-stu-id="ed874-164">Investigations are grouped into **Pending action**, **Waiting for device**, and **Running**.</span></span>

![활성 자동화된 조사의 미지원](images/atp-active-investigations-tile.png)


## <a name="automated-investigations-statistics"></a><span data-ttu-id="ed874-166">자동화된 조사 통계</span><span class="sxs-lookup"><span data-stu-id="ed874-166">Automated investigations statistics</span></span>
<span data-ttu-id="ed874-167">이 타일은 지난 7일 동안의 자동화된 조사와 관련된 통계를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-167">This tile shows statistics related to automated investigations in the last seven days.</span></span> <span data-ttu-id="ed874-168">완료된 조사 수, 성공적으로 재구성된 조사 수, 조사가 시작되는 데 걸리는 평균 대기 시간, 경고를 수정하는 데 걸리는 평균 시간, 조사된 경고 수 및 일반적인 수동 조사에서 저장된 자동화 시간 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-168">It shows the number of investigations completed, the number of successfully remediated investigations, the average pending time it takes for an investigation to be initiated, the average time it takes to remediate an alert, the number of alerts investigated, and the number of hours of automation saved from a typical manual investigation.</span></span> 

![자동화된 조사 통계 이미지](images/atp-automated-investigations-statistics.png)

<span data-ttu-id="ed874-170">자동화된 **조사,** 재구성된 조사 및 조사된 알림을 클릭하여 해당  범주별로 필터링된 조사 페이지로 이동할 수 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="ed874-170">You can click on **Automated investigations**, **Remediated investigations**, and **Alerts investigated** to navigate to the **Investigations** page, filtered by the appropriate category.</span></span> <span data-ttu-id="ed874-171">이를 통해 컨텍스트에서 자세한 조사 분석 내용을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-171">This lets you see a detailed breakdown of investigations in context.</span></span>

## <a name="users-at-risk"></a><span data-ttu-id="ed874-172">위험에 노출된 사용자</span><span class="sxs-lookup"><span data-stu-id="ed874-172">Users at risk</span></span>
<span data-ttu-id="ed874-173">타일은 가장 활발한 경고가 있는 사용자 계정 목록과 높음, 보통 또는 낮은 경고에 표시될 수 있는 경고 수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-173">The tile shows you a list of user accounts with the most active alerts and the number of alerts seen on high, medium, or low alerts.</span></span> 

![위험에 노출된 사용자 계정 타일은 경고 수가 가장 많은 사용자 계정 목록을 표시하고 경고 심각도 분석](images/atp-users-at-risk.png)

<span data-ttu-id="ed874-175">사용자 계정을 클릭하여 사용자 계정에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-175">Click the user account to see details about the user account.</span></span> <span data-ttu-id="ed874-176">자세한 내용은 사용자 계정 [조사를 참조하세요.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="ed874-176">For more information see [Investigate a user account](investigate-user.md).</span></span>

><span data-ttu-id="ed874-177">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="ed874-177">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ed874-178">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="ed874-178">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="ed874-179">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ed874-179">Related topics</span></span>
- [<span data-ttu-id="ed874-180">끝점 포털용 Microsoft Defender 이해</span><span class="sxs-lookup"><span data-stu-id="ed874-180">Understand the Microsoft Defender for Endpoint portal</span></span>](use.md)
- [<span data-ttu-id="ed874-181">포털 개요</span><span class="sxs-lookup"><span data-stu-id="ed874-181">Portal overview</span></span>](portal-overview.md)
- [<span data-ttu-id="ed874-182">위협 요소 & 관리 대시보드 보기</span><span class="sxs-lookup"><span data-stu-id="ed874-182">View the Threat & Vulnerability Management dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="ed874-183">위협 분석 대시보드 보기 및 권장 완화 작업 수행</span><span class="sxs-lookup"><span data-stu-id="ed874-183">View the Threat analytics dashboard and take recommended mitigation actions</span></span>](threat-analytics.md)
