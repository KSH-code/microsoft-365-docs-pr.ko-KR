---
title: '4단계: Office 365 ProPlus'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise에 대한 Office 365 ProPlus 인프라를 배포하는 단계입니다.
ms.openlocfilehash: cf698e4dbee17a811a4d2bc01d08d4d97d1961c1
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074178"
---
# <a name="phase-4-office-365-proplus"></a><span data-ttu-id="7187e-103">4단계: Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="7187e-103">Phase 4: Office 365 ProPlus</span></span>

![](./media/deploy-foundation-infrastructure/O365proplus_icon.png)

<span data-ttu-id="7187e-104">*이 단계는 E3 및 E5 버전의 Microsoft 365 Enterprise 및 Microsoft 365 Education에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="7187e-104">*This applies to both the E3 and E5 versions of Microsoft 365 Enterprise and Microsoft 365 Education*</span></span>

<span data-ttu-id="7187e-p101">Microsoft 365 Enterprise에는 Office의 구독 버전인 Office 365 ProPlus가 포함되어 있습니다. Office 2016과 마찬가지로 Office 365 ProPlus에는 모든 Office 응용 프로그램이 있으며 이러한 응용 프로그램은 클라이언트 장치에 직접 설치됩니다. Office 2016과 달리 Office 365 ProPlus는 정기적으로 새로운 기능으로 업데이트되며 사용자가 최대 5대의 장치에 Office를 설치할 수 있는 사용자 기반 라이선싱 모델이 있습니다. 자세한 내용은 [엔터프라이즈의 Office 365 ProPlus 정보](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7187e-p101">Microsoft 365 Enterprise includes Office 365 ProPlus, the subscription version of Office. Like Office 2016, Office 365 ProPlus includes all the Office applications, and those applications are installed directly on your client devices. Unlike Office 2016, Office 365 ProPlus is updated with new features on a regular basis and has a user-based licensing model that allows people to install Office on up to 5 devices. For more details, see [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span></span>

<span data-ttu-id="7187e-p102">이 단계에서는 Microsoft 365 Enterprise의 일부로 클라이언트 장치에 Office 365 ProPlus를 설치합니다. 이 지침 외에도 배포에 도움이 되는 [Microsoft Fastrack](https://fasttrack.microsoft.com/office)을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7187e-p102">In this phase, you deploy Office 365 ProPlus to client devices as part of Microsoft 365 Enterprise. In addition to this guidance, we recommend you use [Microsoft Fastrack](https://fasttrack.microsoft.com/office) to help with your deployment.</span></span> 

<span data-ttu-id="7187e-111">Office 365 ProPlus는 다음과 같은 Microsoft 365 Enterprise에 대한 전략적 비즈니스 시나리오를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7187e-111">Office 365 ProPlus enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="7187e-112">실시간으로 또는 원하는 시간에 문서 공동 작업을 수행하여 공동 작성 프로세스 간소화</span><span class="sxs-lookup"><span data-stu-id="7187e-112">Collaborate on documents in real time or on your own time to simplify the cocreation process</span></span>
- <span data-ttu-id="7187e-113">사용자가 조직에서 파일, 정보 및 아이디어를 검색하고, 공유하고, 진행하도록 지원하여 통합적인 지식 및 전문 정보 활용</span><span class="sxs-lookup"><span data-stu-id="7187e-113">Harness collective knowledge and expertise by empowering people to discover, share, and progress files, information, and ideas across your organization</span></span>
- <span data-ttu-id="7187e-114">사용자가 비즈니스 프로세스를 혁신하고 효율성을 높이도록 지원</span><span class="sxs-lookup"><span data-stu-id="7187e-114">Empower users to transform business processes and increase efficiency</span></span>
- <span data-ttu-id="7187e-115">비즈니스 목표에 맞게 프로젝트, 작업 및 기한 관리</span><span class="sxs-lookup"><span data-stu-id="7187e-115">Manage projects, tasks, and deadlines to meet your business objectives</span></span>
- <span data-ttu-id="7187e-116">디자인, 쓰기, 콘텐츠 검색 등에 대한 지능형 보조 기능을 사용하여 뛰어난 품질의 작업 수행</span><span class="sxs-lookup"><span data-stu-id="7187e-116">Use intelligent assistance for design, writing, content discovery, and more to help your work shine</span></span>
- <span data-ttu-id="7187e-117">정보를 검색하고, 데이터를 분석하고, 찾은 내용을 공유하여 모든 사람이 합리적인 결정을 내리도록 지원</span><span class="sxs-lookup"><span data-stu-id="7187e-117">Discover insights, analyze your data, and share your findings to help everyone make informed decisions</span></span>
- <span data-ttu-id="7187e-118">팀과 소통하여 정보를 제공하고, 정보 제공을 요청하고, 협력 및 의견 합의 도달</span><span class="sxs-lookup"><span data-stu-id="7187e-118">Communicate with your team to stay informed, solicit input, and build cohesion and consensus</span></span>
- <span data-ttu-id="7187e-119">예약 및 임시 호출 방식으로 전 세계의 파트너, 동료 및 고객이 규모의 그룹과 소통하고 모든 규모의 그룹과 온라인 모임 진행</span><span class="sxs-lookup"><span data-stu-id="7187e-119">Communicate with partners, colleagues, and customers around the world for scheduled and ad hoc calls and online meetings with groups of all sizes</span></span>
- <span data-ttu-id="7187e-120">조직 내부 및 외부에서 파일을 저장 및 공유하여 조직 경계를 넘나들며 원활하게 작업 가능</span><span class="sxs-lookup"><span data-stu-id="7187e-120">Store and share files inside and outside your organization to work seamlessly across organizational boundaries</span></span>
- <span data-ttu-id="7187e-121">유연한 작업 스타일을 유지하면서 어떤 장치를 사용하든 장소나 시간의 구애를 받지 않고 안전하게 더 많은 작업 처리</span><span class="sxs-lookup"><span data-stu-id="7187e-121">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="7187e-122">업계에서 인증된 방식으로 제어 및 가시성에 대한 전역 표준을 준수하여 안심하고 작업 가능</span><span class="sxs-lookup"><span data-stu-id="7187e-122">Provide peace-of-mind with controls and visibility for industry-verified conformity with global standards in compliance</span></span>
- <span data-ttu-id="7187e-123">사용자의 정보 보호 및 데이터 손실 위험 최소화</span><span class="sxs-lookup"><span data-stu-id="7187e-123">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="7187e-124">보안 위험을 줄이고 IT 효율성을 극대화하면서 데스크톱 소프트웨어 및 장치를 최신 상태로 유지</span><span class="sxs-lookup"><span data-stu-id="7187e-124">Get current and stay current on your desktop software and devices while reducing security risks and maximizing IT efficiency</span></span>

<span data-ttu-id="7187e-125">자세한 내용은 [Microsoft 365를 사용한 디지털 변환](http://transform.microsoft.com)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7187e-125">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

<span data-ttu-id="7187e-126">Office 365 ProPlus를 이미 배포한 경우 이 단계에 대한 [종료 조건](office365proplus-exit-criteria.md)을 검토하여 Microsoft 365 Enterprise에 대한 필수 조건을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7187e-126">If you already have Office 365 ProPlus deployed, please see the [exit criteria](office365proplus-exit-criteria.md) for this phase to make sure that it meets the required conditions for Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="7187e-127">Windows 10 Enterprise 및 Office 365 ProPlus를 함께 배포하려면 [데스크톱 배포 센터](desktop-deployment-center-home.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7187e-127">To deploy both Windows 10 Enterprise and Office 365 ProPlus together, see the [Desktop Deployment Center](desktop-deployment-center-home.md).</span></span>
>

## <a name="step-1-assess-your-environment"></a><span data-ttu-id="7187e-128">1단계: 환경 평가</span><span class="sxs-lookup"><span data-stu-id="7187e-128">Step 1: Assess your environment</span></span>

<span data-ttu-id="7187e-p103">Office 365 ProPlus를 배포하기 전에 [Office 365 ProPlus를 배포하기 위한 사용자 환경 및 요구 사항 평가](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus)의 지침을 따르세요. 이 평가에는 시스템 요구 사항, 클라이언트 장치 정보(예: 아키텍처 및 필요한 언어), 라이선스 요구 사항, 네트워크 기능 및 응용 프로그램 호환성이 포함됩니다. 평가를 완료하면 배포 계획의 일부로 주요 결정을 내릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7187e-p103">Before deploying Office 365 ProPlus, follow the guidance in [Assess your environment and requirements for deploying Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). This assessment includes system requirements, details of your client devices (such as architectures and required languages), licensing requirements, network capability, and application compatibility. Completing the assessment will help you make key decisions as part of planning your deployment.</span></span>

## <a name="step-2-plan-your-deployment"></a><span data-ttu-id="7187e-132">2단계: 배포 계획</span><span class="sxs-lookup"><span data-stu-id="7187e-132">Step 2: Plan your deployment</span></span>

<span data-ttu-id="7187e-p104">사용자 환경을 평가한 후에는 [Office 365 ProPlus 배포 계획](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus)의 지침에 따라 배포 계획을 만듭니다. 이 계획에는 다음과 같은 의사 결정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7187e-p104">After assessing your environment, follow the guidance in [Plan your deployment of Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) to create a deployment plan. This plan includes the following decisions:</span></span> 

- <span data-ttu-id="7187e-135">사용할 도구(예: System Center Configuration Manager 또는 ODT[Office 배포 도구]) 및 Office 설치 위치 등 Office를 배포하는 방법</span><span class="sxs-lookup"><span data-stu-id="7187e-135">How to deploy Office, including what tool to use (such as System Center Configuration Manager or the Office Deployment Tool [ODT]) and where to install Office from</span></span>
- <span data-ttu-id="7187e-136">Office에 대한 업데이트를 관리하는 방법</span><span class="sxs-lookup"><span data-stu-id="7187e-136">How to manage updates to Office</span></span>
- <span data-ttu-id="7187e-137">사용할 업데이트 채널(Office의 업데이트 채널에 따라 사용자에게 Office 응용 프로그램에 대한 기능 업데이트가 제공되는 빈도가 달라짐)</span><span class="sxs-lookup"><span data-stu-id="7187e-137">Which update channels to use (update channels for Office control how frequently your users receive feature updates to their Office applications)</span></span>
- <span data-ttu-id="7187e-138">어떤 사용자에게 어떤 Office 응용 프로그램 및 언어를 설치해야 하는지를 포함하여 사용할 Office 설치 패키지 및 배포 그룹</span><span class="sxs-lookup"><span data-stu-id="7187e-138">The Office installation packages and deployment groups you want to use, including which Office applications and languages should be installed for which users</span></span>

<span data-ttu-id="7187e-139">[계획 문서](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus)에는 배포 관리, 업데이트 관리, 설치 패키지 정의, 배포 그룹 만들기 등 이러한 모든 옵션에 대한 모범 사례가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7187e-139">The [planning article](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) includes best practices for all these options, including managing your deployment, managing your updates, defining installation packages, and creating deployment groups.</span></span> 

## <a name="step-3-deploy"></a><span data-ttu-id="7187e-140">3단계: 배포</span><span class="sxs-lookup"><span data-stu-id="7187e-140">Step 3: Deploy</span></span>

<span data-ttu-id="7187e-141">2단계의 배포 계획에 따라 배포할 방법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7187e-141">Based on your deployment plan from step 2, choose how you want to deploy:</span></span>

- <span data-ttu-id="7187e-142">**[System Center Configuration Manager를 사용하여 Office 365 ProPlus 배포](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Configuration Manager를 사용하여 배포를 관리하고, 네트워크의 배포 지점에서 Office를 다운로드하여 배포</span><span class="sxs-lookup"><span data-stu-id="7187e-142">**[Deploy Office 365 ProPlus with System Center Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Manage your deployment with Configuration Manager, and download and deploy Office from distribution points on your network</span></span>

- <span data-ttu-id="7187e-143">**[클라우드에서 ODT를 사용하여 Office 365 ProPlus 배포](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** ODT를 사용하여 배포를 관리하고 Office CDN에서 직접 클라이언트 장치에 Office 설치</span><span class="sxs-lookup"><span data-stu-id="7187e-143">**[Deploy Office 365 ProPlus with the ODT from the cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Manage your deployment with the ODT, and install Office on client devices directly from the Office CDN</span></span>
 
- <span data-ttu-id="7187e-144">**[로컬 원본에서 ODT를 사용하여 Office 365 ProPlus 배포](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-a-local-source):** ODT를 사용하여 배포를 관리하고 네트워크의 로컬 원본에서 Office를 다운로드하여 배포</span><span class="sxs-lookup"><span data-stu-id="7187e-144">**[Deploy Office 365 ProPlus with the ODT from a local source](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-a-local-source):** Manage your deployment with the ODT, and download and deploy Office from a local source on your network</span></span> 

- <span data-ttu-id="7187e-145">**[Office 포털에서 Office 365 ProPlus 자가 설치](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** Office 포털에서 배포를 관리하고 사용자가 포털에서 직접 클라이언트 장치에 Office를 설치하도록 함</span><span class="sxs-lookup"><span data-stu-id="7187e-145">**[Self-install Office 365 ProPlus from the Office portal](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** Manage your deployment from the Office portal and have your users install Office on their client devices directly from the portal</span></span>

<span data-ttu-id="7187e-p105">대부분의 조직에서는 다양한 사용자에 대해 이러한 옵션의 조합을 사용합니다. 예를 들어 조직에서는 Configuration Manager를 사용하여 대부분의 사용자에게 Office를 배포하지만 내부 네트워크에 자주 연결되지 않는 소규모 작업 그룹을 위해 자가 설치를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7187e-p105">Many organizations will use a combination of these options for different users. For example, an organization might use Configuration Manager to deploy Office to most of their users, but enable self-install for a small group of workers who are not frequently connected to the internal network.</span></span> 

<span data-ttu-id="7187e-p106">조직에서 Configuration Manager를 사용하는 경우 현재 분기로 업그레이드하고 현재 릴리스로 업데이트하는 것이 좋습니다. 자세한 내용은 [사용해야 하는 Configuration Manager 분기](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7187e-p106">If your organization uses Configuration Manager, we recommend upgrading to the Current Branch and updating to the current release. For more details, see [Which branch of Configuration Manager should I use?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="7187e-150">Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법</span><span class="sxs-lookup"><span data-stu-id="7187e-150">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="7187e-151">Microsoft의 전문가가 [Office 365 ProPlus의 업데이트를 배포하고 관리](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR7)하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="7187e-151">Learn how the experts at Microsoft are [deploying and mananging updates for Office 365 ProPlus](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="7187e-152">Contoso의 Microsoft 365 Enterprise 사용 방식</span><span class="sxs-lookup"><span data-stu-id="7187e-152">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="7187e-153">가상의 대표적 다국적 기업인 Contoso Corporation가 [Office 365 ProPlus를 배포](contoso-o365pp.md)한 방식을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="7187e-153">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Office 365 ProPlus](contoso-o365pp.md).</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="7187e-154">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7187e-154">Next step</span></span>

[<span data-ttu-id="7187e-155">Office 365 ProPlus 인프라 종료 조건</span><span class="sxs-lookup"><span data-stu-id="7187e-155">Office 365 ProPlus infrastructure exit criteria</span></span>](office365proplus-exit-criteria.md)
