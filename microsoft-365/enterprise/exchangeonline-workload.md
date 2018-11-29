---
title: Exchange Online Microsoft 365 Enterprise에 대 한 배포
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/28/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Strat_O365_Enterprise
description: 단계에 대 한 계획을 제공 하 고 조직 전체에서 Microsoft 365 기업에서 Exchange Online의 값을 제어 하는 프로세스를 통해 수행 합니다.
ms.openlocfilehash: 36b24290acd4467400eab86b4c2760ccad65deab
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870341"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a><span data-ttu-id="72f88-103">Exchange Online Microsoft 365 Enterprise에 대 한 배포</span><span class="sxs-lookup"><span data-stu-id="72f88-103">Deploy Exchange Online for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="72f88-p101">Exchange Online은 전자 메일에 대 한 기본 클라우드 서비스 및이 통해 일정 실시간 채팅 필요 하지 않은 또는 문서 저장소에 집중 하는 방법으로 공동 작업 사용자에 게 합니다. Exchange Online 개별 및 작은 그룹 단기 통신 및 일정 방법 이며 Microsoft 365 Enterprise의 더욱 원활 값에 대 한 내장의 핵심 요소입니다. Exchange Online 더 수행 하 고 잘 알려진 Outlook 응용 프로그램의 없이 이동 중일 장치에 관계 없이 보다 효과적으로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-p101">Exchange Online is your primary cloud service for email and calendaring that helps your users collaborate in ways that do not require real-time chatting or centralized document storage. Exchange Online is how you do individual and small group short-lived communication and scheduling and is a key element of the Built for Teamwork value of Microsoft 365 Enterprise. Exchange Online lets you accomplish more and work more effectively with the well-known Outlook application, no matter what device you’re on.</span></span>

<span data-ttu-id="72f88-p102">Exchange Online도 고급 사서함을 보호 하기 위해 맬웨어 방지 및 스팸 방지 필터링을 비롯 하 여 보안 기능 및 사용자가 실수로 중요 한 정보를 보내는 경우 권한이 없는 사람에 게 하지 못하도록 하는 데이터 손실 방지 기능 합니다. Exchange Online 보안은 Microsoft 365 Enterprise의 지능형 보안 값의 핵심 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-p102">Exchange Online also has advanced security capabilities including anti-malware and anti-spam filtering to protect mailboxes and data loss prevention capabilities that prevent users from mistakenly sending sensitive information to unauthorized people. Exchange Online security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="72f88-109">Exchange Online으로 새로운 인 경우 [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="72f88-109">If you are brand new to Exchange Online, see [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).</span></span>

<span data-ttu-id="72f88-110">다음 단계를 안내 하 envisioning 온 보 딩 조직에서 Exchange online 역할 점진적 롤아웃 시리즈를 통해 Exchange online 조직 및 Exchange Online의 사용을 제어 하는 프로세스 및 해당 최종 사용자에 게 값입니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-110">The following phases and steps guide you through the process of envisioning the role of Exchange Online in your organization, onboarding your organization to Exchange Online through a series of progressive rollouts, and driving usage of Exchange Online and its value to your end users.</span></span>

>[!Note]
><span data-ttu-id="72f88-111">Microsoft 365 enterprise [foundation 인프라](deploy-foundation-infrastructure.md) 를 완료 한 후에이 배포 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-111">These deployment instructions should be followed only after you’ve completed your [foundation infrastructure](deploy-foundation-infrastructure.md) for Microsoft 365 Enterprise.</span></span>
>

## <a name="phase-1-envision"></a><span data-ttu-id="72f88-112">1단계: 구상</span><span class="sxs-lookup"><span data-stu-id="72f88-112">Phase 1: Envision</span></span>

<span data-ttu-id="72f88-113">이 단계에서 Exchange Online 배포에 대 한 사람을 수집 및 어떻게 조직에서 사용할 Exchange Online의 비즈니스 요구를 해결 하는 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-113">In this phase, you gather the people for your Exchange Online deployment and determine how your organization will use Exchange Online to address its business needs.</span></span>

### <a name="step-1-gather-your-exchange-online-deployment-members"></a><span data-ttu-id="72f88-114">1 단계: Exchange Online 배포 구성원에 수집</span><span class="sxs-lookup"><span data-stu-id="72f88-114">Step 1: Gather your Exchange Online deployment members</span></span>

