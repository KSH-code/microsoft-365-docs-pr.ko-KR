---
title: Microsoft 365를 사용하여 원격 작업을 위한 인프라 설정
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-overview
- M365initiative-coredeploy
ms.custom: seo-marvel-jun2020
keywords: 재택근무, 재택근무, 하이브리드, 원격근무, 하이브리드 근무, 원격직원, 하이브리드 연결, 원격접속, 재택근무, 재택근무, 재택근무, 원격근무, 원격근무, 원격근무, 유연한 근무 장소
description: 원격 직원이 온-프레미스 및 Microsoft 365 리소스에 안전하게 액세스할 수 있도록 인프라 계층으로 이동합니다.
ms.openlocfilehash: 1a8cf471cf92e1301c231f395ed0238bb35359cb
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246323"
---
# <a name="set-up-your-infrastructure-for-remote-work-with-microsoft-365"></a><span data-ttu-id="48198-104">Microsoft 365를 사용하여 원격 작업을 위한 인프라 설정</span><span class="sxs-lookup"><span data-stu-id="48198-104">Set up your infrastructure for remote work with Microsoft 365</span></span>

<span data-ttu-id="48198-105">원격 작업의 생산성 및 공동 작업을 보호하고 최적화하려면 원격 작업을 사용하도록 IT 및 클라우드 인프라를 구성하고 조직의 온-프레미스 및 클라우드 기반 정보, 도구 및 리소스에 대한 액세스를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48198-105">To secure and optimize your remote worker’s productivity and collaboration, you need to configure your IT and cloud infrastructure to enable remote work and to provide access to your organization's on-premises and cloud-based information, tools, and resources.</span></span> <span data-ttu-id="48198-106">이 솔루션에서는 작업자가 어디에 있든 최고의 업무를 할 수 있도록 하는 인프라의 주요 계층을 배포하는 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="48198-106">This solution steps through the deployment of key layers of infrastructure that empower your workers to do their best work, wherever they are.</span></span>

<span data-ttu-id="48198-107">직원이 원격으로 작업할 수 있도록 하는 것은 조직에 다음과 같은 이유로 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="48198-107">Allowing workers to work away from the office is important for many organizations to:</span></span>

- <span data-ttu-id="48198-108">사무실 공간에 저장</span><span class="sxs-lookup"><span data-stu-id="48198-108">Save on office space.</span></span>
- <span data-ttu-id="48198-109">이동할 의사가 없는 직원을 고용하고 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48198-109">Hire and retain workers who are unwilling to relocate.</span></span>
- <span data-ttu-id="48198-110">직원의 출퇴근를 줄여 업무 이외에 생산성을 높이고 스트레스 해소 활동을 위한 시간을 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48198-110">Reduce worker commuting, leaving them with more time to be productive and for stress-reducing activities outside of work.</span></span>

<span data-ttu-id="48198-111">Microsoft 365에는 직원이 원격으로 작업할 수 있도록 도와주는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48198-111">Microsoft 365 has the capabilities to empower your workers to work remotely.</span></span>

![Microsoft 365를 사용하여 원격 작업자의 역량 강화하기](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)

>[!Note]
><span data-ttu-id="48198-113">Microsoft 365를 처음 사용하는 경우, [다음 리소스](https://www.microsoft.com/microsoft-365)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="48198-113">If you are new to Microsoft 365, see [these resources](https://www.microsoft.com/microsoft-365).</span></span>
>

<span data-ttu-id="48198-114">이 비디오를 시청하고 배포 프로세스에 대한 개요를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="48198-114">Watch this video for an overview of the deployment process.</span></span>
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4F1af]

<span data-ttu-id="48198-115">작업 생산성을 높이기 위해 인트라 사이트 및 클라우드 기반 인프라를 관리하는 IT 전문가를 위해 이 솔루션은 다음과 같은 주요 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="48198-115">For IT professionals managing onsite and cloud-based infrastructure to enable worker productivity, this solution provides these key capabilities:</span></span>

- <span data-ttu-id="48198-116">연결</span><span class="sxs-lookup"><span data-stu-id="48198-116">Connected</span></span>

  <span data-ttu-id="48198-117">원격 작업자는 전 세계 어디서나 언제든지 다음 항목에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48198-117">From anywhere in the world and at any time, remote workers are able to access:</span></span> 

  - <span data-ttu-id="48198-118">Microsoft 365 구독의 클라우드 기반 서비스 및 데이터</span><span class="sxs-lookup"><span data-stu-id="48198-118">Cloud-based services and data in your Microsoft 365 subscription.</span></span> 

  - <span data-ttu-id="48198-119">온-프레미스 응용 프로그램 데이터 센터에서 제공하는 그러한 조직 리소스</span><span class="sxs-lookup"><span data-stu-id="48198-119">Organization resources, such those offered by on-premises application datacenters.</span></span>

