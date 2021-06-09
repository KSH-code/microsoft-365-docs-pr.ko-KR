---
title: NAT 지원(Office 365)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2017
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: 170e96ea-d65d-4e51-acac-1de56abe39b9
description: 이 문서에서는 NAT를 사용하여 조직의 IP 주소당 사용할 수 있는 클라이언트 수를 대략화하는 방법에 대해 자세히 제공합니다.
ms.openlocfilehash: f48874853c3acb80927933761862b14379b6d4bd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692284"
---
# <a name="nat-support-with-office-365"></a><span data-ttu-id="51045-103">NAT 지원(Office 365)</span><span class="sxs-lookup"><span data-stu-id="51045-103">NAT support with Office 365</span></span>

<span data-ttu-id="51045-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="51045-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="51045-105">이전에는 IP 주소당 사용해야 하는 Exchange 클라이언트의 최대 수가 네트워크 포트당 Office 365 약 2,000개 클라이언트로 나타났습니다.</span><span class="sxs-lookup"><span data-stu-id="51045-105">Previously, guidance suggested that the maximum number of Exchange clients you should use per IP address to connect to Office 365 was about 2,000 clients per network port.</span></span>
  
## <a name="why-use-nat"></a><span data-ttu-id="51045-106">NAT를 사용하는 이유</span><span class="sxs-lookup"><span data-stu-id="51045-106">Why use NAT?</span></span>

<span data-ttu-id="51045-107">NAT를 사용하여 수천 명의 회사 네트워크 사용자들이 공개적으로 라우팅할 수 있는 몇 가지 IP 주소를 "공유"할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51045-107">By using NAT, thousands of people on a corporate network can "share" a few publicly routable IP addresses.</span></span>
  
<span data-ttu-id="51045-108">대부분의 회사 네트워크는 개인(RFC1918) IP 주소 공간을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51045-108">Most corporate networks use private (RFC1918) IP address space.</span></span> <span data-ttu-id="51045-109">개인 주소 공간은 IANA(인터넷 할당 번호 기관)에서 할당하며 전역 인터넷에서 직접 라우팅되지 않는 네트워크 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="51045-109">Private address space is allocated by the Internet Assigned Numbers Authority (IANA) and intended solely for networks that do not route directly to and from the global Internet.</span></span>
  
<span data-ttu-id="51045-110">개인 IP 주소 공간의 장치에 인터넷 액세스를 제공하기 위해 조직에서는 NAT(Network Address Translation) 또는 PAT(포트 주소 변환) 서비스를 제공하는 방화벽 및 Proxies와 같은 게이트웨이 기술을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51045-110">To provide Internet access to devices on a private IP address space, organizations use gateway technologies like firewalls and proxies that provide network address translation (NAT) or port address translation (PAT) services.</span></span> <span data-ttu-id="51045-111">이러한 게이트웨이는 내부 장치에서 인터넷으로(Office 365 포함) 트래픽이 공개적으로 라우팅 가능한 IP 주소에서 오는 것으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="51045-111">These gateways make traffic from internal devices to the Internet (including Office 365) appear to be coming from one or more publicly routable IP addresses.</span></span> <span data-ttu-id="51045-112">내부 장치에서의 각 아웃바운드 연결은 공용 IP 주소의 다른 원본 TCP 포트로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="51045-112">Each outbound connection from an internal device translates to a different source TCP port on the public IP address.</span></span> 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a><span data-ttu-id="51045-113">연결을 동시에 열기 위해 많은 연결이 Office 365 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="51045-113">Why do you need to have so many connections open to Office 365 at the same time?</span></span>

