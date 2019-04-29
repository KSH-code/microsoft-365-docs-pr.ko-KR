---
title: '3단계: Windows 10 Enterprise 인프라 종료 기준'
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 03/05/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 구성이 Windows 10 Enterprise에 대한 Microsoft 365 Enterprise 조건을 충족하는지 확인합니다.
ms.openlocfilehash: 1e8a2e748f42431465c027acbc468f4c5891d320
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289520"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a><span data-ttu-id="df589-103">3단계: Windows 10 Enterprise 인프라 종료 기준</span><span class="sxs-lookup"><span data-stu-id="df589-103">Phase 3: Windows 10 Enterprise infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="df589-104">Windows 10 Enterprise 인프라가 다음과 같은 필수 조건을 충족하는지 확인하고 선택적 항목을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df589-104">Make sure your Windows 10 Enterprise infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a><span data-ttu-id="df589-105">필수 작업: Microsoft 365 도메인 추가 및 확인</span><span class="sxs-lookup"><span data-stu-id="df589-105">Required: Your Microsoft 365 domains are added and verified</span></span>

<span data-ttu-id="df589-106">Office 365 및 Intune 구독을 위한 Azure AD 테넌트는 "onmicrosoft.com"을 포함하는 도메인 이름이 아니라 인터넷 도메인 이름(예: contoso.com)으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="df589-106">The Azure AD tenant for your Office 365 and Intune subscriptions are configured with your Internet domain names (such as contoso.com), rather than just a domain name that includes “onmicrosoft.com”.</span></span> 

<span data-ttu-id="df589-p101">이렇게 하지 않으면 구성할 수 있는 인증 방법이 제한됩니다. 예를 들어, 통과 인증 및 페더레이션 인증에서는 "onmicrosoft.com" 도메인 이름을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df589-p101">If you do not do so, you will be limited in the authentication methods that you can configure. For example, pass-through and federated authentication cannot use the “onmicrosoft.com”  domain name.</span></span>

<span data-ttu-id="df589-109">필요한 경우 [1단계](windows10-prepare-your-org.md)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df589-109">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this requirement.</span></span>

## <a name="optional-your-users-are-added-and-licensed"></a><span data-ttu-id="df589-110">선택적 작업: 사용자 추가 및 사용 허가</span><span class="sxs-lookup"><span data-stu-id="df589-110">Optional: Your users are added and licensed</span></span>

<span data-ttu-id="df589-111">사용자에 해당하는 계정은 Office 365 및 Intune 구독을 위한 Azure AD 테넌트에 직접 추가되거나 온-프레미스 AD DS(Active Directory Domain Services)에서의 디렉터리 동기화를 통해 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="df589-111">The accounts corresponding to your users are added, either directly to your Azure AD tenant for your Office 365 and Intune subscriptions, or from directory synchronization from your on-premises Windows Server AD.</span></span>

<span data-ttu-id="df589-112">사용자가 추가되면 전역 또는 사용자 관리자로서 직접, 또는 그룹 구성원 자격을 통해 자동으로 Microsoft 365 Enterprise 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df589-112">Once the users are added, you can assign them Microsoft 365 Enterprise licenses, either directly as a global or user administrator, or automatically through group membership.</span></span>

<span data-ttu-id="df589-113">필요한 경우 [1단계](windows10-prepare-your-org.md)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df589-113">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

## <a name="optional-diagnostics-are-enabled"></a><span data-ttu-id="df589-114">선택 사항: 진단 사용</span><span class="sxs-lookup"><span data-stu-id="df589-114">Optional: Diagnostics are enabled</span></span>

<span data-ttu-id="df589-115">그룹 정책, Microsoft Intune, 레지스트리 편집기를 사용한 진단 데이터 설정 또는 명령 프롬프트에서 진단 데이터 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="df589-115">You have enabled diagnostic data settings using Group Policy, Microsoft Intune, the Registry Editor, or at the command prompt.</span></span>