<span data-ttu-id="72f88-p103">Microsoft 365 [foundation 인프라](deploy-foundation-infrastructure.md)와 Exchange Online의 성공적인 배포를 입력 하 고 피드백에 대 한 권한 있는 사용자를 가져올 해야 합니다. 주요 작업 자가 비즈니스 의사 결정권자, IT 담당자가 설계자 및 구현, 최종 사용자에 대 한을 대표 등을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-p103">For a successful deployment of Exchange Online on top of the Microsoft 365 [foundation infrastructure](deploy-foundation-infrastructure.md), you need to get the right people for input and feedback. Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="72f88-117">이러한 세 그룹 Exchange Online 배포 비즈니스 요구 사항, 사서함 마이그레이션 및 보안을의 기술적 측면 및 일반적인 사용자가 사용 되어 있음을 결과 수를 처리 하는 고려 사항을 포함 되어있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-117">These three groups ensure that your Exchange Online deployment includes considerations that address business needs, technical aspects of mailbox migration and security, and that the result will be something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="72f88-118">결과</span><span class="sxs-lookup"><span data-stu-id="72f88-118">Result</span></span>

<span data-ttu-id="72f88-119">조직의 비즈니스, 기술 및 최종 사용자 측면을 대표하는 구성원 목록을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-119">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a><span data-ttu-id="72f88-120">2 단계: 확인 하 고 Exchange Online 비즈니스 시나리오를 우선순위</span><span class="sxs-lookup"><span data-stu-id="72f88-120">Step 2: Determine and prioritize your Exchange Online business scenarios</span></span>

<span data-ttu-id="72f88-p104">Exchange Online을 다른 용도로 사용할 수 있습니다. 어떤 목적으로 별도 수준의 조직, 비즈니스 그룹, 부서 또는 개별 작업 시간 및 프로젝트 팀에 비즈니스 요구 사항에 맞게 파악 해야 합니다. Exchange Online에 개별 및 작은 그룹 단기 통신 및 예약 요구를 해결 하는 대상 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-p104">Exchange Online can be used for different purposes. You need to figure out which purposes map to your business needs on the separate levels of your organization, your business groups, your departments, or individual working and project teams. You should target Exchange Online to address your individual and small group short-lived communication and scheduling needs.</span></span> 

<span data-ttu-id="72f88-p105">Exchange Online의 혜택을 참조 하는 한 가지 방법은 개인, 팀 또는 v 팀 오늘날 상호작용 하 고 찾기를 통신, 모임 예약 및 공동 작업을 편리 하 게 제공 하는 적절 한 시나리오를 어떻게를 검사 하는 합니다. [Microsoft 팀의](teams-workload.md) 공동 작업 시나리오 중 일부에 대 한 보다 적합할 수 있다는 것을 염두에 두십시오.</span><span class="sxs-lookup"><span data-stu-id="72f88-p105">One way to see the benefits of Exchange Online is to examine how individuals, a team, or v-team interact today, and then find an appropriate scenario that provides easier ways to communicate, schedule meetings, and collaborate. Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your collaboration scenarios.</span></span>

