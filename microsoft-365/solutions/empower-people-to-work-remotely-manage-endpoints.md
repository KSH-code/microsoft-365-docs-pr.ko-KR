---
title: 4단계. 장치, PC 및 기타 끝점에 대한 끝점 관리 기능 배포
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/03/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Microsoft Endpoint Manager를 사용하여 장치, PC 및 기타 끝점을 관리합니다.
ms.openlocfilehash: 5c6e433918709a55f03d786891ec0fd7ac62a26b
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377238"
---
# <a name="step-4-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a><span data-ttu-id="7a6ec-104">4단계.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-104">Step 4.</span></span> <span data-ttu-id="7a6ec-105">장치, PC 및 기타 끝점에 대한 끝점 관리 기능 배포</span><span class="sxs-lookup"><span data-stu-id="7a6ec-105">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>

<span data-ttu-id="7a6ec-106">원격 작업자의 경우 점점 늘어나는 개인 장치를 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-106">With remote workers, you need to support a growing number of personal devices.</span></span> <span data-ttu-id="7a6ec-107">끝점 관리 기능은 장치에서 리소스에 대한 액세스 권한을 부여받기 전에 특정 기준을 준수해야 하는 정책 기반의 보안 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-107">Endpoint management is a policy-based approach to security that requires devices to comply with specific criteria before they are granted access to resources.</span></span> <span data-ttu-id="7a6ec-108">Microsoft Endpoint Manager는 클라우드 및 온-프레미스에서 데이터를 안전하게 유지하기 위한 최신 관리 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-108">Microsoft Endpoint Manager delivers modern management capabilities to keep your data secure in the cloud and on-premises.</span></span> 

<span data-ttu-id="7a6ec-109">Endpoint Manager는 이미 알고 있고 사용하고 있는 다음 서비스를 결합하여 모바일 장치, 데스크톱 컴퓨터, 가상 머신, 내장 장치, 서버를 관리하는 서비스와 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-109">Endpoint Manager provides services and tools for managing mobile devices, desktop computers, virtual machines, embedded devices, and servers by combining the following services you may already know and be using.</span></span>

