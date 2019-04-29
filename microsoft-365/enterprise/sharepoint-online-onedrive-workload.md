---
title: Microsoft 365 Enterprise에 대한 SharePoint Online 및 비즈니스용 OneDrive 배포
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: 조직 전체에서 Microsoft 365 Enterprise의 SharePoint Online을 계획 및 롤아웃하고 가치를 창출하는 프로세스를 안내합니다.
ms.openlocfilehash: 30fe3a971a869a4609d6b8ef2809692b4d4e5420
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400182"
---
# <a name="deploy-sharepoint-online-and-onedrive-for-business-for-microsoft-365-enterprise"></a><span data-ttu-id="9fd97-103">Microsoft 365 Enterprise에 대한 SharePoint Online 및 비즈니스용 OneDrive 배포</span><span class="sxs-lookup"><span data-stu-id="9fd97-103">Deploy SharePoint Online for Business for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="9fd97-104">*이 작업은 Microsoft 365 Enterprise E3 및 E5 버전에 모두 포함됩니다.*</span><span class="sxs-lookup"><span data-stu-id="9fd97-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="9fd97-105">SharePoint Online 및 Microsoft Teams는 사용자가 파일 저장 및 공유, 콘텐츠 관리, 공동 작업을 수행하는 방식이며, Microsoft 365 Enterprise가 제공하는 팀 작업을 위한 Office 제품의 핵심 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-105">SharePoint Online and Microsoft Teams is how you do file storage and sharing, content management, and collaboration and is a key element of the Built for Teamwork value of Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="9fd97-p101">또한 SharePoint Online은 사용 중이거나 미사용 상태일 때의 액세스 제어, 사용 권한 및 암호화를 포함하는 고급 보안 기능도 제공합니다. SharePoint Online 보안은 Microsoft 365 Enterprise가 제공하는 지능형 보안 가치에서 핵심적인 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-p101">SharePoint Online also has advanced security capabilities including access control and permissions and encryption in flight and at rest. SharePoint Online security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="9fd97-108">SharePoint Online을 완전히 처음 사용하는 경우 [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) 및 [SharePoint 시작](https://support.office.com/article/Get-started-with-SharePoint-3a26444b-08c5-46ad-b80a-cda82b11b27b#ID0EAABAAA=Basics)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fd97-108">If you are brand new to SharePoint Online, see [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) and [Get Started with SharePoint](https://support.office.com/article/Get-started-with-SharePoint-3a26444b-08c5-46ad-b80a-cda82b11b27b#ID0EAABAAA=Basics).</span></span>

<span data-ttu-id="9fd97-109">다음 단계에서는 조직에서 SharePoint Online 역할을 구상하고, 일련의 점진적 롤아웃을 통해 조직을 온보딩하며, 사용 가치를 최종 사용자에게 전달하는 프로세스를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-109">The following phases and steps guide you through the process of envisioning the role of Teams in your organization, onboarding your organization to Teams through a series of progressive rollouts, and driving usage of Teams and its value to your end users.</span></span> <span data-ttu-id="9fd97-110">시작하기 전에 SharePoint Online 사이트에서 필요한 보안 기능을 갖출 수 있도록 적절한 [기초 인프라](deploy-foundation-infrastructure.md) 단계를 구성했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-110">Before you begin, make sure you've configured the right [foundation infrastructure](deploy-foundation-infrastructure.md) phases so that your teams have the security capabilities you need.</span></span> 