<span data-ttu-id="72f88-126">Exchange Online은 다음과 같은 Microsoft 365 Enterprise에 대한 전략적 비즈니스 시나리오를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-126">Exchange Online enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="72f88-127">실시간으로 또는 원하는 시간에 문서 공동 작업을 수행하여 공동 작성 프로세스 간소화</span><span class="sxs-lookup"><span data-stu-id="72f88-127">Collaborate on documents in real time or on your own time to simplify the cocreation process</span></span>
- <span data-ttu-id="72f88-128">비즈니스 목표에 맞게 프로젝트, 작업 및 기한 관리</span><span class="sxs-lookup"><span data-stu-id="72f88-128">Manage projects, tasks, and deadlines to meet your business objectives</span></span>
- <span data-ttu-id="72f88-129">작업 습관을 이해하여 미치는 영향 개선</span><span class="sxs-lookup"><span data-stu-id="72f88-129">Understand your work habits to improve your influence and impact</span></span>
- <span data-ttu-id="72f88-130">팀과 소통하여 정보를 제공하고, 정보 제공을 요청하고, 협력 및 의견 합의 도달</span><span class="sxs-lookup"><span data-stu-id="72f88-130">Communicate with your team to stay informed, solicit input, and build cohesion and consensus</span></span>
- <span data-ttu-id="72f88-131">조직 내부 및 외부에서 파일을 저장 및 공유하여 조직 경계를 넘나들며 원활하게 작업 가능</span><span class="sxs-lookup"><span data-stu-id="72f88-131">Store and share files inside and outside your organization to work seamlessly across organizational boundaries</span></span>
- <span data-ttu-id="72f88-132">유연한 작업 스타일을 유지하면서 어떤 장치를 사용하든 장소나 시간의 구애를 받지 않고 안전하게 더 많은 작업 처리</span><span class="sxs-lookup"><span data-stu-id="72f88-132">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="72f88-133">사용자의 정보 보호 및 데이터 손실 위험 최소화</span><span class="sxs-lookup"><span data-stu-id="72f88-133">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="72f88-134">검색 하 고 외부 위협 으로부터 보호</span><span class="sxs-lookup"><span data-stu-id="72f88-134">Detect and protect against external threats</span></span> 
- <span data-ttu-id="72f88-135">모니터링, 보고 및 조직의 보안을 제공 하려면 신속 하 게 대처 하는 작업을 분석</span><span class="sxs-lookup"><span data-stu-id="72f88-135">Monitor, report and analyze activity to react promptly to provide organizational security</span></span>
- <span data-ttu-id="72f88-136">개인 정보 보호 및 규정 준수로 조직이 GDPR(일반 데이터 보호 규정)을 준수하도록 지원</span><span class="sxs-lookup"><span data-stu-id="72f88-136">Support your organization with enhanced privacy and compliance to meet the General Data Protection Regulation (GDPR)</span></span>

