---
title: '2단계: 디렉터리 및 네트워크 준비'
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 환경에서 디렉터리 및 네트워크 준비 상태를 평가하는 방법을 알아봅니다.
ms.openlocfilehash: e690e99110e647ffc06c9ff7d40b789d8670e571
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869738"
---
# <a name="step-2-directory-and-network-readiness"></a><span data-ttu-id="4d2a2-103">2단계: 디렉터리 및 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="4d2a2-103">Step 2: Directory and Network Readiness</span></span>

<span data-ttu-id="4d2a2-p101">디렉터리와 네트워크가 구성되고, Windows 10 및 Office 365 ProPlus로의 전원을 지원할 준비가 되었는지 확인합니다. 이를 위해서는 사용자가 Azure Active Directory 서비스를 사용할 수 있게 설정되고, 네트워크에는 일반 트래픽과 방대해질 수 있는 데이터의 이동(예: PC가 업그레이드되거나 사용자 파일, 설정 및 응용 프로그램이 복원되는 경우)을 처리할 수 있는 용량이 준비되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p101">Ensure your directory and the network are configured and ready to support to your shift to Windows 10 and Office 365 ProPlus. This will require Azure Active Directory Services to be in place for users, and your network must have the capacity to handle both its regular traffic and the movement of potentially vast amounts of data as PCs are upgraded, and users’ files, settings and applications are restored.</span></span>

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-5.png" alt="Step 2" height="144" width="144" /></td>
<td><p><span data-ttu-id="4d2a2-106"><strong>2단계: 디렉터리 및 네트워크 준비</strong></span><span class="sxs-lookup"><span data-stu-id="4d2a2-106"><strong>Step 2: Directory and Network Readiness</strong></span></span></p>
<p><span data-ttu-id="4d2a2-p102">Office 365 ProPlus의 클라우드 연결 서비스와 새로운 배포 옵션(예: Windows Autopilot)에는 Azure Active Directory가 필요합니다. Windows 이미지, 앱, 드라이버 및 관련 파일을 PC로 이동할 때 계획해야 하는 중요한 영역이 바로 네트워크와 연결입니다. 새로운 도구와 배포 옵션으로 네트워크 트래픽을 줄이고 능률화하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p102">Cloud connected services in Office 365 ProPlus and new deployment options like Windows Autopilot require Azure Active Directory. Your network and connectivity are also important areas to plan when moving Windows images, apps, drivers and related files to your PCs. Learn how new tools and deployment options reduce and streamline network traffic.</span></span></p></td>
<td><a href="https://aka.ms/ddev2" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-15.png" alt="Step 2" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="4d2a2-p103">디렉터리 및 네트워크 준비는 Azure Active Directory를 중심으로 네트워크를 최적화하기 위한 권장 배포 프로세스 사이클의 두 번째 단계입니다. 전체 데스크톱 배포 프로세스를 보려면 [최신 데스크톱 배포 센터](https://aka.ms/HowToShift)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p103">Directory and Network Readiness is the second step in our recommended deployment process wheel focusing on Azure Active Directory and optizming the network. To see the full desktop deployment process, visit the [Modern Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="4d2a2-p104">디렉터리 및 네트워크 준비는 원활한 OS 및 데스크톱 배포를 위한 기본 과정입니다. 자동화된 배포와 마찬가지로, 파일 공유에 연결할 수 있어야 하고, 네트워크는 대용량 파일을 한 번에 수백 대 또는 수천 대의 PC로 전송하도록 지원할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p104">Directory and Network readiness is fundamental to ensuring a smooth OS and desktop deployment. As with any automated deployment, it is important to ensure your file shares can be reached, and your network will need to be able to support the transfer of very large files, possibly to hundreds or even thousands of PCs at a time.</span></span>

<span data-ttu-id="4d2a2-p105">Windows 10 및 Office 365 ProPlus로의 전환을 수행할 경우 클라우드 기반 ID를 Azure Active Directory를 통해 설정해야 합니다. 이러한 작업은 Office 365 ProPlus를 활성화하는 데 중요할 뿐만 아니라, Windows Autopilot과 같은 최신 프로비저닝 솔루션을 활용하는 데도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p105">With your shift to Windows 10 and Office 365 ProPlus you also now need to make sure that cloud-based identity is set up with Azure Active Directory. This is key not only to activating Office 365 ProPlus, it also allows you to take advantage of modern provisioning solutions like Windows Autopilot.</span></span>

<span data-ttu-id="4d2a2-116">이 문서에서는 Windows 10 및 Office 365 ProPlus에 배포하기 위해 디렉터리 서비스 및 사용자 및 장치 권한을 준비하기 위한 도구 및 옵션을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-116">In this article we’ll explore the tools and options to prepare your directory services, and user and device permissions, ready for deployment to Windows 10 and Office 365 ProPlus.</span></span>

## <a name="adding-azure-active-directory"></a><span data-ttu-id="4d2a2-117">Azure Active Directory 추가</span><span class="sxs-lookup"><span data-stu-id="4d2a2-117">Adding Azure Active Directory</span></span>

<span data-ttu-id="4d2a2-p106">조직에서 Office 365, Exchange Online, Microsoft Intune 또는 기타 Microsoft Online 서비스를 이미 사용하고 있는 경우 Azure Active Directory도 이미 사용하고 있다는 이점이 있습니다. 그렇다면 데스크톱 배포의 대상으로 지정하는 사용자가 Azure Active Directory에 포함되어 있으며 해당 라이선스가 이미 할당되어 있는지만 확인하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p106">If your organization already uses Office 365, Exchange Online, Microsoft Intune or other Microsoft Online services, the good news is, you are already using Azure Active Directory. If you are, you just need to ensure that the users you are targeting for desktop deployment are in your Azure Active Directory, and that licenses have been assigned.</span></span>

<span data-ttu-id="4d2a2-p107">현재 Azure Active Directory를 사용하고 있지 않으면 설정하는 데 도움이 되는 [다양한 리소스](https://docs.microsoft.com/ko-KR/azure/active-directory/)가 있습니다. Office 365 라이선스의 일부로 제공되는 Microsoft FastTrack을 통해 개인별 지원을 받을 수 있습니다. Microsoft Fastrack에 대한 자세한 내용은 [여기](https://fasttrack.microsoft.com)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p107">If you are not currently using Azure Active Directory, there are [lots of resources](https://docs.microsoft.com/ko-KR/azure/active-directory/) to help you set it up. You may well qualify for personalized assistance via Microsoft FastTrack, as part of your Office 365 license. You can check out more about Microsoft Fastrack [here](https://fasttrack.microsoft.com).</span></span>

<span data-ttu-id="4d2a2-123">Azure Active Directory가 준비되면 사용자는 Office 365 ProPlus 앱에 로그인한 후 정품 인증을 수행할 수 있으며, 앱 및 정책의 자동 배포에 Microsoft Intune 또는 Windows Autopilot을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-123">Once you have Azure Active Directory in place, your users can sign in to and activate their Office 365 ProPlus apps, and you can use Microsoft Intune or Windows Autopilot deployment for automated deployment of apps and policy.</span></span>

## <a name="network-readiness"></a><span data-ttu-id="4d2a2-124">네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="4d2a2-124">Network Readiness</span></span>

<span data-ttu-id="4d2a2-p108">배포를 계획할 때 대역폭 요구 사항을 고려해야 합니다. 네트워크에 영향을 미치는 배포의 세 가지 주요 구성 요소는 PC 이미징, 소프트웨어 업데이트 및 사용자 개인 설정입니다. 이러한 요인으로 인해 초기 마이그레이션 시 PC당 20GB가 초과되고, 최신 상태 유지를 위해 PC당 매월 1GB 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p108">You must consider bandwidth requirements when planning your deployments. There are three main components in a deployment that will have an impact on your network – PC imaging; software updates; user personalization. Between them, this can mean in excess of 20 GB per PC for the initial migration, and often 1 GB or more per month per PC to stay up-to-date.</span></span>

<span data-ttu-id="4d2a2-128">먼저 이러한 세 가지 주요 구성 요소 각각에 대한 요구 사항을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-128">Let’s start by exploring the requirements of each of these three main components:</span></span>

### <a name="pc-imaging"></a><span data-ttu-id="4d2a2-129">PC 이미징</span><span class="sxs-lookup"><span data-stu-id="4d2a2-129">PC Imaging</span></span>

<span data-ttu-id="4d2a2-p109">아래의 차트는 이미지 크기를 고려해서 계획을 세우도록 도와줍니다. 사용자 지정이 없는 Windows 이미지의 경우, 일반적으로 PC당 3GB를 계획해야 하지만, 앱을 포함하는 사용자 지정된 이미지의 경우에는 6GB 이상을 허용해야 할 수 있습니다. 또한 드라이버 패키지도 고려해야 할 수 있습니다. 이러한 패키지는 PC당 수백 메가바이트를 차지할 수 있으며 1GB에 달하는 경우도 종종 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p109">The chart below will help you to plan based on image size. For Windows Images with no customization you should plan typically for 3GB per PC, while for customized images with apps you may need to allow 6GB, or more. You may also need to consider Driver packages; these can be a few hundred megabytes per PC, sometimes up to 1GB.</span></span>

### <a name="software-updates"></a><span data-ttu-id="4d2a2-133">소프트웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="4d2a2-133">Software Updates</span></span>

<span data-ttu-id="4d2a2-p110">소프트웨어 업데이트에 대한 네트워크 대역폭을 계획해야 합니다. Windows 10 및 Office 365 ProPlus는 새로운 서비스 모델을 사용하여 매월 및 연 2회의 업데이트를 제공합니다. 이 모델을 처음 접하는 경우에는 [여기](https://docs.microsoft.com/ko-KR/windows/deployment/update/waas-overview)에서 작동 방식에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p110">You’ll need to plan network bandwidth for software updates. Windows 10 and Office 365 ProPlus use a new servicing model, delivering monthly and semi-annual updates. If you are new to this model, you can learn more about how this works [here](https://docs.microsoft.com/ko-KR/windows/deployment/update/waas-overview).</span></span>

<span data-ttu-id="4d2a2-p111">새로운 서비스 모델에는 1년에 2번 Windows용 기능 업데이트, Office 반기 채널 업데이트 및 월별 품질 업데이트가 포함되어 있습니다. 기능 업데이트는 크기가 일반적으로 2-4GB이고, Office 반기 채널 업데이트는 업데이트당 300-400MB입니다. 그다음에는 월별 품질 업데이트가 있습니다. 이러한 업데이트 크기는 수백 메가바이트에서 1기가바이트 이상까지 다양합니다. 이러한 다양한 크기는 월별 업데이트가 누적되기 때문이며, 각 Windows 10 버전의 서비스 수명 주기 동안 크기가 커지게 됩니다. 따라서 업데이트를 구현하기 위해 네트워크를 통과해야 하는 데이터 양을 줄이는 데 도움이 되는 도구들이 있습니다. 아래에 이러한 도구에 대한 자세한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p111">The new servicing model includes Feature Updates for Windows twice a year, Office Semi-Annual Channel Updates, and monthly Quality Updates. Feature Updates are typically 2 – 4GB in size, and Office Semi-Annual Channel updates are 300 – 400 MB per update. Then there are the monthly Quality Updates. These may range from a few hundred megabytes to over a gigabyte. This is because monthly updates are cumulative, so these increase in size over the servicing lifetime for each Windows 10 version. That said, there are tools that can help reduce the amount of data that must pass over the network to implement updates. We will cover this in more detail below.</span></span>

### <a name="user-personalization"></a><span data-ttu-id="4d2a2-144">사용자 개인 설정</span><span class="sxs-lookup"><span data-stu-id="4d2a2-144">User Personalization</span></span>

<span data-ttu-id="4d2a2-p112">고려해야 할 세 번째 구성 요소는 사용자 개인 설정입니다. 여기에 PC 새로 고침 또는 교체 과정의 일부로, 사용자 파일, 해당 설정 및 응용 프로그램의 복원을 고려하여 네트워크 대역폭을 계획해야 합니다. 이러한 항목이 전체적으로 PC당 20GB를 초과하는 경우가 자주 발생합니다. 일부 사용자의 경우 100GB가 넘기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p112">The third component to consider is user personalization. Here you need to plan network bandwidth to accommodate the restoring of user files, their settings, and their applications as part of the PC refresh or replacement process. Together, these items often exceed 20 GB per PC; for some users these may exceed 100 GB.</span></span>

## <a name="limiting-bandwidth"></a><span data-ttu-id="4d2a2-148">**대역폭 제한**</span><span class="sxs-lookup"><span data-stu-id="4d2a2-148">**Limiting Bandwidth**</span></span>

<span data-ttu-id="4d2a2-p113">배포 관련 트래픽이 네트워크에 미치는 영향을 제한하는 한 가지 방법은 클라이언트에서 BITS(Background Intelligent Transfer Service) 설정을 사용하여 제한하는 것입니다. BITS는 ABR(Adaptive Bit Rate)을 사용하여 배포 목적으로 사용할 수 있는 대역폭을 조정합니다. 이러한 BITS는 그룹 정책을 사용하여 클라이언트에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p113">One way to limit the impact of deployment-related traffic on the network is to throttle it using the BITS (Background Intelligent Transfer Service) setting on clients. BITS uses an Adaptive Bit Rate (ABR) to adjust bandwidth available for deployment purposes; it can be configured on clients using Group Policy.</span></span>

[<span data-ttu-id="4d2a2-151">BITS 정보</span><span class="sxs-lookup"><span data-stu-id="4d2a2-151">About BITS</span></span>](https://docs.microsoft.com/ko-KR/windows/desktop/bits/about-bits)

<span data-ttu-id="4d2a2-152">System Center Configuration Manager를 사용하는 경우 BITS 지원 배포 지점을 구성하거나 WDS를 통해 멀티캐스트를 사용하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-152">If you use System Center Configuration Manager, you can also configure BITS-enabled Distribution Points or enable multicast with WDS.</span></span>

<span data-ttu-id="4d2a2-p114">특정 트래픽을 제한할 경우 정상적인 네트워크 트래픽이 PC의 업데이트 및 응용 프로그램 다운로드에 따른 영향을 덜 받게 됩니다. 그렇지만 이러한 작업을 위해 특정 비율의 대역폭을 분할하면 생산성이 Windows 또는 Office 배포의 영향을 받지 않으며, 프로세스는 필요에 따라 계속 실행될 수 있습니다. 또한 배포가 실행되는 동안 사용자가 해당 PC를 잠그면 배포 관련 가동 중지 시간이 줄어들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p114">Throttling specific traffic means that normal network traffic is less impacted by PCs downloading updates and applications. But carving out a certain percentage of bandwidth for these tasks helps ensure productivity isn’t impacted by Windows or Office deployment and processes continue to run as needed, it can worsen deployment-related downtime, with users locked out of their PCs while a deployment runs.</span></span>

<span data-ttu-id="4d2a2-155">다행히 사용자가 대규모 데스크톱 배포가 네트워크에 미치는 영향을 보다 쉽게 관리하도록 하는 새로운 도구들이 있습니다. 사용 가능한 대역폭의 사용을 최적화하는 LEDBAT, 배포 트래픽을 네트워크 중심에서 주변 네트워크로 이동하기 위한 P2P(피어 투 피어) 옵션이 여기에 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-155">Fortunately, there are new tools to make it easier for you to manage the network impact of a large-scale desktop deployment, including LEDBAT to optimize use of available bandwidth, and peer-to-peer (P2P) options to move deployment traffic away from the center of the network and out to the perimeter</span></span>

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-3.png)

## <a name="scavenging-bandwidth"></a><span data-ttu-id="4d2a2-156">**대역폭 청소**</span><span class="sxs-lookup"><span data-stu-id="4d2a2-156">**Scavenging Bandwidth**</span></span>

<span data-ttu-id="4d2a2-157">Windows Server 2019 및 System Center Configuration Manager 버전 1806에서 지원되는 LEDBAT(Low Extra Delay Background Transport)는 Windows 클라이언트에 대한 네트워크 트래픽을 최적화되도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-157">Low Extra Delay Background Transport (LEDBAT), supported in Windows Server 2019 and System Center Configuration Manager version 1806, is designed to optimize network traffic to Windows clients.</span></span>

[<span data-ttu-id="4d2a2-158">Windows Server 2019의 상위 10가지 네트워킹 기능: \#9 LEDBAT – 대기 시간 최적화 백그라운드 전송</span><span class="sxs-lookup"><span data-stu-id="4d2a2-158">Top 10 Networking Features in Windows Server 2019: \#9 LEDBAT – Latency Optimized Background Transport</span></span>](https://blogs.technet.microsoft.com/networking/2018/07/25/ledbat/)

<span data-ttu-id="4d2a2-p115">기존 제한과 달리, LEDBAT는 사용 가능한 모든 네트워크 대역폭을 백그라운드 작업으로 사용할 수 있으며, 다른 트래픽이 요청할 때 대역폭을 즉시 양보할 수 있습니다. BITS와 달리 지연도 발생하지 않습니다. 모든 작업은 자동으로 진행되므로 수동 조정이나 일정 관리가 필요하지 않으며, 모든 설치가 서버 쪽에서 진행됩니다. 따라서 성능이 크게 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p115">Unlike traditional throttling, LEDBAT can use all available network bandwidth as a background task, instantly yielding bandwidth when other traffic requests it. Unlike BITS there is no delay; everything is automated – no manual tuning or scheduling required, and everything is setup server side. This affords potentially massive performance gains.</span></span>

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-4.png)

## <a name="peer-to-peer-options"></a><span data-ttu-id="4d2a2-162">**피어 투 피어 옵션**</span><span class="sxs-lookup"><span data-stu-id="4d2a2-162">**Peer-to-Peer options**</span></span>

<span data-ttu-id="4d2a2-p116">피어 투 피어 옵션은 Windows 10 마이그레이션의 PC 이미징, 소프트웨어 업데이트 및 사용자 개인 설정에서 점점 더 많이 사용되고 있습니다. 초기 Windows 10 배포 후의 빌드 간 업그레이드를 용이하게 진행하는 데도 도움이 됩니다. 여기서는 Windows 10 및 Office 관련 트래픽을 네트워크 중심에서 멀리 이동하여 클래식 제한 방법의 필요성을 줄이고, PC가 필요한 업데이트 파일을 배포 지점이나 인터넷에서 다운로드하지 않고, 로컬 네트워크의 피어에서 찾을 수 있도록 하는 데 도움이 되는 몇 가지 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p116">Peer-to-Peer options are increasingly being used in Windows 10 migrations, for PC imaging, software updates and user personalization. They are also valuable in facilitating build-to-build upgrades after your initial Windows 10 deployment. Here we will cover several examples to help move Windows 10 and Office-related traffic away from the center of the network, reducing the need for classic throttling approaches, and allowing PCs to find the update files they need on peers in their local network rather than downloading them from a distribution point or the internet.</span></span>

<span data-ttu-id="4d2a2-p117">**BranchCache**는 네트워크를 포화 상태로 만들지 않고 분산 환경에서 콘텐츠를 다운로드하는 데 도움이 됩니다. 이 기능은 두 가지 옵션으로 제공됩니다. 하나는 로컬 서버를 사용하여 콘텐츠를 캐시할 수 있는 호스트 캐시 모드이고, 다른 하나는 클라이언트가 이미 다운로드한 코텐츠를 서로 공유할 수 있도록 하는 분산 캐시 모드(System Center Configuration Manager에서 지원되는 모드)입니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p117">**BranchCache** can help you download content in distributed environments without saturating the network. It comes in two options: Hosted Cache Mode, which lets you use local servers to cache content, and Distributed Cache Mode (a mode supported in System Center Configuration Manager), which lets clients share already downloaded content with each other.</span></span>

<span data-ttu-id="4d2a2-p118">System Center Configuration Manager에서 지원되는 **피어 캐시** 클라이언트도 피어 캐시를 사용할 수 있습니다. 이 기능은 네트워크에서 안정적으로 사용할 수 있는 PC가 콘텐츠 분산을 위해 원본을 호스트할 수 있도록 합니다. 모든 PC를 이렇게 사용하고 싶지는 않을 것입니다. 따라서 안정적인 네트워크 연결이 있는 PC만 호스트로 타기팅할 수 있습니다(예: 데스크톱, 미니 타워 또는 타워 PC). 피어 캐시는 설치 중에 WIndows PE 단계에서 실행되는 배포 작업에도 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p118">**Peer Cache** Clients supported by System Center Configure can also make use of Peer Cache. This allows PCs that are reliably available on the network to host source for content distribution. You won’t want to enable this all of your PCs – only target with reliable network connections as hosts (e.g. desktop, mini-tower, or tower PCs). Peer Cache can even work for deployment tasks running in Windows PE phases during setup.</span></span>

<span data-ttu-id="4d2a2-172">참고: BranchCache 및 피어 캐시는 보조 기능이며 동일한 환경에서 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-172">Note: BranchCache and Peer Cache are complementary and can work together in the same environment.</span></span>

[<span data-ttu-id="4d2a2-173">BranchCache 및 피어 캐시</span><span class="sxs-lookup"><span data-stu-id="4d2a2-173">BranchCache vs. Peer Cache</span></span>](https://blogs.technet.microsoft.com/swisspfe/2018/01/25/branch-cache-vs-peer-cache/)

<span data-ttu-id="4d2a2-p119">**배달 최적화** 배달 최적화는 다른 피어 투 피어 캐싱 기술로, Windows 배포를 위한 네트워크 기반 컨트롤을 제공합니다. 기본 제공 UWP 앱을 업데이트하기 위한 Windows 10 배달 최적화는 Microsoft Store에서 응용 프로그램을 설치하며, 소프트웨어 업데이트의 경우에는 빠른 업데이트를 사용합니다. Windows 10의 초기 버전부터 사용 가능했지만 최근에 들어서야 System Center Configuration Manager에 통합되었습니다. Windows 10 버전 1803부터, 새 구성 옵션을 사용하면 백그라운드 업데이트 및 포그라운드 작업(예: 스토어에서 앱 설치)에 대한 대역폭 제한을 따로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p119">**Delivery Optimization** Delivery Optimization is another peer-to-peer caching technology, providing network-based controls for Windows deployments. Windows 10 Delivery Optimization to update built-in UWP apps, also to install applications from the Microsoft Store, and for software updates using Express Updates. It has been available since early versions of Windows 10, though it has only recently integrated with System Center Configuration Manager. Since Windows 10 version 1803 new configuration options mean you can now independently set bandwidth limits for background updates and foreground jobs such as an app install from the Store.</span></span>

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-5.png)

<span data-ttu-id="4d2a2-178">**Office 365 ProPlus에 대한 추가 고려 사항**</span><span class="sxs-lookup"><span data-stu-id="4d2a2-178">**Additional Considerations for Office 365 ProPlus**</span></span>

<span data-ttu-id="4d2a2-179">다음은 Office 365 ProPlus 배포로 인한 네트워크 부하를 줄여주는 3가지 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-179">Here are three items that will reduce your network load due to Office 365 ProPlus deployments.</span></span>

<span data-ttu-id="4d2a2-p120">**이진 델타 압축** Office 365 ProPlus는 Office 365 ProPlus의 최신 릴리스에서 다음 릴리스로 업데이트할 때 소프트웨어 업데이트가 사용하는 대역폭을 줄이기 위해 이진 델타 압축을 사용합니다. 이전 릴리스에서 이진 수준 변경 내용만 가져오므로 누적 업데이트의 월별 증가에 따른 영향이 최소화됩니다. 이로 인해 매월 PC 1대당 수백 메가바이트의 데이터가 감소될 수 있습니다. 그렇지만 이러한 기능을 사용하기 위해서는 릴리스를 건너뛰면 안 됩니다. 릴리스를 건너뛰게 되면 전체 누적 업데이트를 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p120">**Binary Delta Compression** Office 365 ProPlus uses Binary Delta Compression to reduce bandwidth consumed by software updates when updating from the most recent release of Office 365 ProPlus to the next release. By only pulling the binary level changes from the previous release, the impact from month-over-month growth of cumulative updates is minimized. This has the potential of saving several hundred megabytes of data, per PC, each month. In order to use this capability though, you cannot skip releases. If you do, then the full cumulative update must be downloaded.</span></span>

[<span data-ttu-id="4d2a2-185">Office 365용 업데이트 다운로드</span><span class="sxs-lookup"><span data-stu-id="4d2a2-185">Downloading Updates for Office 365</span></span>](https://docs.microsoft.com/ko-KR/deployoffice/overview-of-the-update-process-for-office-365-proplus#download-the-updates-for-office-365-proplus)

<span data-ttu-id="4d2a2-p121">**Outlook 데이터 파일** Outlook은 종종 오프라인 사용을 위해 사용자의 전체 사서함을 로컬로 캐시하도록 구성됩니다. 현재 위치 업그레이드를 제외한 모든 Windows 배포에서, 업그레이드 후에 사용자의 Outlook 데이터 파일이 자체적으로 재작성되어야 합니다. 이러한 작업은 자동화된 프로세스이지만, Outlook 사서함 제한이 일반적으로 최대 100GB로 설정되므로 모든 사용자를 위해 전체 사서함을 로컬로 다시 캐시하면 방대한 데이터 전송이 발생합니다. 네트워크 부하를 줄이기 위해서는 그룹 정책을 사용하여 "오프라인으로 유지할 메일” 설정을 줄이는 것을 고려할 수 있습니다. Office 365 ProPlus의 Outlook 또는 Outlook 2016에서는 기본값이 12개월로 설정됩니다. 오프라인 캐시가 1~6개월 동안 지속되도록 설정하는 것이 좋습니다. 이 설정을 변경해도 온라인 사서함 크기에는 영향을 미치지 않으며 온라인 상태에서 여전히 Outlook을 통해 전체 사서함을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p121">**Outlook Data Files** Outlook is often configured to cache users’ entire mailbox locally, for use offline. In any Windows deployment, except an in-place upgrade, that requires the users’ Outlook Data Files to rebuild themselves after the upgrade. This is an automated process, but with Outlook mailbox limits typically set to up to 100GB, re-caching the entire mailbox locally for all users means a lot of data transfer. To reduce the network load you may want to consider using Group Policy to reduce the “Mail to keep offline” setting. In Outlook in Office 365 ProPlus or Outlook 2016 the default value is set to 12 months. Consider setting the offline cache to last between 1 to 6 months. Changing this setting does not affect the size of the online mailbox, and the entire mailbox can still be searched via Outlook when online.</span></span>

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-6.png)

<span data-ttu-id="4d2a2-p122">**및 알려진 폴더 이동** OneDrive는 클라우드의 PC 및 기타 장치에서 사용자 파일을 동기화하고 보호하는 유용한 방법입니다. 알려진 폴더 이동을 사용하면 사용자의 바탕 화면, 문서 및 그림 폴더에서 OneDrive로 파일 동기화가 적용되어, 새 장치 또는 이미지로 다시 설치한 PC에 로그인할 때 해당 파일을 사용할 수 있게 됩니다. 그렇지만 바탕 화면, 문서 및 그림 폴더에 유지되는 파일의 순수한 크기 및 개수 때문에, PC에서 Onedrive를 사용하도록 설정하고 적용하는 정책 롤아웃을 잘 계획하려고 할 것입니다. 한 가지 옵션은 그룹 정책 네트워크 컨트롤을 사용하여 OneDrive 동기화 서비스에서 사용되는 대역폭을 제한하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p122">**OneDrive Files on Demand and Known Folder Move** OneDrive is a great way to synchronize and protect user files from PCs and other devices in the cloud. With Known Folder Move, you can enforce file sync from a user’s Desktop, Documents and Pictures folders to OneDrive, making those files available when signing into a new device a or reimaged PC. Remember though, due to the sheer size and number of files kept in Desktop, Documents and Pictures locations, you’ll want to be planful with the rollout of policies enabling and enforcing OneDrive on your PCs. One option is to use Group Policy Network controls to throttle bandwidth used by the OneDrive sync service.</span></span>

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-7.png)

[<span data-ttu-id="4d2a2-197">알려진 폴더 이동 설정</span><span class="sxs-lookup"><span data-stu-id="4d2a2-197">Setup Known Folder Move</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/Migrate-Your-Files-to-OneDrive-Easily-with-Known-Folder-Move/ba-p/207076)

[<span data-ttu-id="4d2a2-198">OneDrive Files on Demand</span><span class="sxs-lookup"><span data-stu-id="4d2a2-198">OneDrive Files on Demand</span></span>](https://www.microsoft.com/ko-KR/microsoft-365/blog/2017/05/11/introducing-onedrive-files-on-demand-and-additional-features-making-it-easier-to-access-and-share-files/)

<span data-ttu-id="4d2a2-p123">OneDrive를 아직 롤아웃하지 않은 경우 Windows 7에서 Windows 10으로의 전환은 OneDrive를 사용할 수 있는 완벽한 기회가 되며, Office 365 ProPlus도 원활하게 통합됩니다. 앱 및 장치 준비를 진행하면서 이러한 롤아웃을 시작하는 것이 좋습니다. 이렇게 하면 네트워크를 통해 Windows 이미지를 이동하고 앱 배포를 시작하기 전에 먼저 파일이 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p123">If you haven’t already rolled out OneDrive, the shift from Windows 7 to Windows 10 is a perfect opportunity to enable OneDrive, and it integrates seamlessly Office 365 ProPlus. Consider starting this roll-out while working through your app and device readiness. This will give file sync a head start before you start moving Windows images and deploying apps over your network.</span></span>

## <a name="next-step"></a><span data-ttu-id="4d2a2-202">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4d2a2-202">Next Step</span></span> 

## <a name="step-3-office-and-lob-app-deliveryhttpsakamsmdd3"></a>[<span data-ttu-id="4d2a2-203">3단계: Office 및 LOB 앱 배달</span><span class="sxs-lookup"><span data-stu-id="4d2a2-203">Step 3: Office and LOB App Delivery</span></span>](https://aka.ms/mdd3)

## <a name="previous-step"></a><span data-ttu-id="4d2a2-204">이전 단계:</span><span class="sxs-lookup"><span data-stu-id="4d2a2-204">Previous Step:</span></span>

## <a name="step-1-device-and-app-readinesshttpsakamsmdd1"></a>[<span data-ttu-id="4d2a2-205">1단계: 장치 및 앱 준비</span><span class="sxs-lookup"><span data-stu-id="4d2a2-205">Step 1: Device and App Readiness</span></span>](https://aka.ms/mdd1)

## <a name="feedback"></a><span data-ttu-id="4d2a2-206">사용자 의견</span><span class="sxs-lookup"><span data-stu-id="4d2a2-206">Feedback</span></span>

<span data-ttu-id="4d2a2-p124">Microsoft는 사용자의 의견을 환영합니다. 제공하려는 의견 유형을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p124">We'd love to hear your thoughts. Choose the type you'd like to provide:</span></span>

<span data-ttu-id="4d2a2-209">설명서에 대한 사용자 의견을 제공하기 위한 제품 피드백 로그인</span><span class="sxs-lookup"><span data-stu-id="4d2a2-209">Product feedback Sign in to give documentation feedback</span></span>

<span data-ttu-id="4d2a2-p125">새 피드백 시스템은 GitHub 문제를 기준으로 합니다. Microsoft 블로그 게시물에서 이러한 변경에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="4d2a2-p125">Our new feedback system is built on GitHub Issues. Read about this change in our blog post.</span></span>