<span data-ttu-id="df589-116">필요한 경우 [1단계](windows10-prepare-your-org.md)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df589-116">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a><span data-ttu-id="df589-117">현재 위치 업그레이드를 위한 필수 작업: 운영 체제 배포를 위한 Configuration Manager 작업 시퀀스 생성</span><span class="sxs-lookup"><span data-stu-id="df589-117">Required for in-place upgrade: Created a Configuration Manager task sequence for an operating system deployment</span></span>

<span data-ttu-id="df589-118">Windows 7 또는 Windows 8.1이 실행되는 장치에서 현재 위치 업그레이드를 진행하기 위한 Configuration Manager 작업 시퀀스를 시작하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df589-118">To start a Configuration Manager task sequence to do an in-place upgrade on a device running Windows 7 or Windows 8.1, you must have:</span></span>

- <span data-ttu-id="df589-119">적절한 Windows 진단 데이터 수준 설정</span><span class="sxs-lookup"><span data-stu-id="df589-119">Set the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="df589-120">Windows 업그레이드 준비 상태 확인</span><span class="sxs-lookup"><span data-stu-id="df589-120">Verify the readiness to upgrade Windows</span></span>
- <span data-ttu-id="df589-121">Windows 10 운영 체제 이미지에 장치 컬렉션 및 운영 체제 배포를 포함하는 Configuration Manager 작업 시퀀스 생성</span><span class="sxs-lookup"><span data-stu-id="df589-121">Create a Configuration Manager task sequence that includes a device collection and an operating system deployment with a Windows 10 OS image</span></span>

<span data-ttu-id="df589-p102">이 작업이 완료되면 Windows를 업그레이드할 준비가 된 장치에서 현재 위치 업그레이드를 수행할 수 있습니다. Microsoft 365 Enterprise를 최대한 활용하기 위해 Windows 7 및 Windows 8.1이 실행되는 장치를 최대한 많이 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="df589-p102">Once this is in place, you can perform in-place upgrades on devices that are ready to upgrade Windows. To get the maximum benefit out of Microsoft 365 Enterprise, upgrade as many devices running Windows 7 and Windows 8.1 as you can.</span></span> 

<span data-ttu-id="df589-p103">Windows 10 Enterprise를 실행하는 모든 장치는 Microsoft 365 Enterprise의 통합 솔루션 이점을 누릴 수 있습니다. Windows 7 또는 Windows 8.1이 실행되는 나머지 장치는 클라우드 연결 기술 및 Windows 10 Enterprise의 고급 보안 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df589-p103">Each device running Windows 10 Enterprise can participate in the benefits of the integrated solution of Microsoft 365 Enterprise. The remaining devices running Windows 7 or Windows 8.1 cannot use the cloud-connected technologies and advanced security features of Windows 10 Enterprise.</span></span>

<span data-ttu-id="df589-126">필요한 경우 [2단계](windows10-deploy-inplaceupgrade.md)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df589-126">If needed, [Step 2](windows10-deploy-inplaceupgrade.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a><span data-ttu-id="df589-127">새 장치를 위한 필수 작업: Windows Autopilot 구성</span><span class="sxs-lookup"><span data-stu-id="df589-127">Required for new devices: Configured Windows Autopilot</span></span>

<span data-ttu-id="df589-128">Windows Autopilot을 사용하여 새 장치에 Windows 10 Enterprise를 배포하고 사용자 지정하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df589-128">To use Windows Autopilot to deploy and customize Windows 10 Enterprise on a new device, you must have:</span></span>

- <span data-ttu-id="df589-129">적절한 Windows 진단 데이터 수준 구성</span><span class="sxs-lookup"><span data-stu-id="df589-129">Set the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="df589-130">다음을 포함하는 Windows Autopilot에 대한 필수 구성 요소 구성</span><span class="sxs-lookup"><span data-stu-id="df589-130">Completed the prerequisites for Windows Autopilot, which include:</span></span>
   - <span data-ttu-id="df589-131">장치 등록 및 OOBE 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="df589-131">Device registration and OOBE customization</span></span>
   - <span data-ttu-id="df589-132">OOBE에 대한 회사 브랜딩</span><span class="sxs-lookup"><span data-stu-id="df589-132">Company branding for OOBE</span></span>
   - <span data-ttu-id="df589-133">Microsoft Intune에서 MDM 자동 등록</span><span class="sxs-lookup"><span data-stu-id="df589-133">MDM auto-enrollment in Microsoft Intune</span></span>
   - <span data-ttu-id="df589-134">Windows Autopilot에서 사용되는 클라우드 서비스에 대한 네트워크 연결</span><span class="sxs-lookup"><span data-stu-id="df589-134">Network connectivity to cloud services used by Windows Autopilot</span></span>
