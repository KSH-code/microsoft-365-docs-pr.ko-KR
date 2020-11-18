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
ms.openlocfilehash: fe0a06dd104f0f0532363ee046f4bad1c03c5400
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130889"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="97943-104">Microsoft 365 Defender 평가판 랩 또는 파일럿 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="97943-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="97943-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="97943-105">**Applies to:**</span></span>
- <span data-ttu-id="97943-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97943-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="97943-107">이 시험 운용 랩 또는 파일럿 환경을 만드는 목적은 포괄적이 고 통합 된 Microsoft 365 Defender 기능을 보여 주기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="97943-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="97943-108">이 지능형 보안 솔루션은 조직에 고급 위협 요소를 감지, 방지, 자동 조사 및 대응 하는 방법을 경험 합니다.</span><span class="sxs-lookup"><span data-stu-id="97943-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="97943-109">이 가이드에서는 권장 되는 배포 경로를 기반으로 Microsoft 365 Defender evaluation을 시작 하는 단계를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="97943-109">This guide takes you through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="97943-110">목표는 평가판 계정을 사용 하는 랩 환경 또는 프로덕션 환경에서 정식 라이선스로 보안 솔루션을 설정 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97943-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="97943-111">평가판 랩 또는 파일럿 환경을 준비 하면 보안 작업 사용 사례를 조직의 의사 결정자에 게 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97943-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="97943-112">공격 시뮬레이션을 실행 하 고 결과에 만족 하면 조직의 Microsoft 기술 영업 전문가 또는 전문가를 지원 하 여 조직에서이를 완벽 하 게 배포 하 고 operationalize 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97943-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="97943-113">이 가이드는 다음과 같은 작업에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97943-113">This guide will help you:</span></span>
- <span data-ttu-id="97943-114">랩 서버 및 컴퓨터 설정</span><span class="sxs-lookup"><span data-stu-id="97943-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="97943-115">사용자 및 그룹을 사용 하 여 Active Directory 구성</span><span class="sxs-lookup"><span data-stu-id="97943-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="97943-116">Microsoft Defender for Identity, Office 365 용 microsoft Defender, 끝점에 대 한 Microsoft Defender 및 Microsoft Cloud App Security을 설정 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="97943-116">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="97943-117">서버 및 컴퓨터에 대 한 로컬 정책 설정</span><span class="sxs-lookup"><span data-stu-id="97943-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="97943-118">위협 공격을 모방 하 여 Microsoft 365 Defender에서 테스트 인시던트 또는 경고 생성</span><span class="sxs-lookup"><span data-stu-id="97943-118">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="97943-119">최적의 결과를 위해 랩 설치 지침을 최대한 면밀 하 게 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="97943-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="97943-120">배포 단계</span><span class="sxs-lookup"><span data-stu-id="97943-120">Deployment phases</span></span>

<span data-ttu-id="97943-121">Microsoft 365 Defender 평가판 랩 환경을 만들고 배포 하는 과정은 다음 세 단계로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97943-121">There are three phases in creating a Microsoft 365 Defender trial lab environment and deploying it:</span></span>

![배포 단계: prepare, setup, 온보드](../../media/phase-diagrams/deployment-phases.png)

