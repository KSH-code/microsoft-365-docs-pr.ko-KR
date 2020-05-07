---
title: 2단계. 온-프레미스 앱 및 서비스로의 원격 액세스 제공
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: Microsoft 365 클라우드 서비스로의 액세스를 최적화하는 동안 원격 작업자는 온-프레미스 리소스에 액세스할 수 있는지 확인합니다.
ms.openlocfilehash: daa1a04912dd83c7a53769299b3870b90dbfd33a
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049561"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a><span data-ttu-id="a11e5-104">2단계.</span><span class="sxs-lookup"><span data-stu-id="a11e5-104">Step 2.</span></span> <span data-ttu-id="a11e5-105">온-프레미스 앱 및 서비스로의 원격 액세스 제공</span><span class="sxs-lookup"><span data-stu-id="a11e5-105">Provide remote access to on-premises apps and services</span></span>

<span data-ttu-id="a11e5-106">조직에서 원격 액세스 VPN 솔루션을 사용하는 경우(일반적으로 사용자 장치에는 네트워크의 가장자리에 VPN 서버와 VPN 클라이언트를 설치), 사용자는 온-프레미스 앱과 서버에 액세스하는 데 원격 액세스 VPN 연결을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-106">If your organization uses a remote access VPN solution, typically with VPN servers on the edge of your network and VPN clients installed on your users' devices, your users can use remote access VPN connections to access on-premises apps and servers.</span></span> <span data-ttu-id="a11e5-107">하지만 Microsoft 365 클라우드 기반 서비스로의 트래픽을 최적화해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-107">But you may need to optimize traffic to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="a11e5-108">사용자가 VPN 솔루션을 사용하지 않는 경우에는 Azure AD(Azure Active Directory) 응용 프로그램 프록시 및 Azure 지점 및 사이트 간(P2S) VPN을 사용하여 모든 앱이 웹 기반 인지에 따라 액세스 권한을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-108">If your users do not use a VPN solution, you can use Azure Active Directory (Azure AD) Application Proxy and Azure Point-to-Site (P2S) VPN to provide access, depending on whether all your apps are web-based.</span></span>

<span data-ttu-id="a11e5-109">다음과 같은 세 가지 기본 구성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-109">There are three primary configurations:</span></span>

1. <span data-ttu-id="a11e5-110">이미 원격 액세스 VPN 솔루션을 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-110">You are already using a remote access VPN solution.</span></span>
2. <span data-ttu-id="a11e5-111">원격 액세스 VPN 솔루션을 사용하지 않고 있으며 하이브리드 ID가 있어, 사용자는 온-프레미스 웹 기반 앱으로의 원격 액세스만 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-111">You are not using a remote access VPN solution, you have hybrid identity, and you need remote access only to on-premises web-based apps.</span></span>
3. <span data-ttu-id="a11e5-112">원격 액세스 VPN 솔루션을 사용하지 않고 있어, 온-프레미스 앱으로의 액세스 권한이 필요하며 앱 중 일부는 웹 기반이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-112">You are not using a remote access VPN solution and you need access to on-premises apps, some of which are not web-based.</span></span>

<span data-ttu-id="a11e5-113">이 문서에서 설명하는 원격 액세스 구성 옵션을 보려면 이 순서도를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a11e5-113">See this flowchart for the remote access configuration options discussed in this article.</span></span>

![원격 액세스 구성 순서도](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-flowchart.png)

<span data-ttu-id="a11e5-115">또한 원격 액세스 연결을 사용하여 [원격 데스크톱](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop)을 사용하여 사용자를 온-프레미스 PC에 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-115">With remote access connections, you can also use [Remote Desktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) to connect your users to an on-premises PC.</span></span> <span data-ttu-id="a11e5-116">예를 들어 원격 작업자는 원격 데스크톱을 사용 하 여 Windows, iOS 또는 Android 장치에서 사무실의 PC에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-116">For example, a remote worker can use Remote Desktop to connect to the PC in their office from their Windows, iOS or Android device.</span></span> <span data-ttu-id="a11e5-117">원격으로 연결되면 바로 앞에 앉아있는 것처럼 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-117">Once they are remotely connected, they can use it as if they were sitting in front of it.</span></span>

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a><span data-ttu-id="a11e5-118">Microsoft 365 클라우드 서비스에 대한 원격 액세스 VPN 클라이언트의 성능 최적화</span><span class="sxs-lookup"><span data-stu-id="a11e5-118">Optimize performance for remote access VPN clients to Microsoft 365 cloud services</span></span>

<span data-ttu-id="a11e5-119">원격 작업자가 기존 VPN 클라이언트를 사용하 여 조직 네트워크에 대한 원격 액세스 권한을 얻는 경우, VPN 클라이언트에 분할 터널링 지원이 되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-119">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span>

<span data-ttu-id="a11e5-120">분할 터널링을 사용하지 않는 경우에는 모든 원격 작업 트래픽이 조직의 에지 장치로 전송되어 처리된 후 인터넷으로 전송되지 않고 VPN 연결을 통해 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-120">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span>