- <span data-ttu-id="df589-135">Windows 10, 버전 1703 이상이 미리 설치된 디바이스</span><span class="sxs-lookup"><span data-stu-id="df589-135">Devices must be pre-installed with Windows 10, version 1703 or later</span></span>
- <span data-ttu-id="df589-136">조직을 위한 Windows Autopilot Deployment 프로그램 선택</span><span class="sxs-lookup"><span data-stu-id="df589-136">Selected the Windows Autopilot Deployment Program for your organization</span></span>

<span data-ttu-id="df589-137">Windows Autopilot 구성이 완료되면 다음에 대한 OOBE(첫 실행 경험)을 위해 Windows 10 Enterprise를 구성하고 사용자 지정하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df589-137">Once the Windows Autopilot configuration is in place, you can use it to configure and customize Windows 10 Enterprise for the out-of-the-box experience (OOBE) for:</span></span>

- <span data-ttu-id="df589-138">새 장치</span><span class="sxs-lookup"><span data-stu-id="df589-138">New devices</span></span>
- <span data-ttu-id="df589-139">조직에서 기본 설치가 이미 완료된 장치</span><span class="sxs-lookup"><span data-stu-id="df589-139">Devices that have already completed an out-of-box setup in your organization.</span></span> 

<span data-ttu-id="df589-140">Windows Autopilot은 해당 장치를 구성하고 Azure AD에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="df589-140">Windows Autopilot configures the device and connects it to Azure AD.</span></span>

<span data-ttu-id="df589-141">Windows Autopilot이 없으면 Azure AD 연결하는 작업을 비롯하여 새 장치를 수동으로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df589-141">Without Windows Autopilot, you must manually configure new devices, including the connection to Azure AD.</span></span>

<span data-ttu-id="df589-142">필요한 경우 [3단계](windows10-deploy-autopilot.md)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df589-142">If needed, [Step 3](windows10-deploy-autopilot.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a><span data-ttu-id="df589-143">선택적 작업: Windows Analytics 장치 상태를 사용하여 Windows 10 Enterprise 기반 장치 모니터링</span><span class="sxs-lookup"><span data-stu-id="df589-143">Optional: You are using Windows Analytics Device Health to monitor your Windows 10 Enterprise-based devices</span></span>

<span data-ttu-id="df589-p104">“장치 상태 기능을 통해 장치의 상태 모니터링”의 정보를 사용하여 최종 사용자에게 영향을 주는 문제 감지 및 수정. 최종 사용자 문제를 빠르게 처리하면 지원 비용이 절감되고, Windows 10 Enterprise 채택에 대한 IT 부서 노력을 보여 줌으로써 조직 전체의 채택에 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df589-p104">You used the information in Monitor the health of devices with Device Health to detect and remediate issues affecting end users. Quickly addressing end-user issues can reduce your support costs and demonstrate to your users the IT commitment to Windows 10 Enterprise, which can help drive adoption across your organization.</span></span> 

<span data-ttu-id="df589-146">필요한 경우 [4단계](windows10-enable-windows-analytics.md)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df589-146">If needed, [Step 4](windows10-enable-windows-analytics.md) can help you with this option.</span></span>

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a><span data-ttu-id="df589-147">필수 작업: Windows Defender 바이러스 백신 또는 맬웨어 방지 솔루션 사용</span><span class="sxs-lookup"><span data-stu-id="df589-147">Required: You are using Windows Defender Antivirus or your own antimalware solution</span></span>

