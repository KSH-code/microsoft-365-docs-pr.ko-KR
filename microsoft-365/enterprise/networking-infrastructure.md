---
title: '1단계: Microsoft 365 Enterprise에 대한 네트워킹 인프라'
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
description: Microsoft 365 Enterprise에 대한 네트워킹 인프라를 배포하는 단계입니다.
ms.openlocfilehash: 9b8c23d543eca97147801d70e42de7105266c52d
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "33399962"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a><span data-ttu-id="c0b21-103">1단계: Microsoft 365 Enterprise에 대한 네트워킹 인프라</span><span class="sxs-lookup"><span data-stu-id="c0b21-103">Phase 1: Networking infrastructure for Microsoft 365 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon.png)

<span data-ttu-id="c0b21-104">Microsoft 365 Enterprise에는 EMS (Enterprise Management + Security)의 일부로 Office 365와 Microsoft Intune이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0b21-104">Microsoft 365 Enterprise includes Office 365 and Microsoft Intune as part of Enterprise Management + Security (EMS).</span></span> <span data-ttu-id="c0b21-105">이러한 클라우드 기반 서비스 두 가지 모두 인터넷이나 전용 회선을 통해 클라이언트 장치의 연결 보안, 성능 및 안정성에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="c0b21-105">Both of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="c0b21-106">Microsoft는 이러한 서비스를 호스팅하고 전 세계 고객이 사용할 수 있도록하기 위해 성능 및 통합을 중점을 둔 네트워킹 인프라를 설계했습니다.</span><span class="sxs-lookup"><span data-stu-id="c0b21-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="c0b21-p102">이 단계에서는 Microsoft 365 Enterprise의 클라우드 서비스에 대한 뛰어난 성능의 연결을 만들기 위한 주요 고려 사항을 안내합니다. 개요는 [Office 365 네트워킹 원칙](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0b21-p102">In this phase, you step through the key considerations for creating a performant connection to the cloud services of Microsoft 365 Enterprise. For an overview, see [Office 365 networking principles](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

>[!Note]
><span data-ttu-id="c0b21-109">네트워킹 인프라를 이미 배포한 경우 이 단계에 대한 [종료 조건](networking-exit-criteria.md)을 검토하여 Microsoft 365 Enterprise에 대한 필수 및 선택적 조건을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c0b21-109">If you already have a networking infrastructure deployed, please see the [exit criteria](networking-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a><span data-ttu-id="c0b21-110">Microsoft 365 Enterprise 네트워킹 인프라 계획 및 배포</span><span class="sxs-lookup"><span data-stu-id="c0b21-110">Plan and deploy your Microsoft 365 Enterprise networking infrastructure</span></span> 

<span data-ttu-id="c0b21-111">다음 단계를 사용하여 Microsoft 365 Enterprise의 요구 사항 및 기능에 적합한 네트워킹 인프라를 구축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0b21-111">Use the following steps to build out your networking infrastructure for the requirements and capabilities of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="c0b21-112">Microsoft 365에 맞게 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="c0b21-112">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="c0b21-113">각 사무실에 대해 로컬 인터넷 연결 구성</span><span class="sxs-lookup"><span data-stu-id="c0b21-113">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="c0b21-114">네트워크 헤어핀 방지</span><span class="sxs-lookup"><span data-stu-id="c0b21-114">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="c0b21-115">트래픽 바이패스 구성</span><span class="sxs-lookup"><span data-stu-id="c0b21-115">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="c0b21-116">클라이언트 및 Office 365 서비스 성능 최적화</span><span class="sxs-lookup"><span data-stu-id="c0b21-116">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|


<span data-ttu-id="c0b21-117">이러한 단계를 완료했으면 이 단계에 대한 [종료 조건](networking-exit-criteria.md)으로 이동하여 Microsoft 365 Enterprise에 대한 필수 및 선택적 조건을 충족하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c0b21-117">When you've completed these steps, go to the [exit criteria](networking-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="c0b21-118">Microsoft에서 Microsoft 365 Enterprise으로의 마이그레이션을 수행하는 방법</span><span class="sxs-lookup"><span data-stu-id="c0b21-118">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c0b21-119">Microsoft 내부 상황을 살펴보고 [Microsoft Office 365에 대한 네트워크 성능 최적화](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)에서 Microsoft가 Office 365 클라우드 서비스를 위해 Microsoft 네트워크를 준비하고 최적화한 방식을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c0b21-119">Peek inside Microsoft and learn how the company prepared for and optimized the Microsoft network for the Office 365 cloud services with [Optimizing network performance for Microsoft Office 365](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="c0b21-120">Contoso의 Microsoft 365 Enterprise 사용 방식</span><span class="sxs-lookup"><span data-stu-id="c0b21-120">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c0b21-121">가상의 대표적 다국적 기업인 Contoso Corporation이 Microsoft 365 클라우드 서비스에 맞게 [네트워크를 최적화](contoso-networking.md)한 방식을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c0b21-121">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="c0b21-122">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c0b21-122">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="c0b21-123">Microsoft 365에 맞게 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="c0b21-123">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|

