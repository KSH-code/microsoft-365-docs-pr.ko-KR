---
title: '1단계: 네트워킹 인프라 종료 조건'
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
description: 구성이 네트워킹 인프라에 대한 Microsoft 365 Enterprise 조건을 충족하는지 확인합니다.
ms.openlocfilehash: 6d9133fa6f3c993efe88ea53b412b9a272c1b98b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631492"
---
# <a name="phase-1-networking-infrastructure-exit-criteria"></a><span data-ttu-id="1c715-103">1단계: 네트워킹 인프라 종료 조건</span><span class="sxs-lookup"><span data-stu-id="1c715-103">Phase 1: Networking infrastructure exit criteria</span></span>

![1 단계-네트워킹](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="1c715-105">네트워킹 인프라가 다음과 같은 필수 조건 및 선택 요소에 확실히 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c715-105">Make sure your networking infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-networking-step1"></a>
## <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a><span data-ttu-id="1c715-106">필수 사항: 네트워크에서 Microsoft 365 Enterprise 사용 준비 완료</span><span class="sxs-lookup"><span data-stu-id="1c715-106">Required: Your network is ready for Microsoft 365 Enterprise</span></span>

- <span data-ttu-id="1c715-107">사무실에 Office 365, Microsoft Intune, Windows 10 Enterprise 설치 및 업데이트를 포함하여 Microsoft 365 트래픽에 적합한 인터넷 대역폭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c715-107">Your offices have adequate Internet bandwidth for Microsoft 365 traffic, including Office 365, Microsoft Intune, and Windows 10 Enterprise installation and updates.</span></span>
- <span data-ttu-id="1c715-108">전체 네트워크가 [Microsoft 365 참조 아키텍처](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2)에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c715-108">Your overall network maps to an [Microsoft 365 reference architecture](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).</span></span>
- <span data-ttu-id="1c715-109">네트워크 변경 사항이 시험 및 테스트되었으며 트래픽 대기 시간 요구 사항을 충족합니다.</span><span class="sxs-lookup"><span data-stu-id="1c715-109">Your network changes have been piloted and tested and meet with your traffic latency requirements.</span></span>

<span data-ttu-id="1c715-110">필요한 경우 [1단계](networking-provide-bandwidth-cloud-services.md)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c715-110">If needed, [Step 1](networking-provide-bandwidth-cloud-services.md) can help you with this requirement.</span></span>

<a name="crit-networking-step2"></a>
## <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a><span data-ttu-id="1c715-111">필수 사항: 지사에 로컬 인터넷 연결 및 이름 확인 구성</span><span class="sxs-lookup"><span data-stu-id="1c715-111">Required: Your local offices have local Internet connections and name resolution</span></span>

<span data-ttu-id="1c715-p101">해당 DNS 서버가 인터넷상의 위치를 식별하는 로컬 공용 IP 주소를 사용하도록 각 지사에 로컬 ISP를 통한 인터넷 액세스를 구성해야 합니다. 이렇게 하면 Microsoft 365 클라우드 서비스에 액세스하는 사용자에 대해 최상의 성능이 보장됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c715-p101">You configured each local office with Internet access with a local ISP whose DNS servers use a local public IP address that identifies their location on the Internet. This ensures the best possible performance for users who access Microsoft 365 cloud services.</span></span>

<span data-ttu-id="1c715-114">각 지사에 로컬 ISP를 사용하지 않으면 네트워크 트래픽이 조직의 백본 또는 원격 프런트 엔드 서버에서 제공하는 데이터 요청을 통과해야 하기 때문에 성능이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c715-114">If you don’t use a local ISP for each branch office, performance can suffer because network traffic must traverse an organization’s backbone or data requests are serviced by remote front-end servers.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="1c715-115">테스트하는 방법</span><span class="sxs-lookup"><span data-stu-id="1c715-115">How to test</span></span>
<span data-ttu-id="1c715-p102">해당 사무실의 장치에서 도구 또는 웹 사이트를 사용하여 프록시 서버가 사용 중인 공용 IP 주소를 확인합니다. 예를 들어 [내 IP 주소](https://www.whatismypublicip.com/) 웹 페이지를 사용합니다. ISP에 의해 할당된 공용 IP 주소는 지리적으로 로컬이어야 하며, 본사의 공용 IP 주소 범위 또는 클라우드 기반 네트워크 보안 공급업체에서 제공되는 것이 아니어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c715-p102">Use a tool or web site from a device in that office to determine the public IP address that the proxy server is using. For example, use the [What Is My IP Address](https://www.whatismypublicip.com/) web page. This public IP address assigned by your ISP should be geographically local. It should not be from a public IP address range for a central office or from a cloud-based network security vendor.</span></span>

<span data-ttu-id="1c715-120">필요한 경우 [2단계](networking-dns-resolution-same-location.md)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c715-120">If needed, [Step 2](networking-dns-resolution-same-location.md) can help you with this requirement.</span></span>

<a name="crit-networking-step3"></a>
## <a name="optional-unnecessary-network-hairpins-are-removed"></a><span data-ttu-id="1c715-121">선택 사항: 불필요한 네트워크 헤어핀 제거</span><span class="sxs-lookup"><span data-stu-id="1c715-121">Optional: Unnecessary network hairpins are removed</span></span>

<span data-ttu-id="1c715-p103">네트워크 헤어핀을 검사하고 모든 사무실의 성능에 미치는 영향을 확인했습니다. 가능한 경우 네트워크 헤어핀을 제거하거나 타사 네트워크 또는 보안 공급자와 함께 네트워크에 대한 최적 Microsoft 365 피어링을 구현했습니다.</span><span class="sxs-lookup"><span data-stu-id="1c715-p103">You examined your network hairpins and determined their impact on performance for all of your offices. You removed network hairpins where possible or worked with your third-party network or security provider to implement optimal Microsoft 365 peering for their network.</span></span>

<span data-ttu-id="1c715-124">필요한 경우 [3단계](networking-avoid-network-hairpins.md)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c715-124">If needed, [Step 3](networking-avoid-network-hairpins.md) can help you with this option.</span></span>


<a name="crit-networking-step4"></a>
## <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a><span data-ttu-id="1c715-125">선택 사항: 인터넷 브라우저 및 에지 장치에 대해 트래픽 바이패스 구성</span><span class="sxs-lookup"><span data-stu-id="1c715-125">Optional: You have configured traffic bypass on your Internet browsers and edge devices</span></span>

<span data-ttu-id="1c715-126">Microsoft 365 DNS 도메인 이름으로의 트래픽이 프록시 서버를 무시하도록 온-프레미스 인터넷 브라우저로 최신 PAC 파일을 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="1c715-126">You deployed the latest PAC files to your on-premises Internet browsers so that traffic to Microsoft 365 DNS domain names bypass proxy servers.</span></span>

<span data-ttu-id="1c715-127">트래픽 바이패스를 사용하거나 Microsoft 365 끝점의 최적화 및 허용 범주로의 트래픽을 최소로 처리하도록 네트워크 경계 장치(예: 방화벽, SSL 중단 및 조사, 패킷 검사 장치)를 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="1c715-127">You configured your network perimeter devices—such as firewalls, and SSL Break and Inspect, and packet inspection devices— to use traffic bypass or to minimally process traffic to the Optimize and Allow categories of Microsoft 365 endpoints.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="1c715-128">테스트 방법</span><span class="sxs-lookup"><span data-stu-id="1c715-128">How to test</span></span>

<span data-ttu-id="1c715-129">네트워크 경계 장치에서 로깅 도구를 사용하여 Microsoft 365 대상에 대해 검사, 암호 해독 또는 기타 방해 작업이 수행되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c715-129">Use the logging tools on your network perimeter devices to ensure that traffic to Microsoft 365 destinations isn’t being inspected, decrypted, or otherwise hindered.</span></span>

<span data-ttu-id="1c715-130">필요한 경우 [4단계](networking-configure-proxies-firewalls.md)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c715-130">If needed, [Step 4](networking-configure-proxies-firewalls.md) can help you with this option.</span></span>


<a name="crit-networking-step5"></a>
## <a name="optional-your-clients-and-microsoft-365-applications-are-configured-for-optimal-performance"></a><span data-ttu-id="1c715-131">선택 사항: 클라이언트와 Microsoft 365 응용 프로그램이 최적의 성능을 발휘하도록 구성됨</span><span class="sxs-lookup"><span data-stu-id="1c715-131">Optional: Your clients and Microsoft 365 applications are configured for optimal performance</span></span>

<span data-ttu-id="1c715-132">Exchange Online, 비즈니스용 Skype Online, SharePoint Online 및 Project Online 서비스에 대해 클라이언트 장치에서 TCP(전송 제어 프로토콜) 설정을 최적화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c715-132">You have optimized the Transmission Control Protocol (TCP) settings on your client devices and for Exchange Online, Skype for Business Online, SharePoint Online, and Project Online services.</span></span>

<span data-ttu-id="1c715-133">필요한 경우 [5단계](networking-optimize-tcp-performance.md)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c715-133">If needed, [Step 5](networking-optimize-tcp-performance.md) can help you with this option.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="1c715-134">결과 및 다음 단계</span><span class="sxs-lookup"><span data-stu-id="1c715-134">Results and next steps</span></span>

<span data-ttu-id="1c715-135">인트라넷 사용자는 이제 인터넷으로의 효율적인 네트워킹 경로를 통해 Microsoft 365 클라우드 서비스를 사용할 준비가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c715-135">Your intranet users are now ready to consume Microsoft 365 cloud services over an efficient networking path to and across the Internet.</span></span>

|||
|:-------|:-----|
|![2단계-ID](../media/deploy-foundation-infrastructure/identity_icon-small.png)| <span data-ttu-id="1c715-137">Microsoft 365 Enterprise의 종단 간 배포 단계를 수행중인 경우 다음 단계는 [ID](identity-infrastructure.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="1c715-137">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [identity](identity-infrastructure.md).</span></span> |
