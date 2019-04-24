---
title: '2단계: 각 사무실에 대해 로컬 인터넷 연결 구성'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 성능 향상을 위해 DNS 확인을 이해하고 구성합니다.
ms.openlocfilehash: 6f276bd1fd90b8dee76a0b0d350f256956ded412
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291133"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a><span data-ttu-id="06a09-103">2단계: 각 사무실에 대해 로컬 인터넷 연결 구성</span><span class="sxs-lookup"><span data-stu-id="06a09-103">Step 2: Configure local Internet connections for each office</span></span>

<span data-ttu-id="06a09-104">*이 단계는 필수 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="06a09-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="06a09-p101">2단계에서는 각 사무실에 로컬 인터넷 연결이 설정되고 로컬 DNS 서버를 사용하고 있어야 합니다.연결 대기 시간을 줄이고 온-프레미스 클라이언트 컴퓨터가 Microsoft 365 클라우드 기반 서비스의 가장 가까운 입력 지점에 연결되어 있도록 하려면 이러한 두 요소가 모두 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="06a09-p101">In Step 2, you ensure that each of your offices have local Internet connections and use local DNS servers. Both of these elements are required to reduce connection latency and ensure that on-premises client computers make connections to the nearest point of entry to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="06a09-p102">대규모 조직에 대한 기존 네트워크에서 인터넷 트래픽은 네트워크 백본을 거쳐 중앙 인터넷 연결로 이동합니다. 이러한 방식은 Microsoft 365에서 Office 365 및 EMS(Enterprise Mobility + Security) 제품을 포함하는 전역 분산 SaaS(Software-as-a-Service) 인프라에 대한 성능을 최적화하는 데는 적절하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06a09-p102">In traditional networks for large organizations, Internet traffic travels across the network backbone to a central Internet connection. This does not work well for optimizing performance to a globally distributed Software-as-a-Service (SaaS) infrastructure, which includes the Office 365 and Enterprise Mobility + Security (EMS) products in Microsoft 365.</span></span>

<span data-ttu-id="06a09-p103">Microsoft 전역 네트워크에는 전 세계 Microsoft 365의 클라우드 서비스 집합에 대한 프런트 엔드 서버가 포함되어 있습니다. 최상의 성능을 위해서는 온-프레미스 클라이언트가 네트워크 백본을 통해 조직의 중앙 인터넷 연결에 가장 가까운 프런트 엔드 서버로 트래픽을 전송하기보다는 지리적으로 가장 가까운 프런트 엔드 서버에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a09-p103">The Microsoft Global Network includes front end servers to the set of cloud services for Microsoft 365 all over the world. For the best performance, on-premises clients should access a front-end server that is geographically closest to them, rather than sending the traffic over a network backbone and to the front-end server that is closest to the organization’s central Internet connection.</span></span>

<span data-ttu-id="06a09-p104">클라이언트 요청을 지리적으로 가장 가까운 프런트 엔드 서버로 보내기 위해 Microsoft DNS 서버는 클라이언트의 초기 연결 요청에 해당하는 DNS 쿼리를 사용합니다. 따라서 네트워크 대기 시간을 최소화하기 위해 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="06a09-p104">To direct a client request to the geographically nearest front-end server, Microsoft’s DNS servers use the DNS queries corresponding the client’s initial connection request. Therefore, for the lowest network latency:</span></span>

- <span data-ttu-id="06a09-113">조직의 모든 사무실은 [최적화](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) 범주 네트워크 트래픽에 대해 로컬 인터넷 연결이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a09-113">All offices of your organization should have local Internet connections for [Optimize](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) category network traffic.</span></span>
- <span data-ttu-id="06a09-114">각 로컬 인터넷 연결은 해당 위치에서의 아웃바운드 인터넷 트래픽에 지역적으로 로컬에 있는 DNS 서버를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06a09-114">Each local Internet connection should be using a regionally local DNS server for outbound Internet traffic from that location.</span></span>

<span data-ttu-id="06a09-115">자세한 내용은 [네트워크 연결을 로컬로 송신](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06a09-115">For more information, see [Egress network connections locally](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span></span> 

<span data-ttu-id="06a09-116">중간 검사점으로 이 단계에 대한 [종료 조건](networking-exit-criteria.md#crit-networking-step2)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06a09-116">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step2) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="06a09-117">다음 단계</span><span class="sxs-lookup"><span data-stu-id="06a09-117">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="06a09-118">네트워크 헤어핀 방지</span><span class="sxs-lookup"><span data-stu-id="06a09-118">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
