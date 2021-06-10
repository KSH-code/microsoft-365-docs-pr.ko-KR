---
title: Endpoint용 Microsoft Defender의 위협 방지 보고서
description: 위협 방지 보고서를 사용하여 경고 감지, 범주 및 심각도 추적
keywords: 경고 검색, 원본, 범주별 경고, 경고 심각도, 경고 분류, 결정
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
ms.openlocfilehash: d32ab04f4acda60f65316719a4607c6c9bbd6447
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688984"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="1bce8-104">Endpoint용 Microsoft Defender의 위협 방지 보고서</span><span class="sxs-lookup"><span data-stu-id="1bce8-104">Threat protection report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1bce8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="1bce8-105">**Applies to:**</span></span>
- [<span data-ttu-id="1bce8-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1bce8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1bce8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1bce8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="1bce8-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="1bce8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1bce8-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="1bce8-110">위협 방지 보고서는 조직에서 생성된 경고에 대한 높은 수준의 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-110">The threat protection report provides high-level information about alerts generated in your organization.</span></span> <span data-ttu-id="1bce8-111">이 보고서에는 검색 원본, 범주, 심각도, 상태, 분류 및 시간 경과에 대한 경고 확인을 보여주는 추세 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-111">The report includes trending information showing the detection sources, categories, severities, statuses, classifications, and determinations of alerts across time.</span></span>

<span data-ttu-id="1bce8-112">대시보드는 다음 두 섹션으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-112">The dashboard is structured into two sections:</span></span>

![위협 방지 보고서의 이미지](images/threat-protection-reports.png)

<span data-ttu-id="1bce8-114">섹션</span><span class="sxs-lookup"><span data-stu-id="1bce8-114">Section</span></span> | <span data-ttu-id="1bce8-115">설명</span><span class="sxs-lookup"><span data-stu-id="1bce8-115">Description</span></span> 
:---|:---
<span data-ttu-id="1bce8-116">1</span><span class="sxs-lookup"><span data-stu-id="1bce8-116">1</span></span> | <span data-ttu-id="1bce8-117">경고 추세</span><span class="sxs-lookup"><span data-stu-id="1bce8-117">Alerts trends</span></span>
<span data-ttu-id="1bce8-118">2</span><span class="sxs-lookup"><span data-stu-id="1bce8-118">2</span></span> | <span data-ttu-id="1bce8-119">경고 요약</span><span class="sxs-lookup"><span data-stu-id="1bce8-119">Alert summary</span></span>

## <a name="alert-trends"></a><span data-ttu-id="1bce8-120">경고 추세</span><span class="sxs-lookup"><span data-stu-id="1bce8-120">Alert trends</span></span>
<span data-ttu-id="1bce8-121">기본적으로 경고 추세는 마지막 전체 일에 끝나는 30일 기간의 경고 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-121">By default, the alert trends display alert information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="1bce8-122">조직에서 발생하는 추세에 대한 더 나은 관점을 얻기 위해 표시된 기간을 조정하여 보고 기간을 미세 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-122">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="1bce8-123">기간을 조정하려면 드롭다운 옵션에서 시간 범위를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-123">To adjust the time period, select a time range from the drop-down options:</span></span>

- <span data-ttu-id="1bce8-124">30일</span><span class="sxs-lookup"><span data-stu-id="1bce8-124">30 days</span></span>
- <span data-ttu-id="1bce8-125">3개월</span><span class="sxs-lookup"><span data-stu-id="1bce8-125">3 months</span></span>
- <span data-ttu-id="1bce8-126">6개월</span><span class="sxs-lookup"><span data-stu-id="1bce8-126">6 months</span></span>
- <span data-ttu-id="1bce8-127">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="1bce8-127">Custom</span></span>

>[!NOTE]
><span data-ttu-id="1bce8-128">이러한 필터는 경고 추세 섹션에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-128">These filters are only applied on the alert trends section.</span></span> <span data-ttu-id="1bce8-129">경고 요약 섹션에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-129">It doesn't affect the alert summary section.</span></span>


## <a name="alert-summary"></a><span data-ttu-id="1bce8-130">경고 요약</span><span class="sxs-lookup"><span data-stu-id="1bce8-130">Alert summary</span></span>
<span data-ttu-id="1bce8-131">경고 추세는 추세 경고 정보를 표시하는 반면, 경고 요약에는 현재 일자까지의 경고 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-131">While the alert trends shows trending alert information, the alert summary shows alert information scoped to the current day.</span></span>

 <span data-ttu-id="1bce8-132">경고 요약을 사용하면 해당 필터가 적용된 특정 경고 큐로 드릴다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-132">The alert summary allows you to drill down to a particular alert queue with the corresponding filter applied to it.</span></span> <span data-ttu-id="1bce8-133">예를 들어 검색 원본 카드에서 EDR 표시줄을 클릭하면 경고 큐에 알림 큐가 표시될 수 있습니다. 이 경우 검색된 검색에서 생성된 경고만 EDR 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-133">For example, clicking on the EDR bar in the Detection sources card will bring you the alerts queue with results showing only alerts generated from EDR detections.</span></span> 

>[!NOTE]
><span data-ttu-id="1bce8-134">요약 섹션에 반영된 데이터는 현재 날짜 이전 180일로 범위가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-134">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="1bce8-135">예를 들어 오늘 날짜가 2019년 11월 5일인 경우 요약 섹션의 데이터에는 2019년 5월 5일부터 2019년 11월 5일까지의 숫자가 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-135">For example if today's date is November 5, 2019, the data on the summary section will reflect numbers starting from May 5, 2019 to November 5, 2019.</span></span><br>
> <span data-ttu-id="1bce8-136">추세 섹션에 적용된 필터는 요약 섹션에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-136">The filter applied on the trends section is not applied on the summary section.</span></span> 

## <a name="alert-attributes"></a><span data-ttu-id="1bce8-137">경고 특성</span><span class="sxs-lookup"><span data-stu-id="1bce8-137">Alert attributes</span></span>
<span data-ttu-id="1bce8-138">보고서는 다음과 같은 경고 특성을 표시하는 카드로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-138">The report is made up of cards that display the following alert attributes:</span></span>

- <span data-ttu-id="1bce8-139">**검색 원본**: 경고를 트리거하기 위해 끝점용 Microsoft Defender에서 사용하는 데이터를 제공하는 센서 및 감지 기술에 대한 정보를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-139">**Detection sources**: shows information about the sensors and detection technologies that provide the data used by Microsoft Defender for Endpoint to trigger alerts.</span></span>

- <span data-ttu-id="1bce8-140">**위협 범주**: 경고를 트리거한 위협 또는 공격 활동의 유형을 표시하여 보안 작업에 대한 가능한 포커스 영역을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-140">**Threat categories**: shows the types of threat or attack activity that triggered alerts, indicating possible focus areas for your security operations.</span></span>

- <span data-ttu-id="1bce8-141">**심각도**: 경고의 심각도 수준을 표시하여 조직에 위협이 미칠 수 있는 총체적인 영향과 경고를 해결하기 위해 필요한 대응 수준을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-141">**Severity**: shows the severity level of alerts, indicating the collective potential impact of threats to your organization and the level of response needed to address them.</span></span>

- <span data-ttu-id="1bce8-142">**상태**: 수동 경고 응답의 효율성과 자동화된 수정(활성화된 경우)의 효율성을 나타내는 경고의 해결 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-142">**Status**: shows the resolution status of alerts, indicating the efficiency of your manual alert responses and of automated remediation (if enabled).</span></span> 

- <span data-ttu-id="1bce8-143">**분류 & 결정**: 해결 시 경고를 분류한 방법, 실제 위협(실제 경고) 또는 잘못된 검색(거짓 경고)으로 분류한 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-143">**Classification & determination**: shows how you have classified alerts upon resolution, whether you have classified them as actual threats (true alerts) or as incorrect detections (false alerts).</span></span> <span data-ttu-id="1bce8-144">또한 이러한 카드는 확인된 경고의 확인을 보여 주며, 발견된 실제 위협 유형 또는 잘못 감지된 합법적인 활동과 같은 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-144">These cards also show the determination of resolved alerts, providing additional insight like the types of actual threats found or the legitimate activities that were incorrectly detected.</span></span>


 

## <a name="filter-data"></a><span data-ttu-id="1bce8-145">데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="1bce8-145">Filter data</span></span>

<span data-ttu-id="1bce8-146">제공된 필터를 사용하여 특정 특성의 경고를 포함하거나 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-146">Use the provided filters to include or exclude alerts with certain attributes.</span></span>

>[!NOTE]
><span data-ttu-id="1bce8-147">이러한 필터는 **보고서의 모든** 카드에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-147">These filters apply to **all** the cards in the report.</span></span>

<span data-ttu-id="1bce8-148">예를 들어 심각도 높은 경고에 대한 데이터만 표시하는 경우:</span><span class="sxs-lookup"><span data-stu-id="1bce8-148">For example, to show data about high-severity alerts only:</span></span>

1. <span data-ttu-id="1bce8-149">필터 **> 심각도에서** 높음 **선택**</span><span class="sxs-lookup"><span data-stu-id="1bce8-149">Under **Filters > Severity**, select **High**</span></span>
2. <span data-ttu-id="1bce8-150">심각도에 있는 다른 모든 **옵션이** 선택을 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-150">Ensure that all other options under **Severity** are deselected.</span></span>
3. <span data-ttu-id="1bce8-151">**적용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce8-151">Select **Apply**.</span></span> 

## <a name="related-topic"></a><span data-ttu-id="1bce8-152">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1bce8-152">Related topic</span></span>
- [<span data-ttu-id="1bce8-153">장치 상태 및 준수 보고서</span><span class="sxs-lookup"><span data-stu-id="1bce8-153">Device health and compliance report</span></span>](machine-reports.md)
