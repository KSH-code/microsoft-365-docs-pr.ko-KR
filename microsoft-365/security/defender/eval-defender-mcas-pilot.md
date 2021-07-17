---
title: 파일럿 Microsoft Cloud App Security 파일럿 Microsoft 365 Defender, 파일럿 그룹 만들기, 조건부 액세스 제어 구성, 기능 시험 실행, 파일럿 작업의 일부로 Microsoft 365 Defender
description: 장치, Microsoft 365 Defender, 데이터 및 응용 프로그램을 보호하도록 설계된 보안 솔루션을 테스트하고 경험할 수 있도록 테스트 테스트 랩 또는 파일럿 환경을 설정하세요.
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
ms.openlocfilehash: e061bf213ee929f91a48b03c71b9654a7ea76b8c
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458045"
---
# <a name="pilot-microsoft-cloud-app-security-with-microsoft-365-defender"></a><span data-ttu-id="6d1d4-103">파일럿 Microsoft Cloud App Security 파일럿 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d1d4-103">Pilot Microsoft Cloud App Security with Microsoft 365 Defender</span></span>


<span data-ttu-id="6d1d4-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6d1d4-104">**Applies to:**</span></span>
- <span data-ttu-id="6d1d4-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d1d4-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="6d1d4-106">이 문서는 사용자 환경의 평가 환경을 설정하는 프로세스의 [3단계](eval-defender-mcas-overview.md) 중 Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-106">This article is [Step 3 of 3](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security.</span></span> <span data-ttu-id="6d1d4-107">이 프로세스에 대한 자세한 내용은 개요 문서를 [참조하세요.](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6d1d4-107">For more information about this process, see the [overview article](eval-defender-mcas-overview.md).</span></span>

<span data-ttu-id="6d1d4-108">다음 단계에 따라 파일럿을 설정하고 구성하여 Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-108">Use the following steps to setup and configure the pilot for Microsoft Cloud App Security.</span></span>


![파일럿 Microsoft Cloud App Security](../../media/defender/m365-defender-mcas-pilot-steps.png)

- <span data-ttu-id="6d1d4-110">1단계.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-110">Step 1.</span></span> [<span data-ttu-id="6d1d4-111">파일럿 그룹 만들기 - 특정 사용자 그룹으로 파일럿 배포 범위 지정</span><span class="sxs-lookup"><span data-stu-id="6d1d4-111">Create the pilot group — Scope your pilot deployment to certain user groups</span></span>](#step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups)
- [<span data-ttu-id="6d1d4-112">2단계. 보호 구성 - 조건부 액세스 앱 제어</span><span class="sxs-lookup"><span data-stu-id="6d1d4-112">Step 2. Configure protection — Conditional Access App Control</span></span>](#step-2-configure-protection--conditional-access-app-control)
- [<span data-ttu-id="6d1d4-113">3단계. 기능 사용 - 환경 보호를 위한 자습서를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-113">Step 3. Try out capabilities — Walk through tutorials for protecting your environment</span></span>](#step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment) 


## <a name="step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups"></a><span data-ttu-id="6d1d4-114">1단계.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-114">Step 1.</span></span> <span data-ttu-id="6d1d4-115">파일럿 그룹 만들기 - 특정 사용자 그룹으로 파일럿 배포 범위 지정</span><span class="sxs-lookup"><span data-stu-id="6d1d4-115">Create the pilot group — Scope your pilot deployment to certain user groups</span></span>

<span data-ttu-id="6d1d4-116">Microsoft Cloud App Security 배포 범위를 지정하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-116">Microsoft Cloud App Security enables you to scope your deployment.</span></span> <span data-ttu-id="6d1d4-117">스코어를 사용하면 앱에 대해 모니터링하거나 모니터링에서 제외할 특정 사용자 그룹을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-117">Scoping allows you to select certain user groups to be monitored for apps or excluded from monitoring.</span></span> <span data-ttu-id="6d1d4-118">사용자 그룹을 포함하거나 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-118">You can include or exclude user groups.</span></span> <span data-ttu-id="6d1d4-119">파일럿 배포의 범위를 지정하기 위해 [범위가 지정한 배포를 참조합니다.](/cloud-app-security/scoped-deployment)</span><span class="sxs-lookup"><span data-stu-id="6d1d4-119">To scope your pilot deployment, see [Scoped Deployment](/cloud-app-security/scoped-deployment).</span></span>


## <a name="step-2-configure-protection--conditional-access-app-control"></a><span data-ttu-id="6d1d4-120">2단계.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-120">Step 2.</span></span> <span data-ttu-id="6d1d4-121">보호 구성 - 조건부 액세스 앱 제어</span><span class="sxs-lookup"><span data-stu-id="6d1d4-121">Configure protection — Conditional Access App Control</span></span>

<span data-ttu-id="6d1d4-122">구성할 수 있는 가장 강력한 보호 중 하나는 조건부 액세스 앱 제어입니다.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-122">One of the most powerful protections you can configure is Conditional Access App Control.</span></span> <span data-ttu-id="6d1d4-123">이를 위해서는 Azure AD(Azure Active Directory 통합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-123">This requires integration with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="6d1d4-124">이를 통해 관련 정책(예: 정상 디바이스 요구)을 비롯한 조건부 액세스 정책을 승인된 클라우드 앱에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-124">It allows you to apply Conditional Access policies, including related policies (like requiring healthy devices), to cloud apps you've sanctioned.</span></span> 

<span data-ttu-id="6d1d4-125">Microsoft Cloud App Security 사용하여 SaaS 앱을 관리하는 첫 번째 단계는 이러한 앱을 검색한 다음 Azure AD 테넌트에 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-125">The first step in using Microsoft Cloud App Security to manage SaaS apps is to discover these and then add them to your Azure AD tenant.</span></span> <span data-ttu-id="6d1d4-126">검색에 도움이 필요한 경우 [네트워크에서 SaaS 앱](/cloud-app-security/tutorial-shadow-it)검색 및 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-126">If you need help with discovery, see [Discover and manage SaaS apps in your network](/cloud-app-security/tutorial-shadow-it).</span></span> <span data-ttu-id="6d1d4-127">앱을 검색한 후 Azure AD 테넌트에 [추가합니다.](/azure/active-directory/manage-apps/add-application-portal)</span><span class="sxs-lookup"><span data-stu-id="6d1d4-127">After you've discovered apps, [add these to your Azure AD tenant](/azure/active-directory/manage-apps/add-application-portal).</span></span>

<span data-ttu-id="6d1d4-128">다음을 수행하여 이러한 관리 작업을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-128">You can begin to manage these by doing the following:</span></span>

- <span data-ttu-id="6d1d4-129">먼저 Azure AD에서 새 조건부 액세스 정책을 만들고 "조건부 액세스 앱 제어 사용"으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-129">First, in Azure AD, create a new conditional access policy and configure it to "Use Conditional Access App Control."</span></span> <span data-ttu-id="6d1d4-130">그러면 요청이 Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-130">This redirects the request to Cloud App Security.</span></span> <span data-ttu-id="6d1d4-131">하나의 정책을 만들고 모든 SaaS 앱을 이 정책에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-131">You can create one policy and add all SaaS apps to this policy.</span></span>
- <span data-ttu-id="6d1d4-132">다음으로, Cloud App Security 세션 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-132">Next, in Cloud App Security, create session policies.</span></span> <span data-ttu-id="6d1d4-133">적용할 각 컨트롤에 대해 정책을 하나씩 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-133">Create one policy for each control you want to apply.</span></span>

<span data-ttu-id="6d1d4-134">지원되는 앱 및 클라이언트를 비롯한 자세한 내용은 조건부 액세스 앱 제어로 Microsoft Cloud App Security [보호를 참조하세요.](/cloud-app-security/proxy-intro-aad)</span><span class="sxs-lookup"><span data-stu-id="6d1d4-134">For more information, including supported apps and clients, see [Protect apps with Microsoft Cloud App Security Conditional Access App Control](/cloud-app-security/proxy-intro-aad).</span></span> 

<span data-ttu-id="6d1d4-135">예를 들어 정책은 [SaaS 앱에 Microsoft Cloud App Security 권장 정책을 참조하세요.](../office-365-security/mcas-saas-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="6d1d4-135">For example policies, see [Recommended Microsoft Cloud App Security policies for SaaS apps](../office-365-security/mcas-saas-access-policies.md).</span></span> <span data-ttu-id="6d1d4-136">이러한 정책은 모든 [](../office-365-security/microsoft-365-policies-configurations.md) 고객에게 시작점으로 권장되는 공통 ID 및 장치 액세스 정책 집합을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-136">These policies build on a set of [common identity and device access policies](../office-365-security/microsoft-365-policies-configurations.md) that are recommended as a starting point for all customers.</span></span> 

## <a name="step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment"></a><span data-ttu-id="6d1d4-137">3단계.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-137">Step 3.</span></span> <span data-ttu-id="6d1d4-138">기능 사용 - 환경 보호를 위한 자습서를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-138">Try out capabilities — Walk through tutorials for protecting your environment</span></span> 

<span data-ttu-id="6d1d4-139">이 Microsoft Cloud App Security 설명서에는 위험을 검색하고 환경을 보호하는 데 도움이 되는 일련의 자습서가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-139">The Microsoft Cloud App Security documentation includes a series of tutorials to help you discover risk and protect your environment.</span></span> 

<span data-ttu-id="6d1d4-140">다음 자습서를 Cloud App Security 사용해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1d4-140">Try out Cloud App Security tutorials:</span></span>

- [<span data-ttu-id="6d1d4-141">의심스러운 사용자 활동 감지</span><span class="sxs-lookup"><span data-stu-id="6d1d4-141">Detect suspicious user activity</span></span>](/cloud-app-security/tutorial-suspicious-activity)
- [<span data-ttu-id="6d1d4-142">위험한 사용자 조사</span><span class="sxs-lookup"><span data-stu-id="6d1d4-142">Investigate risky users</span></span>](/cloud-app-security/tutorial-ueba)
- [<span data-ttu-id="6d1d4-143">위험한 OAuth 앱 조사</span><span class="sxs-lookup"><span data-stu-id="6d1d4-143">Investigate risky OAuth apps</span></span>](/cloud-app-security/investigate-risky-oauth)
- [<span data-ttu-id="6d1d4-144">중요한 정보 검색 및 보호</span><span class="sxs-lookup"><span data-stu-id="6d1d4-144">Discover and protect sensitive information</span></span>](/cloud-app-security/tutorial-dlp)
- [<span data-ttu-id="6d1d4-145">실시간으로 조직의 모든 앱 보호</span><span class="sxs-lookup"><span data-stu-id="6d1d4-145">Protect any app in your organization in real time</span></span>](/cloud-app-security/tutorial-proxy)
- [<span data-ttu-id="6d1d4-146">중요한 정보 다운로드 차단</span><span class="sxs-lookup"><span data-stu-id="6d1d4-146">Block downloads of sensitive information</span></span>](/cloud-app-security/use-case-proxy-block-session-aad)
- [<span data-ttu-id="6d1d4-147">관리자를 통해 파일 보호</span><span class="sxs-lookup"><span data-stu-id="6d1d4-147">Protect your files with admin quarantine</span></span>](/cloud-app-security/use-case-admin-quarantine)
- [<span data-ttu-id="6d1d4-148">위험한 작업 시 단계별 인증 필요</span><span class="sxs-lookup"><span data-stu-id="6d1d4-148">Require step-up authentication upon risky action</span></span>](/cloud-app-security/tutorial-step-up-authentication)

## <a name="next-steps"></a><span data-ttu-id="6d1d4-149">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6d1d4-149">Next steps</span></span>

[<span data-ttu-id="6d1d4-150">파일럿 환경에서 파일럿 Microsoft 365 Defender 사용하여 조사 및 대응</span><span class="sxs-lookup"><span data-stu-id="6d1d4-150">Investigate and respond using Microsoft 365 Defender in a pilot environment</span></span>](eval-defender-investigate-respond.md)

<span data-ttu-id="6d1d4-151">평가용 [개요로 Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6d1d4-151">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="6d1d4-152">평가 및 파일럿 테스트 [개요로 Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6d1d4-152">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>