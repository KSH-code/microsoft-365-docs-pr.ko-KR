---
title: Microsoft 365 Enterprise 기본 인프라
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/27/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 조직에서 Microsoft 365 Enterprise 기본 인프라를 배포하는 주요 단계를 이해합니다.
ms.openlocfilehash: abc38dc0eb3d33f7af9e2c91f020a735cf0c8d96
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869718"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure"></a><span data-ttu-id="c4359-103">Microsoft 365 Enterprise 기본 인프라</span><span class="sxs-lookup"><span data-stu-id="c4359-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="c4359-104">Microsoft 365 Enterprise를 최대한 활용하려면 해당 기본 인프라와 함께 배포를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c4359-104">To fully realize the benefits of Microsoft 365 Enterprise, you’ll begin your deployment with its foundation infrastructure.</span></span> 

## <a name="foundation-infrastructure-for-deploying-microsoft-365-enterprise"></a><span data-ttu-id="c4359-105">Microsoft 365 Enterprise 배포를 위한 기본 인프라</span><span class="sxs-lookup"><span data-stu-id="c4359-105">Foundation infrastructure for deploying Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c4359-p101">기본 인프라는 생산성 워크로드(예: Microsoft Teams 및 Office 365의 Exchange Online) 및 시나리오(예: Microsoft 365로의 마이그레이션 및 클라이언트 업데이트 자동화)를 배포할 수 있는 토대로서, 지속적인 관리를 간소화하는 지능형 보안 및 통합 기능을 제공하며, 향상된 최신 생산성 및 보안 기능으로 클라이언트 소프트웨어를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="c4359-p101">The foundation infrastructure is the groundwork upon which you can deploy productivity workloads (such as Microsoft Teams and Exchange Online in Office 365) and scenarios (such as migrating to Microsoft 365 and automating client updates). It provides intelligent security and integration that simplifies ongoing management, which ensures that your client software is updated with the latest productivity and security enhancements.</span></span>

