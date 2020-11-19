---
title: Contoso의 COVID-19 대응 및 하이브리드 인력에 대 한 지원
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso Corporation이 COVID-19 pandemic에 응답 하 고, 하이브리드 직원을 위해 소프트웨어 설치 및 업데이트 인프라를 구축 하는 방법을 이해 합니다.
ms.openlocfilehash: a29ffee1413f60da30ad34aa62ca465ca16e0430
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357972"
---
# <a name="contosos-covid-19-response-and-support-for-a-hybrid-workforce"></a><span data-ttu-id="25f78-103">Contoso의 COVID-19 대응 및 하이브리드 인력에 대 한 지원</span><span class="sxs-lookup"><span data-stu-id="25f78-103">Contoso's COVID-19 response and support for a hybrid workforce</span></span>

<span data-ttu-id="25f78-104">Contoso는 파리 본사의 중앙 VPN 서버를 통해 온-프레미스 리소스에 액세스 하는 원격 작업자를 항상 지원 했습니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-104">Contoso had always supported its remote workers, who accessed on-premises resources through a central VPN server in the Paris headquarters.</span></span> <span data-ttu-id="25f78-105">Contoso는 모든 원격 작업자에 게 관리 되는 랩톱을 발급 했습니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-105">Contoso had issued all remote workers a managed laptop.</span></span> <span data-ttu-id="25f78-106">온-프레미스 작업 자가 데스크톱 컴퓨터와 랩톱을 혼합 했습니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-106">On-premises workers had a mixture of desktop computers and laptops.</span></span>

## <a name="contosos-response-to-covid-19"></a><span data-ttu-id="25f78-107">Contoso의 COVID-19에 대 한 응답</span><span class="sxs-lookup"><span data-stu-id="25f78-107">Contoso’s response to COVID-19</span></span>

<span data-ttu-id="25f78-108">COVID-19 pandemic의 onset을 사용 하 여 모든 필수 작업 자가 원격 작업자 였지만 모든 작업을 수행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-108">With the onset of the COVID-19 pandemic, suddenly all but essential workers were remote workers.</span></span> <span data-ttu-id="25f78-109">Contoso는 직원 들이 집에서 작업 하기 위해 인력을 이동 하 고, 온-프레미스 리소스에 대 한 원격 액세스와 Microsoft 365 클라우드 서비스를 사용 하 여 온라인으로 기본 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-109">Contoso responded by shifting its workforce to work from home and conduct its primary activities through remote access to on-premises resources and online using Microsoft 365 cloud services.</span></span>

<span data-ttu-id="25f78-110">Contoso는 기존 원격 인력의 25%를 지원 하기 위해 파리 본사 사무실에 원격 액세스 VPN 서버를 제공 했지만, 해당 직원의 90%를 지원 하기 위해 it의 원격 액세스 용량을 빠르게 수평으로 이동 했습니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-110">Contoso had remote access VPN servers in the Paris headquarters office to support the 25% of its already remote workforce, but quickly moved to scale up it's remote access capacity to support 90% of its workforce.</span></span> <span data-ttu-id="25f78-111">Contoso는 원격 작업자 들이 Contoso 인트라넷 액세스를 위해 지역적으로 close 진입점을 사용할 수 있도록 각 위성 사무실에 원격 액세스 VPN 서버를 배포 했습니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-111">Contoso deployed remote access VPN servers in each satellite office so that remote workers would use a regionally close entry point for access to the Contoso intranet.</span></span>

<span data-ttu-id="25f78-112">또한 Contoso는 분할 터널링을 위해 랩톱, 태블릿 및 스마트 전화에 설치 된 VPN 클라이언트의 구성을 업데이트 하 여, 최적화 된 Office 365 끝점에 대 한 트래픽이 VPN 연결을 무시 하 고 인터넷을 통해 직접 전송 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-112">Contoso also updated the configuration of VPN clients installed on laptops, tablets, and smart phones for split tunneling so that traffic for the Optimize set of Office 365 endpoints bypassed the VPN connection and was sent directly over the internet.</span></span> <span data-ttu-id="25f78-113">자세한 내용은 [VPN 분할 터널링을 사용 하 여 원격 사용자에 대 한 Office 365 연결 최적화](../enterprise/microsoft-365-vpn-split-tunnel.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25f78-113">For more information, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).</span></span>

<span data-ttu-id="25f78-114">파리 본부 및 각 위성 사무소에 설치 된 VPN 장치를 사용한 결과 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-114">Here is the resulting configuration with VPN devices installed in the Paris headquarters and each of the satellite offices.</span></span> 

![Contoso의 VPN 인프라](../media/contoso-hybrid-workforce/contoso-vpn-infrastructure.png)

