---
title: Microsoft 365 Enterprise용 Microsoft Teams 배포
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: 조직 전체에서 Microsoft 365 Enterprise의 Microsoft Teams를 계획 및 롤아웃하고 가치를 창출하는 프로세스를 안내합니다.
ms.openlocfilehash: 646062babf525be176386264b4ef3c4a3a21647a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291662"
---
# <a name="deploy-microsoft-teams-for-microsoft-365-enterprise"></a><span data-ttu-id="1d24c-103">Microsoft 365 Enterprise용 Microsoft Teams 배포</span><span class="sxs-lookup"><span data-stu-id="1d24c-103">Deploy Microsoft Teams for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="1d24c-104">*이 작업은 Microsoft 365 Enterprise E3 및 E5 버전에 모두 포함됩니다.*</span><span class="sxs-lookup"><span data-stu-id="1d24c-104">*This step is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="1d24c-p101">Microsoft Teams는 간편하게 콘텐츠를 만들고 그룹 간에 공유할 수 있는 방식으로 채팅, 회의, 문서 공유 및 스레드된 대화를 통합합니다. Teams는 Microsoft 365 Enterprise에 대한 팀 작업 및 공동 작업을 수행하는 방법이며, Microsoft 365가 강조하는 팀 작업(Built for Teamwork) 가치의 주요 요소입니다. Teams를 처음 접하는 경우 [Microsoft Teams 개요](https://docs.microsoft.com/MicrosoftTeams/teams-overview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d24c-p101">Microsoft Teams brings together chat, conferencing, document sharing, and threaded conversations in a way that makes it easy to create and share content across groups. Teams is the way you do teamwork and collaboration for Microsoft 365 Enterprise and is a key element of the Built for Teamwork value of Microsoft 365. If you are brand new to Teams, see [Overview of Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview).</span></span>
 
