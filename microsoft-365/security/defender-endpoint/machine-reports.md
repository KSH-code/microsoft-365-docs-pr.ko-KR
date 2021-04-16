---
title: 끝점용 Microsoft Defender의 장치 상태 및 규정 준수 보고서
description: 장치 상태 및 준수 보고서를 사용하여 장치 상태 검색, 바이러스 백신 상태, OS 플랫폼 및 Windows 10 버전 추적
keywords: 상태, 바이러스 백신, os 플랫폼, Windows 10 버전, 버전, 상태, 규정 준수, 상태
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
ms.openlocfilehash: 35100a4b8bdaee23c427816450e948ced9ed3191
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860294"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="938aa-104">끝점용 Microsoft Defender의 장치 상태 및 규정 준수 보고서</span><span class="sxs-lookup"><span data-stu-id="938aa-104">Device health and compliance report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="938aa-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="938aa-105">**Applies to:**</span></span>
- [<span data-ttu-id="938aa-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="938aa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="938aa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="938aa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="938aa-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="938aa-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="938aa-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="938aa-110">장치 상태 보고서는 조직의 장치에 대한 높은 수준의 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-110">The devices status report provides high-level information about the devices in your organization.</span></span> <span data-ttu-id="938aa-111">이 보고서에는 센서 상태, 바이러스 백신 상태, OS 플랫폼 및 Windows 10 버전을 보여주는 추세 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-111">The report includes trending information showing the sensor health state, antivirus status, OS platforms, and Windows 10 versions.</span></span>

<span data-ttu-id="938aa-112">대시보드는 장치 보고서의 이미지와 같은 두 섹션으로 ![ 구성됩니다.](images/device-reports.png)</span><span class="sxs-lookup"><span data-stu-id="938aa-112">The dashboard is structured into two sections: ![Image of the device report](images/device-reports.png)</span></span>
 
<span data-ttu-id="938aa-113">섹션</span><span class="sxs-lookup"><span data-stu-id="938aa-113">Section</span></span> | <span data-ttu-id="938aa-114">설명</span><span class="sxs-lookup"><span data-stu-id="938aa-114">Description</span></span>
:---|:---
<span data-ttu-id="938aa-115">1</span><span class="sxs-lookup"><span data-stu-id="938aa-115">1</span></span> | <span data-ttu-id="938aa-116">디바이스 추세</span><span class="sxs-lookup"><span data-stu-id="938aa-116">Device trends</span></span>
<span data-ttu-id="938aa-117">2</span><span class="sxs-lookup"><span data-stu-id="938aa-117">2</span></span> | <span data-ttu-id="938aa-118">장치 요약(현재 일)</span><span class="sxs-lookup"><span data-stu-id="938aa-118">Device summary (current day)</span></span>
 
 
## <a name="device-trends"></a><span data-ttu-id="938aa-119">디바이스 추세</span><span class="sxs-lookup"><span data-stu-id="938aa-119">Device trends</span></span> 
<span data-ttu-id="938aa-120">기본적으로 장치 추세는 마지막 전체 일에 끝나는 30일 기간의 장치 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-120">By default, the device trends displays device information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="938aa-121">조직에서 발생하는 추세에 대한 더 나은 관점을 얻기 위해 표시된 기간을 조정하여 보고 기간을 미세 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-121">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="938aa-122">기간을 조정하려면 드롭다운 옵션에서 시간 범위를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-122">To adjust the time period, select a time range from the drop-down options:</span></span>
 
- <span data-ttu-id="938aa-123">30일</span><span class="sxs-lookup"><span data-stu-id="938aa-123">30 days</span></span>
- <span data-ttu-id="938aa-124">3개월</span><span class="sxs-lookup"><span data-stu-id="938aa-124">3 months</span></span>
- <span data-ttu-id="938aa-125">6개월</span><span class="sxs-lookup"><span data-stu-id="938aa-125">6 months</span></span>
- <span data-ttu-id="938aa-126">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="938aa-126">Custom</span></span>

>[!NOTE]
><span data-ttu-id="938aa-127">이러한 필터는 장치 추세 섹션에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-127">These filters are only applied on the device trends section.</span></span> <span data-ttu-id="938aa-128">장치 요약 섹션에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-128">It doesn't affect the device summary section.</span></span>

## <a name="device-summary"></a><span data-ttu-id="938aa-129">장치 요약</span><span class="sxs-lookup"><span data-stu-id="938aa-129">Device summary</span></span> 
<span data-ttu-id="938aa-130">장치 추세는 추세 장치 정보를 표시하는 반면, 장치 요약에는 현재 일자까지의 장치 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-130">While the devices trends shows trending device information, the device summary shows device information scoped to the current day.</span></span> 

>[!NOTE]
><span data-ttu-id="938aa-131">요약 섹션에 반영된 데이터는 현재 날짜 이전 180일로 범위가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-131">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="938aa-132">예를 들어 오늘 날짜가 2019년 3월 27일인 경우 요약 섹션의 데이터에는 2018년 9월 28일에서 2019년 3월 27일까지의 숫자가 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-132">For example if today's date is March 27, 2019, the data on the summary section will reflect numbers starting from September 28, 2018 to March 27, 2019.</span></span><br>
> <span data-ttu-id="938aa-133">추세 섹션에 적용된 필터는 요약 섹션에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-133">The filter applied on the trends section is not applied on the summary section.</span></span> 
 
<span data-ttu-id="938aa-134">장치 추세 섹션에서는 해당 필터가 적용된 장치 목록으로 드릴다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-134">The device trends section allows you to drill down to the devices list with the corresponding filter applied to it.</span></span> <span data-ttu-id="938aa-135">예를 들어 센서 상태 카드에서 비활성 막대를 클릭하면 센서 상태가 비활성 상태인 장치만 표시하는 결과가 있는 장치 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-135">For example, clicking on the Inactive bar in the Sensor health state card will bring you the devices list with results showing only devices whose sensor status is inactive.</span></span> 
 
 
 
## <a name="device-attributes"></a><span data-ttu-id="938aa-136">장치 특성</span><span class="sxs-lookup"><span data-stu-id="938aa-136">Device attributes</span></span>
<span data-ttu-id="938aa-137">이 보고서는 다음과 같은 장치 특성을 표시하는 카드로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-137">The report is made up of cards that display the following device attributes:</span></span>
 
- <span data-ttu-id="938aa-138">**상태**: 장치의 센서 상태 정보를 표시하여 활성 상태, 통신 장애가 발생하거나, 비활성 상태 또는 센서 데이터가 없는 경우 집계된 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-138">**Health state**: shows information about the sensor state on devices, providing an aggregated view of devices that are active, experiencing impaired communications, inactive, or where no sensor data is seen.</span></span>
  
- <span data-ttu-id="938aa-139">**활성 Windows 10** 장치의 바이러스 백신 상태: 장치 수와 Microsoft Defender 바이러스 백신의 상태를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="938aa-139">**Antivirus status for active Windows 10 devices**: shows the number of devices and status of Microsoft Defender Antivirus.</span></span>
    
- <span data-ttu-id="938aa-140">**OS 플랫폼**: 조직 내에 있는 OS 플랫폼의 배포를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-140">**OS platforms**: shows the distribution of OS platforms that exists within your organization.</span></span> 
 
- <span data-ttu-id="938aa-141">**Windows 10 버전:** 조직에서 Windows 10 장치 및 해당 버전의 배포를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="938aa-141">**Windows 10 versions**: shows the distribution of Windows 10 devices and their versions in your organization.</span></span>
 
 
 
## <a name="filter-data"></a><span data-ttu-id="938aa-142">데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="938aa-142">Filter data</span></span>
 
<span data-ttu-id="938aa-143">제공된 필터를 사용하여 특정 특성의 장치를 포함하거나 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-143">Use the provided filters to include or exclude devices with certain attributes.</span></span>

<span data-ttu-id="938aa-144">장치 특성에서 적용할 여러 필터를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-144">You can select multiple filters to apply from the device attributes.</span></span> 
 
>[!NOTE]
><span data-ttu-id="938aa-145">이러한 필터는 **보고서의 모든** 카드에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-145">These filters apply to **all** the cards in the report.</span></span>
 
<span data-ttu-id="938aa-146">예를 들어 활성 센서 상태의 Windows 10 장치에 대한 데이터를 표시하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-146">For example, to show data about Windows 10 devices with Active sensor health state:</span></span>
 
1. <span data-ttu-id="938aa-147">필터에서 > 활성 상태인 > **상태입니다.**</span><span class="sxs-lookup"><span data-stu-id="938aa-147">Under **Filters > Sensor health state > Active**.</span></span>
2. <span data-ttu-id="938aa-148">그런 다음 **Windows 10에서 OS > 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="938aa-148">Then select **OS platforms > Windows 10**.</span></span>
3. <span data-ttu-id="938aa-149">**적용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="938aa-149">Select **Apply**.</span></span>


## <a name="related-topic"></a><span data-ttu-id="938aa-150">관련 항목</span><span class="sxs-lookup"><span data-stu-id="938aa-150">Related topic</span></span>
- [<span data-ttu-id="938aa-151">위협 방지 보고서</span><span class="sxs-lookup"><span data-stu-id="938aa-151">Threat protection report</span></span>](threat-protection-reports.md)
