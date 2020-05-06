---
title: Microsoft Threat Protection 평가
description: Microsoft Threat Protection 평가판 랩 환경을 설정 하 여 장치, id, 데이터 및 응용 프로그램을 보호 하도록 설계 된 위협 방지 솔루션을 통해 조직에서 도움을 제공 하는 방법을 확인할 수 있습니다.
keywords: Microsoft 위협 보호 평가판, microsoft threat protection, microsoft threat protection 평가 랩, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, id, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화 된 조사 및 개선, 고급 구하기
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: f6ee8147965a29b87d84690535116f096e4c6006
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049642"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="d30ec-104">Microsoft Threat Protection 평가판 랩 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="d30ec-104">Create a Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="d30ec-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d30ec-105">**Applies to:**</span></span>
- <span data-ttu-id="d30ec-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="d30ec-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="d30ec-107">이 평가판 랩 환경을 만드는 목적은 검색, 예방, 조사 및 조직에서 사용할 수 있는 응답에 대 한 Microsoft 위협 보호의 포괄적이 고 통합 된 기능을 보여 주기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d30ec-107">The purpose of creating this trial lab environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="d30ec-108">이 가이드에서는 권장 되는 배포 경로를 기반으로 Microsoft Threat Protection 평가를 시작 하는 단계를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ec-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="d30ec-109">이 목표는 조직에서 보안 솔루션 의사 결정권자에 게 발표할 때 랩 환경 또는 개념 증명 (POC)으로 통합 Microsoft 위협 보호 서비스를 설정 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d30ec-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment or as a proof of concept (POC) when presenting to security solution decision makers in your organization.</span></span> <span data-ttu-id="d30ec-110">공격 시뮬레이션이 실행 되 고 자동화 된 조사 및 응답을 수행 하 고 결과에 만족 하면 조직의 Microsoft 기술 영업 전문가 또는 전문가를 지원 하 여 프로덕션 환경에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d30ec-110">When you’re done running your attack simulations, automated investigation and response, and are satisfied with the results, you can deploy it in your production environment with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="d30ec-111">이 가이드는 다음과 같은 작업에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d30ec-111">This guide will help you:</span></span>
- <span data-ttu-id="d30ec-112">랩 서버 및 컴퓨터 설정</span><span class="sxs-lookup"><span data-stu-id="d30ec-112">Set up your lab server and computers</span></span>
- <span data-ttu-id="d30ec-113">사용자 및 그룹을 사용 하 여 Active Directory 구성</span><span class="sxs-lookup"><span data-stu-id="d30ec-113">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="d30ec-114">Azure ATP, Office ATP, Microsoft Defender ATP 및 Microsoft Cloud App Security를 설정 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ec-114">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="d30ec-115">서버 및 컴퓨터에 대 한 로컬 정책 설정</span><span class="sxs-lookup"><span data-stu-id="d30ec-115">Setup local policies for your server and computers</span></span>
- <span data-ttu-id="d30ec-116">위협 공격을 모방 하 여 Microsoft Threat Protection에서 테스트 인시던트 또는 경고 생성</span><span class="sxs-lookup"><span data-stu-id="d30ec-116">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="d30ec-117">최적의 결과를 위해 랩 설치 지침을 최대한 면밀 하 게 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d30ec-117">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="d30ec-118">배포 단계</span><span class="sxs-lookup"><span data-stu-id="d30ec-118">Deployment phases</span></span>