|<span data-ttu-id="97943-123">단계</span><span class="sxs-lookup"><span data-stu-id="97943-123">Phase</span></span> | <span data-ttu-id="97943-124">설명</span><span class="sxs-lookup"><span data-stu-id="97943-124">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="97943-125">1 단계: 준비</span><span class="sxs-lookup"><span data-stu-id="97943-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="97943-126">평가판 랩 또는 파일럿 환경에서 Microsoft 365 Defender를 배포할 때 고려해 야 할 사항에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="97943-126">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="97943-127">-관련자 및 승인</span><span class="sxs-lookup"><span data-stu-id="97943-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="97943-128">-환경 고려 사항</span><span class="sxs-lookup"><span data-stu-id="97943-128">- Environment considerations</span></span> <br><span data-ttu-id="97943-129">-액세스</span><span class="sxs-lookup"><span data-stu-id="97943-129">- Access</span></span> <br><span data-ttu-id="97943-130">-Azure Active Directory 설치</span><span class="sxs-lookup"><span data-stu-id="97943-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="97943-131">-구성 순서</span><span class="sxs-lookup"><span data-stu-id="97943-131">- Configuration order</span></span>
|[<span data-ttu-id="97943-132">2 단계: 설치</span><span class="sxs-lookup"><span data-stu-id="97943-132">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="97943-133">Microsoft 365 보안 센터에 액세스 하는 초기 단계를 수행 하 여 Microsoft 365 Defender 평가판 lab 또는 파일럿 환경을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="97943-133">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="97943-134">다음을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="97943-134">You'll be guided to:</span></span><br><br><span data-ttu-id="97943-135">-Microsoft 365 E5 평가판 등록</span><span class="sxs-lookup"><span data-stu-id="97943-135">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="97943-136">-도메인 구성</span><span class="sxs-lookup"><span data-stu-id="97943-136">- Configure domain</span></span><br><span data-ttu-id="97943-137">-Microsoft 365 E5 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="97943-137">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="97943-138">-포털에서 설치 마법사 완료</span><span class="sxs-lookup"><span data-stu-id="97943-138">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="97943-139">3 단계: 온보드 & 구성</span><span class="sxs-lookup"><span data-stu-id="97943-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="97943-140">각 Microsoft 365 Defender 기둥 및 온보드 끝점을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="97943-140">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="97943-141">다음을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="97943-141">You'll be guided to:</span></span><br><br><span data-ttu-id="97943-142">-Office 365 용 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="97943-142">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="97943-143">-Microsoft Cloud App Security 구성</span><span class="sxs-lookup"><span data-stu-id="97943-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="97943-144">-Id를 사용 하 여 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="97943-144">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="97943-145">-끝점에 대 한 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="97943-145">- Configure Microsoft Defender for Endpoint</span></span>


## <a name="in-scope"></a><span data-ttu-id="97943-146">범위 내</span><span class="sxs-lookup"><span data-stu-id="97943-146">In scope</span></span>

<span data-ttu-id="97943-147">이 가이드의 범위에서는 다음과 같은 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="97943-147">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="97943-148">Azure Active Directory 설정</span><span class="sxs-lookup"><span data-stu-id="97943-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="97943-149">Microsoft 365 Defender 설정</span><span class="sxs-lookup"><span data-stu-id="97943-149">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="97943-150">파일럿을 실행 하는 경우 Microsoft 365 E5 평가판에 등록 하거나 정식 라이선스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="97943-150">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="97943-151">도메인 구성</span><span class="sxs-lookup"><span data-stu-id="97943-151">Configure domain</span></span>
    -   <span data-ttu-id="97943-152">Microsoft 365 E5 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="97943-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="97943-153">포털 내에서 설정 마법사 완료</span><span class="sxs-lookup"><span data-stu-id="97943-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="97943-154">모범 사례를 기반으로 모든 Microsoft 365 Defender 핵심 요소로를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="97943-154">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="97943-155">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="97943-155">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="97943-156">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="97943-156">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="97943-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="97943-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="97943-158">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="97943-158">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="97943-159">범위를 벗어남</span><span class="sxs-lookup"><span data-stu-id="97943-159">Out of scope</span></span>

<span data-ttu-id="97943-160">이 배포 가이드의 범위는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="97943-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="97943-161">Microsoft 365 Defender와 통합할 수 있는 타사 솔루션 구성</span><span class="sxs-lookup"><span data-stu-id="97943-161">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="97943-162">프로덕션 환경의 침투 테스트</span><span class="sxs-lookup"><span data-stu-id="97943-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="97943-163">다음 단계</span><span class="sxs-lookup"><span data-stu-id="97943-163">Next step</span></span>
<span data-ttu-id="97943-164">[1 단계: 준비](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="97943-164">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="97943-165">Microsoft 365 Defender 평가판 랩 또는 파일럿 환경 준비</span><span class="sxs-lookup"><span data-stu-id="97943-165">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
