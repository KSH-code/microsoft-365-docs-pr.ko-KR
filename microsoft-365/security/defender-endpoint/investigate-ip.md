---
title: 경고와 연결된 IP 주소 조사
description: 조사 옵션을 사용하여 장치와 외부 IP 주소 간의 통신을 검사합니다.
keywords: 조사, 조사, IP 주소, 경고, 끝점용 Microsoft Defender, 외부 IP
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: cb95deb890b52f0f5fde26a3a193181713b8ae5f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933832"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="77bbd-104">끝점 경고에 대한 Microsoft Defender와 연결된 IP 주소 조사</span><span class="sxs-lookup"><span data-stu-id="77bbd-104">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="77bbd-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="77bbd-105">**Applies to:**</span></span>
- [<span data-ttu-id="77bbd-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="77bbd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="77bbd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="77bbd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="77bbd-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="77bbd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="77bbd-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="77bbd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="77bbd-110">장치와 외부 IP(인터넷 프로토콜) 주소 간의 통신을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="77bbd-110">Examine possible communication between your devices and external internet protocol (IP) addresses.</span></span>

<span data-ttu-id="77bbd-111">C2(명령 및 제어) 서버와 같은 의심스러우거나 알려진 악성 IP 주소와 통신한 조직의 모든 장치를 식별하면 잠재적인 위반 범위, 관련 파일 및 감염된 장치를 확인하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77bbd-111">Identifying all devices in the organization that communicated with a suspected or known malicious IP address, such as Command and Control (C2) servers, helps determine the potential scope of breach, associated files, and infected devices.</span></span>

<span data-ttu-id="77bbd-112">IP 주소 보기의 다음 섹션에서 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77bbd-112">You can find information from the following sections in the IP address view:</span></span>

- <span data-ttu-id="77bbd-113">전 세계 IP</span><span class="sxs-lookup"><span data-stu-id="77bbd-113">IP worldwide</span></span>
- <span data-ttu-id="77bbd-114">역방향 DNS 이름</span><span class="sxs-lookup"><span data-stu-id="77bbd-114">Reverse DNS names</span></span>
- <span data-ttu-id="77bbd-115">이 IP와 관련된 알림</span><span class="sxs-lookup"><span data-stu-id="77bbd-115">Alerts related to this IP</span></span>
- <span data-ttu-id="77bbd-116">조직의 IP</span><span class="sxs-lookup"><span data-stu-id="77bbd-116">IP in organization</span></span>
- <span data-ttu-id="77bbd-117">보전</span><span class="sxs-lookup"><span data-stu-id="77bbd-117">Prevalence</span></span>

## <a name="ip-worldwide-and-reverse-dns-names"></a><span data-ttu-id="77bbd-118">IP Worldwide 및 Reverse DNS names(IP Worldwide 및 역방향 DNS 이름)</span><span class="sxs-lookup"><span data-stu-id="77bbd-118">IP Worldwide and Reverse DNS names</span></span>

<span data-ttu-id="77bbd-119">IP 주소 세부 정보 섹션에는 해당 ASN 및 역방향 DNS 이름과 같은 IP 주소의 특성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77bbd-119">The IP address details section shows attributes of the IP address such as its ASN and its Reverse DNS names.</span></span>

## <a name="alerts-related-to-this-ip"></a><span data-ttu-id="77bbd-120">이 IP와 관련된 알림</span><span class="sxs-lookup"><span data-stu-id="77bbd-120">Alerts related to this IP</span></span>

<span data-ttu-id="77bbd-121">이 IP와 관련된 알림 **섹션에서는 IP와** 연결된 경고 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="77bbd-121">The **Alerts related to this IP** section provides a list of alerts that are associated with the IP.</span></span>

## <a name="ip-in-organization"></a><span data-ttu-id="77bbd-122">조직의 IP</span><span class="sxs-lookup"><span data-stu-id="77bbd-122">IP in organization</span></span>

<span data-ttu-id="77bbd-123">조직의 **IP 섹션에서는** 조직의 IP 주소 보전에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="77bbd-123">The **IP in organization** section provides details on the prevalence of the IP address in the organization.</span></span>

## <a name="prevalence"></a><span data-ttu-id="77bbd-124">보전</span><span class="sxs-lookup"><span data-stu-id="77bbd-124">Prevalence</span></span>

<span data-ttu-id="77bbd-125">**Prevalence 섹션에는** 이 IP 주소에 연결된 장치 수와 IP가 처음 및 마지막으로 확인된 때가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77bbd-125">The **Prevalence** section displays how many devices have connected to this IP address, and when the IP was first and last seen.</span></span> <span data-ttu-id="77bbd-126">이 섹션의 결과는 기간에 따라 필터링할 수 있습니다. 기본 기간은 30일입니다.</span><span class="sxs-lookup"><span data-stu-id="77bbd-126">You can filter the results of this section by time period; the default period is 30 days.</span></span>

## <a name="most-recent-observed-devices-with-ip"></a><span data-ttu-id="77bbd-127">IP가 있는 가장 최근에 관찰된 장치</span><span class="sxs-lookup"><span data-stu-id="77bbd-127">Most recent observed devices with IP</span></span>

<span data-ttu-id="77bbd-128">IP가 **있는** 가장 최근에 관찰된 디바이스 섹션에서는 IP 주소에서 관찰된 이벤트 및 관련 경고에 대한 연도 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="77bbd-128">The **Most recent observed devices** with IP section provides a chronological view on the events and associated alerts that were observed on the IP address.</span></span>

<span data-ttu-id="77bbd-129">**외부 IP 조사:**</span><span class="sxs-lookup"><span data-stu-id="77bbd-129">**Investigate an external IP:**</span></span>

1. <span data-ttu-id="77bbd-130">검색 표시줄 **드롭다운** 메뉴에서 **IP를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77bbd-130">Select **IP** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="77bbd-131">검색 필드에 IP 주소를 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="77bbd-131">Enter the IP address in the **Search** field.</span></span>
3. <span data-ttu-id="77bbd-132">검색 아이콘을 클릭하거나 Enter를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="77bbd-132">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="77bbd-133">등록 세부 정보(사용 가능한 경우), 역방향 IP(예: 도메인), 이 IP 주소와 통신한 조직의 장치 보류(선택 가능한 기간 동안) 및 이 IP 주소와 통신하는 것으로 관찰된 조직의 장치 등 IP 주소에 대한 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77bbd-133">Details about the IP address are displayed, including: registration details (if available), reverse IPs (for example, domains), prevalence of devices in the organization that communicated with this IP Address (during selectable time period), and the devices in the organization that were observed communicating with this IP address.</span></span>

> [!NOTE]
> <span data-ttu-id="77bbd-134">검색 결과는 조직의 장치와 통신하는 것으로 관찰된 IP 주소에 한해 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="77bbd-134">Search results will only be returned for IP addresses observed in communication with devices in the organization.</span></span>

<span data-ttu-id="77bbd-135">검색 필터를 사용하여 검색 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="77bbd-135">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="77bbd-136">타임라인 검색 상자를 사용하여 IP 주소와 통신하는 것으로 관찰된 조직의 모든 장치, 통신과 연결된 파일 및 마지막으로 관찰된 날짜의 표시 결과를 필터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77bbd-136">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the IP address, the file associated with the communication and the last date observed.</span></span>

<span data-ttu-id="77bbd-137">장치 이름을 클릭하면 보고된 경고, 동작 및 이벤트를 계속 조사할 수 있는 디바이스 보기로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="77bbd-137">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="77bbd-138">관련 항목</span><span class="sxs-lookup"><span data-stu-id="77bbd-138">Related topics</span></span>

- [<span data-ttu-id="77bbd-139">끝점 경고 큐에 대한 Microsoft Defender 보기 및 구성</span><span class="sxs-lookup"><span data-stu-id="77bbd-139">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="77bbd-140">끝점 경고에 대한 Microsoft Defender 관리</span><span class="sxs-lookup"><span data-stu-id="77bbd-140">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="77bbd-141">끝점 경고에 대한 Microsoft Defender 조사</span><span class="sxs-lookup"><span data-stu-id="77bbd-141">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="77bbd-142">끝점 경고에 대한 Microsoft Defender와 관련된 파일 조사</span><span class="sxs-lookup"><span data-stu-id="77bbd-142">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="77bbd-143">Microsoft Defender for Endpoint Devices 목록에서 장치 조사</span><span class="sxs-lookup"><span data-stu-id="77bbd-143">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="77bbd-144">끝점 경고에 대한 Microsoft Defender와 연결된 도메인 조사</span><span class="sxs-lookup"><span data-stu-id="77bbd-144">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="77bbd-145">끝점용 Microsoft Defender에서 사용자 계정 조사</span><span class="sxs-lookup"><span data-stu-id="77bbd-145">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
