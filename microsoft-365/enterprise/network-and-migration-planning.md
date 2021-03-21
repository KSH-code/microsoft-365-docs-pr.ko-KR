---
title: Office 365의 네트워크 및 마이그레이션 계획
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: 이 문서에는 네트워크 계획, 테스트 및 Office 365로의 마이그레이션에 대한 정보의 링크가 포함되어 있습니다.
ms.openlocfilehash: 99bcc1bd0447b192860fc0bcc67fc18d87c2d5fc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923591"
---
# <a name="network-and-migration-planning-for-office-365"></a><span data-ttu-id="5566a-103">Office 365의 네트워크 및 마이그레이션 계획</span><span class="sxs-lookup"><span data-stu-id="5566a-103">Network and migration planning for Office 365</span></span>

<span data-ttu-id="5566a-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="5566a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5566a-105">이 문서에는 네트워크 계획 및 테스트, Office 365로의 마이그레이션에 대한 정보의 링크가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-105">This article contains links to information about network planning and testing, and migration to Office 365.</span></span>
  
<span data-ttu-id="5566a-106">Office 365로 처음 배포하거나 Office 365로 마이그레이션하기 전에 이러한 항목의 정보를 사용하여 필요한 대역폭을 예측한 다음 Office 365로 배포하거나 마이그레이션하기에 충분한 대역폭이 있는지 테스트하고 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-106">Before you deploy for the first time or migrate to Office 365, you can use the information in these topics to estimate the bandwidth you need and then to test and verify that you have enough bandwidth to deploy or migrate to Office 365.</span></span>

<span data-ttu-id="5566a-107">이 문서는 [Office 365에](./network-planning-and-performance.md)대한 네트워크 계획 및 성능 조정의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-107">This article is part of [Network planning and performance tuning for Office 365](./network-planning-and-performance.md).</span></span>

<span data-ttu-id="5566a-108">Microsoft 365 및 기타 Microsoft 클라우드 플랫폼 및 서비스에 맞게 네트워크를 최적화하는 단계는 [Microsoft Cloud Networking for Enterprise Architects 포스터를 참조하세요.](../solutions/cloud-architecture-models.md)</span><span class="sxs-lookup"><span data-stu-id="5566a-108">For the steps to optimize your network for Microsoft 365 and other Microsoft cloud platforms and services, see the [Microsoft Cloud Networking for Enterprise Architects](../solutions/cloud-architecture-models.md) poster.</span></span>
   
## <a name="estimate-network-bandwidth-requirements"></a><span data-ttu-id="5566a-109">네트워크 대역폭 요구 사항 예측</span><span class="sxs-lookup"><span data-stu-id="5566a-109">Estimate network bandwidth requirements</span></span>
<span data-ttu-id="5566a-110"><a name="EstimateBandwidthRequirements"> </a></span><span class="sxs-lookup"><span data-stu-id="5566a-110"><a name="EstimateBandwidthRequirements"> </a></span></span>

<span data-ttu-id="5566a-111">Office 365를 사용하는 경우 조직의 인터넷 회로 사용률이 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-111">Using Office 365 may increase the utilization of your organization's internet circuit.</span></span> <span data-ttu-id="5566a-112">Office 365가 완전히 배포된 후 현재 사용 가능한 대역폭의 양이 사용량이 가장 많은 일 수를 처리할 수 있는 용량의 20% 이상을 남겨 두면 예상 증가를 처리할 수 있는지 확인하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-112">It's important to determine if the amount of bandwidth currently available is enough to handle the estimated increase once Office 365 is fully deployed while leaving at least 20% capacity to handle the busiest of days.</span></span>
  
<span data-ttu-id="5566a-113">대역폭을 예측하기 위해 다음 단계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-113">To estimate the bandwidth, use the following steps:</span></span>
  
