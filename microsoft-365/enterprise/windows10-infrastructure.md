---
title: Microsoft 365 Enterprise에 대 한 Windows 10 엔터프라이즈 인프라
description: Microsoft 365 Enterprise의 일부로 Pc에서 Windows 10 엔터프라이즈 배포에 필요한 단계에 대 한 고급 지침을 제공 합니다.
keywords: Microsoft 365, Microsoft 365 Enterprise Microsoft 365 설명서, Windows 10 엔터프라이즈 배포
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/18/2018
ms.author: greglin
ms.openlocfilehash: 80d7c1b56434647387b9c428ca07effdff929abf
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869723"
---
# <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="70c67-104">3단계: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="70c67-104">Phase 3: Windows 10 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

<span data-ttu-id="70c67-p101">Microsoft 365 Enterprise 많은 작업을 할 보안을 유지 하는 도구를 제공 하는 Windows 10 엔터프라이즈를 포함 합니다. Windows 10 엔터프라이즈:</span><span class="sxs-lookup"><span data-stu-id="70c67-p101">Microsoft 365 Enterprise includes Windows 10 Enterprise, which gives you the tools to do more and stay secure. Windows 10 Enterprise:</span></span>

- <span data-ttu-id="70c67-107">**간단 하 게 통합 되어** -오늘날 관리의 복잡성을 줄일 수 있도록 클라우드 기능 테스트 프로그램의 크기에 관계 없이 현대 IT 장치 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="70c67-107">**Is integrated for simplicity** - Harness the power of the cloud to help reduce the complexity of managing today's modern IT device environment, no matter the size.</span></span>
- <span data-ttu-id="70c67-108">**지능형 보안이** -는 것이 가장 안전한 Windows 릴리스 적이 하 고, 기능을 보다 효과적으로 함께 작동 하도록 설계 된 지능형 보안이 포함 된 조직을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c67-108">**Has intelligent security** - It's the most secure release of Windows ever, with intelligent security capabilities that are designed to work together to better protect your organization.</span></span>
- <span data-ttu-id="70c67-109">**창의 성과 더욱 원활 수 있도록** -잠금을 해제 하는 창의 성과 가장 생산적인 제공 하기 위해 더욱 원활 발생 하는 사용자와 선호 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="70c67-109">**Enables creativity and teamwork** - Unlocks creativity and teamwork to deliver the most productive experience that both users and IT will love.</span></span>

<span data-ttu-id="70c67-p102">Windows 10 운영 체제를 배포 하 고 조직에 적합 한 선택 다양 한 방법을 이해 해야 합니다. Microsoft 365 Enterprise 구독에 따라 밖에도 Windows 10 서비스 및 보안 기능을 최대한 활용 Windows 10을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c67-p102">You'll need to understand the different ways you can deploy the Windows 10 operating system and choose the right one for your organization. Depending on your Microsoft 365 Enterprise subscription, there are also Windows 10 services and security features that you'll need to configure to get the most out of Windows 10.</span></span>

<span data-ttu-id="70c67-112">이러한 전략적 비즈니스 시나리오를 수행할 수 있도록 Microsoft 365 Enterprise에 대 한 Windows 10:</span><span class="sxs-lookup"><span data-stu-id="70c67-112">Windows 10 enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="70c67-113">사용자가 조직에서 파일, 정보 및 아이디어를 검색하고, 공유하고, 진행하도록 지원하여 통합적인 지식 및 전문 정보 활용</span><span class="sxs-lookup"><span data-stu-id="70c67-113">Harness collective knowledge and expertise by empowering people to discover, share, and progress files, information, and ideas across your organization</span></span>
- <span data-ttu-id="70c67-114">유연한 작업 스타일을 유지하면서 어떤 장치를 사용하든 장소나 시간의 구애를 받지 않고 안전하게 더 많은 작업 처리</span><span class="sxs-lookup"><span data-stu-id="70c67-114">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="70c67-115">업계에서 인증된 방식으로 제어 및 가시성에 대한 전역 표준을 준수하여 안심하고 작업 가능</span><span class="sxs-lookup"><span data-stu-id="70c67-115">Provide peace-of-mind with controls and visibility for industry-verified conformity with global standards in compliance</span></span>
- <span data-ttu-id="70c67-116">사용자의 정보 보호 및 데이터 손실 위험 최소화</span><span class="sxs-lookup"><span data-stu-id="70c67-116">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="70c67-117">검색 및 외부 위협-모니터 보고서 보호 조직의 보안을 제공 하려면 신속 하 게 대처 하는 작업을 분석</span><span class="sxs-lookup"><span data-stu-id="70c67-117">Detect and protect against external threats --Monitor, report and analyze activity to react promptly to provide organizational security</span></span>
- <span data-ttu-id="70c67-118">사용자와 자신의 계정 보호</span><span class="sxs-lookup"><span data-stu-id="70c67-118">Protect your users and their accounts</span></span>
- <span data-ttu-id="70c67-119">개인 정보 보호 및 규정 준수로 조직이 GDPR(일반 데이터 보호 규정)을 준수하도록 지원</span><span class="sxs-lookup"><span data-stu-id="70c67-119">Support your organization with enhanced privacy and compliance to meet the General Data Protection Regulation (GDPR)</span></span>
- <span data-ttu-id="70c67-120">보안 위험을 줄이고 IT 효율성을 극대화하면서 데스크톱 소프트웨어 및 장치를 최신 상태로 유지</span><span class="sxs-lookup"><span data-stu-id="70c67-120">Get current and stay current on your desktop software and devices while reducing security risks and maximizing IT efficiency</span></span>