<span data-ttu-id="9fd97-111">Microsoft 365 Enterprise를 위한 비즈니스용 OneDrive를 배포하려면 [기업용 OneDrive 가이드](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fd97-111">To deploy OneDrive for Business for Microsoft 365 Enterprise, see the [OneDrive guide for enterprises](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).</span></span>

## <a name="phase-1-envision"></a><span data-ttu-id="9fd97-112">1단계: 구상</span><span class="sxs-lookup"><span data-stu-id="9fd97-112">Phase 1: Envision</span></span>
<span data-ttu-id="9fd97-113">이 단계에서는 SharePoint Online 배포를 수행할 사용자를 모집하고 조직이 어떤 방식으로 이러한 제품을 사용하여 비즈니스 요구를 해결할지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-113">In this phase, you gather the people for your SharePoint Online deployment and determine how your organization will use them to address its business needs.</span></span>

### <a name="step-1-gather-your-sharepoint-online-deployment-members"></a><span data-ttu-id="9fd97-114">1단계: SharePoint Online 배포 구성원 모집</span><span class="sxs-lookup"><span data-stu-id="9fd97-114">Step 1: Gather your SharePoint Online deployment members</span></span>

<span data-ttu-id="9fd97-p103">[Microsoft 365 Enterprise 기본 인프라](deploy-foundation-infrastructure.md)에 SharePoint Online을 성공적으로 배포하려면 입력 및 피드백을 위해 올바른 구성원을 모아야 합니다. 주요 구성원에는 비즈니스 의사 결정권자, IT 담당자(예: 설계자 및 구현자) 및 최종 사용자의 대변자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-p103">For a successful deployment of SharePoint Online on top of the [Microsoft 365 Enterprise foundation infrastructure](deploy-foundation-infrastructure.md), you need to get the right people for input and feedback. Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="9fd97-117">이 세 그룹은 배포 시에 일반적인 사용자들이 비즈니스 요구 사항, 폴더 및 문서 마이그레이션의 기술적 측면, 보안과 관련된 사항을 고려할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-117">These three groups ensure that your deployment includes considerations that address business needs, technical aspects of folder and document migration and security, and that the result will be something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="9fd97-118">결과</span><span class="sxs-lookup"><span data-stu-id="9fd97-118">Result</span></span>

<span data-ttu-id="9fd97-119">조직의 비즈니스, 기술 및 최종 사용자 측면을 대표하는 구성원 목록을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-119">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-sharepoint-online-business-scenarios"></a><span data-ttu-id="9fd97-120">2단계: SharePoint Online 비즈니스 시나리오 확인 및 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="9fd97-120">Step 2: Determine and prioritize your SharePoint Online business scenarios</span></span>

<span data-ttu-id="9fd97-p104">SharePoint Online은 다양한 용도로 사용할 수 있습니다. 비즈니스 요구에 해당되는 목적을 파악해야 합니다. SharePoint Online이 팀, 부서 또는 전체 조직이 갖는 문서 저장과 공유, 콘텐츠 관리, 공동 작업 요구 사항을 해결하는 데 사용되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-p104">SharePoint Online can be used for different purposes. You need to figure out which purposes map to your business needs. You should target SharePoint Online to address the document storage and sharing, content management, and collaboration needs of your teams, your division, or your entire organization.</span></span> 

<span data-ttu-id="9fd97-124">시나리오 및 기능 목록은 [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fd97-124">See the list of scenarios and capabilities at [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software).</span></span>

<span data-ttu-id="9fd97-125">다음과 같은 비즈니스 핵심 요소로 조직의 요구를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-125">The following business pillars can address your organization’s needs:</span></span>

|||
|:-----|:-----|
| <span data-ttu-id="9fd97-126">공유 및 공동 작업</span><span class="sxs-lookup"><span data-stu-id="9fd97-126">Share and Work Together</span></span> | <span data-ttu-id="9fd97-127">팀 사이트, 공동 작업 사이트 및 동기화를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-127">Take advantage of team sites, collaboration sites, and sync.</span></span> |
| <span data-ttu-id="9fd97-128">정보 전달 및 소통</span><span class="sxs-lookup"><span data-stu-id="9fd97-128">Inform and Engage</span></span> | <span data-ttu-id="9fd97-129">향후 제공될 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-129">Information coming in the future.</span></span> |
| <span data-ttu-id="9fd97-130">변환</span><span class="sxs-lookup"><span data-stu-id="9fd97-130">Transform</span></span> | <span data-ttu-id="9fd97-131">흐름을 사용하여 저장소 또는 워크플로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-131">Uses Flow to create a store or workflow.</span></span> |
| <span data-ttu-id="9fd97-132">집단 지성 활용</span><span class="sxs-lookup"><span data-stu-id="9fd97-132">Harness Collective Knowledge</span></span> | <span data-ttu-id="9fd97-133">검색을 사용하여 조직 내에서 원하는 결과를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-133">Uses Search to give the desired results within your organization.</span></span> |
| <span data-ttu-id="9fd97-134">보호</span><span class="sxs-lookup"><span data-stu-id="9fd97-134">Protect</span></span> | <span data-ttu-id="9fd97-135">조직이 안전하게 보호되고 올바른 규정을 준수하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-135">Ensures your organization is secured and has the correct compliance.</span></span> |
| <span data-ttu-id="9fd97-136">외부/개발</span><span class="sxs-lookup"><span data-stu-id="9fd97-136">External/Develop</span></span> | <span data-ttu-id="9fd97-137">SharePoint 프레임워크를 사용하여 조직이 솔루션 및 앱을 개발할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-137">Lets your organization develop customize solutions and apps by using the SharePoint Framework.</span></span> |
|||

<span data-ttu-id="9fd97-138">필요에 맞게 SharePoint Online을 구성하는 방법에 대한 리소스는 [SharePoint Online 관리자](https://docs.microsoft.com/sharepoint/sharepoint-online)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fd97-138">See [SharePoint Online admin](https://docs.microsoft.com/sharepoint/sharepoint-online) for resources on how to configure SharePoint Online for your needs.</span></span>

<span data-ttu-id="9fd97-p105">SharePoint Online의 이점을 알아보는 한 가지 방법은 개인, 팀, 부서 또는 조직 전체가 현재 상호 작용하는 방식을 검토한 후, 파일을 저장 및 공유하고 공동으로 작업하는 보다 쉬운 방법을 제공하는 적절한 시나리오를 찾아보는 것입니다. [Microsoft Teams](teams-workload.md)가 일부 시나리오에 적합한 옵션이 될 수 있다는 점에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="9fd97-p105">One way to see the benefits of SharePoint Online is to examine how individuals, a team, a division, or your entire organization interact today, and then find an appropriate scenario that provides easier ways to store and share files collaborate. Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your scenarios.</span></span>

<span data-ttu-id="9fd97-141">SharePoint Online은 다음과 같은 Microsoft 365 Enterprise에 대한 전략적 비즈니스 시나리오를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-141">SharePoint Online enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="9fd97-142">팀과 소통하여 정보를 제공하고, 정보 제공을 요청하고, 협력 및 의견 합의 도달</span><span class="sxs-lookup"><span data-stu-id="9fd97-142">Communicate with your team to stay informed, solicit input, and build cohesion and consensus</span></span>
- <span data-ttu-id="9fd97-143">집단 지성 활용</span><span class="sxs-lookup"><span data-stu-id="9fd97-143">Harness collective knowledge</span></span>
- <span data-ttu-id="9fd97-144">사용자가 비즈니스 프로세스를 혁신하도록 지원</span><span class="sxs-lookup"><span data-stu-id="9fd97-144">Empower users to transform business processes</span></span>
- <span data-ttu-id="9fd97-145">기업 문화 조성</span><span class="sxs-lookup"><span data-stu-id="9fd97-145">Shape the company culture</span></span>
- <span data-ttu-id="9fd97-146">비즈니스 목표에 맞게 프로젝트, 작업 및 기한 관리</span><span class="sxs-lookup"><span data-stu-id="9fd97-146">Manage projects, tasks, and deadlines to meet your business objectives</span></span>
- <span data-ttu-id="9fd97-147">Firstline worker가 디지털 혁신을 진행하도록 지원</span><span class="sxs-lookup"><span data-stu-id="9fd97-147">Engage your firstline workers to enable your Digital Transformation</span></span>
- <span data-ttu-id="9fd97-148">작업 습관을 이해하여 미치는 영향 개선</span><span class="sxs-lookup"><span data-stu-id="9fd97-148">Understand your work habits to improve your influence and impact</span></span>
- <span data-ttu-id="9fd97-149">파트너, 동료 및 고객과 의사 소통</span><span class="sxs-lookup"><span data-stu-id="9fd97-149">Communicate with partners, colleagues, and customers</span></span>
- <span data-ttu-id="9fd97-150">조직 내부 및 외부에서 파일을 저장 및 공유하여 조직 경계를 넘나들며 원활하게 작업 가능</span><span class="sxs-lookup"><span data-stu-id="9fd97-150">Store and share files inside and outside your organization to work seamlessly across organizational boundaries</span></span>
- <span data-ttu-id="9fd97-151">유연한 작업 스타일을 유지하면서 어떤 장치를 사용하든 장소나 시간의 구애를 받지 않고 안전하게 더 많은 작업 처리</span><span class="sxs-lookup"><span data-stu-id="9fd97-151">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="9fd97-152">사용자의 정보 보호 및 데이터 손실 위험 최소화</span><span class="sxs-lookup"><span data-stu-id="9fd97-152">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="9fd97-153">개인 정보 보호 및 규정 준수로 조직이 GDPR(일반 데이터 보호 규정)을 준수하도록 지원</span><span class="sxs-lookup"><span data-stu-id="9fd97-153">Support your organization with enhanced privacy and compliance to meet the General Data Protection Regulation (GDPR)</span></span>

<span data-ttu-id="9fd97-154">자세한 내용은 [Microsoft 365를 사용한 디지털 변환](http://transform.microsoft.com)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fd97-154">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

#### <a name="sharepoint-online-site-for-highly-regulated-data"></a><span data-ttu-id="9fd97-155">높은 규제 대상 데이터에 대한 SharePoint Online 사이트</span><span class="sxs-lookup"><span data-stu-id="9fd97-155">SharePoint Online site for highly regulated data</span></span>

<span data-ttu-id="9fd97-p106">높은 규제 대상 데이터는 지역 규제가 적용되는 데이터이거나 영업 비밀, 재무 또는 인사 관련 정보와 조직의 전략과 같이 조직에서 가장 중요한 데이터를 나타냅니다. 이 유형의 데이터에 대해 제한된 액세스, 데이터 분류, 데이터 손실 방지 및 암호화를 구성할 수 있습니다. 자세한 내용은 [높은 규제 대상 데이터에 대한 Microsoft Teams 및 SharePoint Online 사이트](teams-sharepoint-online-sites-highly-regulated-data.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fd97-p106">Highy regulated data is subject to regional regulations or is the most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy. You can configure a SharePoint Online site for restricted access, data classification, data loss prevention, and encryption for this type of data. For the details, see [Microsoft Teams and SharePoint Online sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>

#### <a name="result"></a><span data-ttu-id="9fd97-159">결과</span><span class="sxs-lookup"><span data-stu-id="9fd97-159">Result</span></span>
<span data-ttu-id="9fd97-160">조직의 문서 저장 및 공유, 콘텐츠 관리, 공동 작업에 대한 요구를 충족하는 SharePoint Online 시나리오 목록을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-160">A list of SharePoint Online scenarios that address your organization’s needs for document storage and sharing, content management, and collaboration.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="9fd97-161">2단계: 온보딩</span><span class="sxs-lookup"><span data-stu-id="9fd97-161">Phase 2: Onboard</span></span>

<span data-ttu-id="9fd97-162">이 단계에서는 SharePoint Online 배포의 기술적 측면을 계획하고 선택한 사용자 그룹에 롤아웃하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-162">In this phase, you plan for the technical aspects of a SharePoint Online deployment and start rolling then out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="9fd97-163">필수 구성 요소: ID 및 장치 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="9fd97-163">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="9fd97-164">SharePoint Online 사이트에 대한 액세스를 보호하려면 [ID 및 장치 액세스 정책](identity-access-policies.md) 및 [권장 SharePoint Online 액세스 정책](sharepoint-file-access-policies.md)을 구성했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-164">To protect access to SharePoint Online sites, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="9fd97-165">1단계: 기술 계획 완료</span><span class="sxs-lookup"><span data-stu-id="9fd97-165">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="9fd97-p107">기술 계획을 시작하기 전에 FastTrack을 사용할지 여부를 결정합니다. 조직에 50명이 넘는 사용자가 있고 [적격 요금제](https://technet.microsoft.com/library/dn783224.aspx)에 가입한 경우 추가 비용 없이 사용 가능한 FastTrack 이점을 사용하여 계획, 배포 및 서비스 도입을 안내할 수 있습니다. 또는 Office 365 계정으로 로그인하면 [FastTrack](https://fasttrack.microsoft.com/)에서 제공되는 FastTrack 온보딩 마법사를 사용하여 이 작업을 직접 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-p107">Before you begin technical planning, determine whether you want to use FastTrack. If your organization has over 50 seats and is participating in an [eligible plan](https://technet.microsoft.com/library/dn783224.aspx), you can use FastTrack benefits, available at no additional cost to guide you through planning, deployment, and service adoption. Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Office 365 account.</span></span>

<span data-ttu-id="9fd97-p108">사용자 고유의 계획을 수행하거나 FastTrack과 연계해서 작업하는 경우 네트워크 및 조직이 SharePoint Online을 사용할 준비가 되어 있는지 확인해야 합니다. 특히, SharePoint Online 기반 문서의 추가 트래픽 성능을 극대화하기 위해 인터넷 대역폭, 처리량 및 트래픽 지연에 중점을 두고 기본 인프라의 네트워킹에 대한 종료 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-p108">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for SharePoint Online. It is especially important that you meet the exit criteria for networking in your foundation infrastructure, with special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for SharePoint Online-based documents.</span></span>

<span data-ttu-id="9fd97-171">다음과 같은 리소스를 사용하여 SharePoint Online 롤아웃의 기술적 측면을 대비하세요.</span><span class="sxs-lookup"><span data-stu-id="9fd97-171">Use these resources to prepare for the technical aspects of a SharePoint Online rollout:</span></span> 

- [<span data-ttu-id="9fd97-172">SharePoint Online 계획 가이드</span><span class="sxs-lookup"><span data-stu-id="9fd97-172">SharePoint Online Planning Guide</span></span>](https://support.office.com/article/sharepoint-online-planning-guide-abacd1bb-295d-4235-afdd-15f5e4cc2e6c)
- [<span data-ttu-id="9fd97-173">SharePoint Online으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="9fd97-173">Migrate to SharePoint Online</span></span>](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) 

<span data-ttu-id="9fd97-174">SharePoint Online의 보안을 보다 잘 이해하려면 다음 리소스를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="9fd97-174">For a better understanding of security in SharePoint Online, review the following resources:</span></span>

-   [<span data-ttu-id="9fd97-175">SharePoint Online 및 OneDrive가 클라우드에서 데이터를 보호하는 방법</span><span class="sxs-lookup"><span data-stu-id="9fd97-175">How SharePoint Online and OneDrive safeguard your data in the cloud</span></span>](https://support.office.com/article/How-SharePoint-Online-and-OneDrive-safeguard-your-data-in-the-cloud-5aa038e8-8ff0-4704-9e6a-fd72af0a2035)
-   [<span data-ttu-id="9fd97-176">비즈니스용 OneDrive 및 SharePoint Online에서의 데이터 암호화</span><span class="sxs-lookup"><span data-stu-id="9fd97-176">Data Encryption in OneDrive for Business and SharePoint Online</span></span>](https://support.office.com/article/Data-Encryption-in-OneDrive-for-Business-and-SharePoint-Online-6501B5EF-6BF7-43DF-B60D-F65781847D6C)

#### <a name="result"></a><span data-ttu-id="9fd97-177">결과</span><span class="sxs-lookup"><span data-stu-id="9fd97-177">Result</span></span>

<span data-ttu-id="9fd97-178">SharePoint Online 사이트 및 온-프레미스 폴더 및 문서 마이그레이션과 보안을 이해하고, 조직의 선택한 그룹에 SharePoint Online을 롤아웃하기 시작할 준비를 갖출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-178">You understand SharePoint Online sites and on-premises folder and document migration and security and are ready to begin rolling out SharePoint Online to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="9fd97-179">2단계: IT 파일럿 실행</span><span class="sxs-lookup"><span data-stu-id="9fd97-179">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="9fd97-p109">대부분의 중간 규모 및 대규모 조직에서는 1단계의 이해 관계자, 얼리 어답터 및 기술 전문가와 함께 IT 파일럿을 실행해야 합니다. IT 파일럿 중에 수행하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-p109">In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1 and early adopters and technical enthusiasts. During the IT pilot:</span></span>

- <span data-ttu-id="9fd97-182">IT 파일럿 참가자가 연습해볼 수 있는 SharePoint Online 비즈니스 시나리오를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-182">Choose a SharePoint Online business scenario in which your IT pilot participants can practice.</span></span>
- <span data-ttu-id="9fd97-183">파일럿 참가자들에게 SharePoint Online 문서 저장, 공유, 공동 작업, 팀 기반 일정 관리 및 기타 기능을 테스트할 수 있는 일련의 연습을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-183">Give your pilot participants a set of exercises to test SharePoint Online document storage, sharing, collaboration, team-based scheduling, and other capabilities.</span></span>
- <span data-ttu-id="9fd97-p110">변경 관리 전략을 결정하고 조직 전체의 SharePoint Online에 대한 사용자 도입을 촉진하기 위해 자료를 생성합니다. 변경 관리 자료에는 전자 메일 알림 텍스트, 내부 교육 계획, 포스터 및 프레젠테이션이 포함될 수 있습니다. 이러한 자료는 인지도 상승 및 사용 촉진 목표와 함께 SharePoint Online과 그 이점을 조직에 알려 줍니다. 몇 가지 아이디어는 [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)에 대한 변경 관리 전략 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fd97-p110">Determine your change management strategy and produce materials to drive organization-wide user adoption of SharePoint Online. Change management materials can include email announcement text, internal training plans, hallway posters, and presentations. These materials will inform your organization about SharePoint Online and its benefits with the goals of raising awareness and driving usage. See the change management strategy for [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) article for some ideas.</span></span>
- <span data-ttu-id="9fd97-p111">IT 파일럿 참가자가 자신의 경험에 따라 변경 관리 자료를 검토하게 합니다. 이들은 모범 사례에 대한 팁, SharePoint Online의 이점을 가장 잘 설명하는 방법에 대한 조언, 공동 작업 및 일정 예약에 이 제품을 사용하는 방법에 대한 조언 등을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-p111">Have your IT pilot participants review the change management materials based on their experiences. They can provide tips on best practices and advice on how to best describe the benefits of SharePoint Online and how to use it for communication and scheduling.</span></span>

#### <a name="result"></a><span data-ttu-id="9fd97-190">결과</span><span class="sxs-lookup"><span data-stu-id="9fd97-190">Result</span></span>

<span data-ttu-id="9fd97-191">SharePoint Online IT 파일럿이 완료되고 초기 변경 관리 자료가 개발, 검토 및 구체화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-191">Your SharePoint Online IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="9fd97-192">3단계: 비즈니스 그룹에 롤아웃</span><span class="sxs-lookup"><span data-stu-id="9fd97-192">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="9fd97-p112">IT 파일럿을 완료한 후에는 조직의 비즈니스 그룹이나 부서에 SharePoint Online을 롤아웃합니다. 이 롤아웃에는 다음이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-p112">After completing your IT pilot, roll out SharePoint Online to a business group or department in your organization. This rollout should include:</span></span>

- <span data-ttu-id="9fd97-195">비즈니스 그룹 내에서 SharePoint Online에 대한 주요 비즈니스 시나리오 식별</span><span class="sxs-lookup"><span data-stu-id="9fd97-195">Identification of key business scenarios for SharePoint Online within the business group.</span></span>
- <span data-ttu-id="9fd97-196">부서, 작업 또는 프로젝트 팀에 SharePoint Online을 사용할 예상 일정을 사용자에게 알리는 공지 활동</span><span class="sxs-lookup"><span data-stu-id="9fd97-196">Announcement activities to inform users of the expectations and timelines for SharePoint Online usage for departments and work or project teams.</span></span>
- <span data-ttu-id="9fd97-197">비즈니스 그룹 구성원의 온-프레미스 폴더 및 문서를 SharePoint Online으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="9fd97-197">Migration of on-premises folders and documents of your business group members to SharePoint Online.</span></span>
- <span data-ttu-id="9fd97-p113">SharePoint Online을 도입하기 위한 사용자 교육 또는 리소스 링크와 사용 방법 전달. [SharePoint Online](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) 비디오 교육을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fd97-p113">Delivering user training or links to resources to introduce SharePoint Online and how to use it. See [SharePoint Online](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) video training.</span></span>
- <span data-ttu-id="9fd97-200">비즈니스 그룹의 사용자로부터 의견을 수집하고 문제에 대해 조치를 취하기 위한 피드백 메커니즘(예: 비즈니스 그룹의 모든 사용자를 포함하는 중앙 Microsoft Teams 팀)</span><span class="sxs-lookup"><span data-stu-id="9fd97-200">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>
 
<span data-ttu-id="9fd97-201">롤아웃하는 동안 조직 차원의 롤아웃을 준비하려면 변경 관리 자료를 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-201">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="9fd97-202">결과</span><span class="sxs-lookup"><span data-stu-id="9fd97-202">Result</span></span>

<span data-ttu-id="9fd97-203">SharePoint Online을 통해 비즈니스 그룹이 운영되고 변경 관리 자료가 테스트 및 구체화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-203">A business group is up and running with SharePoint Online and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="9fd97-204">3단계: 가치 창출</span><span class="sxs-lookup"><span data-stu-id="9fd97-204">Phase 3: Drive value</span></span>

<span data-ttu-id="9fd97-205">이 단계에서는 SharePoint Online의 롤아웃을 완료하여 사용자가 이점을 실현하도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-205">In this phase, you complete the rollout of SharePoint Online support your users to help them realize its benefits.</span></span>

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a><span data-ttu-id="9fd97-206">1단계: 조직의 나머지 구성원에게 롤아웃</span><span class="sxs-lookup"><span data-stu-id="9fd97-206">Step 1: Roll out to the rest of your organization</span></span>

<span data-ttu-id="9fd97-207">나머지 조직 구성원에게 롤아웃하는 과정에는 다음이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-207">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="9fd97-208">분리된 비즈니스 그룹 내에서 SharePoint Online에 대한 주요 비즈니스 시나리오 식별</span><span class="sxs-lookup"><span data-stu-id="9fd97-208">Identification of key business scenarios for SharePoint Online Online within separate business groups.</span></span>
- <span data-ttu-id="9fd97-209">구체화된 변경 관리 자료를 사용하여 사용에 따른 예상 결과 및 일정을 조직에 알리는 공지 활동</span><span class="sxs-lookup"><span data-stu-id="9fd97-209">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for usage.</span></span>
- <span data-ttu-id="9fd97-210">나머지 조직 구성원의 폴더 및 문서를 SharePoint Online으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="9fd97-210">Migration of folders and documents for the rest of your organization to SharePoint Online.</span></span>
- <span data-ttu-id="9fd97-211">SharePoint Online을 도입하기 위한 사용자 교육 및 리소스 링크와 사용 방법 전달</span><span class="sxs-lookup"><span data-stu-id="9fd97-211">Delivering user training or provide links to resources to introduce SharePoint Online and how to use it.</span></span>
- <span data-ttu-id="9fd97-p114">조직의 사용자로부터 의견 및 문제를 수집하기 위한 피드백 메커니즘(예: 모든 사용자를 포함하는 중앙 팀). 조직의 사용자가 2500명 미만인 경우 Teams의 공개 채널을 사용하고, 2500명 이상인 경우 Yammer의 공용 그룹 사용</span><span class="sxs-lookup"><span data-stu-id="9fd97-p114">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="9fd97-215">결과</span><span class="sxs-lookup"><span data-stu-id="9fd97-215">Result</span></span>
<span data-ttu-id="9fd97-216">조직이 운영되며, 사용자에게 알림 및 교육을 제공하고 SharePoint Online을 사용할 수 있도록 하는 변경 관리 전략이 수립되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-216">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use SharePoint Online.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="9fd97-217">2단계: 사용 현황 측정, 만족도 관리 및 도입 촉진</span><span class="sxs-lookup"><span data-stu-id="9fd97-217">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="9fd97-218">전체 조직에 롤아웃한 후에는 변경 관리 전략을 계속 실행하여 다음 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-218">After rolling out to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="9fd97-219">책임자가 SharePoint Online이 문서 저장과 공유, 팀, 부서 또는 조직 전체의 공동 작업을 위한 기본 도구로 사용되도록 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-219">Have your leadership promote SharePoint Online as the primary tool for document storage and sharing and team, division, or organization-wide collaboration.</span></span>
- <span data-ttu-id="9fd97-220">개인이 비즈니스 그룹, 부서, 업무 및 프로젝트 팀 의사 소통과 공동 작업에 이러한 제품을 사용하도록 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-220">Encourage individuals to use it for business group, departmental, work, and project team collaboration and calendaring.</span></span>

<span data-ttu-id="9fd97-221">다음은 몇 가지 추천 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-221">Here are some suggested activities:</span></span>

- <span data-ttu-id="9fd97-222">[Office 365 도입 지침](https://aka.ms/successfactors)을 통해 클라우드 서비스 도입에 대한 일반적인 모범 사례를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-222">See [Office 365 adoption guidance](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="9fd97-p115">[Office 365 활동 보고서](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)를 통해 조직 전체의 Office 365 서비스 사용을 이해합니다. 조직의 Office 365 전역 관리자에게 활동 보고서에 액세스할 수 있도록 사용자 계정에 보고서 읽기 권한자 권한을 부여해 달라고 요청합니다(Office 365 전역 관리자가 아닌 경우).</span><span class="sxs-lookup"><span data-stu-id="9fd97-p115">See [Office 365 activity reports](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="9fd97-p116">피드백 공간(중앙 Teams 팀 또는 Yammer의 공개 채널)에서 개인의 SharePoint Online 사용 경험에 대한 피드백 및 문제를 모니터링합니다. 최대한 신속하게 질문과 문제를 해결하여 개인의 불만을 방지하고 롤아웃 지원을 예시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-p116">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with SharePoint Online. Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="9fd97-p117">각 비즈니스 그룹에서 챔피언을 식별 및 육성하고 이들의 SharePoint Online 사용 성과 및 모범 사례를 강조합니다. 이들의 성공을 조직에 반영하여 프로젝트 성공 및 도입을 보여 줍니다. 비즈니스 그룹 내 기술 책임자의 보증은 리더 및 동료에게 강력한 영향을 발휘할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-p117">Identify and nurture champions in each business group and highlight their accomplishments and best practices by using SharePoint Online. Reflect their successes out to the organization to show project success and adoption. Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="9fd97-230">결과</span><span class="sxs-lookup"><span data-stu-id="9fd97-230">Result</span></span>

<span data-ttu-id="9fd97-231">조직은 문서 저장 및 공동 작업을 지원하기 위한 서비스로 SharePoint Online를 채택했습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd97-231">Your organization has adopted SharePoint Online as a service to support documentation storage and collaboration.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="9fd97-232">Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법</span><span class="sxs-lookup"><span data-stu-id="9fd97-232">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="9fd97-233">Microsoft 내부 상황을 살펴보고 Microsoft에서 SharePoint Online을 배포한 방식을 알아보려면 [SharePoint를 클라우드로: Microsoft가 자체 마이그레이션을 수행한 방법 알아보기](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fd97-233">To peek inside Microsoft and learn how the company deployed SharePoint Online, see [SharePoint to the cloud: Learn how Microsoft ran its own migration](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9fd97-234">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9fd97-234">Next steps</span></span>

<span data-ttu-id="9fd97-235">SharePoint Online의 지속적인 유지 관리에 대한 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fd97-235">See these resources for the ongoing maintenance of SharePoint Online:</span></span> 

- [<span data-ttu-id="9fd97-236">SharePoint의 권한 수준 이해</span><span class="sxs-lookup"><span data-stu-id="9fd97-236">Understanding permission levels in SharePoint</span></span>](https://support.office.com/article/Understanding-permission-levels-in-SharePoint-87ecbb0e-6550-491a-8826-c075e4859848)
- [<span data-ttu-id="9fd97-237">SharePoint 사이트 사용 권한 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="9fd97-237">Customize SharePoint site permissions</span></span>](https://support.office.com/article/Customize-SharePoint-site-permissions-b1e3cd23-1a78-4264-9284-87fed7282048)
- [<span data-ttu-id="9fd97-238">SharePoint Online에 대한 외부 공유 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="9fd97-238">Turn external sharing on or off for SharePoint Online</span></span>](https://support.office.com/article/Turn-external-sharing-on-or-off-for-SharePoint-Online-6288296a-b6b7-4ea4-b4ed-c297bf833e30)
- [<span data-ttu-id="9fd97-239">액세스 요청 설정 및 관리</span><span class="sxs-lookup"><span data-stu-id="9fd97-239">Set up and manage access requests</span></span>](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)