<span data-ttu-id="1d24c-p102">현재 비즈니스용 Skype를 사용 중인 경우 비즈니스용 Skype 기능을 Teams에 구축할 수 있습니다. 이는 향후에 지원될 예정이며 궁극적으로 Teams는 단일 클라이언트 환경이 될 것입니다. Microsoft는 소중한 비즈니스용 Skype 고객인 여러분을 항상 곁에서 지원해 드릴 것입니다. 자세한 내용은 [비즈니스용 Skype에서 Microsoft Teams로 전환](https://docs.microsoft.com/microsoftteams/journey-skypeforbusiness-teams)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d24c-p102">If you’re currently using Skype for Business, we’re building Skype for Business capabilities into Teams. This will happen over time, and ultimately Teams will become the single client experience. As a valued Skype for Business customer, Microsoft is here to support you. See the [Journey from Skype for Business to Microsoft Teams](https://docs.microsoft.com/microsoftteams/journey-skypeforbusiness-teams) for more information.</span></span>

<span data-ttu-id="1d24c-112">다음 단계에서는 조직에서 Teams 역할을 구상하고, 일련의 점진적 롤아웃을 통해 조직을 Teams에 온보딩하며, Teams 사용을 촉진하고 최종 사용자를 위한 가치를 창출하는 프로세스를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-112">The following phases and steps guide you through the process of envisioning the role of Teams in your organization, onboarding your organization to Teams through a series of progressive rollouts, and driving usage of Teams and its value to your end users.</span></span> 

<span data-ttu-id="1d24c-113">시작하기 전에 팀에서 필요한 보안 기능을 갖출 수 있도록 적절한 [기초 인프라](deploy-foundation-infrastructure.md) 단계를 구성했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-113">Before you begin, make sure you've configured the right [foundation infrastructure](deploy-foundation-infrastructure.md) phases so that your teams have the security capabilities you need.</span></span>

## <a name="phase-1-envision"></a><span data-ttu-id="1d24c-114">1단계: 구상</span><span class="sxs-lookup"><span data-stu-id="1d24c-114">Phase 1: Envision</span></span>

<span data-ttu-id="1d24c-115">이 단계에서는 Teams 배포를 위해 구성원을 모으고 조직에서 Teams를 사용하여 비즈니스 요구 사항을 해결하는 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-115">In this phase, you gather the people for your Teams deployment and determine how your organization will use Teams to address its business needs.</span></span>

### <a name="step-1-gather-your-teams-deployment-members"></a><span data-ttu-id="1d24c-116">1단계: Teams 배포 구성원 모으기</span><span class="sxs-lookup"><span data-stu-id="1d24c-116">Step 1: Gather your Teams deployment members</span></span>
<span data-ttu-id="1d24c-p103">Microsoft 365 [기본 인프라](deploy-foundation-infrastructure.md)에 Teams를 성공적으로 배포하려면 입력 및 피드백을 위해 올바른 구성원을 모아야 합니다. 주요 구성원에는 비즈니스 의사 결정권자, IT 담당자(예: 설계자 및 구현자) 및 최종 사용자의 대변자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-p103">For a successful deployment of Teams on top of the Microsoft 365 [foundation infrastructure](deploy-foundation-infrastructure.md), you need to get the right people for input and feedback. Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="1d24c-119">이 세 그룹은 비즈니스 요구 사항, 라이선싱의 기술적 측면 및 보안을 다루는 고려 사항이 Teams 배포에 포함되고 일반 사용자가 Teams를 사용하도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-119">These three groups ensure that your Teams deployment includes considerations that address business needs, technical aspects of licensing and security, and that Teams will be something that your typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="1d24c-120">결과</span><span class="sxs-lookup"><span data-stu-id="1d24c-120">Result</span></span>

<span data-ttu-id="1d24c-121">조직의 비즈니스, 기술 및 최종 사용자 측면을 대표하는 구성원 목록을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-121">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-teams-business-scenarios"></a><span data-ttu-id="1d24c-122">2단계: Teams 비즈니스 시나리오 확인 및 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="1d24c-122">Step 2: Determine and prioritize your Teams business scenarios</span></span>
<span data-ttu-id="1d24c-p104">여러 가지 목적으로 Teams를 사용할 수 있습니다. 비즈니스 그룹, 부서, 개별 작업 및 프로젝트 팀 등 조직의 개별 수준에서 비즈니스 요구 사항에 매핑할 항목을 파악해야 합니다. Teams 시나리오를 정의하는 데 유용한 예는 [Microsoft 365 생산성 라이브러리](https://www.microsoft.com/en-us/microsoft-365/success/?rtc=1)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d24c-p104">Teams can be used for many different purposes. You need to figure out which purposes map to your business needs on the separate levels of your organization, your business groups, your departments, and individual working and project teams. Take a look at the [Microsoft 365 Productivity Library](https://www.microsoft.com/en-us/microsoft-365/success/?rtc=1) for examples to help you define Teams scenarios.</span></span> 

<span data-ttu-id="1d24c-p105">빠르게 움직이고 고도의 공동 작업을 수행하면서 밀접하게 협력하고 Exchange Online에서 제공할 수 있는 전자 메일보다 훨씬 다양한 기능을 필요로 하는 팀의 요구를 충족하는 데 Teams를 사용해야 합니다. 예를 들어 녹음된 기록을 사용하는 실시간 그룹 채팅 및 파일 및 메모를 저장할 수 있는 일반적이고 찾기 쉬운 위치 등을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-p105">You should target Teams to address fast-moving and highly collaborative teams that work closely together and require many more facilities than just email with Exchange Online can provide. Examples are live group chats with a recorded history and a common and easy-to-find place to store files and notes.</span></span> 

<span data-ttu-id="1d24c-128">Teams의 이점을 확인하는 한 가지 방법은 팀이 현재 상호 작용하는 방식을 조사한 다음 상호 작용을 대체하고 보다 간편한 공동 작업 방법을 제공하는 적절한 Teams 시나리오를 찾아서 추가 기능을 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-128">One way to see the benefits of Teams is to examine how a team or v-team interacts today, and then find an appropriate Teams scenario that replaces the interaction and provides easier ways to collaborate and provide additional capabilities.</span></span>

<span data-ttu-id="1d24c-129">Teams는 다음과 같은 Microsoft 365 Enterprise에 대한 전략적 비즈니스 시나리오를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-129">Teams enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="1d24c-130">팀과 소통하여 정보를 제공하고, 정보 제공을 요청하고, 협력 및 의견 합의 도달</span><span class="sxs-lookup"><span data-stu-id="1d24c-130">Communicate with your team to stay informed, solicit input, and build cohesion and consensus</span></span>
- <span data-ttu-id="1d24c-131">최전방 작업자들이 디지털 혁신을 진행하도록 지원</span><span class="sxs-lookup"><span data-stu-id="1d24c-131">Engage your firstline workers to enable your Digital Transformation</span></span>
- <span data-ttu-id="1d24c-132">작업 습관을 이해하여 미치는 영향 개선</span><span class="sxs-lookup"><span data-stu-id="1d24c-132">Understand your work habits to improve your influence and impact</span></span>

<span data-ttu-id="1d24c-133">자세한 내용은 [Microsoft 365를 사용한 디지털 변환](http://transform.microsoft.com)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d24c-133">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

#### <a name="microsoft-teams-for-highly-regulated-data"></a><span data-ttu-id="1d24c-134">높은 규제 대상 데이터에 대한 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1d24c-134">Microsoft Teams for highly regulated data</span></span>

<span data-ttu-id="1d24c-p106">높은 규제 대상 데이터는 지역 규제가 적용되는 데이터이거나 영업 비밀, 재무 또는 인사 관련 정보와 조직의 전략과 같이 조직에서 가장 중요한 데이터를 나타냅니다. 이 유형의 데이터에 대한 제한된 액세스, 데이터 분류, 데이터 손실 방지 및 암호화를 위해 팀을 구성할 수 있습니다. 자세한 내용은 [높은 규제 대상 데이터에 대한 Microsoft Teams 및 SharePoint Online 사이트](teams-sharepoint-online-sites-highly-regulated-data.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d24c-p106">Highy regulated data is subject to regional regulations or is the most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy. You can configure a team for restricted access, data classification, data loss prevention, and encryption for this type of data. For the details, see [Microsoft Teams and SharePoint Online sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>

#### <a name="result"></a><span data-ttu-id="1d24c-138">결과</span><span class="sxs-lookup"><span data-stu-id="1d24c-138">Result</span></span>

<span data-ttu-id="1d24c-139">공동 작업 및 팀 작업에 대한 조직의 요구 사항을 해결하는 Teams 시나리오 목록을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-139">A list of Teams scenarios that address your organization’s needs for collaboration and teamwork.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="1d24c-140">2단계: 온보딩</span><span class="sxs-lookup"><span data-stu-id="1d24c-140">Phase 2: Onboard</span></span>

<span data-ttu-id="1d24c-141">이 단계에서는 Teams 배포의 기술적 측면을 계획하고 선택한 사용자 그룹에 Teams를 롤아웃하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-141">In this phase, you plan for the technical aspects of a Teams deployment and start rolling out Teams to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="1d24c-142">필수 구성 요소: ID 및 장치 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="1d24c-142">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="1d24c-143">팀에 대한 액세스를 보호하려면 [ID 및 장치 액세스 정책](identity-access-policies.md) 및 [권장 SharePoint Online 액세스 정책](sharepoint-file-access-policies.md)을 구성했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-143">To protect access to teams, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="1d24c-144">1단계: 기술 계획 완료</span><span class="sxs-lookup"><span data-stu-id="1d24c-144">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="1d24c-p107">기술 계획을 시작하기 전에 FastTrack을 사용할지 여부를 결정합니다. 조직에 50명이 넘는 사용자가 있고 [적격 요금제](https://technet.microsoft.com/library/dn783224.aspx)에 가입한 경우 추가 비용 없이 사용 가능한 [Microsoft 365용 FastTrack](https://fasttrack.microsoft.com/microsoft365)을 사용하여 계획, 배포 및 서비스 도입을 안내할 수 있습니다. 또는 Office 365 계정으로 로그인하면 [FastTrack](https://fasttrack.microsoft.com/)에서 제공되는 FastTrack 온보딩 마법사를 사용하여 이 작업을 직접 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-p107">Before you begin technical planning, determine whether you want to use FastTrack. If your organization has over 50 seats and is participating in an [eligible plan](https://technet.microsoft.com/library/dn783224.aspx), you can use [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365), available at no additional cost to guide you through planning, deployment and service adoption. Or, you can complete this work yourself using our FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Office 365 account.</span></span>

<span data-ttu-id="1d24c-p108">사용자 고유의 계획(또는 FastTrack과 결합된 계획)을 수행하는 경우 네트워크 및 조직이 Teams를 사용할 준비가 되어 있는지 확인해야 합니다. 특히, Teams 기반 모임 성능을 극대화하기 위해 대역폭, 처리량 및 트래픽 지연에 중점을 두고 [기본 인프라](deploy-foundation-infrastructure.md)의 네트워킹에 대한 종료 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-p108">If you are doing your own planning (or in conjunction with FastTrack), you need to determine if your network and organization are ready for Teams. It is especially important that you meet the exit criteria for networking in your [foundation infrastructure](deploy-foundation-infrastructure.md), with special attention to bandwidth, throughput, and traffic delays to maximize performance for Teams-based meetings.</span></span>

<span data-ttu-id="1d24c-150">다음 리소스를 사용하여 Teams 롤아웃을 위한 조직의 기술적 측면을 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-150">Use these resources to prepare the technical aspects of your organization for a Teams rollout:</span></span> 

- [<span data-ttu-id="1d24c-151">Teams에 대한 사용자 환경의 준비 상태 확인</span><span class="sxs-lookup"><span data-stu-id="1d24c-151">Check your environment's readiness for Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/environment-readiness)
- [<span data-ttu-id="1d24c-152">Teams에 맞게 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="1d24c-152">Prepare your network for Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/prepare-network)
- [<span data-ttu-id="1d24c-153">Office 365 URL 및 IP 주소 범위</span><span class="sxs-lookup"><span data-stu-id="1d24c-153">Office 365 URLs and IP address ranges</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)

<span data-ttu-id="1d24c-154">Teams의 보안을 보다 잘 이해하려면 다음 추가 리소스를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-154">For a better understanding of security in Teams, review the following additional resources:</span></span>

- [<span data-ttu-id="1d24c-155">Teams의 보안 및 준수 개요</span><span class="sxs-lookup"><span data-stu-id="1d24c-155">Overview of security and compliance in Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview)
- [<span data-ttu-id="1d24c-156">Office 365 그룹 및 Teams</span><span class="sxs-lookup"><span data-stu-id="1d24c-156">Office 365 groups and Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)
- [<span data-ttu-id="1d24c-157">Teams의 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="1d24c-157">Guest access in Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)

<span data-ttu-id="1d24c-158">이제, 다음 리소스를 사용하여 Teams 라이선싱을 이해하고 조직에 대한 Teams 설정을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-158">Next, use these resources to understand Teams licensing and to perform the setup of Teams for your organization:</span></span>

- [<span data-ttu-id="1d24c-159">Teams용 Office 365 라이선싱</span><span class="sxs-lookup"><span data-stu-id="1d24c-159">Office 365 licensing for Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)
- [<span data-ttu-id="1d24c-160">Microsoft Teams에 대한 사용자 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="1d24c-160">Manage user access to Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/user-access)
- [<span data-ttu-id="1d24c-161">Microsoft Teams용 클라이언트 다운로드</span><span class="sxs-lookup"><span data-stu-id="1d24c-161">Get clients for Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/get-clients)
- [<span data-ttu-id="1d24c-162">Office 365 조직에서 Microsoft Teams 설정</span><span class="sxs-lookup"><span data-stu-id="1d24c-162">Turn on Microsoft Teams in your Office 365 organization</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-set-up)
- [<span data-ttu-id="1d24c-163">Office 365 조직에서 Microsoft Teams 기능 관리</span><span class="sxs-lookup"><span data-stu-id="1d24c-163">Manage Microsoft Teams features in your Office 365 organization</span></span>](https://docs.microsoft.com/microsoftteams/enable-features-office-365)

#### <a name="result"></a><span data-ttu-id="1d24c-164">결과</span><span class="sxs-lookup"><span data-stu-id="1d24c-164">Result</span></span>

<span data-ttu-id="1d24c-165">네트워크, 보안 및 Office 365 라이선싱 계획이 완료되고 조직의 선택한 그룹에 Teams를 롤아웃할 준비가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-165">Your network, security, and Office 365 licensing planning is done and you are ready to begin rolling out Teams to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="1d24c-166">2단계: IT 파일럿 실행</span><span class="sxs-lookup"><span data-stu-id="1d24c-166">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="1d24c-p109">대부분의 중간 규모 및 대규모 조직에서는 1단계의 이해 관계자, 얼리 어답터 및 기술 전문가와 함께 IT 파일럿을 실행해야 합니다. IT 파일럿 중에 수행하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-p109">In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1 and early adopters and technical enthusiasts. During the IT pilot:</span></span>

- <span data-ttu-id="1d24c-p110">IT 파일럿 참가자가 실습할 수 있는 Teams 비즈니스 시나리오를 선택합니다. 자세한 내용은 [Microsoft Teams 시작 키트](http://microsoft.com/download/56505)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d24c-p110">Choose a Teams business scenario in which your IT pilot participants can practice. See the [Microsoft Teams getting started kit](http://microsoft.com/download/56505) for ideas.</span></span>
- <span data-ttu-id="1d24c-171">파일럿 참가자에게 Teams 기반 채팅, 파일 저장, 모임 및 기타 기능을 테스트할 수 있는 연습 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-171">Give your pilot participants a set of exercises to test Teams-based chats, file storage, meetings, and other capabilities.</span></span>
- <span data-ttu-id="1d24c-p111">변경 관리 전략을 결정하고 조직 전체의 사용자 도입을 촉진하기 위해 자료를 생성합니다. 변경 관리 자료에는 전자 메일 알림 텍스트, 내부 교육 계획, 포스터 및 프레젠테이션이 포함될 수 있습니다. 이러한 자료는 인지도 상승 및 사용 촉진 목표와 함께 Teams와 그 이점을 조직에 알려 줍니다. 몇 가지 아이디어는 [Microsoft Teams에 대한 변경 관리 전략](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d24c-p111">Determine your change management strategy and produce materials to drive organization-wide user adoption. Change management materials can include email announcement text, internal training plans, hallway posters, and presentations. These materials will inform your organization about Teams and its benefits with the goals of raising awareness and driving usage. See [change management strategy for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) for some ideas.</span></span>
- <span data-ttu-id="1d24c-p112">IT 파일럿 참가자가 자신의 경험에 따라 변경 관리 전략 자료를 검토하게 합니다. 이들은 모범 사례에 대한 팁, Teams의 이점을 가장 잘 설명하는 방법에 대한 조언, 공동 작업 및 팀 작업에 Teams를 사용하는 방법에 대한 조언 등을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-p112">Have your IT pilot participants review the change management strategy materials based on their experiences. They can provide tips on best practices and advice on how to best describe the benefits of Teams and how to use it for collaboration and teamwork.</span></span>

#### <a name="result"></a><span data-ttu-id="1d24c-178">결과</span><span class="sxs-lookup"><span data-stu-id="1d24c-178">Result</span></span>

<span data-ttu-id="1d24c-179">Teams IT 파일럿이 완료되고 초기 변경 관리 자료가 개발, 검토 및 구체화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-179">Your Teams IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="1d24c-180">3단계: 비즈니스 그룹에 롤아웃</span><span class="sxs-lookup"><span data-stu-id="1d24c-180">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="1d24c-p113">IT 파일럿을 완료한 후에는 조직의 비즈니스 그룹이나 부서에 Teams를 롤아웃합니다. 이 롤아웃에는 다음이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-p113">After completing your IT pilot, roll out Teams to a business group or department in your organization. This rollout should include:</span></span>

- <span data-ttu-id="1d24c-183">비즈니스 그룹 내에서 Teams에 대한 주요 비즈니스 시나리오 식별</span><span class="sxs-lookup"><span data-stu-id="1d24c-183">Identification of key business scenarios for Teams within the business group.</span></span>
- <span data-ttu-id="1d24c-184">부서, 작업 또는 프로젝트 팀에 Teams를 사용할 예상 일정을 사용자에게 알리는 공지 활동</span><span class="sxs-lookup"><span data-stu-id="1d24c-184">Announcement activities to inform users of the expectations and timelines for Teams usage for departmental, work, or project teams.</span></span>
- <span data-ttu-id="1d24c-185">Teams에 대한 사용자 교육 또는 Teams와 그 사용 방법을 소개하는 리소스의 링크 전달</span><span class="sxs-lookup"><span data-stu-id="1d24c-185">Direct user training on Teams or links to resources to introduce Teams and how to use it.</span></span>
- <span data-ttu-id="1d24c-186">비즈니스 그룹의 사용자로부터 의견 및 문제를 수집하기 위한 피드백 메커니즘(예: 비즈니스 그룹의 모든 사용자를 포함하는 중앙 팀)</span><span class="sxs-lookup"><span data-stu-id="1d24c-186">A feedback mechanism, such as a central team containing everyone in the business group, to collect comments and issues from users in the business group.</span></span>

<span data-ttu-id="1d24c-187">롤아웃하는 동안 조직 차원의 롤아웃을 준비하려면 변경 관리 자료를 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-187">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="1d24c-188">결과</span><span class="sxs-lookup"><span data-stu-id="1d24c-188">Result</span></span>

<span data-ttu-id="1d24c-189">Teams를 통해 비즈니스 그룹이 운영되고 변경 관리 자료가 테스트 및 구체화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-189">A business group is up and running with Teams and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="1d24c-190">3단계: 가치 창출</span><span class="sxs-lookup"><span data-stu-id="1d24c-190">Phase 3: Drive value</span></span>

<span data-ttu-id="1d24c-191">이 단계에서는 조직에 Teams를 롤아웃하고 사용자가 그 이점을 실현할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-191">In this phase, you complete the rollout of Teams to your organization and support your users so that they are realizing its benefits.</span></span>

### <a name="step-1-roll-out-teams-to-the-rest-of-your-organization"></a><span data-ttu-id="1d24c-192">1단계: 조직의 나머지 구성원에게 Teams 롤아웃</span><span class="sxs-lookup"><span data-stu-id="1d24c-192">Step 1: Roll out Teams to the rest of your organization</span></span>

<span data-ttu-id="1d24c-p114">대상 비즈니스 그룹에 롤아웃을 완료한 후에는 조직의 나머지 구성원에게 Teams를 롤아웃합니다. 이 롤아웃에는 다음이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-p114">After completing your rollout to a targeted business group, roll out Teams to the rest of your organization. This rollout should include:</span></span>

- <span data-ttu-id="1d24c-195">개별 비즈니스 그룹 내에서 Teams에 대한 주요 비즈니스 시나리오 식별</span><span class="sxs-lookup"><span data-stu-id="1d24c-195">Identification of key business scenarios for Teams within your separate business groups.</span></span>
- <span data-ttu-id="1d24c-196">구체화된 변경 관리 자료를 사용하여 부서, 작업 또는 프로젝트 팀에 Teams를 사용할 예상 일정을 조직에 알리는 공지 활동</span><span class="sxs-lookup"><span data-stu-id="1d24c-196">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for Teams usage for departmental, work, or project teams.</span></span>
- <span data-ttu-id="1d24c-p115">Teams에 대한 사용자 교육 또는 Teams와 그 사용 방법을 소개하는 리소스의 링크 전달(교육 리소스는 [Microsoft Teams에 대한 최종 사용자 교육](https://docs.microsoft.com/microsoftteams/enduser-training) 참조)</span><span class="sxs-lookup"><span data-stu-id="1d24c-p115">Delivering user training on Teams or links to resources to introduce Teams and how to use it. See the training resources at [End user training for Microsoft Teams](https://docs.microsoft.com/microsoftteams/enduser-training).</span></span>
- <span data-ttu-id="1d24c-p116">조직의 사용자로부터 의견 및 문제를 수집하기 위한 피드백 메커니즘(예: 모든 사용자를 포함하는 중앙 팀). 조직의 사용자가 2500명 미만인 경우 Teams의 공개 채널을 사용하고, 2500명 이상인 경우 Yammer의 공용 그룹 사용</span><span class="sxs-lookup"><span data-stu-id="1d24c-p116">A feedback mechanism, such as a central team containing everyone, to collect comments and act on issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="1d24c-202">결과</span><span class="sxs-lookup"><span data-stu-id="1d24c-202">Result</span></span>

<span data-ttu-id="1d24c-203">조직이 운영되며, 사용자에게 알림 및 교육을 제공하고 Teams 사용을 시작할 수 있도록 하는 변경 관리 전략이 수립되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-203">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to begin using Teams.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="1d24c-204">2단계: 사용 현황 측정, 만족도 관리 및 도입 촉진</span><span class="sxs-lookup"><span data-stu-id="1d24c-204">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="1d24c-205">전체 조직에 Teams를 롤아웃한 후에는 변경 관리 전략을 계속 실행하여 다음 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-205">After rolling out Teams to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="1d24c-206">조직의 리더가 조직의 팀 작업 및 공동 작업 도구로 Teams를 홍보하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-206">Have your leadership promote Teams as the teamwork and collaboration tool for the organization.</span></span>
- <span data-ttu-id="1d24c-207">개인이 비즈니스 그룹, 부서, 작업 및 프로젝트 팀 통신 및 공동 작업에 Teams를 사용하도록 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-207">Encourage individuals to use it for business group, departmental, work, and project team communications and collaboration.</span></span>

<span data-ttu-id="1d24c-208">다음은 몇 가지 추천 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-208">Here are some suggested activities:</span></span>

- <span data-ttu-id="1d24c-209">[Office 365 도입 지침](https://aka.ms/successfactors)을 통해 클라우드 서비스 도입에 대한 일반적인 모범 사례를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-209">See [Office 365 adoption guidance](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="1d24c-p117">[Office 365 활동 보고서](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)를 통해 조직 전체의 Office 365 서비스 사용을 이해합니다. 조직의 Office 365 전역 관리자에게 활동 보고서에 액세스할 수 있도록 사용자 계정에 보고서 읽기 권한자 권한을 부여해 달라고 요청합니다(Office 365 전역 관리자가 아닌 경우).</span><span class="sxs-lookup"><span data-stu-id="1d24c-p117">See [Office 365 activity reports](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is to grant your user account Reports Reader permissions so you can access activity reports.</span></span>
- <span data-ttu-id="1d24c-p118">피드백 공간(중앙 팀 또는 Yammer의 공개 채널)에서 개인의 Teams 사용 경험에 대한 피드백 및 문제를 모니터링합니다. 최대한 신속하게 질문과 문제를 해결하면 개인의 불만 및 Teams 포기를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-p118">Monitor your feedback venue (a public channel in a central team or Yammer) for issues and feedback from individuals about their experiences with Teams. Address questions and issues as quickly as you can to prevent frustration and abandonment of Teams by individuals.</span></span>
- <span data-ttu-id="1d24c-p119">각 비즈니스 그룹에서 챔피언을 식별 및 육성하고 이들의 Teams 사용 성과 및 모범 사례를 강조합니다. 이들의 성공을 조직에 반영하여 프로젝트 성공 및 도입을 보여 줍니다. 비즈니스 그룹 내 기술 책임자의 보증은 리더 및 동료에게 강력한 영향을 발휘할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-p119">Identify and nurture your champions in each business group and highlight their accomplishments and best practices using Teams. Reflect their successes out to the organization to show project success and adoption. Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="1d24c-217">결과</span><span class="sxs-lookup"><span data-stu-id="1d24c-217">Result</span></span>

<span data-ttu-id="1d24c-218">조직에서 공동 작업 및 팀 작업 도구로 Teams를 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="1d24c-218">Your organization has adopted Teams as its collaboration and teamwork tool.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="1d24c-219">Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법</span><span class="sxs-lookup"><span data-stu-id="1d24c-219">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="1d24c-220">Microsoft 내부를 들여다보고 Microsoft가 Microsoft Teams를 배포하고 사용하여 공동 작업하는 방법을 알아보려면 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d24c-220">To peek inside Microsoft and learn how the company deployed and is using Microsoft Teams for collaboration, see:</span></span>

- [<span data-ttu-id="1d24c-221">Microsoft Teams 배포를 통한 공동 작업의 간소화 및 팀워크 개선</span><span class="sxs-lookup"><span data-stu-id="1d24c-221">Deploying Microsoft Teams streamlines collaboration and improves teamwork</span></span>](https://www.microsoft.com/itshowcase/Article/Content/1013/Deploying-Microsoft-Teams-streamlines-collaboration-and-improves-teamwork)
- [<span data-ttu-id="1d24c-222">Microsoft Teams를 통한 최신 Microsoft 작업 공간에서의 공동 작업 증가</span><span class="sxs-lookup"><span data-stu-id="1d24c-222">Microsoft Teams increases collaboration in the modern workplace at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/1012/Microsoft-Teams-increases-collaboration-in-the-modern-workplace-at-Microsoft)

## <a name="next-steps"></a><span data-ttu-id="1d24c-223">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1d24c-223">Next steps</span></span>

- [<span data-ttu-id="1d24c-224">Office 365 조직에서 Microsoft Teams 기능 관리</span><span class="sxs-lookup"><span data-stu-id="1d24c-224">Manage Microsoft Teams features in your Office 365 organization</span></span>](https://docs.microsoft.com/microsoftteams/enable-features-office-365)
- [<span data-ttu-id="1d24c-225">Microsoft Teams에 대한 관리 교육</span><span class="sxs-lookup"><span data-stu-id="1d24c-225">Admin training for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/itadmin-readiness)
