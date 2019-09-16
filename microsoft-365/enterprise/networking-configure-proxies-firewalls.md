---
title: '4단계: 트래픽 바이패스 구성'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 신뢰할 수 있는 Office 365 위치로의 트래픽 바이패스를 위해 웹 브라우저 및 에 장치를 이해하고 구성합니다.
ms.openlocfilehash: 416c93fd3f44e1cd9edba52a9d6117ac6d133760
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982789"
---
# <a name="step-4-configure-traffic-bypass"></a><span data-ttu-id="2764d-103">4단계: 트래픽 바이패스 구성</span><span class="sxs-lookup"><span data-stu-id="2764d-103">Step 4: Configure traffic bypass</span></span>

<span data-ttu-id="2764d-104">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="2764d-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="2764d-p101">일반 인터넷 트래픽이 위험할 수 있으므로 일반적인 조직 네트워크는 프록시 서버, SSL 중단 및 조사, 패킷 검사 장치와 같은 에지 장치와 데이터 손실 방지 시스템을 통해 보안을 적용합니다. “Office 365 트래픽에 대해 타사 네트워크 장치 또는 솔루션 사용”에서 네트워크 차단 장치의 일부 문제점을 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="2764d-p101">Because general Internet traffic can be risky, typical organization networks enforce security with edge devices such as proxy servers, SSL Break and Inspect, and packet inspection devices, and data loss prevention systems. Read about some of the issues with network interception devices at Using third-party network devices or solutions on Office 365 traffic.</span></span>

<span data-ttu-id="2764d-p102">그러나 Microsoft 365 클라우드 기반 서비스에서 사용하는 DNS 도메인 이름 및  IP 주소는 잘 알려져 있습니다. 또한 트래픽 및 서비스 자체는 많은 보안 기능으로 보호됩니다. 이러한 보안 및 보호는 이미 설정되어 있으므로 에지 장치에서 복제할 필요가 없습니다. Microsoft 365 트래픽에 대한 중간 대상 및 중복 보안 처리로 인해 성능이 크게 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2764d-p102">However, the DNS domain names and IP addresses used by Microsoft 365 cloud-based services are well known. Additionally, the traffic and services themselves are protected with many security features. Because this security and protection is already in place, your edge devices don’t need to duplicate it. Intermediate destinations and duplicate security processing for Microsoft 365 traffic can dramatically decrease performance.</span></span>

<span data-ttu-id="2764d-p103">중간 대상 및 중복 보안 처리를 제거하는 첫 번째 단계는 Microsoft 365 트래픽을 식별하는 것입니다. Microsoft는 끝점이라고 하는 다음과 같은 유형의 DNS 도메인 이름 및 IP 주소 범위를 정의했습니다.</span><span class="sxs-lookup"><span data-stu-id="2764d-p103">The first step in eliminating intermediate destinations and duplicate security processing is to identify Microsoft 365 traffic. Microsoft has defined the following types of DNS domain names and IP address ranges, known as endpoints:</span></span>

- <span data-ttu-id="2764d-p104">**최적화** - 모든 Office 365 서비스에 연결하는 데 필요하며 75%가 넘는 Microsoft 365 대역폭, 연결 및 데이터 볼륨을 나타냅니다. 이러한 엔드포인트는 네트워크 성능, 대기 시간 및 가용성에 가장 민감한 Microsoft 365 시나리오를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2764d-p104">**Optimize** - Required for connectivity to every Office 365 service and represent over 75% of Microsoft 365 bandwidth, connections, and volume of data. These endpoints represent Microsoft 365 scenarios that are the most sensitive to network performance, latency and availability.</span></span>
- <span data-ttu-id="2764d-115">**허용** - 특정 Microsoft 365 서비스 및 기능에 연결하는 데 필요하지만 최적화 범주의 경우만큼 네트워크 성능 및 대기 시간에 민감하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2764d-115">**Allow** - Required for connectivity to specific Microsoft 365 services and features but are not as sensitive to network performance and latency as those in the Optimize category.</span></span>
 - <span data-ttu-id="2764d-p105">**기본** - 최적화를 요구하지 않는 Microsoft 365 서비스 및 종속성을 나타냅니다. 기본 범주 엔드포인트를 일반적인 인터넷 트래픽으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2764d-p105">**Default** - Represent Microsoft 365 services and dependencies that do not require any optimization. You can treat Default category endpoints as normal Internet traffic.</span></span>

<span data-ttu-id="2764d-118">[https://aka.ms/o365endpoints](https://aka.ms/o365endpoints)에서 DNS 도메인 이름 및 IP 주소 범위를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2764d-118">You can find the DNS domain names and IP address ranges at [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span></span>

<span data-ttu-id="2764d-119">다음이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="2764d-119">Microsoft recommends that you:</span></span>

- <span data-ttu-id="2764d-p106">온-프레미스 컴퓨터의 인터넷 브라우저에서 PAC(프록시 자동 구성) 스크립트를 사용하여 Microsoft 365 클라우드 기반 서비스의 DNS 도메인 이름에 대한 프록시 서버를 무시합니다. 최신 Microsoft 365 PAC 스크립트의 경우 [Get-Pacfile PowerShell 스크립트](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2764d-p106">Use Proxy Automatic Configuration (PAC) scripts on the Internet browsers of your on-premises computers to bypass your proxy servers for the DNS domain names of Microsoft 365 cloud-based services. For the latest Microsoft 365 PAC script, see the Get-Pacfile PowerShell script.</span></span>
- 
- <span data-ttu-id="2764d-p107">에지 장치를 분석하여 중복 처리를 확인한 후, 처리하지 않고 최적화 및 허용 끝점으로 트래픽을 전달하도록 구성합니다. 이것을 트래픽 바이패스라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2764d-p107">Analyze your edge devices to determine the duplicate processing and then configure them to forward traffic to Optimize and Allow endpoints without processing. This is known as traffic bypass.</span></span> 

<span data-ttu-id="2764d-p108">에지 장치에는 방화벽, SSL 중단 및 조사, 패킷 검사 장치, 데이터 손실 방지 시스템이 포함되어 있습니다. 에지 장치를 구성하고 구성을 업데이트하려면 스크립트 또는 REST 호출을 사용하여 Office 365 끝점 웹 서비스의 구조화된 끝점 목록을 사용할 수 있습니다. 자세한 내용은 [Office 365 IP 주소 및 URL 웹 서비스](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2764d-p108">Edge devices include firewalls, SSL Break and Inspect, and packet inspection devices, and data loss prevention systems. To configure and update the configurations of edge devices, you can use a script or a REST call to consume a structured list of endpoints from the Office 365 Endpoints web service. For more information, see [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

<span data-ttu-id="2764d-p109">Microsoft 365 최적화 및 허용 범주 끝점에 대한 트래픽의 일반 프록시 및 네트워크 보안 처리만 우회하게 됩니다. 다른 모든 일반 인터넷 트래픽은 프록시 처리되며, 기존 네트워크 보안 처리를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2764d-p109">Note that you are only bypassing normal proxy and network security processing for traffic to Microsoft 365 Optimize and Allow categories endpoints. All other general Internet traffic will be proxied and be subject to your existing network security processing.</span></span>


<span data-ttu-id="2764d-129">중간 검사점으로 이 단계에 대한 [종료 조건](networking-exit-criteria.md#crit-networking-step4)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2764d-129">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="2764d-130">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2764d-130">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="2764d-131">클라이언트 및 Office 365 서비스 성능 최적화</span><span class="sxs-lookup"><span data-stu-id="2764d-131">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md) |



