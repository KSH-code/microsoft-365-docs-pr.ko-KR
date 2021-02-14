---
title: Office 365 서비스에 연결되는 네트워크 장치 계획
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 073433ca-3511-4db9-b173-7a2edca57691
description: '요약: Office 365에 연결하는 데 사용되는 네트워크 용량, WAN 가속기 및 부하 분산 장치에 대한 고려 사항을 제공합니다.'
ms.openlocfilehash: a4ea75eb294d74004125be4d258dbe86d7d89810
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692539"
---
# <a name="plan-for-network-devices-that-connect-to-office-365-services"></a><span data-ttu-id="0124f-103">Office 365 서비스에 연결되는 네트워크 장치 계획</span><span class="sxs-lookup"><span data-stu-id="0124f-103">Plan for network devices that connect to Office 365 services</span></span>

<span data-ttu-id="0124f-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="0124f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>
  
<span data-ttu-id="0124f-105">일부 네트워크 하드웨어에는 지원되는 동시 세션 수에 제한이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-105">Some network hardware may have limitations on the number of concurrent sessions that are supported.</span></span> <span data-ttu-id="0124f-106">사용자가 2,000명 이상인 조직의 경우 네트워크 장치를 모니터링하여 추가 Office 365 서비스 트래픽을 처리할 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-106">For organizations having more than 2,000 users, we recommend that they monitor their network devices to ensure they are capable of handling the additional Office 365 service traffic.</span></span> <span data-ttu-id="0124f-107">SNMP(Simple Network Management Protocol) 모니터링 소프트웨어를 사용하면 이 작업을 쉽게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-107">Simple Network Management Protocol (SNMP) monitoring software can help you do this.</span></span>

