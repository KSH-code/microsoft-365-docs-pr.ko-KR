---
title: Microsoft 365 Defender 평가
description: 조직에서 Microsoft 365 Defender, ID, 데이터 및 응용 프로그램을 보호하도록 설계된 보안 솔루션을 시험해 보거나 경험할 수 있도록 Microsoft 365 Defender 테스트 랩 또는 파일럿 환경을 설정하세요.
keywords: Microsoft 365 Defender 평가, Microsoft 365 Defender 평가, Microsoft 365 Defender Microsoft 365 Defender 평가 랩, Microsoft 365 Defender 파일럿, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, ID, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화된 조사 및 수정, 고급 헌팅
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1c260588b80d8325567b74148a7a62586cfbc707
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458831"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="6b531-104">테스트 Microsoft 365 Defender 또는 파일럿 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="6b531-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6b531-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6b531-105">**Applies to:**</span></span>
- <span data-ttu-id="6b531-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6b531-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="6b531-107">이 가이드는 사용자 및 그룹과 함께 랩 환경을 설정하는 데 도움을 주며 위협 공격을 모방하고 의미 있는 시험 결과를 얻을 수 있도록 Microsoft 365 Defender 기능의 구성을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="6b531-108">이 평가판 랩 또는 파일럿 환경을 만드는 목적은 포괄적이고 통합된 Microsoft 365 Defender 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="6b531-109">이 지능형 보안 솔루션이 조직에서 고급 위협을 감지, 방지, 자동으로 조사 및 대응하는 방법을 경험해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="6b531-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="6b531-110">권장 배포 경로를 기반으로 Microsoft 365 Defender 평가를 시작하는 단계를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="6b531-111">테스트 환경에서 평가판 계정을 사용하거나 프로덕션 환경에서 정식 라이선스를 통해 파일럿 환경에서 보안 솔루션을 설정할 수 있도록 하는 것이 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="6b531-112">시험 랩 또는 파일럿 환경을 준비하면 조직의 의사 결정권자에게 보안 작업 사용 사례를 제시하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="6b531-113">공격 시뮬레이션 실행을 완료하고 결과에 만족하면 조직의 Microsoft 기술 영업 전문가 또는 전문가의 도움을 통해 조직에서 공격 시뮬레이션을 완전히 배포하고 운영할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="6b531-114">이 가이드는 다음을 도와 줄 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-114">This guide will help you:</span></span>
- <span data-ttu-id="6b531-115">랩 서버 및 컴퓨터 설정</span><span class="sxs-lookup"><span data-stu-id="6b531-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="6b531-116">사용자 및 그룹을 통해 Active Directory 구성</span><span class="sxs-lookup"><span data-stu-id="6b531-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="6b531-117">Id에 대한 Microsoft Defender, microsoft Defender for Office 365, 끝점용 Microsoft Defender 및 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6b531-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="6b531-118">서버 및 컴퓨터에 대한 로컬 정책 설정</span><span class="sxs-lookup"><span data-stu-id="6b531-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="6b531-119">위협 공격을 모방하여 테스트 인시던트 또는 경고를 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6b531-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="6b531-120">최적의 결과를 얻기 위해 랩 설정 지침을 최대한 따르세요.</span><span class="sxs-lookup"><span data-stu-id="6b531-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="6b531-121">배포 단계</span><span class="sxs-lookup"><span data-stu-id="6b531-121">Deployment phases</span></span>

