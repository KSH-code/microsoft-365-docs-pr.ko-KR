---
title: Microsoft 365 Defender 평가
description: Microsoft 365 Defender 평가판 lab 또는 파일럿 환경을 설정 하 여 조직의 장치, id, 데이터 및 응용 프로그램을 보호 하도록 설계 된 보안 솔루션을 체험해 보세요.
keywords: Microsoft Threat Protection 평가판, microsoft threat protection 체험, microsoft threat protection 평가 랩, microsoft 위협의 보호 파일럿, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, id, 사용자, 데이터, 응용 프로그램, 사건, 자동화 된 조사 및 개선, 고급 구하기
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: d6c96f7720344721bb2786dc130c490a5a8ea657
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846487"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="648e0-104">Microsoft 365 Defender 평가판 랩 또는 파일럿 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="648e0-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="648e0-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="648e0-105">**Applies to:**</span></span>
- <span data-ttu-id="648e0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="648e0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="648e0-107">이 시험 운용 랩 또는 파일럿 환경을 만드는 목적은 포괄적이 고 통합 된 Microsoft 365 Defender 기능을 보여 주기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="648e0-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="648e0-108">이 지능형 보안 솔루션은 조직에 고급 위협 요소를 감지, 방지, 자동 조사 및 대응 하는 방법을 경험 합니다.</span><span class="sxs-lookup"><span data-stu-id="648e0-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="648e0-109">이 가이드에서는 권장 되는 배포 경로를 기반으로 Microsoft 365 Defender evaluation을 시작 하는 단계를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="648e0-109">This guide takes you through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="648e0-110">목표는 평가판 계정을 사용 하는 랩 환경 또는 프로덕션 환경에서 정식 라이선스로 보안 솔루션을 설정 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="648e0-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="648e0-111">평가판 랩 또는 파일럿 환경을 준비 하면 보안 작업 사용 사례를 조직의 의사 결정자에 게 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="648e0-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="648e0-112">공격 시뮬레이션을 실행 하 고 결과에 만족 하면 조직의 Microsoft 기술 영업 전문가 또는 전문가를 지원 하 여 조직에서이를 완벽 하 게 배포 하 고 operationalize 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="648e0-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="648e0-113">이 가이드는 다음과 같은 작업에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="648e0-113">This guide will help you:</span></span>
- <span data-ttu-id="648e0-114">랩 서버 및 컴퓨터 설정</span><span class="sxs-lookup"><span data-stu-id="648e0-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="648e0-115">사용자 및 그룹을 사용 하 여 Active Directory 구성</span><span class="sxs-lookup"><span data-stu-id="648e0-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="648e0-116">Microsoft Defender for Identity, Office 365 용 microsoft Defender, 끝점에 대 한 Microsoft Defender 및 Microsoft Cloud App Security을 설정 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="648e0-116">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="648e0-117">서버 및 컴퓨터에 대 한 로컬 정책 설정</span><span class="sxs-lookup"><span data-stu-id="648e0-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="648e0-118">위협 공격을 모방 하 여 Microsoft 365 Defender에서 테스트 인시던트 또는 경고 생성</span><span class="sxs-lookup"><span data-stu-id="648e0-118">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="648e0-119">최적의 결과를 위해 랩 설치 지침을 최대한 면밀 하 게 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="648e0-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="648e0-120">배포 단계</span><span class="sxs-lookup"><span data-stu-id="648e0-120">Deployment phases</span></span>

<span data-ttu-id="648e0-121">Microsoft 365 Defender 평가판 랩 환경을 만들고 배포 하는 과정은 다음 세 단계로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="648e0-121">There are three phases in creating a Microsoft 365 Defender trial lab environment and deploying it:</span></span>

