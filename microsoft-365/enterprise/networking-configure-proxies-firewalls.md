---
title: '4단계: 트래픽 바이패스 구성'
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
description: 신뢰할 수 있는 Office 365 위치로의 트래픽 바이패스를 위해 웹 브라우저 및 에 장치를 이해하고 구성합니다.
ms.openlocfilehash: 71f62c5e245962f3514c49477e3cdeda17cb6397
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066692"
---
# <a name="step-4-configure-traffic-bypass"></a><span data-ttu-id="5f713-103">4단계: 트래픽 바이패스 구성</span><span class="sxs-lookup"><span data-stu-id="5f713-103">Step 4: Configure traffic bypass</span></span>

<span data-ttu-id="5f713-104">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="5f713-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![1단계-네트워킹](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="5f713-106">일반 인터넷 트래픽이 위험할 수 있으므로 일반적인 조직 네트워크는 프록시 서버, SSL 중단 및 조사, 패킷 검사 장치와 같은 에지 장치와 데이터 손실 방지 시스템을 통해 보안을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="5f713-106">Because general Internet traffic can be risky, typical organization networks enforce security with edge devices such as proxy servers, SSL Break and Inspect, packet inspection devices, and data loss prevention systems.</span></span> <span data-ttu-id="5f713-107">[Office 365 트래픽에 대해 타사 네트워크 장치 또는 솔루션 사용](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365)에서 네트워크 차단 장치의 일부 문제점을 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="5f713-107">Read about some of the issues with network interception devices at [Using third-party network devices or solutions on Office 365 traffic](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).</span></span>

<span data-ttu-id="5f713-p102">그러나 Microsoft 365 클라우드 기반 서비스에서 사용하는 DNS 도메인 이름 및  IP 주소는 잘 알려져 있습니다. 또한 트래픽 및 서비스 자체는 많은 보안 기능으로 보호됩니다. 이러한 보안 및 보호는 이미 설정되어 있으므로 에지 장치에서 복제할 필요가 없습니다. Microsoft 365 트래픽에 대한 중간 대상 및 중복 보안 처리로 인해 성능이 크게 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f713-p102">However, the DNS domain names and IP addresses used by Microsoft 365 cloud-based services are well known. Additionally, the traffic and services themselves are protected with many security features. Because this security and protection is already in place, your edge devices don’t need to duplicate it. Intermediate destinations and duplicate security processing for Microsoft 365 traffic can dramatically decrease performance.</span></span>

<span data-ttu-id="5f713-p103">중간 대상 및 중복 보안 처리를 제거하는 첫 번째 단계는 Microsoft 365 트래픽을 식별하는 것입니다. Microsoft는 끝점이라고 하는 다음과 같은 유형의 DNS 도메인 이름 및 IP 주소 범위를 정의했습니다.</span><span class="sxs-lookup"><span data-stu-id="5f713-p103">The first step in eliminating intermediate destinations and duplicate security processing is to identify Microsoft 365 traffic. Microsoft has defined the following types of DNS domain names and IP address ranges, known as endpoints:</span></span>

- <span data-ttu-id="5f713-114">**최적화** - 모든 Office 365 서비스에 연결이 필요하며 Microsoft 365 대역폭, 연결, 데이터 볼륨의 75%를 초과하여 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5f713-114">**Optimize** - Required for connectivity to every Office 365 service and represent over 75% of Microsoft 365 bandwidth, connections, and volume of data.</span></span> <span data-ttu-id="5f713-115">이러한 끝점은 네트워크 성능, 대기 시간 및 가용성에 가장 중요한 Microsoft 365 시나리오를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5f713-115">These endpoints represent Microsoft 365 scenarios that are the most sensitive to network performance, latency, and availability.</span></span>
- <span data-ttu-id="5f713-116">**허용** - 특정 Microsoft 365 서비스 및 기능에 연결하는 데 필요하지만 최적화 범주의 경우만큼 네트워크 성능 및 대기 시간에 민감하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f713-116">**Allow** - Required for connectivity to specific Microsoft 365 services and features but are not as sensitive to network performance and latency as those in the Optimize category.</span></span>
 - <span data-ttu-id="5f713-p105">**기본** - 최적화를 요구하지 않는 Microsoft 365 서비스 및 종속성을 나타냅니다. 기본 범주 엔드포인트를 일반적인 인터넷 트래픽으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f713-p105">**Default** - Represent Microsoft 365 services and dependencies that do not require any optimization. You can treat Default category endpoints as normal Internet traffic.</span></span>

