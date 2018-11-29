---
title: '1단계: 네트워킹 인프라 종료 조건'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 구성이 네트워킹 인프라에 대한 Microsoft 365 Enterprise 조건을 충족하는지 확인합니다.
ms.openlocfilehash: 8161fa2b92ffb4c7c4713e9356c0bc1bfec39d07
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869708"
---
# <a name="phase-1-networking-infrastructure-exit-criteria"></a><span data-ttu-id="ea353-103">1단계: 네트워킹 인프라 종료 조건</span><span class="sxs-lookup"><span data-stu-id="ea353-103">Phase 1: Networking infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="ea353-104">네트워킹 인프라가 다음 조건을 충족하는 경우 2단계로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea353-104">If your networking infrastructure meets the following conditions, you’re ready to move to Phase 2.</span></span>

<a name="crit-networking-step1"></a>
## <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a><span data-ttu-id="ea353-105">필수 사항: 네트워크에서 Microsoft 365 Enterprise 사용 준비 완료</span><span class="sxs-lookup"><span data-stu-id="ea353-105">Required: Your network is ready for Microsoft 365 Enterprise</span></span>

- <span data-ttu-id="ea353-106">사무실에 Office 365, Microsoft Intune, Windows 10 Enterprise 설치 및 업데이트를 포함하여 Microsoft 365 트래픽에 적합한 인터넷 대역폭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea353-106">Your offices have adequate Internet bandwidth for Microsoft 365 traffic, including Office 365, Microsoft Intune, Windows 10 Enterprise installation and updates</span></span>
- <span data-ttu-id="ea353-107">모든 일반 인터넷 트래픽을 위한 중앙 사무실</span><span class="sxs-lookup"><span data-stu-id="ea353-107">Central offices for all general Internet traffic</span></span>
- <span data-ttu-id="ea353-108">범주 끝점 트래픽을 최적화하기 위한 지사</span><span class="sxs-lookup"><span data-stu-id="ea353-108">Branch offices for Optimize category endpoint traffic</span></span>
- <span data-ttu-id="ea353-109">전체 네트워크가 Office 365 참조 아키텍처에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea353-109">Your overall network maps to an Office 365 reference architecture</span></span>

<span data-ttu-id="ea353-110">필요한 경우 [1단계](networking-provide-bandwidth-cloud-services.md)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea353-110">If needed, [Step 1](networking-provide-bandwidth-cloud-services.md) can help you with this requirement.</span></span>

<a name="crit-networking-step2"></a>
## <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a><span data-ttu-id="ea353-111">필수 사항: 지사에 로컬 인터넷 연결 및 이름 확인 구성</span><span class="sxs-lookup"><span data-stu-id="ea353-111">Required: Your local offices have local Internet connections and name resolution</span></span>

<span data-ttu-id="ea353-p101">해당 DNS 서버가 인터넷상의 위치를 식별하는 로컬 공용 IP 주소를 사용하도록 각 지사에 로컬 ISP를 통한 인터넷 액세스를 구성해야 합니다. 이렇게 하면 Office 365 및 Intune에 액세스하는 사용자에 대해 최상의 성능이 보장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea353-p101">You configured each local office with Internet access with a local ISP whose DNS servers use a local public IP address that identifies their location on the Internet. This ensures the best possible performance for users who access Office 365 and Intune.</span></span>

