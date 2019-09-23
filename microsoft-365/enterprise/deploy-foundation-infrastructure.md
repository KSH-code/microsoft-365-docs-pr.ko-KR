---
title: Microsoft 365 Enterprise 기본 인프라
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 조직에 Microsoft 365 Enterprise의 기본 인프라를 배포하는 주요 단계(핵심 배포라고도 함)를 이해합니다.
ms.openlocfilehash: 016764333b7234681aa06e511227b203f9c9eaea
ms.sourcegitcommit: 78fa107271252d902e600196a75cfa746bca73e6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2019
ms.locfileid: "37050309"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure"></a><span data-ttu-id="168a6-103">Microsoft 365 Enterprise 기본 인프라</span><span class="sxs-lookup"><span data-stu-id="168a6-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="168a6-104">Microsoft 365 Enterprise의 종단 간 배포를 하는 경우, 먼저 응용프로그램 및 서비스가 보안 환경에서 창의성과 팀워크를 해제할 수 있는 안전한 기초 위에 구축해야합니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-104">If you're doing the end-to-end deployment of Microsoft 365 Enterprise yourself, you should first build a firm foundation upon which applications and services can unlock creativity and teamwork in a secure environment.</span></span> <span data-ttu-id="168a6-105">이 기초를 *핵심 배포*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-105">This foundation is sometimes referred to as the core deployment.</span></span>

<span data-ttu-id="168a6-106">배포에 대한 종단 간 경로에 있어서 Microsoft 365 Enterprise 의 기초 인프라 배포와 계획을 위해 이러한 단계들을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-106">For a defined end-to-end path for deployment, you can use these phases to plan for and deploy the foundation infrastructure of Microsoft 365 Enterprise:</span></span>

