---
title: Microsoft 365 Defender 계산
description: Microsoft 365 Defender 평가판 랩 또는 파일럿 환경을 설정하여 조직의 장치, ID, 데이터 및 응용 프로그램을 보호하도록 설계된 보안 솔루션을 시험해 보거나 경험해 보십시오.
keywords: Microsoft 365 Defender 평가, Microsoft 365 Defender 평가, Microsoft 365 Defender 평가, Microsoft 365 Defender 평가 랩, Microsoft 365 Defender 파일럿, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, ID, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화된 조사 및 수정, 고급 헌팅
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
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933172"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="4eb51-104">Microsoft 365 Defender 평가판 랩 또는 파일럿 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="4eb51-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4eb51-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="4eb51-105">**Applies to:**</span></span>
- <span data-ttu-id="4eb51-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4eb51-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="4eb51-107">이 가이드는 사용자 및 그룹과 함께 랩 환경을 설정하는 데 도움을 주며 위협 공격을 모방하고 의미 있는 평가판 결과를 얻을 수 있도록 Microsoft 365 Defender의 기능 구성을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb51-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="4eb51-108">이 평가판 랩 또는 파일럿 환경을 만드는 목적은 포괄적이고 통합된 Microsoft 365 Defender 기능을 설명하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4eb51-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="4eb51-109">이 지능형 보안 솔루션이 조직에서 고급 위협을 감지, 방지, 자동으로 조사 및 대응하는 방법을 경험해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="4eb51-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="4eb51-110">권장 배포 경로를 기반으로 Microsoft 365 Defender 평가를 시작하는 단계를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb51-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="4eb51-111">테스트 환경에서 평가판 계정을 사용하거나 프로덕션 환경에서 정식 라이선스를 통해 파일럿 환경에서 보안 솔루션을 설정할 수 있도록 하는 것이 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="4eb51-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="4eb51-112">시험 랩 또는 파일럿 환경을 준비하면 조직의 의사 결정권자에게 보안 작업 사용 사례를 제시하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb51-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="4eb51-113">공격 시뮬레이션 실행을 완료하고 결과에 만족하면 조직의 Microsoft 기술 영업 전문가 또는 전문가의 도움을 통해 조직에서 공격 시뮬레이션을 완전히 배포하고 운영할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb51-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="4eb51-114">이 가이드는 다음을 도와 줄 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4eb51-114">This guide will help you:</span></span>
- <span data-ttu-id="4eb51-115">랩 서버 및 컴퓨터 설정</span><span class="sxs-lookup"><span data-stu-id="4eb51-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="4eb51-116">사용자 및 그룹을 통해 Active Directory 구성</span><span class="sxs-lookup"><span data-stu-id="4eb51-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="4eb51-117">ID에 대한 Microsoft Defender, Office 365용 Microsoft Defender, 끝점용 Microsoft Defender 및 Microsoft Cloud App Security 설정 및 구성</span><span class="sxs-lookup"><span data-stu-id="4eb51-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="4eb51-118">서버 및 컴퓨터에 대한 로컬 정책 설정</span><span class="sxs-lookup"><span data-stu-id="4eb51-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="4eb51-119">위협 공격을 모방하여 Microsoft 365 Defender에서 테스트 인시던트 또는 경고 생성</span><span class="sxs-lookup"><span data-stu-id="4eb51-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="4eb51-120">최적의 결과를 얻기 위해 랩 설정 지침을 최대한 따르세요.</span><span class="sxs-lookup"><span data-stu-id="4eb51-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="4eb51-121">배포 단계</span><span class="sxs-lookup"><span data-stu-id="4eb51-121">Deployment phases</span></span>

