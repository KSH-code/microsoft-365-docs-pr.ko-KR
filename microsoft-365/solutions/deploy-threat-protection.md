---
title: Microsoft 365에 위협 방지 기능 배포
description: Microsoft 365 E5에 위협 방지 서비스 및 보안 기능을 배포하는 방법을 학습합니다.
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
ms.openlocfilehash: a2d758ca4628e4cd5f73e77d0d86946e350163c5
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50424110"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a><span data-ttu-id="c21e5-103">Microsoft 365에 위협 방지 기능 배포</span><span class="sxs-lookup"><span data-stu-id="c21e5-103">Deploy threat protection capabilities across Microsoft 365</span></span>

<span data-ttu-id="c21e5-104">[맬웨어](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)및 정교한 사이버 공격(예: 파일 없는 위협)은 일반적으로 발생합니다. [](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats)</span><span class="sxs-lookup"><span data-stu-id="c21e5-104">[Malware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware), and sophisticated cyberattacks, such as [fileless threats](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats), are a common occurrence.</span></span> <span data-ttu-id="c21e5-105">기업은 효과적인 IT 보안 기능으로 자신과 고객을 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-105">Businesses need to protect themselves and their customers with effective IT security capabilities.</span></span> <span data-ttu-id="c21e5-106">사이버 공격은 신뢰 상실에서 재무적 위험, 비즈니스를 위협하는 다운타임 등 조직에 중요한 문제를 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-106">Cyberattacks can cause major problems for your organization, ranging from a loss of trust to financial woes, business-threatening downtime, and more.</span></span> <span data-ttu-id="c21e5-107">위협으로부터 보호하는 것은 중요하지만 조직의 시간, 작업 및 리소스에 집중할 위치를 결정하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-107">Protecting against threats is important, but it can be challenging to determine where to focus your organization's time, effort, and resources.</span></span> 