<span data-ttu-id="25f78-116">설치 된 VPN 클라이언트를 사용 하는 원격 작업자는 DNS를 사용 하 여 가장 가까운 지역적으로의 office를 검색 하 고 여기에 설치 된 VPN 장치에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-116">A remote worker with the installed VPN client uses DNS to find the regionally closest office and connects to the VPN device installed there.</span></span> <span data-ttu-id="25f78-117">분할 터널링을 사용 하는 경우 Microsoft 365 최적화 끝점에 대 한 트래픽은 지역적으로 가장 가까운 Microsoft 365 네트워크 위치로 바로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-117">With split tunneling, traffic to Microsoft 365 Optimize endpoints gets sent directly to the regionally closest Microsoft 365 network location.</span></span> <span data-ttu-id="25f78-118">다른 모든 트래픽은 vpn 연결을 통해 VPN 장치로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-118">All other traffic gets sent over the VPN connection to the VPN device.</span></span>

## <a name="contosos-support-for-a-dynamic-hybrid-workforce"></a><span data-ttu-id="25f78-119">Contoso의 동적 하이브리드 인력 지원</span><span class="sxs-lookup"><span data-stu-id="25f78-119">Contoso’s support for a dynamic hybrid workforce</span></span>

<span data-ttu-id="25f78-120">처음 변경 후에는 지역 잠금을 중에 대부분의 원격 작업자를 지원 하기 위해 Contoso는 직원 들이 다음과 같은 작업을 수행할 수 있도록 인프라를 변경 했습니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-120">After the initial changes were made to support mostly remote workers during regional lockdowns, Contoso made infrastructure changes to support a hybrid workforce in which a worker could be:</span></span>

- <span data-ttu-id="25f78-121">Always 원격</span><span class="sxs-lookup"><span data-stu-id="25f78-121">Always remote.</span></span>
- <span data-ttu-id="25f78-122">항상 온-프레미스로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-122">Always on-premises.</span></span>
- <span data-ttu-id="25f78-123">원격 및 온-프레미스의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-123">A combination of remote and on-premises.</span></span>

<span data-ttu-id="25f78-124">Microsoft 365 id, 보안 및 규정 준수 기능은 제로 트러스트를 위해 설계 되었으며 사용자 및 해당 장치의 위치에 관계 없이 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-124">Microsoft 365 identity, security, and compliance features are designed for Zero Trust and to work regardless of the location of the user and their device.</span></span> <span data-ttu-id="25f78-125">자세한 내용은 [제로 트러스트](https://www.microsoft.com/security/business/zero-trust)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="25f78-125">For more information, see [Zero Trust](https://www.microsoft.com/security/business/zero-trust).</span></span>

<span data-ttu-id="25f78-126">그러나 소프트웨어를 새로 설치 하 고 업데이트 하는 것은 설치할 소프트웨어를 온-프레미스 또는 인터넷 원본에서 가져올 수 있기 때문에 장치 위치에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-126">However, managing new installs and updates of software is dependent on the location of the device because the software to install could come from an on-premises or an internet source.</span></span> <span data-ttu-id="25f78-127">Contoso IT 설계자는 작업자 대신 장치 위치에 따라 새로운 설치 및 업데이트 인프라를 설계 했습니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-127">Contoso IT architects designed their new installs and updates infrastructure based on the location of the device, rather than the worker.</span></span>

<span data-ttu-id="25f78-128">두 가지 유형의 장치 (전용 온-프레미스 및 로밍)를 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-128">They designated two types of devices: dedicated on-premises and roaming.</span></span>

### <a name="dedicated-on-premises"></a><span data-ttu-id="25f78-129">전용 온-프레미스</span><span class="sxs-lookup"><span data-stu-id="25f78-129">Dedicated on-premises</span></span>

<span data-ttu-id="25f78-130">전용 온-프레미스 장치는 Contoso 인트라넷을 떠나 VPN 클라이언트를 설치 하지 않은 데스크톱 또는 서버 컴퓨터입니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-130">A dedicated on-premises device is a desktop or server computer that never leaves the Contoso intranet and does not have a VPN client installed.</span></span> <span data-ttu-id="25f78-131">이러한 온-프레미스 장치는 Windows 10, Microsoft 365 앱 및에 지 브라우저의 설치 및 업데이트를 위해 Microsoft Endpoint Configuration Manager 및 해당 배포 지점을 계속 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-131">These on-premises devices continue to use Microsoft Endpoint Configuration Manager and its distribution points for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and the Edge browser.</span></span>

### <a name="roaming"></a><span data-ttu-id="25f78-132">로밍</span><span class="sxs-lookup"><span data-stu-id="25f78-132">Roaming</span></span>

<span data-ttu-id="25f78-133">로밍 장치는 contoso 인트라넷을 사용 하 고 많은 office 작업자 및 모든 원격 작업자 및 기타 조직 소유 장치 (예: Contoso VPN 클라이언트를 설치한 경우)와 smart 휴대폰 및 태블릿 등의 조직이 소유한 장치로 사서함을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-133">A roaming device can leave the Contoso intranet and includes laptops issued to many office workers and all remote workers and other organization-owned devices such as smart phones and tablets with the Contoso VPN client installed.</span></span> 

<span data-ttu-id="25f78-134">이러한 장치는 언제 든 지 인터넷에 연결 될 수 있기 때문에 Windows 10의 설치 및 업데이트를 위해 Intune 또는 기타 클라우드 기반 서비스를 사용 하 고, Microsoft 365 for 엔터프라이즈 및 Edge에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-134">Because these devices can be connected to the Internet at any given time, they use Intune or other cloud-based services for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="25f78-135">기존 온-프레미스 구성 관리자 배포 지점은 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-135">They do not use the existing on-premises Configuration Manager distribution points.</span></span>