![터널링이 없는 VPN 클라이언트의 네트워크 트래픽](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="a11e5-122">Microsoft 365 트래픽은 조직을 통해 간접 경로를 가져와야 하며 이는 그 후 VPN 클라이언트의 실제 위치에서 멀리 떨어져 있는 Microsoft 네트워크 진입점으로 전달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-122">Microsoft 365 traffic must take an indirect route through your organization, which could be the forwarded to a Microsoft network entry point far away from the VPN client’s physical location.</span></span> <span data-ttu-id="a11e5-123">이 간접 경로는 네트워크 트래픽에 대기 시간을 더하여 전반적인 성능을 저하시킵니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-123">This indirect path adds latency to the network traffic and decreases overall performance.</span></span> 

<span data-ttu-id="a11e5-124">분할 터널링을 사용할 경우, 사용자는 특정 유형의 트래픽을 제외하여 VPN 연결을 통해 조직 네트워크에 보내지 않도록 VPN 클라이언트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-124">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="a11e5-125">Microsoft 365 클라우드 리소스에 대한 액세스를 최적화하려면 VPN 연결을 통해 범주 **최적화** Microsoft 365 끝점으로의 트래픽을 제외하도록 분할 터널링 VPN 클라이언트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-125">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="a11e5-126">자세한 내용은 [Office 365 끝점 범주](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a11e5-126">For more information, see [Office 365 endpoint categories](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span></span> <span data-ttu-id="a11e5-127">[여기](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)에서 범주 최적화 끝점 목록을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a11e5-127">See the list of Optimize category endpoints [here](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

![터널링이 있는 VPN 클라이언트에서의 네트워크 트래픽](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="a11e5-129">이는 VPN 클라이언트가 인터넷을 통해 직접 중요한 Microsoft 365 클라우드 서비스 트래픽을 가장 가까운 진입점으로 Microsoft 네트워크로 전송하고 받도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-129">This allows the VPN client to send and receive crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest entry point into the Microsoft network.</span></span>

<span data-ttu-id="a11e5-130">자세한 내용과 지침은 [VPN 분산 터널링을 사용한 원격 근무자의 Office 365 연결 최적화](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)를 참조하세요. </span><span class="sxs-lookup"><span data-stu-id="a11e5-130">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).</span></span>

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a><span data-ttu-id="a11e5-131">모든 앱이 웹 앱이고 하이브리드 ID가 있는 경우 원격 액세스 배포</span><span class="sxs-lookup"><span data-stu-id="a11e5-131">Deploy remote access when all your apps are web apps and you have hybrid identity</span></span>

<span data-ttu-id="a11e5-132">원격 작업자가 기존 VPN 클라이언트를 사용하지 않고 온-프레미스 사용자 계정 및 그룹이 Azure AD와 동기화되어 있는 경우, Azure AD 응용 프로그램 프록시를 사용하여 인트라넷 서버에 호스트되는 웹 기반 응용 프로그램에 대한 안전한 원격 액세스를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-132">If your remote workers are not using a traditional VPN client and your on-premises user accounts and groups are synchronized with Azure AD, you can use Azure AD Application Proxy to provide secure remote access for web-based applications hosted on intranet servers.</span></span> <span data-ttu-id="a11e5-133">웹 기반 응용 프로그램에는 SharePoint 사이트, Outlook Web Access 서버 또는 기타 웹 기반 기간 업무 비즈니스 응용 프로그램이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-133">Web-based applications include SharePoint sites, Outlook Web Access servers, or any other web-based line of business applications.</span></span> 

<span data-ttu-id="a11e5-134">Azure AD 응용 프로그램 프록시의 구성 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-134">Here are the components of Azure AD Application Proxy.</span></span>

![Azure AD 응용 프로그램 프록시의 구성 요소](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

<span data-ttu-id="a11e5-136">자세한 내용은 이 [Azure AD 응용 프로그램 프록시 개요](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a11e5-136">For more information, see this [overview of Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span></span>

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a><span data-ttu-id="a11e5-137">모든 앱이 웹 앱이 아닌 경우의 원격 액세스 배포</span><span class="sxs-lookup"><span data-stu-id="a11e5-137">Deploy remote access when not all your apps are web apps</span></span>

<span data-ttu-id="a11e5-138">원격 작업자가 기존 VPN 클라이언트를 사용하고 있지 않고 웹 기반이 아닌 앱이 있는 경우, Azure 지점 및 사이트 간(P2S) VPN을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-138">If your remote workers are not using a traditional VPN client and any of your apps are not web-based, you can use an Azure Point-to-Site (P2S) VPN.</span></span>

<span data-ttu-id="a11e5-139">P2S VPN 연결은 Azure 가상 네트워크를 통해 원격 작업자의 장치에서 조직 네트워크로의 연결을 안전하게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-139">A P2S VPN connection creates a secure connection from a remote worker’s device to your organization network through an Azure virtual network.</span></span> 

![Azure P2S VPN의 구성 요소](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

<span data-ttu-id="a11e5-141">자세한 내용은 이 [P2S VPN의 개요](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a11e5-141">For more information, see this [overview of P2S VPN](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span></span>

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a><span data-ttu-id="a11e5-142">Windows Virtual Desktop을 배포하여 개인 장치를 사용하는 원격 작업자에게 원격 액세스 기능을 제공</span><span class="sxs-lookup"><span data-stu-id="a11e5-142">Deploy Windows Virtual Desktop to provide remote access for remote workers using personal devices</span></span> 

<span data-ttu-id="a11e5-143">개인 장치 및 관리되지 않는 장치만 사용할 수 있는 원격 작업자를 지원하려면 Azure에서 Windows Virtual Desktop을 사용하여 사용자가 집에서 사용할 가상 데스크톱을 만들고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-143">To support remote workers who can only use their personal and unmanaged devices, use Windows Virtual Desktop in Azure to create and allocate virtual desktops for your users to use from home.</span></span>

<span data-ttu-id="a11e5-144">가상화된 PC는 조직 네트워크에 연결된 PC와 동일하게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-144">Virtualized PCs can act just like PCs connected to your organization network.</span></span>

<span data-ttu-id="a11e5-145">자세한 내용은 [Windows Virtual Desktop의 개요](https://docs.microsoft.com/azure/virtual-desktop/overview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a11e5-145">For more information, see [this overview of Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview).</span></span>

## <a name="admin-technical-resources-for-remote-access"></a><span data-ttu-id="a11e5-146">원격 액세스를 위한 관리자 기술 리소스</span><span class="sxs-lookup"><span data-stu-id="a11e5-146">Admin technical resources for remote access</span></span>

- [<span data-ttu-id="a11e5-147">원격 직원에 맞게 Office 365 트래픽을 빠르게 최적화하고 인프라의 부하를 줄이는 방법</span><span class="sxs-lookup"><span data-stu-id="a11e5-147">How to quickly optimize Office 365 traffic for remote staff & reduce the load on your infrastructure</span></span>](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)
- [<span data-ttu-id="a11e5-148">VPN 분할 터널링을 사용하여 원격 사용자의 Office 365 연결 최적화</span><span class="sxs-lookup"><span data-stu-id="a11e5-148">Optimize Office 365 connectivity for remote users using VPN split tunneling</span></span>](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)

## <a name="results-of-step-2"></a><span data-ttu-id="a11e5-149">2단계의 결과</span><span class="sxs-lookup"><span data-stu-id="a11e5-149">Results of Step 2</span></span>

<span data-ttu-id="a11e5-150">원격 작업자를 위한 원격 액세스 솔루션을 배포한 후에는 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-150">After deployment of a remote access solution for your remote workers:</span></span>

| <span data-ttu-id="a11e5-151">원격 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="a11e5-151">Remote access configuration</span></span> | <span data-ttu-id="a11e5-152">결과</span><span class="sxs-lookup"><span data-stu-id="a11e5-152">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="a11e5-153">원격 액세스 VPN 솔루션이 가동 중입니다</span><span class="sxs-lookup"><span data-stu-id="a11e5-153">A remote access VPN solution is in place</span></span> | <span data-ttu-id="a11e5-154">분할 터널링 및 Microsoft 365 끝점의 범주 최적화에 대한 원격 액세스 VPN 클라이언트를 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-154">You have configured your remote access VPN client for split tunneling and for the Optimize category of Microsoft 365 endpoints.</span></span> |
| <span data-ttu-id="a11e5-155">원격 액세스 VPN 솔루션을 사용하지 않으며 사용자는 온-프레미스 웹 기반 앱으로의 원격 액세스만 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-155">No remote access VPN solution and you need remote access only to on-premises web-based apps</span></span> | <span data-ttu-id="a11e5-156">Azure 응용 프로그램 프록시를 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-156">You have configured Azure Application Proxy.</span></span> |
| <span data-ttu-id="a11e5-157">원격 액세스 VPN 솔루션을 사용하지 않으며 온-프레미스 앱으로의 액세스 권한이 필요하며, 앱 중 일부는 웹 기반이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-157">No remote access VPN solution and you need access to on-premises apps, some of which are not web-based</span></span> | <span data-ttu-id="a11e5-158">Azure P2S VPN을 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-158">You have configured Azure P2S VPN.</span></span> |
| <span data-ttu-id="a11e5-159">원격 작업자는 집에서 개인 장치를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-159">Remote workers are using their personal devices from home</span></span> | <span data-ttu-id="a11e5-160">Windows Virtual Desktop을 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-160">You have configured Windows Virtual Desktop.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="a11e5-161">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a11e5-161">Next step</span></span>

<span data-ttu-id="a11e5-162">[3단계](empower-people-to-work-remotely-manage-endpoints.md)를 계속 진행하여 장치, PC 및 기타 끝점을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="a11e5-162">Continue with [Step 3](empower-people-to-work-remotely-manage-endpoints.md) to manage your devices, PCs, and other endpoints.</span></span>