1. <span data-ttu-id="5566a-114">각 인터넷 연결을 사용할 클라이언트 수를 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-114">Assess the number of clients that will use each Internet egress.</span></span> <span data-ttu-id="5566a-115">다중 테라비트 네트워크에서 가능한 한 많은 연결을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-115">Let our multi-terabit network handle as much of the connection as possible.</span></span> 
    
2. <span data-ttu-id="5566a-116">클라이언트에서 사용할 수 있는 Office 365 서비스 및 기능을 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="5566a-116">Determine which Office 365 services and features will be available for clients to use.</span></span> <span data-ttu-id="5566a-117">서비스 또는 사용 프로필이 다른 사용자 그룹이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-117">You will likely have groups of people with different services or usage profiles.</span></span>
    
3. <span data-ttu-id="5566a-118">파일럿 클라이언트 그룹에 대한 네트워크 사용을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-118">Measure the network use for a pilot group of clients.</span></span> <span data-ttu-id="5566a-119">파일럿 클라이언트가 조직의 여러 사용자 프로필과 다양한 지리적 위치를 대표하는지 확인</span><span class="sxs-lookup"><span data-stu-id="5566a-119">Ensure the pilot clients are representative of the different profiles of people in the organization as well as the different geographic locations.</span></span> <span data-ttu-id="5566a-120">Exchange 및 [Microsoft Teams용](/microsoftteams/prepare-network) 이전 계산기 [](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744) 또는 자체 네트워크에서 수행한 사례 연구에 대해 결과를 교차 확인할 수 있습니다. [](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)</span><span class="sxs-lookup"><span data-stu-id="5566a-120">You can cross-check your results against our old calculators for [Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744) and [Microsoft Teams](/microsoftteams/prepare-network) or the [case study](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365) we performed on our own network.</span></span> 
    
4. <span data-ttu-id="5566a-121">파일럿 그룹의 측정값을 사용하여 전체 조직의 요구 사항을 추정하고 다시 테스트하여 네트워크를 변경하기 전에 예측의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-121">Use the measurements from the pilot group to extrapolate the entire organization's needs and re-test to validate the estimations before making any changes to your network.</span></span>
    
## <a name="test-your-existing-network"></a><span data-ttu-id="5566a-122">기존 네트워크 테스트</span><span class="sxs-lookup"><span data-stu-id="5566a-122">Test your existing network</span></span>
<span data-ttu-id="5566a-123"><a name="calculators"> </a></span><span class="sxs-lookup"><span data-stu-id="5566a-123"><a name="calculators"> </a></span></span>

 <span data-ttu-id="5566a-124">**네트워크 도구.**</span><span class="sxs-lookup"><span data-stu-id="5566a-124">**Network tools.**</span></span> <span data-ttu-id="5566a-125">인터넷 대역폭을 테스트하고 유효성을 검사하여 다운로드, 업로드 및 대기 시간 제약 조건을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-125">Test and validate your Internet bandwidth to determine download, upload, and latency constraints.</span></span> <span data-ttu-id="5566a-126">이러한 도구는 완전히 배포된 후뿐만 아니라 마이그레이션을 위한 네트워크의 기능을 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-126">These tools will help you determine the capabilities of your network for migration as well as after you're fully deployed.</span></span> 
    
