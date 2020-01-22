---
title: 배터리 정보
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b14ef9970aa709ad5e23fdae467992497a1331e8
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260157"
---
# <a name="battery-insights"></a><span data-ttu-id="38057-103">배터리 정보</span><span class="sxs-lookup"><span data-stu-id="38057-103">Battery insights</span></span>
<span data-ttu-id="38057-104">이 보기는 Microsoft 관리 데스크톱 장치에 대 한 전원, 배터리 및 앱 사용 메트릭을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38057-104">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="38057-105">이러한 용도의 앱은 실행 중이 고 포커스가 있는 경우 "사용 중"으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38057-105">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="38057-106">사용 현황 데이터를 보려면 **배터리** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="38057-106">To view usage data, select the **Battery** tab.</span></span>

![배터리 창: 왼쪽 위에 있는 각 장치에 대해 예상 되는 배터리 수명 모델입니다.](images/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="38057-109">예측 한 배터리 수명</span><span class="sxs-lookup"><span data-stu-id="38057-109">Predicted battery life</span></span>

<span data-ttu-id="38057-110">예상 되는 **배터리 수명** 영역에서 장치 모델에 따라 구성 된 장치에 대 한 예상 배터리 수명 예측을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38057-110">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="38057-111">이 데이터는 Microsoft Managed Desktop deployment에서 데이터를 보고 하는 장치를 임의로 <em>선택</em> 했을 때 에너지 사용량, 사용 시간 및 배터리 용량 샘플링에서 파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38057-111">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="38057-112">이 표에서는 다른 Microsoft Managed Desktop 배포의 동일한 모델에 대 한 예상 배터리 수명, 평균 배터리 수명 및 해당 환경에서이 데이터를 보고 하는 장치 수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38057-112">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="38057-113">열 머리글을 선택 하 여 데이터를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="38057-113">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="38057-114">주요 에너지 소비자</span><span class="sxs-lookup"><span data-stu-id="38057-114">Top energy consumers</span></span>

<span data-ttu-id="38057-115">**상위 에너지 소비자** 분야에서는 MilliWatt (mWh)에서 가장 많은 에너지를 사용 하는 환경에서 앱을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38057-115">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="38057-116">표시 되는 앱은 왼쪽에 있는 **예측 된 배터리 수명** 섹션에서 선택한 특정 장치에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38057-116">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="38057-117">예를 들어 마이크로 Sft Surface Book 2 장치의 앱 단위 소비량을 보려면 배터리 수명 영역에서 해당 행을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="38057-117">For example, to see the per-app consumption for your Microsft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="38057-118">모델을 선택 하지 않으면 기본적으로 데이터를 포함 하는 모든 앱에 대 한 앱 소비 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38057-118">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="38057-119">각 앱에 대해 색 세그먼트는 다음 범주 중에서 앱의 에너지 사용 분포를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="38057-119">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="38057-120">CPU</span><span class="sxs-lookup"><span data-stu-id="38057-120">CPU</span></span>
- <span data-ttu-id="38057-121">디스플레이</span><span class="sxs-lookup"><span data-stu-id="38057-121">Display</span></span>
- <span data-ttu-id="38057-122">네트워크</span><span class="sxs-lookup"><span data-stu-id="38057-122">Network</span></span>
- <span data-ttu-id="38057-123">기타</span><span class="sxs-lookup"><span data-stu-id="38057-123">Other</span></span>

<span data-ttu-id="38057-124">"Other"는 디스크 활동, 모바일 광대역 사용량, 내부 저항에 대 한 에너지 손실 등 다양 한 원본의 에너지 소비량을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38057-124">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="38057-125">\* \* 최고의 에너지 소비자 "에 표시 되는 앱</span><span class="sxs-lookup"><span data-stu-id="38057-125">The apps displayed in \*\*Top energy consumers"</span></span>

<span data-ttu-id="38057-126">오른쪽 위에 있는 메뉴를 사용 하 여 포그라운드 앱, 백그라운드 앱 또는 둘 다를 표시 하도록이 보기를 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38057-126">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="38057-127">포그라운드 앱은 마우스를 사용 하 여 항목을 선택 하는 것과 같이 지난 28 일 이내에 사용자 상호 작용이 발생 한 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="38057-127">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="38057-128">인사이트</span><span class="sxs-lookup"><span data-stu-id="38057-128">Insights</span></span>

<span data-ttu-id="38057-129">이 **Insights** 영역에는 CPU 및 네트워크 범주에 있는 세 가지 에너지 소비자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38057-129">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="38057-130">이러한 항목은 모든 Microsoft Managed Desktop 배포에 비해 평균 에너지 보다 높은 수준으로 소비 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38057-130">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="38057-131">표시 리소스는 장치 사용 시간 및 화면 밝기 설정에 크게 좌우 되므로 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38057-131">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="38057-132">자세한 내용을 보려면 **세부 정보** 열에서 목록을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="38057-132">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="38057-133">배터리 최적화</span><span class="sxs-lookup"><span data-stu-id="38057-133">Battery optimization</span></span>

<span data-ttu-id="38057-134">Windows 10에서는 전원 사용을 개선 하 고 Microsoft 관리 되는 데스크톱 장치의 배터리 수명 증가를 위해 다양 한 [장치 설정을](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38057-134">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="38057-135">이러한 설정 중 일부는 다른 Windows 기능을 줄일 수 있으므로 조직의 장치 역할과 같은 다른 요소도 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38057-135">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="38057-136">Windows 지원에서는 이러한 [배터리 저장 팁](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)의 목록을 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="38057-136">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="38057-137">사용자는 관리자 권한 상승이 나 지원을 필요로 하지 않고 자체 설정을 직접 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38057-137">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="38057-138">다른 설정을 위해서는 조직의 IT 관리자가 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38057-138">Other settings require support from your organization's IT administrator.</span></span>
