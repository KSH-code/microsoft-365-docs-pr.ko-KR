---
title: Microsoft 365 Enterprise 기본 인프라
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 03/05/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 조직에서 Microsoft 365 Enterprise 기본 인프라를 배포하는 주요 단계를 이해합니다.
ms.openlocfilehash: 668775097eeffff569b99cc9fe4cd259f5d25c22
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287132"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure"></a><span data-ttu-id="bbc5d-103">Microsoft 365 Enterprise 기본 인프라</span><span class="sxs-lookup"><span data-stu-id="bbc5d-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="bbc5d-104">Microsoft 365 Enterprise의 종단 간 배포를 하는 경우, 먼저 응용프로그램 및 서비스가 보안 환경에서 창의성과 팀워크를 해제할 수 있는 안전한 기초 위에 구축해야합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-104">If you're doing the end-to-end deployment of Microsoft 365 Enterprise yourself, you should first build a firm foundation upon which applications and services can unlock creativity and teamwork in a secure environment.</span></span> 

<span data-ttu-id="bbc5d-105">배포에 대한 종단 간 경로에 있어서 Microsoft 365 Enterprise 의 기초 인프라 배포와 계획을 위해 이러한 단계들을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-105">For a defined end-to-end path for deployment, you can use these phases to plan for and deploy the foundation infrastructure of Microsoft 365 Enterprise:</span></span>

