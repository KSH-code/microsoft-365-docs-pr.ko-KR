---
title: Microsoft 365 Enterprise용 SharePoint 및 OneDrive 배포
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: 조직 전체에서 SharePoint를 계획하고 배포하며 가치를 창출하는 프로세스를 안내합니다.
ms.openlocfilehash: d8a61a6bc6b4dae431d94e7ccfb9fb0ea8019427
ms.sourcegitcommit: a77c4889c5b7d3b8f16e74917079300e8f222941
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2019
ms.locfileid: "37329211"
---
# <a name="deploy-sharepoint-and-onedrive-for-microsoft-365-enterprise"></a><span data-ttu-id="d737d-103">Microsoft 365 Enterprise용 SharePoint 및 OneDrive 배포</span><span class="sxs-lookup"><span data-stu-id="d737d-103">Deploy SharePoint Online and OneDrive for Business for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="d737d-104">*이 작업은 Microsoft 365 Enterprise E3 및 E5 버전에 모두 포함됩니다.*</span><span class="sxs-lookup"><span data-stu-id="d737d-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="d737d-105">SharePoint 및 Microsoft Teams는 사용자가 파일 저장 및 공유, 콘텐츠 관리, 공동 작업을 수행하는 방식이며, Microsoft 365 Enterprise가 제공하는 팀 작업을 위한 Office 제품의 핵심 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-105">SharePoint Online and Microsoft Teams is how you do file storage and sharing, content management, and collaboration and is a key element of the Built for Teamwork value of Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="d737d-p101">또한 SharePoint는 사용 중이거나 미사용 상태일 때 권한 및 암호화를 사용한 액세스 제어를 포함하는 고급 보안 기능도 제공합니다. SharePoint 보안은 Microsoft 365 Enterprise가 제공하는 지능형 보안 가치에서 핵심적인 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-p101">SharePoint Online also has advanced security capabilities including access control and permissions and encryption in flight and at rest. SharePoint Online security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="d737d-108">SharePoint를 완전히 처음 사용하는 경우 [SharePoint](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) 및 [SharePoint 시작](https://support.office.com/article/Get-started-with-SharePoint-3a26444b-08c5-46ad-b80a-cda82b11b27b#ID0EAABAAA=Basics)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d737d-108">If you are brand new to SharePoint Online, see [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) and [Get Started with SharePoint](https://support.office.com/article/Get-started-with-SharePoint-3a26444b-08c5-46ad-b80a-cda82b11b27b#ID0EAABAAA=Basics).</span></span>

<span data-ttu-id="d737d-109">다음 단계에서는 조직에서 SharePoint 역할을 구상하고, 일련의 점진적 배포를 통해 조직을 온보딩하며, 사용 및 가치를 최종 사용자에게 전달하는 프로세스를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-109">The following phases and steps guide you through the process of envisioning the role of SharePoint Online in your organization, onboarding your organization through a series of progressive rollouts, and driving usage its value to your end users.</span></span> <span data-ttu-id="d737d-110">시작하기 전에 SharePoint 사이트에서 필요한 보안 기능을 갖출 수 있도록 적절한 [기초 인프라](deploy-workloads.md#foundation-infrastructure-prerequisites) 단계를 구성했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-110">Before you begin, make sure you've configured the right [foundation infrastructure](deploy-workloads.md#foundation-infrastructure-prerequisites) phases so that your SharePoint Online sites have the security capabilities you need.</span></span> 