<span data-ttu-id="d30ec-119">Microsoft Threat Protection 평가판 랩 환경을 만들고 배포 하는 과정은 다음 세 단계로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d30ec-119">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="d30ec-120">단계</span><span class="sxs-lookup"><span data-stu-id="d30ec-120">Phase</span></span> | <span data-ttu-id="d30ec-121">설명</span><span class="sxs-lookup"><span data-stu-id="d30ec-121">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="d30ec-122">![1 단계: 준비](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="d30ec-122">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="d30ec-123">1 단계: 준비</span><span class="sxs-lookup"><span data-stu-id="d30ec-123">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="d30ec-124">평가판 랩 환경에서 Microsoft 위협 보호를 배포할 때 고려해 야 할 사항에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d30ec-124">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab environment:</span></span> <br><br><span data-ttu-id="d30ec-125">-관련자 및 승인</span><span class="sxs-lookup"><span data-stu-id="d30ec-125">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="d30ec-126">-환경 고려 사항</span><span class="sxs-lookup"><span data-stu-id="d30ec-126">- Environment considerations</span></span> <br><span data-ttu-id="d30ec-127">-액세스</span><span class="sxs-lookup"><span data-stu-id="d30ec-127">- Access</span></span> <br><span data-ttu-id="d30ec-128">-Azure Active Directory 설치</span><span class="sxs-lookup"><span data-stu-id="d30ec-128">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="d30ec-129">-구성 순서</span><span class="sxs-lookup"><span data-stu-id="d30ec-129">- Configuration order</span></span>
|  <span data-ttu-id="d30ec-130">![2 단계: 설치](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="d30ec-130">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="d30ec-131">2 단계: 설치</span><span class="sxs-lookup"><span data-stu-id="d30ec-131">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="d30ec-132">Microsoft 365 보안 센터에 액세스 하 여 Microsoft Threat Protection 평가판 랩 환경을 설정 하기 위한 초기 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ec-132">Take the initial steps to access Microsoft 365 Security Center to setup your Microsoft Threat Protection trial lab environment.</span></span> <span data-ttu-id="d30ec-133">다음을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ec-133">You will be guided to:</span></span><br><br><span data-ttu-id="d30ec-134">-Microsoft 365 E5 평가판 등록</span><span class="sxs-lookup"><span data-stu-id="d30ec-134">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="d30ec-135">-도메인 구성</span><span class="sxs-lookup"><span data-stu-id="d30ec-135">- Configure domain</span></span><br><span data-ttu-id="d30ec-136">-Microsoft 365 E5 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="d30ec-136">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="d30ec-137">-포털에서 설치 마법사 완료</span><span class="sxs-lookup"><span data-stu-id="d30ec-137">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="d30ec-138">![3 단계: 온보드 & 구성](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="d30ec-138">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="d30ec-139">3 단계: 온보드 & 구성</span><span class="sxs-lookup"><span data-stu-id="d30ec-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="d30ec-140">각 Microsoft Threat Protection 기둥 및 온보드 끝점을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ec-140">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="d30ec-141">다음을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ec-141">You will be guided to:</span></span><br><br><span data-ttu-id="d30ec-142">-Office 365 Advanced Threat Protection 구성</span><span class="sxs-lookup"><span data-stu-id="d30ec-142">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="d30ec-143">-Microsoft Cloud App Security 구성</span><span class="sxs-lookup"><span data-stu-id="d30ec-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="d30ec-144">-Azure Advanced Threat Protection 구성</span><span class="sxs-lookup"><span data-stu-id="d30ec-144">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="d30ec-145">-Microsoft Defender Advanced Threat Protection 구성</span><span class="sxs-lookup"><span data-stu-id="d30ec-145">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="d30ec-146">범위 내</span><span class="sxs-lookup"><span data-stu-id="d30ec-146">In scope</span></span>

<span data-ttu-id="d30ec-147">이 평가판 랩 환경 가이드의 범위는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d30ec-147">The following is in scope for this trial lab environment guide:</span></span>
-   <span data-ttu-id="d30ec-148">Azure Active Directory 설정</span><span class="sxs-lookup"><span data-stu-id="d30ec-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="d30ec-149">Microsoft Threat Protection 설정</span><span class="sxs-lookup"><span data-stu-id="d30ec-149">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="d30ec-150">Microsoft 365 E5 평가판 등록</span><span class="sxs-lookup"><span data-stu-id="d30ec-150">Sign up for Microsoft 365 E5 Trial</span></span>
    -   <span data-ttu-id="d30ec-151">도메인 구성</span><span class="sxs-lookup"><span data-stu-id="d30ec-151">Configure domain</span></span>
    -   <span data-ttu-id="d30ec-152">Microsoft 365 E5 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="d30ec-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="d30ec-153">포털 내에서 설정 마법사 완료</span><span class="sxs-lookup"><span data-stu-id="d30ec-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="d30ec-154">모범 사례에 따라 모든 Microsoft Threat Protection 핵심 요소로를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ec-154">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="d30ec-155">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d30ec-155">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="d30ec-156">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d30ec-156">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="d30ec-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d30ec-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="d30ec-158">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d30ec-158">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="d30ec-159">범위를 벗어남</span><span class="sxs-lookup"><span data-stu-id="d30ec-159">Out of scope</span></span>

<span data-ttu-id="d30ec-160">이 배포 가이드의 범위는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d30ec-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="d30ec-161">Microsoft Defender ATP와 통합할 수 있는 타사 솔루션 구성</span><span class="sxs-lookup"><span data-stu-id="d30ec-161">Configuration of third-party solutions that might integrate with Microsoft Defender ATP</span></span>
-   <span data-ttu-id="d30ec-162">프로덕션 환경의 침투 테스트</span><span class="sxs-lookup"><span data-stu-id="d30ec-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="d30ec-163">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d30ec-163">Next step</span></span>
|||
|:-------|:-----|
|<span data-ttu-id="d30ec-164">![1 단계: 준비](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="d30ec-164">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br>[<span data-ttu-id="d30ec-165">1 단계: 준비</span><span class="sxs-lookup"><span data-stu-id="d30ec-165">Phase 1: Prepare</span></span>](prepare-mtpeval.md) | <span data-ttu-id="d30ec-166">Microsoft Threat Protection 평가 랩 환경 준비</span><span class="sxs-lookup"><span data-stu-id="d30ec-166">Prepare your Microsoft Threat Protection evaluation lab environment</span></span>
