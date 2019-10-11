---
title: Microsoft 365 Enterprise에 대 한 Exchange Online 배포
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-email-calendar
ms.custom:
- Strat_O365_Enterprise
description: 조직 전체에서 Microsoft 365 Enterprise의 Exchange Online 가치를 계획, 롤아웃 및 추진 하는 프로세스를 안내 합니다.
ms.openlocfilehash: c11a4ca0216d42f039005616c5d414759b8c0bad
ms.sourcegitcommit: db580dc2626328d324f65c7380a5816a500688a7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2019
ms.locfileid: "37437818"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a><span data-ttu-id="d3637-103">Microsoft 365 Enterprise에 대 한 Exchange Online 배포</span><span class="sxs-lookup"><span data-stu-id="d3637-103">Deploy Exchange Online for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="d3637-104">*이 작업은 Microsoft 365 Enterprise E3 및 E5 버전에 모두 포함됩니다.*</span><span class="sxs-lookup"><span data-stu-id="d3637-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="d3637-105">Exchange Online은 전자 메일 및 일정 관리를 위한 기본 클라우드 서비스로, 사용자가 실시간 채팅 또는 중앙화된 문서 저장을 필요로 하지 않는 방식으로 공동 작업하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-105">Exchange Online is your primary cloud service for email and calendaring that helps your users collaborate in ways that do not require real-time chatting or centralized document storage.</span></span> <span data-ttu-id="d3637-106">Exchange Online은 Microsoft 365 Enterprise의 기본 제공 팀 작업 값의 주요 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-106">Exchange Online is a key element of the Built for Teamwork value of Microsoft 365 Enterprise.</span></span> <span data-ttu-id="d3637-107">Exchange Online을 사용 하는 경우에는 장치에 관계 없이 잘 알려진 Outlook 응용 프로그램을 보다 효율적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-107">Exchange Online lets you accomplish more and work more effectively with the well-known Outlook application, no matter what device you’re on.</span></span>

