---
title: Microsoft 365를 사용하여 원격 작업자의 역량 강화하기
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
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
- M365solutions
ms.custom: ''
description: 직원들이 언제 어디서나 원격으로 작업할 수 있도록 하는 보안 및 서비스 인프라를 구성합니다.
ms.openlocfilehash: 763c8e745eb54897c1df88ecb5a9064987ed5a13
ms.sourcegitcommit: 9195c83c725a7e6ed395ce0253304da54e2195f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "44560465"
---
# <a name="empower-remote-workers-with-microsoft-365"></a><span data-ttu-id="bbe7f-103">Microsoft 365를 사용하여 원격 작업자의 역량 강화하기</span><span class="sxs-lookup"><span data-stu-id="bbe7f-103">Empower remote workers with Microsoft 365</span></span>

<span data-ttu-id="bbe7f-104">직원들이 회사의 사내 구축 환경 및 클라우드 기반 정보, 도구 및 리소스에 안전하게 액세스할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-104">Your business may need to enable your workers to have secure access to your organization's on-premises and cloud-based information, tools, and resources from their homes.</span></span> <span data-ttu-id="bbe7f-105">많은 조직에서 Office를 원활하고 안전하게 사용할 수 있도록 하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-105">Allowing workers to work away from the office seamlessly and securely is important for many organizations to:</span></span>

- <span data-ttu-id="bbe7f-106">사무실 공간에 저장</span><span class="sxs-lookup"><span data-stu-id="bbe7f-106">Save on office space.</span></span>
- <span data-ttu-id="bbe7f-107">이동할 의사가 없는 직원을 고용하고 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-107">Hire and retain workers who are unwilling to relocate.</span></span>
- <span data-ttu-id="bbe7f-108">직원의 출퇴근를 줄여 업무 이외에 생산성을 높이고 스트레스 해소 활동을 위한 시간을 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-108">Reduce worker commuting, leaving them with more time to be productive and for stress-reducing activities outside of work.</span></span>

<span data-ttu-id="bbe7f-109">원격 작업(teleworking이라고도 함)은 다음과 같은 항목을 포함하는 스펙트럼에 걸쳐 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-109">Remote working, also known as teleworking, can span a spectrum that includes:</span></span>

- <span data-ttu-id="bbe7f-110">회의나 클라이언트 회의를 위해 가끔 사무실을 떠나는 직원</span><span class="sxs-lookup"><span data-stu-id="bbe7f-110">workers that are occasionally away from the office for conferences or client meetings.</span></span>
- <span data-ttu-id="bbe7f-111">풀타임 원격으로 작업을 하는 몇몇 직원</span><span class="sxs-lookup"><span data-stu-id="bbe7f-111">Some workers that work remotely full-time.</span></span>
- <span data-ttu-id="bbe7f-112">사무실이 없고 모든 직원이 원격으로 일하는 완전한 원격 조직</span><span class="sxs-lookup"><span data-stu-id="bbe7f-112">A fully remote organization in which there is no office and all workers are remote.</span></span>

<span data-ttu-id="bbe7f-113">원격 작업자는 전 세계 어디서나 언제든지 다음 항목에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-113">From anywhere in the world and at any time, remote workers must be able to access:</span></span>

- <span data-ttu-id="bbe7f-114">온-프레미스 응용 프로그램 데이터 센터에서 제공하는 그러한 조직 리소스</span><span class="sxs-lookup"><span data-stu-id="bbe7f-114">Organization resources, such those offered by on-premises application datacenters.</span></span>
- <span data-ttu-id="bbe7f-115">Teams, Exchange Online, SharePoint 및 OneDrive와 같은 Microsoft 365 구독의 클라우드 기반 서비스 및 데이터</span><span class="sxs-lookup"><span data-stu-id="bbe7f-115">Cloud-based services and data in your Microsoft 365 subscription, such as Teams, Exchange Online, SharePoint, and OneDrive.</span></span>

<span data-ttu-id="bbe7f-116">원활하게 로그인하려면 Active Directory 도메인 서비스(AD DS) 사용자 계정을 Azure Active Directory(Azure AD)와 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-116">For a seamless sign-in experience, your Active Directory Domain Services (AD DS) user accounts should be synchronized with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="bbe7f-117">Windows 10 장치를 보호하려면 Intune에서 장치를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-117">To protect your Windows 10 devices, they should be enrolled in Intune.</span></span> <span data-ttu-id="bbe7f-118">다음은 인프라의 개괄적인 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-118">Here is a high-level view of the infrastructure.</span></span>

