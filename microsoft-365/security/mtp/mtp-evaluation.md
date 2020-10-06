---
title: Microsoft Threat Protection 사용 설정
description: Microsoft Threat Protection 평가판 랩 또는 파일럿 환경을 설정 하 여 장치, id, 데이터 및 응용 프로그램을 보호 하도록 설계 된 위협 방어 보호 솔루션을 통해 조직에서 도움을 얻을 수 있는 방법을 확인 하세요.
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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 3768937fc882fee8d6a744e4fb504095882c7e81
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48368062"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="c9f1d-104">Microsoft Threat Protection 평가판 랩 또는 파일럿 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="c9f1d-104">Create a Microsoft Threat Protection trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c9f1d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c9f1d-105">**Applies to:**</span></span>
- <span data-ttu-id="c9f1d-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="c9f1d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c9f1d-107">이 시험 운용 랩 또는 파일럿 환경을 만드는 목적은 검색, 예방, 조사 및 조직에서 사용할 수 있는 응답에 대 한 Microsoft 위협 보호의 포괄적이 고 통합 된 기능을 보여 주기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c9f1d-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="c9f1d-108">이 가이드에서는 권장 되는 배포 경로를 기반으로 Microsoft Threat Protection 평가를 시작 하는 단계를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9f1d-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="c9f1d-109">목표는 평가판 계정을 사용 하는 경우 랩 환경에서 통합 Microsoft 위협 보호 서비스를 설정 하는 데 도움이 되거나 정식 라이선스를 사용 하는 경우 프로덕션 환경의 파일럿 환경에 설치 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c9f1d-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment when using a trial account, or in a pilot environment in production when using a full license.</span></span> <span data-ttu-id="c9f1d-110">결과는 조직의 보안 솔루션 의사 결정권자에 게 보안 작업 사용 사례를 제공 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9f1d-110">The results of which will be useful in presenting security operation use cases to security solution decision makers in your organization.</span></span> <span data-ttu-id="c9f1d-111">공격 시뮬레이션을 실행 하 고 결과에 만족 하면 조직의 Microsoft 기술 영업 전문가 또는 전문가를 위한 도움을 사용 하 여 조직에서이를 완벽 하 게 배포 하 고 operationalize 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9f1d-111">When you’re done running your attack simulations, and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="c9f1d-112">이 가이드는 다음과 같은 작업에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9f1d-112">This guide will help you:</span></span>
- <span data-ttu-id="c9f1d-113">랩 서버 및 컴퓨터 설정</span><span class="sxs-lookup"><span data-stu-id="c9f1d-113">Set up your lab server and computers</span></span>
- <span data-ttu-id="c9f1d-114">사용자 및 그룹을 사용 하 여 Active Directory 구성</span><span class="sxs-lookup"><span data-stu-id="c9f1d-114">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="c9f1d-115">Azure ATP, Office ATP, Microsoft Defender ATP 및 Microsoft Cloud App Security를 설정 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9f1d-115">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="c9f1d-116">서버 및 컴퓨터에 대 한 로컬 정책 설정</span><span class="sxs-lookup"><span data-stu-id="c9f1d-116">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="c9f1d-117">위협 공격을 모방 하 여 Microsoft Threat Protection에서 테스트 인시던트 또는 경고 생성</span><span class="sxs-lookup"><span data-stu-id="c9f1d-117">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="c9f1d-118">최적의 결과를 위해 랩 설치 지침을 최대한 면밀 하 게 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c9f1d-118">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="c9f1d-119">배포 단계</span><span class="sxs-lookup"><span data-stu-id="c9f1d-119">Deployment phases</span></span>