<span data-ttu-id="5f713-119">[https://aka.ms/o365endpoints](https://aka.ms/o365endpoints)에서 DNS 도메인 이름 및 IP 주소 범위를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f713-119">You can find the DNS domain names and IP address ranges at [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span></span>

<span data-ttu-id="5f713-120">다음이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f713-120">Microsoft recommends that you:</span></span>

- <span data-ttu-id="5f713-121">온-프레미스 컴퓨터의 인터넷 브라우저에서 PAC(프록시 자동 구성) 스크립트를 사용하여 Microsoft 365 클라우드 기반 서비스의 DNS 도메인 이름에 대한 프록시 서버를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="5f713-121">Use Proxy Automatic Configuration (PAC) scripts on the Internet browsers of your on-premises computers to bypass your proxy servers for the DNS domain names of Microsoft 365 cloud-based services.</span></span> <span data-ttu-id="5f713-122">최신 Microsoft 365 PAC 스크립트의 경우 [Get-Pacfile PowerShell 스크립트](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f713-122">For the latest Microsoft 365 PAC script, see the [Get-Pacfile PowerShell script](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span></span>

- <span data-ttu-id="5f713-p107">에지 장치를 분석하여 중복 처리를 확인한 후, 처리하지 않고 최적화 및 허용 끝점으로 트래픽을 전달하도록 구성합니다. 이것을 트래픽 바이패스라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f713-p107">Analyze your edge devices to determine the duplicate processing and then configure them to forward traffic to Optimize and Allow endpoints without processing. This is known as traffic bypass.</span></span> 

<span data-ttu-id="5f713-125">다음은 네트워크 인프라에 몇 가지 권장 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5f713-125">Here are these recommendations in your network infrastructure.</span></span>

![온-프레미스 트래픽 최적화에 대한 권장 사항](../media/networking-configure-proxies-firewalls/bypassing-edge-devices.png)

<span data-ttu-id="5f713-127">에지 장치에는 방화벽, SSL 중단 및 조사, 패킷 검사 장치, 데이터 손실 방지 시스템 등이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f713-127">Edge devices include firewalls, SSL Break and Inspect, packet inspection devices, and data loss prevention systems.</span></span> <span data-ttu-id="5f713-128">에지 장치를 구성하고 업데이트하려면 스크립트나 REST 호출을 사용하여 Office 365 끝점 웹 서비스에서 끝점의 구조화 목록을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f713-128">To configure and update the configurations of edge devices, you can use a script or a REST call to consume a structured list of endpoints from the Office 365 Endpoints web service.</span></span> <span data-ttu-id="5f713-129">자세한 내용은 [Office 365 IP 주소 및 URL 웹 서비스](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f713-129">For more information, see [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

<span data-ttu-id="5f713-p109">Microsoft 365 최적화 및 허용 범주 끝점에 대한 트래픽의 일반 프록시 및 네트워크 보안 처리만 우회하게 됩니다. 다른 모든 일반 인터넷 트래픽은 프록시 처리되며, 기존 네트워크 보안 처리를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="5f713-p109">Note that you are only bypassing normal proxy and network security processing for traffic to Microsoft 365 Optimize and Allow categories endpoints. All other general Internet traffic will be proxied and be subject to your existing network security processing.</span></span>


<span data-ttu-id="5f713-132">중간 검사점으로 이 단계에 대한 [종료 조건](networking-exit-criteria.md#crit-networking-step4)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f713-132">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="5f713-133">다음 단계</span><span class="sxs-lookup"><span data-stu-id="5f713-133">Next step</span></span>

|||
|:-------|:-----|
|![5단계](../media/stepnumbers/Step5.png)|[<span data-ttu-id="5f713-135">클라이언트 및 Office 365 서비스 성능 최적화</span><span class="sxs-lookup"><span data-stu-id="5f713-135">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md) |



