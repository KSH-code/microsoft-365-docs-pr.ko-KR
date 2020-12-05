---
title: Contoso의 COVID-19 응답 및 원격 및 부사장 작업 지원
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
description: Contoso Corporation이 COVID-19 팬데믹에 대응하고 원격 및 인사이트 작업을 위한 소프트웨어 설치 및 업데이트 인프라를 설계한 방법을 이해합니다.
ms.openlocfilehash: d04b4efcdd4dd04315ad37311cdd2cfbc2e64e88
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580676"
---
# <a name="contosos-covid-19-response-and-support-for-remote-and-onsite-work"></a><span data-ttu-id="de25b-103">Contoso의 COVID-19 응답 및 원격 및 부사장 작업 지원</span><span class="sxs-lookup"><span data-stu-id="de25b-103">Contoso's COVID-19 response and support for remote and onsite work</span></span>

<span data-ttu-id="de25b-104">Contoso는 항상 파리 본사의 중앙 VPN 서버를 통해 프레미스 리소스에 액세스한 원격 작업자를 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-104">Contoso had always supported its remote workers, who accessed on-premises resources through a central VPN server in the Paris headquarters.</span></span> <span data-ttu-id="de25b-105">Contoso는 모든 원격 작업자에게 관리되는 노트북을 발급했습니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-105">Contoso had issued all remote workers a managed laptop.</span></span> <span data-ttu-id="de25b-106">On-premises workers had a mixture of desktop computers and laptops.</span><span class="sxs-lookup"><span data-stu-id="de25b-106">On-premises workers had a mixture of desktop computers and laptops.</span></span>

## <a name="contosos-response-to-covid-19"></a><span data-ttu-id="de25b-107">CONtoso의 COVID-19에 대한 응답</span><span class="sxs-lookup"><span data-stu-id="de25b-107">Contoso’s response to COVID-19</span></span>

<span data-ttu-id="de25b-108">COVID-19 팬데믹이 시작된 후 갑자기 필수적인 작업자를 모두 원격 작업자로 시작했습니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-108">With the onset of the COVID-19 pandemic, suddenly all but essential workers were remote workers.</span></span> <span data-ttu-id="de25b-109">Contoso는 인력을 집에서 일하고 Microsoft 365 클라우드 서비스를 사용하여 온라인으로 원격 액세스를 통해 기본 활동을 수행하게 하여 대응했습니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-109">Contoso responded by shifting its workforce to work from home and conduct its primary activities through remote access to on-premises resources and online using Microsoft 365 cloud services.</span></span>

<span data-ttu-id="de25b-110">Contoso는 이미 원격 인력의 25%를 지원하기 위해 파리 본사에 원격 액세스 VPN 서버를 사용했지만, 인력의 90%를 지원하기 위해 원격 액세스 용량을 확장하기 위해 빠르게 이동했습니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-110">Contoso had remote access VPN servers in the Paris headquarters office to support the 25% of its already remote workforce, but quickly moved to scale up it's remote access capacity to support 90% of its workforce.</span></span> <span data-ttu-id="de25b-111">Contoso는 원격 작업자가 Contoso 인트라넷에 액세스하기 위해 지역적으로 가까운 진입점을 사용할 수 있도록 각 위성 사무실에 원격 액세스 VPN 서버를 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-111">Contoso deployed remote access VPN servers in each satellite office so that remote workers would use a regionally close entry point for access to the Contoso intranet.</span></span>

<span data-ttu-id="de25b-112">Contoso는 또한 분할 터널링을 위해 랩톱, 태블릿 및 스마트폰에 설치된 VPN 클라이언트의 구성을 업데이트하여 최적화된 Office 365 끝점 집합에 대한 트래픽이 VPN 연결을 무시하고 인터넷을 통해 직접 전송되었습니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-112">Contoso also updated the configuration of VPN clients installed on laptops, tablets, and smart phones for split tunneling so that traffic for the Optimize set of Office 365 endpoints bypassed the VPN connection and was sent directly over the internet.</span></span> <span data-ttu-id="de25b-113">자세한 내용은 VPN 분할 터널링을 사용하여 원격 사용자에 대한 [Office 365 연결 최적화를 참조하세요.](../enterprise/microsoft-365-vpn-split-tunnel.md)</span><span class="sxs-lookup"><span data-stu-id="de25b-113">For more information, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).</span></span>

<span data-ttu-id="de25b-114">다음은 파리 본사 및 각 위성 사무소에 VPN 장치를 설치한 결과 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-114">Here is the resulting configuration with VPN devices installed in the Paris headquarters and each of the satellite offices.</span></span> 