<span data-ttu-id="ea353-114">각 지사에 로컬 ISP를 사용하지 않으면 네트워크 트래픽이 조직의 백본 또는 원격 프런트 엔드 서버에서 제공하는 데이터 요청을 통과해야 하기 때문에 성능이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea353-114">If you don’t use a local ISP for each branch office, performance can suffer because network traffic must traverse an organization’s backbone or data requests are serviced by remote front-end servers.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="ea353-115">테스트하는 방법</span><span class="sxs-lookup"><span data-stu-id="ea353-115">How to test</span></span>
<span data-ttu-id="ea353-p102">해당 사무실의 장치에서 도구 또는 웹 사이트를 사용하여 프록시 서버가 사용 중인 공용 IP 주소를 확인합니다. 예를 들어 [내 IP 주소](https://www.whatismypublicip.com/) 웹 페이지를 사용합니다. ISP에 의해 할당된 공용 IP 주소는 지리적으로 로컬이어야 하며, 본사의 공용 IP 주소 범위 또는 클라우드 기반 네트워크 보안 공급업체에서 제공되는 것이 아니어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea353-p102">Use a tool or web site from a device in that office to determine the public IP address that the proxy server is using. For example, use the [What Is My IP Address](https://www.whatismypublicip.com/) web page. This public IP address assigned by your ISP should be geographically local. It should not be from a public IP address range for a central office or from a cloud-based network security vendor.</span></span>

<span data-ttu-id="ea353-120">필요한 경우 [2단계](networking-dns-resolution-same-location.md)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea353-120">If needed, [Step 2](networking-dns-resolution-same-location.md) can help you with this requirement.</span></span>

<a name="crit-networking-step3"></a>
## <a name="optional-unneeded-network-hairpins-are-removed"></a><span data-ttu-id="ea353-121">선택 사항: 불필요한 네트워크 헤어핀 제거</span><span class="sxs-lookup"><span data-stu-id="ea353-121">Optional: Unneeded network hairpins are removed</span></span>

<span data-ttu-id="ea353-p103">네트워크 헤어핀을 검사하고 모든 사무실의 성능에 미치는 영향을 확인했습니다. 가능한 경우 네트워크 헤어핀을 제거하거나 타사 네트워크 또는 보안 공급자와 함께 네트워크에 대한 최적 Microsoft 365 피어링을 구현했습니다.</span><span class="sxs-lookup"><span data-stu-id="ea353-p103">You examined your network hairpins and determined their impact on performance for all of your offices. You removed network hairpins where possible or worked with your third-party network or security provider to implement optimal Microsoft 365 peering for their network.</span></span>

<span data-ttu-id="ea353-124">필요한 경우 [3단계](networking-avoid-network-hairpins.md)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea353-124">If needed, [Step 3](networking-avoid-network-hairpins.md) can help you with this option.</span></span>


<a name="crit-networking-step4"></a>
## <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a><span data-ttu-id="ea353-125">선택 사항: 인터넷 브라우저 및 에지 장치에 대해 트래픽 바이패스 구성</span><span class="sxs-lookup"><span data-stu-id="ea353-125">Optional: You have configured traffic bypass on your Internet browsers and edge devices</span></span>

<span data-ttu-id="ea353-126">Microsoft 365 DNS 도메인 이름으로의 트래픽이 프록시 서버를 무시하도록 온-프레미스 인터넷 브라우저로 최신 PAC 파일을 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="ea353-126">You deployed the latest PAC files to your on-premises Internet browsers so that traffic to Microsoft 365 DNS domain names bypass proxy servers.</span></span>

<span data-ttu-id="ea353-127">트래픽 바이패스를 사용하거나 Microsoft 365 끝점의 최적화 및 허용 범주로의 트래픽을 최소로 처리하도록 네트워크 경계 장치(예: 방화벽, SSL 중단 및 조사, 패킷 검사 장치)를 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="ea353-127">You configured your network perimeter devices—such as firewalls, and SSL Break and Inspect, and packet inspection devices— to use traffic bypass or to minimally process traffic to the Optimize and Allow categories of Microsoft 365 endpoints.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="ea353-128">테스트 방법</span><span class="sxs-lookup"><span data-stu-id="ea353-128">How to test</span></span>

<span data-ttu-id="ea353-129">네트워크 경계 장치에서 로깅 도구를 사용하여 Microsoft 365 대상에 대해 검사, 암호 해독 또는 기타 방해 작업이 수행되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ea353-129">Use the logging tools on your network perimeter devices to ensure that traffic to Microsoft 365 destinations isn’t being inspected, decrypted, or otherwise hindered.</span></span>

<span data-ttu-id="ea353-130">필요한 경우 [4단계](networking-configure-proxies-firewalls.md)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea353-130">If needed, [Step 4](networking-configure-proxies-firewalls.md) can help you with this option.</span></span>


<a name="crit-networking-step5"></a>
## <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a><span data-ttu-id="ea353-131">선택: 최적 성능을 위해 클라이언트 및 Office 365 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="ea353-131">Optional: Your clients and Office 365 applications are configured for optimal performance</span></span>

<span data-ttu-id="ea353-132">Exchange Online, 비즈니스용 Skype Online, SharePoint Online 및 Project Online 서비스에 대해 클라이언트 장치에서 TCP(전송 제어 프로토콜) 설정을 최적화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea353-132">You have optimized the Transmssion Control Protocol (TCP) settings on your client devices and for Exchange Online, Skype for Business Online, SharePoint Online, and Project Online services.</span></span>

<span data-ttu-id="ea353-133">필요한 경우 [5단계](networking-optimize-tcp-performance.md)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea353-133">If needed, [Step 5](networking-optimize-tcp-performance.md) can help you with this option.</span></span>

## <a name="next-phase"></a><span data-ttu-id="ea353-134">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ea353-134">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)| <span data-ttu-id="ea353-135">Microsoft 365 Enterprise에 대한 종단 간 배포 프로세스의 다음 단계는 [ID](identity-infrastructure.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="ea353-135">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [identity](identity-infrastructure.md).</span></span> |
