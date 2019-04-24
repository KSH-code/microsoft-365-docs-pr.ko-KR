---
title: Microsoft 365 enterprise 용 Windows 10 enterprise 인프라
description: Microsoft 365 enterprise의 일부로 pc에 Windows 10 Enterprise를 배포 하는 데 필요한 단계에 대 한 간략 한 지침을 제공 합니다.
keywords: microsoft 365, microsoft 365 Enterprise, microsoft 365 설명서, Windows 10 Enterprise, 배포
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/18/2018
ms.author: greglin
ms.openlocfilehash: 88517c6b8de95c54ee9a2e47d4545266eb198249
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289441"
---
# <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="1491f-104">3단계: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1491f-104">Phase 3: Windows 10 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

<span data-ttu-id="1491f-105">Microsoft 365 enterprise에는 더 많은 작업을 수행 하 고 보안을 유지 하는 도구를 제공 하는 Windows 10 enterprise가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-105">Microsoft 365 Enterprise includes Windows 10 Enterprise, which gives you the tools to do more and stay secure.</span></span> <span data-ttu-id="1491f-106">Windows 10 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="1491f-106">Windows 10 Enterprise:</span></span>

- <span data-ttu-id="1491f-107">**는 간단한 기능을 위해 통합 되어** 오늘 최신 IT 장치 환경을 관리 하는 복잡성을 줄이는 데 도움을 줄 수 있습니다 (크기에 관계 없음).</span><span class="sxs-lookup"><span data-stu-id="1491f-107">**Is integrated for simplicity** - Harness the power of the cloud to help reduce the complexity of managing today's modern IT device environment, no matter the size.</span></span>
- <span data-ttu-id="1491f-108">**지능형 보안** 기능을 사용 하는 것이 가장 안전한 Windows 릴리스가 며, 함께 작동 하도록 설계 된 지능형 보안 기능을 통해 조직을 보다 효율적으로 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-108">**Has intelligent security** - It's the most secure release of Windows ever, with intelligent security capabilities that are designed to work together to better protect your organization.</span></span>
- <span data-ttu-id="1491f-109">**팀 작업** 및 팀 작업의 향상 된 기능을 사용 하 여 사용자와 공동으로 작업할 수 있는 가장 생산적인 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-109">**Enables creativity and teamwork** - Unlocks creativity and teamwork to deliver the most productive experience that both users and IT will love.</span></span>

<span data-ttu-id="1491f-110">Windows 10 운영 체제를 배포 하 고 조직에 적합 한 시스템을 선택할 수 있는 다양 한 방법을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-110">You'll need to understand the different ways you can deploy the Windows 10 operating system and choose the right one for your organization.</span></span> <span data-ttu-id="1491f-111">Microsoft 365 Enterprise 구독에 따라 windows 10 서비스 및 보안 기능을 구성 하는 데 필요한 windows 10 서비스가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-111">Depending on your Microsoft 365 Enterprise subscription, there are also Windows 10 services and security features that you'll need to configure to get the most out of Windows 10.</span></span>

<span data-ttu-id="1491f-112">Windows 10에서는 Microsoft 365 Enterprise에 대 한 다음과 같은 전략적 비즈니스 시나리오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-112">Windows 10 enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="1491f-113">사용자가 조직에서 파일, 정보 및 아이디어를 검색하고, 공유하고, 진행하도록 지원하여 통합적인 지식 및 전문 정보 활용</span><span class="sxs-lookup"><span data-stu-id="1491f-113">Harness collective knowledge and expertise by empowering people to discover, share, and progress files, information, and ideas across your organization</span></span>
- <span data-ttu-id="1491f-114">유연한 작업 스타일을 유지하면서 어떤 장치를 사용하든 장소나 시간의 구애를 받지 않고 안전하게 더 많은 작업 처리</span><span class="sxs-lookup"><span data-stu-id="1491f-114">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="1491f-115">업계에서 인증된 방식으로 제어 및 가시성에 대한 전역 표준을 준수하여 안심하고 작업 가능</span><span class="sxs-lookup"><span data-stu-id="1491f-115">Provide peace-of-mind with controls and visibility for industry-verified conformity with global standards in compliance</span></span>
- <span data-ttu-id="1491f-116">사용자의 정보 보호 및 데이터 손실 위험 최소화</span><span class="sxs-lookup"><span data-stu-id="1491f-116">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="1491f-117">외부 위협에 대 한 감지 및 보호--조직 보안을 제공 하기 위한 신속한 대응 활동을 모니터링 하 고 보고서를 작성 하 고 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-117">Detect and protect against external threats --Monitor, report and analyze activity to react promptly to provide organizational security</span></span>
- <span data-ttu-id="1491f-118">사용자 및 계정 보호</span><span class="sxs-lookup"><span data-stu-id="1491f-118">Protect your users and their accounts</span></span>
- <span data-ttu-id="1491f-119">개인 정보 보호 및 규정 준수로 조직이 GDPR(일반 데이터 보호 규정)을 준수하도록 지원</span><span class="sxs-lookup"><span data-stu-id="1491f-119">Support your organization with enhanced privacy and compliance to meet the General Data Protection Regulation (GDPR)</span></span>
- <span data-ttu-id="1491f-120">보안 위험을 줄이고 IT 효율성을 극대화하면서 데스크톱 소프트웨어 및 장치를 최신 상태로 유지</span><span class="sxs-lookup"><span data-stu-id="1491f-120">Get current and stay current on your desktop software and devices while reducing security risks and maximizing IT efficiency</span></span>