<span data-ttu-id="72f88-137">자세한 내용은 [Microsoft 365를 사용한 디지털 변환](http://transform.microsoft.com)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="72f88-137">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

#### <a name="result"></a><span data-ttu-id="72f88-138">결과</span><span class="sxs-lookup"><span data-stu-id="72f88-138">Result</span></span>
<span data-ttu-id="72f88-139">통신, 일정 및 단기 공동 작업에 대 한 조직의 요구를 처리 하는 Exchange Online 시나리오 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-139">A list of Exchange Online scenarios that address your organization’s needs for communication, scheduling, and short-lived collaboration.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="72f88-140">2단계: 온보딩</span><span class="sxs-lookup"><span data-stu-id="72f88-140">Phase 2: Onboard</span></span>

<span data-ttu-id="72f88-141">이 단계는 Exchange Online 배포의 기술적 측면에 대 한 계획 하 고 사용자의 선택 된 그룹 전체에 배포를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-141">In this phase, you plan for the technical aspects of an Exchange Online deployment and start rolling it out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="72f88-142">필수 구성 요소: Id 및 장치 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="72f88-142">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="72f88-143">Exchange Online 사서함에 대 한 액세스를 보호 하려면 웹 [id 및 장치에 대 한 액세스 정책](identity-access-policies.md) 및 [Exchange Online 액세스 정책 권장](secure-email-recommended-policies.md)구성 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-143">To protect access to Exchange Online mailboxes, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended Exchange Online access policies](secure-email-recommended-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="72f88-144">1단계: 기술 계획 완료</span><span class="sxs-lookup"><span data-stu-id="72f88-144">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="72f88-p106">기술 계획을 시작 하기 전에 FastTrack을 사용 하 여 할지 여부를 결정 합니다. 조직 50 개 이상의 시트에 하는 [가능한 계획](https://technet.microsoft.com/library/dn783224.aspx)에 참여 하는 경우에 [Microsoft 365 FastTrack](https://fasttrack.microsoft.com/microsoft365), 계획, 배포 및 서비스 채택 안내 하는 추가 비용 없이 사용할 수 있는 사용할 수 있습니다. 또는 Office 365 계정을 사용 하 여 로그인 한 후 [FastTrack](https://fasttrack.microsoft.com/) 에서 사용할 수 있는 FastTrack 온 보 딩 마법사를 사용 하 여 직접이 작업을 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-p106">Before you begin technical planning, determine whether you want to use FastTrack. If your organization has over 50 seats and is participating in an [eligible plan](https://technet.microsoft.com/library/dn783224.aspx), you can use [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365), available at no additional cost to guide you through planning, deployment, and service adoption. Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Office 365 account.</span></span>

<span data-ttu-id="72f88-p107">FastTrack와 함께에서 또는 직접 계획을 수행 하는 경우 네트워크와 조직의 Exchange Online에 대 한 준비가 되었는지 여부를 확인할 필요가 있습니다. 것이 특히 중요 인터넷 대역폭, 처리량 및 Exchange에 대 한 추가 트래픽에 대 한 성능을 최대화 하기 위해 트래픽 지연에 특히 주의 하 여 foundation 인프라에서 네트워킹에 대 한 종료 기준 맞는지 온라인 기반 전자 메일 및 첨부 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-p107">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for Exchange Online. It is especially important that you meet the exit criteria for networking in your foundation infrastructure, with special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for Exchange Online-based email and attachments.</span></span>

<span data-ttu-id="72f88-150">이러한 리소스를 사용 하 여는 Exchange Online 배포의 기술적 측면에 대 한 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-150">Use these resources to prepare for the technical aspects of an Exchange Online rollout:</span></span> 

- [<span data-ttu-id="72f88-151">Office 365로 여러 전자 메일 계정을 마이그레이션하는 방법</span><span class="sxs-lookup"><span data-stu-id="72f88-151">Ways to migrate multiple email accounts to Office 365</span></span>](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)
- <span data-ttu-id="72f88-152">[Office 365 메일 마이그레이션 관리자](https://portal.office.com/onboarding/mailsetupadvisor#/) (로그인 해야 Office 365 구독)</span><span class="sxs-lookup"><span data-stu-id="72f88-152">[Office 365 mail migration advisor](https://portal.office.com/onboarding/mailsetupadvisor#/) (must be signed in to your Office 365 subscription)</span></span>
- <span data-ttu-id="72f88-153">[Exchange Online의 공동 작업](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="72f88-153">[Collaboration in Exchange Online](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)</span></span>
- <span data-ttu-id="72f88-154">[Exchange Online의 받는 사람](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="72f88-154">[Recipients in Exchange Online](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)</span></span>

<span data-ttu-id="72f88-155">제대로 이해 Exchange Online의 보안을 다음 리소스를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-155">For a better understanding of security in Exchange Online, review the following resources:</span></span>

- <span data-ttu-id="72f88-156">[Exchange Online의 사용 권한](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="72f88-156">[Permissions in Exchange Online](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx)</span></span> 
- <span data-ttu-id="72f88-157">[보안 및 Exchange Online에 대 한 규정 준수](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="72f88-157">[Security and compliance for Exchange Online](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx)</span></span> 
- <span data-ttu-id="72f88-158">[스팸 방지 및 맬웨어 방지 보호](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="72f88-158">[Anti-spam and anti-malware protection](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)</span></span>

<span data-ttu-id="72f88-159">다음으로, 이러한 리소스를 사용 하 여 Exchange Online 사서함 관리를 이해 하려면:</span><span class="sxs-lookup"><span data-stu-id="72f88-159">Next, use these resources to understand Exchange Online mailbox management:</span></span>

- <span data-ttu-id="72f88-160">[Exchange Online에서 사용자 사서함 만들기](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="72f88-160">[Create user mailboxes in Exchange Online](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)</span></span>
- <span data-ttu-id="72f88-161">[사용자 사서함 관리](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="72f88-161">[Manage user mailboxes](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx)</span></span> 
- [<span data-ttu-id="72f88-162">메일 그룹 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="72f88-162">Create and manage distribution groups</span></span>](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)

#### <a name="result"></a><span data-ttu-id="72f88-163">결과</span><span class="sxs-lookup"><span data-stu-id="72f88-163">Result</span></span>

<span data-ttu-id="72f88-164">프로젝트 관리자는 사서함 마이그레이션, 보안 및 관리를 이해 하 고이 정보를 Exchange Online 조직에서 선택한 그룹에 제공 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-164">You understand mailbox migration, security, and management and are ready to begin rolling out Exchange Online to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="72f88-165">2단계: IT 파일럿 실행</span><span class="sxs-lookup"><span data-stu-id="72f88-165">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="72f88-p108">대부분의 중간 규모 및 대규모 조직에서는 1단계의 이해 관계자, 얼리 어답터 및 기술 전문가와 함께 IT 파일럿을 실행해야 합니다. IT 파일럿 중에 수행하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-p108">In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1 and early adopters and technical enthusiasts. During the IT pilot:</span></span>

- <span data-ttu-id="72f88-168">IT 파일럿 참가자에 게는 연습을 할 수는 Exchange Online 비즈니스 시나리오를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-168">Choose an Exchange Online business scenario in which your IT pilot participants can practice.</span></span>
- <span data-ttu-id="72f88-169">파일럿 참가자에 게 Office 365 라이선스 부여 하 고 Exchange Online으로 온-프레미스 사서함을 마이그레이션하십시오.</span><span class="sxs-lookup"><span data-stu-id="72f88-169">Give your pilot participants Office 365 licenses and migrate their on-premises mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="72f88-170">Exchange Online 전자 메일, 일정 및 기타 기능을 테스트 하는 연습 집합이 파일럿 참가자에 게 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-170">Give your pilot participants a set of exercises to test Exchange Online email, scheduling, and other capabilities.</span></span>
- <span data-ttu-id="72f88-p109">변경 관리 전략을 결정 하 고 Exchange Online의 드라이브 조직 전체의 사용자 채택 하는 자료를 생성 합니다. 변경 관리 자료 (영문) 전자 메일 알림 텍스트, 내부 교육 계획 준비, 복도 포스터 및 프레젠테이션에 포함 될 수 있습니다. 이러한 자료는 Exchange Online 및 발생 인식과 구동 사용의 목표와 그 이점에 대 한 조직을 게 알립니다. 일부 아이디어를 그릴 수에 대 한 [Microsoft 팀에 대 한 관리 전략을 변경](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) 하는 문서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="72f88-p109">Determine your change management strategy and produce materials to drive organization-wide user adoption of Exchange Online. Change management materials can include email announcement text, internal training plans, hallway posters, and presentations. These materials will inform your organization about Exchange Online and its benefits with the goals of raising awareness and driving usage. See the [change management strategy for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) article for some ideas.</span></span>
- <span data-ttu-id="72f88-p110">해당 환경에 따라 변경 관리 자료를 검토 하 여 IT 파일럿 참가자가입니다. 모범 사례에 대 한 팁 및 조언 가장 Exchange Online의 이점에 설명 하는 방법 및 통신 및 일정을 사용 하는 방법에 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-p110">Have your IT pilot participants review the change management materials based on their experiences. They can provide tips on best practices and advice on how to best describe the benefits of Exchange Online and how to use it for communication and scheduling.</span></span>

#### <a name="result"></a><span data-ttu-id="72f88-177">결과</span><span class="sxs-lookup"><span data-stu-id="72f88-177">Result</span></span>

<span data-ttu-id="72f88-178">Exchange Online IT 시험 완료 되 고 초기 변경 관리 자료 된 개발, 검토 하 고, 있고 미세 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-178">Your Exchange Online IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="72f88-179">3단계: 비즈니스 그룹에 롤아웃</span><span class="sxs-lookup"><span data-stu-id="72f88-179">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="72f88-p111">IT 시험을 완료 한 후 비즈니스 그룹 또는 조직에서 부서를 Exchange Online 아웃 롤 합니다. 예: Exchange 서버는 온-프레미스 전자 메일 서비스를 사용 하는 경우이 롤아웃 사서함 마이그레이션 구성 됩니다. 이 배포는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-p111">After completing your IT pilot, roll out Exchange Online to a business group or department in your organization. If your organization is using an on-premises email service such as Exchange Server, this rollout consists of mailbox migration. This rollout should include:</span></span>

- <span data-ttu-id="72f88-183">비즈니스 그룹 내에서 Exchange Online에 대 한 주요 비즈니스 시나리오의 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-183">Identification of key business scenarios for Exchange Online within the business group.</span></span>
- <span data-ttu-id="72f88-184">알림 활동을 기대 및 부서 및 회사 또는 프로젝트 팀에 대 한 Exchange Online 사용 현황에 대 한 일정의 사용자에 게 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-184">Announcement activities to inform users of the expectations and timelines for Exchange Online usage for departments and work or project teams.</span></span>
- <span data-ttu-id="72f88-185">Exchange Online으로 비즈니스 그룹 구성원의 온-프레미스 사서함의 마이그레이션 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-185">Migration of on-premises mailboxes of your business group members to Exchange Online.</span></span>
- <span data-ttu-id="72f88-186">Exchange Online 및 사용 하는 방법을 소개 하는 리소스를 Exchange Online 또는 링크에 대 한 사용자 교육을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-186">Delivering user training on Exchange Online or links to resources to introduce Exchange Online and how to use it.</span></span>
- <span data-ttu-id="72f88-187">비즈니스 그룹의 사용자로부터 의견을 수집하고 문제에 대해 조치를 취하기 위한 피드백 메커니즘(예: 비즈니스 그룹의 모든 사용자를 포함하는 중앙 Microsoft Teams 팀)</span><span class="sxs-lookup"><span data-stu-id="72f88-187">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>

<span data-ttu-id="72f88-188">롤아웃하는 동안 조직 차원의 롤아웃을 준비하려면 변경 관리 자료를 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-188">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="72f88-189">결과</span><span class="sxs-lookup"><span data-stu-id="72f88-189">Result</span></span>

<span data-ttu-id="72f88-190">비즈니스 그룹 올라갑니다 및 Exchange Online과 함께 실행 하 고 변경 관리 자료를 테스트 및 미세 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-190">A business group is up and running with Exchange Online and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="72f88-191">3단계: 가치 창출</span><span class="sxs-lookup"><span data-stu-id="72f88-191">Phase 3: Drive value</span></span>

<span data-ttu-id="72f88-192">이 단계에서 Exchange Online의 배포를 완료 하 고 그 혜택을 실현 하기 위해 사용자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-192">In this phase, you complete the rollout of Exchange Online and support your users to help them realize its benefits.</span></span>

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a><span data-ttu-id="72f88-193">1 단계: 롤아웃을 Exchange Online 조직의 나머지 부분에</span><span class="sxs-lookup"><span data-stu-id="72f88-193">Step 1: Roll out Exchange Online to the rest of your organization</span></span>

<span data-ttu-id="72f88-194">나머지 조직 구성원에게 롤아웃하는 과정에는 다음이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-194">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="72f88-195">별도 비즈니스 그룹 내에서 Exchange Online에 대 한 주요 비즈니스 시나리오의 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-195">Identification of key business scenarios for Exchange Online within separate business groups.</span></span>
- <span data-ttu-id="72f88-196">기대의 조직을 알리기 위해 알림 활동에 대 한 구체화 된 변경 관리 재료 및 Exchange Online 사용 현황에 대 한 시간 표시 막대의 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-196">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for Exchange Online usage.</span></span>
- <span data-ttu-id="72f88-197">Exchange online 조직의 나머지 부분에 대 한 사서함의 마이그레이션 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-197">Migration of the mailboxes for the rest of your organization to Exchange Online.</span></span>
- <span data-ttu-id="72f88-198">사용자 교육 제공 (영문) Exchange Online 또는 Exchange Online 및 사용 하는 방법을 소개 하는 리소스에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-198">Delivering user training on Exchange Online or provide links to resources to introduce Exchange Online and how to use it.</span></span>
- <span data-ttu-id="72f88-p112">조직의 사용자로부터 의견 및 문제를 수집하기 위한 피드백 메커니즘(예: 모든 사용자를 포함하는 중앙 팀). 조직의 사용자가 2500명 미만인 경우 Teams의 공개 채널을 사용하고, 2500명 이상인 경우 Yammer의 공용 그룹 사용</span><span class="sxs-lookup"><span data-stu-id="72f88-p112">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="72f88-202">결과</span><span class="sxs-lookup"><span data-stu-id="72f88-202">Result</span></span>

<span data-ttu-id="72f88-203">조직을 이며 실행 하 고 변경 관리 전략 전체에 게 알리기, 교육, 및 Exchange Online을 사용 하 여 사용자를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-203">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use Exchange Online.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="72f88-204">2단계: 사용 현황 측정, 만족도 관리 및 도입 촉진</span><span class="sxs-lookup"><span data-stu-id="72f88-204">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="72f88-205">전체 조직에 Exchange Online 아웃 롤링을 한 후에 변경 관리 전략을 활용 하는 계속 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-205">After rolling out Exchange Online to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="72f88-206">개별와 짧은 통신을 위한 기본 도구로 Exchange Online 승격 하 여 리더 있고 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-206">Have your leadership promote Exchange Online as the primary tool for individual and short-lived communication and scheduling.</span></span>
- <span data-ttu-id="72f88-207">부서, 작업, 비즈니스 그룹에 대해 사용 하 여 개인을 촉진 하 고 프로젝트 팀 통신, 일정, 및 공동 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-207">Encourage individuals to use it for business group, departmental, work, and project team communications, calendaring, and collaboration.</span></span>

<span data-ttu-id="72f88-208">다음은 몇 가지 추천 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-208">Here are some suggested activities:</span></span>

- <span data-ttu-id="72f88-209">[Office 365 도입 지침](https://aka.ms/successfactors)을 통해 클라우드 서비스 도입에 대한 일반적인 모범 사례를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-209">See [Office 365 adoption guidance](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="72f88-p113">[Office 365 활동 보고서](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)를 통해 조직 전체의 Office 365 서비스 사용을 이해합니다. 조직의 Office 365 전역 관리자에게 활동 보고서에 액세스할 수 있도록 사용자 계정에 보고서 읽기 권한자 권한을 부여해 달라고 요청합니다(Office 365 전역 관리자가 아닌 경우).</span><span class="sxs-lookup"><span data-stu-id="72f88-p113">See [Office 365 activity reports](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="72f88-p114">문제 및 Exchange Online과 경험 하는 방법에 대 한 개인의 피드백에 대 한 사용자 의견 위치 (팀이 팀 또는 Yammer를 중앙에서 공용 채널)를 모니터링 합니다. 당황한 개인을 방지 하 고 시연 롤아웃에 대 한 지원을를 최대한 신속 하 게 질문 및 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-p114">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with Exchange Online. Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="72f88-p115">식별 하 고 각 비즈니스 그룹에서 챔피언 촉진 시키는 자신의 성과 및 Exchange Online을 사용 하 여 최상의 방법을 중점적으로 설명 합니다. 프로젝트 성공 및 채택을 표시 하는 조직에 아웃 성공 사례를 반영 합니다. 비즈니스 그룹 내에서 기술 리더의 보증에는 리더 및 동료를 통해는 강력한 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-p115">Identify and nurture champions in each business group and highlight their accomplishments and best practices using Exchange Online. Reflect their successes out to the organization to show project success and adoption. Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="72f88-217">결과</span><span class="sxs-lookup"><span data-stu-id="72f88-217">Result</span></span>

<span data-ttu-id="72f88-218">조직은 해당 기본 개별 및 작은 그룹 단기 통신 및 일정 관리 도구와 Exchange Online 채택 했습니다.</span><span class="sxs-lookup"><span data-stu-id="72f88-218">Your organization has adopted Exchange Online as its primary individual and small group short-lived communication and scheduling tool.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="72f88-219">Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법</span><span class="sxs-lookup"><span data-stu-id="72f88-219">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="72f88-220">Microsoft 내의 내밀기 고 회사의 Exchange Online으로 마이그레이션한 및 인터넷 공격 으로부터 보호 하기 위해 Exchange Online Protection을 사용 하는 방법에 대해 알아봅니다 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="72f88-220">To peek inside Microsoft and learn how the company migrated to Exchange Online and is using Exchange Online Protection to protect against cyber attacks, see:</span></span>

- [<span data-ttu-id="72f88-221">Microsoft에서 150,000개의 사서함을 Exchange Online으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="72f88-221">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="72f88-222">Microsoft는 위협 인텔리전스를 사용하여 위협 방지, 감지 및 대응</span><span class="sxs-lookup"><span data-stu-id="72f88-222">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="72f88-223">Microsoft는 Office 365를 사용하여 피싱 시도 저지</span><span class="sxs-lookup"><span data-stu-id="72f88-223">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a><span data-ttu-id="72f88-224">다음 단계</span><span class="sxs-lookup"><span data-stu-id="72f88-224">Next steps</span></span>

<span data-ttu-id="72f88-225">Exchange Online의 지속적인 유지 관리에 대 한 이러한 리소스를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="72f88-225">See these resources for the ongoing maintenance of Exchange Online:</span></span>

- <span data-ttu-id="72f88-226">[Exchange Online의 Exchange 관리 센터](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="72f88-226">[Exchange admin center in Exchange Online](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx)</span></span> 
- <span data-ttu-id="72f88-227">[Exchange Online의 모니터링, 보고 및 메시지 추적](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="72f88-227">[Monitoring, reporting, and message tracing in Exchange Online](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)</span></span>
- <span data-ttu-id="72f88-228">[Exchange Online에서 전자 메일 백업](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="72f88-228">[Backing up email in Exchange Online](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx)</span></span> 