<span data-ttu-id="4eb51-122">Microsoft 365 Defender 평가판 랩 환경을 만드는 세 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb51-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![배포 단계: 준비, 설정, 온보드](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="4eb51-124">단계</span><span class="sxs-lookup"><span data-stu-id="4eb51-124">Phase</span></span> | <span data-ttu-id="4eb51-125">설명</span><span class="sxs-lookup"><span data-stu-id="4eb51-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="4eb51-126">1 단계: 준비</span><span class="sxs-lookup"><span data-stu-id="4eb51-126">Phase 1: Prepare</span></span>](prepare-m365d-eval.md)| <span data-ttu-id="4eb51-127">평가판 랩 또는 파일럿 환경에서 Microsoft 365 Defender를 배포할 때 고려해야 할 사항에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb51-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="4eb51-128">- 이해 관계자 및 사인오프</span><span class="sxs-lookup"><span data-stu-id="4eb51-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="4eb51-129">- 환경 고려 사항</span><span class="sxs-lookup"><span data-stu-id="4eb51-129">- Environment considerations</span></span> <br><span data-ttu-id="4eb51-130">- Access</span><span class="sxs-lookup"><span data-stu-id="4eb51-130">- Access</span></span> <br><span data-ttu-id="4eb51-131">- Azure Active Directory 설정</span><span class="sxs-lookup"><span data-stu-id="4eb51-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="4eb51-132">- 구성 순서</span><span class="sxs-lookup"><span data-stu-id="4eb51-132">- Configuration order</span></span>
|[<span data-ttu-id="4eb51-133">2 단계: 설정</span><span class="sxs-lookup"><span data-stu-id="4eb51-133">Phase 2: Setup</span></span>](setup-m365deval.md)|  <span data-ttu-id="4eb51-134">초기 단계에 따라 Microsoft 365 보안 센터에 액세스하여 Microsoft 365 Defender 평가판 랩 또는 파일럿 환경을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="4eb51-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="4eb51-135">다음을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb51-135">You'll be guided to:</span></span><br><br><span data-ttu-id="4eb51-136">- Microsoft 365 E5 평가판 등록</span><span class="sxs-lookup"><span data-stu-id="4eb51-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="4eb51-137">- 도메인 구성</span><span class="sxs-lookup"><span data-stu-id="4eb51-137">- Configure domain</span></span><br><span data-ttu-id="4eb51-138">- Microsoft 365 E5 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="4eb51-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="4eb51-139">- 포털에서 설정 마법사 완료</span><span class="sxs-lookup"><span data-stu-id="4eb51-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="4eb51-140">3단계: 온보드 & 구성</span><span class="sxs-lookup"><span data-stu-id="4eb51-140">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="4eb51-141">각 Microsoft 365 Defender 원창을 구성하고 끝점을 온보딩합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb51-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="4eb51-142">다음을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb51-142">You'll be guided to:</span></span><br><br><span data-ttu-id="4eb51-143">- Office 365용 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="4eb51-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="4eb51-144">- Microsoft Cloud App Security 구성</span><span class="sxs-lookup"><span data-stu-id="4eb51-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="4eb51-145">- ID에 맞게 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="4eb51-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="4eb51-146">- 끝점에 대한 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="4eb51-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="4eb51-147">이 가이드를 완료하면 관련 이해 관계자와 필요한 승인을 식별하고, 올바른 액세스 권한을 가지고, 평가판에 등록하고, 도메인을 구성하고, 각 Microsoft 365 Defender 기조를 등록하고, 끝점이 서비스에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eb51-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="4eb51-148">주요 기능</span><span class="sxs-lookup"><span data-stu-id="4eb51-148">Key capabilities</span></span>

<span data-ttu-id="4eb51-149">Microsoft 365 Defender는 많은 기능을 제공 하지만 이 배포 가이드의 주요 목적은 장치를 온보딩하여 시작하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4eb51-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="4eb51-150">이 지침은 온보드 외에도 다음 기능으로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb51-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="4eb51-151">기능</span><span class="sxs-lookup"><span data-stu-id="4eb51-151">Capability</span></span> | <span data-ttu-id="4eb51-152">설명</span><span class="sxs-lookup"><span data-stu-id="4eb51-152">Description</span></span> 
:---|:---
<span data-ttu-id="4eb51-153">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4eb51-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="4eb51-154">오늘날의 위협으로부터 전체 Office 365 열고 보호</span><span class="sxs-lookup"><span data-stu-id="4eb51-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="4eb51-155">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4eb51-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="4eb51-156">손상된 ID 및 악의적인 내부자 작업에 대한 위협을 식별하고 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb51-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="4eb51-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4eb51-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="4eb51-158">다양한 가시성을 제공하고, 데이터 이동을 제어하고, 클라우드 서비스 전반에서 사이버 위협을 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb51-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="4eb51-159">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4eb51-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="4eb51-160">포괄적인 끝점 보안을 통해 고급 위협을 방지, 감지 및 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb51-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="4eb51-161">범위 내</span><span class="sxs-lookup"><span data-stu-id="4eb51-161">In scope</span></span>

<span data-ttu-id="4eb51-162">이 가이드의 범위는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb51-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="4eb51-163">Azure Active Directory 설정</span><span class="sxs-lookup"><span data-stu-id="4eb51-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="4eb51-164">Microsoft 365 Defender 설정</span><span class="sxs-lookup"><span data-stu-id="4eb51-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="4eb51-165">파일럿을 실행하는 경우 Microsoft 365 E5 평가판에 등록하거나 정식 라이선스 사용</span><span class="sxs-lookup"><span data-stu-id="4eb51-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="4eb51-166">도메인 구성</span><span class="sxs-lookup"><span data-stu-id="4eb51-166">Configure domain</span></span>
    -   <span data-ttu-id="4eb51-167">Microsoft 365 E5 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="4eb51-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="4eb51-168">포털 내에서 설정 마법사 완료</span><span class="sxs-lookup"><span data-stu-id="4eb51-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="4eb51-169">모범 사례에 따라 모든 Microsoft 365 Defender 기조 구성</span><span class="sxs-lookup"><span data-stu-id="4eb51-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="4eb51-170">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4eb51-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="4eb51-171">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4eb51-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="4eb51-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4eb51-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="4eb51-173">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4eb51-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="4eb51-174">범위를 벗어남</span><span class="sxs-lookup"><span data-stu-id="4eb51-174">Out of scope</span></span>

<span data-ttu-id="4eb51-175">다음은 이 배포 가이드의 범위를 벗어나는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4eb51-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="4eb51-176">Microsoft 365 Defender와 통합될 수 있는 타사 솔루션 구성</span><span class="sxs-lookup"><span data-stu-id="4eb51-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="4eb51-177">프로덕션 환경에서 침투 테스트</span><span class="sxs-lookup"><span data-stu-id="4eb51-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="4eb51-178">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4eb51-178">Next step</span></span>
<span data-ttu-id="4eb51-179">[1단계: 준비](prepare-m365d-eval.md) 
</span><span class="sxs-lookup"><span data-stu-id="4eb51-179">[Phase 1: Prepare](prepare-m365d-eval.md) 
</span></span><br> <span data-ttu-id="4eb51-180">Microsoft 365 Defender 평가판 랩 또는 파일럿 환경 준비</span><span class="sxs-lookup"><span data-stu-id="4eb51-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