<span data-ttu-id="51045-114">Outlook 8개 이상의 연결을 열 수 있습니다(추가 기능, 공유 일정, 사서함 등이 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="51045-114">Outlook may open eight or more connections (in situations where there are add-ins, shared calendars, mailboxes, etc.).</span></span> <span data-ttu-id="51045-115">Windows 기반 NAT 장치에서는 최대 64,000개 포트를 사용할 수 있기 때문에 포트가 소진되기 전에 IP 주소 뒤에 최대 8,000명까지 사용자가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51045-115">Because there are a maximum of 64,000 ports available on a Windows-based NAT device, there can be a maximum of 8,000 users behind an IP address before the ports are exhausted.</span></span> <span data-ttu-id="51045-116">고객이 NAT에 비 OS 기반 Windows 사용하는 경우 사용 가능한 총 포트는 사용 가능한 NAT 장치 또는 소프트웨어에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="51045-116">Note that if customers are using non-Windows OS-based devices for NAT, the total available ports are dependent on what NAT device or software is being used.</span></span> <span data-ttu-id="51045-117">이 시나리오에서는 최대 포트 수가 64,000개 미만일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51045-117">In this scenario, the maximum number of ports could be less than 64,000.</span></span> <span data-ttu-id="51045-118">또한 포트의 가용성은 자체적으로 사용할 수 있도록 Windows 4,000개 포트를 제한하는 등의 다른 요인의 영향을 받지만, 사용 가능한 총 포트 수를 60,000개로 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="51045-118">Availability of ports is also affected by other factors such as Windows restricting 4,000 ports for its own use, which reduces the total number of available ports to 60,000.</span></span> <span data-ttu-id="51045-119">다른 응용 프로그램(예: Internet Explorer 포트가 필요한 경우)이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51045-119">There may be other applications, such as Internet Explorer, that could connect at the same time, requiring additional ports.</span></span>
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a><span data-ttu-id="51045-120">단일 공용 IP 주소 뒤에서 지원되는 최대 장치 계산을 Office 365</span><span class="sxs-lookup"><span data-stu-id="51045-120">Calculating maximum supported devices behind a single public IP address with Office 365</span></span>

<span data-ttu-id="51045-121">단일 공용 IP 주소 뒤에 있는 최대 장치 수를 결정하기 위해 네트워크 트래픽을 모니터링하여 클라이언트당 최대 포트 사용량을 파악해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51045-121">To determine the maximum number of devices behind a single public IP address, you should monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="51045-122">또한 최대 계수는 포트 사용량(최소 4)에 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51045-122">Also, a peak factor should be used for the port usage (minimum 4).</span></span> 
  
 <span data-ttu-id="51045-123">**다음 수식을 사용하여 IP 주소당 지원되는 장치 수를 계산합니다.**</span><span class="sxs-lookup"><span data-stu-id="51045-123">**Use the following formula to calculate the number of supported devices per IP address:**</span></span>
  
<span data-ttu-id="51045-124">단일 공용 IP 주소 뒤에 지원되는 최대 장치 = (64,000 - 제한된 포트)/(최대 포트 사용 + 최대 비율)</span><span class="sxs-lookup"><span data-stu-id="51045-124">Maximum supported devices behind a single public IP address = (64,000 - restricted ports)/(Peak port consumption + peak factor)</span></span>
  
 <span data-ttu-id="51045-125">**예를 들어 다음에 해당하면 다음과 같습니다.**</span><span class="sxs-lookup"><span data-stu-id="51045-125">**For example, if the following were true:**</span></span>
  
- <span data-ttu-id="51045-126">**제한된 포트:** 운영 체제의 경우 4,000개</span><span class="sxs-lookup"><span data-stu-id="51045-126">**Restricted ports:** 4,000 for the operating system</span></span>

- <span data-ttu-id="51045-127">**최대 포트 사용:** 장치당 6개</span><span class="sxs-lookup"><span data-stu-id="51045-127">**Peak port consumption:** 6 per device</span></span>

- <span data-ttu-id="51045-128">**최대 계수:** 4</span><span class="sxs-lookup"><span data-stu-id="51045-128">**Peak factor:** 4</span></span>

<span data-ttu-id="51045-129">그런 다음 단일 공용 IP 주소 뒤에 지원되는 최대 장치 = (64,000 - 4,000)/(6 + 4) = 6,000</span><span class="sxs-lookup"><span data-stu-id="51045-129">Then, the maximum supported devices behind a single public IP address = (64,000 - 4,000)/(6 + 4) = 6,000</span></span>
  
<span data-ttu-id="51045-130">Office 365 호스팅 팩의 릴리스에서는 Microsoft Office Outlook 2007용 2011년 9월 또는 Microsoft Outlook 2010용 업데이트 또는 이후 업데이트에 포함된 Outlook(Office Outlook 2007 서비스 팩 2 및 Outlook 2010)에서 Exchange 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51045-130">With the release of Office 365 hosting pack, included in the updates from September 2011 for Microsoft Office Outlook 2007, or November 2011 for Microsoft Outlook 2010, or a later update, the number of connections from Outlook (both Office Outlook 2007 with Service Pack 2 and Outlook 2010) to Exchange can be as few as 2.</span></span> <span data-ttu-id="51045-131">네트워크에 최대로 필요한 최소 및 최대 포트 수를 결정하려면 다양한 운영 체제, 사용자 동작을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51045-131">You'll need to factor in the different operating systems, user behaviors, and so on to determine the minimum and maximum number of ports that your network will require at peak.</span></span>
  
<span data-ttu-id="51045-132">단일 공용 IP 주소 뒤에 더 많은 장치를 지원하려는 경우 지원할 수 있는 최대 장치 수를 평가하기 위해 설명된 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="51045-132">If you want to support more devices behind a single public IP address, follow the steps outlined to assess the maximum number of devices that can be supported:</span></span>
  
<span data-ttu-id="51045-133">네트워크 트래픽을 모니터링하여 클라이언트당 최대 포트 사용량을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="51045-133">Monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="51045-134">다음 데이터를 수집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51045-134">You should collect this data:</span></span>
  
- <span data-ttu-id="51045-135">여러 위치에서</span><span class="sxs-lookup"><span data-stu-id="51045-135">From multiple locations</span></span>
    
- <span data-ttu-id="51045-136">여러 장치에서</span><span class="sxs-lookup"><span data-stu-id="51045-136">From multiple devices</span></span>
    
- <span data-ttu-id="51045-137">여러 번</span><span class="sxs-lookup"><span data-stu-id="51045-137">At multiple times</span></span>
    
<span data-ttu-id="51045-138">앞의 수식을 사용하여 해당 환경에서 지원할 수 있는 IP 주소당 최대 사용자를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="51045-138">Use the preceding formula to calculate the maximum users per IP address that can be supported in their environment.</span></span>
  
<span data-ttu-id="51045-139">추가 공용 IP 주소에 클라이언트 부하를 분산하는 다양한 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51045-139">There are various methods for distributing client load across additional public IP addresses.</span></span> <span data-ttu-id="51045-140">사용할 수 있는 전략은 회사 게이트웨이 솔루션의 기능에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51045-140">Strategies available depend on the capabilities of the corporate gateway solution.</span></span> <span data-ttu-id="51045-141">가장 간단한 해결 방법은 사용자 주소 공간을 분할하고 여러 IP 주소를 각 게이트웨이에 정적으로 "할당"하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="51045-141">The simplest solution is to segment your user address space and statically "assign" a number of IP addresses to each gateway.</span></span> <span data-ttu-id="51045-142">많은 게이트웨이 장치에서 제공하는 또 다른 대안으로 IP 주소 풀을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51045-142">Another alternative that many gateway devices offer is the ability to use a pool of IP addresses.</span></span> <span data-ttu-id="51045-143">주소 풀의 이점은 사용자 기반이 커질수록 훨씬 더 동적이며 조정이 필요하지 않는다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="51045-143">The benefit of the address pool is that it is much more dynamic and less likely to require adjustment as your user base grows.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="51045-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51045-144">See also</span></span>

[<span data-ttu-id="51045-145">Office 365 끝점 관리</span><span class="sxs-lookup"><span data-stu-id="51045-145">Managing Office 365 endpoints</span></span>](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[<span data-ttu-id="51045-146">Office 365 끝점 FAQ</span><span class="sxs-lookup"><span data-stu-id="51045-146">Office 365 endpoints FAQ</span></span>](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
