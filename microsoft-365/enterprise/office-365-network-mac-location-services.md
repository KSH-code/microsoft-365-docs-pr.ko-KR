---
title: Microsoft 365 네트워크 연결 위치 서비스
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 네트워크 연결 위치 서비스
ms.openlocfilehash: ed78d7ba48cd9666ce1aae1af5478e3b7536e1e1
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470451"
---
# <a name="microsoft-365-network-connectivity-location-services"></a><span data-ttu-id="768db-103">Microsoft 365 네트워크 연결 위치 서비스</span><span class="sxs-lookup"><span data-stu-id="768db-103">Microsoft 365 Network Connectivity Location Services</span></span>

<span data-ttu-id="768db-104">이제 Microsoft 365 관리 센터에 네트워크 인사이트 및 성능 권장 사항인 네트워크 인사이트 및 성능 권장 사항이 표시됩니다. 이는 Microsoft 365 테넌트에서 수집한 라이브 성능 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="768db-104">The Microsoft 365 Admin Center now shows **Network Insights and performance recommendations**, which are live performance metrics that are collected from your Microsoft 365 tenant.</span></span> <span data-ttu-id="768db-105">이러한 메트릭은 테넌트의 관리 사용자만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="768db-105">These metrics can be viewed only by administrative users in your tenant.</span></span> <span data-ttu-id="768db-106">조직 네트워크 연결은 인터넷으로의 네트워크 이동 위치를 통해 사무실 위치당 설계됩니다.</span><span class="sxs-lookup"><span data-stu-id="768db-106">Organizational network connectivity is designed per office location through a network egress location to the Internet.</span></span> <span data-ttu-id="768db-107">Microsoft 365 클라이언트 연결에서는 해당 경로를 사용하여 인터넷을 통해 Microsoft 서비스 프런트 도어 서버로 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="768db-107">Microsoft 365 client connectivity uses that route and then across the Internet to Microsoft service front door servers.</span></span> <span data-ttu-id="768db-108">사무실 위치를 식별하는 것은 이러한 네트워크 정보를 표시하는 데 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="768db-108">Identifying office locations is key to being able to show these network insights.</span></span>

## <a name="location-in-network-measurements"></a><span data-ttu-id="768db-109">네트워크 측정의 위치</span><span class="sxs-lookup"><span data-stu-id="768db-109">Location in network measurements</span></span>

<span data-ttu-id="768db-110">조직의 관리자는 이 기능에 사용되는 네트워크 측정에 포함될 위치를 옵트인(opt in)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="768db-110">An organization's administrator can opt in for location to be included in the network measurements used by this feature.</span></span> <span data-ttu-id="768db-111">이렇게 하면 각 사무실이 있는 구를 자동으로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="768db-111">This enables auto-discovery of the city where each office is located.</span></span> <span data-ttu-id="768db-112">위치 정보는 정확하지 않습니다. 300m로 난청되어 도시별로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="768db-112">Location information is not precise and is obfuscated to 300m and categorized by city.</span></span> <span data-ttu-id="768db-113">위치가 Windows 디바이스에 캡처될 때 장치에 도구 트레이에 사용  중 위치 아이콘이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="768db-113">At the time when location is captured on a Windows device, the device will show a **Location In-Use** icon in the tool tray.</span></span> <span data-ttu-id="768db-114">관리자는 사용자에게 이 아이콘의 모양을 알리고 싶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="768db-114">Administrators may want to notify users of the appearance of this icon.</span></span> <span data-ttu-id="768db-115">이 처리를 통해 위치는 개인 또는 장치의 위치가 아니라 조직 사무실 위치로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="768db-115">With this processing, the location is treated as the organization office location and not the location of a person or a device.</span></span> <span data-ttu-id="768db-116">네트워크 인사이트는 검색된 사무실 위치 도시에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="768db-116">Network insights can be shown at these discovered office location cities.</span></span> <span data-ttu-id="768db-117">권장 사항에서 더 높은 정확도를 원할 경우 특정 사무실 위치 주소를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="768db-117">If you want higher accuracy in the recommendations, you can enter specific office location addresses.</span></span> <span data-ttu-id="768db-118">네트워크 인사이트는 해당 위치로 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="768db-118">The network insights will be aggregated to those locations instead.</span></span> <span data-ttu-id="768db-119">Office 위치는 300미터보다 긴밀하게 집계할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="768db-119">Office locations cannot be aggregated more closely than 300 meters.</span></span>