![Microsoft 365를 사용하는 원격 작업자용 기본 인프라](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)


<span data-ttu-id="bbe7f-120">COVID-19 위기에 대응하는 등 원격 작업자를 지원하기 위해 Microsoft 365의 기능을 조합하여 원격 작업자는 다음과 같은 매우 협력적인 방식으로 업무를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-120">To support remote workers, for example in response to the COVID-19 crisis, a combination of features in Microsoft 365 enables your remote workers in a highly collaborative way, such as:</span></span>

- <span data-ttu-id="bbe7f-121">온라인 회의 및 채팅 세션</span><span class="sxs-lookup"><span data-stu-id="bbe7f-121">Online meetings and chat sessions.</span></span>
- <span data-ttu-id="bbe7f-122">전역 접근성과 실시간 공동 작업을 통해 클라우드 기반 파일 저장소를 위한 공유 작업 영역</span><span class="sxs-lookup"><span data-stu-id="bbe7f-122">Shared workspaces for cloud-based file storage with global accessibility and real-time collaboration.</span></span>
- <span data-ttu-id="bbe7f-123">작업을 분할하고 작업을 완료하기 위한 공유 작업 및 워크플로</span><span class="sxs-lookup"><span data-stu-id="bbe7f-123">Shared tasks and workflows to divide up the work and get things done.</span></span>

<span data-ttu-id="bbe7f-124">강력한 보안을 위해 Microsoft 365에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-124">For strong security, Microsoft 365 includes:</span></span>

- <span data-ttu-id="bbe7f-125">인증 요구 사항을 적용하고, 고위험 로그인을 감지하여 대응하고, 선택한 앱과 비규격 장치를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-125">Enforced authentication requirements, detecting and responding to high-risk sign-ins, and blocking selected apps and non-compliant devices.</span></span>
- <span data-ttu-id="bbe7f-126">클라우드에서 암호화된 연결 및 디지털 자산</span><span class="sxs-lookup"><span data-stu-id="bbe7f-126">Encrypted connections and digital assets in the cloud.</span></span>
- <span data-ttu-id="bbe7f-127">파일에 대한 작업을 수행할 수 있는 사용자를 정의하는 권한</span><span class="sxs-lookup"><span data-stu-id="bbe7f-127">Permissions to define who can do what with files.</span></span>
- <span data-ttu-id="bbe7f-128">Windows 10 장치를 보호하는 포괄적인 보안 기능</span><span class="sxs-lookup"><span data-stu-id="bbe7f-128">Comprehensive security features to protect Windows 10 devices.</span></span>

<span data-ttu-id="bbe7f-129">원격 작업자에 대한 이러한 조건을 충족하기 위해 다음과 같은 Microsoft 365 기능 및 특징을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-129">To meet these criteria for remote workers, use these Microsoft 365 capabilities and features.</span></span>