<span data-ttu-id="70c67-121">자세한 내용은 [Microsoft 365를 사용한 디지털 변환](http://transform.microsoft.com)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70c67-121">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

>[!Note]
><span data-ttu-id="70c67-122">Windows 10 Enterprise 및 Office 365 ProPlus를 함께 배포하고 [최신 데스크톱](https://www.microsoft.com/microsoft-365/modern-desktop)으로 전환하려면 [최신 데스크톱 배포 센터](http://aka.ms/howtoshift)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70c67-122">To deploy both Windows 10 Enterprise and Office 365 ProPlus together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](http://aka.ms/howtoshift).</span></span>
>

## <a name="windows-10-deployment"></a><span data-ttu-id="70c67-123">Windows 10 배포</span><span class="sxs-lookup"><span data-stu-id="70c67-123">Windows 10 deployment</span></span>

<span data-ttu-id="70c67-p103">여러 가지 방법으로 조직에 대 한 Windows 10 Enterprise를 배포할 수 있습니다. 여기에에 대해 중점적 방법을 구성할 수 있으며 이러한 현대 배포 시나리오를 통해 Windows 10 Enterprise 이미지를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c67-p103">There are multiple ways you can deploy Windows 10 Enterprise for your organization. Here, we'll focus on how you can configure and deploy a Windows 10 Enterprise image through these modern deployment scenarios.</span></span>

| <span data-ttu-id="70c67-126">배포 시나리오</span><span class="sxs-lookup"><span data-stu-id="70c67-126">Deployment scenario</span></span> | <span data-ttu-id="70c67-127">사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="70c67-127">When to use it</span></span> |
|:--- |:--- |
| [<span data-ttu-id="70c67-128">System Center Configuration Manager를 사용 하 여으로 전체 업그레이드</span><span class="sxs-lookup"><span data-stu-id="70c67-128">Using System Center Configuration Manager as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) | <span data-ttu-id="70c67-129">Windows 7을 업그레이드 해야 하거나 <a href="https://aka.ms/windows-10-release-information" target="_blank">현재 버전</a> 의 Windows 10 엔터프라이즈에 Windows 8.1 컴퓨터 및 컴퓨터에서 <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (현재 분기)</a>와 현재 관리 하는 경우이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c67-129">Select this option if you need to upgrade Windows 7 or Windows 8.1 computers to the <a href="https://aka.ms/windows-10-release-information" target="_blank">current version</a> of Windows 10 Enterprise and your computers are currently managed with <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (Current branch)</a>.</span></span> |
| [<span data-ttu-id="70c67-130">Windows 작업을 자동화할을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="70c67-130">Using Windows Autopilot</span></span>](windows10-deploy-autopilot.md) | <span data-ttu-id="70c67-p104">Windows 10 Enterprise, 1703 또는 나중에 미리 설치 된 버전을 포함 하는 새 Windows 컴퓨터를 설정 하는 경우이 옵션을 선택 합니다. 최종 사용자가 작업을 입력 하 여 원하는 구성을 사용 하 여 설치를 시작 되거나 계정 자격 증명을 학교 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70c67-p104">Select this option if you are setting up new Windows computers that have Windows 10 Enterprise, version 1703 or later pre-installed. End users will initiate setup using your desired configuration by entering their work or school account credentials.</span></span> |

<span data-ttu-id="70c67-p105">이러한 배포 시나리오는 조직의 요구 사항에 맞지 않는 하는 경우에 다른 시나리오에 대 한 설명 수 있으며 [Windows 10 배포 시나리오](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)에서 각각의 제한 사항 및 기능을 이해 수 있습니다. 사용자가 직접 <a href="https://aka.ms/planforwin10deployment" target="_blank">Windows 10 배포 계획을</a> 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c67-p105">If these deployment scenarios do not fit the needs of your organization, you can learn about other scenarios and understand the capabilities and limitations of each in [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). You can also <a href="https://aka.ms/planforwin10deployment" target="_blank">plan for Windows 10 deployment</a> on your own.</span></span>

<span data-ttu-id="70c67-135">이러한 문서와 함께 Windows 10에 대 한 자세한를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c67-135">You can learn more about Windows 10 with these articles:</span></span>

- [<span data-ttu-id="70c67-136">Microsoft 365 Enterprise 제품 페이지</span><span class="sxs-lookup"><span data-stu-id="70c67-136">Microsoft 365 Enterprise product page</span></span>](https://www.microsoft.com/microsoft-365/enterprise)
- [<span data-ttu-id="70c67-137">Windows 10</span><span class="sxs-lookup"><span data-stu-id="70c67-137">Windows 10</span></span>](https://docs.microsoft.com/windows/windows-10)
- [<span data-ttu-id="70c67-138">배포 및 Windows 10 업데이트</span><span class="sxs-lookup"><span data-stu-id="70c67-138">Deploy and update Windows 10</span></span>](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a><span data-ttu-id="70c67-139">추가 서비스 및 기능</span><span class="sxs-lookup"><span data-stu-id="70c67-139">Additional services and features</span></span>
<span data-ttu-id="70c67-140">Windows 10 엔터프라이즈 배포의 일부로, 이러한 추가 서비스 및 기능을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c67-140">As part of your deployment of Windows 10 Enterprise, you can add these additional services and features.</span></span>

### <a name="windows-analytics"></a><span data-ttu-id="70c67-141">Windows Analytics</span><span class="sxs-lookup"><span data-stu-id="70c67-141">Windows Analytics</span></span>

<span data-ttu-id="70c67-142">Windows 진단 데이터를 사용 하 여 작업의 효율성과 환경의 Windows 10 장치의 상태에 세부 정보 파악 하는데 도움이 되는 다양 하 고 이들 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="70c67-142">Windows uses diagnostics data to provide rich, actionable information to help you gain deep insights into operational efficiency and the health of Windows 10 devices in your environment.</span></span>

* <span data-ttu-id="70c67-143">업그레이드 준비-업그레이드 준비 Windows 10으로 이동 하 고 새 Windows 10 기능 업데이트를 통해 최신 상태를 유지 하는데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70c67-143">Upgrade Readiness - Upgrade Readiness will help you move to Windows 10 and stay current with new Windows 10 Feature Updates.</span></span> 
* <span data-ttu-id="70c67-144">IT 관리자가 모든 추가 인프라 요구 사항 없이 모든 Windows 10 장치를 전체적으로 볼 수 있는 업데이트 규정 준수-업데이트 준수 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="70c67-144">Update Compliance - Update Compliance is targeted to the IT admin who wants to gain a holistic view of all their Windows 10 devices, without any additional infrastructure requirements.</span></span>
* <span data-ttu-id="70c67-145">장치 상태-사전 검색 및 최종 사용자 영향을 받는 문제를 수정 하려면 장치 상태를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70c67-145">Device Health - You can use Device Health to proactively detect and remediate end-user impacting issues.</span></span>

<span data-ttu-id="70c67-146">자세한 내용은 [Windows 분석 개요 (영문)을](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="70c67-146">See [Windows Analytics Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) for more information.</span></span>

### <a name="windows-security"></a><span data-ttu-id="70c67-147">Windows 보안</span><span class="sxs-lookup"><span data-stu-id="70c67-147">Windows security</span></span>

<span data-ttu-id="70c67-p106">Windows 10 위협 으로부터, 도움말 장치로, 보안 및 액세스 제어를 도와줄를 보호 하는 기능을 제공 합니다. Windows 10과 함께 시작 부분에서 장치 오른쪽을 보호 하는 중요 한 보안 기능 얻을 수 있습니다. Microsoft 365 E3 비즈니스, Windows Defender 응용 프로그램 제어 및 Windows 정보 보호에 대 한 Windows Hello 등의 보안 기능을 추가합니다. Microsoft 365 e 5와 Microsoft 365 E3 보안 및 클라우드 기반 보안 기능 및 Windows Defender 고급 위협 보호에서 모든 보호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="70c67-p106">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control. With Windows 10, you get critical security features that protect your device right from the start. Microsoft 365 E3 adds security features such as Windows Hello for Business, Windows Defender Application Control, and Windows Information Protection. With Microsoft 365 E5, you get all the protection from Microsoft 365 E3 security plus cloud-based security features and Windows Defender Advanced Threat Protection.</span></span> 

<span data-ttu-id="70c67-152">Windows 10 Enterprise 및 배포, 관리, 구성 하는 방법 세 주요 보안 기능 문제해결에 대 한 get 지침 얻을 수 있는 보안 기능에 대 한 자세한 내용은 참조 하십시오. [5 단계: Windows 10 엔터프라이즈 배포 보안 기능](windows10-enable-security-features.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70c67-152">To learn more about the security features that you get with Windows 10 Enterprise and get guidance on how you can deploy, manage, configure, and troubleshoot three key ecurity features, see [Step 5: Deploy Windows 10 Enterprise security features](windows10-enable-security-features.md).</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="70c67-153">Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법</span><span class="sxs-lookup"><span data-stu-id="70c67-153">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="70c67-154">Microsoft 내의 내밀기 고 회사를에 대 한 계획, 배포 및 Windows 10에 대 한 업데이트를 관리 하는 방법에 대해 알아봅니다 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="70c67-154">To peek inside Microsoft and learn how the company planned for, deployed, and is managing updates for Windows 10, see:</span></span>

- [<span data-ttu-id="70c67-155">조직의 원활한 Windows 10 배포 준비</span><span class="sxs-lookup"><span data-stu-id="70c67-155">Preparing your organization for a seamless Windows 10 deployment</span></span>](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [<span data-ttu-id="70c67-156">Microsoft에서 Windows를 서비스로 채택</span><span class="sxs-lookup"><span data-stu-id="70c67-156">Adopting Windows as a service at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [<span data-ttu-id="70c67-157">Microsoft의 Windows 10dmf 현재 위치 업그레이드 방식으로 배포</span><span class="sxs-lookup"><span data-stu-id="70c67-157">Deploying Windows 10 at Microsoft as an in-place upgrade</span></span>](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [<span data-ttu-id="70c67-158">비즈니스용 Windows Hello를 통해 강력한 사용자 인증 구현</span><span class="sxs-lookup"><span data-stu-id="70c67-158">Implementing strong user authentication with Windows Hello for Business</span></span>](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- <span data-ttu-id="70c67-159">[Windows 10 배포: Microsoft IT의 팀과 트릭](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT)(비디오)</span><span class="sxs-lookup"><span data-stu-id="70c67-159">[Windows 10 deployment: tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)</span></span>
- [<span data-ttu-id="70c67-160">Windows Defender ATP로 정교한 위협 감지 지원</span><span class="sxs-lookup"><span data-stu-id="70c67-160">Windows Defender ATP helps detect sophisticated threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- <span data-ttu-id="70c67-161">[Windows Defender 및 Windows Defender ATP로 최신 엔터프라이즈 보안 유지](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP)(비디오)</span><span class="sxs-lookup"><span data-stu-id="70c67-161">[Securing the modern enterprise with Windows Defender and Windows Defender ATP](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (video)</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="70c67-162">Contoso의 Microsoft 365 Enterprise 사용 방식</span><span class="sxs-lookup"><span data-stu-id="70c67-162">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="70c67-163">Contoso Corporation, 가상의 하지만 전형적인 다국적 비즈니스, [Windows 10 Enterprise를 배포](contoso-win10.md)하는 방법을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="70c67-163">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Windows 10 Enterprise](contoso-win10.md).</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="70c67-164">다음 단계</span><span class="sxs-lookup"><span data-stu-id="70c67-164">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="70c67-165">Windows 10 Enterprise에 대 한 조직 준비</span><span class="sxs-lookup"><span data-stu-id="70c67-165">Prepare your organization for Windows 10 Enterprise</span></span>](windows10-prepare-your-org.md) |
