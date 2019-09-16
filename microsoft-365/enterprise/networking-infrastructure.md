---
title: '1단계: Microsoft 365 Enterprise에 대한 네트워킹 인프라'
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
description: Microsoft 365 Enterprise에 대한 네트워킹 인프라를 배포하는 단계입니다.
ms.openlocfilehash: 35c65515854bb0c47a45e48d8e3c6af6a80d907c
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982799"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a><span data-ttu-id="46303-103">1단계: Microsoft 365 Enterprise에 대한 네트워킹 인프라</span><span class="sxs-lookup"><span data-stu-id="46303-103">Phase 1: Networking infrastructure for Microsoft 365 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon.png)

<span data-ttu-id="46303-104">Microsoft 365 Enterprise에는 Office 365, Microsoft Intune 및 Microsoft Azure의 여러 ID와 보안 서비스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46303-104">Microsoft 365 Enterprise includes Office 365, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="46303-105">이러한 모든 클라우드 기반 서비스는 인터넷이나 전용 회선을 통해 클라이언트 장치의 연결 보안, 성능 및 안정성에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="46303-105">Both of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="46303-106">Microsoft는 이러한 서비스를 호스팅하고 전 세계 고객이 사용할 수 있도록하기 위해 성능 및 통합을 중점을 둔 네트워킹 인프라를 설계했습니다.</span><span class="sxs-lookup"><span data-stu-id="46303-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="46303-p102">이 단계에서는 Microsoft 365 Enterprise의 클라우드 서비스에 대한 뛰어난 성능의 연결을 만들기 위한 주요 고려 사항을 안내합니다. 개요는 [Office 365 네트워킹 원칙](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46303-p102">In this phase, you step through the key considerations for creating a performant connection to the cloud services of Microsoft 365 Enterprise. For an overview, see [Office 365 networking principles](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

>[!Note]
><span data-ttu-id="46303-109">네트워킹 인프라를 이미 배포한 경우 이 단계에 대한 [종료 조건](networking-exit-criteria.md)을 검토하여 Microsoft 365 Enterprise에 대한 필수 및 선택적 조건을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="46303-109">If you already have a networking infrastructure deployed, please see the [exit criteria](networking-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a><span data-ttu-id="46303-110">Microsoft 365 Enterprise 네트워킹 인프라 계획 및 배포</span><span class="sxs-lookup"><span data-stu-id="46303-110">Plan and deploy your Microsoft 365 Enterprise networking infrastructure</span></span> 

<span data-ttu-id="46303-111">다음 단계를 사용하여 Microsoft 365 Enterprise의 요구 사항 및 기능에 적합한 네트워킹 인프라를 구축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46303-111">Use the following steps to build out your networking infrastructure for the requirements and capabilities of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="46303-112">Microsoft 365에 맞게 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="46303-112">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="46303-113">각 사무실에 대해 로컬 인터넷 연결 구성</span><span class="sxs-lookup"><span data-stu-id="46303-113">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="46303-114">네트워크 헤어핀 방지</span><span class="sxs-lookup"><span data-stu-id="46303-114">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="46303-115">트래픽 바이패스 구성</span><span class="sxs-lookup"><span data-stu-id="46303-115">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="46303-116">클라이언트 및 Office 365 서비스 성능 최적화</span><span class="sxs-lookup"><span data-stu-id="46303-116">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|


<span data-ttu-id="46303-117">이러한 단계를 완료했으면 이 단계에 대한 [종료 조건](networking-exit-criteria.md)으로 이동하여 Microsoft 365 Enterprise에 대한 필수 및 선택적 조건을 충족하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="46303-117">When you've completed these steps, go to the [exit criteria](networking-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="46303-118">Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법</span><span class="sxs-lookup"><span data-stu-id="46303-118">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="46303-119">Microsoft 내부를 살펴보고 회사가 [클라우드 서비스를 위한 Microsoft 네트워크를 최적화](https://www.microsoft.com/ko-KR/itshowcase/deploying-and-managing-microsoft-365#primaryR4)한 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="46303-119">Peek inside Microsoft and learn how the company prepared for and optimized the Microsoft network for the Office 365 cloud services with [Optimizing network performance for Microsoft Office 365](https://www.microsoft.com/ko-KR/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="46303-120">Contoso의 Microsoft 365 Enterprise 사용 방식</span><span class="sxs-lookup"><span data-stu-id="46303-120">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="46303-121">가상의 대표적 다국적 기업인 Contoso Corporation이 Microsoft 365 클라우드 서비스에 맞게 [네트워크 장치 및 인터넷 연결을 최적화](contoso-networking.md)한 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="46303-121">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="46303-122">다음 단계</span><span class="sxs-lookup"><span data-stu-id="46303-122">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="46303-123">Microsoft 365에 맞게 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="46303-123">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|