<span data-ttu-id="1491f-121">자세한 내용은 [Microsoft 365를 사용한 디지털 변환](http://transform.microsoft.com)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1491f-121">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

>[!Note]
><span data-ttu-id="1491f-122">Windows 10 Enterprise 및 Office 365 ProPlus를 함께 배포하고 [최신 데스크톱](https://www.microsoft.com/microsoft-365/modern-desktop)으로 전환하려면 [최신 데스크톱 배포 센터](http://aka.ms/howtoshift)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1491f-122">To deploy both Windows 10 Enterprise and Office 365 ProPlus together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](http://aka.ms/howtoshift).</span></span>
>

## <a name="windows-10-deployment"></a><span data-ttu-id="1491f-123">Windows 10 배포</span><span class="sxs-lookup"><span data-stu-id="1491f-123">Windows 10 deployment</span></span>

<span data-ttu-id="1491f-124">조직에 Windows 10 Enterprise를 배포 하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-124">There are multiple ways you can deploy Windows 10 Enterprise for your organization.</span></span> <span data-ttu-id="1491f-125">여기서는 이러한 최신 배포 시나리오를 통해 Windows 10 Enterprise 이미지를 구성 및 배포 하는 방법에 대해 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-125">Here, we'll focus on how you can configure and deploy a Windows 10 Enterprise image through these modern deployment scenarios.</span></span>

| <span data-ttu-id="1491f-126">배포 시나리오</span><span class="sxs-lookup"><span data-stu-id="1491f-126">Deployment scenario</span></span> | <span data-ttu-id="1491f-127">사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="1491f-127">When to use it</span></span> |
|:--- |:--- |
| [<span data-ttu-id="1491f-128">현재 위치 업그레이드로 System Center Configuration Manager 사용</span><span class="sxs-lookup"><span data-stu-id="1491f-128">Using System Center Configuration Manager as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) | <span data-ttu-id="1491f-129">windows 7 또는 windows 8.1 컴퓨터를 <a href="https://aka.ms/windows-10-release-information" target="_blank">현재 버전</a> 의 windows 10 Enterprise로 업그레이드 해야 하 고 컴퓨터가 현재 <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (현재 분기)</a>를 사용 하 여 관리 되는 경우이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-129">Select this option if you need to upgrade Windows 7 or Windows 8.1 computers to the <a href="https://aka.ms/windows-10-release-information" target="_blank">current version</a> of Windows 10 Enterprise and your computers are currently managed with <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (Current branch)</a>.</span></span> |
| [<span data-ttu-id="1491f-130">Windows Autopilot 사용</span><span class="sxs-lookup"><span data-stu-id="1491f-130">Using Windows Autopilot</span></span>](windows10-deploy-autopilot.md) | <span data-ttu-id="1491f-131">windows 10 Enterprise, 버전 1703 이상 사전 설치 된 새 Windows 컴퓨터를 설정 하는 경우이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-131">Select this option if you are setting up new Windows computers that have Windows 10 Enterprise, version 1703 or later pre-installed.</span></span> <span data-ttu-id="1491f-132">최종 사용자는 회사 또는 학교 계정 자격 증명을 입력 하 여 원하는 구성을 사용 하 여 설치 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-132">End users will initiate setup using your desired configuration by entering their work or school account credentials.</span></span> |

<span data-ttu-id="1491f-133">이러한 배포 시나리오가 조직의 요구 사항에 적합 하지 않은 경우에는 다른 시나리오에 대해 알아보고 [Windows 10 배포 시나리오](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)에서 각각의 기능과 제한 사항을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-133">If these deployment scenarios do not fit the needs of your organization, you can learn about other scenarios and understand the capabilities and limitations of each in [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="1491f-134">또한 직접 <a href="https://aka.ms/planforwin10deployment" target="_blank">Windows 10 배포를 계획할</a> 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-134">You can also <a href="https://aka.ms/planforwin10deployment" target="_blank">plan for Windows 10 deployment</a> on your own.</span></span>

<span data-ttu-id="1491f-135">다음 문서를 사용 하 여 Windows 10에 대 한 자세한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-135">You can learn more about Windows 10 with these articles:</span></span>

- [<span data-ttu-id="1491f-136">Microsoft 365 Enterprise 제품 페이지</span><span class="sxs-lookup"><span data-stu-id="1491f-136">Microsoft 365 Enterprise product page</span></span>](https://www.microsoft.com/microsoft-365/enterprise)
- [<span data-ttu-id="1491f-137">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1491f-137">Windows 10</span></span>](https://docs.microsoft.com/windows/windows-10)
- [<span data-ttu-id="1491f-138">Windows 10 배포 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="1491f-138">Deploy and update Windows 10</span></span>](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a><span data-ttu-id="1491f-139">추가 서비스 및 기능</span><span class="sxs-lookup"><span data-stu-id="1491f-139">Additional services and features</span></span>
<span data-ttu-id="1491f-140">Windows 10 Enterprise 배포의 일환으로 이러한 추가 서비스와 기능을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-140">As part of your deployment of Windows 10 Enterprise, you can add these additional services and features.</span></span>

### <a name="windows-analytics"></a><span data-ttu-id="1491f-141">Windows Analytics</span><span class="sxs-lookup"><span data-stu-id="1491f-141">Windows Analytics</span></span>

<span data-ttu-id="1491f-142">windows는 진단 데이터를 사용 하 여 사용자 환경에서 windows 10 장치의 운영 효율성과 상태를 심층적으로 파악할 수 있도록 다양 한 작업 가능 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-142">Windows uses diagnostics data to provide rich, actionable information to help you gain deep insights into operational efficiency and the health of Windows 10 devices in your environment.</span></span>

* <span data-ttu-id="1491f-143">업그레이드 준비 상태-업그레이드 준비 상태는 windows 10으로 이동 하 고 새로운 windows 10 기능 업데이트를 최신 상태로 유지 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-143">Upgrade Readiness - Upgrade Readiness will help you move to Windows 10 and stay current with new Windows 10 Feature Updates.</span></span> 
* <span data-ttu-id="1491f-144">업데이트 준수-업데이트 준수는 추가 인프라 요구 사항 없이 모든 Windows 10 장치를 전체적으로 확인 하려는 IT 관리자를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-144">Update Compliance - Update Compliance is targeted to the IT admin who wants to gain a holistic view of all their Windows 10 devices, without any additional infrastructure requirements.</span></span>
* <span data-ttu-id="1491f-145">장치 상태-장치 상태를 사용 하 여 최종 사용자에 게 영향을 주는 문제를 사전에 검색 하 고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-145">Device Health - You can use Device Health to proactively detect and remediate end-user impacting issues.</span></span>

<span data-ttu-id="1491f-146">자세한 내용은 [Windows 분석 개요](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1491f-146">See [Windows Analytics Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) for more information.</span></span>

### <a name="windows-security"></a><span data-ttu-id="1491f-147">Windows 보안</span><span class="sxs-lookup"><span data-stu-id="1491f-147">Windows security</span></span>

<span data-ttu-id="1491f-148">Windows 10에서는 위협 으로부터 보호 하 고, 장치를 보호 하 고, 액세스 제어에 도움을 주는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-148">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control.</span></span> <span data-ttu-id="1491f-149">Windows 10을 사용 하는 경우 시작에서 바로 장치를 보호 하는 중요 한 보안 기능을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-149">With Windows 10, you get critical security features that protect your device right from the start.</span></span> <span data-ttu-id="1491f-150">Microsoft 365 E3 windows Hello for Business, windows Defender Application Control 및 Windows Information Protection과 같은 보안 기능을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-150">Microsoft 365 E3 adds security features such as Windows Hello for Business, Windows Defender Application Control, and Windows Information Protection.</span></span> <span data-ttu-id="1491f-151">microsoft 365 E5를 사용 하면 microsoft 365 E3 보안의 모든 보호 기능과 클라우드 기반 보안 기능 및 Windows Defender Advanced Threat protection이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1491f-151">With Microsoft 365 E5, you get all the protection from Microsoft 365 E3 security plus cloud-based security features and Windows Defender Advanced Threat Protection.</span></span> 

<span data-ttu-id="1491f-152">windows 10 enterprise에서 제공 하는 보안 기능에 대 한 자세한 내용을 알아보고 3 가지 주요 ecurity 기능을 배포, 관리, 구성 및 문제를 해결 하는 방법에 대 한 지침을 확인 하려면 [5 단계: Windows 10 Enterprise 보안 기능 배포](windows10-enable-security-features.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1491f-152">To learn more about the security features that you get with Windows 10 Enterprise and get guidance on how you can deploy, manage, configure, and troubleshoot three key ecurity features, see [Step 5: Deploy Windows 10 Enterprise security features](windows10-enable-security-features.md).</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="1491f-153">Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법</span><span class="sxs-lookup"><span data-stu-id="1491f-153">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="1491f-154">Microsoft 내부를 살펴보고 회사에서 Windows 10 용 업데이트를 계획, 배포 및 관리 하는 방법을 알아보려면 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1491f-154">To peek inside Microsoft and learn how the company planned for, deployed, and is managing updates for Windows 10, see:</span></span>

- [<span data-ttu-id="1491f-155">조직의 원활한 Windows 10 배포 준비</span><span class="sxs-lookup"><span data-stu-id="1491f-155">Preparing your organization for a seamless Windows 10 deployment</span></span>](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [<span data-ttu-id="1491f-156">Microsoft에서 Windows를 서비스로 채택</span><span class="sxs-lookup"><span data-stu-id="1491f-156">Adopting Windows as a service at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [<span data-ttu-id="1491f-157">Microsoft의 Windows 10dmf 현재 위치 업그레이드 방식으로 배포</span><span class="sxs-lookup"><span data-stu-id="1491f-157">Deploying Windows 10 at Microsoft as an in-place upgrade</span></span>](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [<span data-ttu-id="1491f-158">비즈니스용 Windows Hello를 통해 강력한 사용자 인증 구현</span><span class="sxs-lookup"><span data-stu-id="1491f-158">Implementing strong user authentication with Windows Hello for Business</span></span>](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- <span data-ttu-id="1491f-159">[Windows 10 배포: Microsoft IT의 팀과 트릭](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT)(비디오)</span><span class="sxs-lookup"><span data-stu-id="1491f-159">[Windows 10 deployment: tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)</span></span>
- [<span data-ttu-id="1491f-160">Windows Defender ATP로 정교한 위협 감지 지원</span><span class="sxs-lookup"><span data-stu-id="1491f-160">Windows Defender ATP helps detect sophisticated threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- <span data-ttu-id="1491f-161">[Windows Defender 및 Windows Defender ATP로 최신 엔터프라이즈 보안 유지](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP)(비디오)</span><span class="sxs-lookup"><span data-stu-id="1491f-161">[Securing the modern enterprise with Windows Defender and Windows Defender ATP](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (video)</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="1491f-162">Contoso의 Microsoft 365 Enterprise 사용 방식</span><span class="sxs-lookup"><span data-stu-id="1491f-162">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="1491f-163">Contoso Corporation (가상의 대표적인 다국적 기업 비즈니스)과 [Windows 10 Enterprise를 배포](contoso-win10.md)하는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1491f-163">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Windows 10 Enterprise](contoso-win10.md).</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="1491f-164">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1491f-164">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="1491f-165">Windows 10 Enterprise에 대 한 조직 준비</span><span class="sxs-lookup"><span data-stu-id="1491f-165">Prepare your organization for Windows 10 Enterprise</span></span>](windows10-prepare-your-org.md) |
