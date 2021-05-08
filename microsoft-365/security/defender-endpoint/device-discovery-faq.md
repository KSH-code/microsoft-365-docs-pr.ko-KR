---
title: 장치 검색에 자주 묻는 질문
description: 장치 검색에 대한 FAQ(질문과 대답)에 대한 답변 찾기
keywords: 장치 검색, 검색, 수동, 사전, 네트워크, 표시 여부, 서버, Workstation, 온보드, 관리되지 않는 장치
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1c61e69b5c8d414ab229fa8bf64eb657a6e40304
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245963"
---
# <a name="device-discovery-frequently-asked-questions"></a><span data-ttu-id="75b1f-104">장치 검색에 자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="75b1f-104">Device discovery frequently asked questions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="75b1f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="75b1f-105">**Applies to:**</span></span>
- [<span data-ttu-id="75b1f-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="75b1f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="75b1f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75b1f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="75b1f-108">장치 검색에 대한 FAQ(질문과 대답)에 대한 답변을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-108">Find answers to frequently asked questions (FAQs) about device discovery.</span></span>

## <a name="what-is-basic-discovery-mode"></a><span data-ttu-id="75b1f-109">기본 검색 모드란?</span><span class="sxs-lookup"><span data-stu-id="75b1f-109">What is Basic discovery mode?</span></span>
<span data-ttu-id="75b1f-110">이 모드를 사용하면 모든 끝점용 Microsoft Defender 온보딩 장치에서 네트워크 데이터를 수집하고 인접한 장치를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-110">This mode allows every Microsoft Defender for Endpoint onboarded device to collect network data and discover neighboring devices.</span></span> <span data-ttu-id="75b1f-111">온보드 엔드포인트는 네트워크에서 수동적으로 이벤트를 수집하고 해당 끝점에서 장치 정보를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-111">Onboarded endpoints passively collect events in the network and extract device information from them.</span></span> <span data-ttu-id="75b1f-112">네트워크 트래픽이 시작되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-112">No network traffic will be initiated.</span></span> <span data-ttu-id="75b1f-113">온보드 엔드포인트는 단순히 온보더된 장치에서 볼 수 있는 모든 네트워크 트래픽에서 데이터를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-113">Onboarded endpoints will simply extract data from every network traffic that is seen by an onboarded device.</span></span> <span data-ttu-id="75b1f-114">네트워크에서 관리되지 않는 장치를 나열하는 데 사용되는 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-114">This data used to list unmanaged devices in your network.</span></span>

## <a name="can-i-disable-basic-discovery"></a><span data-ttu-id="75b1f-115">기본 검색을 사용하지 않도록 설정할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="75b1f-115">Can I disable Basic discovery?</span></span>
<span data-ttu-id="75b1f-116">고급 기능 페이지를 통해 장치 검색을 해제할 [수](advanced-features.md) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-116">You have the option to turn off device discovery through the [Advanced features](advanced-features.md) page.</span></span> <span data-ttu-id="75b1f-117">그러나 네트워크에서 관리되지 않는 장치에 대한 가시성을 잃게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-117">However, you will lose visibility on unmanaged devices in your network.</span></span> 

## <a name="what-is-standard-discovery-mode"></a><span data-ttu-id="75b1f-118">표준 검색 모드란?</span><span class="sxs-lookup"><span data-stu-id="75b1f-118">What is Standard discovery mode?</span></span>
 <span data-ttu-id="75b1f-119">이 모드 끝점에서 끝점용 Microsoft Defender에 온보딩된 끝점은 네트워크에서 관찰된 장치를 적극적으로 프로브하여 수집된 데이터를 보강할 수 있습니다(네트워크 트래픽의 미미한 양).</span><span class="sxs-lookup"><span data-stu-id="75b1f-119">In this mode endpoints onboarded to Microsoft Defender for Endpoint can actively probe observed devices in the network to enrich collected data (with negligible amount of network traffic).</span></span> <span data-ttu-id="75b1f-120">이 모드는 신뢰할 수 있고 뛰어난 장치 인벤토리를 구축하는 데 매우 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-120">This mode is highly recommended for building a reliable and coherent device inventory.</span></span> <span data-ttu-id="75b1f-121">이 모드를 사용하지 않도록 선택하고 기본 검색 모드를 선택하면 네트워크에서 관리되지 않는 끝점만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-121">If you choose to disable this mode, and select Basic discovery mode, you will likely only gain limited visibility of unmanaged endpoints in your network.</span></span>

## <a name="can-i-control-which-devices-perform-standard-discovery"></a><span data-ttu-id="75b1f-122">표준 검색을 수행하는 장치를 제어할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="75b1f-122">Can I control which devices perform Standard discovery?</span></span>
 <span data-ttu-id="75b1f-123">표준 검색을 수행하는 데 사용되는 장치 목록을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-123">You can customize the list of devices that are used to perform Standard discovery.</span></span> <span data-ttu-id="75b1f-124">이 기능을 지원하는 모든 온보드 디바이스에서 Standard 검색을 사용하도록 설정하거나(현재 Windows 10 장치만 해당) 장치 태그를 지정하여 장치의 하위 집합 또는 하위 집합을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-124">You can either enable Standard discovery on all the onboarded devices that also support this capability (currently Windows 10 devices only) or select a subset or subsets of your devices by specifying their device tags.</span></span> <span data-ttu-id="75b1f-125">이 경우 다른 모든 장치는 기본 검색만 실행하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-125">In this case, all other devices will be configured to run Basic discovery only.</span></span> <span data-ttu-id="75b1f-126">구성은 장치 검색 설정 페이지에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-126">The configuration is available in the device discovery settings page.</span></span>

## <a name="can-i-exclude-unmanaged-devices-from-the-device-inventory-list"></a><span data-ttu-id="75b1f-127">관리되지 않는 장치를 장치 인벤토리 목록에서 제외할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="75b1f-127">Can I exclude unmanaged devices from the device inventory list?</span></span>
<span data-ttu-id="75b1f-128">예, 장치 인벤토리 목록에서 관리되지 않는 장치를 제외하는 필터를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-128">Yes, you can apply filters exclude unmanaged devices from the device inventory list.</span></span> <span data-ttu-id="75b1f-129">API 쿼리의 등록 상태 열을 사용하여 관리되지 않는 장치를 필터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-129">You can also use the onboarding status column on API queries to filter out unmanaged devices.</span></span> 


## <a name="which-onboarded-devices-can-perform-discovery"></a><span data-ttu-id="75b1f-130">검색을 수행할 수 있는 온보드 장치는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="75b1f-130">Which onboarded devices can perform discovery?</span></span>
 <span data-ttu-id="75b1f-131">Windows 10 버전 1809 이상에서 실행되는 온보드 장치는 검색을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-131">Onboarded devices running on Windows 10 version 1809 or later can perform discovery.</span></span>

## <a name="what-happens-if-my-onboarded-devices-is-connected-to-my-home-network-or-to-public-access-point"></a><span data-ttu-id="75b1f-132">온보드 장치가 홈 네트워크 또는 공용 액세스 지점에 연결되어 있는 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="75b1f-132">What happens if my onboarded devices is connected to my home network, or to public access point?</span></span>
 <span data-ttu-id="75b1f-133">검색 엔진은 회사 네트워크에서 수신되는 네트워크 이벤트와 회사 네트워크 외부에서 수신되는 네트워크 이벤트를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-133">The discovery engine distinguishes between network events that are received in the corporate network versus outside of the corporate network.</span></span> <span data-ttu-id="75b1f-134">모든 테넌트 클라이언트에서 네트워크 식별자를 상호 연결하면 개인 네트워크와 회사 네트워크에서 받은 이벤트 간에 이벤트가 차별화됩니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-134">By correlating network identifiers across all tenant's clients, events are differentiated between ones that were received from private networks and corporate networks.</span></span> <span data-ttu-id="75b1f-135">예를 들어 네트워크 보고서에 있는 대부분의 장치가 동일한 네트워크 이름에 연결되어 기본 게이트웨이와 DHCP 서버 주소가 동일한 경우 이 네트워크가 회사 네트워크일 수 있는 것으로 가정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-135">For example, if the majority of the devices in the network report that they are connected to the same network name, with the same default gateway and DHCP server address, it can be assumed that this network is likely a corporate network.</span></span> <span data-ttu-id="75b1f-136">개인 네트워크 장치는 인벤토리에 나열되지 않을 뿐만 아니라 적극적으로 프로브되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-136">Private network devices will not be listed in the inventory and will not be actively probed.</span></span>

## <a name="what-protocols-are-you-capturing-and-analyzing"></a><span data-ttu-id="75b1f-137">어떤 프로토콜을 캡처하고 분석하나요?</span><span class="sxs-lookup"><span data-stu-id="75b1f-137">What protocols are you capturing and analyzing?</span></span>
 <span data-ttu-id="75b1f-138">기본적으로 Windows 10 버전 1809 이상에서 실행되는 모든 온보드 장치는 ARP, CDP, DHCP, DHCPv6, IP(헤더), LLDP, LLMNR, mDNS, MNDP, NBNS, SSDP, TCP(헤더), UDP(헤더), WSD 프로토콜을 캡처하고 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-138">By default, all onboarded devices running on Windows 10 version 1809 or later are capturing and analyzing the following protocols: ARP, CDP, DHCP, DHCPv6, IP (headers), LLDP, LLMNR, mDNS, MNDP, NBNS, SSDP, TCP (headers), UDP (headers), WSD</span></span>

## <a name="which-protocols-do-you-use-for-active-probing-in-standard-discovery"></a><span data-ttu-id="75b1f-139">표준 검색에서 활성 프로비전에 어떤 프로토콜을 사용하나요?</span><span class="sxs-lookup"><span data-stu-id="75b1f-139">Which protocols do you use for active probing in Standard discovery?</span></span>
 <span data-ttu-id="75b1f-140">장치가 표준 검색을 실행하도록 구성된 경우 노출된 서비스는 ARP, FTP, HTTP, ICMP, LLMNR, NBNS, RDP, SIP, SMTP, SNMP, SSH, Telnet, UPNP, WSD, SMB, NBSS, IPP, PJL을 사용하여 프로브되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-140">When a device is configured to run Standard discovery, exposed services are being probed by using the following protocols: ARP, FTP, HTTP, ICMP, LLMNR, NBNS, RDP, SIP, SMTP, SNMP, SSH, Telnet, UPNP, WSD, SMB, NBSS, IPP, PJL</span></span>

## <a name="how-can-i-exclude-targets-from-being-probed-with-standard-discovery"></a><span data-ttu-id="75b1f-141">표준 검색을 사용하여 대상이 프로브되지 못하게 제외하는 방법</span><span class="sxs-lookup"><span data-stu-id="75b1f-141">How can I exclude targets from being probed with Standard discovery?</span></span>
 <span data-ttu-id="75b1f-142">네트워크에 적극적으로 프로브하지 말아야 하는 장치가 있는 경우 제외 목록을 정의하여 검사하지 못하게 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-142">If there are devices on your network which should not be actively probed, you can also define a list of exclusions to prevent them from being scanned.</span></span> <span data-ttu-id="75b1f-143">구성은 장치 검색 설정 페이지에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-143">The configuration is available in the device discovery settings page.</span></span>

## <a name="can-i-exclude-devices-from-being-discovered"></a><span data-ttu-id="75b1f-144">장치가 검색되지 못하게 제외할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="75b1f-144">Can I exclude devices from being discovered?</span></span>
 <span data-ttu-id="75b1f-145">장치 검색에서는 수동 방법을 사용하여 네트워크에서 장치를 검색할 때 회사 네트워크의 온보드 장치와 통신하는 모든 장치를 검색하여 인벤토리에 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-145">As device discovery uses passive methods to discover devices in the network, any device that communicates with your onboarded devices in the corporate network can be discovered and listed in the inventory.</span></span> <span data-ttu-id="75b1f-146">장치를 활성 프로비전에서만 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-146">You can exclude devices from active probing only.</span></span>

## <a name="how-frequent-is-the-active-probing"></a><span data-ttu-id="75b1f-147">활성 프로비전은 얼마나 자주 하나요?</span><span class="sxs-lookup"><span data-stu-id="75b1f-147">How frequent is the active probing?</span></span>
 <span data-ttu-id="75b1f-148">장치 특성의 변경이 관찰될 때(1~3주마다) 기존 정보가 최신 상태인지 확인하려면 디바이스가 적극적으로 프로브됩니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-148">Devices will actively be probed when changes in device characteristics are observed (every 1 to 3 weeks) to make sure the existing information is up-to-date.</span></span>

## <a name="my-security-tool-raised-alert-on-unicastscannerps1-or-port-scanning-activity-initiated-by-it-what-should-i-do"></a><span data-ttu-id="75b1f-149">보안 도구에서 시작된 UnicastScanner.ps1 포트 검색 활동에 대해 경고가 발생했습니다. 어떻게 해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="75b1f-149">My security tool raised alert on UnicastScanner.ps1 or port scanning activity initiated by it, what should I do?</span></span>
 <span data-ttu-id="75b1f-150">활성 프로비전 스크립트는 Microsoft에서 서명하며 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-150">The active probing scripts are signed by Microsoft and are safe.</span></span> <span data-ttu-id="75b1f-151">제외 목록에 다음 경로를 추가할 수 있습니다. `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`</span><span class="sxs-lookup"><span data-stu-id="75b1f-151">You can add the following path to your exclusion list: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`</span></span>


## <a name="what-is-the-amount-of-traffic-being-generated-by-the-standard-discovery-active-probe"></a><span data-ttu-id="75b1f-152">Standard 검색 활성 프로브에서 생성되는 트래픽의 양은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="75b1f-152">What is the amount of traffic being generated by the Standard discovery active probe?</span></span>
 <span data-ttu-id="75b1f-153">활성 프로비전은 모든 프로비전 시도 시 온보더된 장치와 프로브 장치 간에 최대 5K의 트래픽을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-153">Active probing can generate up to 5K of traffic between the onboarded device and the probed device, every probing attempt</span></span>

## <a name="why-is-there-a-discrepancy-between-can-be-onboarded-devices-in-the-device-inventory-and-the-number-of-devices-to-onboard-in-the-dashboard-tile"></a><span data-ttu-id="75b1f-154">장치 인벤토리에 "온보드할 수 있는" 장치와 대시보드 타일의 "온보더할 장치" 수가 불일치하는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="75b1f-154">Why is there a discrepancy between "can be onboarded" devices in the device inventory, and the number of "devices to onboard" in the dashboard tile?</span></span>
<span data-ttu-id="75b1f-155">장치 인벤토리의 "온보딩할 수 있습니다." 아래에 나열된 장치 수, "끝점용 Microsoft Defender에 온보딩" 보안 권장 및 "온보딩할 장치" 대시보드 위젯의 수가 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-155">You may notice differences between the number of listed devices under "can be onboarded" in the device inventory, "onboard to Microsoft Defender for Endpoint" security recommendation, and "devices to onboard" dashboard widget.</span></span>

 <span data-ttu-id="75b1f-156">보안 권장 및 대시보드 위젯은 네트워크에서 안정된 디바이스에 사용됩니다. 비정기 장치, 게스트 장치 및 기타 제외</span><span class="sxs-lookup"><span data-stu-id="75b1f-156">The security recommendation and the dashboard widget are for devices that are stable in the network; excluding ephemeral devices, guest devices and others.</span></span> <span data-ttu-id="75b1f-157">이 아이디어는 조직의 전체 보안 점수를 의미하는 영구 장치에 권장하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-157">The idea is to recommend on persistent devices, that also imply on the overall security score of the organization.</span></span>

## <a name="can-i-onboard-unmanaged-devices-that-were-found"></a><span data-ttu-id="75b1f-158">찾은 관리되지 않는 장치를 온보드할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="75b1f-158">Can I onboard unmanaged devices that were found?</span></span>
 <span data-ttu-id="75b1f-159">예.</span><span class="sxs-lookup"><span data-stu-id="75b1f-159">Yes.</span></span> <span data-ttu-id="75b1f-160">네트워크에서 관리되지 않는 끝점은 네트워크에 취약성 및 위험을 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-160">Unmanaged endpoints in your network introduce vulnerabilities and risks to your network.</span></span> <span data-ttu-id="75b1f-161">서비스를 온보더링하면 서비스에 대한 보안 가시성을 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75b1f-161">Onboarding them to the service can increase the security visibility on them.</span></span> 