| | <span data-ttu-id="168a6-107">단계</span><span class="sxs-lookup"><span data-stu-id="168a6-107">Phase</span></span> | <span data-ttu-id="168a6-108">결과</span><span class="sxs-lookup"><span data-stu-id="168a6-108">Results</span></span> |
|:-------|:-----|:-----|
|![](./media/deploy-foundation-infrastructure/networking_icon-small.png)|[<span data-ttu-id="168a6-109">1단계: 네트워킹</span><span class="sxs-lookup"><span data-stu-id="168a6-109">Phase 1: Networking</span></span>](networking-infrastructure.md)| <span data-ttu-id="168a6-110">Microsoft 365 클라우드 기반 서비스에 액세스 하기 위해 네트워크가 최적화 되어있습니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-110">Your network is optimized for access to Microsoft 365's cloud-based services.</span></span> |
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)|[<span data-ttu-id="168a6-111">2단계: ID</span><span class="sxs-lookup"><span data-stu-id="168a6-111">Phase 2: Identity</span></span>](identity-infrastructure.md)| <span data-ttu-id="168a6-112">관리자 계정이 보호되고, 사용자 및 그룹은 동기화되며, 사용자 인증은 강력합니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-112">Your admin accounts are protected, your users and groups are synchronized, and your user authentication is strong.</span></span> |
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[<span data-ttu-id="168a6-113">3단계: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="168a6-113">Phase 3: Windows 10 Enterprise</span></span>](windows10-infrastructure.md)| <span data-ttu-id="168a6-114">기존 Windows 기반 컴퓨터는 Windows 10 Enterprise를 업그레이드 할 수 있으며 새 장치는 Windows 10 Enterprise와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-114">Your existing Windows-based computers can upgrade to Windows 10 Enterprise and new devices are installed with Windows 10 Enterprise.</span></span> |
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[<span data-ttu-id="168a6-115">4단계: Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="168a6-115">Phase 4: Office 365 ProPlus</span></span>](office365proplus-infrastructure.md)| <span data-ttu-id="168a6-116">기존 사용자의 Microsoft Office는 Office 365 ProPlus으로 업그레이드 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-116">Your existing users of Microsoft Office can upgrade to Office 365 ProPlus.</span></span> |
|![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[<span data-ttu-id="168a6-117">5단계: 모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="168a6-117">Phase 5: Mobile device management</span></span>](mobility-infrastructure.md)| <span data-ttu-id="168a6-118">장치를 등록하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-118">Your devices can be enrolled and managed.</span></span> |
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[<span data-ttu-id="168a6-119">6단계: 정보 보호</span><span class="sxs-lookup"><span data-stu-id="168a6-119">Phase 6: Information protection</span></span>](infoprotect-infrastructure.md)| <span data-ttu-id="168a6-120">Office 365 보안 기능이 사용 설정되었으며 레이블과 정책으로 문서 및 전자 메일을 보호할 준비가 되어있습니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-120">Office 365 security features are enabled and your sensitivity or Azure Information Protection labels are ready to protect documents.</span></span> |

<span data-ttu-id="168a6-121">이 단계들은 가장 기초적인 (네트워킹 및 아이디) 것으로 시작하며 인프라 설정 및 그룹들을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-121">The phases start with the most foundational (networking and identity), and then create layers of infrastructure settings and groups to:</span></span>

- <span data-ttu-id="168a6-122">장치에 최신의 안전한 Windows 버전을 설치하고 장치를 최신 상태로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-122">Install the most current and secure version of Windows on your devices.</span></span>
- <span data-ttu-id="168a6-123">장치에 최신 버전의 Microsoft Office를 설치하고 장치를 최신 상태로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-123">Install the most current version of Microsoft Office on your devices and keep it current.</span></span>
- <span data-ttu-id="168a6-124">조직의 장치 및 앱에 대한 액세스를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-124">Manage your organization's devices and their access to apps.</span></span>
- <span data-ttu-id="168a6-125">클라우드에서 장치에 대한 정보를 보호하십시오.</span><span class="sxs-lookup"><span data-stu-id="168a6-125">Protect the information on those devices and in the cloud.</span></span>

<span data-ttu-id="168a6-126">하지만 IT 리소스 및 비즈니스 요구에 맞는 단계 내에서 절차 및 단계를 유연하게 구성하고 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-126">However, you have the flexibility of configuring and rolling out the phases or steps within phases to fit your IT resources and business needs.</span></span>

- <span data-ttu-id="168a6-127">**더 작고 최신 조직인 경우**, 조직적으로 인프라를 구축하기 위해 필요한 단계를 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="168a6-127">**If you are a smaller or newer organization**, follow the phases as needed to methodically build out your infrastructure.</span></span> <span data-ttu-id="168a6-128">비 엔터프라이즈에 대한 배포를 단순화하려면 [여기](deploy-foundation-infrastructure-non-enterprises.md)를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="168a6-128">For a simplified deployment for non-enterprises, click [here](deploy-foundation-infrastructure-non-enterprises.md).</span></span>

-  <span data-ttu-id="168a6-129">**엔터프라이즈 조직인 경우**, 규정된 경로 보다는 IT 인프라 단계를 살펴보십시오. 그리고 조직 전체에서 각 레이어의 요구 사항을 최종적으로 준수하는 가장 효과적인 방법을 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="168a6-129">**If you are an enterprise organization**, view the phases as layers of IT infrastructure, rather than a defined path, and determine how to best work toward eventual adherence to the requirements for each layer across your organization.</span></span>

<span data-ttu-id="168a6-130">각 작업 단계의 마지막에 충족해야 할 필수 조건과 고려할 선택 조건을 포함하는 *종료 기준*을 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-130">At the end of each phase, you should examine its exit criteria, which include required conditions that you must meet and optional conditions to consider.</span></span> <span data-ttu-id="168a6-131">각 단계의 종료 기준에서 온 프레미스 및 클라우드 인프라 그리고 종단간 구성 결과가 Microsoft 365 Enterprise 배포의 요구조건을 충족하는지 확인해야합니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-131">Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meet the requirements for a Microsoft 365 Enterprise deployment.</span></span>

<span data-ttu-id="168a6-132">콘텐츠 구성 방식을 알아보려면 이 짧은 비디오를 시청 하십시오.</span><span class="sxs-lookup"><span data-stu-id="168a6-132">To see how the content is structured, watch this short video.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

<span data-ttu-id="168a6-133">전체 Microsoft 365 Enterprise 배포 가이드에서 기초 인프라는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-133">Here's the foundation infrastructure in the overall Microsoft 365 Enterprise deployment guide:</span></span>

![](./media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="at-a-glance"></a><span data-ttu-id="168a6-134">간략한 개요</span><span class="sxs-lookup"><span data-stu-id="168a6-134">At-a-glance</span></span>

<span data-ttu-id="168a6-135">[Microsoft 365 Enterprise 기본 인프라 포스터](media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf)는 각 단계에서 볼 수 있는 중앙 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-135">The [Microsoft 365 Enterprise foundation infrastructure poster](media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf) is a central location for you to view, for each phase:</span></span>

- <span data-ttu-id="168a6-136">관리자 및 사용자를 위한 단계의 전반적인 목표</span><span class="sxs-lookup"><span data-stu-id="168a6-136">The overall goals of the phase for administrators and users</span></span>
- <span data-ttu-id="168a6-137">서비스, 기능 및 도구</span><span class="sxs-lookup"><span data-stu-id="168a6-137">The services, features, and tools</span></span>
- <span data-ttu-id="168a6-138">계획에 대한 주요 디자인 결정</span><span class="sxs-lookup"><span data-stu-id="168a6-138">The key design decisions for planning</span></span>
- <span data-ttu-id="168a6-139">구성 결과</span><span class="sxs-lookup"><span data-stu-id="168a6-139">The configuration results</span></span>
- <span data-ttu-id="168a6-140">새 사용자를 온보딩하는 프로세스</span><span class="sxs-lookup"><span data-stu-id="168a6-140">The process for onboarding a new user</span></span>
- <span data-ttu-id="168a6-141">모니터링 및 업데이트 방법</span><span class="sxs-lookup"><span data-stu-id="168a6-141">How to monitor and update</span></span>

<span data-ttu-id="168a6-142">[![Microsoft 365 Enterprise 기본 인프라 포스터의 이미지](./media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.png)](media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf)</span><span class="sxs-lookup"><span data-stu-id="168a6-142">[![Image for the Microsoft 365 Enterprise foundation infrastructure poster](./media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.png)](media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf)</span></span>

<span data-ttu-id="168a6-143">포스터 사본을 다운로드 하려면 [여기](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf)를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="168a6-143">To download a copy of the poster, click [here](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf).</span></span>


## <a name="infrastructure-configuration-vs-user-rollout"></a><span data-ttu-id="168a6-144">인프라 구성 대 사용자 공개</span><span class="sxs-lookup"><span data-stu-id="168a6-144">Infrastructure configuration vs. user rollout</span></span>

<span data-ttu-id="168a6-145">기초 인프라는 사용자가 함께 병행될 때, Microsoft Enterprise 365에서 제공하는 기능 및 보호의 전체 스펙트럼을 활용하게 해주는 구성된 소프트웨어와 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-145">The foundation infrastructure is a set of configured software and services that, when combined together for a user, allow them to take advantage of the entire spectrum of capabilities and protections that Microsoft 365 Enterprise offers.</span></span> <span data-ttu-id="168a6-146">종단 간 배포 이동의 최종 목적은 이 인프라를 모든 사용자 및 해당 Windows 기반 장치에 적용하도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-146">The ultimate destination of your end-to-end deployment journey is to have this infrastructure apply to all of your users and their Windows-based devices.</span></span> 

<span data-ttu-id="168a6-147">그러나 Microsoft 365 Enterprise 기초 인프라가 사용자를 위한 개별된 소프트웨어 및 서비스의 시작이라는 사실을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-147">However, it is important to note that the Microsoft 365 Enterprise foundation infrastructure is independent of the rollout of software and services to your users.</span></span> <span data-ttu-id="168a6-148">***모든 사용자에게 해당 레이어를 공개하지 않고도 기초 인프라의 레이어를 구성할 수 있습니다.***</span><span class="sxs-lookup"><span data-stu-id="168a6-148">***You can configure the layers of the foundation infrastructure without having to roll out those layers to all of your users.***</span></span>

<span data-ttu-id="168a6-149">조직의 사무실, 지역 또는 부서에서 많은 사용자를 위한 구성 요소 전에 기초 인프라의 요소들을 구성하고 테스트하며 시험 사용하는 것이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-149">Therefore, it is possible to configure, test, and pilot elements of the foundation infrastructure well ahead of the rollout of those elements to the multitude of your users in the offices, regions, or divisions of your organization.</span></span>

<span data-ttu-id="168a6-150">예를 들어, 설정을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-150">For example, you create the settings for:</span></span>

| <span data-ttu-id="168a6-151">단계</span><span class="sxs-lookup"><span data-stu-id="168a6-151">Phase</span></span> | <span data-ttu-id="168a6-152">결과</span><span class="sxs-lookup"><span data-stu-id="168a6-152">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="168a6-153">ID</span><span class="sxs-lookup"><span data-stu-id="168a6-153">Identity</span></span> | <span data-ttu-id="168a6-154">계정 동기화와 ID를 기반으로 조건부 액세스 정책에 대 한 그룹.</span><span class="sxs-lookup"><span data-stu-id="168a6-154">Account synchronization and groups for identity-based conditional access policies.</span></span> |
| <span data-ttu-id="168a6-155">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="168a6-155">Windows 10 Enterprise</span></span> | <span data-ttu-id="168a6-156">실행 중인 Windows 7 또는 Windows 8.1을 Windows 10 Enterprise로 자동으로 업그레이드 할 수 있는 그룹.</span><span class="sxs-lookup"><span data-stu-id="168a6-156">Groups to automatically upgrade computers running Windows 7 or Windows 8.1 to Windows 10 Enterprise in place.</span></span> |
| <span data-ttu-id="168a6-157">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="168a6-157">Office 365 ProPlus</span></span> | <span data-ttu-id="168a6-158">그룹을 자동으로 Office 2010, Office 2013 또는 Office 2016의 사용자를 위해 Office 365 ProPlus를 배포하는 그룹.</span><span class="sxs-lookup"><span data-stu-id="168a6-158">Groups to automatically deploy Office 365 ProPlus for users with Office 2010, Office 2013, or Office 2016.</span></span> |
| <span data-ttu-id="168a6-159">모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="168a6-159">Mobile device management</span></span> | <span data-ttu-id="168a6-160">장치 등록 및 장치 기반 조건부 액세스 정책에 대한 그룹.</span><span class="sxs-lookup"><span data-stu-id="168a6-160">Groups for device enrollment and device-based conditional access policies.</span></span> |
| <span data-ttu-id="168a6-161">정보 보호</span><span class="sxs-lookup"><span data-stu-id="168a6-161">Information protection</span></span> | <span data-ttu-id="168a6-162">Office 365 민감도 레이블을 위한 그룹</span><span class="sxs-lookup"><span data-stu-id="168a6-162">Groups for Office 365 sensitivity labels.</span></span> |

<span data-ttu-id="168a6-163">사용자를 위한 인프라 구성요소를 공개할 준비가 된 경우.</span><span class="sxs-lookup"><span data-stu-id="168a6-163">When you are ready to rollout elements of this infrastructure to users, you:</span></span>

| <span data-ttu-id="168a6-164">단계</span><span class="sxs-lookup"><span data-stu-id="168a6-164">Phase</span></span> | <span data-ttu-id="168a6-165">공개 작업</span><span class="sxs-lookup"><span data-stu-id="168a6-165">Rollout action</span></span> |
|:-------|:-----|
| <span data-ttu-id="168a6-166">ID</span><span class="sxs-lookup"><span data-stu-id="168a6-166">Identity</span></span> | <span data-ttu-id="168a6-167">ID 기반의 조건부 액세스 정책에 대한 그룹에 사용자 계정을 추가하십시오.</span><span class="sxs-lookup"><span data-stu-id="168a6-167">Add user accounts to the groups for identity-based conditional access policies.</span></span> |
| <span data-ttu-id="168a6-168">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="168a6-168">Windows 10 Enterprise</span></span> | <span data-ttu-id="168a6-169">Windows 7 또는 Windows 8.1 사용자를 위해 Windows 10 Enterprise를 자동으로 배포하는 그룹에 계정을 추가하십시오.</span><span class="sxs-lookup"><span data-stu-id="168a6-169">Add accounts to the groups to automatically deploy Windows 10 Enterprise in place for users with Windows 7 or Windows 8.1.</span></span> |
| <span data-ttu-id="168a6-170">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="168a6-170">Office 365 ProPlus</span></span> | <span data-ttu-id="168a6-171">Office 2010, Office 2013 또는 Office 2016의 사용자를 위해 Office 365 ProPlus를 자동으로 배포하는 그룹에 사용자 계정을 추가하십시오.</span><span class="sxs-lookup"><span data-stu-id="168a6-171">Add user accounts to the groups to automatically deploy Office 365 ProPlus for users with Office 2010, Office 2013, or Office 2016.</span></span> |
| <span data-ttu-id="168a6-172">모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="168a6-172">Mobile device management</span></span> | <span data-ttu-id="168a6-173">장치 등록 및 장치 기반 조건부 액세스 정책에 대한 그룹에 계정을 추가하십시오.</span><span class="sxs-lookup"><span data-stu-id="168a6-173">Add accounts to the groups for device enrollment and device-based conditional access policies.</span></span> |
| <span data-ttu-id="168a6-174">정보 보호</span><span class="sxs-lookup"><span data-stu-id="168a6-174">Information protection</span></span> | <span data-ttu-id="168a6-175">민감도 레이블을 위한 그룹에 사용자 계정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-175">Add user accounts to the groups for Information Protection labels.</span></span> |

<span data-ttu-id="168a6-176">기초 인프라의 단계나 요소를 완료하고 테스트하며 시험 사용한 후, Windows 10 Enterprise 및 Office 365 ProPlus와 같이 설치된 소프트웨어와 디바이스 등록 및 조건부 액세스 정책과 같이 클라우드 기반 서비스 및 보호 기능을 비즈니스 목적 및 IT 리소스에 최적화된 방식으로 사용자에게 공개할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-176">Once the foundation infrastructure is completed, tested, and piloted, you can roll out installed software, such as Windows 10 Enterprise and Office 365 ProPlus, and cloud-based services and protections, such as device enrollment and conditional access policies, to your users in the manner that best fits your business goals and IT resources.</span></span>

## <a name="deployment-and-project-management-strategies"></a><span data-ttu-id="168a6-177">배포 및 프로젝트 관리 전략</span><span class="sxs-lookup"><span data-stu-id="168a6-177">Deployment and project management strategies</span></span>

<span data-ttu-id="168a6-178">시험 사용자 및 조직의 나머지를 위한 기초 인프라의 각 단계 프로젝트 관리에 접근하는 방법에 대한 몇 가지 아이디어를 제공하기 위해 [배포 전략](deployment-strategies-microsoft-365-enterprise.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="168a6-178">To give you some ideas on how to approach the project management of the different phases of the foundation infrastructure for pilot users and the rest of your organization, see [deployment strategies](deployment-strategies-microsoft-365-enterprise.md).</span></span>

## <a name="deployment-for-non-enterprises"></a><span data-ttu-id="168a6-179">비 엔터프라이즈를 위한 배포</span><span class="sxs-lookup"><span data-stu-id="168a6-179">Deployment for non-enterprises</span></span>

<span data-ttu-id="168a6-180">조직이 소규모이므로 Microsoft 365 Business가 사용자에게 적합하지 않은 경우 [비 엔터프라이즈를 위한 배포](deploy-foundation-infrastructure-non-enterprises.md)를 참조하여 간소화된 배포 방법을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="168a6-180">If your organization is smaller and Microsoft 365 Business is not suitable for you, see [deployment for non-enterprises](deploy-foundation-infrastructure-non-enterprises.md) for a simplified deployment method.</span></span>


## <a name="next-step"></a><span data-ttu-id="168a6-181">다음 단계</span><span class="sxs-lookup"><span data-stu-id="168a6-181">Next step</span></span>

| <span data-ttu-id="168a6-182">내 위치</span><span class="sxs-lookup"><span data-stu-id="168a6-182">Where I am</span></span> | <span data-ttu-id="168a6-183">가야할 곳</span><span class="sxs-lookup"><span data-stu-id="168a6-183">Where I need to go</span></span> |
|:-------|:-----|
| <span data-ttu-id="168a6-184">현재 Office 365, Enterprise 편리성+보안성 (EMS) 또는 Windows 10 Enterprise에 대한 기존 인프라를 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-184">I have existing infrastructure for Office 365, Enterprise Mobility + Security (EMS), or Windows 10 Enterprise:</span></span> | <span data-ttu-id="168a6-185">[기존 인프라를 사용하여 배포](deploy-with-existing-infrastructure.md)부터 시작하여 각 단계에 대한 종료 기준을 단계별로 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-185">Start with [Deploy with existing infrastructure](deploy-with-existing-infrastructure.md), which steps you through the exit criteria for each phase.</span></span> |
| <span data-ttu-id="168a6-186">엔터프라이즈로 처음부터 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-186">I'm starting from scratch as an enterprise</span></span> | <span data-ttu-id="168a6-187">[1 단계: 네트워킹](networking-infrastructure.md)으로 종단 간 배포의 첫걸음을 시작해보십시오.</span><span class="sxs-lookup"><span data-stu-id="168a6-187">Begin your end-to-end deployment journey with [Phase 1: Networking](networking-infrastructure.md).</span></span> |
| <span data-ttu-id="168a6-188">비 엔터프라이즈로 처음부터 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="168a6-188">I'm starting from scratch as a non-enterprise</span></span> | <span data-ttu-id="168a6-189">[비 엔터프라이즈에 대한 배포](deploy-foundation-infrastructure-non-enterprises.md)로 종단 간 배포의 첫걸음을 시작해보십시오.</span><span class="sxs-lookup"><span data-stu-id="168a6-189">Begin your end-to-end deployment journey with [Deployment for non-enterprises](deploy-foundation-infrastructure-non-enterprises.md).</span></span> |