- <span data-ttu-id="5566a-127">[Microsoft 원격 연결 분석기:](https://go.microsoft.com/fwlink/p/?LinkId=517243)Exchange Online 환경에서 연결을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-127">[Microsoft Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=517243): Tests connectivity in your Exchange Online environment.</span></span>
    
- <span data-ttu-id="5566a-128">Office [365용 Microsoft 지원 및](https://diagnostics.office.com/#/Download?env=SOC) 복구 도우미를 사용하여 Outlook 및 Office 365 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-128">Use the [Microsoft Support and Recovery Assistant for Office 365](https://diagnostics.office.com/#/Download?env=SOC) to fix Outlook and Office 365 problems.</span></span> 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a><span data-ttu-id="5566a-129">Office 365의 네트워크 계획 및 마이그레이션 성능 개선을 위한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="5566a-129">Best practices for network planning and improving migration performance for Office 365</span></span>
<span data-ttu-id="5566a-130"><a name="BestPractices"> </a></span><span class="sxs-lookup"><span data-stu-id="5566a-130"><a name="BestPractices"> </a></span></span>

<span data-ttu-id="5566a-131">Office 365 환경 개선에 대한 자세한 내용은 이러한 모범 사례에 대해 좀 더 깊이 파고들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-131">Dig a little deeper into these best practices for more information about improving your Office 365 experience.</span></span>
  
1. <span data-ttu-id="5566a-132">사용자를 바로 지원하기 시작하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="5566a-132">Want to get started helping your users right away?</span></span> <span data-ttu-id="5566a-133">네트워크가 공조되지 않는 경우 SharePoint Online, Exchange Online 및 Lync Online을 비롯한 Office 365 사용에 대한 팁은 느린 네트워크에서 [Office 365를](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) 사용하는 모범 사례를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5566a-133">See [Best practices for using Office 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) for tips on using Office 365, including SharePoint Online, Exchange Online, and Lync Online, when your network just isn't cooperating.</span></span> <span data-ttu-id="5566a-134">이 문서는 Office 365 환경을 최적화하기 위해 TechNet 및 Support.office.com 콘텐츠 로드에 연결하고 웹 페이지를 사용자 지정하는 쉬운 방법과 최상의 Office 365 환경을 위해 Internet Explorer 설정을 지정하는 방법에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-134">This article links out to loads of content on TechNet and Support.office.com for optimizing your Office 365 experience and includes information on easy ways to customize your web pages and how to set your Internet Explorer settings for the best Office 365 experience.</span></span> 
    
2. <span data-ttu-id="5566a-135">[Office 365 네트워크](./microsoft-365-network-connectivity-principles.md) 연결 원칙을 읽고 Office 365 트래픽을 안전하게 관리하고 최상의 성능을 확보하기 위한 연결 원칙을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-135">Read [Office 365 Network Connectivity Principles](./microsoft-365-network-connectivity-principles.md) to understand the connectivity principles for securely managing Office 365 traffic and getting the best possible performance.</span></span> <span data-ttu-id="5566a-136">이 문서는 Office 365 네트워크 연결을 안전하게 최적화하기 위한 최신 가이드를 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-136">This article will help you understand the most recent guidance for securely optimizing Office 365 network connectivity.</span></span> 
    
3. <span data-ttu-id="5566a-137">Windows 업데이트 일정을 신중하게 관리하여 메일 마이그레이션 성능을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-137">Improve mail migration performance by carefully managing the schedule for Windows Updates.</span></span> <span data-ttu-id="5566a-138">클라이언트 컴퓨터를 일괄적으로 업데이트하고 네트워크 대역폭 사용을 규제하기 위해 Office 365로 마이그레이션하기 전에 모든 클라이언트 컴퓨터를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-138">You can update your client computers in batches and ensure that all client computers are updated before migrating to Office 365 to regulate the use of network bandwidth.</span></span> <span data-ttu-id="5566a-139">자세한 내용은 최신 업데이트에 대한 Office 365 데스크톱 수동 업데이트 및 [구성을 참조하세요.](https://support.microsoft.com/gp/office-2013-365-update)</span><span class="sxs-lookup"><span data-stu-id="5566a-139">For more information, see [Manually update and configure desktops for Office 365 for the latest updates](https://support.microsoft.com/gp/office-2013-365-update).</span></span>
    
4. <span data-ttu-id="5566a-140">Office 365 네트워크 트래픽은 신뢰할 수 있는 인터넷 서비스로 취급되어 일부 조직이 신뢰할 수 없는 인터넷 서비스에 대한 네트워크 트래픽에 적용하는 기존의 필터링 및 검색을 무시할 수 있는 경우 가장 잘 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-140">Office 365 network traffic performs best when it's treated as a trusted Internet service and allowed to bypass much of the traditional filtering and scanning that some organizations place on network traffic to untrusted Internet services.</span></span> <span data-ttu-id="5566a-141">여기에는 일반적으로 프록시 사용자 인증 및 패킷 검사와 같은 아웃바운드 처리가 제거될 뿐만 아니라, 적절한 NAT(Network Address Translation) 및 증가하는 네트워크 요청을 처리할 수 있는 충분한 대역폭 용량을 사용하여 인터넷으로 로컬로 전송하도록 보장하는 작업도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-141">This typically includes removing outbound processing such as proxy user authentication and packet inspection, as well as ensuring local egress to the Internet with the proper Network Address Translation (NAT) and enough bandwidth capacity to handle the increased network requests.</span></span> <span data-ttu-id="5566a-142">Office [365를](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)네트워크에서 신뢰할 수 있는 인터넷 서비스로 처리하기 위해 네트워크를 구성하는 방법에 대한 추가 지침은 Office 365 끝점 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5566a-142">Refer to [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)for additional guidance on configuring your network to handle Office 365 as a trusted Internet service on your network.</span></span>
    
1. <span data-ttu-id="5566a-143">[Office 365 끝점 관리를 보장합니다.](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)</span><span class="sxs-lookup"><span data-stu-id="5566a-143">Ensure [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span></span> <span data-ttu-id="5566a-144">Office 365로의 트래픽이 늘어나면 아웃바운드 프록시 연결이 증가하고 TLS/SSL을 통해 보안 트래픽이 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-144">The additional traffic going to Office 365 results in an increase of outbound proxy connections as well as an increase in secure traffic over TLS/SSL.</span></span>
    
2. <span data-ttu-id="5566a-145">아웃바운드 Proxy에 사용자 인증이 필요한 경우 연결 속도가 느려지거나 기능이 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-145">If your outbound proxies require user authentication you may experience slow connectivity or a loss of functionality.</span></span> <span data-ttu-id="5566a-146">Office 365 도메인에 대한 인증 요구 사항을 무시하면 이 오버헤드를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-146">Bypassing the authentication requirement for the Office 365 domains can reduce this overhead.</span></span>
    
3. <span data-ttu-id="5566a-147">공유 일정 및 사서함 수가 많은 경우 Outlook에서 Exchange로의 연결 수가 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-147">If you have a large number of shared calendars and mailboxes, you may see an increase in the number of connections from Outlook to Exchange.</span></span> <span data-ttu-id="5566a-148">예를 들어 Outlook 클라이언트는 사용 중인 각 공유 일정에 대해 최대 두 개의 추가 연결을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-148">For instance, the Outlook client may open up to two additional connections for each shared calendar in use.</span></span> <span data-ttu-id="5566a-149">이 경우, 연결 프록시가 연결을 처리하거나 Outlook용 Office 365에 대한 연결을 위해 프록시를 무시할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-149">In this situation, ensure that the egress proxy can handle the connections, or bypass the proxy for connections to Office 365 for Outlook.</span></span>
    
4. <span data-ttu-id="5566a-150">공용 IP 주소에 대해 지원되는 최대 장치 수와 여러 IP 주소에서 부하를 분산하는 방법을 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="5566a-150">Determine the maximum number of supported devices for a public IP address and how to load balance across multiple IP addresses.</span></span> <span data-ttu-id="5566a-151">자세한 내용은 [Office 365를 통해 NAT 지원을 참조하세요.](nat-support-with-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="5566a-151">For more information, see [NAT support with Office 365](nat-support-with-microsoft-365.md).</span></span>
    
5. <span data-ttu-id="5566a-152">네트워크의 컴퓨터에서 아웃바운드 연결을 검사하는 경우 이 필터링을 Office 365 도메인으로 무시하면 연결 및 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-152">If you're inspecting outbound connections from computers on your network, bypassing this filtering to the Office 365 domains will improve connectivity and performance.</span></span> <span data-ttu-id="5566a-153">또한 아웃바운드 검사를 무시하면 단일 인터넷에 대한 필요성이 제거될 수 있으며 Office 365로 예정된 네트워크 요청에 대해 로컬 인터넷을 유출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-153">Additionally, bypassing outbound inspection often removes the need for a single Internet egress and enables local Internet egress for Office 365 destined network requests.</span></span>
    
6. <span data-ttu-id="5566a-154">일부 고객은 내부 네트워크 설정이 성능에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-154">Some customers find internal network settings may affect performance.</span></span> <span data-ttu-id="5566a-155">MTU(최대 전송 단위) 크기, 네트워크 자동 협상 또는 자동 검색, 인터넷에 대한 최적 경로와 같은 설정은 일반적으로 볼 수 있는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-155">Settings such as maximum transmission unit (MTU) size, network auto-negotiation or auto-detection, and sub-optimal routes to the Internet are common places to look.</span></span>
    
## <a name="network-planning-reference-for-office-365"></a><span data-ttu-id="5566a-156">Office 365에 대한 네트워크 계획 참조</span><span class="sxs-lookup"><span data-stu-id="5566a-156">Network planning reference for Office 365</span></span>
<span data-ttu-id="5566a-157"><a name="NetReference"> </a></span><span class="sxs-lookup"><span data-stu-id="5566a-157"><a name="NetReference"> </a></span></span>

<span data-ttu-id="5566a-158">이러한 항목에는 자세한 Office 365 네트워크 참조 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5566a-158">These topics contain detailed Office 365 network reference information.</span></span>
  
- [<span data-ttu-id="5566a-159">Office 365 끝점 관리</span><span class="sxs-lookup"><span data-stu-id="5566a-159">Managing Office 365 endpoints</span></span>](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [<span data-ttu-id="5566a-160">콘텐츠 배달 네트워크</span><span class="sxs-lookup"><span data-stu-id="5566a-160">Content delivery networks</span></span>](content-delivery-networks.md)
    
- [<span data-ttu-id="5566a-161">Office 365에 대한 외부 Domain Name System 레코드</span><span class="sxs-lookup"><span data-stu-id="5566a-161">External Domain Name System records for Office 365</span></span>](external-domain-name-system-records.md)
    
- [<span data-ttu-id="5566a-162">Office 365 서비스의 IPv6 지원</span><span class="sxs-lookup"><span data-stu-id="5566a-162">IPv6 support in Office 365 services</span></span>](ipv6-support.md)
    
- [<span data-ttu-id="5566a-163">Office 365 네트워크 연결 원칙</span><span class="sxs-lookup"><span data-stu-id="5566a-163">Office 365 Network Connectivity Principles</span></span>](./microsoft-365-network-connectivity-principles.md)
    
- [<span data-ttu-id="5566a-164">Office 365 비디오 네트워킹 FAQ(질문과 대답)</span><span class="sxs-lookup"><span data-stu-id="5566a-164">Office 365 video networking Frequently Asked Questions (FAQ)</span></span>](office-365-video-networking-faq.md)
    
- [<span data-ttu-id="5566a-165">Office 365 서비스에 연결되는 네트워크 장치 계획</span><span class="sxs-lookup"><span data-stu-id="5566a-165">Plan for network devices that connect to Office 365 services</span></span>](plan-for-network-devices.md)
    
- [<span data-ttu-id="5566a-166">Office 365 서비스의 설치 가이드</span><span class="sxs-lookup"><span data-stu-id="5566a-166">Setup guides for Office 365 services</span></span>](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a><span data-ttu-id="5566a-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5566a-167">See also</span></span>

[<span data-ttu-id="5566a-168">Microsoft 365 Enterprise 개요</span><span class="sxs-lookup"><span data-stu-id="5566a-168">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)