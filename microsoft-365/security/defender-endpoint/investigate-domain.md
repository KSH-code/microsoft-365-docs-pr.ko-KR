---
title: 끝점 도메인에 대한 Microsoft Defender 조사
description: 조사 옵션을 사용하여 장치와 서버가 악성 도메인과 통신하고 있는지 볼 수 있습니다.
keywords: 도메인 조사, 도메인, 악성 도메인, Microsoft Defender atp, 경고, URL
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
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 3d4520c805332bac41746a39bb8b668dbfb1a570
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587494"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="eed68-104">끝점 경고에 대한 Microsoft Defender와 연결된 도메인 조사</span><span class="sxs-lookup"><span data-stu-id="eed68-104">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="eed68-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="eed68-105">**Applies to:**</span></span>
- <span data-ttu-id="eed68-106">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="eed68-106">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="eed68-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eed68-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="eed68-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="eed68-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="eed68-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatedomain-abovefoldlink) 

<span data-ttu-id="eed68-110">도메인을 조사하여 엔터프라이즈 네트워크의 장치와 서버가 알려진 악성 도메인과 통신하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-110">Investigate a domain to see if devices and servers in your enterprise network have been communicating with a known malicious domain.</span></span>

<span data-ttu-id="eed68-111">검색 기능을 사용하여 또는 장치 타임라인에서 도메인 링크를 클릭하여 도메인을 **조사할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="eed68-111">You can investigate a domain by using the search feature or by clicking on a domain link from the **Device timeline**.</span></span>

<span data-ttu-id="eed68-112">URL 보기에서 다음 섹션의 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-112">You can see information from the following sections in the URL view:</span></span>

- <span data-ttu-id="eed68-113">URL 세부 정보, 연락처, 이름 서비스</span><span class="sxs-lookup"><span data-stu-id="eed68-113">URL details, Contacts, Nameservers</span></span>
- <span data-ttu-id="eed68-114">이 URL과 관련된 알림</span><span class="sxs-lookup"><span data-stu-id="eed68-114">Alerts related to this URL</span></span> 
- <span data-ttu-id="eed68-115">조직의 URL</span><span class="sxs-lookup"><span data-stu-id="eed68-115">URL in organization</span></span>
- <span data-ttu-id="eed68-116">URL이 있는 가장 최근에 관찰된 장치</span><span class="sxs-lookup"><span data-stu-id="eed68-116">Most recent observed devices with URL</span></span>

## <a name="url-worldwide"></a><span data-ttu-id="eed68-117">전 세계 URL</span><span class="sxs-lookup"><span data-stu-id="eed68-117">URL worldwide</span></span>

<span data-ttu-id="eed68-118">**URL Worldwide** 섹션에는 URL, Whois의 추가 세부 정보 링크, 관련된 오픈 인시던트 수 및 활성 경고 수가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-118">The **URL Worldwide** section lists the URL, a link to further details at Whois, the number of related open incidents, and the number of active alerts.</span></span>

## <a name="incident"></a><span data-ttu-id="eed68-119">인시던트</span><span class="sxs-lookup"><span data-stu-id="eed68-119">Incident</span></span>

<span data-ttu-id="eed68-120">**인시던트** 카드에는 지난 180일 동안의 인시던트에 있는 모든 활성 경고의 막대 차트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-120">The **Incident** card displays a bar chart of all active alerts in incidents over the past 180 days.</span></span>

## <a name="prevalence"></a><span data-ttu-id="eed68-121">보전</span><span class="sxs-lookup"><span data-stu-id="eed68-121">Prevalence</span></span>

<span data-ttu-id="eed68-122">**Prevalence** 카드는 지정된 기간 동안 조직 내의 URL 보전에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-122">The **Prevalence** card provides details on the prevalence of the URL within the organization, over a specified period of time.</span></span>

<span data-ttu-id="eed68-123">기본 기간이 지난 30일이지만 카드 모서리에서 아래쪽을 가리는 화살표를 선택하여 범위를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-123">Although the default time period is the past 30 days, you can customize the range by selecting the downward-pointing arrow in the corner of the card.</span></span> <span data-ttu-id="eed68-124">사용 가능한 가장 짧은 범위는 지난 날의 보편적으로 사용 가능하고 가장 긴 범위는 지난 6개월 동안의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-124">The shortest range available is for prevalence over the past day, while the longest range is over the past 6 months.</span></span>

## <a name="alerts"></a><span data-ttu-id="eed68-125">경고</span><span class="sxs-lookup"><span data-stu-id="eed68-125">Alerts</span></span>

<span data-ttu-id="eed68-126">경고 **탭은** URL과 연결된 경고 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-126">The **Alerts** tab provides a list of alerts that are associated with the URL.</span></span> <span data-ttu-id="eed68-127">여기에 표시된 표는 경고 큐 화면에 표시되는 필터링된 버전의 경고로, 도메인과 관련된 경고, 심각도, 상태, 관련 인시던트, 분류, 조사 상태 등만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-127">The table shown here is a filtered version of the alerts visible on the Alert queue screen, showing only alerts associated with the domain, their severity, status, the associated incident, classification, investigation state, and more.</span></span>

