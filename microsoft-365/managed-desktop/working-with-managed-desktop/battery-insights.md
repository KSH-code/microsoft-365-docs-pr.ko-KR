---
title: 배터리 정보 활용
description: 예측된 배터리 사용시간 및 최고 전력 소비자에 대한 데이터를 보여주는 보고서
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 32ab3a984d5ab46aac26989518cd3e570082d688
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739832"
---
# <a name="battery-insights"></a><span data-ttu-id="2de7f-104">배터리 정보 활용</span><span class="sxs-lookup"><span data-stu-id="2de7f-104">Battery insights</span></span>
<span data-ttu-id="2de7f-105">이 보기는 디바이스에 전원, 배터리 및 앱 사용 메트릭을 Microsoft Managed Desktop 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-105">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="2de7f-106">이러한 목적을 위해 앱이 실행 중일 때 포커스가 있는 경우 앱은 "사용 중"으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-106">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="2de7f-107">사용 현황 데이터를 확인하려면 배터리 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-107">To view usage data, select the **Battery** tab.</span></span>

![배터리 창: 왼쪽 상단의 장치 모델당 배터리 사용 시간 예측, 오른쪽 위 에너지 소비자(앱에서) 아래쪽의 인사이트 표](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="2de7f-110">예측된 배터리 수명</span><span class="sxs-lookup"><span data-stu-id="2de7f-110">Predicted battery life</span></span>

<span data-ttu-id="2de7f-111">예측된 배터리 **수명** 영역에는 장치 모델별로 구성되는 장치의 예상 배터리 수명에 대한 예측이 제공되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-111">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="2de7f-112">이 데이터는 에너지 사용량, 사용 시간 및 배터리 용량 <em></em> 샘플링에서 파생된 것으로, 데이터를 보고하는 Microsoft Managed Desktop 배포에서 임의로 선택한 장치에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-112">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="2de7f-113">이 표에서는 예측된 배터리 사용 시간(시간), 다른 Microsoft Managed Desktop 배포에서 동일한 모델의 평균 배터리 사용 시간 및 사용자 환경에서 이 데이터를 보고하는 장치 수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-113">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="2de7f-114">열 제목을 선택하여 데이터를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-114">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="2de7f-115">상위 에너지 소비자</span><span class="sxs-lookup"><span data-stu-id="2de7f-115">Top energy consumers</span></span>

<span data-ttu-id="2de7f-116">Top **energy consumers(상위** 에너지 소비자) 영역에는 밀리와트 시간(mWh)에서 가장 많은 에너지가 소비되는 앱을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-116">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="2de7f-117">표시된 앱은 왼쪽의 예측된 배터리 사용  수명 섹션에서 선택하는 특정 장치별입니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-117">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="2de7f-118">예를 들어 Microsoft Surface Book 2 장치의 앱당 소비를 확인하려면 배터리 사용 Surface Book 영역의 해당 행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-118">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="2de7f-119">모델을 선택하지 않은 경우 표시되는 앱 사용 데이터는 데이터를 집합적으로 사용하는 모든 앱에 대해 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-119">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="2de7f-120">각 앱에 대해 색이 있는 세그먼트는 다음 범주에 앱의 에너지 사용 분포를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="2de7f-120">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="2de7f-121">CPU</span><span class="sxs-lookup"><span data-stu-id="2de7f-121">CPU</span></span>
- <span data-ttu-id="2de7f-122">디스플레이</span><span class="sxs-lookup"><span data-stu-id="2de7f-122">Display</span></span>
- <span data-ttu-id="2de7f-123">네트워크</span><span class="sxs-lookup"><span data-stu-id="2de7f-123">Network</span></span>
- <span data-ttu-id="2de7f-124">기타</span><span class="sxs-lookup"><span data-stu-id="2de7f-124">Other</span></span>

<span data-ttu-id="2de7f-125">"기타"에는 디스크 활동, 모바일 광대역 사용량, 내부 저항으로 손실된 에너지 등 다양한 소스의 에너지 소비가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-125">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="2de7f-126">이 보기를 필터링하여 포그라운드 앱, 백그라운드 앱 또는 둘 다 오른쪽 위에 있는 메뉴를 사용하여 둘 다를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-126">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="2de7f-127">포그라운드 앱은 마우스로 무언가를 선택하는 등 지난 28일 동안 사용자 조작이 있는 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-127">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="2de7f-128">인사이트</span><span class="sxs-lookup"><span data-stu-id="2de7f-128">Insights</span></span>

<span data-ttu-id="2de7f-129">**인사이트 영역에는** CPU 및 네트워크 범주의 상위 3가지 에너지 소비자가 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-129">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="2de7f-130">이러한 항목은 모든 배포에 비해 평균 에너지 Microsoft Managed Desktop 소비됩니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-130">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="2de7f-131">디스플레이 리소스는 장치 사용 시간 및 화면 밝기 설정에 크게 의존하기 때문에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-131">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="2de7f-132">자세한 내용은 **세부** 정보 열에서 목록을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-132">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="2de7f-133">배터리 최적화</span><span class="sxs-lookup"><span data-stu-id="2de7f-133">Battery optimization</span></span>

<span data-ttu-id="2de7f-134">Windows 10 다양한 장치 [](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) 설정을 사용하여 전원 사용량을 개선하고 장치 장치의 배터리 Microsoft Managed Desktop 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-134">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="2de7f-135">이러한 설정 중 일부는 다른 Windows 기능을 떨어질 수 있으므로 조직에서 장치의 역할과 같은 다른 요인도 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-135">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="2de7f-136">Windows 지원에서는 이러한 배터리 절약 팁 [목록을 유지 관리합니다.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)</span><span class="sxs-lookup"><span data-stu-id="2de7f-136">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="2de7f-137">사용자는 관리자 권한 상승 또는 지원 없이도 일부 설정을 직접 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-137">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="2de7f-138">다른 설정을 사용하려면 조직의 IT 관리자로부터 지원을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="2de7f-138">Other settings require support from your organization's IT administrator.</span></span>
