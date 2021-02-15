---
title: 중국 사용자를 위한 Microsoft 365 전역 테넌트 성능 최적화
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
- m365initiative-coredeploy
search.appverid: MET150
f1.keywords:
- NOCSH
description: 이 문서에서는 글로벌 Microsoft 365 테넌트의 중국 사용자에 대한 네트워크 성능을 최적화하기 위한 지침을 제공합니다.
ms.openlocfilehash: 9b397e60b4a3b80563ed31731a6f7aa8e0bdab7f
ms.sourcegitcommit: d76a4c07f0be2938372bdfae50e0e4d523bd8e9f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456366"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a><span data-ttu-id="7fac7-103">중국 사용자를 위한 Microsoft 365 전역 테넌트 성능 최적화</span><span class="sxs-lookup"><span data-stu-id="7fac7-103">Microsoft 365 global tenant performance optimization for China users</span></span>

>[!IMPORTANT]
><span data-ttu-id="7fac7-104">이 지침은 중국에 있는 엔터프라이즈 Microsoft 365 사용자가 전역 **Microsoft 365** 테넌트에 연결하는 사용 **시나리오와 관련이 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="7fac7-104">This guidance is specific to usage scenarios in which **enterprise Microsoft 365 users located in China** connect to a **global Microsoft 365 tenant**.</span></span> <span data-ttu-id="7fac7-105">이 **지침은** 21Vianet에서 운영하는 Office 365의 테넌트에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-105">This guidance does **not** apply to tenants in Office 365 operated by 21Vianet.</span></span>

<span data-ttu-id="7fac7-106">글로벌 Microsoft 365 테넌트가 있는 기업의 경우 중국 기반 사용자에 대한 Microsoft 365 클라이언트 성능은 중국 텔코의 인터넷 아키텍처에 고유한 요인으로 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-106">For enterprises with global Microsoft 365 tenants and a corporate presence in China, Microsoft 365 client performance for China-based users can be complicated by factors unique to China Telco's Internet architecture.</span></span>

<span data-ttu-id="7fac7-107">중국 ISP는 높은 수준의 경계 네트워크 정체에 가까우는 경계 장치를 통과하는 전역 공용 인터넷에 대한 오프해어 연결을 규제했습니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-107">China ISPs have regulated offshore connections to the global public Internet that go through perimeter devices which are prone to high-levels of cross-border network congestion.</span></span> <span data-ttu-id="7fac7-108">이 정체로 인해 중국으로 들어와서 들어와는 모든 인터넷 트래픽에 대한 패킷 손실 및 대기 시간이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-108">This congestion creates packet loss and latency for all Internet traffic going into and out of China.</span></span>

![Microsoft 365 트래픽 - 미개시](../media/O365-networking/China-O365-unoptimized.png)

<span data-ttu-id="7fac7-110">패킷 손실 및 대기 시간은 네트워크 서비스의 성능에 손상이 됩니다. 특히 대용량 데이터 교환(예: 대용량 파일 전송)이 필요하거나 거의 실시간 성능이 필요한 서비스(오디오 및 비디오 응용 프로그램)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-110">Packet loss and latency is detrimental to the performance of network services, especially services that require large data exchanges (such as large file transfers) or requiring near real-time performance (audio and video applications).</span></span>

<span data-ttu-id="7fac7-111">이 항목의 목표는 Microsoft 365 서비스에 대한 중국 간 네트워크 정체의 영향을 완화하기 위한 모범 사례를 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-111">The goal of this topic is to provide best practices for mitigating the impact of China cross-border network congestion on Microsoft 365 services.</span></span> <span data-ttu-id="7fac7-112">이 항목에서는 중국 통신 사업자 내의 복잡한 라우팅으로 인한 높은 패킷 대기 시간 문제와 같은 일반적인 마지막 마일 성능 문제를 해결하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-112">This topic does not address other common last-mile performance issues such as issues of high packet latency due to complex routing within China carriers.</span></span>

## <a name="corporate-network-best-practices"></a><span data-ttu-id="7fac7-113">회사 네트워크 모범 사례</span><span class="sxs-lookup"><span data-stu-id="7fac7-113">Corporate network best practices</span></span>

<span data-ttu-id="7fac7-114">글로벌 Microsoft 365 테넌트와 중국의 사용자가 있는 많은 기업은 중국 사무실 위치와 전 세계 해상 위치 간의 회사 네트워크 트래픽을 전달하는 개인 네트워크를 구현했습니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-114">Many enterprises with global Microsoft 365 tenants and users in China have implemented private networks that carry corporate network traffic between China office locations and offshore locations around the world.</span></span> <span data-ttu-id="7fac7-115">이러한 기업은 이 네트워크 인프라를 활용하여 국경 간 네트워크 정체를 방지하고 중국의 Microsoft 365 서비스 성능을 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-115">These enterprises can leverage this network infrastructure to avoid cross-border network congestion and optimize their Microsoft 365 service performance in China.</span></span>