![Contoso의 VPN 인프라](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

<span data-ttu-id="de25b-116">설치된 VPN 클라이언트가 있는 원격 작업원은 DNS를 사용하여 지역적으로 가장 가까운 사무실을 찾은 후 설치된 VPN 장치에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-116">A remote worker with the installed VPN client uses DNS to find the regionally closest office and connects to the VPN device installed there.</span></span> <span data-ttu-id="de25b-117">분할 터널링을 통해 Microsoft 365 최적화 끝점에 대한 트래픽이 지역적으로 가장 가까운 Microsoft 365 네트워크 위치로 직접 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-117">With split tunneling, traffic to Microsoft 365 Optimize endpoints gets sent directly to the regionally closest Microsoft 365 network location.</span></span> <span data-ttu-id="de25b-118">다른 모든 트래픽은 VPN 연결을 통해 VPN 장치로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-118">All other traffic gets sent over the VPN connection to the VPN device.</span></span>

## <a name="contosos-support-for-remote-and-onsite-work"></a><span data-ttu-id="de25b-119">Contoso의 원격 및 인사이트 작업 지원</span><span class="sxs-lookup"><span data-stu-id="de25b-119">Contoso’s support for remote and onsite work</span></span>

<span data-ttu-id="de25b-120">지역 잠금 중에 대부분 원격 작업자를 지원하기 위해 초기 변경이 적용된 후 Contoso는 원격 및 출장 작업을 지원하기 위해 인프라를 변경하여 작업자가 다음을 할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-120">After the initial changes were made to support mostly remote workers during regional lockdowns, Contoso made infrastructure changes to support remote and onsite work in which a worker could be:</span></span>

- <span data-ttu-id="de25b-121">항상 원격.</span><span class="sxs-lookup"><span data-stu-id="de25b-121">Always remote.</span></span>
- <span data-ttu-id="de25b-122">항상 Onsite.</span><span class="sxs-lookup"><span data-stu-id="de25b-122">Always onsite.</span></span>
- <span data-ttu-id="de25b-123">사설 및 원격의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-123">A combination of onsite and remote.</span></span>

<span data-ttu-id="de25b-124">Microsoft 365 ID, 보안 및 규정 준수 기능은 제로 트러스트용으로 설계되었습니다. 사용자 및 장치의 위치에 관계없이 작동하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-124">Microsoft 365 identity, security, and compliance features are designed for Zero Trust and to work regardless of the location of the user and their device.</span></span> <span data-ttu-id="de25b-125">자세한 내용은 [제로 트러스트를 참조하세요.](https://www.microsoft.com/security/business/zero-trust)</span><span class="sxs-lookup"><span data-stu-id="de25b-125">For more information, see [Zero Trust](https://www.microsoft.com/security/business/zero-trust).</span></span>

<span data-ttu-id="de25b-126">그러나 설치할 소프트웨어가 온-프레미스 또는 인터넷 원본에서 제공될 수 있기 때문에 새 소프트웨어 설치 및 업데이트 관리는 장치의 위치에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-126">However, managing new installs and updates of software is dependent on the location of the device because the software to install could come from an on-premises or an internet source.</span></span> <span data-ttu-id="de25b-127">Contoso IT 설계자는 새로운 설치 및 업데이트 인프라를 작업자가 아닌 디바이스의 위치에 따라 설계했습니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-127">Contoso IT architects designed their new installs and updates infrastructure based on the location of the device, rather than the worker.</span></span>

<span data-ttu-id="de25b-128">이 두 가지 유형의 장치를 지정했습니다. 전용은 전용 On-premises 및 roaming입니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-128">They designated two types of devices: dedicated on-premises and roaming.</span></span>

### <a name="dedicated-on-premises"></a><span data-ttu-id="de25b-129">전용 On-premises</span><span class="sxs-lookup"><span data-stu-id="de25b-129">Dedicated on-premises</span></span>

<span data-ttu-id="de25b-130">전용 On-premises 장치는 Contoso 인트라넷을 떠나지 않는 데스크톱 또는 서버 컴퓨터로, VPN 클라이언트가 설치되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-130">A dedicated on-premises device is a desktop or server computer that never leaves the Contoso intranet and does not have a VPN client installed.</span></span> <span data-ttu-id="de25b-131">이러한 On-premises 장치는 Windows 10, 엔터프라이즈용 Microsoft 365 앱 및 에지 브라우저의 설치 및 업데이트에 Microsoft Endpoint Configuration Manager 및 배포 지점을 계속 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-131">These on-premises devices continue to use Microsoft Endpoint Configuration Manager and its distribution points for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and the Edge browser.</span></span>

### <a name="roaming"></a><span data-ttu-id="de25b-132">로밍</span><span class="sxs-lookup"><span data-stu-id="de25b-132">Roaming</span></span>

<span data-ttu-id="de25b-133">로밍 장치는 Contoso 인트라넷을 떠날 수 있으며, Contoso VPN 클라이언트가 설치된 스마트폰 및 태블릿과 같은 여러 사무실 작업자와 모든 원격 작업자 및 기타 조직 소유의 장치에 발급된 랩톱을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-133">A roaming device can leave the Contoso intranet and includes laptops issued to many office workers and all remote workers and other organization-owned devices such as smart phones and tablets with the Contoso VPN client installed.</span></span> 

<span data-ttu-id="de25b-134">이러한 장치는 인터넷에 연결할 수 있기 때문에 Windows 10, 엔터프라이즈용 Microsoft 365 앱 및 Edge의 설치 및 업데이트에 Intune 또는 기타 클라우드 기반 서비스를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-134">Because these devices can be connected to the Internet at any given time, they use Intune or other cloud-based services for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="de25b-135">기존 On-premises Configuration Manager 배포 지점을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-135">They do not use the existing on-premises Configuration Manager distribution points.</span></span>

<span data-ttu-id="de25b-136">즉, 로밍 장치에 대한 일부 설치 및 업데이트는 인터넷을 통해 수행되고, 이러한 설치 및 업데이트는 인트라넷에 연결되어 있는 동안 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-136">This means some of the installs and updates for roaming device will be done over the internet while they are on-premises and connected to the intranet.</span></span> <span data-ttu-id="de25b-137">그러나 Contoso IT 설계자는 특히 대부분의 원격 작업자가 인트라넷에 연결되지 않은 경우 인터넷에 대한 인트라넷 대역폭을 최적화하는 것보다 구성의 단순성을 중요하게 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-137">But Contoso IT architects decided that simplicity of configuration was more important than optimization of intranet bandwidth to the internet, especially when most remote workers are seldom connected to the intranet.</span></span>

<span data-ttu-id="de25b-138">결과 인프라는 다음과 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-138">Here is the resulting infrastructure.</span></span>

![Contoso의 설치 및 업데이트 인프라](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

<span data-ttu-id="de25b-140">설치 및 업데이트 동작은 장치의 컴퓨터 계정을 다음 그룹 중 하나의 구성원으로 설정하여 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-140">Install and update behavior is determined by making the computer accounts of devices a member of one of these groups:</span></span>

- <span data-ttu-id="de25b-141">OnPremDevices</span><span class="sxs-lookup"><span data-stu-id="de25b-141">OnPremDevices</span></span>

  <span data-ttu-id="de25b-142">장치의 Configuration Manager 클라이언트는 설치 및 업데이트에 배포 지점을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-142">The Configuration Manager client on the device uses distribution points for installs and updates.</span></span>

- <span data-ttu-id="de25b-143">RoamingDevices</span><span class="sxs-lookup"><span data-stu-id="de25b-143">RoamingDevices</span></span>

  <span data-ttu-id="de25b-144">Intune 및 디바이스의 기타 설정은 설치 및 업데이트에 Microsoft 365 네트워크 사용을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-144">Intune and other settings on the device specify the use of the Microsoft 365 network for installs and updates.</span></span>

## <a name="new-onboarding-process"></a><span data-ttu-id="de25b-145">새 온보더링 프로세스</span><span class="sxs-lookup"><span data-stu-id="de25b-145">New onboarding process</span></span>

<span data-ttu-id="de25b-146">새 작업자 또는 데이터 센터의 새 서버에 대해 발급된 새 전용 On-premises 장치의 경우, 사용자가 로그인하면 OnPremDevices 그룹의 디바이스 멤버 자격에 따라 Configuration Manager 클라이언트가 Windows 10, 엔터프라이즈용 Microsoft 365 앱 및 Edge에 대한 최신 업데이트를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-146">For a new dedicated on-premises device issued to a new worker or for a new server in a datacenter, when the worker signs in, the Configuration Manager client based on the device's membership in the OnPremDevices group downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge from on-premises Configuration Manager distribution points.</span></span> <span data-ttu-id="de25b-147">완료되면 전용 On-premises 장치를 사용할 수 있으며 지속적인 업데이트에 이러한 배포 지점을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-147">When complete, the dedicated on-premises device is ready for use and uses these distribution points for ongoing updates.</span></span>

<span data-ttu-id="de25b-148">새 작업 담당자에게 발급된 새 원격 장치의 경우, 로밍Devices 그룹의 구성원 자격에 따라 장치가 Intune 클라우드 서비스 및 기타 서비스에 연결하고 Windows 10, 엔터프라이즈용 Microsoft 365 앱 및 Edge에 대한 최신 업데이트를 다운로드하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-148">For a new remote device issued to a new worker, when the worker signs in, the device, based on its membership in the RoamingDevices group, contacts the Intune cloud service and other services and downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="de25b-149">완료되면 원격 장치를 사용할 준비가 완료되고 설치된 VPN 클라이언트를 사용하여 진행되는 업데이트에 대한 Microsoft 365 네트워크 및 Microsoft 365 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-149">When complete, the remote device is ready for use and uses the installed VPN client for access to on-premises resources and the Microsoft 365 network for ongoing updates.</span></span>

## <a name="next-step"></a><span data-ttu-id="de25b-150">다음 단계</span><span class="sxs-lookup"><span data-stu-id="de25b-150">Next step</span></span>

<span data-ttu-id="de25b-151">[조직의 원격 작업자에게](empower-people-to-work-remotely.md) 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="de25b-151">[Empower the remote workers](empower-people-to-work-remotely.md) in your organization.</span></span>