<span data-ttu-id="c9f1d-120">Microsoft Threat Protection 평가판 랩 환경을 만들고 배포 하는 과정은 다음 세 단계로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9f1d-120">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="c9f1d-121">단계</span><span class="sxs-lookup"><span data-stu-id="c9f1d-121">Phase</span></span> | <span data-ttu-id="c9f1d-122">설명</span><span class="sxs-lookup"><span data-stu-id="c9f1d-122">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="c9f1d-123">![1 단계: 준비](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="c9f1d-123">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="c9f1d-124">1 단계: 준비</span><span class="sxs-lookup"><span data-stu-id="c9f1d-124">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="c9f1d-125">평가판 랩 또는 파일럿 환경에서 Microsoft 위협 보호를 배포할 때 고려해 야 할 사항에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c9f1d-125">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="c9f1d-126">-관련자 및 승인</span><span class="sxs-lookup"><span data-stu-id="c9f1d-126">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="c9f1d-127">-환경 고려 사항</span><span class="sxs-lookup"><span data-stu-id="c9f1d-127">- Environment considerations</span></span> <br><span data-ttu-id="c9f1d-128">-액세스</span><span class="sxs-lookup"><span data-stu-id="c9f1d-128">- Access</span></span> <br><span data-ttu-id="c9f1d-129">-Azure Active Directory 설치</span><span class="sxs-lookup"><span data-stu-id="c9f1d-129">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="c9f1d-130">-구성 순서</span><span class="sxs-lookup"><span data-stu-id="c9f1d-130">- Configuration order</span></span>
|  <span data-ttu-id="c9f1d-131">![2 단계: 설치](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="c9f1d-131">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="c9f1d-132">2 단계: 설치</span><span class="sxs-lookup"><span data-stu-id="c9f1d-132">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="c9f1d-133">Microsoft 365 보안 센터에 액세스 하는 초기 단계를 수행 하 여 Microsoft Threat Protection 평가판 랩 또는 파일럿 환경을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9f1d-133">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft Threat Protection trial lab or pilot environment.</span></span> <span data-ttu-id="c9f1d-134">다음을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9f1d-134">You'll be guided to:</span></span><br><br><span data-ttu-id="c9f1d-135">-Microsoft 365 E5 평가판 등록</span><span class="sxs-lookup"><span data-stu-id="c9f1d-135">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="c9f1d-136">-도메인 구성</span><span class="sxs-lookup"><span data-stu-id="c9f1d-136">- Configure domain</span></span><br><span data-ttu-id="c9f1d-137">-Microsoft 365 E5 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="c9f1d-137">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="c9f1d-138">-포털에서 설치 마법사 완료</span><span class="sxs-lookup"><span data-stu-id="c9f1d-138">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="c9f1d-139">![3 단계: 온보드 & 구성](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="c9f1d-139">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="c9f1d-140">3 단계: 온보드 & 구성</span><span class="sxs-lookup"><span data-stu-id="c9f1d-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="c9f1d-141">각 Microsoft Threat Protection 기둥 및 온보드 끝점을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9f1d-141">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="c9f1d-142">다음을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9f1d-142">You'll be guided to:</span></span><br><br><span data-ttu-id="c9f1d-143">-Office 365 Advanced Threat Protection 구성</span><span class="sxs-lookup"><span data-stu-id="c9f1d-143">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="c9f1d-144">-Microsoft Cloud App Security 구성</span><span class="sxs-lookup"><span data-stu-id="c9f1d-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="c9f1d-145">-Azure Advanced Threat Protection 구성</span><span class="sxs-lookup"><span data-stu-id="c9f1d-145">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="c9f1d-146">-Microsoft Defender Advanced Threat Protection 구성</span><span class="sxs-lookup"><span data-stu-id="c9f1d-146">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="c9f1d-147">범위 내</span><span class="sxs-lookup"><span data-stu-id="c9f1d-147">In scope</span></span>

<span data-ttu-id="c9f1d-148">이 가이드의 범위에서는 다음과 같은 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9f1d-148">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="c9f1d-149">Azure Active Directory 설정</span><span class="sxs-lookup"><span data-stu-id="c9f1d-149">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="c9f1d-150">Microsoft Threat Protection 설정</span><span class="sxs-lookup"><span data-stu-id="c9f1d-150">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="c9f1d-151">파일럿을 실행 하는 경우 Microsoft 365 E5 평가판에 등록 하거나 정식 라이선스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9f1d-151">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="c9f1d-152">도메인 구성</span><span class="sxs-lookup"><span data-stu-id="c9f1d-152">Configure domain</span></span>
    -   <span data-ttu-id="c9f1d-153">Microsoft 365 E5 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="c9f1d-153">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="c9f1d-154">포털 내에서 설정 마법사 완료</span><span class="sxs-lookup"><span data-stu-id="c9f1d-154">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="c9f1d-155">모범 사례에 따라 모든 Microsoft Threat Protection 핵심 요소로를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9f1d-155">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="c9f1d-156">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c9f1d-156">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="c9f1d-157">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c9f1d-157">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="c9f1d-158">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c9f1d-158">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="c9f1d-159">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c9f1d-159">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="c9f1d-160">범위를 벗어남</span><span class="sxs-lookup"><span data-stu-id="c9f1d-160">Out of scope</span></span>

<span data-ttu-id="c9f1d-161">이 배포 가이드의 범위는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9f1d-161">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="c9f1d-162">Microsoft Threat Protection과 통합할 수 있는 타사 솔루션 구성</span><span class="sxs-lookup"><span data-stu-id="c9f1d-162">Configuration of third-party solutions that might integrate with Microsoft Threat Protection</span></span>
-   <span data-ttu-id="c9f1d-163">프로덕션 환경의 침투 테스트</span><span class="sxs-lookup"><span data-stu-id="c9f1d-163">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="c9f1d-164">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c9f1d-164">Next step</span></span>
<span data-ttu-id="c9f1d-165">![1 단계: 준비](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="c9f1d-165">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="c9f1d-166">[1 단계: 준비](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="c9f1d-166">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="c9f1d-167">Microsoft Threat Protection 평가판 랩 또는 파일럿 환경 준비</span><span class="sxs-lookup"><span data-stu-id="c9f1d-167">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>