>[!IMPORTANT]
><span data-ttu-id="7fac7-116">모든 사설 WAN 구현과 함께 항상 해당 국가 및/또는 지역에 대한 규정 요구 사항을 문의하여 네트워크 구성이 규정을 준수하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-116">As with all private WAN implementations, you should always consult regulatory requirements for your country and/or region to ensure that your network configuration is in compliance.</span></span>

<span data-ttu-id="7fac7-117">첫 번째 [단계에서는 Microsoft 365의](https://aka.ms/tune)네트워크 계획 및 성능 조정에 대한 벤치마크 네트워크 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-117">As a first step, it is crucial that you follow our benchmark network guidance at [Network planning and performance tuning for Microsoft 365](https://aka.ms/tune).</span></span> <span data-ttu-id="7fac7-118">주요 목표는 가능한 경우 중국의 인터넷에서 전역 Microsoft 365 서비스에 액세스하지 않도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-118">The primary goal should be to avoid accessing global Microsoft 365 services from the Internet in China if possible.</span></span>

- <span data-ttu-id="7fac7-119">기존 개인 네트워크를 활용하여 중국 사무실 네트워크와 중국 외부의 공용 인터넷을 통해 나가는 지점 간의 Microsoft 365 네트워크 트래픽을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-119">Leverage your existing private network to carry Microsoft 365 network traffic between China office networks and offshore locations that egress on the public Internet outside China.</span></span> <span data-ttu-id="7fac7-120">중국 외부의 거의 모든 위치는 명확한 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-120">Almost any location outside China will provide a clear benefit.</span></span> <span data-ttu-id="7fac7-121">네트워크 관리자는 대기 시간이 짧은 영역을 Microsoft 전역 네트워크와 연결하여 더욱 [최적화할 수 있습니다.](https://docs.microsoft.com/azure/networking/microsoft-global-network)</span><span class="sxs-lookup"><span data-stu-id="7fac7-121">Network administrators can further optimize by egressing in areas with low-latency interconnect with the [Microsoft global network](https://docs.microsoft.com/azure/networking/microsoft-global-network).</span></span> <span data-ttu-id="7fac7-122">홍콩, 일본 및 대한민국이 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-122">Hong Kong, Japan, and South Korea are examples.</span></span>
- <span data-ttu-id="7fac7-123">Microsoft 365 트래픽이 회사 네트워크의 개인 오프사이어 링크를 전송할 수 있도록 VPN 연결을 통해 회사 네트워크에 액세스하도록 사용자 장치를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-123">Configure user devices to access the corporate network over a VPN connection to allow Microsoft 365 traffic to transit the corporate network's private offshore link.</span></span> <span data-ttu-id="7fac7-124">VPN 클라이언트가 분할 터널링을 사용하도록 구성되지 않은지 또는 사용자 장치가 Microsoft 365 트래픽에 대한 분할 터널링을 무시하도록 구성되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="7fac7-124">Ensure that VPN clients are either not configured to use split tunneling, or that user devices are configured to ignore split tunneling for Microsoft 365 traffic.</span></span>
- <span data-ttu-id="7fac7-125">모든 Microsoft 365 트래픽을 개인 오프사이어 링크를 통해 라우팅하도록 네트워크를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-125">Configure your network to route all Microsoft 365 traffic across your private offshore link.</span></span> <span data-ttu-id="7fac7-126">개인 링크의 트래픽 양을 최소화해야 하는 경우 최적화 범주의 끝점만 라우팅하고 허용 및  기본  끝점에 인터넷을 전송하도록 허용하도록 선택할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="7fac7-126">If you must minimize the volume of traffic on your private link, you can choose to only route endpoints in the **Optimize** category, and allow requests to **Allow** and **Default** endpoints to transit the Internet.</span></span> <span data-ttu-id="7fac7-127">이렇게 하면 대기 시간 및 패킷 손실에 가장 민감한 중요한 서비스로 최적화된 트래픽을 제한하여 성능을 개선하고 대역폭 소비를 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-127">This will improve performance and minimize bandwidth consumption by limiting optimized traffic to critical services that are most sensitive to high latency and packet loss.</span></span>
- <span data-ttu-id="7fac7-128">가능한 경우 Teams와 같은 라이브 미디어 스트리밍 트래픽에 TCP 대신 UDP를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-128">If possible, use UDP instead of TCP for live media streaming traffic, such as for Teams.</span></span> <span data-ttu-id="7fac7-129">UDP는 TCP보다 더 나은 라이브 미디어 스트리밍 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-129">UDP offers better live media streaming performance than TCP.</span></span>

<span data-ttu-id="7fac7-130">Microsoft 365 트래픽을 선택적으로 라우팅하는 방법에 대한 자세한 내용은 [Office 365 끝점 관리를 참조하세요.](managing-office-365-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="7fac7-130">For information about how to selectively route Microsoft 365 traffic, see [Managing Office 365 endpoints](managing-office-365-endpoints.md).</span></span> <span data-ttu-id="7fac7-131">전 세계 모든 Office 365 URL 및 IP 주소 목록은 [Office 365 URL](urls-and-ip-address-ranges.md)및 IP 주소 범위를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7fac7-131">For a list of all worldwide Office 365 URLs and IP addresses, see [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>

![Microsoft 365 트래픽 - 최적화](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a><span data-ttu-id="7fac7-133">사용자 모범 사례</span><span class="sxs-lookup"><span data-stu-id="7fac7-133">User best practices</span></span>

<span data-ttu-id="7fac7-134">집, 커피숍, 커피숍 및 지사와 같은 원격 위치에서 글로벌 Microsoft 365 테넌트에 연결하는 중국의 사용자는 장치와 Microsoft 365 간의 트래픽이 중국의 정체된 교차 네트워크 회로를 전송해야 하기 때문에 네트워크 성능이 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-134">Users in China who connect to global Microsoft 365 tenants from remote locations such as homes, coffee shops, hotels and branch offices with no connection to enterprise networks can experience poor network performance because traffic between their devices and Microsoft 365 must transit China's congested cross-border network circuits.</span></span>

<span data-ttu-id="7fac7-135">경계 간 개인 네트워크 및/또는 회사 네트워크에 대한 VPN 액세스가 옵션이 아닌 경우 중국 기반 사용자에게 이러한 모범 사례를 따르는 교육을 통해 사용자당 성능 문제를 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-135">If cross-border private networks and/or VPN access into the corporate network are not an option, per-user performance issues can still be mitigated by training your China-based users to follow these best practices.</span></span>

- <span data-ttu-id="7fac7-136">캐싱을 지원하는 다양한 Office 클라이언트(예: Outlook, Teams, OneDrive 등)를 활용하고 웹 기반 클라이언트를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-136">Utilize rich Office clients that support caching (e.g. Outlook, Teams, OneDrive, etc.), and avoid web-based clients.</span></span> <span data-ttu-id="7fac7-137">Office 클라이언트 캐싱 및 오프라인 액세스 기능은 네트워크 정체 및 대기 시간의 영향을 크게 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-137">Office client caching and offline access features can dramatically reduce the impact of network congestion and latency.</span></span>
- <span data-ttu-id="7fac7-138">Microsoft 365 테넌트가 오디오 회의  기능을 사용하여 구성된 경우 Teams 사용자는 PSTN(공용 전화망)을 통해 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-138">If your Microsoft 365 tenant has been configured with the _Audio Conferencing_ feature, Teams users can join meetings via the public switched telephone network (PSTN).</span></span> <span data-ttu-id="7fac7-139">자세한 내용은 [Office 365의](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)오디오 회의를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7fac7-139">For more information, see [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span>
- <span data-ttu-id="7fac7-140">사용자가 네트워크 성능 문제가 발생하면 IT 부서에 문제 해결을 보고하고 Microsoft 365 서비스에 문제가 있는 것으로 의심되는 경우 Microsoft 지원으로 에스컬레이터해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-140">If users experience network performance issues, they should report to their IT department for troubleshooting, and escalate to Microsoft support if trouble with Microsoft 365 services is suspected.</span></span> <span data-ttu-id="7fac7-141">경계 간 네트워크 성능으로 인해 모든 문제가 발생하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-141">Not all issues are caused by cross-border network performance.</span></span>

<span data-ttu-id="7fac7-142">Microsoft는 최대한 광범위한 네트워크 아키텍처 및 특성을 통해 Microsoft 365 사용자 환경 및 클라이언트 성능을 개선하기 위해 지속적으로 작업하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-142">Microsoft is continually working to improve the Microsoft 365 user experience and the performance of clients over the widest possible range of network architectures and characteristics.</span></span> <span data-ttu-id="7fac7-143">Office [365](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) 기술 커뮤니티를 방문하여 대화를 시작하거나 참가하고, 리소스를 찾고, 기능 요청 및 제안을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="7fac7-143">Visit the [Office 365 Tech Community](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) to start or join a conversation, find resources, and submit feature requests and suggestions.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7fac7-144">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7fac7-144">Related topics</span></span>

[<span data-ttu-id="7fac7-145">Microsoft 365의 네트워크 계획 및 성능 조정</span><span class="sxs-lookup"><span data-stu-id="7fac7-145">Network planning and performance tuning for Microsoft 365</span></span>](https://aka.ms/tune)

[<span data-ttu-id="7fac7-146">Microsoft 365 네트워크 연결 원칙</span><span class="sxs-lookup"><span data-stu-id="7fac7-146">Microsoft 365 network connectivity principles</span></span>](microsoft-365-network-connectivity-principles.md)

[<span data-ttu-id="7fac7-147">Office 365 엔드포인트 관리</span><span class="sxs-lookup"><span data-stu-id="7fac7-147">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)

[<span data-ttu-id="7fac7-148">Office 365 URL 및 IP 주소 범위</span><span class="sxs-lookup"><span data-stu-id="7fac7-148">Office 365 URLs and IP address ranges</span></span>](urls-and-ip-address-ranges.md)

[<span data-ttu-id="7fac7-149">Microsoft 전역 네트워크</span><span class="sxs-lookup"><span data-stu-id="7fac7-149">Microsoft global network</span></span>](https://docs.microsoft.com/azure/networking/microsoft-global-network)
