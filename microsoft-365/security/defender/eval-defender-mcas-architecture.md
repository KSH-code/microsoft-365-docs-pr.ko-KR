---
title: 아키텍처 요구 사항 및 구성을 검토하고 Microsoft Cloud App Security 아키텍처의 프레임워크를 확인하여 구성 및 디자인을 Cloud App Security Microsoft 365 Defender
description: Microsoft Cloud App Security 다이어그램은 파일럿 환경을 구축하는 데 도움이 되는 Microsoft 365 Defender 아키텍처에 대해 설명합니다.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: a3fa9670262b90d1566c375680946a131bb9c78a
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458013"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-cloud-app-security"></a><span data-ttu-id="4f348-103">아키텍처 요구 사항 및 주요 개념을 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4f348-103">Review architecture requirements and key concepts for Microsoft Cloud App Security</span></span>


<span data-ttu-id="4f348-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="4f348-104">**Applies to:**</span></span>

- <span data-ttu-id="4f348-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4f348-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="4f348-106">이 문서는 [1단계 중 3단계로,](eval-defender-mcas-overview.md) 사용자 환경과 함께 Microsoft Cloud App Security 환경을 Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4f348-106">This article is [Step 1 of 3](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security alongside Microsoft 365 Defender.</span></span> <span data-ttu-id="4f348-107">이 프로세스에 대한 자세한 내용은 개요 문서를 [참조하세요.](eval-defender-identity-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4f348-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="4f348-108">이 Microsoft Cloud App Security 사용하도록 설정하기 전에 아키텍처를 이해하고 요구 사항을 충족할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-108">Before enabling Microsoft Cloud App Security, be sure you understand the architecture and can meet the requirements.</span></span> 

## <a name="understand-the-architecture"></a><span data-ttu-id="4f348-109">아키텍처 이해</span><span class="sxs-lookup"><span data-stu-id="4f348-109">Understand the architecture</span></span>

<span data-ttu-id="4f348-110">Microsoft Cloud App Security CASB(클라우드 액세스 보안 브로커)입니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-110">Microsoft Cloud App Security is a Cloud Access Security Broker (CASB).</span></span> <span data-ttu-id="4f348-111">CASB는 사용자가 어디에 있든 사용중인 디바이스에 관계없이 엔터프라이즈 사용자와 사용하는 클라우드 리소스 간에 실시간으로 액세스를 브로커하기 위한 게이트키퍼 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-111">CASBs act a gatekeeper to broker access in real time between your enterprise users and cloud resources they use, wherever your users are located and regardless of the device they are using.</span></span> <span data-ttu-id="4f348-112">Microsoft Cloud App Security Microsoft 보안 기능과 기본적으로 통합되어 있습니다( Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4f348-112">Microsoft Cloud App Security natively integrates with Microsoft security capabilities, including Microsoft 365 Defender.</span></span> 

<span data-ttu-id="4f348-113">이 Cloud App Security 없는 경우 조직에서 사용하는 클라우드 앱은 그림과 같은 관리되지 않고 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-113">Without Cloud App Security, cloud apps that are used by your organization are unmanaged and unprotected, as illustrated.</span></span>

![Microsoft Cloud App Security](../../media/defender/m365-defender-mcas-architecture-a.png)

<span data-ttu-id="4f348-115">이 그림의 내용</span><span class="sxs-lookup"><span data-stu-id="4f348-115">In the illustration:</span></span>
- <span data-ttu-id="4f348-116">조직에서 클라우드 앱을 사용하는 것은 원치 않는 것이고 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-116">The use of cloud apps by an organization is unmonitored and unprotected.</span></span> 
- <span data-ttu-id="4f348-117">이 사용은 관리되는 조직 내에서 달성된 보호 외부에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-117">This use falls outside the protections achieved within a managed organization.</span></span> 

#### <a name="discovering-cloud-apps"></a><span data-ttu-id="4f348-118">클라우드 앱 검색</span><span class="sxs-lookup"><span data-stu-id="4f348-118">Discovering cloud apps</span></span>

<span data-ttu-id="4f348-119">클라우드 앱 사용을 관리하는 첫 번째 단계는 조직에서 사용하는 클라우드 앱을 검색하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-119">The first step to managing the use of cloud apps is to discover which cloud apps are used by your organization.</span></span> <span data-ttu-id="4f348-120">다음 다이어그램은 클라우드 검색이 클라우드 검색에서 작동하는 Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="4f348-120">This next diagram illustrates how cloud discovery works with Cloud App Security.</span></span>

![Microsoft Cloud App Security 아키텍처 - 클라우드 검색](../../media/defender/m365-defender-mcas-architecture-b.png)

<span data-ttu-id="4f348-122">이 그림에는 네트워크 트래픽을 모니터링하고 조직에서 사용중인 클라우드 앱을 검색하는 데 사용할 수 있는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-122">In this illustration, there are two methods that can be used to monitor network traffic and discover cloud apps that are being used by your organization.</span></span>
- <span data-ttu-id="4f348-123">대답.</span><span class="sxs-lookup"><span data-stu-id="4f348-123">A.</span></span> <span data-ttu-id="4f348-124">Cloud App Discovery는 기본적으로 끝점용 Microsoft Defender와 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-124">Cloud App Discovery integrates with Microsoft Defender for Endpoint natively.</span></span> <span data-ttu-id="4f348-125">Endpoint용 Defender는 IT 관리 디바이스에서 액세스하는 클라우드 앱 및 Windows 10 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-125">Defender for Endpoint reports cloud apps and services being accessed from IT-managed Windows 10 devices.</span></span> 
- <span data-ttu-id="4f348-126">B.</span><span class="sxs-lookup"><span data-stu-id="4f348-126">B.</span></span> <span data-ttu-id="4f348-127">네트워크에 연결된 모든 디바이스에서 적용 범위를 위해 Cloud App Security 로그 수집기 및 끝점에서 데이터를 수집하기 위한 기타 proxies에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-127">For coverage on all devices connected to a network, the Cloud App Security log collector is installed on firewalls and other proxies to collect data from endpoints.</span></span> <span data-ttu-id="4f348-128">이 데이터는 분석을 위해 Cloud App Security 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-128">This data is sent to Cloud App Security for analysis.</span></span>

#### <a name="managing-cloud-apps"></a><span data-ttu-id="4f348-129">클라우드 앱 관리</span><span class="sxs-lookup"><span data-stu-id="4f348-129">Managing cloud apps</span></span>

<span data-ttu-id="4f348-130">클라우드 앱을 검색하고 조직에서 이러한 앱을 사용하는 방식의 동작을 분석한 후 선택한 클라우드 앱 관리를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-130">After you discover cloud apps and analyze the behavior of how these are used by your organization, you can begin managing cloud apps that you choose.</span></span> 

![비즈니스용 Microsoft Cloud App Security - 클라우드 앱 관리](../../media/defender/m365-defender-mcas-architecture-c.png)

<span data-ttu-id="4f348-132">이 그림에서는 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-132">In this illustration:</span></span>
- <span data-ttu-id="4f348-133">일부 앱은 사용이 제재됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-133">Some apps are sanctioned for use.</span></span> <span data-ttu-id="4f348-134">이는 앱을 관리하는 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-134">This is a simple way of beginning to manage apps.</span></span>
- <span data-ttu-id="4f348-135">앱을 앱 커넥터에 연결하여 가시성과 제어를 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-135">You can enable greater visibility and control by connecting apps with app connectors.</span></span> <span data-ttu-id="4f348-136">앱 커넥터는 앱 공급자의 API를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-136">App connectors use the APIs of app providers.</span></span>


#### <a name="applying-session-controls-to-cloud-apps"></a><span data-ttu-id="4f348-137">클라우드 앱에 세션 컨트롤 적용</span><span class="sxs-lookup"><span data-stu-id="4f348-137">Applying session controls to cloud apps</span></span>

<span data-ttu-id="4f348-138">Microsoft Cloud App Security 역방향 프록시 역할을 하여 인증된 클라우드 앱에 대한 프록시 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-138">Microsoft Cloud App Security serves as a reverse proxy, providing proxy access to sanctioned cloud apps.</span></span> <span data-ttu-id="4f348-139">이렇게 하면 Cloud App Security 세션 컨트롤을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-139">This allows Cloud App Security to apply session controls that you configure.</span></span> 

![Microsoft Cloud App Security 아키텍처 - 프록시 액세스 세션 제어](../../media/defender/m365-defender-mcas-architecture-d.png)

<span data-ttu-id="4f348-141">이 그림에서는 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-141">In this illustration:</span></span>
- <span data-ttu-id="4f348-142">조직의 사용자 및 장치에서 허용된 클라우드 앱에 대한 액세스는 사용자 및 디바이스를 통해 Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="4f348-142">Access to sanctioned cloud apps from users and devices in your organization is routed through Cloud App Security.</span></span>
- <span data-ttu-id="4f348-143">이 프록시 액세스를 사용하면 세션 컨트롤을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-143">This proxy access allows session controls to be applied.</span></span>
- <span data-ttu-id="4f348-144">제재를 받거나 명시적으로 사용되지 않은 클라우드 앱은 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-144">Cloud apps that you have not sanctioned or explicitly unsanctioned are not affected.</span></span>

<span data-ttu-id="4f348-145">세션 컨트롤을 사용하면 조직에서 클라우드 앱을 사용하는 방법에 매개 변수를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-145">Session controls allow you to apply parameters to how cloud apps are used by your organization.</span></span> <span data-ttu-id="4f348-146">예를 들어 조직에서 Salesforce를 사용하는 경우 관리되는 장치만 Salesforce에서 조직의 데이터에 액세스할 수 있도록 허용하는 세션 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-146">For example, if your organization is using Salesforce, you can configure a session policy that allows only managed devices to access your organization's data in Salesforce.</span></span> <span data-ttu-id="4f348-147">더 간단한 예는 더 엄격한 정책을 적용하기 전에 이 트래픽의 위험을 분석할 수 있도록 관리되지 않는 장치의 트래픽을 모니터링하는 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-147">A simpler example could be configuring a policy to monitor traffic from unmanaged devices so you can analyze the risk of this traffic before applying stricter policies.</span></span>

#### <a name="integrating-with-azure-ad-with-conditional-access-app-control"></a><span data-ttu-id="4f348-148">조건부 액세스 앱 컨트롤과 Azure AD 통합</span><span class="sxs-lookup"><span data-stu-id="4f348-148">Integrating with Azure AD with Conditional Access App Control</span></span>

<span data-ttu-id="4f348-149">다단계 인증 및 기타 조건부 액세스 정책을 적용하기 위해 Azure AD 테넌트에 SaaS 앱을 이미 추가한 상태일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-149">You might already have SaaS apps added to your Azure AD tenant to enforce multi-factor authentication and other conditional access policies.</span></span> <span data-ttu-id="4f348-150">Microsoft Cloud App Security Azure AD와 기본적으로 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-150">Microsoft Cloud App Security natively integrates with Azure AD.</span></span> <span data-ttu-id="4f348-151">Azure AD에서 조건부 액세스 앱 제어를 사용하도록 Azure AD에서 정책을 구성하기만 Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="4f348-151">All you have to do is configure a policy in Azure AD to use Conditional Access App Control in Cloud App Security.</span></span> <span data-ttu-id="4f348-152">이렇게 하면 이러한 관리되는 SaaS 앱에 대한 네트워크 트래픽이 Cloud App Security 프록시로 라우팅됩니다. 이 Cloud App Security 모니터링하고 세션 컨트롤을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-152">This routes network traffic for these managed SaaS apps through Cloud App Security as a proxy, which allows Cloud App Security to monitor this traffic and to apply session controls.</span></span> 

![Microsoft Cloud App Security 아키텍처 - SaaS 앱](../../media/defender/m365-defender-mcas-architecture-e.png)

<span data-ttu-id="4f348-154">이 그림에서는 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-154">In this illustration:</span></span>
- <span data-ttu-id="4f348-155">SaaS 앱은 Azure AD 테넌트와 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-155">SaaS apps are integrated with the Azure AD tenant.</span></span> <span data-ttu-id="4f348-156">이를 통해 Azure AD는 다단계 인증을 비롯한 조건부 액세스 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-156">This allows Azure AD to enforce conditional access policies, including multi-factor authentication.</span></span>
- <span data-ttu-id="4f348-157">SaaS 앱에 대한 Azure Active Directory 트래픽을 다른 앱으로 Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="4f348-157">A policy is added to Azure Active Directory to direct traffic for SaaS apps to Cloud App Security.</span></span> <span data-ttu-id="4f348-158">이 정책은 해당 정책을 적용할 SaaS 앱을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-158">The policy specifies which SaaS apps to apply this policy to.</span></span> <span data-ttu-id="4f348-159">따라서 Azure AD가 이러한 SaaS 앱에 적용되는 조건부 액세스 정책을 적용한 후 Azure AD는 해당 정책을 통해 세션 트래픽을 Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="4f348-159">Consequently, after Azure AD enforces any conditional access policies that apply to these SaaS apps, Azure AD then directs (proxies) the session traffic through Cloud App Security.</span></span>
- <span data-ttu-id="4f348-160">Cloud App Security 모니터링하고 관리자가 구성한 모든 세션 제어 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-160">Cloud App Security monitors this traffic and applies any session control policies that have been configured by administrators.</span></span> 

<span data-ttu-id="4f348-161">Azure AD에 추가되지 않은 클라우드 Cloud App Security 클라우드 앱을 검색하고 인가한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-161">You might have discovered and sanctioned cloud apps using Cloud App Security that have not been added to Azure AD.</span></span> <span data-ttu-id="4f348-162">이러한 클라우드 앱을 Azure AD 테넌트 및 조건부 액세스 규칙의 범위에 추가하여 조건부 액세스 앱 제어를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-162">You can take advantage of Conditional Access App Control by adding these cloud apps to your Azure AD tenant and the scope of your conditional access rules.</span></span>

#### <a name="protecting-your-organization-from-hackers"></a><span data-ttu-id="4f348-163">해커로부터 조직 보호</span><span class="sxs-lookup"><span data-stu-id="4f348-163">Protecting your organization from hackers</span></span>

<span data-ttu-id="4f348-164">Cloud App Security 자체적으로 강력한 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-164">Cloud App Security provides powerful protection on its own.</span></span> <span data-ttu-id="4f348-165">그러나 이 기능의 다른 기능과 Microsoft 365 Defender Cloud App Security 함께 공격을 중지하는 데 도움이 되는 공유 신호에 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-165">However, when combined with the other capabilities of Microsoft 365 Defender, Cloud App Security provides data into the shared signals which, together, helps stop attacks.</span></span>

<span data-ttu-id="4f348-166">이 그림을 개요에서 이 평가 및 파일럿 Microsoft 365 Defender 반복하는 것이 가치가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-166">It's worth repeating this illustration from the overview to this Microsoft 365 Defender evaluation and pilot guide.</span></span> 

![보안 Microsoft 365 Defender 체인을 중지하는 방법](../../media/defender/m365-defender-eval-threat-chain.png)

<span data-ttu-id="4f348-168">이 그림의 오른쪽에 중점을 두면 Microsoft Cloud App Security, 자격 증명 액세스, 비정상적인 다운로드, 파일 공유 또는 메일 전달 활동과 같은 비정상적인 동작을 발견하여 보안 팀에 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-168">Focusing on the right side of this illustration, Microsoft Cloud App Security notices anomalous behavior like impossible-travel, credential access, and unusual download, file share, or mail forwarding activity and reports these to the security team.</span></span> <span data-ttu-id="4f348-169">따라서 Cloud App Security 해커의 측면 이동 및 중요한 데이터 유출을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-169">Consequently, Cloud App Security helps prevent lateral movement by hackers and exfiltration of sensitive data.</span></span> <span data-ttu-id="4f348-170">Microsoft 356 Defender는 모든 구성 요소의 신호와 상관을 하여 전체 공격 스토리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-170">Microsoft 356 Defender correlates the signals from all the components to provide the full attack story.</span></span>

## <a name="understand-key-concepts"></a><span data-ttu-id="4f348-171">주요 개념 이해</span><span class="sxs-lookup"><span data-stu-id="4f348-171">Understand key concepts</span></span>

<span data-ttu-id="4f348-172">다음 표에서는 이러한 개념을 평가, 구성 및 배포할 때 이해해야 하는 주요 개념을 Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="4f348-172">The following table identified key concepts that are important to understand when evaluating, configuring, and deploying Microsoft Cloud App Security.</span></span>


|<span data-ttu-id="4f348-173">개념</span><span class="sxs-lookup"><span data-stu-id="4f348-173">Concept</span></span>  |<span data-ttu-id="4f348-174">설명</span><span class="sxs-lookup"><span data-stu-id="4f348-174">Description</span></span> |<span data-ttu-id="4f348-175">추가 정보</span><span class="sxs-lookup"><span data-stu-id="4f348-175">More information</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="4f348-176">Cloud App Security 대시보드</span><span class="sxs-lookup"><span data-stu-id="4f348-176">Cloud App Security Dashboard</span></span> | <span data-ttu-id="4f348-177">조직에 대한 가장 중요한 정보에 대한 개요를 제시하고 심층 조사에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-177">Presents an overview of the most important information about your organization and gives links to deeper investigation.</span></span>        | [<span data-ttu-id="4f348-178">대시보드 작업 </span><span class="sxs-lookup"><span data-stu-id="4f348-178">Working with the dashboard </span></span>](/cloud-app-security/daily-activities-to-protect-your-cloud-environment)       |
| <span data-ttu-id="4f348-179">조건부 액세스 앱 컨트롤</span><span class="sxs-lookup"><span data-stu-id="4f348-179">Conditional Access App Control</span></span>    | <span data-ttu-id="4f348-180">IdP(ID 공급자)와 통합되어 Azure AD 조건부 액세스 정책을 제공하고 선택적으로 세션 제어를 적용하는 역방향 프록시 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-180">Reverse proxy architecture that integrates with your Identity Provider (IdP) to give Azure AD conditional access policies and selectively enforce session controls.</span></span>        |  [<span data-ttu-id="4f348-181">조건부 액세스 Microsoft Cloud App Security 컨트롤을 사용하여 앱 보호</span><span class="sxs-lookup"><span data-stu-id="4f348-181">Protect apps with Microsoft Cloud App Security Conditional Access App Control</span></span>](/cloud-app-security/proxy-intro-aad)       |
|  <span data-ttu-id="4f348-182">Cloud App Catalog</span><span class="sxs-lookup"><span data-stu-id="4f348-182">Cloud App Catalog</span></span>   | <span data-ttu-id="4f348-183">Cloud App Catalog는 80개가 넘는 위험 요인을 기준으로 순위를 정하고 점수가 점수를 거는 16,000개가 넘는 클라우드 앱의 Microsoft 카탈로그에 대한 전체 그림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-183">The Cloud App Catalog gives you a full picture against Microsoft catalog of over 16,000 cloud apps that are ranked and scored based on more than 80 risk factors.</span></span>    |  [<span data-ttu-id="4f348-184">앱 위험 점수 작업</span><span class="sxs-lookup"><span data-stu-id="4f348-184">Working with App risk scores</span></span>](/cloud-app-security/risk-score)       |
| <span data-ttu-id="4f348-185">클라우드 검색 대시보드</span><span class="sxs-lookup"><span data-stu-id="4f348-185">Cloud Discovery Dashboard</span></span>    | <span data-ttu-id="4f348-186">클라우드 검색은 트래픽 로그를 분석하고 조직에서 클라우드 앱이 사용되는 방식에 대한 더 많은 정보를 제공하고 경고 및 위험 수준을 제공하도록 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-186">Cloud Discovery analyzes your traffic logs and is designed to give more insight into how cloud apps are being used in your organization as well as give alerts and risk levels.</span></span>     |  [<span data-ttu-id="4f348-187">검색된 앱 작업   </span><span class="sxs-lookup"><span data-stu-id="4f348-187">Working with discovered apps   </span></span>](/cloud-app-security/discovered-apps)    |
|<span data-ttu-id="4f348-188">연결된 앱</span><span class="sxs-lookup"><span data-stu-id="4f348-188">Connected Apps</span></span> |<span data-ttu-id="4f348-189">Cloud App Security 앱 액세스 제어를 활용하는 클라우드-클라우드 통합, API 커넥터 및 실시간 액세스 및 세션 컨트롤을 사용하여 연결된 앱에 대한 종단-종단으로 보호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-189">Cloud App Security provides end-to-end protection for connected apps using Cloud-to-Cloud integration, API connectors, and real-time access and session controls leveraging our Conditional App Access Controls.</span></span> |[<span data-ttu-id="4f348-190">연결된 앱 보호</span><span class="sxs-lookup"><span data-stu-id="4f348-190">Protecting connected apps</span></span>](/cloud-app-security/protect-connected-apps) |
| | | |

## <a name="review-architecture-requirements"></a><span data-ttu-id="4f348-191">아키텍처 요구 사항 검토</span><span class="sxs-lookup"><span data-stu-id="4f348-191">Review architecture requirements</span></span>

### <a name="discovering-cloud-apps"></a><span data-ttu-id="4f348-192">클라우드 앱 검색</span><span class="sxs-lookup"><span data-stu-id="4f348-192">Discovering cloud apps</span></span>

<span data-ttu-id="4f348-193">환경에서 사용되는 클라우드 앱을 검색하기 위해 다음 중 하나 또는 둘 다를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-193">To discover cloud apps used in your environment, you can do one or both of the following:</span></span>

- <span data-ttu-id="4f348-194">끝점용 Microsoft Defender와 통합하여 클라우드 검색을 빠르게 시작하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-194">Get up and running quickly with Cloud Discovery by integrating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="4f348-195">이 네이티브 통합을 통해 네트워크의 모든 디바이스에서 클라우드 트래픽에 Windows 10 즉시 데이터를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-195">This native integration enables you to immediately start collecting data on cloud traffic across your Windows 10 devices, on and off your network.</span></span>
- <span data-ttu-id="4f348-196">네트워크에 연결된 모든 장치에서 액세스하는 모든 클라우드 앱을 검색하려면 방화벽 및 기타 Cloud App Security 로그 수집기 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-196">To discover all cloud apps accessed by all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies.</span></span> <span data-ttu-id="4f348-197">그러면 끝점에서 데이터를 수집하여 분석하기 위해 Cloud App Security 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-197">This collects data from your endpoints and sends it to Cloud App Security for analysis.</span></span> <span data-ttu-id="4f348-198">Cloud App Security 기능을 위해 기본적으로 일부 타사 Proxies와 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-198">Cloud App Security natively integrates with some third-party proxies for even more capabilities.</span></span>

<span data-ttu-id="4f348-199">이러한 옵션은 [2단계에 포함되어 있습니다. 평가 환경 사용.](eval-defender-mcas-enable-eval.md)</span><span class="sxs-lookup"><span data-stu-id="4f348-199">These options are included in [Step 2. Enable the evaluation environment](eval-defender-mcas-enable-eval.md).</span></span> 

### <a name="applying-azure-ad-conditional-access-policies-to-cloud-apps"></a><span data-ttu-id="4f348-200">클라우드 앱에 Azure AD 조건부 액세스 정책 적용</span><span class="sxs-lookup"><span data-stu-id="4f348-200">Applying Azure AD Conditional Access policies to cloud apps</span></span>

<span data-ttu-id="4f348-201">조건부 액세스 앱 제어(클라우드 앱에 조건부 액세스 정책을 적용하는 기능)에는 Azure AD와 통합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-201">Conditional Access App Control (the ability to apply Conditional Access policies to cloud apps) requires integration with Azure AD.</span></span> <span data-ttu-id="4f348-202">이 설정은 2016년 8월에 시작해야 하는 Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="4f348-202">This isn't a requirement for getting started with Cloud App Security.</span></span> <span data-ttu-id="4f348-203">파일럿 단계인 3단계 동안 시도해 [보시고 권장하는 단계입니다. 파일럿 Microsoft Cloud App Security.](eval-defender-mcas-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="4f348-203">It is a step we encourage you to try out during the pilot phase — [Step 3. Pilot Microsoft Cloud App Security](eval-defender-mcas-pilot.md).</span></span>

## <a name="siem-integration"></a><span data-ttu-id="4f348-204">SIEM 통합</span><span class="sxs-lookup"><span data-stu-id="4f348-204">SIEM integration</span></span>

<span data-ttu-id="4f348-205">일반 SIEM Microsoft Cloud App Security Azure Sentinel과 통합하여 연결된 앱의 경고 및 활동을 중앙에서 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-205">You can integrate Microsoft Cloud App Security with your generic SIEM server or with Azure Sentinel to enable centralized monitoring of alerts and activities from connected apps.</span></span> 

<span data-ttu-id="4f348-206">또한 Azure Sentinel에는 Azure Sentinel과 Microsoft Cloud App Security 통합할 수 있는 Microsoft Cloud App Security 커넥터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-206">Additionally, Azure Sentinel includes a Microsoft Cloud App Security connector to provide deeper integration with Azure Sentinel.</span></span> <span data-ttu-id="4f348-207">이를 통해 클라우드 앱에 대한 가시성을 확보할 뿐만 아니라 사이버 위협을 식별하고 퇴치하고 데이터 이동 방법을 제어할 수 있는 정교한 분석을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f348-207">This enables you to not only gain visibility into your cloud apps but to also get sophisticated analytics to identify and combat cyberthreats and to control how your data travels.</span></span>

- [<span data-ttu-id="4f348-208">일반 SIEM 통합</span><span class="sxs-lookup"><span data-stu-id="4f348-208">Generic SIEM integration</span></span>](/cloud-app-security/siem)
- [<span data-ttu-id="4f348-209">MCAS에서 Azure Sentinel로 경고 및 클라우드 검색 로그 스트림</span><span class="sxs-lookup"><span data-stu-id="4f348-209">Stream alerts and Cloud Discovery logs from MCAS into Azure Sentinel</span></span>](/azure/sentinel/connect-cloud-app-security)

### <a name="next-steps"></a><span data-ttu-id="4f348-210">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4f348-210">Next steps</span></span>

<span data-ttu-id="4f348-211">3단계 중 2단계: [사용자에](eval-defender-mcas-enable-eval.md) 대해 평가 환경을 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4f348-211">Step 2 of 3: [Enable the evaluation environment for Microsoft Cloud App Security](eval-defender-mcas-enable-eval.md)</span></span>

<span data-ttu-id="4f348-212">평가용 [개요로 Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4f348-212">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="4f348-213">평가 및 파일럿 테스트 [개요로 Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4f348-213">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>