<span data-ttu-id="25f78-136">즉, 로밍 장치에 대 한 일부 설치 및 업데이트는 온-프레미스에 있고 인트라넷에 연결 되어 있는 동안 인터넷을 통해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-136">This means some of the installs and updates for roaming device will be done over the internet while they are on-premises and connected to the intranet.</span></span> <span data-ttu-id="25f78-137">그러나 Contoso IT 설계자는 인트라넷 대역폭 최적화 (특히 대부분의 원격 작업 자가 인트라넷에 거의 연결 되지 않은 경우) 보다 구성 단순함 보다 더 중요 하다 고 결정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-137">But Contoso IT architects decided that simplicity of configuration was more important than optimization of intranet bandwidth to the internet, especially when most remote workers are seldom connected to the intranet.</span></span>

<span data-ttu-id="25f78-138">결과 인프라는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-138">Here is the resulting infrastructure.</span></span>

![Contoso의 설치 및 업데이트 인프라](../media/contoso-hybrid-workforce/contoso-updates-infrastructure.png)

<span data-ttu-id="25f78-140">설치 및 업데이트 동작은 장치에 대 한 컴퓨터 계정을 다음 그룹 중 하나의 구성원으로 만들어 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-140">Install and update behavior is determined by making the computer accounts of devices a member of one of these groups:</span></span>

- <span data-ttu-id="25f78-141">OnPremDevices</span><span class="sxs-lookup"><span data-stu-id="25f78-141">OnPremDevices</span></span>

  <span data-ttu-id="25f78-142">장치의 Configuration Manager 클라이언트에서 설치 및 업데이트를 위한 배포 지점을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-142">The Configuration Manager client on the device uses distribution points for installs and updates.</span></span>

- <span data-ttu-id="25f78-143">RoamingDevices</span><span class="sxs-lookup"><span data-stu-id="25f78-143">RoamingDevices</span></span>

  <span data-ttu-id="25f78-144">Intune 및 장치의 기타 설정 설치 및 업데이트를 위해 Microsoft 365 네트워크의 사용을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-144">Intune and other settings on the device specify the use of the Microsoft 365 network for installs and updates.</span></span>

## <a name="new-onboarding-process"></a><span data-ttu-id="25f78-145">새 온 보 딩 프로세스</span><span class="sxs-lookup"><span data-stu-id="25f78-145">New onboarding process</span></span>

<span data-ttu-id="25f78-146">새 작업자에 게 발급 되거나 데이터 센터의 새 서버에 대해 새 전용 온-프레미스 장치를 실행 하는 경우, 해당 작업자에 로그인 하는 경우 OnPremDevices 그룹의 해당 장치 구성원을 기반으로 하는 Configuration Manager 클라이언트는 Windows 365 10 용 최신 업데이트를 다운로드 하 고 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-146">For a new dedicated on-premises device issued to a new worker or for a new server in a datacenter, when the worker signs in, the Configuration Manager client based on the device's membership in the OnPremDevices group downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge from on-premises Configuration Manager distribution points.</span></span> <span data-ttu-id="25f78-147">완료 되 면 전용 온-프레미스 장치를 사용할 준비가 되 고 이러한 배포 지점을 사용 하 여 업데이트를 진행 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-147">When complete, the dedicated on-premises device is ready for use and uses these distribution points for ongoing updates.</span></span>

<span data-ttu-id="25f78-148">새 작업자에 게 발급 된 새 원격 장치의 경우, 작업자에 로그인 하면 해당 장치는 RoamingDevices 그룹의 구성원을 기반으로 하 여 Intune 클라우드 서비스 및 기타 서비스에 연결 하 고 Windows 10 용 최신 업데이트를 다운로드 하 고 설치 합니다 (Microsoft 365 for enterprise 및 Edge).</span><span class="sxs-lookup"><span data-stu-id="25f78-148">For a new remote device issued to a new worker, when the worker signs in, the device, based on its membership in the RoamingDevices group, contacts the Intune cloud service and other services and downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="25f78-149">완료 되 면 원격 장치가 사용 가능 하 게 준비 되 고 설치 된 VPN 클라이언트를 사용 하 여 온-프레미스 리소스에 액세스 하 고 Microsoft 365 네트워크를 통해 진행 중인 업데이트를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-149">When complete, the remote device is ready for use and uses the installed VPN client for access to on-premises resources and the Microsoft 365 network for ongoing updates.</span></span>

## <a name="next-step"></a><span data-ttu-id="25f78-150">다음 단계</span><span class="sxs-lookup"><span data-stu-id="25f78-150">Next step</span></span>

<span data-ttu-id="25f78-151">조직의 [원격 작업자에 게 역량을](empower-people-to-work-remotely.md) 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="25f78-151">[Empower the remote workers](empower-people-to-work-remotely.md) in your organization.</span></span>