## <a name="location-in-the-microsoft-365-admin-center"></a><span data-ttu-id="768db-120">Microsoft 365 관리 센터의 위치</span><span class="sxs-lookup"><span data-stu-id="768db-120">Location in the Microsoft 365 Admin Center</span></span>

<span data-ttu-id="768db-121">Microsoft 365 관리 센터에서 Bing 지도 컨트롤을 사용하여 조직 사무실 위치가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="768db-121">In the Microsoft 365 Admin Center, Bing map controls are used to show where organization office locations are.</span></span> <span data-ttu-id="768db-122">컨트롤에는 선택한 사무실 위치에 대한 네트워크 경계 토폴로지도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="768db-122">The controls also show network perimeter topology for a selected office location.</span></span> <span data-ttu-id="768db-123">관리자가 사무실 위치에 대한 특정 주소 정보를 추가하면 Bing 지도 쉽게 입력할 수 있도록 주소를 제안하는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="768db-123">When an administrator adds specific address details for office locations, Bing Maps is also used to suggest addresses to make data entry easier.</span></span>

## <a name="terms-of-use"></a><span data-ttu-id="768db-124">사용 약관</span><span class="sxs-lookup"><span data-stu-id="768db-124">Terms of Use</span></span>

<span data-ttu-id="768db-125">지오코드를 Bing 지도 통해 제공되는 모든 콘텐츠는 콘텐츠가 제공되는 제품 내에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="768db-125">Any content provided through Bing Maps, including geocodes, can only be used within the product through which the content is provided.</span></span> <span data-ttu-id="768db-126">고객의 Microsoft 365 관리 센터 위치 서비스 기능의 사용은 Bing 지도 사용 약관 및 Microsoft  개인 정보 취급 방침 에서 Bing 지도 End-User 사용 약관에 <https://go.microsoft.com/?linkid=9710837> 따라 [관리됩니다.](https://go.microsoft.com/fwlink/?LinkID=248686)</span><span class="sxs-lookup"><span data-stu-id="768db-126">Customer's use of the Microsoft 365 Admin Center Location Services feature, powered by Bing Maps, is governed by the _Bing Maps End-User Terms of Use_ available at <https://go.microsoft.com/?linkid=9710837> and the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?LinkID=248686).</span></span>

<span data-ttu-id="768db-127">이 기능은 **TomTom** Bing 지도 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="768db-127">This feature, provided through Bing Maps, is also supported by **TomTom**.</span></span> <span data-ttu-id="768db-128">TomTom의 제품 및 서비스에 대한 자세한 내용은 에서 찾을 수 [https://www.tomtom.com/legal](https://www.tomtom.com/legal) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="768db-128">More information about TomTom's products and services may be found at [https://www.tomtom.com/legal](https://www.tomtom.com/legal).</span></span>

## <a name="related-topics"></a><span data-ttu-id="768db-129">관련 항목</span><span class="sxs-lookup"><span data-stu-id="768db-129">Related topics</span></span>

[<span data-ttu-id="768db-130">Microsoft 365 관리 센터의 네트워크 연결(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="768db-130">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="768db-131">Microsoft 365 네트워크 성능 인사이트(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="768db-131">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="768db-132">Microsoft 365 네트워크 평가(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="768db-132">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="768db-133">Microsoft 365 관리 센터의 Microsoft 365 연결 테스트(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="768db-133">Microsoft 365 connectivity test in the Microsoft 365 admin center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)
