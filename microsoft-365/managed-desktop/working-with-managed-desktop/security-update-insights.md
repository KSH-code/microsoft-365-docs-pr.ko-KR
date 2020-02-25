---
title: Windows 보안 업데이트 insights
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 600491fbdd70315385587eb8cb443a1696c3bee6
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42257833"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="9bac2-103">Windows 보안 업데이트 insights</span><span class="sxs-lookup"><span data-stu-id="9bac2-103">Windows security update insights</span></span>
<span data-ttu-id="9bac2-104">이 보기에서는 Microsoft Managed Desktop 장치에 대 한 보안 업데이트 상태에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="9bac2-105">사용 현황 데이터를 보려면 <strong>Windows 보안 업데이트</strong> 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![Windows 보안 업데이트 창: 왼쪽 열에 표시 되는 장치 상태 및 업데이트 버전의 막대 그래프, 센터 열에서 시간이 지남에 따라 배포 진행률을 업데이트 하 고, 배포 그룹별 활성 장치 비율 및 95% 배포에 도달 하는 데 소요 되는 일 수를 표시 합니다. 오른쪽 열의 대상입니다.](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="9bac2-107">장치 상태</span><span class="sxs-lookup"><span data-stu-id="9bac2-107">Device status</span></span>

<span data-ttu-id="9bac2-108">Windows 업데이트를 통해 장치를 업데이트 하려면 해당 장치가 인터넷에 연결 되어 있어야 하 고, 최소 6 시간 동안 최대 절전 상태가 아니어야 하며,이 중 두 가지는 연속적 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="9bac2-109">장치가 최대 절전 모드와 연결 되어 있지 않으면 "사용 중인 것으로 간주 됩니다."</span><span class="sxs-lookup"><span data-stu-id="9bac2-109">As long as a device is connected and not hibernating, it's considered to be "in use."</span></span> <span data-ttu-id="9bac2-110">이러한 요구 사항을 충족 하지 않는 장치가 업데이트 될 수 있지만, 이러한 장치를 충족 하는 장치를 업데이트 하는 것이 가장 높습니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-110">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="9bac2-111">다음 용어로 Windows Update 컨텍스트에서 장치 활동을 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-111">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="9bac2-112"><strong>활성 상태:</strong> 최신 보안 업데이트 릴리스에 대 한 최소 사용 조건 (6 시간, 두 개 연속)을 충족 하 고 최소 5 일 마다 Microsoft Intune을 체크 인 한 장치</span><span class="sxs-lookup"><span data-stu-id="9bac2-112"><strong>Active:</strong> Devices that have met the minimum usage criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="9bac2-113"><strong>동기화 됨:</strong> 지난 28 일 이내에 Intune을 사용 하 여 체크 인 한 장치</span><span class="sxs-lookup"><span data-stu-id="9bac2-113"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="9bac2-114"><strong>동기화</strong> <i>되지 않음</i> -지난 28 일 동안 Intune을 사용 하 여 체크 인하지 않은 장치</span><span class="sxs-lookup"><span data-stu-id="9bac2-114"><strong>Out of sync</strong> – Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="9bac2-115">업데이트 버전 상태</span><span class="sxs-lookup"><span data-stu-id="9bac2-115">Update version status</span></span>

<span data-ttu-id="9bac2-116">Microsoft는 해당 월의 두 번째 화요일 마다 보안 업데이트를 릴리스 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-116">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="9bac2-117">각 릴리스는 알려진 보안 취약성에 대 한 중요 업데이트를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-117">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="9bac2-118">Microsoft Managed Desktop은 해당 관리 장치의 95%가 매달 사용 가능한 최신 보안 업데이트로 업데이트 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-118">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="9bac2-119">새 위협 요소를 urgently 위해 보안 업데이트가 다른 시간에 출시 되는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-119">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="9bac2-120">Microsoft Managed Desktop은 이러한 업데이트를 비슷한 방식으로 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-120">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="9bac2-121">보안 업데이트 버전의 상태는 다음과 같은 용어로 분류 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-121">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="9bac2-122"><strong>현재:</strong> 이번 달에 출시 된 업데이트를 실행 하는 장치</span><span class="sxs-lookup"><span data-stu-id="9bac2-122"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="9bac2-123"><strong>이전 작업:</strong> 이전 달에 출시 된 업데이트를 실행 하는 장치</span><span class="sxs-lookup"><span data-stu-id="9bac2-123"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="9bac2-124"><strong>이전 버전:</strong> 이전 달 이전에 릴리스된 보안 업데이트를 실행 하는 장치</span><span class="sxs-lookup"><span data-stu-id="9bac2-124"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="9bac2-125"><strong>오래</strong> 된 범주에서 일부 장치를 확인 해야 하는 경우--크거나 커지는 모집단은 Microsoft Managed Desktop에 보고 해야 하는 문제를 파악 하 여 조사를 수행할 수 있다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-125">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="9bac2-126">배포 진행률</span><span class="sxs-lookup"><span data-stu-id="9bac2-126">Deployment progress</span></span>

<span data-ttu-id="9bac2-127">각 보안 업데이트 릴리스 주기가 시작 될 때 Microsoft Managed Desktop은 장치 채우기에 대 한 스냅숏을 만들고 해당 모집단의 95%로 해당 배포 대상을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-127">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="9bac2-128"><strong>배포 진행률</strong> 영역에는 업데이트 배포가 각 릴리스에 대해이 목표를 충족 하는 정도를 추적 하 여 매일 업데이트 되는 역사적 추세를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-128">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="9bac2-129">이 그래프에는 활성 상태인 장치만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-129">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="9bac2-130">오른쪽 상단의 드롭다운 메뉴를 사용 하 여 이전 업데이트 주기에 대해이 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-130">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="9bac2-131">이 메뉴에서 선택한 기간은 전체 페이지에 있는 모든 정보에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-131">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="9bac2-132"><strong>배포 그룹별 업데이트 된 활성 장치</strong> 영역은 각 Microsoft 관리 되는 데스크톱 배포 그룹에 대 한 업데이트 설치의 진행률을 표시 하는 다양 한 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-132">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="9bac2-133"><strong>대상에 도달 하</strong> 는 데 소요 되는 날짜 영역에는 현재 보안 업데이트를 사용 하 여 업데이트 되는 총 장치 수의 95%가 발생 한 시간이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-133">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="9bac2-134">배포를 진행 하는 동안이 영역에는 선택한 업데이트에 대 한 95% 대상이 도달할 때까지 <strong>업데이트를 계속</strong> 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-134">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="9bac2-135">장치 세부 정보 영역</span><span class="sxs-lookup"><span data-stu-id="9bac2-135">Device details area</span></span>

<span data-ttu-id="9bac2-136">대시보드의 아래쪽에는 [장치 상태](#device-status) 및 [업데이트 버전 상태](#update-version-status)를 포함 하 여 장치에 대 한 자세한 정보가 표시 되는 표가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-136">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="9bac2-137">이 목록을 검색 하거나 나열 된 값으로 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bac2-137">You can search this list or filter it by any listed value.</span></span>


![장치 이름, 할당 된 사용자, 장치 상태, 업데이트 버전, 운영 체제 버전 및 장치를 마지막으로 동기화 한 날짜에 대 한 열이 표시 되는 디바이스 정보 테이블](../../media/security-update-insights-device-table-sterile.png)