![끝점 관리용 구성 요소](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a><span data-ttu-id="7a6ec-111">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="7a6ec-111">Microsoft Intune</span></span>

<span data-ttu-id="7a6ec-112">Microsoft Intune은 Microsoft 365에 포함된 MDM(모바일 장치 관리) 및 MAM(모바일 응용 프로그램 관리)에 중점을 둔 클라우드 기반 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-112">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM) that is included with Microsoft 365.</span></span> 

- <span data-ttu-id="7a6ec-113">**MDM:** 조직 소유의 장치의 경우 설정, 기능 및 보안을 포함하여 모든 권한을 발휘할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-113">**MDM:** For organization-owned devices, you can exercise full control including settings, features, and security.</span></span> <span data-ttu-id="7a6ec-114">장치는에서 규칙과 설정을 사용하여 Intune 정책을 받는 Intune에서 "등록”되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-114">Devices are "enrolled" in Intune where they receive Intune policies with rules and settings.</span></span> <span data-ttu-id="7a6ec-115">예를 들어, 암호와 PIN 요구 사항을 설정하고, VPN 연결을 만들고, 위협 방지를 설정하는 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-115">For example, you can set password and PIN requirements, create a VPN connection, set up threat protection, and more.</span></span>

- <span data-ttu-id="7a6ec-116">**MAM:** 원격 작업자는 BYOD(Bring-Your-Own Device)라고도 하는 개인 기기를 완전히 제어하는 것을 원하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-116">**MAM:** Remote workers might not want you to have full control on their personal devices, also known as bring-your-own device (BYOD) devices.</span></span> <span data-ttu-id="7a6ec-117">원격 작업자 옵션을 제공하고 계속해서 조직을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-117">You can give your remote workers options and still protect your organization.</span></span> <span data-ttu-id="7a6ec-118">예를 들어 원격 작업자가 조직 리소스에 대한 전체 액세스 권한을 원할 경우 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-118">For example, remote workers can enroll their devices if they want full access to your organization resources.</span></span> <span data-ttu-id="7a6ec-119">또는 이러한 사용자가 전자 메일 또는 Microsoft Teams에만 액세스하려면 MFA(다단계 인증)가 필요한 앱 보호 정책을 사용하여 이러한 앱을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-119">Or, if these users only want access to email or Microsoft Teams, then use app protection policies that require multi-factor authentication (MFA) to use these apps.</span></span>

<span data-ttu-id="7a6ec-120">자세한 내용은 이 [Microsoft Intune의 개요](https://docs.microsoft.com/intune/fundamentals/what-is-intune)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-120">For more information, see this [overview of Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).</span></span>

## <a name="configuration-manager"></a><span data-ttu-id="7a6ec-121">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7a6ec-121">Configuration Manager</span></span>

<span data-ttu-id="7a6ec-122">Configuration Manager는 온-프레미스 관리 솔루션으로서 네트워크에 있거나 또는 인터넷 기반의 데스크톱, 서버 및 노트북을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-122">Configuration Manager is an on-premises management solution to manage desktops, servers, and laptops that are on your network or internet-based.</span></span> <span data-ttu-id="7a6ec-123">Configuration Manager를 사용하여 앱, 소프트웨어 업데이트 및 운영 체제를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-123">Use Configuration Manager to deploy apps, software updates, and operating systems.</span></span> <span data-ttu-id="7a6ec-124">또한 규정 준수를 모니터링하고, 쿼리를 실행하고, 실시간으로 클라이언트에 대한 작업을 수행하는 등의 더 많은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-124">You can also monitor compliance, query and act on clients in real time, and much more.</span></span> <span data-ttu-id="7a6ec-125">클라우드를 사용하도록 설정하여 Intune, Azure AD, Microsoft Defender ATP 및 기타 클라우드 서비스와 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-125">You can cloud-enable it to integrate with Intune, Azure AD, Microsoft Defender ATP, and other cloud services.</span></span> 

<span data-ttu-id="7a6ec-126">자세한 내용은 이 [Configuration Manager 개요](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-126">For more information, see this [overview of Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).</span></span>

## <a name="co-management"></a><span data-ttu-id="7a6ec-127">공동 관리</span><span class="sxs-lookup"><span data-stu-id="7a6ec-127">Co-management</span></span>

<span data-ttu-id="7a6ec-128">공동 관리는 Intune과 기타 Microsoft 365 클라우드 서비스를 사용하여 기존 온-프레미스 Configuration Manager 투자와 클라우드를 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-128">Co-management combines your existing on-premises Configuration Manager investment with the cloud using Intune and other Microsoft 365 cloud services.</span></span> <span data-ttu-id="7a6ec-129">사용자는 Configuration Manager 또는 Intune을 다양한 워크로드에 대한 관리 기관으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-129">You choose whether Configuration Manager or Intune is the management authority for different workload.</span></span> 

<span data-ttu-id="7a6ec-130">공동 관리는 조건부 액세스 및 장치 규정 준수 적용을 비롯한 Intune 기반 클라우드 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-130">Co-management uses Intune-based cloud features, including Conditional Access and enforcing device compliance.</span></span> <span data-ttu-id="7a6ec-131">Intune을 이용하여 클라우드에서 다른 작업을 실행하는 동안 몇 가지 작업을 온-프레미스에 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-131">You keep some tasks on-premises, while running other tasks in the cloud.</span></span>

<span data-ttu-id="7a6ec-132">자세한 내용은 이 [공동 관리 개요](https://docs.microsoft.com/mem/configmgr/comanage/overview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-132">For more information, see this [overview of co-management](https://docs.microsoft.com/mem/configmgr/comanage/overview).</span></span>

## <a name="desktop-analytics"></a><span data-ttu-id="7a6ec-133">Desktop Analytics</span><span class="sxs-lookup"><span data-stu-id="7a6ec-133">Desktop Analytics</span></span>

<span data-ttu-id="7a6ec-134">Desktop Analytics는 Configuration Manager와 통합하고 사용자에게 Windows 클라이언트에 대한 의사 결정을 내리는 데 도움이 되는 정보와 인텔리전스를 제공하는 클라우드 기반 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-134">Desktop Analytics is a cloud-based service that integrates with Configuration Manager and provides you with insight and intelligence so you can make informed decisions about your Windows clients.</span></span> <span data-ttu-id="7a6ec-135">Microsoft 클라우드 서비스에 연결된 수백만 개의 장치에서 집계한 데이터를 조직의 데이터와 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-135">It combines data from your organization with data aggregated from millions of devices connected to Microsoft cloud services.</span></span> 

<span data-ttu-id="7a6ec-136">데스크톱 분석을 통해 다음의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-136">With Desktop Analytics, you can:</span></span>

- <span data-ttu-id="7a6ec-137">조직에서 실행 중인 앱의 인벤토리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-137">Create an inventory of apps running in your organization.</span></span>
- <span data-ttu-id="7a6ec-138">최신 Windows 10 기능 업데이트와 앱 호환성을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-138">Assess app compatibility with the latest Windows 10 feature updates.</span></span>
- <span data-ttu-id="7a6ec-139">호환성 문제를 확인하고 클라우드 사용 데이터를 기반으로 하는 완화 제안을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-139">Identify compatibility issues, and receive mitigation suggestions based on cloud-enabled data insights.</span></span>
- <span data-ttu-id="7a6ec-140">최소 장치 집합에서 전체 응용 프로그램 및 드라이버 공간을 나타내는 파일럿 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-140">Create pilot groups that represent the entire application and driver estate across a minimal set of devices.</span></span>
- <span data-ttu-id="7a6ec-141">파일럿 및 프로덕션 관리 장치에 Windows 10을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-141">Deploy Windows 10 to pilot and production-managed devices.</span></span>

<span data-ttu-id="7a6ec-142">자세한 내용은 이 [Desktop Analytics 개요](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-142">For more information, see this [overview of Desktop Analytics](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)</span></span>

## <a name="windows-autopilot"></a><span data-ttu-id="7a6ec-143">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="7a6ec-143">Windows Autopilot</span></span>

<span data-ttu-id="7a6ec-144">Windows Autopilot은 제로터치의 셀프 서비스 Windows 배포 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-144">Windows Autopilot is a zero-touch, self-service Windows deployment platform.</span></span> <span data-ttu-id="7a6ec-145">여기에는 새 장치를 설정하고 사전 구성하는 데 사용되는 기술의 컬렉션이 포함되어 있으며, 이를 통해 장치의 생산적인 활용을 위한 준비를 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-145">It includes a collection of technologies used to set up and pre-configure new devices, getting them ready for productive use.</span></span> <span data-ttu-id="7a6ec-146">또한 Windows Autopilot를 사용하여 장치를 재설정 하고 용도를 변경하며 복구를 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-146">You can also use Windows Autopilot to reset, repurpose and recover devices.</span></span> 

<span data-ttu-id="7a6ec-147">Windows 자동 실행 기능을 사용하면 IT 부서가 쉽고 간단한 프로세스를 통해 관리할 인프라가 거의 없거나 전혀 없는 장치를 미리 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-147">Windows Autopilot enables an IT department to pre-configure devices with little to no infrastructure to manage, with a process that's easy and simple.</span></span> 

- <span data-ttu-id="7a6ec-148">사용자 관점에서 보면 몇 가지 간단한 작업만 수행하면 장치를 사용할 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-148">From the user's perspective, it only takes a few simple operations to make their device ready to use.</span></span> 
- <span data-ttu-id="7a6ec-149">IT 전문가의 관점에서 보면 최종 사용자가 해야하는 작업은 네트워크에 연결하고 해당 자격 증명을 확인하는 것뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-149">From the IT pro's perspective, the only interaction required from the end user is to connect to a network and to verify their credentials.</span></span>

<span data-ttu-id="7a6ec-150">자세한 내용은 이 [Windows Autopilot의 개요](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-150">For more information, see this [overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).</span></span>

## <a name="admin-technical-resources-for-endpoint-management"></a><span data-ttu-id="7a6ec-151">끝점 관리를 위한 관리자 기술 리소스</span><span class="sxs-lookup"><span data-stu-id="7a6ec-151">Admin technical resources for endpoint management</span></span>

- [<span data-ttu-id="7a6ec-152">원격 작업자를 위한 Windows 10 장치 관리에 대한 동영상 파트 3</span><span class="sxs-lookup"><span data-stu-id="7a6ec-152">The Part 3 video on managing Windows 10 devices for remote workers</span></span>](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security)
- [<span data-ttu-id="7a6ec-153">원격 작업자를 위한 사용자 데스크톱 및 브라우저 관리에 대한 동영상 파트 5</span><span class="sxs-lookup"><span data-stu-id="7a6ec-153">The Part 5 video on managing user desktops and browsers for remote workers</span></span>](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security)
- [<span data-ttu-id="7a6ec-154">Microsoft 365에 대한 이동성 인프라 배포</span><span class="sxs-lookup"><span data-stu-id="7a6ec-154">Deploy a mobility infrastructure for Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure)
- [<span data-ttu-id="7a6ec-155">모바일 장치 관리에 다양한 유형의 장치를 등록하는 방법</span><span class="sxs-lookup"><span data-stu-id="7a6ec-155">How to enroll different types of devices for mobile device management</span></span>](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [<span data-ttu-id="7a6ec-156">Microsoft Intune에 대해 최종 사용자를 교육하는 방법</span><span class="sxs-lookup"><span data-stu-id="7a6ec-156">How to educate your end users about Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-3"></a><span data-ttu-id="7a6ec-157">3단계의 결과</span><span class="sxs-lookup"><span data-stu-id="7a6ec-157">Results of Step 3</span></span>

<span data-ttu-id="7a6ec-158">사용자는 끝점 관리자 기능 제품군을 사용하여 모바일 장치, 데스크톱 컴퓨터, 가상 컴퓨터, 내장 장치 그리고 서버를 관리하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-158">You are using the suite of Endpoint Manager features and capabilities to manage mobile devices, desktop computers, virtual machines, embedded devices, and servers.</span></span>

## <a name="next-step"></a><span data-ttu-id="7a6ec-159">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7a6ec-159">Next step</span></span>

<span data-ttu-id="7a6ec-160">[5단계](empower-people-to-work-remotely-teams-productivity-apps.md)를 계속 진행하면 원격 작업자가 Microsoft 팀과 같은 Microsoft 365 생산성 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6ec-160">Continue with [Step 5](empower-people-to-work-remotely-teams-productivity-apps.md) to get your remote workers using Microsoft 365 productivity apps such as Microsoft Teams.</span></span>
