---
title: Microsoft 365에 위협 방지 기능 배포
description: Microsoft 365 E5의 위협 방지 서비스 및 보안에 대한 개요를 참조하세요.
keywords: 위협 방지, 보안, E5, 사이버 공격, 맬웨어, M365, 솔루션
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
audience: Admin
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 922e7b7ea8bceced7085af49485b3479a671d5cd
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599962"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365-e5"></a><span data-ttu-id="addb3-104">Microsoft 365 E5에 위협 방지 기능 배포</span><span class="sxs-lookup"><span data-stu-id="addb3-104">Deploy threat protection capabilities across Microsoft 365 E5</span></span>

<span data-ttu-id="addb3-105">[맬웨어](/windows/security/threat-protection/intelligence/understanding-malware)및 정교한 사이버 공격(예: 파일 없는 위협)은 일반적으로 발생합니다. [](/windows/security/threat-protection/intelligence/fileless-threats)</span><span class="sxs-lookup"><span data-stu-id="addb3-105">[Malware](/windows/security/threat-protection/intelligence/understanding-malware), and sophisticated cyberattacks, such as [fileless threats](/windows/security/threat-protection/intelligence/fileless-threats), are a common occurrence.</span></span> <span data-ttu-id="addb3-106">기업은 효과적인 IT 보안 기능으로 자신과 고객을 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-106">Businesses need to protect themselves and their customers with effective IT security capabilities.</span></span> <span data-ttu-id="addb3-107">사이버 공격은 신뢰 상실에서 재무적 위험, 비즈니스를 위협하는 다운타임 등 조직에 중요한 문제를 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-107">Cyberattacks can cause major problems for your organization, ranging from a loss of trust to financial woes, business-threatening downtime, and more.</span></span> <span data-ttu-id="addb3-108">위협으로부터 보호하는 것은 중요하지만 조직의 시간, 작업 및 리소스에 집중할 위치를 결정하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-108">Protecting against threats is important, but it can be challenging to determine where to focus your organization's time, effort, and resources.</span></span> 

<span data-ttu-id="addb3-109">Microsoft 보안 솔루션은 제품 및 서비스에 기본 제공되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-109">Microsoft security solutions are built into our products and services.</span></span> <span data-ttu-id="addb3-110">자동화 및 기계 학습 기능은 보안 팀의 부하를 줄여 올바른 항목이 해결될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-110">Automation and machine learning capabilities reduce the load on your security teams to make sure the right items are addressed.</span></span> <span data-ttu-id="addb3-111">또한 Microsoft 보안 솔루션의 강점은 지능형 보안 그래프에서 매일 수조 가지 신호를 [처리합니다.](/graph/security-concept-overview)</span><span class="sxs-lookup"><span data-stu-id="addb3-111">And the strength of Microsoft security solutions is built on trillions of signals we process every day in our [Intelligent Security Graph](/graph/security-concept-overview).</span></span> <span data-ttu-id="addb3-112">Microsoft 365 보안 솔루션에는 전자 메일, 데이터, 장치 및 ID 전반의 신호를 모아 조직에 대한 고급 위협 그림을 그릴 수 있는 솔루션인 [Microsoft 365 Defender가](../security/defender/microsoft-365-defender.md)포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-112">Microsoft 365 security solutions include [Microsoft 365 Defender](../security/defender/microsoft-365-defender.md), a solution that brings together signals across your email, data, devices, and identities to paint a picture of advanced threats against your organization.</span></span>

<span data-ttu-id="addb3-113">이 비디오를 시청하고 배포 프로세스에 대한 개요를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="addb3-113">Watch this video for an overview of the deployment process.</span></span>
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]


## <a name="threat-protection-in-microsoft-365-e5"></a><span data-ttu-id="addb3-114">Microsoft 365 E5의 위협 방지</span><span class="sxs-lookup"><span data-stu-id="addb3-114">Threat protection in Microsoft 365 E5</span></span>

<span data-ttu-id="addb3-115">[Microsoft 365 E5를](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) 사용하면 적응형 기본 제공 인텔리전스로 조직을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-115">[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) enables you to protect your organization with adaptive, built-in intelligence.</span></span> <span data-ttu-id="addb3-116">Microsoft 365 E5의 위협 방지 기능을 사용하여, 사내 및 클라우드 환경에서 고급 위협, 손상된 ID 및 악의적인 작업을 감지하고 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-116">With the threat protection features in Microsoft 365 E5, you can detect and investigate advanced threats, compromised identities, and malicious actions across your on-premises and cloud environment.</span></span>