<span data-ttu-id="6b531-122">테스트 랩 환경을 만드는 세 가지 Microsoft 365 Defender 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![배포 단계: 준비, 설정, 온보드](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="6b531-124">단계</span><span class="sxs-lookup"><span data-stu-id="6b531-124">Phase</span></span> | <span data-ttu-id="6b531-125">설명</span><span class="sxs-lookup"><span data-stu-id="6b531-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="6b531-126">1 단계: 준비</span><span class="sxs-lookup"><span data-stu-id="6b531-126">Phase 1: Prepare</span></span>](prepare-m365d-eval.md)| <span data-ttu-id="6b531-127">평가판 랩 또는 파일럿 환경에서 배포할 Microsoft 365 Defender 고려해야 하는 사항에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="6b531-128">- 이해 관계자 및 사인오프</span><span class="sxs-lookup"><span data-stu-id="6b531-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="6b531-129">- 환경 고려 사항</span><span class="sxs-lookup"><span data-stu-id="6b531-129">- Environment considerations</span></span> <br><span data-ttu-id="6b531-130">- Access</span><span class="sxs-lookup"><span data-stu-id="6b531-130">- Access</span></span> <br><span data-ttu-id="6b531-131">- Azure Active Directory 설정</span><span class="sxs-lookup"><span data-stu-id="6b531-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="6b531-132">- 구성 순서</span><span class="sxs-lookup"><span data-stu-id="6b531-132">- Configuration order</span></span>
|[<span data-ttu-id="6b531-133">2 단계: 설정</span><span class="sxs-lookup"><span data-stu-id="6b531-133">Phase 2: Setup</span></span>](setup-m365deval.md)|  <span data-ttu-id="6b531-134">보안 센터에 액세스하는 Microsoft 365 초기 단계를 수행하여 Microsoft 365 Defender 테스트 랩 또는 파일럿 환경을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="6b531-135">다음을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-135">You'll be guided to:</span></span><br><br><span data-ttu-id="6b531-136">- 평가판에 Microsoft 365 E5 등록</span><span class="sxs-lookup"><span data-stu-id="6b531-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="6b531-137">- 도메인 구성</span><span class="sxs-lookup"><span data-stu-id="6b531-137">- Configure domain</span></span><br><span data-ttu-id="6b531-138">- Microsoft 365 E5 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="6b531-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="6b531-139">- 포털에서 설정 마법사 완료</span><span class="sxs-lookup"><span data-stu-id="6b531-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="6b531-140">3단계: 온보드 & 구성</span><span class="sxs-lookup"><span data-stu-id="6b531-140">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="6b531-141">각 Microsoft 365 Defender 구성하고 끝점을 온보드합니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="6b531-142">다음을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-142">You'll be guided to:</span></span><br><br><span data-ttu-id="6b531-143">- 사용자에 대해 Microsoft Defender Office 365</span><span class="sxs-lookup"><span data-stu-id="6b531-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="6b531-144">- 구성 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6b531-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="6b531-145">- ID에 맞게 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="6b531-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="6b531-146">- 끝점에 대한 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="6b531-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="6b531-147">이 가이드를 완료한 후 관련 이해 관계자와 필요한 승인을 식별하고, 올바른 액세스 권한을 가지고, 평가판에 등록하고, 도메인을 구성하고, 각 Microsoft 365 Defender 기조를 사용할 수 있으며, 끝점은 서비스에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="6b531-148">주요 기능</span><span class="sxs-lookup"><span data-stu-id="6b531-148">Key capabilities</span></span>

<span data-ttu-id="6b531-149">여러 Microsoft 365 Defender 기능을 제공하겠지만 이 배포 가이드의 주요 목적은 장치를 온보더링하여 시작하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="6b531-150">이 지침은 온보드 외에도 다음 기능으로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="6b531-151">기능</span><span class="sxs-lookup"><span data-stu-id="6b531-151">Capability</span></span> | <span data-ttu-id="6b531-152">설명</span><span class="sxs-lookup"><span data-stu-id="6b531-152">Description</span></span> 
:---|:---
<span data-ttu-id="6b531-153">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6b531-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="6b531-154">오늘날의 위협으로부터 Office 365 전체 조직을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="6b531-155">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6b531-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="6b531-156">손상된 ID 및 악의적인 내부자 작업에 대한 위협을 식별하고 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="6b531-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6b531-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="6b531-158">다양한 가시성을 제공하고, 데이터 이동을 제어하고, 클라우드 서비스 전반에서 사이버 위협을 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="6b531-159">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6b531-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="6b531-160">포괄적인 끝점 보안을 통해 고급 위협을 방지, 감지 및 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="6b531-161">범위 내</span><span class="sxs-lookup"><span data-stu-id="6b531-161">In scope</span></span>

<span data-ttu-id="6b531-162">이 가이드의 범위는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="6b531-163">설정 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6b531-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="6b531-164">설정 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6b531-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="6b531-165">파일럿을 Microsoft 365 E5 평가판에 등록하거나 정식 라이선스 사용</span><span class="sxs-lookup"><span data-stu-id="6b531-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="6b531-166">도메인 구성</span><span class="sxs-lookup"><span data-stu-id="6b531-166">Configure domain</span></span>
    -   <span data-ttu-id="6b531-167">라이선스 Microsoft 365 E5 할당</span><span class="sxs-lookup"><span data-stu-id="6b531-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="6b531-168">포털 내에서 설정 마법사 완료</span><span class="sxs-lookup"><span data-stu-id="6b531-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="6b531-169">모범 사례를 Microsoft 365 Defender 모든 기본 구성 기조 구성</span><span class="sxs-lookup"><span data-stu-id="6b531-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="6b531-170">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6b531-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="6b531-171">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6b531-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="6b531-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6b531-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="6b531-173">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6b531-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="6b531-174">범위를 벗어남</span><span class="sxs-lookup"><span data-stu-id="6b531-174">Out of scope</span></span>

<span data-ttu-id="6b531-175">다음은 이 배포 가이드의 범위를 벗어나는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6b531-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="6b531-176">타사 솔루션과 통합될 수 있는 타사 솔루션 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6b531-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="6b531-177">프로덕션 환경에서 침투 테스트</span><span class="sxs-lookup"><span data-stu-id="6b531-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="6b531-178">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6b531-178">Next step</span></span>
<span data-ttu-id="6b531-179">[1단계: 준비](prepare-m365d-eval.md) 
</span><span class="sxs-lookup"><span data-stu-id="6b531-179">[Phase 1: Prepare](prepare-m365d-eval.md) 
</span></span><br> <span data-ttu-id="6b531-180">테스트 Microsoft 365 Defender 파일럿 환경 준비</span><span class="sxs-lookup"><span data-stu-id="6b531-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
