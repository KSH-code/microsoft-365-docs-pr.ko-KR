---
title: Office 365용 Azure Express 경로
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/5/2019
audience: ITPro
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
- MOE150
- BCS160
ms.assetid: 6d2534a2-c19c-4a99-be5e-33a0cee5d3bd
description: Office 365에서 Azure ExpressRoute를 사용하는 방법을 알아보고 이를 사용하여 배포하는 경우 네트워크 구현 프로젝트를 계획합니다.
ms.openlocfilehash: 7e44feefd375088d2fef36c7e7859e242c1a30aa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905359"
---
# <a name="azure-expressroute-for-office-365"></a><span data-ttu-id="f5ecb-103">Office 365용 Azure Express 경로</span><span class="sxs-lookup"><span data-stu-id="f5ecb-103">Azure ExpressRoute for Office 365</span></span>

<span data-ttu-id="f5ecb-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="f5ecb-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f5ecb-105">Office 365에서 Azure ExpressRoute를 사용하는 방법 및 Office 365에서 사용하기 위해 Azure ExpressRoute를 배포하는 경우 필요한 네트워크 구현 프로젝트를 계획하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-105">Learn how Azure ExpressRoute is used with Office 365 and how to plan the network implementation project that will be required if you are deploying Azure ExpressRoute for use with Office 365.</span></span> <span data-ttu-id="f5ecb-106">Azure에서 실행되는 인프라 및 플랫폼 서비스는 네트워크 아키텍처 및 성능 고려 사항을 해결하여 종종 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-106">Infrastructure and platform services running in Azure will often benefit by addressing network architecture and performance considerations.</span></span> <span data-ttu-id="f5ecb-107">이러한 경우 Azure용 ExpressRoute를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-107">We recommend ExpressRoute for Azure in these cases.</span></span> <span data-ttu-id="f5ecb-108">Office 365 및 Dynamics 365와 같은 서비스로 제공되는 소프트웨어는 인터넷을 통해 안전하고 안정적으로 액세스할 수 있도록 구축되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-108">Software as a Service offerings like Office 365 and Dynamics 365 have been built to be accessed securely and reliably via the Internet.</span></span> <span data-ttu-id="f5ecb-109">Office [365](assessing-network-connectivity.md)네트워크 연결 평가 문서에서 인터넷 성능 및 보안 및 Office 365용 Azure ExpressRoute를 고려할 수 있는 경우를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-109">You can read about Internet performance and security and when you might consider Azure ExpressRoute for Office 365 in the article [Assessing Office 365 network connectivity](assessing-network-connectivity.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f5ecb-110">Office 365용 ExpressRoute를 사용하려면 Microsoft 권한 부여가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-110">Microsoft authorization is required to use ExpressRoute for Office 365.</span></span> <span data-ttu-id="f5ecb-111">Microsoft는 고객의 규정 요구 사항에 따라 직접 연결을 요구할 때 모든 고객 요청을 검토하고 Office 365 사용에 대한 ExpressRoute를 승인합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-111">Microsoft reviews every customer request and authorizes ExpressRoute for Office 365 usage when a customer's regulatory requirement mandates direct connectivity.</span></span> <span data-ttu-id="f5ecb-112">이러한 요구 사항이 있는 경우 Microsoft 검토를 시작하려면 [Office 365용 ExpressRoute](https://aka.ms/O365ERReview) 요청 양식에 직접 연결이 필요하다는 의미로 해석되는 규정에 대한 텍스트 발췌 및 웹 링크를 제공하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-112">If you have such requirements, please provide the text excerpt and web link to the regulation which you interpret to mean that direct connectivity is required in the [ExpressRoute for Office 365 Request Form](https://aka.ms/O365ERReview) to begin a Microsoft review.</span></span> <span data-ttu-id="f5ecb-113">Office 365에 대한 경로 필터를 만들려고 하는 권한이 없는 구독에 오류 메시지가 [표시됩니다.](https://support.microsoft.com/kb/3181709)</span><span class="sxs-lookup"><span data-stu-id="f5ecb-113">Unauthorized subscriptions trying to create route filters for Office 365 will receive an [error message](https://support.microsoft.com/kb/3181709).</span></span>

<span data-ttu-id="f5ecb-114">이제 선택한 Office 365 네트워크 트래픽에 대해 Office 365에 직접 네트워크 연결을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-114">You can now add a direct network connection to Office 365 for selected Office 365 network traffic.</span></span> <span data-ttu-id="f5ecb-115">Azure ExpressRoute는 직접 연결, 예측 가능한 성능을 제공하며 Microsoft 네트워킹 구성 요소에 대해 99.95%의 UPTIME SLA를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-115">Azure ExpressRoute offers a direct connection, predictable performance, and comes with an uptime SLA of 99.95% for the Microsoft networking components.</span></span> <span data-ttu-id="f5ecb-116">Azure ExpressRoute를 통해 지원되지 않는 서비스에 대한 인터넷 연결이 계속 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-116">You'll still require an internet connection for services that aren't supported over Azure ExpressRoute.</span></span>

## <a name="planning-azure-expressroute-for-office-365"></a><span data-ttu-id="f5ecb-117">Office 365용 Azure ExpressRoute 계획</span><span class="sxs-lookup"><span data-stu-id="f5ecb-117">Planning Azure ExpressRoute for Office 365</span></span>

<span data-ttu-id="f5ecb-118">인터넷 연결 외에도 Microsoft 네트워킹 구성 요소에 대해 예측 가능성 및 99.95%의 UPTIME SLA를 제공하는 직접 연결을 통해 Office 365 네트워크 트래픽의 하위 집합을 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-118">In addition to internet connectivity, you may choose to route a subset of their Office 365 network traffic over a direct connection that offers predictability and a 99.95% uptime SLA for the Microsoft networking components.</span></span> <span data-ttu-id="f5ecb-119">Azure ExpressRoute는 Office 365 및 기타 Microsoft 클라우드 서비스에 대한 이 전용 네트워크 연결을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-119">Azure ExpressRoute provides you with this dedicated network connection to Office 365 and other Microsoft cloud services.</span></span>

<span data-ttu-id="f5ecb-120">기존 MPLS WAN이 있는지 여부에 관계없이 ExpressRoute를 세 가지 방법 중 하나를 사용하여 네트워크 아키텍처에 추가할 수 있습니다. 지원되는 클라우드 교환 공동 위치 공급자, 이더넷 지점 대 지점 연결 공급자 또는 MPLS 연결 공급자를 통해</span><span class="sxs-lookup"><span data-stu-id="f5ecb-120">Regardless of whether you have an existing MPLS WAN, ExpressRoute can be added to your network architecture in one of three ways; through a supported cloud exchange co-location provider, an Ethernet point-to-point connection provider, or through an MPLS connection provider.</span></span> <span data-ttu-id="f5ecb-121">지역 [에서 사용할 수 있는 공급자를 참조합니다.](/azure/expressroute/expressroute-locations)</span><span class="sxs-lookup"><span data-stu-id="f5ecb-121">See what [providers are available in your region](/azure/expressroute/expressroute-locations).</span></span> <span data-ttu-id="f5ecb-122">Direct ExpressRoute 연결을 사용하면 아래에 포함된 Office [365](azure-expressroute.md#BKMK_WhatDoIGet) 서비스에 설명된 응용 프로그램에 대한 연결을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-122">The direct ExpressRoute connection will enable connectivity to the applications outlined in [What Office 365 services are included?](azure-expressroute.md#BKMK_WhatDoIGet) below.</span></span> <span data-ttu-id="f5ecb-123">다른 모든 응용 프로그램 및 서비스에 대한 네트워크 트래픽은 계속해서 인터넷을 트래버스합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-123">Network traffic for all other applications and services will continue to traverse the internet.</span></span>

<span data-ttu-id="f5ecb-124">Office 365, Windows 업데이트 및 TechNet과 같은 모든 Microsoft 응용 프로그램에 액세스하기 위해 인터넷을 통해 Microsoft의 데이터 센터에 연결하는 일반적인 Office 365 고객을 보여주는 다음과 같은 높은 수준의 네트워크 다이어그램을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-124">Consider the following high level network diagram which shows a typical Office 365 customer connecting to Microsoft's datacenters over the internet for access to all Microsoft applications such as Office 365, Windows Update, and TechNet.</span></span> <span data-ttu-id="f5ecb-125">고객은 사내 네트워크에서 연결하는지 독립적인 인터넷 연결에 관계없이 유사한 네트워크 경로를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-125">Customers use a similar network path regardless of whether they're connecting from an on-premises network or from an independent internet connection.</span></span>

![Office 365 네트워크 연결](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

<span data-ttu-id="f5ecb-127">이제 인터넷 및 ExpressRoute를 사용하여 Office 365에 연결하는 Office 365 고객을 설명하는 업데이트된 다이어그램을 살펴 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-127">Now look at the updated diagram which depicts an Office 365 customer who uses both the internet and ExpressRoute to connect to Office 365.</span></span> <span data-ttu-id="f5ecb-128">공용 DNS 및 콘텐츠 배달 네트워크 노드와 같은 일부 연결에는 여전히 공용 인터넷 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-128">Notice that some connections such as Public DNS and Content Delivery Network nodes still require the public internet connection.</span></span> <span data-ttu-id="f5ecb-129">또한 ExpressRoute 연결된 건물에 없는 고객의 사용자가 인터넷을 통해 연결하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-129">Also notice the customer's users who are not located in their ExpressRoute connected building are connecting over the Internet.</span></span>

![ExpressRoute를 통해 Office 365 연결](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

<span data-ttu-id="f5ecb-131">여전히 자세한 정보를 원하세요?</span><span class="sxs-lookup"><span data-stu-id="f5ecb-131">Still want more information?</span></span> <span data-ttu-id="f5ecb-132">[Office 365용 Azure ExpressRoute를](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) 사용하여 네트워크 트래픽을 관리하는 방법을 알아보고 [Office 365용 Azure ExpressRoute를 구성하는 방법을 배워야 합니다.](/azure/expressroute/expressroute-faqs)</span><span class="sxs-lookup"><span data-stu-id="f5ecb-132">Learn how to [manage your network traffic with Azure ExpressRoute for Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) and learn how to [configure Azure ExpressRoute for Office 365](/azure/expressroute/expressroute-faqs).</span></span> <span data-ttu-id="f5ecb-133">또한 개념을 보다 철저하게 설명할 수 있도록 채널 9에 10부의 [Azure ExpressRoute for Office 365 Training](https://channel9.msdn.com/series/aer) 시리즈를 기록했습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-133">We've also recorded a 10 part [Azure ExpressRoute for Office 365 Training](https://channel9.msdn.com/series/aer) series on Channel 9 to help explain the concepts more thoroughly.</span></span>

## <a name="what-office-365-services-are-included"></a><span data-ttu-id="f5ecb-134">어떤 Office 365 서비스가 포함되어 있나요?</span><span class="sxs-lookup"><span data-stu-id="f5ecb-134">What Office 365 services are included?</span></span>
<span data-ttu-id="f5ecb-135"><a name="BKMK_WhatDoIGet"> </a></span><span class="sxs-lookup"><span data-stu-id="f5ecb-135"><a name="BKMK_WhatDoIGet"> </a></span></span>

<span data-ttu-id="f5ecb-136">다음 표에는 ExpressRoute를 통해 지원되는 Office 365 서비스가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-136">The following table lists the Office 365 services that are supported over ExpressRoute.</span></span> <span data-ttu-id="f5ecb-137">Office [365 끝점](./urls-and-ip-address-ranges.md) 문서를 검토하여 이러한 응용 프로그램에 대한 네트워크 요청에 대해 인터넷에 연결해야 하는지 이해하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-137">Please review the [Office 365 endpoints article](./urls-and-ip-address-ranges.md) to understand which network requests for these applications require internet connectivity.</span></span>

|<span data-ttu-id="f5ecb-138">**포함된 응용 프로그램**</span><span class="sxs-lookup"><span data-stu-id="f5ecb-138">**Applications included**</span></span>|
|:-----|
|<span data-ttu-id="f5ecb-139">Exchange Online<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f5ecb-139">Exchange Online<sup>1</sup></span></span> <br/> <span data-ttu-id="f5ecb-140">Exchange Online Protection<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f5ecb-140">Exchange Online Protection<sup>1</sup></span></span> <br/> <span data-ttu-id="f5ecb-141">Delve<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f5ecb-141">Delve<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="f5ecb-142">비즈니스용 Skype Online<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f5ecb-142">Skype for Business Online<sup>1</sup></span></span> <br/> <span data-ttu-id="f5ecb-143">Microsoft Teams <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f5ecb-143">Microsoft Teams <sup>1</sup></span></span> <br/> |
|<span data-ttu-id="f5ecb-144">SharePoint Online<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f5ecb-144">SharePoint Online<sup>1</sup></span></span> <br/> <span data-ttu-id="f5ecb-145">비즈니스용 OneDrive<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f5ecb-145">OneDrive for Business<sup>1</sup></span></span> <br/> <span data-ttu-id="f5ecb-146">Project Online<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f5ecb-146">Project Online<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="f5ecb-147">포털 및 공유<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f5ecb-147">Portal and shared<sup>1</sup></span></span> <br/> <span data-ttu-id="f5ecb-148">Azure AD(Azure Active Directory) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f5ecb-148">Azure Active Directory (Azure AD) <sup>1</sup></span></span> <br/> <span data-ttu-id="f5ecb-149">Azure AD Connect<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f5ecb-149">Azure AD Connect<sup>1</sup></span></span> <br/> <span data-ttu-id="f5ecb-150">Office<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f5ecb-150">Office<sup>1</sup></span></span> <br/> |

<span data-ttu-id="f5ecb-151"><sup>1</sup> 이러한 각 응용 프로그램에는 ExpressRoute를 통해 지원되지 않는 인터넷 연결 요구 사항이 있습니다. 자세한 내용은 [Office 365 끝점](./urls-and-ip-address-ranges.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-151"><sup>1</sup> Each of these applications have internet connectivity requirements not supported over ExpressRoute, see the [Office 365 endpoints article](./urls-and-ip-address-ranges.md) for more information.</span></span>

<span data-ttu-id="f5ecb-152">Office 365용 ExpressRoute에 포함되지 않은 서비스는 중국의 엔터프라이즈용 Microsoft 365 앱 클라이언트 다운로드, On-premises Identity Provider Sign-In 및 Office 365(21 Vianet에서 운영하는) 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-152">The services that aren't included with ExpressRoute for Office 365 are Microsoft 365 Apps for enterprise client downloads, On-premises Identity Provider Sign-In, and Office 365 (operated by 21 Vianet) service in China.</span></span>

## <a name="implementing-expressroute-for-office-365"></a><span data-ttu-id="f5ecb-153">Office 365용 ExpressRoute 구현</span><span class="sxs-lookup"><span data-stu-id="f5ecb-153">Implementing ExpressRoute for Office 365</span></span>

<span data-ttu-id="f5ecb-154">ExpressRoute를 구현하려면 네트워크 및 응용 프로그램 소유자의 개입이 필요하며, 새 네트워크 라우팅 [아키텍처,](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)대역폭 요구 사항, 보안 구현 위치, 고가용성 등 신중하게 계획해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-154">Implementing ExpressRoute requires the involvement of network and application owners and requires careful planning to determine the new [network routing architecture](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408), bandwidth requirements, where security will be implemented, high availability, and so on.</span></span> <span data-ttu-id="f5ecb-155">ExpressRoute를 구현하려면 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-155">To implement ExpressRoute, you'll need to:</span></span>

1. <span data-ttu-id="f5ecb-156">Office 365 연결 계획에서 ExpressRoute가 충족해야 하는 필요성을 완전히 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-156">Fully understand the need ExpressRoute satisfies in your Office 365 connectivity planning.</span></span> <span data-ttu-id="f5ecb-157">인터넷 또는 ExpressRoute를 사용할 응용 프로그램을 이해하고 Office 365 트래픽에 인터넷 및 ExpressRoute를 사용하는 컨텍스트에서 네트워크 용량, 보안 및 고가용성 요구 사항을 완전히 계획합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-157">Understand what applications will use the internet or ExpressRoute and fully plan your network capacity, security, and high availability needs in the context of using both the internet and ExpressRoute for Office 365 traffic.</span></span>

2. <span data-ttu-id="f5ecb-158">인터넷 및 ExpressRoute 트래픽 1 둘 다의 발신 및 피어링 위치를<sup>확인합니다.</sup></span><span class="sxs-lookup"><span data-stu-id="f5ecb-158">Determine the egress and peering locations for both internet and ExpressRoute traffic<sup>1</sup>.</span></span>

3. <span data-ttu-id="f5ecb-159">인터넷 및 ExpressRoute 연결에 필요한 용량을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-159">Determine the capacity required on the internet and ExpressRoute connections.</span></span>

4. <span data-ttu-id="f5ecb-160">보안 및 기타 표준 경계 컨트롤 1을 구현하기 위한 계획을<sup>수립합니다.</sup></span><span class="sxs-lookup"><span data-stu-id="f5ecb-160">Have a plan in place for implementing security and other standard perimeter controls<sup>1</sup>.</span></span>

5. <span data-ttu-id="f5ecb-161">ExpressRoute를 구독할 유효한 Microsoft Azure 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-161">Have a valid Microsoft Azure account to subscribe to ExpressRoute.</span></span>

6. <span data-ttu-id="f5ecb-162">연결 모델 및 승인된 [공급자를 선택합니다.](/azure/expressroute/expressroute-locations)</span><span class="sxs-lookup"><span data-stu-id="f5ecb-162">Select a connectivity model and an [approved provider](/azure/expressroute/expressroute-locations).</span></span> <span data-ttu-id="f5ecb-163">고객은 여러 연결 모델 또는 파트너를 선택할 수 있으며 파트너가 기존 네트워크 공급자와 동일할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-163">Keep in mind, customers can select multiple connectivity models or partners and the partner doesn't need to be the same as your existing network provider.</span></span>

7. <span data-ttu-id="f5ecb-164">트래픽을 ExpressRoute로 지시하기 전에 배포의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-164">Validate deployment prior to directing traffic to ExpressRoute.</span></span>

8. <span data-ttu-id="f5ecb-165">선택적으로 [QoS를 구현하고](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) 지역별 확장을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-165">Optionally [implement QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) and evaluate regional expansion.</span></span>

<span data-ttu-id="f5ecb-166"><sup>1</sup> 중요한 성능 고려 사항.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-166"><sup>1</sup> Important performance considerations.</span></span> <span data-ttu-id="f5ecb-167">여기서 결정한 결정은 비즈니스용 Skype와 같은 응용 프로그램에 중요한 대기 시간에 크게 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-167">Decisions here can dramatically impact latency which is a critical for applications such as Skype for Business.</span></span>

<span data-ttu-id="f5ecb-168">추가 참조를 위해 [](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) ExpressRoute 설명서와 함께 라우팅 [가이드를 사용하세요.](/azure/expressroute/expressroute-introduction)</span><span class="sxs-lookup"><span data-stu-id="f5ecb-168">For additional references, use our [routing guide](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) in addition to the [ExpressRoute documentation](/azure/expressroute/expressroute-introduction).</span></span>

<span data-ttu-id="f5ecb-169">Office 365용 ExpressRoute를 구입하려면 하나 이상의 승인된 [](/azure/expressroute/expressroute-locations) 공급자와 함께 ExpressRoute Premium 구독으로 원하는 수 및 크기 회로를 프로비전해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-169">To purchase ExpressRoute for Office 365, you'll need to work with one or more [approved providers](/azure/expressroute/expressroute-locations) to provision the desired number and size circuits with an ExpressRoute Premium subscription.</span></span> <span data-ttu-id="f5ecb-170">Office 365에서 추가 라이선스를 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ecb-170">There are no additional licenses to purchase from Office 365.</span></span>

<span data-ttu-id="f5ecb-171">다음의 간단한 링크를 사용할 수 있습니다. [https://aka.ms/expressrouteoffice365]()</span><span class="sxs-lookup"><span data-stu-id="f5ecb-171">Here's a short link you can use to come back: [https://aka.ms/expressrouteoffice365]()</span></span>

<span data-ttu-id="f5ecb-172">[Office 365용 ExpressRoute에 등록할 준비가 되나요?](https://aka.ms/ert)</span><span class="sxs-lookup"><span data-stu-id="f5ecb-172">Ready to sign-up for [ExpressRoute for Office 365](https://aka.ms/ert)?</span></span>

## <a name="related-topics"></a><span data-ttu-id="f5ecb-173">관련 주제</span><span class="sxs-lookup"><span data-stu-id="f5ecb-173">Related Topics</span></span>

<span data-ttu-id="f5ecb-174">[Office 365 네트워크 연결 평가](assessing-network-connectivity.md) </span><span class="sxs-lookup"><span data-stu-id="f5ecb-174">[Assessing Office 365 network connectivity](assessing-network-connectivity.md)</span></span>

[<span data-ttu-id="f5ecb-175">Office 365 연결에 대한 ExpressRoute 관리</span><span class="sxs-lookup"><span data-stu-id="f5ecb-175">Managing ExpressRoute for Office 365 connectivity</span></span>](managing-expressroute-for-connectivity.md)

[<span data-ttu-id="f5ecb-176">Office 365용 ExpressRoute를 사용한 라우팅</span><span class="sxs-lookup"><span data-stu-id="f5ecb-176">Routing with ExpressRoute for Office 365</span></span>](routing-with-expressroute.md)

[<span data-ttu-id="f5ecb-177">Office 365용 ExpressRoute를 사용한 네트워크 계획</span><span class="sxs-lookup"><span data-stu-id="f5ecb-177">Network planning with ExpressRoute for Office 365</span></span>](network-planning-with-expressroute.md)

[<span data-ttu-id="f5ecb-178">Office 365용 ExpressRoute 구현</span><span class="sxs-lookup"><span data-stu-id="f5ecb-178">Implementing ExpressRoute for Office 365</span></span>](implementing-expressroute.md)

[<span data-ttu-id="f5ecb-179">Office 365 시나리오용 ExpressRoute에서 BGP 커뮤니티 사용</span><span class="sxs-lookup"><span data-stu-id="f5ecb-179">Using BGP communities in ExpressRoute for Office 365 scenarios</span></span>](bgp-communities-in-expressroute.md)

[<span data-ttu-id="f5ecb-180">비즈니스용 Skype Online의 미디어 품질 및 네트워크 연결 성능</span><span class="sxs-lookup"><span data-stu-id="f5ecb-180">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[<span data-ttu-id="f5ecb-181">초기 계획 및 성능 기록을 사용하여 Office 365 성능 조정</span><span class="sxs-lookup"><span data-stu-id="f5ecb-181">Office 365 performance tuning using baselines and performance history</span></span>](performance-tuning-using-baselines-and-history.md)

[<span data-ttu-id="f5ecb-182">Office 365 성능 문제 해결 계획</span><span class="sxs-lookup"><span data-stu-id="f5ecb-182">Performance troubleshooting plan for Office 365</span></span>](performance-troubleshooting-plan.md)

[<span data-ttu-id="f5ecb-183">Office 365 URL 및 IP 주소 범위</span><span class="sxs-lookup"><span data-stu-id="f5ecb-183">Office 365 URLs and IP address ranges</span></span>](urls-and-ip-address-ranges.md)

[<span data-ttu-id="f5ecb-184">Office 365 네트워크 및 성능 조정</span><span class="sxs-lookup"><span data-stu-id="f5ecb-184">Office 365 network and performance tuning</span></span>](network-planning-and-performance.md)

## <a name="see-also"></a><span data-ttu-id="f5ecb-185">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5ecb-185">See also</span></span>

[<span data-ttu-id="f5ecb-186">Microsoft 365 Enterprise 개요</span><span class="sxs-lookup"><span data-stu-id="f5ecb-186">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)