<span data-ttu-id="eed68-128">알림 탭을 조정하여 열 머리더 위에 있는 작업  메뉴에서 열 사용자 지정을 선택하여 더 많은 정보를 표시하거나 더 적게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-128">The Alerts tab can be adjusted to show more or less information, by selecting **Customize columns** from the action menu above the column headers.</span></span> <span data-ttu-id="eed68-129">동일한 메뉴에서 페이지당 항목을 선택하여 표시되는 항목 수를 **조정할** 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-129">The number of items displayed can also be adjusted, by selecting **items per page** on the same menu.</span></span>

## <a name="observed-in-organization"></a><span data-ttu-id="eed68-130">조직에서 관찰</span><span class="sxs-lookup"><span data-stu-id="eed68-130">Observed in organization</span></span>

<span data-ttu-id="eed68-131">조직에서 **관찰된 탭에서는** URL에서 관찰된 이벤트 및 관련 경고에 대한 연대기 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-131">The **Observed in organization** tab provides a chronological view on the events and associated alerts that were observed on the URL.</span></span> <span data-ttu-id="eed68-132">이 탭에는 시간 표시 막대 및 사용자 지정 가능한 테이블 목록 이벤트 세부 정보(예: 시간, 장치 및 진행된 일)에 대한 간략한 설명이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-132">This tab includes a timeline and a customizable table listing event details, such as the time, device, and a brief description of what happened.</span></span> 

<span data-ttu-id="eed68-133">날짜를 표 헤더 위에 있는 텍스트 필드에 입력하여 다양한 기간의 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-133">You can view events from different periods of time by entering the dates into the text fields above the table headers.</span></span> <span data-ttu-id="eed68-134">시간 표시 막대의 다른 영역을 선택하여 시간 범위를 사용자 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-134">You can also customize the time range by selecting different areas of the timeline.</span></span>

<span data-ttu-id="eed68-135">**도메인 조사:**</span><span class="sxs-lookup"><span data-stu-id="eed68-135">**Investigate a domain:**</span></span>

1. <span data-ttu-id="eed68-136">검색 표시줄 **드롭다운** 메뉴에서 **URL을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-136">Select **URL** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="eed68-137">검색 필드에 **URL을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="eed68-137">Enter the URL in the **Search** field.</span></span>
3. <span data-ttu-id="eed68-138">검색 아이콘을 클릭하거나 Enter를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="eed68-138">Click the search icon   or press **Enter**.</span></span> <span data-ttu-id="eed68-139">URL에 대한 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-139">Details about the URL are displayed.</span></span> <span data-ttu-id="eed68-140">참고: 검색 결과는 조직의 장치와의 통신에서 관찰된 URL에 한해 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-140">Note: search results will only be returned for URLs observed in communications from devices in the organization.</span></span>
4. <span data-ttu-id="eed68-141">검색 필터를 사용하여 검색 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-141">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="eed68-142">타임라인 검색 상자를 사용하여 URL과 통신하는 것으로 관찰된 조직의 모든 장치, 통신과 연결된 파일 및 마지막으로 관찰된 날짜를 필터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-142">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the URL, the file associated with the communication and the last date observed.</span></span>
5. <span data-ttu-id="eed68-143">장치 이름을 클릭하면 보고된 경고, 동작 및 이벤트를 계속 조사할 수 있는 디바이스 보기로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="eed68-143">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="eed68-144">관련 항목</span><span class="sxs-lookup"><span data-stu-id="eed68-144">Related topics</span></span>
- [<span data-ttu-id="eed68-145">끝점 경고 큐에 대한 Microsoft Defender 보기 및 구성</span><span class="sxs-lookup"><span data-stu-id="eed68-145">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="eed68-146">끝점 경고에 대한 Microsoft Defender 관리</span><span class="sxs-lookup"><span data-stu-id="eed68-146">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="eed68-147">끝점 경고에 대한 Microsoft Defender 조사</span><span class="sxs-lookup"><span data-stu-id="eed68-147">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="eed68-148">끝점 경고에 대한 Microsoft Defender와 관련된 파일 조사</span><span class="sxs-lookup"><span data-stu-id="eed68-148">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="eed68-149">Microsoft Defender for Endpoint Devices 목록에서 장치 조사</span><span class="sxs-lookup"><span data-stu-id="eed68-149">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="eed68-150">끝점 경고에 대한 Microsoft Defender와 연결된 IP 주소 조사</span><span class="sxs-lookup"><span data-stu-id="eed68-150">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="eed68-151">끝점용 Microsoft Defender에서 사용자 계정 조사</span><span class="sxs-lookup"><span data-stu-id="eed68-151">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