| | <span data-ttu-id="bbc5d-106">단계</span><span class="sxs-lookup"><span data-stu-id="bbc5d-106">Phase</span></span> | <span data-ttu-id="bbc5d-107">결과</span><span class="sxs-lookup"><span data-stu-id="bbc5d-107">Results</span></span> |
|:-------|:-----|:-----|
|![](./media/deploy-foundation-infrastructure/networking_icon-small.png)|[<span data-ttu-id="bbc5d-108">1단계: 네트워킹</span><span class="sxs-lookup"><span data-stu-id="bbc5d-108">Phase 1: Networking</span></span>](networking-infrastructure.md)| <span data-ttu-id="bbc5d-109">Microsoft 365 클라우드 기반 서비스에 액세스 하기 위해 네트워크가 최적화 되어있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-109">Your network is optimized for access to Microsoft 365's cloud-based services.</span></span> |
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)|[<span data-ttu-id="bbc5d-110">2단계: ID</span><span class="sxs-lookup"><span data-stu-id="bbc5d-110">Phase 2: Identity</span></span>](identity-infrastructure.md)| <span data-ttu-id="bbc5d-111">관리자 계정이 보호되고, 사용자 및 그룹은 동기화되며, 사용자 인증은 강력합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-111">Your admin accounts are protected, your users and groups are synchronized, and your user authentication is strong.</span></span> |
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[<span data-ttu-id="bbc5d-112">3단계: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bbc5d-112">Phase 3: Windows 10 Enterprise</span></span>](windows10-infrastructure.md)| <span data-ttu-id="bbc5d-113">기존 Windows 기반 컴퓨터는 Windows 10 Enterprise를 업그레이드 할 수 있으며 새 장치는 Windows 10 Enterprise와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-113">Your existing Windows-based computers can upgrade to Windows 10 Enterprise and new devices are installed with Windows 10 Enterprise.</span></span> |
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[<span data-ttu-id="bbc5d-114">4단계: Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="bbc5d-114">Phase 4: Office 365 ProPlus</span></span>](office365proplus-infrastructure.md)| <span data-ttu-id="bbc5d-115">기존 사용자의 Microsoft Office는 Office 365 ProPlus으로 업그레이드 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-115">Your existing users of Microsoft Office can upgrade to Office 365 ProPlus.</span></span> |
|![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[<span data-ttu-id="bbc5d-116">5단계: 모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="bbc5d-116">Phase 5: Mobile device management</span></span>](mobility-infrastructure.md)| <span data-ttu-id="bbc5d-117">장치를 등록하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-117">Your devices can be enrolled and managed.</span></span> |
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[<span data-ttu-id="bbc5d-118">6단계: 정보 보호</span><span class="sxs-lookup"><span data-stu-id="bbc5d-118">Phase 6: Information protection</span></span>](infoprotect-infrastructure.md)| <span data-ttu-id="bbc5d-119">레이블은 문서를 보호할 준비가 되어있고 Office 365 보안 기능은 사용가능하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-119">Your labels are ready to protect documents and Office 365 security features are enabled.</span></span> |

<span data-ttu-id="bbc5d-120">이 단계들은 가장 기초적인 (네트워킹 및 아이디) 것으로 시작하며 인프라 설정 및 그룹들을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-120">The phases start with the most foundational (networking and identity), and then create layers of infrastructure settings and groups to:</span></span>

- <span data-ttu-id="bbc5d-121">장치에 가장 안전하고 최신 버전의 Windows를 설치하십시오. </span><span class="sxs-lookup"><span data-stu-id="bbc5d-121">Install the most current and secure version of Windows on your devices.</span></span>
- <span data-ttu-id="bbc5d-122">장치에 최신 버전의 Office를 설치하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-122">Install the most current version of Office on your devices.</span></span>
- <span data-ttu-id="bbc5d-123">조직의 장치를 관리하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-123">Manage your organization's devices.</span></span>
- <span data-ttu-id="bbc5d-124">클라우드에서 장치에 대한 정보를 보호하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-124">Protect the information on those devices and in the cloud.</span></span>

<span data-ttu-id="bbc5d-125">하지만 IT 리소스 및 비즈니스 요구에 맞는 단계 내에서 절차 및 단계를 유연하게 구성하고 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-125">However, you have the flexibility of configuring and rolling out the phases or steps within phases to fit your IT resources and business needs.</span></span>

- <span data-ttu-id="bbc5d-126">**더 작고 최신 조직인 경우**, 조직적으로 인프라를 구축하기 위해 필요한 단계를 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-126">**If you are a smaller or newer organization**, follow the phases as needed to methodically build out your infrastructure.</span></span>

-  <span data-ttu-id="bbc5d-127">**엔터프라이즈 조직인 경우**, 규정된 경로 보다는 IT 인프라 단계를 살펴보십시오. 그리고 조직 전체에서 각 레이어의 요구 사항을 최종적으로 준수하는 가장 효과적인 방법을 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-127">**If you are an enterprise organization**, view the phases as layers of IT infrastructure, rather than a defined path, and determine how to best work toward eventual adherence to the requirements for each layer across your organization.</span></span>

<span data-ttu-id="bbc5d-128">각 작업 단계의 끝에서, 충족해야 할 필수 조건과 선택 조건을 포함하는 종료 기준을 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-128">At the end of each phase, you should examine its exit criteria, which include required conditions that you must meet and optional conditions to consider.</span></span> <span data-ttu-id="bbc5d-129">각 단계의 종료 기준에서 온 프레미스 및 클라우드 인프라 그리고 종단간 구성 결과가 Microsoft 365 Enterprise 배포의 요구조건을 충족하는지 확인해야합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-129">Before you can exit each phase, you must examine its exit criteria, which is a set of required conditions that you must meet and optional conditions to consider. Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meet the requirements for a Microsoft 365 Enterprise deployment.</span></span>

<span data-ttu-id="bbc5d-130">콘텐츠 구성 방식을 알아보려면 이 짧은 비디오를 시청 하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-130">To see how the content is structured, watch this short video.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

<span data-ttu-id="bbc5d-131">전체 Microsoft 365 Enterprise 배포 가이드에서 기초 인프라는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-131">Here's the foundation infrastructure in the overall Microsoft 365 Enterprise deployment guide:</span></span>

![](./media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="infrastructure-configuration-vs-user-rollout"></a><span data-ttu-id="bbc5d-132">인프라 구성 대 사용자 공개</span><span class="sxs-lookup"><span data-stu-id="bbc5d-132">Infrastructure configuration vs. user rollout</span></span>

<span data-ttu-id="bbc5d-133">기초 인프라는 사용자가 함께 병행될 때, Microsoft Enterprise 365에서 제공하는 기능 및 보호의 전체 스펙트럼을 활용하게 해주는 구성된 소프트웨어와 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-133">The foundation infrastructure is a set of configured software and services that, when combined together for a user, allow them to take advantage of the entire spectrum of capabilities and protections that Microsoft 365 Enterprise offers.</span></span> <span data-ttu-id="bbc5d-134">종단 간 배포 이동의 최종 목적은 이 인프라를 모든 사용자 및 해당 Windows 기반 장치에 적용하도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-134">The ultimate destination of your end-to-end deployment journey is to have this infrastructure apply to all of your users and their Windows-based devices.</span></span> 

<span data-ttu-id="bbc5d-135">그러나 Microsoft 365 Enterprise 기초 인프라가 사용자를 위한 개별된 소프트웨어 및 서비스의 시작이라는 사실을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-135">However, it is important to note that the Microsoft 365 Enterprise foundation infrastructure is independent of the rollout of software and services to your users.</span></span> <span data-ttu-id="bbc5d-136">***모든 사용자에게 해당 레이어를 공개하지 않고도 기초 인프라의 레이어를 구성할 수 있습니다.***</span><span class="sxs-lookup"><span data-stu-id="bbc5d-136">***You can configure the layers of the foundation infrastructure without having to roll out those layers to all of your users.***</span></span>

<span data-ttu-id="bbc5d-137">따라서 조직의 사무실, 지역 또는 부서에서 많은 사용자를 위한 구성 요소 전에 기초 인프라의 요소들을 구성하고 테스트하며 시험 사용하는 것이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-137">Therefore, it is possible to configure, test, and pilot elements of the foundation infrastructure well ahead of the rollout of those elements to the multitude of your users in the offices, regions, or divisions of your organization.</span></span>

<span data-ttu-id="bbc5d-138">예를 들어, 설정을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-138">For example, you create the settings for:</span></span>

| <span data-ttu-id="bbc5d-139">단계</span><span class="sxs-lookup"><span data-stu-id="bbc5d-139">Phase</span></span> | <span data-ttu-id="bbc5d-140">결과</span><span class="sxs-lookup"><span data-stu-id="bbc5d-140">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="bbc5d-141">ID</span><span class="sxs-lookup"><span data-stu-id="bbc5d-141">Identity</span></span> | <span data-ttu-id="bbc5d-142">계정 동기화와 ID를 기반으로 조건부 액세스 정책에 대 한 그룹.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-142">Account synchronization and groups for identity-based conditional access policies.</span></span> |
| <span data-ttu-id="bbc5d-143">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bbc5d-143">Windows 10 Enterprise</span></span> | <span data-ttu-id="bbc5d-144">실행 중인 Windows 7 또는 Windows 8.1을 Windows 10 Enterprise로 자동으로 업그레이드 할 수 있는 그룹.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-144">Groups to automatically upgrade computers running Windows 7 or Windows 8.1 to Windows 10 Enterprise in place.</span></span> |
| <span data-ttu-id="bbc5d-145">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="bbc5d-145">Office 365 ProPlus</span></span> | <span data-ttu-id="bbc5d-146">그룹을 자동으로 Office 2010, Office 2013 또는 Office 2016의 사용자를 위해 Office 365 ProPlus를 배포하는 그룹.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-146">Groups to automatically deploy Office 365 ProPlus for users with Office 2010, Office 2013, or Office 2016.</span></span> |
| <span data-ttu-id="bbc5d-147">모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="bbc5d-147">Mobile device management</span></span> | <span data-ttu-id="bbc5d-148">장치 등록 및 장치 기반 조건부 액세스 정책에 대한 그룹.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-148">Groups for device enrollment and device-based conditional access policies.</span></span> |
| <span data-ttu-id="bbc5d-149">정보 보호</span><span class="sxs-lookup"><span data-stu-id="bbc5d-149">Information protection</span></span> | <span data-ttu-id="bbc5d-150">Office 365 및 Azure 정보 보호 레이블 및 그룹.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-150">Office 365 labels and Azure Information Protection labels</span></span> |

<span data-ttu-id="bbc5d-151">사용자를 위한 인프라 구성요소를 공개할 준비가 된 경우.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-151">When you are ready to rollout elements of this infrastructure to users, you:</span></span>

| <span data-ttu-id="bbc5d-152">단계</span><span class="sxs-lookup"><span data-stu-id="bbc5d-152">Phase</span></span> | <span data-ttu-id="bbc5d-153">공개 작업</span><span class="sxs-lookup"><span data-stu-id="bbc5d-153">Rollout action</span></span> |
|:-------|:-----|
| <span data-ttu-id="bbc5d-154">ID</span><span class="sxs-lookup"><span data-stu-id="bbc5d-154">Identity</span></span> | <span data-ttu-id="bbc5d-155">ID 기반의 조건부 액세스 정책에 대한 그룹에 사용자 계정을 추가하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-155">Add user accounts to the groups for identity-based conditional access policies.</span></span> |
| <span data-ttu-id="bbc5d-156">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bbc5d-156">Windows 10 Enterprise</span></span> | <span data-ttu-id="bbc5d-157">Windows 7 또는 Windows 8.1 사용자를 위해 Windows 10 Enterprise를 자동으로 배포하는 그룹에 계정을 추가하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-157">Add accounts to the groups to automatically deploy Windows 10 Enterprise in place for users with Windows 7 or Windows 8.1.</span></span> |
| <span data-ttu-id="bbc5d-158">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="bbc5d-158">Office 365 ProPlus</span></span> | <span data-ttu-id="bbc5d-159">Office 2010, Office 2013 또는 Office 2016의 사용자를 위해 Office 365 ProPlus를 자동으로 배포하는 그룹에 사용자 계정을 추가하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-159">Add user accounts to the groups to automatically deploy Office 365 ProPlus for users with Office 2010, Office 2013, or Office 2016.</span></span> |
| <span data-ttu-id="bbc5d-160">모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="bbc5d-160">Mobile device management</span></span> | <span data-ttu-id="bbc5d-161">장치 등록 및 장치 기반 조건부 액세스 정책에 대한 그룹에 계정을 추가하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-161">Add accounts to the groups for device enrollment and device-based conditional access policies.</span></span> |
| <span data-ttu-id="bbc5d-162">정보 보호</span><span class="sxs-lookup"><span data-stu-id="bbc5d-162">Information protection</span></span> | <span data-ttu-id="bbc5d-163">정보 보호 레이블에 대한 그룹에 사용자 계정을 추가하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-163">Add user accounts to the groups for Information Protection labels.</span></span> |

<span data-ttu-id="bbc5d-164">기초 인프라를 완료하고 테스트하며 시험 사용한 경우, Windows 10 Enterprise 및 Office 365 ProPlus와 같은 설치된 소프트웨어와, 장치 등록 및 조건부 액세스 정책과 같은 클라우드 기반 서비스 및 보호 기능을 비즈니스 목적 및 IT 리소스에 최적화된 방식으로 사용자에게 공개할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-164">Once the foundation infrastructure is completed, tested, and piloted, you can roll out installed software, such as Windows 10 Enterprise and Office 365 ProPlus, and cloud-based services and protections, such as device enrollment and conditional access policies, to your users in the manner that best fits your business goals and IT resources.</span></span>

## <a name="deployment-and-project-management-strategies"></a><span data-ttu-id="bbc5d-165">배포 및 프로젝트 관리 전략</span><span class="sxs-lookup"><span data-stu-id="bbc5d-165">Deployment and project management strategies</span></span>

<span data-ttu-id="bbc5d-166">시험 사용자 및 조직의 나머지를 위한 기초 인프라의 각 단계 프로젝트 관리에 접근하는 방법에 대한 몇 가지 아이디어를 제공하기 위해 [배포 전략](deployment-strategies-microsoft-365-enterprise.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-166">To give you some ideas on how to approach the project management of the different phases of the foundation infrastructure for pilot users and the rest of your organization, see [deployment strategies](deployment-strategies-microsoft-365-enterprise.md).</span></span>


## <a name="next-step"></a><span data-ttu-id="bbc5d-167">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bbc5d-167">Next step</span></span>

- <span data-ttu-id="bbc5d-168">Office 365, Enterprise 편리성 + 안전성 (EMS) 또는 Windows 10 Enterprise에 대한 기존 인프라를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-168">I have existing infrastructure for Office 365, Enterprise Mobility + Security (EMS), or Windows 10 Enterprise:</span></span>
  - <span data-ttu-id="bbc5d-169">[기존 인프라를 사용하여 배포](deploy-with-existing-infrastructure.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-169">See [Deploy with existing infrastructure](deploy-with-existing-infrastructure.md).</span></span> <span data-ttu-id="bbc5d-170">이 기사는 각 단계에 대한 종료 기준을 통해 단계별로 나아가게 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-170">This article steps you through the exit criteria for each phase.</span></span>
- <span data-ttu-id="bbc5d-171">처음부터 새로 시작하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-171">I'm starting from scratch:</span></span> 
   - <span data-ttu-id="bbc5d-172">[1 단계: 네트워킹](networking-infrastructure.md)으로 종단 간 배포의 첫걸음을 시작해보십시오.</span><span class="sxs-lookup"><span data-stu-id="bbc5d-172">Otherwise, you can begin your Microsoft 365 Enterprise end-to-end deployment journey with [Phase 1: Networking](networking-infrastructure.md).</span></span>