<span data-ttu-id="c21e5-108">Microsoft 보안 솔루션은 제품 및 서비스에 기본 제공되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-108">Microsoft security solutions are built into our products and services.</span></span> <span data-ttu-id="c21e5-109">자동화 및 기계 학습 기능은 보안 팀의 부하를 줄여 올바른 항목이 해결될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-109">Automation and machine learning capabilities reduce the load on your security teams to make sure the right items are addressed.</span></span> <span data-ttu-id="c21e5-110">또한 Microsoft 보안 솔루션의 강점은 지능형 보안 그래프에서 매일 수조 가지 신호를 [처리합니다.](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph)</span><span class="sxs-lookup"><span data-stu-id="c21e5-110">And the strength of Microsoft security solutions is built on trillions of signals we process every day in our [Intelligent Security Graph](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph).</span></span> <span data-ttu-id="c21e5-111">Microsoft 365 보안 솔루션에는 전자 메일, 데이터, 장치 및 ID 전반의 신호를 모아 조직에 대한 고급 위협 그림을 그릴 수 있는 솔루션인 [Microsoft 365 Defender가](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-111">Microsoft 365 security solutions include [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection), a solution that brings together signals across your email, data, devices, and identities to paint a picture of advanced threats against your organization.</span></span>


<span data-ttu-id="c21e5-112">이 비디오를 시청하고 배포 프로세스에 대한 개요를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c21e5-112">Watch this video for an overview of the deployment process.</span></span>
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

>[!Note]
><span data-ttu-id="c21e5-113">이 비디오에서는 위협 방지 제품 및 기능의 이전 이름을 사용하지만 개념은 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-113">This video uses the previous names of threat protection products and features, but the concepts are the same.</span></span> <span data-ttu-id="c21e5-114">이 비디오에 대한 업데이트가 진행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-114">An update to this video is in progress.</span></span>
>

<span data-ttu-id="c21e5-115">이 문서를 위협 방지 솔루션을 구현하기 위한 가이드로 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c21e5-115">Use this article as a guide for implementing your threat protection solution.</span></span>

## <a name="threat-protection-in-microsoft-365-e5"></a><span data-ttu-id="c21e5-116">Microsoft 365 E5의 위협 방지</span><span class="sxs-lookup"><span data-stu-id="c21e5-116">Threat protection in Microsoft 365 E5</span></span>

<span data-ttu-id="c21e5-117">[Microsoft 365 E5를](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) 사용하면 적응형 기본 제공 인텔리전스로 조직을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-117">[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) enables you to protect your organization with adaptive, built-in intelligence.</span></span> <span data-ttu-id="c21e5-118">Microsoft 365 E5의 위협 방지 기능을 사용하여, 사내 및 클라우드 환경에서 고급 위협, 손상된 ID 및 악의적인 작업을 감지하고 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-118">With the threat protection features in Microsoft 365 E5, you can detect and investigate advanced threats, compromised identities, and malicious actions across your on-premises and cloud environment.</span></span>

<span data-ttu-id="c21e5-119">Microsoft 365 E5에서는 위협 방지 기능이 기본적으로 통합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-119">In Microsoft 365 E5, threat protection capabilities are integrated by default.</span></span> <span data-ttu-id="c21e5-120">각 기능의 신호는 위협을 감지하고 대응하는 전반적인 기능에 강도를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-120">Signals from each capability add strength to the overall ability to detect and respond to threats.</span></span> <span data-ttu-id="c21e5-121">결합된 기능 집합은 비 Microsoft 제품 실행에 비해 조직, 특히 다국적 조직에 가장 적합한 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-121">The combined set of capabilities offers the best protection for organizations, especially multi-national organizations, compared to running non-Microsoft products.</span></span> <span data-ttu-id="c21e5-122">다음 이미지는 이 문서에서 설명하는 Microsoft 365 E5의 위협 방지 서비스 및 기능을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-122">The following image depicts the threat protection services and capabilities in Microsoft 365 E5 that are described in this article.</span></span>

![Microsoft 365 Defender 개요](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

<span data-ttu-id="c21e5-124">Office 365용 Defender 기능을 배포하는 즉시 Microsoft 365 Defender를 켜서 신호와 데이터를 한 장소에 모을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-124">As soon as you deploy any of the Defender for Office 365 capabilities, you can turn on Microsoft 365 Defender, which brings the signals and data together into one place.</span></span> 

![Microsoft 365 Defender 대시보드의 개념 그림](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

<span data-ttu-id="c21e5-126">다음 그림에서는 이러한 개별 기능을 배포하는 데 권장되는 경로를 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-126">The following illustration depicts a recommended path for deploying these individual capabilities.</span></span> 

![M365 위협 방지 신호](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

|<span data-ttu-id="c21e5-128">솔루션/기능</span><span class="sxs-lookup"><span data-stu-id="c21e5-128">Solution/capabilities</span></span>  |<span data-ttu-id="c21e5-129">설명</span><span class="sxs-lookup"><span data-stu-id="c21e5-129">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="c21e5-130">다단계 인증 및 조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="c21e5-130">Multi-factor authentication and Conditional Access</span></span>     |<span data-ttu-id="c21e5-131">손상된 ID 및 장치로부터 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-131">Protect against compromised identities and devices.</span></span> <span data-ttu-id="c21e5-132">기본이기 때문에 이 보호로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-132">Begin with this protection because it's foundational.</span></span> <span data-ttu-id="c21e5-133">이 지침에서 권장되는 구성에는 Azure AD ID 보호가 선행 구성으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-133">The configuration recommended in this guidance includes Azure AD Identity Protection as a prerequisite.</span></span>     |
|<span data-ttu-id="c21e5-134">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c21e5-134">Microsoft Defender for Identity</span></span>     |  <span data-ttu-id="c21e5-135">AD DS(Active Directory 도메인 서비스) 신호를 활용하여 조직에 대한 고급 위협, 손상된 ID 및 악의적인 내부자 작업을 식별, 감지 및 조사하는 클라우드 기반 보안 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-135">A cloud-based security solution that leverages your on-premises Active Directory Domain Services (AD DS) signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> <span data-ttu-id="c21e5-136">다음으로 Microsoft Defender for Identity에 중점을 두는 이유는, 이 인프라가 사용자의 사내 및 클라우드 인프라를 보호하고, 종속성이나 선행 요구가 없는 것이고, 즉각적인 보안 이점을 제공할 수 있기 때문에 그 다음에 집중합니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-136">Focus on Microsoft Defender for Identity next because it protects your on-premises and cloud infrastructure, has no dependencies or prerequisites, and can provide immediate security benefits.</span></span> | 
|<span data-ttu-id="c21e5-137">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c21e5-137">Microsoft Defender for Office 365</span></span>     | <span data-ttu-id="c21e5-138">전자 메일 메시지, 링크(URL) 및 공동 작업 도구로 위협되는 악의적인 위협에 대해 조직을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-138">Safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> <span data-ttu-id="c21e5-139">맬웨어, 피싱, 스푸핑 및 기타 공격 유형에 대한 보호.</span><span class="sxs-lookup"><span data-stu-id="c21e5-139">Protections for malware, phishing, spoofing, and other attack types.</span></span> <span data-ttu-id="c21e5-140">변경 제어, 현재 시스템에서 설정을 마이그레이션하는 등 배포하는 데 시간이 오래 걸릴 수 있기 때문에 Office 365용 Microsoft Defender를 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-140">Configuring Microsoft Defender for Office 365 is recommended next because change control, migrating settings from incumbent system, and other considerations can take longer to deploy.</span></span> <br><br><span data-ttu-id="c21e5-141">참고: 모든 Office 365 구독(Exchange Online Protection)에 포함된 위협 방지 기능을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-141">Note: Make sure to configure the threat protection capabilities that are included in all Office 365 subscriptions (Exchange Online Protection).</span></span>       |
|<span data-ttu-id="c21e5-142">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c21e5-142">Microsoft Defender for Endpoint</span></span>    | <span data-ttu-id="c21e5-143">고급 위협을 방지, 감지, 조사 및 대응하는 데 도움이 되는 끝점 보호 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-143">An endpoint protection platform that helps prevent, detect, investigate, and respond to advanced threats.</span></span>  <span data-ttu-id="c21e5-144">Endpoint용 Defender를 배포하는 데 시간이 걸릴 수 있지만 구성은 다른 기능과 병렬로 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-144">Defender for Endpoint can take some time to deploy, but configuration can be done in parallel with other capabilities.</span></span>   |
|<span data-ttu-id="c21e5-145">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c21e5-145">Microsoft Cloud App Security</span></span>     |   <span data-ttu-id="c21e5-146">검색, 조사 및 거버넌스를 위한 클라우드 액세스 보안 브로커입니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-146">A cloud access security broker for discovery, investigation, and governance.</span></span> <span data-ttu-id="c21e5-147">Microsoft Cloud App Security를 초기에 사용하도록 설정하여 데이터 및 인사이트 수집을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-147">You can enable Microsoft Cloud App Security early to begin collecting data and insights.</span></span> <span data-ttu-id="c21e5-148">SaaS 앱에 정보 및 기타 대상이 지정된 보호를 구현하는 데는 계획이 수반될 수 있으며 시간이 더 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-148">Implementing information and other targeted protection across your SaaS apps involves planning and can take more time.</span></span>       | 

> [!TIP]
> <span data-ttu-id="c21e5-149">보안 팀이 여러 개 있는 조직에서는 이러한 기능을 동시에 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-149">Organizations with multiple security teams can implement these capabilities in parallel.</span></span>

## <a name="deploy-your-threat-protection-solution"></a><span data-ttu-id="c21e5-150">위협 방지 솔루션 배포</span><span class="sxs-lookup"><span data-stu-id="c21e5-150">Deploy your threat protection solution</span></span>

<span data-ttu-id="c21e5-151">조직에서 최상의 보호 기능을 사용할 수 있도록 다음 단계를 포함하기 위해 보안 솔루션을 설정하고 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-151">To make sure your organization has the best protection possible, set up and deploy your security solution to include the following steps:</span></span>

1. [<span data-ttu-id="c21e5-152">다단계 인증 및 조건부 액세스 정책 설정</span><span class="sxs-lookup"><span data-stu-id="c21e5-152">Set up multi-factor authentication and Conditional Access policies</span></span>](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [<span data-ttu-id="c21e5-153">ID에 맞게 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="c21e5-153">Configure Microsoft Defender for Identity</span></span>](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [<span data-ttu-id="c21e5-154">Microsoft 365 Defender 켜기</span><span class="sxs-lookup"><span data-stu-id="c21e5-154">Turn on Microsoft 365 Defender</span></span>](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [<span data-ttu-id="c21e5-155">Office 365용 Defender 구성</span><span class="sxs-lookup"><span data-stu-id="c21e5-155">Configure Defender for Office 365</span></span>](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [<span data-ttu-id="c21e5-156">끝점에 맞게 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="c21e5-156">Configure Microsoft Defender for Endpoint</span></span>](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [<span data-ttu-id="c21e5-157">Microsoft Cloud App Security 구성</span><span class="sxs-lookup"><span data-stu-id="c21e5-157">Configure Microsoft Cloud App Security</span></span>](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [<span data-ttu-id="c21e5-158">상태 모니터링 및 작업 수행</span><span class="sxs-lookup"><span data-stu-id="c21e5-158">Monitor status and take actions</span></span>](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [<span data-ttu-id="c21e5-159">사용자 교육</span><span class="sxs-lookup"><span data-stu-id="c21e5-159">Train users</span></span>](deploy-threat-protection-configure.md#step-8-train-users)

<span data-ttu-id="c21e5-160">위협 방지 기능을 병렬로 구성할 수 있으므로 여러 네트워크 보안 팀이 서로 다른 서비스를 담당하는 경우 조직의 보호 기능을 동시에 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-160">Your threat protection features can be configured in parallel, so if you have multiple network security teams responsible for different services, they can configure your organization’s protection features at the same time.</span></span> <span data-ttu-id="c21e5-161">다음 다이어그램은 위협 방지 기능을 배포하기 위한 높은 수준의 프로세스를 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c21e5-161">The following diagram illustrates the high-level process for deploying threat protection capabilities.</span></span> 

![위협 방지 기능 배포 프로세스](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png) 