<span data-ttu-id="d737d-111">Microsoft 365 Enterprise용 OneDrive를 배포하려면 [기업용 OneDrive 가이드](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d737d-111">To deploy OneDrive for Business for Microsoft 365 Enterprise, see the [OneDrive guide for enterprises](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).</span></span>

## <a name="phase-1-envision"></a><span data-ttu-id="d737d-112">1단계: 구상</span><span class="sxs-lookup"><span data-stu-id="d737d-112">Phase 1: Envision</span></span>
<span data-ttu-id="d737d-113">이 단계에서는 SharePoint 배포를 수행할 조직 파트너를 모집하고 조직이 어떤 방식으로 SharePoint를 사용하여 비즈니스 요구를 해결할지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-113">In this phase, you gather the people for your SharePoint Online deployment and determine how your organization will use them to address its business needs.</span></span>

### <a name="step-1-gather-your-sharepoint-deployment-members"></a><span data-ttu-id="d737d-114">1단계: SharePoint 배포 구성원 모집</span><span class="sxs-lookup"><span data-stu-id="d737d-114">Step 1: Gather your SharePoint Online deployment members</span></span>

<span data-ttu-id="d737d-p103">[Microsoft 365 Enterprise 기본 인프라](deploy-foundation-infrastructure.md)에 SharePoint를 성공적으로 배포하려면 입력 및 피드백을 위해 올바른 구성원을 모아야 합니다. 주요 구성원에는 비즈니스 의사 결정권자, IT 담당자(예: 설계자 및 구현자) 및 최종 사용자의 대변자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-p103">For a successful deployment of SharePoint Online on top of the [Microsoft 365 Enterprise foundation infrastructure](deploy-foundation-infrastructure.md), you need to get the right people for input and feedback. Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="d737d-117">이 세 그룹은 배포 시에 일반적인 사용자들이 비즈니스 요구 사항, 폴더 및 문서 마이그레이션의 기술적 측면, 보안과 관련된 사항을 고려할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-117">These three groups ensure that your deployment includes considerations that address business needs, technical aspects of folder and document migration and security, and that the result will be something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="d737d-118">결과</span><span class="sxs-lookup"><span data-stu-id="d737d-118">Result</span></span>

<span data-ttu-id="d737d-119">조직의 비즈니스, 기술 및 최종 사용자 측면을 대표하는 구성원 목록을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-119">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-sharepoint-business-scenarios"></a><span data-ttu-id="d737d-120">2단계: SharePoint 비즈니스 시나리오 확인 및 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="d737d-120">Step 2: Determine and prioritize your SharePoint Online business scenarios</span></span>

<span data-ttu-id="d737d-p104">SharePoint는 다양한 용도로 사용할 수 있습니다. 비즈니스 요구에 해당되는 목적을 파악해야 합니다. SharePoint가 팀, 부서 또는 전체 조직이 갖는 문서 저장과 공유, 콘텐츠 관리, 공동 작업 요구 사항을 해결하는 데 사용되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-p104">SharePoint Online can be used for different purposes. You need to figure out which purposes map to your business needs. You should target SharePoint Online to address the document storage and sharing, content management, and collaboration needs of your teams, your division, or your entire organization.</span></span> 

<span data-ttu-id="d737d-124">시나리오 및 기능 목록은 [SharePoint](https://products.office.com/sharepoint/sharepoint-online-collaboration-software)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d737d-124">See the list of scenarios and capabilities at [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software).</span></span>

<span data-ttu-id="d737d-125">다음과 같은 비즈니스 핵심 요소로 조직의 요구를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-125">The following business pillars can address your organization’s needs:</span></span>

|||
|:-----|:-----|
| <span data-ttu-id="d737d-126">공유 및 공동 작업</span><span class="sxs-lookup"><span data-stu-id="d737d-126">Share and Work Together</span></span> | <span data-ttu-id="d737d-127">팀 사이트, 공동 작업 사이트 및 동기화를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-127">Take advantage of team sites, collaboration sites, and sync.</span></span> |
| <span data-ttu-id="d737d-128">정보 전달 및 소통</span><span class="sxs-lookup"><span data-stu-id="d737d-128">Inform and Engage</span></span> | <span data-ttu-id="d737d-129">향후 제공될 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-129">Information coming in the future.</span></span> |
| <span data-ttu-id="d737d-130">변환</span><span class="sxs-lookup"><span data-stu-id="d737d-130">Transform</span></span> | <span data-ttu-id="d737d-131">흐름을 사용하여 저장소 또는 워크플로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-131">Uses Flow to create a store or workflow.</span></span> |
| <span data-ttu-id="d737d-132">집단 지성 활용</span><span class="sxs-lookup"><span data-stu-id="d737d-132">Harness Collective Knowledge</span></span> | <span data-ttu-id="d737d-133">검색을 사용하여 조직 내에서 원하는 결과를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-133">Uses Search to give the desired results within your organization.</span></span> |
| <span data-ttu-id="d737d-134">보호</span><span class="sxs-lookup"><span data-stu-id="d737d-134">Protect</span></span> | <span data-ttu-id="d737d-135">조직이 안전하게 보호되고 올바른 규정을 준수하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-135">Ensures your organization is secured and has the correct compliance.</span></span> |
| <span data-ttu-id="d737d-136">외부/개발</span><span class="sxs-lookup"><span data-stu-id="d737d-136">External/Develop</span></span> | <span data-ttu-id="d737d-137">SharePoint 프레임워크를 사용하여 조직이 솔루션 및 앱을 개발할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-137">Lets your organization develop customize solutions and apps by using the SharePoint Framework.</span></span> |
|||

<span data-ttu-id="d737d-138">필요에 맞게 SharePoint를 구성하는 방법에 대한 리소스는 [SharePoint 관리자](https://docs.microsoft.com/sharepoint/sharepoint-online)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d737d-138">See [SharePoint Online admin](https://docs.microsoft.com/sharepoint/sharepoint-online) for resources on how to configure SharePoint Online for your needs.</span></span>

<span data-ttu-id="d737d-p105">SharePoint의 이점을 알아보는 한 가지 방법은 개인, 팀, 부서 또는 조직 전체가 현재 상호 작용하는 방식을 검토한 후, 파일을 저장 및 공유하는 보다 쉬운 방법을 제공하는 적절한 시나리오를 찾아보는 것입니다. [Microsoft Teams](teams-workload.md)가 일부 시나리오에 적합한 옵션이 될 수 있다는 점에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="d737d-p105">One way to see the benefits of SharePoint Online is to examine how individuals, a team, a division, or your entire organization interact today, and then find an appropriate scenario that provides easier ways to store and share files collaborate. Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your scenarios.</span></span>

#### <a name="sharepoint-site-for-highly-regulated-data"></a><span data-ttu-id="d737d-141">강도 높은 규제 대상 데이터를 위한 SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="d737d-141">SharePoint Online site for highly regulated data</span></span>

<span data-ttu-id="d737d-142">강도 높은 규제 대상 데이터는 해당 지역 규정이 적용되거나, 영업 비밀, 재무 또는 인사 관련 정보와 조직의 전략과 같이 조직에서 가장 중요한 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-142">Highy regulated data is subject to regional regulations or is the most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy. You can configure a team for restricted access, data classification, data loss prevention, and encryption for this type of data. For the details, see Microsoft Teams and SharePoint Online sites for highly regulated data.</span></span> <span data-ttu-id="d737d-143">이 유형의 데이터에 대한 제한된 액세스, 데이터 분류, 데이터 손실 방지 및 암호화를 위해 SharePoint 사이트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-143">You can configure a SharePoint site for restricted access, data classification, data loss prevention, and encryption for this type of data.</span></span> <span data-ttu-id="d737d-144">자세한 내용은 [높은 규제 대상 데이터용 Microsoft Teams 및 SharePoint 사이트](teams-sharepoint-online-sites-highly-regulated-data.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d737d-144">For more information, see the [Microsoft Teams and SharePoint Online sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md) scenario.</span></span>

#### <a name="result"></a><span data-ttu-id="d737d-145">결과</span><span class="sxs-lookup"><span data-stu-id="d737d-145">Result</span></span>
<span data-ttu-id="d737d-146">조직의 문서 저장 및 공유, 콘텐츠 관리, 공동 작업 및 보안에 필요한 사항을 충족하는 SharePoint 시나리오 목록을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-146">A list of SharePoint Online scenarios that address your organization’s needs for document storage and sharing, content management, and collaboration.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="d737d-147">2단계: 온보딩</span><span class="sxs-lookup"><span data-stu-id="d737d-147">Phase 2: Onboard</span></span>

<span data-ttu-id="d737d-148">이 단계에서는 SharePoint 배포의 기술적 측면을 계획하고 선택한 사용자 그룹에 이를 배포하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-148">In this phase, you plan for the technical aspects of a SharePoint Online deployment and start rolling then out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="d737d-149">필수 구성 요소: ID 및 장치 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="d737d-149">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="d737d-150">SharePoint 사이트에 대한 액세스를 보호하려면 [ID 및 장치 액세스 정책](identity-access-policies.md) 및 [권장 SharePoint 액세스 정책](sharepoint-file-access-policies.md)을 구성했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-150">To protect access to SharePoint Online sites, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="d737d-151">1단계: 기술 계획 완료</span><span class="sxs-lookup"><span data-stu-id="d737d-151">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="d737d-152">기술 계획을 시작하기 전에 FastTrack을 사용할지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-152">Before you begin technical planning, determine whether you want to use FastTrack.</span></span> <span data-ttu-id="d737d-153">조직에 50개가 넘는 좌석이 있고 [사용할 수 있는 요금제 적격 요금제](https://technet.microsoft.com/library/dn783224.aspx)에 참여하고 있는 경우, 추가 비용 없이 FastTrack 혜택을 사용하여 계획, 마이그레이션, 배포 및 서비스 도입 방법의 안내를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-153">Before you begin technical planning, determine whether you want to use FastTrack. If your organization has over 50 seats and is participating in an [eligible plan](https://technet.microsoft.com/library/dn783224.aspx), you can use FastTrack benefits, available at no additional cost to guide you through planning, deployment, and service adoption. Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from FastTrack once you sign in with your Office 365 account.</span></span> <span data-ttu-id="d737d-154">또는 Microsoft 365 계정으로 로그인한 후 [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview)에서 사용할 수 있는 FastTrack 온보딩 마법사를 사용하여 직접 이 작업을 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-154">Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview) once you sign in with your Microsoft 365 account.</span></span>

<span data-ttu-id="d737d-155">사용자 고유의 계획을 수행하거나 FastTrack과 연계해서 작업하는 경우, 네트워크 및 조직이 SharePoint를 사용할 준비가 되어 있는지 확인해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="d737d-155">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for SharePoint.</span></span> <span data-ttu-id="d737d-156">특히, SharePoint 기반 문서의 추가 트래픽 성능을 극대화하기 위해 인터넷 대역폭, 처리량 및 트래픽 지연에 중점을 두고 기본 인프라의 네트워킹에 대한 종료 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-156">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for SharePoint Online. It is especially important that you meet the exit criteria for networking in your foundation infrastructure, with special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for SharePoint Online-based documents.</span></span>

<span data-ttu-id="d737d-157">다음과 같은 리소스를 사용하여 SharePoint 배포의 기술적 측면을 대비하세요.</span><span class="sxs-lookup"><span data-stu-id="d737d-157">Use these resources to prepare for the technical aspects of a SharePoint Online rollout:</span></span> 

- [<span data-ttu-id="d737d-158">SharePoint 계획 가이드</span><span class="sxs-lookup"><span data-stu-id="d737d-158">SharePoint planning guide</span></span>](https://docs.microsoft.com/sharepoint/planning-guide)
- [<span data-ttu-id="d737d-159">SharePoint로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="d737d-159">Migrate  to SharePoint Online</span></span>](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) 

<span data-ttu-id="d737d-160">SharePoint의 보안을 보다 잘 이해하려면 다음 리소스를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="d737d-160">For a better understanding of security in SharePoint Online, review the following resources:</span></span>

-   [<span data-ttu-id="d737d-161">SharePoint 및 OneDrive가 클라우드에서 데이터를 보호하는 방법</span><span class="sxs-lookup"><span data-stu-id="d737d-161">How SharePoint Online and OneDrive safeguard your data in the cloud</span></span>](https://docs.microsoft.com/sharepoint/safeguarding-your-data)
-   [<span data-ttu-id="d737d-162">OneDrive 및 SharePoint의 데이터 암호화</span><span class="sxs-lookup"><span data-stu-id="d737d-162">Data Encryption in OneDrive for Business and SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/compliance/data-encryption-in-odb-and-spo)

#### <a name="result"></a><span data-ttu-id="d737d-163">결과</span><span class="sxs-lookup"><span data-stu-id="d737d-163">Result</span></span>

<span data-ttu-id="d737d-164">SharePoint 사이트 및 온-프레미스 폴더 및 문서 마이그레이션과 보안을 이해하고, 조직의 선택한 그룹에 SharePoint의 배포를 시작할 준비를 갖출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-164">You understand SharePoint Online sites and on-premises folder and document migration and security and are ready to begin rolling out SharePoint Online to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="d737d-165">2단계: IT 파일럿 실행</span><span class="sxs-lookup"><span data-stu-id="d737d-165">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="d737d-166">대부분의 중간 규모 및 대규모 조직에서는 1단계의 이해 관계자, 얼리어답터 및 기술 전문가와 함께 IT 파일럿을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-166">In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1 and early adopters and technical enthusiasts. During the IT pilot:</span></span> <span data-ttu-id="d737d-167">IT 파일럿 중에 수행하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-167">During the IT pilot:</span></span>

- <span data-ttu-id="d737d-168">IT 파일럿 참가자가 연습해볼 수 있는 SharePoint 비즈니스 시나리오를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-168">Choose a SharePoint Online business scenario in which your IT pilot participants can practice.</span></span>
- <span data-ttu-id="d737d-169">파일럿 참가자들에게 SharePoint 문서 저장, 공유, 공동 작업, 팀 기반 일정 관리 및 기타 기능을 테스트할 수 있는 일련의 연습을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-169">Give your pilot participants a set of exercises to test SharePoint Online document storage, sharing, collaboration, team-based scheduling, and other capabilities.</span></span>
- <span data-ttu-id="d737d-170">변경 관리 전략을 결정하고 SharePoint의 조직 전체 사용자 채택을 관리할 수 있도록 자료를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-170">Determine your change management strategy and produce materials to drive organization-wide user adoption of SharePoint.</span></span> <span data-ttu-id="d737d-171">변경 관리 자료에는 전자 메일 알림 텍스트, 내부 교육 계획, 복도 포스터 및 프레젠테이션이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-171">Change management materials can include email announcement text, internal training plans, hallway posters, and presentations.</span></span> <span data-ttu-id="d737d-172">이 자료는 SharePoint에 대한 정보 및 인식을 높이고 사용을 추진하는 목표의 장점을 조직에 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-172">These materials will inform your organization about SharePoint and its benefits with the goals of raising awareness and driving usage.</span></span> <span data-ttu-id="d737d-173">몇 가지 아이디어를 보려면 [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) 문서에 대한 변경 관리 전략을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d737d-173">See the change management strategy for [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) article for some ideas.</span></span>
- <span data-ttu-id="d737d-174">IT 파일럿 참여자가 자신의 경험을 기반으로 변경 관리 자료를 검토하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-174">Have your IT pilot participants review the change management materials based on their experiences.</span></span> <span data-ttu-id="d737d-175">이 참여자들이 모범 사례에 대한 팁과 SharePoint의 이점을 가장 잘 설명할 수 있는 방법과 사용 방법에 대한 유용한 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-175">Have your IT pilot participants review the change management materials based on their experiences. They can provide tips on best practices and advice on how to best describe the benefits of SharePoint Online and how to use it for communication and scheduling.</span></span>

#### <a name="result"></a><span data-ttu-id="d737d-176">결과</span><span class="sxs-lookup"><span data-stu-id="d737d-176">Result</span></span>

<span data-ttu-id="d737d-177">SharePoint IT 파일럿이 완료되고 초기 변경 관리 자료가 개발, 검토 및 구체화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-177">Your SharePoint Online IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="d737d-178">3단계: 비즈니스 그룹에 배포</span><span class="sxs-lookup"><span data-stu-id="d737d-178">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="d737d-179">IT 파일럿을 완료한 후 조직의 비즈니스 그룹 또는 부서에 SharePoint를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-179">After completing your IT pilot, roll out SharePoint Online to a business group or department in your organization. This rollout should include:</span></span> <span data-ttu-id="d737d-180">다음은 배포에 포함된 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-180">This rollout should include:</span></span>

- <span data-ttu-id="d737d-181">비즈니스 그룹 내에서 SharePoint에 대한 주요 비즈니스 시나리오 식별.</span><span class="sxs-lookup"><span data-stu-id="d737d-181">Identification of key business scenarios for SharePoint Online within the business group.</span></span>
- <span data-ttu-id="d737d-182">부서, 작업 또는 프로젝트 팀에 SharePoint의 사용에 따른 예상 결과 및 일정을 사용자에게 알리는 공지 활동.</span><span class="sxs-lookup"><span data-stu-id="d737d-182">Announcement activities to inform users of the expectations and timelines for SharePoint Online usage for departments and work or project teams.</span></span>
- <span data-ttu-id="d737d-183">비즈니스 그룹 구성원의 온-프레미스 폴더 및 문서를 SharePoint로 마이그레이션.</span><span class="sxs-lookup"><span data-stu-id="d737d-183">Migration of on-premises folders and documents of your business group members to SharePoint Online.</span></span>
- <span data-ttu-id="d737d-184">SharePoint를 도입하기 위한 사용자 교육 및 리소스 링크와 사용 방법 전달.</span><span class="sxs-lookup"><span data-stu-id="d737d-184">Delivering user training or provide links to resources to introduce SharePoint Online and how to use it.</span></span> <span data-ttu-id="d737d-185">[SharePoint](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) 비디오 교육을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d737d-185">[SharePoint Online video training](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23)</span></span>
- <span data-ttu-id="d737d-186">비즈니스 그룹의 사용자로부터 의견을 수집하고 문제에 대해 조치를 취하기 위한 피드백 메커니즘(예: 비즈니스 그룹의 모든 사용자를 포함하는 중앙 Microsoft Teams 팀)</span><span class="sxs-lookup"><span data-stu-id="d737d-186">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>
 
<span data-ttu-id="d737d-187">롤아웃하는 동안 조직 차원의 롤아웃을 준비하려면 변경 관리 자료를 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-187">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="d737d-188">결과</span><span class="sxs-lookup"><span data-stu-id="d737d-188">Result</span></span>

<span data-ttu-id="d737d-189">SharePoint를 통해 비즈니스 그룹이 운영되고 변경 관리 자료가 테스트 및 구체화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-189">A business group is up and running with SharePoint Online and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="d737d-190">3단계: 가치 창출</span><span class="sxs-lookup"><span data-stu-id="d737d-190">Phase 3: Drive value</span></span>

<span data-ttu-id="d737d-191">이 단계에서는 SharePoint 배포를 완료하고 사용자가 이점을 실현하도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-191">In this phase, you complete the rollout of SharePoint Online support your users to help them realize its benefits.</span></span>

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a><span data-ttu-id="d737d-192">1단계: 조직의 나머지 구성원에게 롤아웃</span><span class="sxs-lookup"><span data-stu-id="d737d-192">Step 1: Roll out to the rest of your organization</span></span>

<span data-ttu-id="d737d-193">나머지 조직 구성원에게 롤아웃하는 과정에는 다음이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-193">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="d737d-194">분리된 비즈니스 그룹 내에서 SharePoint에 대한 주요 비즈니스 시나리오 식별.</span><span class="sxs-lookup"><span data-stu-id="d737d-194">Identification of key business scenarios for SharePoint Online Online within separate business groups.</span></span>
- <span data-ttu-id="d737d-195">구체화된 변경 관리 자료를 사용하여 사용에 따른 예상 결과 및 일정을 조직에 알리는 공지 활동.</span><span class="sxs-lookup"><span data-stu-id="d737d-195">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for usage.</span></span>
- <span data-ttu-id="d737d-196">나머지 조직의 폴더 및 문서를 SharePoint로 마이그레이션.</span><span class="sxs-lookup"><span data-stu-id="d737d-196">Migration of folders and documents for the rest of your organization to SharePoint Online.</span></span>
- <span data-ttu-id="d737d-197">SharePoint를 도입하기 위한 사용자 교육 및 리소스 링크와 사용 방법 전달.</span><span class="sxs-lookup"><span data-stu-id="d737d-197">Delivering user training or provide links to resources to introduce SharePoint Online and how to use it.</span></span>
- <span data-ttu-id="d737d-p114">조직의 사용자로부터 의견 및 문제를 수집하기 위한 피드백 메커니즘(예: 모든 사용자를 포함하는 중앙 팀). 조직의 사용자가 2500명 미만인 경우 Teams의 공개 채널을 사용하고, 2500명 이상인 경우 Yammer의 공용 그룹 사용</span><span class="sxs-lookup"><span data-stu-id="d737d-p114">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="d737d-201">결과</span><span class="sxs-lookup"><span data-stu-id="d737d-201">Result</span></span>
<span data-ttu-id="d737d-202">조직이 운영되며, 사용자에게 알림 및 교육을 제공하고 SharePoint를 사용할 수 있도록 하는 변경 관리 전략이 수립되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-202">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use SharePoint Online.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="d737d-203">2단계: 사용 현황 측정, 만족도 관리 및 도입 촉진</span><span class="sxs-lookup"><span data-stu-id="d737d-203">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="d737d-204">전체 조직에 롤아웃한 후에는 변경 관리 전략을 계속 실행하여 다음 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-204">After rolling out to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="d737d-205">경영진이 문서를 저장하고 공유하는 기본 도구로 SharePoint를 사용하도록 장려하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-205">Have your leadership promote SharePoint Online as the primary tool for document storage and sharing and team, division, or organization-wide collaboration.</span></span>
- <span data-ttu-id="d737d-206">사용자가 비즈니스 그룹, 부서, 업무 및 프로젝트 팀 간에 문서를 저장하고 공유하는 데 이를 사용할 수 있도록 장려합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-206">Encourage individuals to use it for document storage and sharing among business groups, departments, and working and project teams.</span></span>

<span data-ttu-id="d737d-207">다음은 몇 가지 추천 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-207">Here are some suggested activities:</span></span>

- <span data-ttu-id="d737d-208">[Office 365의 성공 요인](https://aka.ms/successfactors)을 통해 클라우드 서비스 도입에 대한 일반적인 모범 사례를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-208">See [Office 365 adoption guidance](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="d737d-p115">[Office 365 활동 보고서](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)를 통해 조직 전체의 Office 365 서비스 사용을 이해합니다. 조직의 Office 365 전역 관리자에게 활동 보고서에 액세스할 수 있도록 사용자 계정에 보고서 읽기 권한자 권한을 부여해 달라고 요청합니다(Office 365 전역 관리자가 아닌 경우).</span><span class="sxs-lookup"><span data-stu-id="d737d-p115">See [Office 365 activity reports](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="d737d-211">SharePoint를 사용한 후 사용자가 제공한 문제와 사용자 의견을 확인하기 위해 사용자 의견 장소(중앙 Teams 팀 또는 Yammer의 공개 채널)을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-211">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with SharePoint Online. Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span> <span data-ttu-id="d737d-212">사용자의 불편을 방지하고 배포에 대한 지원을 보여 주기 위해 질문과 문제를 가능한 한 신속하게 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-212">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with SharePoint Online. Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="d737d-213">각 비즈니스 그룹에서 챔피언를 식별하고 양성하여 SharePoint를 사용할 때 이들의 성과와 모범 사례를 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-213">Identify and nurture champions in each business group and highlight their accomplishments and best practices when using SharePoint.</span></span> <span data-ttu-id="d737d-214">조직에 성공을 반영하여 프로젝트 성공 및 도입을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-214">Reflect their successes out to the organization to show project success and adoption.</span></span> <span data-ttu-id="d737d-215">비즈니스 그룹 내 기술 리더의 지지는 경영진과 동료에게 강력한 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-215">Endorsement by technical leaders within a business group can exert a powerful influence over leadership and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="d737d-216">결과</span><span class="sxs-lookup"><span data-stu-id="d737d-216">Result</span></span>

<span data-ttu-id="d737d-217">조직은 문서 저장 및 공동 작업을 지원하기 위해 Microsoft 365 Enterprise를 채택했습니다.</span><span class="sxs-lookup"><span data-stu-id="d737d-217">Your organization has adopted SharePoint in Microsoft 365 Enterprise to support documentation storage and collaboration.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="d737d-218">Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법</span><span class="sxs-lookup"><span data-stu-id="d737d-218">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="d737d-219">Microsoft 내부 상황을 살펴보고 SharePoint를 배포한 방식을 알아보려면 [SharePoint를 클라우드로: Microsoft가 자체 마이그레이션을 수행한 방법 알아보기](https://www.microsoft.com/ko-KR/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d737d-219">To peek inside Microsoft and learn how the company deployed SharePoint Online, see [SharePoint to the cloud: Learn how Microsoft ran its own migration](https://www.microsoft.com/ko-KR/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d737d-220">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d737d-220">Next steps</span></span>

<span data-ttu-id="d737d-221">SharePoint의 지속적인 유지 관리에 대한 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d737d-221">See these resources for the ongoing maintenance of SharePoint Online:</span></span> 

- [<span data-ttu-id="d737d-222">SharePoint의 권한 수준 이해</span><span class="sxs-lookup"><span data-stu-id="d737d-222">Understanding permission levels in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/understanding-permission-levels)
- [<span data-ttu-id="d737d-223">SharePoint 사이트 사용 권한 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="d737d-223">Customize SharePoint site permissions</span></span>](https://docs.microsoft.com/sharepoint/customize-sharepoint-site-permissions)
- [<span data-ttu-id="d737d-224">SharePoint의 외부 공유 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="d737d-224">Turn external sharing on or off for SharePoint Online</span></span>](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)
- [<span data-ttu-id="d737d-225">액세스 요청 설정 및 관리</span><span class="sxs-lookup"><span data-stu-id="d737d-225">Set up and manage access requests</span></span>](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)