| <span data-ttu-id="bbe7f-130">기능 또는 특징</span><span class="sxs-lookup"><span data-stu-id="bbe7f-130">Capability or feature</span></span> | <span data-ttu-id="bbe7f-131">설명</span><span class="sxs-lookup"><span data-stu-id="bbe7f-131">Description</span></span> | <span data-ttu-id="bbe7f-132">라이선싱</span><span class="sxs-lookup"><span data-stu-id="bbe7f-132">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="bbe7f-133">보안 기본값을 사용하여 MFA 실행</span><span class="sxs-lookup"><span data-stu-id="bbe7f-133">MFA enforced with security defaults</span></span>   | <span data-ttu-id="bbe7f-134">로그인에 대한 보조 인증을 요구함으로써 손상된 ID와 장치로부터 보호합니다. 보안 기본값은 모든 사용자 계정에 대해 MFA를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-134">Protect against compromised identities and devices by requiring a second form of authentication for sign-ins. Security defaults requires MFA for all user accounts.</span></span>   | <span data-ttu-id="bbe7f-135">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="bbe7f-135">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="bbe7f-136">조건부 액세스로 MFA 실행</span><span class="sxs-lookup"><span data-stu-id="bbe7f-136">MFA enforced with Conditional Access</span></span>| <span data-ttu-id="bbe7f-137">조건부 액세스 정책을 포함한 로그인 속성을 기반으로 하는 MFA가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-137">Require MFA based on the properties of the sign-in with Conditional Access policies.</span></span>    | <span data-ttu-id="bbe7f-138">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="bbe7f-138">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="bbe7f-139">위험 기반 조건부 액세스로 MFA 실행</span><span class="sxs-lookup"><span data-stu-id="bbe7f-139">MFA enforced with risk-based Conditional Access</span></span>   | <span data-ttu-id="bbe7f-140">Azure Advanced Threat Protection을 포함한 사용자 로그인에 대한 위험을 기반으로 하는 MFA가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-140">Require MFA based on the risk of the user sign-in with Azure Advanced Threat Protection.</span></span> | <span data-ttu-id="bbe7f-141">Azure AD Premium P2 라이선스를 포함한 Microsoft 365 E5 또는 E3</span><span class="sxs-lookup"><span data-stu-id="bbe7f-141">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> | 
| <span data-ttu-id="bbe7f-142">셀프 서비스 암호 재설정(SSPR)</span><span class="sxs-lookup"><span data-stu-id="bbe7f-142">Self-Service Password Reset (SSPR)</span></span>    | <span data-ttu-id="bbe7f-143">사용자가 암호 또는 계정을 다시 설정하거나 잠금 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-143">Allow your users to reset or unlock their passwords or accounts.</span></span>  | <span data-ttu-id="bbe7f-144">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="bbe7f-144">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="bbe7f-145">Azure AD 응용 프로그램 프록시</span><span class="sxs-lookup"><span data-stu-id="bbe7f-145">Azure AD Application Proxy</span></span>    | <span data-ttu-id="bbe7f-146">인트라넷 서버에서 호스트되는 웹 기반 응용 프로그램에 대한 보안 원격 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-146">Provide secure remote access for web-based applications hosted on intranet servers.</span></span>   | <span data-ttu-id="bbe7f-147">별도의 유료 Azure 구독 필요</span><span class="sxs-lookup"><span data-stu-id="bbe7f-147">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="bbe7f-148">Azure 지점 및 사이트 간 VPN</span><span class="sxs-lookup"><span data-stu-id="bbe7f-148">Azure Point-to-Site VPN</span></span>   | <span data-ttu-id="bbe7f-149">Azure 가상 네트워크를 통해 원격 작업자의 장치에서 인트라넷으로의 연결을 안전하게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-149">Create a secure connection from a remote worker’s device to your intranet through an Azure virtual network.</span></span>   | <span data-ttu-id="bbe7f-150">별도의 유료 Azure 구독 필요</span><span class="sxs-lookup"><span data-stu-id="bbe7f-150">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="bbe7f-151">Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="bbe7f-151">Windows Virtual Desktop</span></span>   | <span data-ttu-id="bbe7f-152">가상 데스크톱이 Azure에서 실행되는 관리되지 않는 개인 장치만 사용할 수 있는 원격 작업자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-152">Support remote workers who can only use their personal and unmanaged devices with virtual desktops running in Azure.</span></span> | <span data-ttu-id="bbe7f-153">별도의 유료 Azure 구독 필요</span><span class="sxs-lookup"><span data-stu-id="bbe7f-153">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="bbe7f-154">원격 데스크톱 서비스(RDS)</span><span class="sxs-lookup"><span data-stu-id="bbe7f-154">Remote Desktop Services (RDS)</span></span> | <span data-ttu-id="bbe7f-155">직원이 인트라넷의 Windows 기반 컴퓨터에 연결하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-155">Allow employees to connect into Windows-based computers on your intranet.</span></span> | <span data-ttu-id="bbe7f-156">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="bbe7f-156">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="bbe7f-157">원격 데스크톱 서비스 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="bbe7f-157">Remote Desktop Services Gateway</span></span>   | <span data-ttu-id="bbe7f-158">통신을 암호화하고 RDS 호스트가 인터넷에 직접 노출되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-158">Encrypt communications and prevent the RDS hosts from being directly exposed to the Internet.</span></span> | <span data-ttu-id="bbe7f-159">별도의 Windows Server 라이선스 필요</span><span class="sxs-lookup"><span data-stu-id="bbe7f-159">Requires separate Windows Server licenses</span></span> |
| <span data-ttu-id="bbe7f-160">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="bbe7f-160">Microsoft Intune</span></span> | <span data-ttu-id="bbe7f-161">장치 및 응용 프로그램을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-161">Manage devices and applications.</span></span>   | <span data-ttu-id="bbe7f-162">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="bbe7f-162">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="bbe7f-163">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bbe7f-163">Configuration Manager</span></span> | <span data-ttu-id="bbe7f-164">장치의 소프트웨어 설치, 업데이트 및 설정 관리</span><span class="sxs-lookup"><span data-stu-id="bbe7f-164">Manage software installations, updates, and settings on your devices</span></span> | <span data-ttu-id="bbe7f-165">별도의 Configuration Manager 라이선스 필요</span><span class="sxs-lookup"><span data-stu-id="bbe7f-165">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="bbe7f-166">Desktop Analytics</span><span class="sxs-lookup"><span data-stu-id="bbe7f-166">Desktop Analytics</span></span> | <span data-ttu-id="bbe7f-167">Windows 클라이언트의 업데이트 준비 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-167">Determine the update readiness of your Windows clients.</span></span>   | <span data-ttu-id="bbe7f-168">별도의 Configuration Manager 라이선스 필요</span><span class="sxs-lookup"><span data-stu-id="bbe7f-168">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="bbe7f-169">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="bbe7f-169">Windows Autopilot</span></span> | <span data-ttu-id="bbe7f-170">새 Windows 10 장치를 업무용으로 사용하도록 설정하고 사전 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-170">Set up and pre-configure new Windows 10 devices for productive use.</span></span>   | <span data-ttu-id="bbe7f-171">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="bbe7f-171">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="bbe7f-172">Microsoft Teams, Exchange Online, SharePoint Online 및 OneDrive, Microsoft 365 Apps, Microsoft Power Platform, Yammer, Power Apps</span><span class="sxs-lookup"><span data-stu-id="bbe7f-172">Microsoft Teams, Exchange Online, SharePoint Online and OneDrive, Microsoft 365 Apps, Microsoft Power Platform, Yammer, Power Apps</span></span> | <span data-ttu-id="bbe7f-173">만들고, 소통하며, 공동 작업합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-173">Create, communicate, and collaborate.</span></span> | <span data-ttu-id="bbe7f-174">Microsoft 365 E3 및 E5</span><span class="sxs-lookup"><span data-stu-id="bbe7f-174">Microsoft 365 E3 and E5</span></span> |
||||