<span data-ttu-id="d3637-108">또한 Exchange Online은 맬웨어 방지 및 스팸 방지 필터링을 비롯하여 사용자가 실수로 중요한 정보를 권한이 없는 사용자에게 보내는 것을 방지하는 사서함 및 데이터 손실 방지 기능을 보호하는 고급 보안 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-108">Exchange Online also has advanced security capabilities including anti-malware and anti-spam filtering to protect mailboxes and data loss prevention capabilities that prevent users from mistakenly sending sensitive information to unauthorized people.</span></span> <span data-ttu-id="d3637-109">Exchange Online 보안은 지능형 보안 가치 (Microsoft 365 Enterprise)의 주요 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-109">Exchange Online security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="d3637-110">Exchange online을 처음으로 사용할 경우 [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3637-110">If you are brand new to Exchange Online, see [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).</span></span>

<span data-ttu-id="d3637-111">다음 단계 및 단계에서는 조직에서 Exchange Online의 역할을 구상 하 고, 조직을 Exchange Online으로 온 보 딩 하 고, Exchange online의 사용을 추진 하는 프로세스를 안내 합니다. 최종 사용자에 게 가치를 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-111">The following phases and steps guide you through the process of envisioning the role of Exchange Online in your organization, onboarding your organization to Exchange Online through a series of progressive rollouts, and driving usage of Exchange Online and its value to your end users.</span></span>

>[!Note]
><span data-ttu-id="d3637-112">이러한 배포 지침은 [Microsoft 365 엔터프라이즈 기본 인프라의 2 단계 id](identity-infrastructure.md)를 완료 한 후에만 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-112">These deployment instructions should be followed only after you’ve completed [Phase 2-Identity of the Microsoft 365 Enterprise foundation infrastructure](identity-infrastructure.md).</span></span>
>

## <a name="phase-1-envision-your-exchange-online-deployment"></a><span data-ttu-id="d3637-113">1 단계: Exchange Online 배포 구상</span><span class="sxs-lookup"><span data-stu-id="d3637-113">Phase 1: Envision your Exchange Online deployment</span></span>

<span data-ttu-id="d3637-114">이 단계에서는 Exchange Online 배포를 위한 사용자를 수집 하 고 조직에서 Exchange Online을 사용 하 여 비즈니스 요구 사항을 해결 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-114">In this phase, you gather the people for your Exchange Online deployment and determine how your organization will use Exchange Online to address its business needs.</span></span>

### <a name="step-1-gather-your-exchange-online-deployment-members"></a><span data-ttu-id="d3637-115">1 단계: Exchange Online 배포 구성원 수집</span><span class="sxs-lookup"><span data-stu-id="d3637-115">Step 1: Gather your Exchange Online deployment members</span></span>

<span data-ttu-id="d3637-116">Microsoft 365 Enterprise foundation 인프라의 [2 단계](identity-infrastructure.md) 위에 Exchange Online을 배포 하는 경우에는 입력 및 의견을 위해 적절 한 사용자를 수집 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-116">For a successful deployment of Exchange Online on top of [Phase 2-Identity](identity-infrastructure.md) of the Microsoft 365 Enterprise foundation infrastructure, you need to gather the right people for input and feedback.</span></span> <span data-ttu-id="d3637-117">주요 사용자에 게는 설계자 및 구현자와 같은 IT 직원과 최종 사용자에 대 한 대표가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-117">Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="d3637-118">이러한 세 그룹은 Exchange Online 배포에 비즈니스 요구 사항, 사서함 마이그레이션 및 보안의 기술적 측면, 그리고 일반적인 사용자가 사용 하는 것에 대 한 고려 사항이 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-118">These three groups ensure that your Exchange Online deployment includes considerations that address business needs, technical aspects of mailbox migration and security, and that the result is something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="d3637-119">결과</span><span class="sxs-lookup"><span data-stu-id="d3637-119">Result</span></span>

<span data-ttu-id="d3637-120">조직의 비즈니스, 기술 및 최종 사용자 측면을 대표하는 구성원 목록을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-120">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a><span data-ttu-id="d3637-121">2 단계: Exchange Online 비즈니스 시나리오 확인 및 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="d3637-121">Step 2: Determine and prioritize your Exchange Online business scenarios</span></span>

<span data-ttu-id="d3637-122">Exchange Online은 다양 한 용도로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-122">Exchange Online can be used for different purposes.</span></span> <span data-ttu-id="d3637-123">조직의 개별 수준, 비즈니스 그룹, 부서 또는 개별 작업 및 프로젝트 팀에서 비즈니스 요구 사항에 맞는 용도를 파악 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-123">You need to figure out which purposes map to your business needs on the separate levels of your organization, your business groups, your departments, or individual working and project teams.</span></span> <span data-ttu-id="d3637-124">개별 및 소규모 그룹의 단기 통신 및 일정 요구 사항을 해결 하기 위해 Exchange Online을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-124">You should target Exchange Online to address your individual and small group short-lived communication and scheduling needs.</span></span> 

<span data-ttu-id="d3637-125">Exchange Online의 이점을 확인 하는 한 가지 방법은 사용자, 팀 또는 v 팀이 현재 어떻게 상호 작용 하는지 검토 한 다음, 보다 쉬운 의사 소통, 모임 예약 및 공동 작업 방법을 제공 하는 적절 한 시나리오를 찾는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-125">One way to see the benefits of Exchange Online is to examine how individuals, a team, or v-team interact today, and then find an appropriate scenario that provides easier ways to communicate, schedule meetings, and collaborate.</span></span> <span data-ttu-id="d3637-126">일부 공동 작업 시나리오에서는 [Microsoft 팀](teams-workload.md) 을 선택 하는 것이 더 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-126">Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your collaboration scenarios.</span></span>

#### <a name="result"></a><span data-ttu-id="d3637-127">결과</span><span class="sxs-lookup"><span data-stu-id="d3637-127">Result</span></span>
<span data-ttu-id="d3637-128">조직의 통신, 일정 및 단기 공동 작업에 대 한 요구를 해결 하는 Exchange Online 시나리오 목록</span><span class="sxs-lookup"><span data-stu-id="d3637-128">A list of Exchange Online scenarios that address your organization’s needs for communication, scheduling, and short-lived collaboration.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="d3637-129">2단계: 온보딩</span><span class="sxs-lookup"><span data-stu-id="d3637-129">Phase 2: Onboard</span></span>

<span data-ttu-id="d3637-130">이 단계에서는 Exchange Online 배포의 기술적 측면을 계획 하 고 선택한 사용자 그룹에 롤아웃하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-130">In this phase, you plan for the technical aspects of an Exchange Online deployment and start rolling it out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="d3637-131">필수 구성 요소: ID 및 장치 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="d3637-131">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="d3637-132">Exchange Online 사서함에 대 한 액세스를 보호 하려면 [id 및 장치 액세스 정책](identity-access-policies.md) 및 [권장 Exchange Online 액세스 정책을](secure-email-recommended-policies.md)구성 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-132">To protect access to Exchange Online mailboxes, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended Exchange Online access policies](secure-email-recommended-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="d3637-133">1단계: 기술 계획 완료</span><span class="sxs-lookup"><span data-stu-id="d3637-133">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="d3637-134">기술 계획을 시작하기 전에 FastTrack을 사용할지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-134">Before you begin technical planning, determine whether you want to use FastTrack.</span></span> <span data-ttu-id="d3637-135">조직이 50 개를 초과 하 고 [적합 한 요금제](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365)에 참여 하 고 있으면 계획, 배포 및 서비스 도입을 안내할 *추가 비용 없이* [Microsoft 365 용 fasttrack](https://fasttrack.microsoft.com/microsoft365)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-135">If your organization has over 50 seats and is participating in an [eligible plan](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365), you can use [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365), *available at no additional cost* to guide you through planning, deployment, and service adoption.</span></span> <span data-ttu-id="d3637-136">또는 Microsoft 365 계정으로 로그인한 후 [FastTrack](https://fasttrack.microsoft.com/)에서 사용할 수 있는 FastTrack 온보딩 마법사를 사용하여 직접 이 작업을 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-136">Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Microsoft 365 account.</span></span>

<span data-ttu-id="d3637-137">직접 계획을 하거나 FastTrack과 함께 사용 하는 경우 네트워크 및 조직이 Exchange Online을 사용할 준비가 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-137">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for Exchange Online.</span></span> <span data-ttu-id="d3637-138">조직 네트워크에 연결 된 사용자의 기본 인프라에서 [네트워킹](networking-infrastructure.md) 에 대 한 종료 기준을 충족 하는 것이 특히 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-138">It is especially important that you meet the exit criteria for [networking](networking-infrastructure.md) in your foundation infrastructure for users connected to your organization network.</span></span> <span data-ttu-id="d3637-139">Exchange Online 기반 전자 메일 및 첨부 파일에 대 한 추가 트래픽의 성능을 최대화 하기 위해 인터넷 대역폭, 처리량 및 트래픽 지연을 특별히 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-139">Pay special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for Exchange Online-based email and attachments.</span></span>

<span data-ttu-id="d3637-140">다음 리소스를 사용 하 여 Exchange Online 롤아웃의 기술적 측면을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-140">Use these resources to prepare for the technical aspects of an Exchange Online rollout:</span></span> 

- [<span data-ttu-id="d3637-141">Office 365로 여러 전자 메일 계정을 마이그레이션하는 방법</span><span class="sxs-lookup"><span data-stu-id="d3637-141">Ways to migrate multiple email accounts to Office 365</span></span>](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [<span data-ttu-id="d3637-142">Exchange Online의 공동 작업</span><span class="sxs-lookup"><span data-stu-id="d3637-142">Collaboration in Exchange Online</span></span>](https://docs.microsoft.com/exchange/collaboration-exo/collaboration-exo)
- [<span data-ttu-id="d3637-143">Exchange Online의 받는 사람</span><span class="sxs-lookup"><span data-stu-id="d3637-143">Recipients in Exchange Online</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/recipients-in-exchange-online)

<span data-ttu-id="d3637-144">Exchange Online의 보안을 보다 잘 이해 하려면 다음 리소스를 검토 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d3637-144">For a better understanding of security in Exchange Online, review the following resources:</span></span>

- [<span data-ttu-id="d3637-145">Exchange Online의 사용 권한</span><span class="sxs-lookup"><span data-stu-id="d3637-145">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- [<span data-ttu-id="d3637-146">Exchange Online의 보안 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="d3637-146">Security and compliance for Exchange Online</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance) 
- [<span data-ttu-id="d3637-147">스팸 방지 및 맬웨어 방지 보호</span><span class="sxs-lookup"><span data-stu-id="d3637-147">Anti-spam and anti-malware protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)

<span data-ttu-id="d3637-148">다음으로, 다음 리소스를 사용 하 여 Exchange Online 사서함 관리를 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-148">Next, use these resources to understand Exchange Online mailbox management:</span></span>

- [<span data-ttu-id="d3637-149">Exchange Online에서 사용자 사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="d3637-149">Create user mailboxes in Exchange Online</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/create-user-mailboxes)
- [<span data-ttu-id="d3637-150">사용자 사서함 관리</span><span class="sxs-lookup"><span data-stu-id="d3637-150">Manage user mailboxes</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes) 
- [<span data-ttu-id="d3637-151">메일 그룹 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="d3637-151">Create and manage distribution groups</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)

#### <a name="result"></a><span data-ttu-id="d3637-152">결과</span><span class="sxs-lookup"><span data-stu-id="d3637-152">Result</span></span>

<span data-ttu-id="d3637-153">사서함 마이그레이션, 보안 및 관리를 이해 하 고 조직의 선택한 그룹에 Exchange Online을 롤아웃하기 시작할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-153">You understand mailbox migration, security, and management and are ready to begin rolling out Exchange Online to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="d3637-154">2단계: IT 파일럿 실행</span><span class="sxs-lookup"><span data-stu-id="d3637-154">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="d3637-155">대부분의 중간 규모 및 대규모 조직의 경우 1 단계, 초기 담당자 및 기술 매니아의 관련자와 함께 IT 파일럿을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-155">For most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1, early adopters, and technical enthusiasts.</span></span> <span data-ttu-id="d3637-156">IT 파일럿 중에 수행하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-156">During the IT pilot:</span></span>

- <span data-ttu-id="d3637-157">파일럿 참가자에 게 Microsoft 365 라이선스를 제공 하 고 온-프레미스 사서함을 Exchange Online으로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-157">Give your pilot participants Microsoft 365 licenses and migrate their on-premises mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="d3637-158">파일럿 참가자에 게 Exchange Online 전자 메일, 일정 및 기타 기능을 테스트할 수 있는 일련의 실습을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-158">Give your pilot participants a set of exercises to test Exchange Online email, scheduling, and other capabilities.</span></span>
- <span data-ttu-id="d3637-159">변경 관리 전략을 결정 하 고 조직 전체의 사용자 채택 및 Exchange Online을 구동 하기 위한 자료를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-159">Determine your change management strategy and produce materials to drive organization-wide user adoption of Outlook and Exchange Online.</span></span> 
 
  <span data-ttu-id="d3637-160">변경 관리 자료에는 전자 메일 알림 텍스트, 내부 교육 계획, 복도 포스터 및 프레젠테이션이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-160">Change management materials can include email announcement text, internal training plans, hallway posters, and presentations.</span></span> <span data-ttu-id="d3637-161">이러한 자료에서는 조직에 Exchange Online 및 인식 및 추진 사용량에 대 한 목표를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-161">These materials will inform your organization about Exchange Online and its benefits with the goals of raising awareness and driving usage.</span></span> <span data-ttu-id="d3637-162">몇 가지 아이디어는 [Microsoft 팀에 대 한 변경 관리 전략](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3637-162">See the [change management strategy for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) article for some ideas.</span></span>

- <span data-ttu-id="d3637-163">IT 파일럿 참여자가 자신의 경험을 기반으로 변경 관리 자료를 검토하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-163">Have your IT pilot participants review the change management materials based on their experiences.</span></span> <span data-ttu-id="d3637-164">Outlook 및 Exchange Online의 이점과이를 사용 하 여 통신 및 일정을 세우는 방법에 대 한 모범 사례와 조언을 제공 하는 팁을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-164">They can provide tips on best practices and advice on how to best describe the benefits of Outlook and Exchange Online and how to use it for communication and scheduling.</span></span>

#### <a name="result"></a><span data-ttu-id="d3637-165">결과</span><span class="sxs-lookup"><span data-stu-id="d3637-165">Result</span></span>

<span data-ttu-id="d3637-166">Exchange Online IT 파일럿이 완료 되 고 초기 변경 관리 자료가 개발, 검토 및 구체화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-166">Your Exchange Online IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="d3637-167">3단계: 비즈니스 그룹에 배포</span><span class="sxs-lookup"><span data-stu-id="d3637-167">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="d3637-168">IT 파일럿을 완료 한 후 조직의 비즈니스 그룹이 나 부서에 Exchange Online을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-168">After completing your IT pilot, roll out Exchange Online to a business group or department in your organization.</span></span> <span data-ttu-id="d3637-169">조직에서 Exchange Server와 같은 온-프레미스 전자 메일 서비스를 사용 하는 경우이 배포는 사서함 마이그레이션으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-169">If your organization is using an on-premises email service such as Exchange Server, this rollout consists of mailbox migration.</span></span> <span data-ttu-id="d3637-170">다음은 배포에 포함된 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-170">This rollout should include:</span></span>

- <span data-ttu-id="d3637-171">비즈니스 그룹 내에서 Exchange Online에 대 한 주요 비즈니스 시나리오 식별</span><span class="sxs-lookup"><span data-stu-id="d3637-171">Identification of key business scenarios for Exchange Online within the business group.</span></span>
- <span data-ttu-id="d3637-172">부서 및 작업 또는 프로젝트 팀에 대 한 Exchange Online 사용에 대 한 예상 및 일정을 사용자에 게 알리는 알림 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-172">Announcement activities to inform users of the expectations and timelines for Exchange Online usage for departments and work or project teams.</span></span>
- <span data-ttu-id="d3637-173">비즈니스 그룹 구성원의 온-프레미스 사서함을 Exchange Online으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="d3637-173">Migration of on-premises mailboxes of your business group members to Exchange Online.</span></span>
- <span data-ttu-id="d3637-174">Outlook에 대 한 [사용자 교육](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) 을 제공 하거나 outlook을 소개 하 고 리소스를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-174">Delivering [user training](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) on Outlook or links to resources to introduce Outlook and how to use it.</span></span>
- <span data-ttu-id="d3637-175">비즈니스 그룹의 사용자로부터 의견을 수집하고 문제에 대해 조치를 취하기 위한 피드백 메커니즘(예: 비즈니스 그룹의 모든 사용자를 포함하는 중앙 Microsoft Teams 팀)</span><span class="sxs-lookup"><span data-stu-id="d3637-175">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>

<span data-ttu-id="d3637-176">롤아웃하는 동안 조직 차원의 롤아웃을 준비하려면 변경 관리 자료를 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-176">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="d3637-177">결과</span><span class="sxs-lookup"><span data-stu-id="d3637-177">Result</span></span>

<span data-ttu-id="d3637-178">Outlook 및 Exchange Online과 함께 비즈니스 그룹이 실행 되 고 변경 관리 자료가 테스트 및 구체화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-178">A business group is up and running with Outlook and Exchange Online and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="d3637-179">3단계: 가치 창출</span><span class="sxs-lookup"><span data-stu-id="d3637-179">Phase 3: Drive value</span></span>

<span data-ttu-id="d3637-180">이 단계에서는 Exchange Online의 롤아웃을 완료 하 고 사용자가 자신의 이점을 실현할 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-180">In this phase, you complete the rollout of Exchange Online and support your users to help them realize its benefits.</span></span>

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a><span data-ttu-id="d3637-181">1 단계: 조직의 나머지 구성원에 게 Exchange Online 배포</span><span class="sxs-lookup"><span data-stu-id="d3637-181">Step 1: Roll out Exchange Online to the rest of your organization</span></span>

<span data-ttu-id="d3637-182">나머지 조직 구성원에게 롤아웃하는 과정에는 다음이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-182">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="d3637-183">개별 비즈니스 그룹 내에서 Exchange Online에 대 한 주요 비즈니스 시나리오 식별</span><span class="sxs-lookup"><span data-stu-id="d3637-183">Identification of key business scenarios for Exchange Online within separate business groups.</span></span>
- <span data-ttu-id="d3637-184">구체화 된 변경 관리 자료를 사용 하 여 Exchange Online 사용에 대 한 예상 및 일정을 조직에 알리는 알림 활동</span><span class="sxs-lookup"><span data-stu-id="d3637-184">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for Exchange Online usage.</span></span>
- <span data-ttu-id="d3637-185">조직의 나머지 부분에 대 한 사서함을 Exchange Online으로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-185">Migration of the mailboxes for the rest of your organization to Exchange Online.</span></span>
- <span data-ttu-id="d3637-186">Outlook에 대 한 [사용자 교육](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) 을 제공 하거나 outlook을 소개 하 고 사용 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-186">Delivering [user training](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) on Outlook or provide links to resources to introduce Outlook and how to use it.</span></span>
- <span data-ttu-id="d3637-p112">조직의 사용자로부터 의견 및 문제를 수집하기 위한 피드백 메커니즘(예: 모든 사용자를 포함하는 중앙 팀). 조직의 사용자가 2500명 미만인 경우 Teams의 공개 채널을 사용하고, 2500명 이상인 경우 Yammer의 공용 그룹 사용</span><span class="sxs-lookup"><span data-stu-id="d3637-p112">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="d3637-190">결과</span><span class="sxs-lookup"><span data-stu-id="d3637-190">Result</span></span>

<span data-ttu-id="d3637-191">조직이 가동 중 이며, 사용자에 게 알림 및 교육을 제공 하 고 Exchange Online을 사용할 수 있도록 하는 변경 관리 전략이 마련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-191">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use Exchange Online.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="d3637-192">2단계: 사용 현황 측정, 만족도 관리 및 도입 촉진</span><span class="sxs-lookup"><span data-stu-id="d3637-192">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="d3637-193">전체 조직에 Exchange Online을 연결한 후에는 변경 관리 전략을 계속 사용 하 여 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-193">After rolling out Exchange Online to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="d3637-194">리더십이 Exchange Online을 개인 및 단기 통신 및 일정 예약에 대 한 기본 도구로 승격 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-194">Have your leadership promote Exchange Online as the primary tool for individual and short-lived communication and scheduling.</span></span>
- <span data-ttu-id="d3637-195">개인이 비즈니스 그룹, 부서, 업무 및 프로젝트 팀의 커뮤니케이션, 일정 및 공동 작업에 사용할 수 있도록 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-195">Encourage individuals to use it for business group, departmental, work, and project team communications, calendaring, and collaboration.</span></span>

<span data-ttu-id="d3637-196">다음은 몇 가지 추천 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-196">Here are some suggested activities:</span></span>

- <span data-ttu-id="d3637-197">[Office 365의 성공 요인](https://aka.ms/successfactors)을 통해 클라우드 서비스 도입에 대한 일반적인 모범 사례를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-197">See [Success factors for Office 365](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="d3637-p113">[Office 365 활동 보고서](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)를 통해 조직 전체의 Office 365 서비스 사용을 이해합니다. 조직의 Office 365 전역 관리자에게 활동 보고서에 액세스할 수 있도록 사용자 계정에 보고서 읽기 권한자 권한을 부여해 달라고 요청합니다(Office 365 전역 관리자가 아닌 경우).</span><span class="sxs-lookup"><span data-stu-id="d3637-p113">See [Office 365 activity reports](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="d3637-200">Exchange Online의 환경에 대 한 사용자 의견 (중앙 팀 팀 또는 Yammer의 공용 채널)을 모니터링 하 여 개인의 문제 및 의견에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-200">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with Exchange Online.</span></span> <span data-ttu-id="d3637-201">사용자의 불편을 방지하고 배포에 대한 지원을 보여 주기 위해 질문과 문제를 가능한 한 신속하게 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-201">Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="d3637-202">각 비즈니스 그룹에서 champions을 식별 및 nurture Outlook을 사용 하 여 해당 모범 사례를 강조 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-202">Identify and nurture champions in each business group and highlight their best practices using Outlook.</span></span> <span data-ttu-id="d3637-203">조직에 성공을 반영하여 프로젝트 성공 및 도입을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-203">Reflect their successes out to the organization to show project success and adoption.</span></span> <span data-ttu-id="d3637-204">비즈니스 그룹 내에서 기술 리더가 인증을 받은 경우에는 리더와 피어에 비해 강한 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-204">Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="d3637-205">결과</span><span class="sxs-lookup"><span data-stu-id="d3637-205">Result</span></span>

<span data-ttu-id="d3637-206">조직에서는 Exchange Online과 Outlook을 기본 개인 및 소규모 그룹의 단기 통신 및 일정 도구로 채택 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d3637-206">Your organization has adopted Exchange Online and Outlook as its primary individual and small group short-lived communication and scheduling tool.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="d3637-207">Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법</span><span class="sxs-lookup"><span data-stu-id="d3637-207">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="d3637-208">Microsoft 내부를 살펴보고 exchange online으로 마이그레이션 및 Exchange Online Protection을 사용 하 여 사이버 공격 으로부터 보호 하는 방법을 알아보려면 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3637-208">To peek inside Microsoft and learn how we migrated to Exchange Online and are using Exchange Online Protection to protect against cyber attacks, see:</span></span>

- [<span data-ttu-id="d3637-209">Microsoft에서 150,000개의 사서함을 Exchange Online으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="d3637-209">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="d3637-210">Microsoft는 위협 인텔리전스를 사용하여 위협 방지, 감지 및 대응</span><span class="sxs-lookup"><span data-stu-id="d3637-210">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="d3637-211">Microsoft는 Office 365를 사용하여 피싱 시도 저지</span><span class="sxs-lookup"><span data-stu-id="d3637-211">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a><span data-ttu-id="d3637-212">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d3637-212">Next steps</span></span>

<span data-ttu-id="d3637-213">Exchange Online의 지속적인 유지 관리에 대 한 다음 리소스를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3637-213">See these resources for the ongoing maintenance of Exchange Online:</span></span>

- [<span data-ttu-id="d3637-214">Exchange Online의 exchange 관리 센터</span><span class="sxs-lookup"><span data-stu-id="d3637-214">Exchange admin center in Exchange Online</span></span>](https://docs.microsoft.com/exchange/exchange-admin-center) 
- [<span data-ttu-id="d3637-215">Exchange Online의 모니터링, 보고 및 메시지 추적</span><span class="sxs-lookup"><span data-stu-id="d3637-215">Monitoring, reporting, and message tracing in Exchange Online</span></span>](https://docs.microsoft.com/exchange/monitoring/monitoring)
- [<span data-ttu-id="d3637-216">Exchange Online에서 전자 메일 백업</span><span class="sxs-lookup"><span data-stu-id="d3637-216">Backing up email in Exchange Online</span></span>](https://docs.microsoft.com/exchange/back-up-email) 