<span data-ttu-id="df589-p105">Windows Defender 바이러스 백신 또는 자신의 바이러스 백신 솔루션을 배포하여 Windows 10 Enterprise 실행 장치를 악성 소프트웨어로부터 보호. Windows Defender 바이러스 백신를 배포한 경우, 바이러스 백신 이벤트 및 활동을 모니터링하기 위한 System Center Configuration Manager 또는 Microsoft Intune과 같은 보고 방법이 구현된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="df589-p105">You deployed Windows Defender Antivirus or your own antivirus solution to protect your devices running Windows 10 Enterprise from malicious software. If you deployed Windows Defender Antivirus, you have implemented a reporting method, such as System Center Configuration Manager or Microsoft Intune, to monitor antivirus events and activity.</span></span>

<span data-ttu-id="df589-150">필요한 경우 [5단계](windows10-enable-security-features.md#windows10-sec-av)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df589-150">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-av) can help you with this requirement.</span></span>

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a><span data-ttu-id="df589-151">필수 작업: Windows Defender Exploit Guard 사용</span><span class="sxs-lookup"><span data-stu-id="df589-151">Required: You are using Windows Defender Exploit Guard</span></span>

<span data-ttu-id="df589-152">Windows Defender Exploit Guard를 배포하여 Windows 10 Enterprise 실행 장치를 침입으로부터 보호하고 침입 이벤트 및 활동을 모니터링하기 위한 System Center Configuration Manager 또는 Microsoft Intune과 같은 보고 방법 구현</span><span class="sxs-lookup"><span data-stu-id="df589-152">You deployed Windows Defender Exploit Guard to protect your devices running Windows 10 Enterprise from intrusion and have implemented a reporting method, such as System Center Configuration Manager or Microsoft Intune, to monitor intrusion events and activity.</span></span>

<span data-ttu-id="df589-153">필요한 경우 [5단계](windows10-enable-security-features.md#windows10-sec-eg)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df589-153">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-eg) can help you with this requirement.</span></span>

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-windows-defender-advanced-threat-protection-microsoft-365-enterprise-e5-only"></a><span data-ttu-id="df589-154">필수 작업: Windows Defender Advanced Threat Protection 사용(Microsoft 365 Enterprise E5만 해당)</span><span class="sxs-lookup"><span data-stu-id="df589-154">Required: You are using Windows Defender Advanced Threat Protection (Microsoft 365 Enterprise E5 only)</span></span>

<span data-ttu-id="df589-155">Windows Defender ATP(Advanced Threat Protection)를 배포하여 네트워크 및 Windows 10 Enterprise 실행 장치에 대한 고급 위협 감지, 조사, 대응</span><span class="sxs-lookup"><span data-stu-id="df589-155">You deployed Windows Defender Advanced Threat Protection (ATP) to detect, investigate, and respond to advanced threats against your network and devices running Windows 10 Enterprise.</span></span> 

<span data-ttu-id="df589-156">필요에 따라 다른 도구에 Windows Defender ATP를 통합하여 기능 확장</span><span class="sxs-lookup"><span data-stu-id="df589-156">Optionally, you have integrated Windows Defender ATP with other tools to expand its capabilities.</span></span>

<span data-ttu-id="df589-157">필요한 경우 [5단계](windows10-enable-security-features.md#windows10-sec-atp)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df589-157">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-atp) can help you with this requirement.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="df589-158">결과 및 다음 단계</span><span class="sxs-lookup"><span data-stu-id="df589-158">Validation and next steps</span></span>

<span data-ttu-id="df589-159">Windows 10 Enterprise 인프라는 새 디바이스에서는 설치를 시작하고, 이전 버전의 Windows에서 실행되는 디바이스에서는 현재 위치 업그레이드를 실행할 준비가 되며, 사용자는 Windows 10 Enterprise의 주요 보안 기능을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df589-159">Your Windows 10 Enterprise infrastructure is ready to begin installation on new devices and upgrades-in-place on devices running previous versions of Windows, and you are using the key security features of Windows 10 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| <span data-ttu-id="df589-160">Microsoft 365 Enterprise의 종단 간 배포 단계를 수행 중인 경우 다음 단계는 [Office 365 ProPlus](office365proplus-infrastructure.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="df589-160">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Office 365 ProPlus](office365proplus-infrastructure.md).</span></span> |