<span data-ttu-id="bbe7f-175">다음 단계를 사용하여 조직의 서버, 데이터 및 클라우드 서비스에 대한 액세스를 보호하고 최적화하며 최대 작업자 생산성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-175">Use these steps to secure and optimize access to your organization's servers, data, and cloud services and enable maximum worker productivity.</span></span>

1. [<span data-ttu-id="bbe7f-176">MFA로 로그인 보안 강화</span><span class="sxs-lookup"><span data-stu-id="bbe7f-176">Increase sign-in security with MFA</span></span>](empower-people-to-work-remotely-secure-sign-in.md)
2. [<span data-ttu-id="bbe7f-177">온-프레미스 앱 및 서비스로의 원격 액세스 제공</span><span class="sxs-lookup"><span data-stu-id="bbe7f-177">Provide remote access to on-premises apps and services</span></span>](empower-people-to-work-remotely-remote-access.md)
3. [<span data-ttu-id="bbe7f-178">장치, PC 및 기타 끝점에 대한 끝점 관리 기능 배포</span><span class="sxs-lookup"><span data-stu-id="bbe7f-178">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>](empower-people-to-work-remotely-manage-endpoints.md)
4. [<span data-ttu-id="bbe7f-179">원격 작업자 생산성 앱 및 서비스 배포</span><span class="sxs-lookup"><span data-stu-id="bbe7f-179">Deploy remote worker productivity apps and services</span></span>](empower-people-to-work-remotely-teams-productivity-apps.md)
5. [<span data-ttu-id="bbe7f-180">커뮤니케이션 장소 만들기</span><span class="sxs-lookup"><span data-stu-id="bbe7f-180">Create communication venues</span></span>](empower-people-to-work-remotely-communication-venues.md)
6. [<span data-ttu-id="bbe7f-181">원격 작업자 교육 및 사용 피드백 처리</span><span class="sxs-lookup"><span data-stu-id="bbe7f-181">Train remote workers and address usage feedback</span></span>](empower-people-to-work-remotely-train-monitor-usage.md)

![Microsoft 365를 사용하여 원격 작업자의 역량을 강화하기 위한 단계](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)

<span data-ttu-id="bbe7f-183">원격 작업자 지원에 대한 Microsoft의 최신 정보는 [원격 작업 기술 커뮤니티 사이트](https://resources.techcommunity.microsoft.com/enabling-remote-work/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bbe7f-183">For the latest information from Microsoft about supporting remote workers, see the [Enabling remote work Tech Community site](https://resources.techcommunity.microsoft.com/enabling-remote-work/).</span></span>