<span data-ttu-id="0124f-108">이 문서는 [Office 365에](https://aka.ms/tune)대한 네트워크 계획 및 성능 조정의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-108">This article is part of [Network planning and performance tuning for Office 365](https://aka.ms/tune).</span></span>

<span data-ttu-id="0124f-109">또한 클라이언트 응용 프로그램의 Office 365 서비스에 대한 연결에 영향을 주는 프레미스 아웃소드 인터넷 프록시 설정도 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-109">On-premises outgoing Internet proxy settings also affect connectivity to Office 365 services for your client applications.</span></span> <span data-ttu-id="0124f-110">또한 Microsoft 클라우드 서비스 URL 및 응용 프로그램에 대한 연결을 허용하도록 네트워크 프록시 장치를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-110">You must also configure your network proxy devices to allow connections for Microsoft cloud services URLs and applications.</span></span> <span data-ttu-id="0124f-111">조직마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-111">Every organization is different.</span></span> <span data-ttu-id="0124f-112">Microsoft에서 이 프로세스를 관리하는 방법과 프로비전하는 대역폭의 양에 대한 아이디어를 얻습니다. 사례 [연구를 읽어 읽습니다.](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)</span><span class="sxs-lookup"><span data-stu-id="0124f-112">To get an idea for how Microsoft manages this process and the amount of bandwidth we provision, [read the case study](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).</span></span>
  
<span data-ttu-id="0124f-113">다음 비즈니스용 Skype 도움말 문서에는 비즈니스용 Skype 설정에 대한 자세한 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-113">The following Skype for Business Help articles have more information about Skype for Business settings:</span></span>
  
- [<span data-ttu-id="0124f-114">관리자를 위한 비즈니스용 Skype Online 로그인 오류 문제 해결</span><span class="sxs-lookup"><span data-stu-id="0124f-114">Troubleshooting Skype for Business Online sign-in errors for administrators</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/troubleshooting-sign-in-errors-for-admins)

- [<span data-ttu-id="0124f-115">비즈니스용 Skype에 연결할 수 없는 경우 또는 특정 기능이 작동하지 않는 경우,프레미스 방화벽에서 연결을 차단하기 때문에</span><span class="sxs-lookup"><span data-stu-id="0124f-115">You cannot connect to Skype for Business, or certain features do not work, because an on-premises firewall blocks the connection</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=243625)

> [!NOTE]
> <span data-ttu-id="0124f-116">이러한 설정 중 상당수는 비즈니스용 Skype 관련 설정이지만 네트워크 구성에 대한 일반적인 지침은 모든 Office 365 서비스에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-116">While many of these settings are Skype for Business-specific, the general guidance on network configuration is useful for all Office 365 services.</span></span>
  
## <a name="determining-network-capacity"></a><span data-ttu-id="0124f-117">네트워크 용량 결정</span><span class="sxs-lookup"><span data-stu-id="0124f-117">Determining Network Capacity</span></span>

<span data-ttu-id="0124f-118">연결에 있는 모든 네트워크 장치에는 용량 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-118">Every network device that exists on a connection has its capacity limit.</span></span> <span data-ttu-id="0124f-119">이러한 장치에는 상호 연결된 클라이언트 및 서버 네트워크 어댑터, 라우터, 스위치 및 허브가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-119">These devices include the client and server network adapters, routers, switches, and hubs that interconnect them.</span></span> <span data-ttu-id="0124f-120">적절한 네트워크 용량은 그 어느 것도 포화 상태가 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-120">Adequate network capacity means that none of them are saturated.</span></span> <span data-ttu-id="0124f-121">네트워크 작업 모니터링은 모든 네트워크 장치의 실제 부하가 최대 용량 미만이 되도록 하는 데 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-121">Monitoring network activity is essential to help ensure that the actual loads on all network devices are less than their maximum capacity.</span></span> <span data-ttu-id="0124f-122">네트워크 용량은 프록시 장치 성능에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-122">Network capacity affects proxy device performance.</span></span>
  
<span data-ttu-id="0124f-123">대부분의 경우 인터넷 연결 대역폭은 트래픽 양에 대한 제한을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-123">In most situations, the Internet connection bandwidth sets the limit for the amount of traffic.</span></span> <span data-ttu-id="0124f-124">트래픽이 많은 시간 동안 성능이 약한 원인은 인터넷 링크를 과도하게 사용하기 때문에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-124">Weak performance during peak traffic hours is probably caused by excessive use of the Internet link.</span></span> <span data-ttu-id="0124f-125">이 상황은 저속 WAN(Wide Area Network) 링크를 통해 지점의 본사에 있는 프록시 장치에 지점 프록시 서버 컴퓨터가 연결된 지점 시나리오에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-125">This situation also applies to a branch office scenario, where branch office proxy server computers are connected to the proxy device at the branch's headquarters over a slow Wide Area Network (WAN) link.</span></span>
  
<span data-ttu-id="0124f-126">네트워크 용량을 테스트하기 위해 프록시 네트워크 인터페이스에서 네트워크 활동을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-126">To test network capacity, monitor the network activity on the proxy network interface.</span></span> <span data-ttu-id="0124f-127">네트워크 인터페이스의 최대 대역폭의 75%를 초과하는 경우 네트워크 인프라의 대역폭을 늘리는 것이 부적절한 경우를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-127">If it's more than 75 percent of the maximum bandwidth of any network interface, consider increasing the bandwidth of the network infrastructure that's inadequate.</span></span> <span data-ttu-id="0124f-128">또는 HTTP 압축과 같은 고급 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-128">Or, consider using advanced features, such as HTTP compression.</span></span>
  
## <a name="wan-accelerators"></a><span data-ttu-id="0124f-129">WAN 가속기</span><span class="sxs-lookup"><span data-stu-id="0124f-129">WAN Accelerators</span></span>

<span data-ttu-id="0124f-130">조직에서 WAN(Wide Area Network) 가속 프록시 어플라이언스를 사용하는 경우 Office 365 서비스에 액세스할 때 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-130">If your organization uses wide area network (WAN) acceleration proxy appliances, you may encounter issues when you access the Office 365 services.</span></span> <span data-ttu-id="0124f-131">사용자가 Office 365에 액세스할 때 일관된 환경을 제공하도록 네트워크 장치 또는 장치를 최적화해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-131">You may need to optimize your network device or devices to ensure that your users have a consistent experience when accessing Office 365.</span></span> <span data-ttu-id="0124f-132">예를 들어 Office 365 서비스는 일부 Office 365 콘텐츠와 TCP 헤더를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-132">For example, Office 365 services encrypt some Office 365 content and the TCP header.</span></span> <span data-ttu-id="0124f-133">디바이스가 이러한 종류의 트래픽을 처리하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-133">Your device may not be able to handle this kind of traffic.</span></span>
  
<span data-ttu-id="0124f-134">[Office 365에서 WAN](https://support.microsoft.com/kb/2690045)최적화 컨트롤러 또는 트래픽/검사 장치 사용에 대한 지원 설명을 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-134">Read our support statement about [Using WAN Optimization Controller or Traffic/Inspection devices with Office 365](https://support.microsoft.com/kb/2690045).</span></span>
  
## <a name="hardware-and-software-load-balancing-devices"></a><span data-ttu-id="0124f-135">하드웨어 및 소프트웨어 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="0124f-135">Hardware and Software Load-balancing Devices</span></span>

<span data-ttu-id="0124f-136">조직에서는 HLB(하드웨어 부하 분산) 또는 NLB(네트워크 부하 분산) 솔루션을 사용하여 AD FS(Active Directory Federation Services) 서버 및/또는 Exchange 하이브리드 서버로 요청을 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-136">Your organization needs to use a hardware load balancer (HLB) or a Network Load Balancing (NLB) solution to distribute requests to your Active Directory Federation Services (AD FS) servers and/or your Exchange hybrid servers.</span></span> <span data-ttu-id="0124f-137">부하 분산 장치는 네트워크에 대한 트래픽을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-137">Load-balancing devices control the network traffic to the on-premises servers.</span></span> <span data-ttu-id="0124f-138">이러한 서버는 Single Sign-On 및 Exchange 하이브리드 배포의 가용성을 보장하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-138">These servers are crucial in helping to ensure the availability of single sign-on and Exchange hybrid deployment.</span></span>
  
<span data-ttu-id="0124f-139">Windows Server에 기본 제공되는 소프트웨어 기반 NLB 솔루션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-139">We provide a software-based NLB solution built into Windows Server.</span></span> <span data-ttu-id="0124f-140">Office 365는 부하 분산을 위해 이 솔루션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-140">Office 365 supports this solution to achieve load balancing.</span></span>
  
## <a name="firewalls-and-proxies"></a><span data-ttu-id="0124f-141">방화벽 및 Proxies</span><span class="sxs-lookup"><span data-stu-id="0124f-141">Firewalls and proxies</span></span>

<span data-ttu-id="0124f-142">Office 365에 연결하기 위한 방화벽 및 팩스 구성에 대한 자세한 내용은 Office 365 끝점 관리, [Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)네트워크 연결 평가 및 Office [365](assessing-network-connectivity.md)끝점 [FAQ를](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) 읽어 장치 및 회로 선택에 대한 자세한 내용을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0124f-142">For more details on configuring firewalls and proxies to connect to Office 365, read [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), [Assessing Office 365 network connectivity](assessing-network-connectivity.md), and [Office 365 endpoints FAQ](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) to learn more about devices and circuit selection.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0124f-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0124f-143">See also</span></span>

[<span data-ttu-id="0124f-144">Office 365 서비스에 대한 설치 가이드</span><span class="sxs-lookup"><span data-stu-id="0124f-144">Setup guides for Office 365 services</span></span>](setup-guides-for-microsoft-365.md)

[<span data-ttu-id="0124f-145">Microsoft 365 Enterprise 개요</span><span class="sxs-lookup"><span data-stu-id="0124f-145">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