|<span data-ttu-id="648e0-122">단계</span><span class="sxs-lookup"><span data-stu-id="648e0-122">Phase</span></span> | <span data-ttu-id="648e0-123">설명</span><span class="sxs-lookup"><span data-stu-id="648e0-123">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="648e0-124">![1 단계: 준비](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="648e0-124">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="648e0-125">1 단계: 준비</span><span class="sxs-lookup"><span data-stu-id="648e0-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="648e0-126">평가판 랩 또는 파일럿 환경에서 Microsoft 365 Defender를 배포할 때 고려해 야 할 사항에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="648e0-126">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="648e0-127">-관련자 및 승인</span><span class="sxs-lookup"><span data-stu-id="648e0-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="648e0-128">-환경 고려 사항</span><span class="sxs-lookup"><span data-stu-id="648e0-128">- Environment considerations</span></span> <br><span data-ttu-id="648e0-129">-액세스</span><span class="sxs-lookup"><span data-stu-id="648e0-129">- Access</span></span> <br><span data-ttu-id="648e0-130">-Azure Active Directory 설치</span><span class="sxs-lookup"><span data-stu-id="648e0-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="648e0-131">-구성 순서</span><span class="sxs-lookup"><span data-stu-id="648e0-131">- Configuration order</span></span>
|  <span data-ttu-id="648e0-132">![2 단계: 설치](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="648e0-132">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="648e0-133">2 단계: 설치</span><span class="sxs-lookup"><span data-stu-id="648e0-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="648e0-134">Microsoft 365 보안 센터에 액세스 하는 초기 단계를 수행 하 여 Microsoft 365 Defender 평가판 lab 또는 파일럿 환경을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="648e0-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="648e0-135">다음을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="648e0-135">You'll be guided to:</span></span><br><br><span data-ttu-id="648e0-136">-Microsoft 365 E5 평가판 등록</span><span class="sxs-lookup"><span data-stu-id="648e0-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="648e0-137">-도메인 구성</span><span class="sxs-lookup"><span data-stu-id="648e0-137">- Configure domain</span></span><br><span data-ttu-id="648e0-138">-Microsoft 365 E5 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="648e0-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="648e0-139">-포털에서 설치 마법사 완료</span><span class="sxs-lookup"><span data-stu-id="648e0-139">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="648e0-140">![3 단계: 온보드 & 구성](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="648e0-140">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="648e0-141">3 단계: 온보드 & 구성</span><span class="sxs-lookup"><span data-stu-id="648e0-141">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="648e0-142">각 Microsoft 365 Defender 기둥 및 온보드 끝점을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="648e0-142">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="648e0-143">다음을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="648e0-143">You'll be guided to:</span></span><br><br><span data-ttu-id="648e0-144">-Office 365 용 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="648e0-144">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="648e0-145">-Microsoft Cloud App Security 구성</span><span class="sxs-lookup"><span data-stu-id="648e0-145">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="648e0-146">-Id를 사용 하 여 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="648e0-146">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="648e0-147">-끝점에 대 한 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="648e0-147">- Configure Microsoft Defender for Endpoint</span></span>


## <a name="in-scope"></a><span data-ttu-id="648e0-148">범위 내</span><span class="sxs-lookup"><span data-stu-id="648e0-148">In scope</span></span>

<span data-ttu-id="648e0-149">이 가이드의 범위에서는 다음과 같은 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="648e0-149">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="648e0-150">Azure Active Directory 설정</span><span class="sxs-lookup"><span data-stu-id="648e0-150">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="648e0-151">Microsoft 365 Defender 설정</span><span class="sxs-lookup"><span data-stu-id="648e0-151">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="648e0-152">파일럿을 실행 하는 경우 Microsoft 365 E5 평가판에 등록 하거나 정식 라이선스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="648e0-152">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="648e0-153">도메인 구성</span><span class="sxs-lookup"><span data-stu-id="648e0-153">Configure domain</span></span>
    -   <span data-ttu-id="648e0-154">Microsoft 365 E5 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="648e0-154">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="648e0-155">포털 내에서 설정 마법사 완료</span><span class="sxs-lookup"><span data-stu-id="648e0-155">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="648e0-156">모범 사례를 기반으로 모든 Microsoft 365 Defender 핵심 요소로를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="648e0-156">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="648e0-157">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="648e0-157">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="648e0-158">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="648e0-158">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="648e0-159">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="648e0-159">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="648e0-160">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="648e0-160">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="648e0-161">범위를 벗어남</span><span class="sxs-lookup"><span data-stu-id="648e0-161">Out of scope</span></span>

<span data-ttu-id="648e0-162">이 배포 가이드의 범위는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="648e0-162">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="648e0-163">Microsoft 365 Defender와 통합할 수 있는 타사 솔루션 구성</span><span class="sxs-lookup"><span data-stu-id="648e0-163">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="648e0-164">프로덕션 환경의 침투 테스트</span><span class="sxs-lookup"><span data-stu-id="648e0-164">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="648e0-165">다음 단계</span><span class="sxs-lookup"><span data-stu-id="648e0-165">Next step</span></span>
<span data-ttu-id="648e0-166">![1 단계: 준비](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="648e0-166">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="648e0-167">[1 단계: 준비](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="648e0-167">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="648e0-168">Microsoft 365 Defender 평가판 랩 또는 파일럿 환경 준비</span><span class="sxs-lookup"><span data-stu-id="648e0-168">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
