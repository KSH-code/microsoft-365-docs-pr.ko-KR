---
title: '3단계: 네트워크 헤어핀 방지'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 더 나은 성능을 위해 네트워크 헤어핀을 이해하고 제거합니다.
ms.openlocfilehash: f9499fdb8e8c3f7b77e3349d6cc99f6dbf465870
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066719"
---
# <a name="step-3-avoid-network-hairpins"></a><span data-ttu-id="2219e-103">3단계: 네트워크 헤어핀 방지</span><span class="sxs-lookup"><span data-stu-id="2219e-103">Step 3: Avoid network hairpins</span></span>

<span data-ttu-id="2219e-104">*이 단계는 필수 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="2219e-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![1 단계-네트워킹](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="2219e-106">목적지의 트래픽 바운드가 온-프레미스 보안 스택, 클라우드 액세스 브로커 또는 클라우드 기반 웹 게이트웨이와 같은 다른 중간 위치로 전달될 시 [네트워크 헤어핀](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3)이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2219e-106">A [network hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) happens when traffic bound for a destination is first directed to another intermediate location, such as an on-premises security stack, cloud access broker, or cloud-based web gateway.</span></span> <span data-ttu-id="2219e-107">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2219e-107">Here is an example.</span></span>

![네트워크 헤어핀의 예시](../media/networking-avoid-network-hairpins/network-hairpin-example.png)

<span data-ttu-id="2219e-109">네트워크 헤어핀은 네트워크 서비스 공급업체로 인해 인터넷에서의 잘못된 라우팅이 원인이 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2219e-109">A network hairpin could also be caused by poor routing on the Internet due to network service providers.</span></span> 

<span data-ttu-id="2219e-110">헤어핀은 대기 시간을 더하고 잠재적으로 지리적으로 떨어진 위치로 트래픽 방향을 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2219e-110">A hairpin adds latency and can potentially redirect traffic to a geographically distant location.</span></span>

<span data-ttu-id="2219e-p102">Microsoft 365 클라우드 기반 서비스에 대한 트래픽의 성능을 최적화하기 위해 로컬 인터넷 연결을 제공하는 ISP가 해당 위치에서 근접한 Microsoft 전역 네트워크와 직접 피어링 관계가 있는지 여부를 확인합니다. 이러한 연결에는 헤어핀이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2219e-p102">To optimize performance for traffic to Microsoft 365 cloud-based services, check whether the ISP providing the local Internet connection has a direct peering relationship with the Microsoft Global Network in close proximity to that location. These connections do not have hairpins.</span></span>

<span data-ttu-id="2219e-p103">Microsoft 365 트래픽을 위해 클라우드 기반 네트워크 또는 보안 서비스를 사용하는 경우 헤어핀 효과를 평가하고 성능에 미치는 영향을 이해해야 합니다. 다음을 검사하세요.</span><span class="sxs-lookup"><span data-stu-id="2219e-p103">If you use cloud-based network or security services for your Microsoft 365 traffic, ensure that the hairpinning effect is evaluated and its impact on performance is understood. Examine the following:</span></span>

- <span data-ttu-id="2219e-115">지사 및 Microsoft 전역 네트워크 피어링 지점과 관련해서 트래픽이 전달되는 서비스 공급자의 번호 및 위치</span><span class="sxs-lookup"><span data-stu-id="2219e-115">The number and locations of your service providers through which the traffic is forwarded in relationship to your branch offices and Microsoft Global Network peering points</span></span> 
- <span data-ttu-id="2219e-116">ISP 및 Microsoft와 서비스 공급자의 네트워크 피어링 관계 품질</span><span class="sxs-lookup"><span data-stu-id="2219e-116">The quality of the network peering relationship of the service provider with your ISP and Microsoft</span></span> 
- <span data-ttu-id="2219e-117">서비스 공급자 인프라의 백홀이 성능에 미치는 영향</span><span class="sxs-lookup"><span data-stu-id="2219e-117">The performance impact of backhauling in the service provider infrastructure</span></span>

<span data-ttu-id="2219e-118">가능하면 인터넷 트래픽을 처리하는 타사 클라우드 또는 클라우드 기반 네트워크 보안 공급업체를 통한 프로시 또는 터널링 대신, 신뢰할 수 있는 Microsoft 365 트래픽을 직접 전송하도록 에지 라우터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2219e-118">Whenever possible, configure your edge routers to send trusted Microsoft 365 traffic directly, instead of proxying or tunneling through a third-party cloud or cloud-based network security vendor that processes your Internet traffic.</span></span> 

![네트워크 헤어핀의 우회 예시](../media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

<span data-ttu-id="2219e-120">중간 검사점으로 이 단계에 대한 [종료 조건](networking-exit-criteria.md#crit-networking-step3)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2219e-120">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step3) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="2219e-121">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2219e-121">Next step</span></span>

|||
|:-------|:-----|
|![4단계](../media/stepnumbers/Step4.png)|[<span data-ttu-id="2219e-123">트래픽 바이패스 구성</span><span class="sxs-lookup"><span data-stu-id="2219e-123">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
