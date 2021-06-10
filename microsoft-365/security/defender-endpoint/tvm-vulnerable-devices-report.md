---
title: 취약한 장치 보고서 - 위협 및 취약성 관리
description: 취약한 장치 추세 및 현재 통계를 보여주는 보고서입니다. 목표는 장치 노출의 숨과 범위를 이해하는 데 있습니다.
keywords: Endpoint-tvm 취약 디바이스용 Microsoft Defender, 끝점용 Microsoft Defender, tvm, 위협 & 노출 감소, 위협 및 취약성 감소, 보안 구성 모니터링
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 355561936642b1fa38228bfa07ad59269c48d817
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245483"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a><span data-ttu-id="4a28a-105">취약한 장치 보고서 - 위협 및 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="4a28a-105">Vulnerable devices report - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4a28a-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="4a28a-106">**Applies to:**</span></span>

- [<span data-ttu-id="4a28a-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4a28a-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="4a28a-108">위협 및 취약성 관리</span><span class="sxs-lookup"><span data-stu-id="4a28a-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="4a28a-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4a28a-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="4a28a-110">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="4a28a-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4a28a-111">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4a28a-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="4a28a-112">이 보고서에는 취약한 장치 추세 및 현재 통계가 있는 그래프 및 막대 차트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a28a-112">The report shows graphs and bar charts with vulnerable device trends and current statistics.</span></span> <span data-ttu-id="4a28a-113">목표는 장치 노출의 숨과 범위를 이해하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a28a-113">The goal is for you to understand the breath and scope of your device exposure.</span></span>

<span data-ttu-id="4a28a-114">보고서 및 취약한 Microsoft Defender 보안 센터 **보고서로** > 액세스</span><span class="sxs-lookup"><span data-stu-id="4a28a-114">Access the report in the Microsoft Defender Security Center by going to **Reports > Vulnerable devices**</span></span>

<span data-ttu-id="4a28a-115">두 개의 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a28a-115">There are two columns:</span></span>

- <span data-ttu-id="4a28a-116">추세(시간 경과에 따라)</span><span class="sxs-lookup"><span data-stu-id="4a28a-116">Trends (over time).</span></span> <span data-ttu-id="4a28a-117">지난 30일, 3개월, 6개월 또는 사용자 지정 날짜 범위를 표시 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a28a-117">Can show the past 30 days, 3 months, 6 months, or a custom date range.</span></span>
- <span data-ttu-id="4a28a-118">오늘(현재 정보)</span><span class="sxs-lookup"><span data-stu-id="4a28a-118">Today (current information)</span></span>

<span data-ttu-id="4a28a-119">**필터:** 취약성 심각도 수준, 악용 가용성, 취약성 사용 시간, 운영 체제 플랫폼, Windows 10 또는 장치 그룹을별로 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a28a-119">**Filter**: You can filter the data by vulnerability severity levels, exploit availability, vulnerability age, operating system platform, Windows 10 version, or device group.</span></span>

<span data-ttu-id="4a28a-120">**드릴다운:** 추가 탐색할 인사이트가 있는 경우 관련 막대 차트를 선택하여 장치 인벤토리 페이지에서 필터링된 장치 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4a28a-120">**Drill down**: If there is an insight you want to explore further, select the relevant bar chart to view a filtered list of devices in the Device inventory page.</span></span> <span data-ttu-id="4a28a-121">이 목록에서 목록을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a28a-121">From there, you can export the list.</span></span>

## <a name="severity-level-graphs"></a><span data-ttu-id="4a28a-122">심각도 수준 그래프</span><span class="sxs-lookup"><span data-stu-id="4a28a-122">Severity level graphs</span></span>

<span data-ttu-id="4a28a-123">각 장치는 해당 디바이스에서 발견되는 가장 심각한 취약점에 따라 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a28a-123">Each device is counted only once according to the most severe vulnerability found on that device.</span></span>

![현재 장치 취약성 심각도 수준의 그래프 1개와 시간의 따라 수준을 표시하는 그래프 1개](images/tvm-report-severity.png)

## <a name="exploit-availability-graphs"></a><span data-ttu-id="4a28a-125">Exploit availability graphs</span><span class="sxs-lookup"><span data-stu-id="4a28a-125">Exploit availability graphs</span></span>

<span data-ttu-id="4a28a-126">각 장치는 알려진 가장 높은 수준의 악용에 따라 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a28a-126">Each device is counted only once based on the highest level of known exploit.</span></span>

![현재 장치 악용 가용성의 그래프 하나와 시간의 따라 가용성을 보여 주는 그래프 한 개](images/tvm-report-exploit-availability.png)

## <a name="vulnerability-age-graphs"></a><span data-ttu-id="4a28a-128">취약성 연령 그래프</span><span class="sxs-lookup"><span data-stu-id="4a28a-128">Vulnerability age graphs</span></span>

<span data-ttu-id="4a28a-129">각 장치는 가장 오래된 취약점 게시 날짜에 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a28a-129">Each device is counted only once under the oldest vulnerability publication date.</span></span> <span data-ttu-id="4a28a-130">오래된 취약성은 악용 가능성이 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="4a28a-130">Older vulnerabilities have a higher chance of being exploited.</span></span>

![현재 장치 취약성 연령의 그래프 1개와 시간이 지난 기간을 보여주는 그래프 한 개.](images/tvm-report-age.png)

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a><span data-ttu-id="4a28a-132">운영 체제 플랫폼 그래프를 통해 취약한 장치</span><span class="sxs-lookup"><span data-stu-id="4a28a-132">Vulnerable devices by operating system platform graphs</span></span>

<span data-ttu-id="4a28a-133">소프트웨어 취약성으로 인해 노출되는 각 운영 체제의 장치 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4a28a-133">The number of devices on each operating system that are exposed due to software vulnerabilities.</span></span>

![운영 체제 플랫폼을 통해 현재 취약한 장치의 그래프 한 개와 시간이 지날 때 OS 플랫폼에 의해 취약한 장치를 보여주는 그래프 하나.](images/tvm-report-os.png)

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a><span data-ttu-id="4a28a-135">버전 그래프를 Windows 10 취약한 장치</span><span class="sxs-lookup"><span data-stu-id="4a28a-135">Vulnerable devices by Windows 10 version graphs</span></span>

<span data-ttu-id="4a28a-136">취약한 응용 프로그램 또는 OS로 Windows 10 각 버전에 있는 장치 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4a28a-136">The number of devices on each Windows 10 version that are exposed due to vulnerable applications or OS.</span></span>

![현재 취약한 장치의 한 그래프와 Windows 10 버전을 통해 취약한 장치를 보여 Windows 10 그래프.](images/tvm-report-version.png)

## <a name="related-topics"></a><span data-ttu-id="4a28a-138">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4a28a-138">Related topics</span></span>

- [<span data-ttu-id="4a28a-139">위협 및 취약성 관리 개요</span><span class="sxs-lookup"><span data-stu-id="4a28a-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="4a28a-140">보안 권장 사항</span><span class="sxs-lookup"><span data-stu-id="4a28a-140">Security recommendations</span></span>](tvm-security-recommendation.md)