- <span data-ttu-id="48198-120">보안</span><span class="sxs-lookup"><span data-stu-id="48198-120">Secure</span></span>

  <span data-ttu-id="48198-121">로그인이 다단계 인증(MFA)으로 보안되며 Microsoft 365 및 Windows 10의 기본 제공 보안 기능은 맬웨어, 악의적인 공격 및 데이터 손실로부터 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48198-121">Sign-ins are secured with multi-factor authentication (MFA) and built-in security features of Microsoft 365 and Windows 10 protect against malware, malicious attacks, and data loss.</span></span>

- <span data-ttu-id="48198-122">관리</span><span class="sxs-lookup"><span data-stu-id="48198-122">Managed</span></span>

  <span data-ttu-id="48198-123">보안 설정, 허용 앱을 사용해 원격 작업자의 장치를 클라우드에서 관리하고 시스템 상태 규정을 준수할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48198-123">Your remote worker's devices can be managed from the cloud with security settings, allowed apps, and to require compliance with system health.</span></span>

- <span data-ttu-id="48198-124">공동 작업 및 생산성</span><span class="sxs-lookup"><span data-stu-id="48198-124">Collaborative and productive</span></span>

  <span data-ttu-id="48198-125">원격 작업자는 다음과 같이 매우 협력적인 방식으로 온-프레미스 환경에서처럼 생산적으로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48198-125">Your remote workers can be as productive as on-premises in a highly collaborative way with:</span></span>

  - <span data-ttu-id="48198-126">Teams를 통한 온라인 팀 회의 및 채팅</span><span class="sxs-lookup"><span data-stu-id="48198-126">Online meetings and chat sessions with Teams.</span></span> 

  - <span data-ttu-id="48198-127">SharePoint 및 OneDrive를 통한 전역 접근성과 실시간 공동 작업이 가능한 클라우드 기반 파일 저장소를 위한 공유 작업 영역</span><span class="sxs-lookup"><span data-stu-id="48198-127">Shared workspaces for cloud-based file storage with global accessibility and real-time collaboration with SharePoint and OneDrive.</span></span>

  - <span data-ttu-id="48198-128">작업을 분할하고 완료하기 위한 공유 작업 및 워크플로</span><span class="sxs-lookup"><span data-stu-id="48198-128">Shared tasks and workflows to divide up the work and get things done.</span></span> 

<span data-ttu-id="48198-129">원활하게 로그인하려면 온-프레미스 Active Directory 도메인 서비스(AD DS) 사용자 계정을 Azure Active Directory(Azure AD)와 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48198-129">For a seamless sign-in experience, your on-premises Active Directory Domain Services (AD DS) user accounts should be synchronized with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="48198-130">Windows 10 장치를 보호하려면 Intune에서 장치를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48198-130">To protect your Windows 10 devices, they should be enrolled in Intune.</span></span> <span data-ttu-id="48198-131">다음은 인프라의 개괄적인 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="48198-131">Here is a high-level view of the infrastructure.</span></span>