<span data-ttu-id="addb3-117">Microsoft 365 E5에서는 위협 방지 기능이 기본적으로 통합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-117">In Microsoft 365 E5, threat protection capabilities are integrated by default.</span></span> <span data-ttu-id="addb3-118">각 기능의 신호는 위협을 감지하고 대응하는 전반적인 기능에 강도를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-118">Signals from each capability add strength to the overall ability to detect and respond to threats.</span></span> <span data-ttu-id="addb3-119">결합된 기능 집합은 비 Microsoft 제품 실행에 비해 조직, 특히 다국적 조직에 가장 적합한 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-119">The combined set of capabilities offers the best protection for organizations, especially multi-national organizations, compared to running non-Microsoft products.</span></span> <span data-ttu-id="addb3-120">다음 이미지는 이 문서에서 설명하는 Microsoft 365 E5의 위협 방지 서비스 및 기능을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-120">The following image depicts the threat protection services and capabilities in Microsoft 365 E5 that are described in this article.</span></span>

![Microsoft 365 Defender 개요](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

<span data-ttu-id="addb3-122">Microsoft 365 Defender는 신호와 데이터를 [통합된 Microsoft 365 보안 센터로 통합합니다.](/microsoft-365/security/defender/overview-security-center)</span><span class="sxs-lookup"><span data-stu-id="addb3-122">Microsoft 365 Defender brings the signals and data together into a [unified Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center).</span></span> 

![Microsoft 365 Defender 대시보드의 개념 그림](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

<span data-ttu-id="addb3-124">다음 그림에서는 이러한 개별 기능을 배포하는 데 권장되는 경로를 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-124">The following illustration depicts a recommended path for deploying these individual capabilities.</span></span> 

![M365 위협 방지 신호](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

|<span data-ttu-id="addb3-126">솔루션/기능</span><span class="sxs-lookup"><span data-stu-id="addb3-126">Solution/capabilities</span></span>  |<span data-ttu-id="addb3-127">설명</span><span class="sxs-lookup"><span data-stu-id="addb3-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="addb3-128">다단계 인증 및 조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="addb3-128">Multi-factor authentication and Conditional Access</span></span>     |<span data-ttu-id="addb3-129">손상된 ID 및 장치로부터 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-129">Protect against compromised identities and devices.</span></span> <span data-ttu-id="addb3-130">기본이기 때문에 이 보호로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-130">Begin with this protection because it's foundational.</span></span> <span data-ttu-id="addb3-131">이 지침에서 권장되는 구성에는 Azure AD ID 보호가 선행 구성으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-131">The configuration recommended in this guidance includes Azure AD Identity Protection as a prerequisite.</span></span>     |
|<span data-ttu-id="addb3-132">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="addb3-132">Microsoft Defender for Identity</span></span>     |  <span data-ttu-id="addb3-133">AD DS(Active Directory 도메인 서비스) 신호를 활용하여 조직에 대한 고급 위협, 손상된 ID 및 악의적인 내부자 작업을 식별, 감지 및 조사하는 클라우드 기반 보안 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-133">A cloud-based security solution that leverages your on-premises Active Directory Domain Services (AD DS) signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> <span data-ttu-id="addb3-134">다음으로 Microsoft Defender for Identity에 중점을 두는 이유는, 이 인프라가 사용자의 사내 및 클라우드 인프라를 보호하고, 종속성이나 선행 요구가 없는 것이고, 즉각적인 보안 이점을 제공할 수 있기 때문에 그 다음에 집중합니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-134">Focus on Microsoft Defender for Identity next because it protects your on-premises and cloud infrastructure, has no dependencies or prerequisites, and can provide immediate security benefits.</span></span> | 
|<span data-ttu-id="addb3-135">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="addb3-135">Microsoft Defender for Office 365</span></span>     | <span data-ttu-id="addb3-136">전자 메일 메시지, 링크(URL) 및 공동 작업 도구로 위협되는 악의적인 위협에 대해 조직을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-136">Safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> <span data-ttu-id="addb3-137">맬웨어, 피싱, 스푸핑 및 기타 공격 유형에 대한 보호.</span><span class="sxs-lookup"><span data-stu-id="addb3-137">Protections for malware, phishing, spoofing, and other attack types.</span></span> <span data-ttu-id="addb3-138">변경 제어, 현재 시스템에서 설정을 마이그레이션하는 등 배포하는 데 시간이 오래 걸릴 수 있기 때문에 Office 365용 Microsoft Defender를 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-138">Configuring Microsoft Defender for Office 365 is recommended next because change control, migrating settings from incumbent system, and other considerations can take longer to deploy.</span></span> <p><span data-ttu-id="addb3-139">**참고:** 모든 Office 365 구독(Exchange Online Protection)에 포함된 위협 방지 기능을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-139">**NOTE**: Make sure to configure the threat protection capabilities that are included in all Office 365 subscriptions (Exchange Online Protection).</span></span>       |
|<span data-ttu-id="addb3-140">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="addb3-140">Microsoft Defender for Endpoint</span></span>    | <span data-ttu-id="addb3-141">고급 위협을 방지, 감지, 조사 및 대응하는 데 도움이 되는 끝점 보호 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-141">An endpoint protection platform that helps prevent, detect, investigate, and respond to advanced threats.</span></span>  <span data-ttu-id="addb3-142">Endpoint용 Defender를 배포하는 데 시간이 걸릴 수 있지만 구성은 다른 기능과 병렬로 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-142">Defender for Endpoint can take some time to deploy, but configuration can be done in parallel with other capabilities.</span></span>   |
|<span data-ttu-id="addb3-143">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="addb3-143">Microsoft Cloud App Security</span></span>     |   <span data-ttu-id="addb3-144">검색, 조사 및 거버넌스를 위한 클라우드 액세스 보안 브로커입니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-144">A cloud access security broker for discovery, investigation, and governance.</span></span> <span data-ttu-id="addb3-145">Microsoft Cloud App Security를 초기에 사용하도록 설정하여 데이터 및 인사이트 수집을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-145">You can enable Microsoft Cloud App Security early to begin collecting data and insights.</span></span> <span data-ttu-id="addb3-146">SaaS 앱에 정보 및 기타 대상이 지정된 보호를 구현하는 데는 계획이 수반될 수 있으며 시간이 더 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-146">Implementing information and other targeted protection across your SaaS apps involves planning and can take more time.</span></span>       | 

> [!TIP]
> <span data-ttu-id="addb3-147">보안 팀이 여러 개 있는 조직에서는 이러한 기능을 동시에 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-147">Organizations who have multiple security teams can implement these capabilities in parallel.</span></span> 

## <a name="deploy-your-threat-protection-solution"></a><span data-ttu-id="addb3-148">위협 방지 솔루션 배포</span><span class="sxs-lookup"><span data-stu-id="addb3-148">Deploy your threat protection solution</span></span>

 <span data-ttu-id="addb3-149">다음 다이어그램은 위협 방지 기능을 배포하기 위한 높은 수준의 프로세스를 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-149">The following diagram illustrates the high-level process for deploying threat protection capabilities.</span></span> 

![위협 방지 기능 배포 프로세스](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

<span data-ttu-id="addb3-151">조직에서 최상의 보호를 사용할 수 있도록 다음 단계를 포함하는 프로세스로 보안 솔루션을 설정하고 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-151">To make sure your organization has the best protection possible, set up and deploy your security solution with a process that includes the following steps:</span></span>

1. [<span data-ttu-id="addb3-152">다단계 인증 및 조건부 액세스 정책 설정</span><span class="sxs-lookup"><span data-stu-id="addb3-152">Set up multi-factor authentication and Conditional Access policies</span></span>](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [<span data-ttu-id="addb3-153">ID에 맞게 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="addb3-153">Configure Microsoft Defender for Identity</span></span>](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [<span data-ttu-id="addb3-154">Microsoft 365 Defender 켜기</span><span class="sxs-lookup"><span data-stu-id="addb3-154">Turn on Microsoft 365 Defender</span></span>](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [<span data-ttu-id="addb3-155">Office 365용 Defender 구성</span><span class="sxs-lookup"><span data-stu-id="addb3-155">Configure Defender for Office 365</span></span>](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [<span data-ttu-id="addb3-156">끝점에 맞게 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="addb3-156">Configure Microsoft Defender for Endpoint</span></span>](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [<span data-ttu-id="addb3-157">Microsoft Cloud App Security 구성</span><span class="sxs-lookup"><span data-stu-id="addb3-157">Configure Microsoft Cloud App Security</span></span>](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [<span data-ttu-id="addb3-158">상태 모니터링 및 작업 수행</span><span class="sxs-lookup"><span data-stu-id="addb3-158">Monitor status and take actions</span></span>](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [<span data-ttu-id="addb3-159">사용자 교육</span><span class="sxs-lookup"><span data-stu-id="addb3-159">Train users</span></span>](deploy-threat-protection-configure.md#step-8-train-users)

<span data-ttu-id="addb3-160">위협 방지 기능을 병렬로 구성할 수 있으므로 여러 네트워크 보안 팀이 서로 다른 서비스를 담당하는 경우 조직의 보호 기능을 동시에 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="addb3-160">Your threat protection features can be configured in parallel, so if you have multiple network security teams responsible for different services, they can configure your organization’s protection features at the same time.</span></span>

## <a name="next-step"></a><span data-ttu-id="addb3-161">다음 단계</span><span class="sxs-lookup"><span data-stu-id="addb3-161">Next step</span></span>


![위협 방지 기능 배포 프로세스](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

<span data-ttu-id="addb3-163">Microsoft [365에서](deploy-threat-protection-configure.md) 위협 방지 기능 구성 진행</span><span class="sxs-lookup"><span data-stu-id="addb3-163">Proceed to [Configure threat protection capabilities across Microsoft 365](deploy-threat-protection-configure.md)</span></span>

