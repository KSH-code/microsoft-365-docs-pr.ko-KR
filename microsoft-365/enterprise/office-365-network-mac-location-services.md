---
title: Microsoft 365 Network Connectivity Location Services(미리 보기)
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
description: Microsoft 365 Network Connectivity Location Services(미리 보기)
ms.openlocfilehash: f2ab872f67eca70ab2791d3ad6fe1396b009cc18
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200784"
---
# <a name="microsoft-365-network-connectivity-location-services-preview"></a><span data-ttu-id="2d178-103">Microsoft 365 Network Connectivity Location Services(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="2d178-103">Microsoft 365 Network Connectivity Location Services (preview)</span></span>

<span data-ttu-id="2d178-104">이제 Microsoft 365 관리 센터에는 Microsoft 365 테넌트에서 수집되고 테넌트의 관리자만 볼 수 있는 라이브 성능 메트릭인 **네트워크** 인사이트 및 성능 권장 사항이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d178-104">The Microsoft 365 Admin Center now shows **Network Insights and performance recommendations**, which are live performance metrics collected from your Microsoft 365 tenant and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="2d178-105">조직 네트워크 연결은 인터넷으로의 네트워크 이동 위치를 통해 사무실 위치당 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d178-105">Organizational network connectivity is designed per office location through a network egress location to the Internet.</span></span> <span data-ttu-id="2d178-106">Microsoft 365 클라이언트 연결은 해당 경로를 사용하여 인터넷을 통해 Microsoft 서비스 프런트 도어 서버를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="2d178-106">Microsoft 365 client connectivity uses that route and then across the Internet to Microsoft service front door servers.</span></span> <span data-ttu-id="2d178-107">사무실 위치를 식별하는 것은 이러한 네트워크 정보를 표시하는 데 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="2d178-107">Identifying office locations is key to being able to show these network insights.</span></span>

## <a name="location-in-network-measurements"></a><span data-ttu-id="2d178-108">네트워크 측정 위치</span><span class="sxs-lookup"><span data-stu-id="2d178-108">Location in network measurements</span></span>

<span data-ttu-id="2d178-109">조직의 관리자는 이 기능에 사용되는 네트워크 측정에 포함될 위치를 옵트인(opt in)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d178-109">An organization's administrator can opt in for location to be included in the network measurements used by this feature.</span></span> <span data-ttu-id="2d178-110">이렇게 하면 각 사무실이 있는 도시를 자동으로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d178-110">This enables auto-discovery of the city where each office is located.</span></span> <span data-ttu-id="2d178-111">위치 정보는 정확하지 않습니다. 300m로 난청되어 도시별로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d178-111">Location information is not precise and is obfuscated to 300m and categorized by city.</span></span> <span data-ttu-id="2d178-112">Windows 장치에서 위치가 캡처될 때 도구 트레이에  사용 중 위치 아이콘이 표시될 수 있으며 관리자는 이를 사용자에게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d178-112">At the time when location is captured on a Windows device it will show a **Location In-Use** icon in the tool tray and administrators may want to notify users of this.</span></span> <span data-ttu-id="2d178-113">이 처리를 통해 위치는 개인 또는 장치의 위치가 아니라 조직 사무실 위치로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d178-113">With this processing, the location is treated as the organization office location and not the location of a person or a device.</span></span> <span data-ttu-id="2d178-114">네트워크 인사이트는 검색된 사무실 위치 도시에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d178-114">Network insights can be shown at these discovered office location cities.</span></span> <span data-ttu-id="2d178-115">권장 사항이 더 정확하게 필요한 경우 관리자는 특정 사무실 위치 주소를 입력할 수 있으며 네트워크 인사이트는 대신 이러한 주소로 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d178-115">If greater accuracy of recommendations is desired, an administrator can enter specific office location addresses and the network insights will be aggregated to those instead.</span></span> <span data-ttu-id="2d178-116">Office 위치는 300미터보다 긴밀하게 집계할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d178-116">Office locations cannot be aggregated more closely than 300 meters.</span></span>

## <a name="location-in-the-microsoft-365-admin-center"></a><span data-ttu-id="2d178-117">Microsoft 365 관리 센터의 위치</span><span class="sxs-lookup"><span data-stu-id="2d178-117">Location in the Microsoft 365 Admin Center</span></span>

<span data-ttu-id="2d178-118">Microsoft 365 관리 센터에서 Bing 지도 컨트롤은 조직 사무실 위치 위치를 표시하고 선택한 사무실 위치에 대한 네트워크 경계 토폴로지 표시에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d178-118">In the Microsoft 365 Admin Center, Bing map controls are used to show where organization office locations are and to show network perimeter topology for a selected office location.</span></span> <span data-ttu-id="2d178-119">관리자가 사무실 위치에 대한 특정 주소 정보를 추가하면 Bing 지도를 사용하여 데이터를 보다 쉽게 입력할 수 있도록 주소를 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="2d178-119">When an administrator adds specific address details for office locations, Bing Maps is also used to suggest addresses to make data entry easier.</span></span>

## <a name="terms-of-use"></a><span data-ttu-id="2d178-120">사용 약관</span><span class="sxs-lookup"><span data-stu-id="2d178-120">Terms of Use</span></span>

<span data-ttu-id="2d178-121">Bing 지도를 통해 제공되는 모든 콘텐츠(지오코드 포함)는 콘텐츠가 제공되는 제품 내에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d178-121">Any content provided through Bing Maps, including geocodes, can only be used within the product through which the content is provided.</span></span> <span data-ttu-id="2d178-122">고객의 Microsoft 365 관리 센터 위치 서비스 기능 사용은 Bing 지도를 통해 지원됩니다. _Bing 지도_ 최종 사용자 사용 약관 및 사용 가능한 Microsoft 개인 정보 취급 방침의 <https://go.microsoft.com/?linkid=9710837> 관리 <https://go.microsoft.com/fwlink/?LinkID=248686.></span><span class="sxs-lookup"><span data-stu-id="2d178-122">Customer's use of the Microsoft 365 Admin Center Location Services feature, powered by Bing Maps, is governed by the _Bing Maps End User Terms of Use_ available at <https://go.microsoft.com/?linkid=9710837> and the _Microsoft Privacy Statement_ available at <https://go.microsoft.com/fwlink/?LinkID=248686.></span></span>

<span data-ttu-id="2d178-123">Bing 지도를 통해 제공되는 이 기능은 **Here 기술에서도 지원됩니다.**</span><span class="sxs-lookup"><span data-stu-id="2d178-123">This feature, provided through Bing Maps, is also supported by **Here Technologies**.</span></span> <span data-ttu-id="2d178-124">Bing 지도가 여기 기술에서 제공하는 위치 서비스를 활용하는 방식은 사용 가능한 여기 기술 _서비스_ 약관에 따라 <https://legal.here.com/en-gb/terms> 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d178-124">How Bing Maps leverages location services provided by Here Technologies is governed by the _Here Technologies Service Terms_ available at <https://legal.here.com/en-gb/terms>.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2d178-125">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2d178-125">Related topics</span></span>

[<span data-ttu-id="2d178-126">Microsoft 365 관리 센터의 네트워크 연결(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="2d178-126">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="2d178-127">Microsoft 365 네트워크 성능 인사이트(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="2d178-127">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="2d178-128">Microsoft 365 네트워크 평가(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="2d178-128">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="2d178-129">M365 관리 센터의 Microsoft 365 연결 테스트(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="2d178-129">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)