![Microsoft 365를 사용하는 원격 작업자용 기본 인프라](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

<span data-ttu-id="48198-133">원격 작업자를 위한 Microsoft 365의 기능을 사용하려면 다음 Microsoft 365 기능을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="48198-133">To enable the capabilities of Microsoft 365 for your remote workers, use these Microsoft 365 features.</span></span>

| <span data-ttu-id="48198-134">기능 또는 특징</span><span class="sxs-lookup"><span data-stu-id="48198-134">Capability or feature</span></span> | <span data-ttu-id="48198-135">설명</span><span class="sxs-lookup"><span data-stu-id="48198-135">Description</span></span> | <span data-ttu-id="48198-136">라이선싱</span><span class="sxs-lookup"><span data-stu-id="48198-136">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="48198-137">보안 기본값을 사용하여 MFA 실행</span><span class="sxs-lookup"><span data-stu-id="48198-137">MFA enforced with security defaults</span></span>   | <span data-ttu-id="48198-138">로그인에 대한 보조 인증을 요구함으로써 손상된 ID와 장치로부터 보호합니다. 보안 기본값은 모든 사용자 계정에 대해 MFA를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="48198-138">Protect against compromised identities and devices by requiring a second form of authentication for sign-ins. Security defaults requires MFA for all user accounts.</span></span>   | <span data-ttu-id="48198-139">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="48198-139">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="48198-140">조건부 액세스로 MFA 실행</span><span class="sxs-lookup"><span data-stu-id="48198-140">MFA enforced with Conditional Access</span></span>| <span data-ttu-id="48198-141">조건부 액세스 정책을 포함한 로그인 속성을 기반으로 하는 MFA가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="48198-141">Require MFA based on the properties of the sign-in with Conditional Access policies.</span></span>    | <span data-ttu-id="48198-142">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="48198-142">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="48198-143">위험 기반 조건부 액세스로 MFA 실행</span><span class="sxs-lookup"><span data-stu-id="48198-143">MFA enforced with risk-based Conditional Access</span></span>   | <span data-ttu-id="48198-144">ID용 Microsoft Defender와 함께 사용자 로그인의 위험을 기반으로 하는 MFA가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="48198-144">Require MFA based on the risk of the user sign-in with Microsoft Defender for Identity.</span></span> | <span data-ttu-id="48198-145">Azure AD Premium P2 라이선스를 포함한 Microsoft 365 E5 또는 E3</span><span class="sxs-lookup"><span data-stu-id="48198-145">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> | 
| <span data-ttu-id="48198-146">셀프 서비스 암호 재설정(SSPR)</span><span class="sxs-lookup"><span data-stu-id="48198-146">Self-Service Password Reset (SSPR)</span></span>    | <span data-ttu-id="48198-147">사용자가 암호 또는 계정을 다시 설정하거나 잠금 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48198-147">Allow your users to reset or unlock their passwords or accounts.</span></span>  | <span data-ttu-id="48198-148">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="48198-148">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="48198-149">Azure AD 응용 프로그램 프록시</span><span class="sxs-lookup"><span data-stu-id="48198-149">Azure AD Application Proxy</span></span>    | <span data-ttu-id="48198-150">인트라넷 서버에서 호스트되는 웹 기반 응용 프로그램에 대한 보안 원격 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="48198-150">Provide secure remote access for web-based applications hosted on intranet servers.</span></span>   | <span data-ttu-id="48198-151">별도의 유료 Azure 구독 필요</span><span class="sxs-lookup"><span data-stu-id="48198-151">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="48198-152">Azure 지점 및 사이트 간 VPN</span><span class="sxs-lookup"><span data-stu-id="48198-152">Azure Point-to-Site VPN</span></span>   | <span data-ttu-id="48198-153">Azure 가상 네트워크를 통해 원격 작업자의 장치에서 인트라넷으로의 연결을 안전하게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="48198-153">Create a secure connection from a remote worker’s device to your intranet through an Azure virtual network.</span></span>   | <span data-ttu-id="48198-154">별도의 유료 Azure 구독 필요</span><span class="sxs-lookup"><span data-stu-id="48198-154">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="48198-155">Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="48198-155">Windows Virtual Desktop</span></span>   | <span data-ttu-id="48198-156">가상 데스크톱이 Azure에서 실행되는 관리되지 않는 개인 장치만 사용할 수 있는 원격 작업자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="48198-156">Support remote workers who can only use their personal and unmanaged devices with virtual desktops running in Azure.</span></span> | <span data-ttu-id="48198-157">별도의 유료 Azure 구독 필요</span><span class="sxs-lookup"><span data-stu-id="48198-157">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="48198-158">원격 데스크톱 서비스(RDS)</span><span class="sxs-lookup"><span data-stu-id="48198-158">Remote Desktop Services (RDS)</span></span> | <span data-ttu-id="48198-159">직원이 인트라넷의 Windows 기반 컴퓨터에 연결하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="48198-159">Allow employees to connect into Windows-based computers on your intranet.</span></span> | <span data-ttu-id="48198-160">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="48198-160">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="48198-161">원격 데스크톱 서비스 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="48198-161">Remote Desktop Services Gateway</span></span>   | <span data-ttu-id="48198-162">통신을 암호화하고 RDS 호스트가 인터넷에 직접 노출되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="48198-162">Encrypt communications and prevent the RDS hosts from being directly exposed to the Internet.</span></span> | <span data-ttu-id="48198-163">별도의 Windows Server 라이선스 필요</span><span class="sxs-lookup"><span data-stu-id="48198-163">Requires separate Windows Server licenses</span></span> |
| <span data-ttu-id="48198-164">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="48198-164">Microsoft Intune</span></span> | <span data-ttu-id="48198-165">장치 및 응용 프로그램을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="48198-165">Manage devices and applications.</span></span>   | <span data-ttu-id="48198-166">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="48198-166">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="48198-167">기능이며</span><span class="sxs-lookup"><span data-stu-id="48198-167">Configuration Manager</span></span> | <span data-ttu-id="48198-168">장치의 소프트웨어 설치, 업데이트 및 설정 관리</span><span class="sxs-lookup"><span data-stu-id="48198-168">Manage software installations, updates, and settings on your devices</span></span> | <span data-ttu-id="48198-169">별도의 Configuration Manager 라이선스 필요</span><span class="sxs-lookup"><span data-stu-id="48198-169">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="48198-170">Desktop Analytics</span><span class="sxs-lookup"><span data-stu-id="48198-170">Desktop Analytics</span></span> | <span data-ttu-id="48198-171">Windows 클라이언트의 업데이트 준비 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="48198-171">Determine the update readiness of your Windows clients.</span></span>   | <span data-ttu-id="48198-172">별도의 Configuration Manager 라이선스 필요</span><span class="sxs-lookup"><span data-stu-id="48198-172">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="48198-173">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="48198-173">Windows Autopilot</span></span> | <span data-ttu-id="48198-174">새 Windows 10 장치를 업무용으로 사용하도록 설정하고 사전 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="48198-174">Set up and pre-configure new Windows 10 devices for productive use.</span></span>   | <span data-ttu-id="48198-175">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="48198-175">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="48198-176">Microsoft Teams, Exchange Online, SharePoint Online 및 OneDrive, Microsoft 365 앱, Microsoft Power Platform 및 Yammer</span><span class="sxs-lookup"><span data-stu-id="48198-176">Microsoft Teams, Exchange Online, SharePoint Online and OneDrive, Microsoft 365 Apps, Microsoft Power Platform, and Yammer</span></span> | <span data-ttu-id="48198-177">만들고, 소통하며, 공동 작업합니다.</span><span class="sxs-lookup"><span data-stu-id="48198-177">Create, communicate, and collaborate.</span></span> | <span data-ttu-id="48198-178">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="48198-178">Microsoft 365 E3 or E5</span></span> |
||||

<span data-ttu-id="48198-179">보안 및 규정 준수 기준에 대한 내용은 [원격 작업자에 대한 보안 및 규정 준수 배포](empower-people-to-work-remotely-security-compliance.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="48198-179">For security and compliance criteria, see [Deploy security and compliance for remote workers](empower-people-to-work-remotely-security-compliance.md).</span></span>

<a name="poster"></a> <span data-ttu-id="48198-180">이 솔루션의 2페이지 요약은 [원격 작업자 지원 포스터](../downloads/empower-remote-workers.pdf)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="48198-180">For a 2-page summary of this solution, see the [Empower remote workers poster](../downloads/empower-remote-workers.pdf).</span></span>

<span data-ttu-id="48198-181">[![원격 작업자 지원](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../downloads/empower-remote-workers.pdf)</span><span class="sxs-lookup"><span data-stu-id="48198-181">[![Empower remote workers poster](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../downloads/empower-remote-workers.pdf)</span></span>

<span data-ttu-id="48198-182">이 포스터를 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/empower-remote-workers.pdf)나 [PowerPoint](https://download.microsoft.com/download/5/1/1/511b77a9-a34c-4ea7-af2a-32b07f20b780/empower-remote-workers.pptx) 형식으로 다운로드할 수 있고 편지형, 법률형, 타블로이드(11 x 17) 크기 용지에 인쇄할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48198-182">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/empower-remote-workers.pdf) or  [PowerPoint](https://download.microsoft.com/download/5/1/1/511b77a9-a34c-4ea7-af2a-32b07f20b780/empower-remote-workers.pptx) formats and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

## <a name="provide-remote-working-for-all-of-your-workers"></a><span data-ttu-id="48198-183">모든 직원에게 원격 작업 제공</span><span class="sxs-lookup"><span data-stu-id="48198-183">Provide remote working for all of your workers</span></span>

<span data-ttu-id="48198-184">모든 직원이 다음 장치를 사용하여 어디서나 생산성을 유지할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48198-184">You can enable all of your workers to stay productive from anywhere with these devices:</span></span>

- <span data-ttu-id="48198-185">웹을 통해 직접 Microsoft 365 클라우드 앱 및 서비스에 액세스할 수 있는 기능, 보안 및 성능을 갖춘 Surface 노트북 및 Windows 10과 같은 최신 장치</span><span class="sxs-lookup"><span data-stu-id="48198-185">A modern device, such as a Surface laptop and Windows 10, which has the features, security, and performance to access Microsoft 365 cloud apps and services directly over the web.</span></span>

- <span data-ttu-id="48198-186">빠르게 배포된 [Windows 10 기반 가상 데스크톱](empower-people-to-work-remotely-remote-access.md#deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices)을 통해 간접적으로 Microsoft 365 클라우드 앱 및 서비스에 액세스할 수 있는 가정에서 사용되는 구형 노트북 또는 데스크톱을 포함한 모든 장치</span><span class="sxs-lookup"><span data-stu-id="48198-186">Any device including older laptops or desktops used from home, which can access Microsoft 365 cloud apps and services indirectly through a quickly deployed [Windows 10-based virtual desktop](empower-people-to-work-remotely-remote-access.md#deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices).</span></span> <span data-ttu-id="48198-187">이 옵션은 고성능, 강력한 보안 및 단순화된 IT 관리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="48198-187">This option provides high performance, strong security, and simplified IT management.</span></span>

## <a name="next-steps"></a><span data-ttu-id="48198-188">다음 단계</span><span class="sxs-lookup"><span data-stu-id="48198-188">Next steps</span></span>

<span data-ttu-id="48198-189">다음 단계를 사용하여 조직의 서버 및 클라우드 서비스에 대한 액세스를 보호하고 최적화하며 원격 작업자의 생산성을 극대화합니다.</span><span class="sxs-lookup"><span data-stu-id="48198-189">Use these steps to secure and optimize access to your organization's servers and cloud services and maximize your remote worker's productivity.</span></span>

1. [<span data-ttu-id="48198-190">MFA로 로그인 보안 강화</span><span class="sxs-lookup"><span data-stu-id="48198-190">Increase sign-in security with MFA</span></span>](empower-people-to-work-remotely-secure-sign-in.md)
2. [<span data-ttu-id="48198-191">온-프레미스 앱 및 서비스로의 원격 액세스 제공</span><span class="sxs-lookup"><span data-stu-id="48198-191">Provide remote access to on-premises apps and services</span></span>](empower-people-to-work-remotely-remote-access.md)
3. [<span data-ttu-id="48198-192">보안 및 규정 준수 서비스 배포</span><span class="sxs-lookup"><span data-stu-id="48198-192">Deploy security and compliance services</span></span>](empower-people-to-work-remotely-security-compliance.md)
4. [<span data-ttu-id="48198-193">장치, PC 및 기타 끝점에 대한 끝점 관리 기능 배포</span><span class="sxs-lookup"><span data-stu-id="48198-193">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>](empower-people-to-work-remotely-manage-endpoints.md)
5. [<span data-ttu-id="48198-194">원격 작업자 생산성 앱 및 서비스 배포</span><span class="sxs-lookup"><span data-stu-id="48198-194">Deploy remote worker productivity apps and services</span></span>](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [<span data-ttu-id="48198-195">원격 작업자 교육 및 사용 피드백 처리</span><span class="sxs-lookup"><span data-stu-id="48198-195">Train remote workers and address usage feedback</span></span>](empower-people-to-work-remotely-train-monitor-usage.md)

<span data-ttu-id="48198-196">[![Microsoft 365에서 원격 작업을 위한 인프라를 설정하는 단계](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)</span><span class="sxs-lookup"><span data-stu-id="48198-196">[![The steps to set up your infrastructure for remote work with Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)</span></span>

<span data-ttu-id="48198-197">가상이지만 대표적인 다국적 조직이 원격 작업을 위해 인프라를 구축하는 방법을 보려면 [Contoso의 COVID-19 대응 및 원격 및 현장 작업을 위한 인프라](contoso-remote-onsite-work.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="48198-197">To see how a fictional but representative multi-national organization set up its infrastructure for remote work, see [Contoso's COVID-19 response and infrastructure for remote and onsite work](contoso-remote-onsite-work.md).</span></span>