<span data-ttu-id="c4359-108">다음 단계를 사용하여 조직에서 Microsoft 365 Enterprise의 기본 인프라를 계획하고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4359-108">You'll use the following phases to plan for and deploy the foundation infrastructure of Microsoft 365 Enterprise in your organization:</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/networking_icon-small.png)|[<span data-ttu-id="c4359-109">1단계: 네트워킹</span><span class="sxs-lookup"><span data-stu-id="c4359-109">Phase 1: Networking</span></span>](networking-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)|[<span data-ttu-id="c4359-110">2단계: ID</span><span class="sxs-lookup"><span data-stu-id="c4359-110">Phase 2: Identity</span></span>](identity-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[<span data-ttu-id="c4359-111">3단계: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c4359-111">Phase 3: Windows 10 Enterprise</span></span>](windows10-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[<span data-ttu-id="c4359-112">4단계: Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="c4359-112">Phase 4: Office 365 ProPlus</span></span>](office365proplus-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[<span data-ttu-id="c4359-113">5단계: 모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="c4359-113">Phase 5: Mobile device management</span></span>](mobility-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[<span data-ttu-id="c4359-114">6단계: 정보 보호</span><span class="sxs-lookup"><span data-stu-id="c4359-114">Phase 6: Information protection</span></span>](infoprotect-infrastructure.md)|


<span data-ttu-id="c4359-p102">각 단계를 종료하려면 먼저 반드시 충족해야 하는 필수 조건과 고려할 선택적 조건의 집합인 종료 조건을 검사해야 합니다. 각 단계의 종료 조건은 온-프레미스 및 클라우드 인프라와 결과적인 종단 간 구성이 Microsoft 365 Enterprise 배포에 대한 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c4359-p102">Before you can exit each phase, you must examine its exit criteria, which is a set of required conditions that you must meet and optional conditions to consider. Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meet the requirements for a Microsoft 365 Enterprise deployment.</span></span>

<span data-ttu-id="c4359-117">기초 인프라 콘텐츠 작동 방법에 대한 간단한 비디오를 보세요.</span><span class="sxs-lookup"><span data-stu-id="c4359-117">Watch this short video on how the foundation infrastructure content works.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

<span data-ttu-id="c4359-118">다음 그림에서는 전체 Microsoft 365 Enterprise 배포 콘텐츠의 기본 인프라와 관련 경로를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4359-118">The following figure shows the foundation infrastructure in the overall Microsoft 365 Enterprise deployment content and your path through it.</span></span>

![](./media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="fasttrack"></a><span data-ttu-id="c4359-119">FastTrack</span><span class="sxs-lookup"><span data-stu-id="c4359-119">FastTrack</span></span>

<span data-ttu-id="c4359-p103">FastTrack은 사용자가 원하는 일정에 따라 클라우드로 전환할 수 있도록 Microsoft 엔지니어가 제공하는 지속적이고 반복 가능한 혜택입니다(구독의 일부로 제공). 또한 FastTrack은 필요에 따라 적격 파트너에게 추가 서비스에 대한 액세스를 제공합니다. 지금까지 40,000여 명의 고객을 보유한 FastTrack은 조직 전체에서 ROI를 극대화하고, 배포를 가속화하고, 도입을 늘리도록 도와줍니다. [Microsoft 365용 FastTrack](https://fasttrack.microsoft.com/microsoft365)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c4359-p103">FastTrack is an ongoing and repeatable benefit—available as part of your subscription—that is delivered by Microsoft engineers to help you move to the cloud at your own pace. FastTrack also gives you access to qualified partners for additional services, as needed. With over 40,000 customers enabled to date, FastTrack helps maximize ROI, accelerate deployment, and increase adoption across your organization. See [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span></span> 

<span data-ttu-id="c4359-p104">FastTrack을 활용하여 Microsoft 365 Enterprise를 배포하려는 경우 [Microsoft 365 배포 관리자](https://aka.ms/microsoft365setupguide)를 사용하여 기본 인프라 배포 및 설정 방법에 대한 지침을 확인할 수 있습니다. 이 페이지에 액세스하려면 Office 365 또는 Microsoft 365 테넌트에서 전역 관리자로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4359-p104">If you want to take advantage of FastTrack to deploy Microsoft 365 Enterprise, you can use the FastTrack [Microsoft 365 deployment advisor](https://aka.ms/microsoft365setupguide) for guidance on how to deploy and set up your foundation infrastructure. You must be signed on as a global administrator in an Office 365 or Microsoft 365 tenant in order to access this page.</span></span>

## <a name="next-step"></a><span data-ttu-id="c4359-126">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c4359-126">Next step</span></span>

<span data-ttu-id="c4359-p105">Office 365, Enterprise Mobility + Security 또는 Windows 10 Enterprise에 대한 기존 인프라가 있는 경우 [기존 인프라를 사용하여 Microsoft 365 Enterprise 배포](deploy-with-existing-infrastructure.md)를 참조하세요. 이 문서에서는 각 단계의 종료 조건을 안내합니다. 이 정보를 통해 IT 인프라를 Microsoft 365 Enterprise와 호환되도록 하기 위해 변경해야 하는 항목을 보다 신속하게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4359-p105">If you have existing infrastructure for Office 365, Enterprise Mobility + Security, or Windows 10 Enterprise, see [Deployment of Microsoft 365 Enterprise with existing infrastructure](deploy-with-existing-infrastructure.md). This article steps you through the exit criteria for each phase. With this information, you can more quickly determine what you need to change to make your IT infrastructure Microsoft 365 Enterprise-compliant.</span></span>

<span data-ttu-id="c4359-130">기존 인프라가 없는 경우에는 [1단계: 네트워킹](networking-infrastructure.md)을 사용하여 Microsoft 365 Enterprise 종단 간 배포 과정을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4359-130">Otherwise, you can begin your Microsoft 365 Enterprise end-to-end deployment journey with [Phase 1: Networking](networking-infrastructure.md).</span></span>