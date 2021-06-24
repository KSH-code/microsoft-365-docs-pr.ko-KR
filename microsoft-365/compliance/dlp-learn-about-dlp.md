---
title: 데이터 손실 방지에 대해 알아보기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 데이터 손실 방지 정책 및 도구를 사용하여 Microsoft 365 보호하는 방법을 알아보고 DLP 수명 주기를 둘러보는 방법을 알아보고 있습니다.
ms.openlocfilehash: 9b449886e0856f7407fcd49b83192dd0c01474bd
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108262"
---
# <a name="learn-about-data-loss-prevention"></a><span data-ttu-id="44fda-103">데이터 손실 방지에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="44fda-103">Learn about data loss prevention</span></span>

<span data-ttu-id="44fda-104">조직은 재무 데이터, 소유 데이터, 신용 카드 번호, 의료 기록 또는 주민 등록 번호와 같은 중요한 정보를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-104">Organizations have sensitive information under their control such as financial data, proprietary data, credit card numbers, health records, or social security numbers.</span></span> <span data-ttu-id="44fda-105">이러한 중요한 데이터를 보호하고 위험을 줄이기 위해 사용자는 이 데이터를 사용할 수 없는 사용자와 부적절하게 공유하지 못하게 하는 방법이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-105">To help protect this sensitive data and reduce risk, they need a way to prevent their users from inappropriately sharing it with people who shouldn't have it.</span></span> <span data-ttu-id="44fda-106">이 사례를 DLP(데이터 손실 방지)라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-106">This practice is called data loss prevention (DLP).</span></span>

<span data-ttu-id="44fda-107">이 Microsoft 365 DLP 정책을 정의하고 적용하여 데이터 손실 방지를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-107">In Microsoft 365, you implement data loss prevention by defining and applying DLP policies.</span></span> <span data-ttu-id="44fda-108">DLP 정책을 사용하면 다음을 통해 중요한 항목을 식별, 모니터링 및 자동으로 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-108">With a DLP policy, you can identify, monitor, and automatically protect sensitive items across:</span></span>

- <span data-ttu-id="44fda-109">Microsoft 365, Teams, Exchange, SharePoint 및 OneDrive</span><span class="sxs-lookup"><span data-stu-id="44fda-109">Microsoft 365 services such as Teams, Exchange, SharePoint, and OneDrive</span></span>
- <span data-ttu-id="44fda-110">Office, Excel 및 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="44fda-110">Office applications such as Word, Excel, and PowerPoint</span></span>
- <span data-ttu-id="44fda-111">Windows 10 끝점</span><span class="sxs-lookup"><span data-stu-id="44fda-111">Windows 10 endpoints</span></span>
- <span data-ttu-id="44fda-112">비 Microsoft 클라우드 앱</span><span class="sxs-lookup"><span data-stu-id="44fda-112">non-Microsoft cloud apps</span></span>
- <span data-ttu-id="44fda-113">On-premises file shares and on-premises file shares and on-premises SharePoint.</span><span class="sxs-lookup"><span data-stu-id="44fda-113">on-premises file shares and on-premises SharePoint.</span></span>

<span data-ttu-id="44fda-114">Microsoft 365 단순한 텍스트 검색이 아니라 심층 콘텐츠 분석을 사용하여 중요한 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-114">Microsoft 365 detects sensitive items by using deep content analysis, not by just a simple text scan.</span></span> <span data-ttu-id="44fda-115">콘텐츠는 키워드와의 기본 데이터 일치, 정규식 평가, 내부 함수 유효성 검사 및 기본 데이터 일치와 근접한 보조 데이터 일치를 통해 분석됩니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-115">Content is analyzed for primary data matches to keywords, by the evaluation of regular expressions, by internal function validation, and by secondary data matches that are in proximity to the primary data match.</span></span> <span data-ttu-id="44fda-116">또한 DLP는 기계 학습 알고리즘 및 기타 방법을 사용하여 DLP 정책과 일치하는 콘텐츠를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-116">Beyond that DLP also uses machine learning algorithms and other methods to detect content that matches your DLP policies.</span></span>
  
## <a name="dlp-is-part-of-the-larger-microsoft-365-compliance-offering"></a><span data-ttu-id="44fda-117">DLP는 더 큰 Microsoft 365 규정 준수 제공의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-117">DLP is part of the larger Microsoft 365 Compliance offering</span></span>

<span data-ttu-id="44fda-118">Microsoft 365 DLP는 거주하거나 여행하는 모든 Microsoft 365 보호하는 데 사용할 수 있는 규정 준수 도구 중 하나에 불과합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-118">Microsoft 365 DLP is just one of the Microsoft 365 Compliance tools that you will use to help protect your sensitive items wherever they live or travel.</span></span> <span data-ttu-id="44fda-119">규정 준수 도구 집합의 다른 도구와 Microsoft 365 상호 연결하고 함께 작업하는 방법을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-119">You should understand the other tools in the Microsoft 365 Compliance tools set, how they interrelate, and work better together.</span></span>  <span data-ttu-id="44fda-120">정보 보호 [Microsoft 365 대한 자세한](protect-information.md) 내용은 준수 도구를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44fda-120">See, [Microsoft 365 compliance tools](protect-information.md) to learn more about the information protection process.</span></span>

## <a name="protective-actions-of-dlp-policies"></a><span data-ttu-id="44fda-121">DLP 정책의 보호 작업</span><span class="sxs-lookup"><span data-stu-id="44fda-121">Protective actions of DLP policies</span></span>

<span data-ttu-id="44fda-122">Microsoft 365 DLP 정책은 사용자가 미사용 중요한 항목, 전송되는 중요한 항목 또는 사용 중이던 중요한 항목에 대해 수행한 활동을 모니터링하고 보호 조치를 취하는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-122">Microsoft 365 DLP policies are how you monitor the activities that users take on sensitive items at rest, sensitive items in transit, or sensitive items in use and take protective actions.</span></span> <span data-ttu-id="44fda-123">예를 들어 사용자가 승인되지 않은 위치에 중요한 항목을 복사하거나 전자 메일 또는 정책에 정해진 기타 조건에서 의료 정보를 공유하는 등 금지된 작업을 수행하려고 할 때 DLP는 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-123">For example, when a user attempts to take a prohibited action, like copying a sensitive item to an unapproved location or sharing medical information in an email or other conditions laid out in a policy, DLP can:</span></span>

- <span data-ttu-id="44fda-124">중요한 항목을 부적절하게 공유하려고 할 수 있는 경우를 경고하는 팝업 정책 팁을 사용자에게 표시</span><span class="sxs-lookup"><span data-stu-id="44fda-124">show a pop-up policy tip to the user that warns them that they may be trying to share a sensitive item inappropriately</span></span>
- <span data-ttu-id="44fda-125">공유를 차단하고, 정책 팁을 통해 사용자가 차단을 오버라이드하고 사용자의 사유를 캡처할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="44fda-125">block the sharing and, via a policy tip, allow the user to override the block and capture the users' justification</span></span>
- <span data-ttu-id="44fda-126">Override 옵션 없이 공유 차단</span><span class="sxs-lookup"><span data-stu-id="44fda-126">block the sharing without the override option</span></span>
- <span data-ttu-id="44fda-127">미사용 데이터의 경우 중요한 항목을 잠가 안전한 검지 위치로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-127">for data at rest, sensitive items can be locked and moved to a secure quarantine location</span></span>
- <span data-ttu-id="44fda-128">Teams 경우 중요한 정보가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-128">for Teams chat, the sensitive information will not be displayed</span></span>

<span data-ttu-id="44fda-129">모든 DLP 모니터링 활동은 기본적으로 [](search-the-audit-log-in-security-and-compliance.md) Microsoft 365 감사 로그에 기록되어 활동 [탐색기로 라우팅됩니다.](data-classification-activity-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="44fda-129">All DLP monitored activities are recorded to the [Microsoft 365 Audit log](search-the-audit-log-in-security-and-compliance.md) by default and routed to [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="44fda-130">사용자가 DLP 정책의 기준을 충족하는 작업을 수행하고 경고가 구성된 경우 DLP는 DLP 경고 관리 대시보드에 [알림을 제공합니다.](dlp-configure-view-alerts-policies.md)</span><span class="sxs-lookup"><span data-stu-id="44fda-130">When a user performs an action that meets the criteria of a DLP policy, and you have alerts configured, DLP provides alerts in the [DLP alert management dashboard](dlp-configure-view-alerts-policies.md).</span></span>

## <a name="dlp-lifecycle"></a><span data-ttu-id="44fda-131">DLP 수명 주기</span><span class="sxs-lookup"><span data-stu-id="44fda-131">DLP lifecycle</span></span>

<span data-ttu-id="44fda-132">DLP 구현은 일반적으로 다음과 같은 주요 단계를 따르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-132">A DLP implementation typically follows these major phases.</span></span>

- [<span data-ttu-id="44fda-133">DLP 계획</span><span class="sxs-lookup"><span data-stu-id="44fda-133">Plan for DLP</span></span>](#plan-for-dlp)
- [<span data-ttu-id="44fda-134">DLP 준비</span><span class="sxs-lookup"><span data-stu-id="44fda-134">Prepare for DLP</span></span>](#prepare-for-dlp)
- [<span data-ttu-id="44fda-135">프로덕션에서 정책 배포</span><span class="sxs-lookup"><span data-stu-id="44fda-135">Deploy your policies in production</span></span>](#deploy-your-policies-in-production)


<!--ADD DIAGRAM OF THE DLP LIFECYCLE WORK ON WITH MAS-->

### <a name="plan-for-dlp"></a><span data-ttu-id="44fda-136">DLP 계획</span><span class="sxs-lookup"><span data-stu-id="44fda-136">Plan for DLP</span></span>

<span data-ttu-id="44fda-137">Microsoft 365 DLP 모니터링 및 보호는 사용자가 매일 사용하는 응용 프로그램에 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-137">Microsoft 365 DLP monitoring and protection are native to the applications that users use every day.</span></span> <span data-ttu-id="44fda-138">이렇게 하면 사용자가 데이터 손실 방지 사고와 관행에 익숙하지 않은 경우에도 조직의 중요한 항목을 위험한 활동으로부터 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-138">This helps to protect your organizations' sensitive items from risky activities even if your users are unaccustomed to data loss prevention thinking and practices.</span></span> <span data-ttu-id="44fda-139">조직과 사용자가 데이터 손실 방지 방법을 잘 아는 경우 DLP를 채택하려면 비즈니스 프로세스가 변경될 수 있으며 사용자에 대한 문화 변화가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-139">If your organization and your users are new to data loss prevention practices, the adoption of DLP may require a change to your business processes and there will be a culture shift for your users.</span></span> <span data-ttu-id="44fda-140">그러나 적절한 계획, 테스트 및 조정을 통해 DLP 정책은 잠재적인 비즈니스 프로세스 중단을 최소화하면서 중요한 항목을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-140">But, with proper planning, testing and tuning, your DLP policies will protect your sensitive items while minimizing any potential business process disruptions.</span></span>

<span data-ttu-id="44fda-141">**DLP에 대한 기술 계획**</span><span class="sxs-lookup"><span data-stu-id="44fda-141">**Technology planning for DLP**</span></span>

<span data-ttu-id="44fda-142">기술로 DLP는 미사용 데이터, 사용 중 데이터, Microsoft 365 서비스, Windows 10 장치, Windows 10 파일 공유 및 사내 장치 전체에서 이동되는 데이터를 모니터링하고 보호할 수 SharePoint.</span><span class="sxs-lookup"><span data-stu-id="44fda-142">Keep in mind that DLP as a technology can monitor and protect your data at rest, data in use and data in motion across Microsoft 365 services, Windows 10 devices, on-premises file shares, and on-premises SharePoint.</span></span> <span data-ttu-id="44fda-143">다양한 위치, 모니터링 및 보호하려는 데이터의 유형, 정책 일치 시 수행할 작업에 대한 계획이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-143">There are planning implications for the different locations, the type of data you want to monitor and protect, and the actions to be taken when a policy match occurs.</span></span>  

<span data-ttu-id="44fda-144">**DLP에 대한 비즈니스 프로세스 계획**</span><span class="sxs-lookup"><span data-stu-id="44fda-144">**Business processes planning for DLP**</span></span>

<span data-ttu-id="44fda-145">DLP 정책은 전자 메일을 통해 중요한 정보를 부적절하게 공유하는 등 금지된 활동을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-145">DLP policies can block prohibited activities, like inappropriate sharing of sensitive information via email.</span></span> <span data-ttu-id="44fda-146">DLP 정책을 계획할 때 중요한 항목을 터치하는 비즈니스 프로세스를 식별해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-146">As you plan your DLP policies, you must identify the business processes that touch your sensitive items.</span></span> <span data-ttu-id="44fda-147">비즈니스 프로세스 소유자는 허용해야 하는 적절한 사용자 동작과 보호해야 하는 부적절한 사용자 동작을 식별하는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-147">The business process owners can help you identify appropriate user behaviors that should be allowed and inappropriate user behaviors that should be protected against.</span></span> <span data-ttu-id="44fda-148">정책을 계획하고 테스트 모드에서 배포하고, 보다 제한적인 [](data-classification-activity-explorer.md) 모드에서 적용하기 전에 먼저 활동 탐색기를 통해 영향을 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-148">You should plan your policies and deploy them in test mode, and evaluate their impact via [activity explorer](data-classification-activity-explorer.md) first, before applying them in more restrictive modes.</span></span>

<span data-ttu-id="44fda-149">**DLP에 대한 조직 문화 계획**</span><span class="sxs-lookup"><span data-stu-id="44fda-149">**Organizational culture planning for DLP**</span></span>

<span data-ttu-id="44fda-150">성공적인 DLP 구현은 사용자가 잘 계획 및 조정된 정책에 따라 데이터 손실 방지 사례를 교육하고 적용하는 데 크게 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-150">A successful DLP implementation is as much dependent on getting your users trained and acclimated to data loss prevention practices as it is on well planned and tuned policies.</span></span> <span data-ttu-id="44fda-151">사용자의 참여가 까다로워지기 때문에 사용자에 대한 교육도 계획해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-151">Since your users are heavily involved, be sure to plan for training for them too.</span></span> <span data-ttu-id="44fda-152">정책 적용을 테스트 모드에서 더 제한적인 모드로 변경하기 전에 정책 팁을 전략적으로 사용하여 사용자에 대한 인식을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-152">You can strategically use policy tips to raise awareness with your users before changing the policy enforcement from test mode to more restrictive modes.</span></span>

<!--For more information on planning for DLP, including suggestions for deployment based on your needs and resources, see [Planning for Microsoft 365 data loss prevention](dlp-plan-for-dlp.md).-->

### <a name="prepare-for-dlp"></a><span data-ttu-id="44fda-153">DLP 준비</span><span class="sxs-lookup"><span data-stu-id="44fda-153">Prepare for DLP</span></span>

<span data-ttu-id="44fda-154">미사용 데이터, 사용 중 데이터 및 위치에서 이동하는 데이터에 DLP 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-154">You can apply DLP policies to data at rest, data in use, and data in motion in locations, such as:</span></span>

- <span data-ttu-id="44fda-155">Exchange Online 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="44fda-155">Exchange Online email</span></span>
- <span data-ttu-id="44fda-156">SharePoint Online 사이트</span><span class="sxs-lookup"><span data-stu-id="44fda-156">SharePoint Online sites</span></span>
- <span data-ttu-id="44fda-157">OneDrive 계정</span><span class="sxs-lookup"><span data-stu-id="44fda-157">OneDrive accounts</span></span>
- <span data-ttu-id="44fda-158">Teams 채팅 및 채널 메시지</span><span class="sxs-lookup"><span data-stu-id="44fda-158">Teams chat and channel messages</span></span>
- <span data-ttu-id="44fda-159">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="44fda-159">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="44fda-160">Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="44fda-160">Windows 10 devices</span></span>
- <span data-ttu-id="44fda-161">사내 리포지토리</span><span class="sxs-lookup"><span data-stu-id="44fda-161">On-premises repositories</span></span>

<span data-ttu-id="44fda-162">각 선행 준비는 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-162">Each one has different pre-requisites.</span></span> <span data-ttu-id="44fda-163">일부 위치의 중요한 항목(예: 온라인 Exchange)은 해당 항목에 적용되는 정책을 구성하기만 하여 DLP umbrella 아래에 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-163">Sensitive items in some locations, like Exchange online, can be brought under the DLP umbrella by just configuring a policy that applies to them.</span></span> <span data-ttu-id="44fda-164">사내 파일 리포지토리와 같은 다른 기능을 사용하려면 AIP(Azure Information Protection) 스캐너를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-164">Others, such as on-premises file repositories require a deployment of Azure Information Protection (AIP) scanner.</span></span> <span data-ttu-id="44fda-165">차단 작업을 활성화하기 전에 환경, 코드 초안 정책을 준비하고 철저하게 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-165">You'll need to prepare your environment, code draft policies, and test them thoroughly before activating any blocking actions.</span></span>

### <a name="deploy-your-policies-in-production"></a><span data-ttu-id="44fda-166">프로덕션에서 정책 배포</span><span class="sxs-lookup"><span data-stu-id="44fda-166">Deploy your policies in production</span></span>

#### <a name="design-your-policies"></a><span data-ttu-id="44fda-167">정책 디자인</span><span class="sxs-lookup"><span data-stu-id="44fda-167">Design your policies</span></span>

<span data-ttu-id="44fda-168">먼저 컨트롤 목표를 정의하고 각 워크로드에 적용되는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-168">Start by defining your control objectives, and how they apply across each respective workload.</span></span> <span data-ttu-id="44fda-169">목표를 구상하는 정책 초안을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-169">Draft a policy that embodies your objectives.</span></span> <span data-ttu-id="44fda-170">한 번의 작업으로 시작하거나 모든 워크로드에서 자유롭게 시작할 수 있습니다. 아직 영향이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-170">Feel free to start with one workload at a time, or across all workloads - there's no impact yet.</span></span>

#### <a name="implement-policy-in-test-mode"></a><span data-ttu-id="44fda-171">테스트 모드에서 정책 구현</span><span class="sxs-lookup"><span data-stu-id="44fda-171">Implement policy in test mode</span></span>

<span data-ttu-id="44fda-172">테스트 모드에서 DLP 정책을 사용하여 컨트롤을 구현하여 컨트롤의 영향을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-172">Evaluate the impact of the controls by implementing them with a DLP policy in test mode.</span></span> <span data-ttu-id="44fda-173">모든 결과를 얻을 수 있도록 테스트 모드에서 모든 워크로드에 정책을 적용하는 것이 괜찮지만 필요한 경우 하나의 워크로드로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-173">It's ok to apply the policy to all workloads in test mode, so that you can get the full breadth of results, but you can start with one workload if you need to.</span></span>

#### <a name="monitor-outcomes-and-fine-tune-the-policy"></a><span data-ttu-id="44fda-174">결과 모니터링 및 정책 미세 조정</span><span class="sxs-lookup"><span data-stu-id="44fda-174">Monitor outcomes and fine-tune the policy</span></span>

<span data-ttu-id="44fda-175">테스트 모드에서는 정책의 결과를 모니터링하고 컨트롤 목표를 충족하도록 세부 조정하면서 유효한 사용자 워크플로 및 생산성에 부정적인 영향을 미치거나 부적당하게 영향을 끼치지 않는지 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-175">While in test mode, monitor the outcomes of the policy and fine-tune it so that it meets your control objectives while ensuring you aren't adversely or inadvertently impacting valid user workflows and productivity.</span></span> <span data-ttu-id="44fda-176">다음은 세부적으로 조정해야 할 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-176">Here are some examples of things to fine-tune:</span></span>

- <span data-ttu-id="44fda-177">범위에 포함되거나 범위를 벗어날 위치 및 사람/위치 조정</span><span class="sxs-lookup"><span data-stu-id="44fda-177">adjusting the locations and people/places that are in or out of scope</span></span>
- <span data-ttu-id="44fda-178">항목 및 해당 항목으로 수행되는 것이 정책과 일치하는지 확인하는 데 사용되는 조건 및 예외 조정</span><span class="sxs-lookup"><span data-stu-id="44fda-178">tune the conditions and exceptions that are used to determine if an item and what is being done with it matches the policy</span></span>
- <span data-ttu-id="44fda-179">중요한 정보 정의/s</span><span class="sxs-lookup"><span data-stu-id="44fda-179">the sensitive information definition/s</span></span>
- <span data-ttu-id="44fda-180">동작</span><span class="sxs-lookup"><span data-stu-id="44fda-180">the actions</span></span>
- <span data-ttu-id="44fda-181">제한 수준</span><span class="sxs-lookup"><span data-stu-id="44fda-181">the level of restrictions</span></span>
- <span data-ttu-id="44fda-182">새 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="44fda-182">add new controls</span></span>
- <span data-ttu-id="44fda-183">새 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="44fda-183">add new people</span></span>
- <span data-ttu-id="44fda-184">새 제한된 앱 추가</span><span class="sxs-lookup"><span data-stu-id="44fda-184">add new restricted apps</span></span>
- <span data-ttu-id="44fda-185">새 제한된 사이트 추가</span><span class="sxs-lookup"><span data-stu-id="44fda-185">add new restricted sites</span></span>

#### <a name="enable-the-control-and-tune-your-policies"></a><span data-ttu-id="44fda-186">제어를 사용하도록 설정하고 정책 조정</span><span class="sxs-lookup"><span data-stu-id="44fda-186">Enable the control and tune your policies</span></span>

<span data-ttu-id="44fda-187">정책이 모든 목표를 충족하면 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-187">Once the policy meets all your objectives, turn it on.</span></span> <span data-ttu-id="44fda-188">정책 응용 프로그램의 결과를 계속 모니터링하고 필요한 경우 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-188">Continue to monitor the outcomes of the policy application and tune as needed.</span></span> <span data-ttu-id="44fda-189">일반적으로 정책은 켜진 후 1시간 정도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-189">In general, policies take effect about an hour after being turned on.</span></span> 

<!--See, LINK TO topic for SLAs for location specific  details-->

## <a name="dlp-policy-configuration-overview"></a><span data-ttu-id="44fda-190">DLP 정책 구성 개요</span><span class="sxs-lookup"><span data-stu-id="44fda-190">DLP policy configuration overview</span></span>

<span data-ttu-id="44fda-191">DLP 정책을 만들고 구성하는 방법에는 유연성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-191">You have flexibility in how you create and configure your DLP policies.</span></span> <span data-ttu-id="44fda-192">미리 정의한 템플릿에서 시작하여 몇 번의 클릭으로 정책을 만들거나 직접 디자인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-192">You can start from a predefined template and create a policy in just a few clicks or you can design your own from the ground up.</span></span> <span data-ttu-id="44fda-193">어떤 DLP 정책을 선택하든 상관없이 모든 DLP 정책에 동일한 정보가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-193">No matter which you choose, all DLP policies require the same information from you.</span></span>

1. <span data-ttu-id="44fda-194">**모니터링할** 정책 선택 - Microsoft 365 미리 정의한 여러 정책 템플릿이 함께 사용되어 시작하거나 사용자 지정 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-194">**Choose what you want to monitor** - Microsoft 365 comes with many predefined policy templates to help you get started or you can create a custom policy.</span></span>
    - <span data-ttu-id="44fda-195">미리 정의한 정책 템플릿: 재무 데이터, 의료 및 의료 데이터, 다양한 국가 및 지역에 대한 개인 정보 보호 데이터.</span><span class="sxs-lookup"><span data-stu-id="44fda-195">A predefined policy template: Financial data, Medical and health data, Privacy data all for various countries and regions.</span></span>
    - <span data-ttu-id="44fda-196">사용 가능한 중요한 정보 유형, 보존 레이블 및 민감도 레이블을 사용하는 사용자 지정 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-196">A custom policy that uses the available sensitive information types, retention labels, and sensitivity labels.</span></span>
2. <span data-ttu-id="44fda-197">**모니터링할** 위치 선택 - DLP에서 중요한 정보를 모니터링할 위치를 하나 이상 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-197">**Choose where you want to monitor** - You pick one or more locations that you want DLP to monitor for sensitive information.</span></span> <span data-ttu-id="44fda-198">다음을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-198">You can monitor:</span></span>
    
<span data-ttu-id="44fda-199">위치</span><span class="sxs-lookup"><span data-stu-id="44fda-199">location</span></span> | <span data-ttu-id="44fda-200">포함/제외 기준</span><span class="sxs-lookup"><span data-stu-id="44fda-200">include/exclude by</span></span>|
|---------|---------|
|<span data-ttu-id="44fda-201">Exchange 전자 메일</span><span class="sxs-lookup"><span data-stu-id="44fda-201">Exchange email</span></span>| <span data-ttu-id="44fda-202">메일 그룹</span><span class="sxs-lookup"><span data-stu-id="44fda-202">distribution groups</span></span>|
|<span data-ttu-id="44fda-203">SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="44fda-203">SharePoint sites</span></span> |<span data-ttu-id="44fda-204">사이트</span><span class="sxs-lookup"><span data-stu-id="44fda-204">sites</span></span> |
|<span data-ttu-id="44fda-205">OneDrive 계정</span><span class="sxs-lookup"><span data-stu-id="44fda-205">OneDrive accounts</span></span> |<span data-ttu-id="44fda-206">계정 또는 메일 그룹</span><span class="sxs-lookup"><span data-stu-id="44fda-206">accounts or distribution groups</span></span> |
|<span data-ttu-id="44fda-207">Teams 채팅 및 채널 메시지</span><span class="sxs-lookup"><span data-stu-id="44fda-207">Teams chat and channel messages</span></span> |<span data-ttu-id="44fda-208">계정</span><span class="sxs-lookup"><span data-stu-id="44fda-208">accounts</span></span> |
|<span data-ttu-id="44fda-209">Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="44fda-209">Windows 10 devices</span></span> |<span data-ttu-id="44fda-210">사용자 또는 그룹</span><span class="sxs-lookup"><span data-stu-id="44fda-210">user or group</span></span> |
|<span data-ttu-id="44fda-211">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="44fda-211">Microsoft Cloud App Security</span></span> |<span data-ttu-id="44fda-212">인스턴스</span><span class="sxs-lookup"><span data-stu-id="44fda-212">instance</span></span> |
|<span data-ttu-id="44fda-213">사내 리포지토리</span><span class="sxs-lookup"><span data-stu-id="44fda-213">On-premises repositories</span></span>| <span data-ttu-id="44fda-214">리포지토리 파일 경로</span><span class="sxs-lookup"><span data-stu-id="44fda-214">repository file path</span></span>|

3. <span data-ttu-id="44fda-215">**항목에 정책을** 적용하기 위해 일치해야 하는 조건을 선택하십시오. 미리 구성된 조건을 수락하거나 사용자 지정 조건을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-215">**Choose the conditions that must be matched for a policy to be applied to an item** - you can accept pre-configured conditions or define custom conditions.</span></span> <span data-ttu-id="44fda-216">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-216">Some examples are:</span></span>

- <span data-ttu-id="44fda-217">항목에는 특정 컨텍스트에서 사용되는 특정 종류의 중요한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-217">item contains a specified kind of sensitive information that is being used in a certain context.</span></span> <span data-ttu-id="44fda-218">예를 들어, 95개 주민 등록 번호를 받는 사람에게 전자 메일로 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-218">For example, 95 social security numbers being emailed to recipient outside your org.</span></span>
- <span data-ttu-id="44fda-219">항목에 지정된 민감도 레이블이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-219">item has a specified sensitivity label</span></span>
- <span data-ttu-id="44fda-220">중요한 정보가 있는 항목은 내부 또는 외부적으로 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-220">item with sensitive information is shared either internally or externally</span></span>

4. <span data-ttu-id="44fda-221">**정책 조건이 충족되는** 경우 수행할 작업을 선택하십시오. 작업은 활동이 수행되는 위치에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-221">**Choose the action to take when the policy conditions are met** - The actions depend on the location where the activity is happening.</span></span>  <span data-ttu-id="44fda-222">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-222">Some examples are:</span></span>

- <span data-ttu-id="44fda-223">SharePoint/Exchange/OneDrive: 조직 외부의 사람이 콘텐츠에 액세스하는 것을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-223">SharePoint/Exchange/OneDrive: Block people who are outside your organization form accessing the content.</span></span> <span data-ttu-id="44fda-224">사용자에게 팁을 표시하고 DLP 정책에 의해 금지된 작업을 수행하고 있는 전자 메일 알림을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-224">Show the user a tip and send them an email notification that they are taking an action that is prohibited by the DLP policy.</span></span>
- <span data-ttu-id="44fda-225">Teams 채팅 및 채널: 채팅 또는 채널에서 중요한 정보가 공유되지 못하게 차단</span><span class="sxs-lookup"><span data-stu-id="44fda-225">Teams Chat and Channel: Block sensitive information from being shared in the chat or channel</span></span>
- <span data-ttu-id="44fda-226">Windows 10 장치: 중요한 항목을 제거 가능한 USB 장치로 복사 감사 또는 제한</span><span class="sxs-lookup"><span data-stu-id="44fda-226">Windows 10 Devices: Audit or restrict copying a sensitive item to a removeable USB device</span></span> 
- <span data-ttu-id="44fda-227">Office 앱: 사용자에게 위험한 동작에 참여하고 있으며 이를 차단하거나 차단하지만 이를 허용하도록 알리는 팝업을 표시하세요.</span><span class="sxs-lookup"><span data-stu-id="44fda-227">Office Apps: Show a popup notifying the user that they are engaging in a risky behavior and block or block but allow override.</span></span>
- <span data-ttu-id="44fda-228">On-premises file shares: move the file from where it is stored to a quarantine folder</span><span class="sxs-lookup"><span data-stu-id="44fda-228">On-premises file shares: move the file from where it is stored to a quarantine folder</span></span>

> [!NOTE]
> <span data-ttu-id="44fda-229">수행할 조건과 동작은 Rule이라는 개체에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-229">The conditions and the actions to take are defined in an object called a Rule.</span></span>

<!--## Create a DLP policy

All DLP policies are created and maintained in the Microsoft 365 Compliance center. See, INSERT LINK TO ARTICLE THAT WILL START WALKING THEM THROUGH THE POLICY CREATION PROCEDURES for more information.-->

<span data-ttu-id="44fda-230">준수 센터에서 DLP 정책을 만든 후 중앙 정책 저장소에 저장되어 다음을 비롯한 다양한 콘텐츠 원본과 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-230">After you create a DLP policy in the Compliance Center, it's stored in a central policy store, and then synced to the various content sources, including:</span></span>
  
- <span data-ttu-id="44fda-231">Exchange Online, 웹용 Outlook 및 Outlook.</span><span class="sxs-lookup"><span data-stu-id="44fda-231">Exchange Online, and from there to Outlook on the web and Outlook.</span></span>
- <span data-ttu-id="44fda-232">비즈니스용 OneDrive 사이트.</span><span class="sxs-lookup"><span data-stu-id="44fda-232">OneDrive for Business sites.</span></span>
- <span data-ttu-id="44fda-233">SharePoint Online 사이트.</span><span class="sxs-lookup"><span data-stu-id="44fda-233">SharePoint Online sites.</span></span>
- <span data-ttu-id="44fda-234">Office 데스크톱 프로그램 (Excel, PowerPoint 및 Word).</span><span class="sxs-lookup"><span data-stu-id="44fda-234">Office desktop programs (Excel, PowerPoint, and Word).</span></span>
- <span data-ttu-id="44fda-235">Microsoft Teams 채널 및 채팅 메시지.</span><span class="sxs-lookup"><span data-stu-id="44fda-235">Microsoft Teams channels and chat messages.</span></span>
    
<span data-ttu-id="44fda-236">정책이 올바른 위치와 동기화된 후 콘텐츠를 평가하고 작업을 적용하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-236">After the policy's synced to the right locations, it starts to evaluate content and enforce actions.</span></span>

## <a name="viewing-policy-application-results"></a><span data-ttu-id="44fda-237">정책 응용 프로그램 결과 보기</span><span class="sxs-lookup"><span data-stu-id="44fda-237">Viewing policy application results</span></span>

<span data-ttu-id="44fda-238">DLP는 모니터링, 정책 일치 Microsoft 365 작업 및 사용자 활동에서 광범위한 정보를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-238">DLP reports a vast amount of information into Microsoft 365 from monitoring, policy matches and actions, and user activities.</span></span> <span data-ttu-id="44fda-239">중요한 항목에 대해 수행된 정책 및 선고 작업을 조정하기 위해 해당 정보를 사용 및 조치를 취해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-239">You'll need to consume and act on that information to tune your policies and triage actions taken on sensitive items.</span></span> <span data-ttu-id="44fda-240">원격 분석은 Microsoft 365 준수 [](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log-in-the-compliance-center) 센터 감사 로그로 이동하고, 처리된 후 다른 보고 도구로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-240">The telemetry goes into the [Microsoft 365 Compliance center Audit Logs](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log-in-the-compliance-center) first, is processed, and makes its way to different reporting tools.</span></span> <span data-ttu-id="44fda-241">각 보고 도구의 용도는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-241">Each reporting tool has a different purpose.</span></span>  

### <a name="dlp-alerts-dashboard"></a><span data-ttu-id="44fda-242">DLP 경고 대시보드</span><span class="sxs-lookup"><span data-stu-id="44fda-242">DLP Alerts Dashboard</span></span>

<span data-ttu-id="44fda-243">DLP가 중요한 항목에 대해 작업을 수행하면 구성 가능한 경고를 통해 해당 작업을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-243">When DLP takes an action on a sensitive item, you can be notified of that action via a configurable alert.</span></span> <span data-ttu-id="44fda-244">규정 준수 센터는 이러한 경고를 사서함에 더해지기보다는 DLP 경고 관리 대시보드에서 해당 경고를 사용할 [수 있도록 합니다.](dlp-configure-view-alerts-policies.md)</span><span class="sxs-lookup"><span data-stu-id="44fda-244">Rather than having these alerts pile up in a mailbox for you to sift through, the Compliance center makes them available in the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span> <span data-ttu-id="44fda-245">DLP 경고 대시보드를 사용하여 경고를 구성하고, 검토하고, 경고를 심사하고, DLP 경고의 해결 방법을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-245">Use the DLP Alerts dashboard to configure alerts, review them, triage them and track resolution of DLP Alerts.</span></span> <span data-ttu-id="44fda-246">다음은 정책 일치 및 정책 일치 및 장치 활동으로 생성된 경고의 Windows 10 예입니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-246">Here's an example of alerts generated by policy matches and activities from Windows 10 devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="44fda-247">![경고 정보](../media/Alert-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="44fda-247">![Alert info](../media/Alert-info-1.png)</span></span>

<span data-ttu-id="44fda-248">동일한 대시보드에서 서식 있는 메타데이터와 관련된 이벤트 세부 정보를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-248">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="44fda-249">![이벤트 정보](../media/Event-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="44fda-249">![event info](../media/Event-info-1.png)</span></span>

### <a name="reports"></a><span data-ttu-id="44fda-250">보고서</span><span class="sxs-lookup"><span data-stu-id="44fda-250">Reports</span></span>

<span data-ttu-id="44fda-251">[DLP 보고서는](view-the-dlp-reports.md#view-the-reports-for-data-loss-prevention) 시간이 경과에 따라 광범위한 추세를 표시하고 다음에 대한 특정 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-251">The [DLP reports](view-the-dlp-reports.md#view-the-reports-for-data-loss-prevention) show broad trends over time and give specific insights into:</span></span>

- <span data-ttu-id="44fda-252">**DLP 정책 날짜** 범위, 위치, 정책 또는 작업을 사용하여 시간이 지날 때 일치하고 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-252">**DLP Policy Matches** over time and filter by date range, location, policy, or action</span></span>
- <span data-ttu-id="44fda-253">**또한 DLP 인시던트 일치는** 시간이 지날 때 일치 항목을 표시하지만 정책 규칙이 아닌 항목에 대한 피벗입니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-253">**DLP incident matches** also shows matches over time, but pivots on the items rather than the policy rules.</span></span>
- <span data-ttu-id="44fda-254">**DLP 가짓 긍정** 및 다시 설정은 가짓 긍정의 수를 표시하고, 구성된 경우 사용자 정당성과 함께 사용자 다시 설정의 수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-254">**DLP false positives and overrides** shows the count of false positives and, if configured, user-overrides along with the user justification.</span></span>

### <a name="dlp-activity-explorer"></a><span data-ttu-id="44fda-255">DLP 활동 탐색기</span><span class="sxs-lookup"><span data-stu-id="44fda-255">DLP Activity Explorer</span></span>

<span data-ttu-id="44fda-256">DLP 페이지의 활동 탐색기 탭에는 활동 필터가 *DLPRuleMatch로 미리 설정되어 있습니다.* </span><span class="sxs-lookup"><span data-stu-id="44fda-256">The Activity explorer tab on the DLP page has the *Activity* filter preset to *DLPRuleMatch*.</span></span> <span data-ttu-id="44fda-257">이 도구를 사용하여 중요한 정보를 포함하거나 레이블이 적용된 콘텐츠와 관련된 활동을 검토할 수 있습니다(예: 변경된 레이블, 파일이 수정된 후 규칙과 일치).</span><span class="sxs-lookup"><span data-stu-id="44fda-257">Use this tool to review activity related to content that contains sensitive info or has labels applied, such as what labels were changed, files were modified, and matched a rule.</span></span>

![<span data-ttu-id="44fda-258">DLPRuleMatch 범위 활동 탐색기 스크린샷</span><span class="sxs-lookup"><span data-stu-id="44fda-258">screenshot of the DLPRuleMatch scoped activity explorer</span></span> ](../media/dlp-activity-explorer.png)

<span data-ttu-id="44fda-259">자세한 내용은 활동 탐색기 [시작을 참조하세요.](data-classification-activity-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="44fda-259">For more information, see [Get started with activity explorer](data-classification-activity-explorer.md)</span></span>

<span data-ttu-id="44fda-260">DLP에 대한 Microsoft 365 자세한 내용은 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="44fda-260">To learn more about Microsoft 365 DLP, see:</span></span>

- [<span data-ttu-id="44fda-261">Microsoft 365 끝점 데이터 손실 방지에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="44fda-261">Learn about Microsoft 365 Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="44fda-262">Microsoft Teams의 기본 데이터 손실 방지 정책에 대한 자세한 정보(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="44fda-262">Learn about the default data loss prevention policy in Microsoft Teams (preview)</span></span>](dlp-teams-default-policy.md)
- [<span data-ttu-id="44fda-263">Microsoft 365 데이터 손실 방지 온-프레미스 스캐너 알아보기(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="44fda-263">Learn about the Microsoft 365 data loss prevention on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="44fda-264">Microsoft 규정 준수 확장(미리 보기)에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="44fda-264">Learn about the Microsoft Compliance Extension (preview)</span></span>](dlp-chrome-learn-about.md)
- [<span data-ttu-id="44fda-265">데이터 손실 방지 알림 대시보드에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="44fda-265">Learn about the data loss prevention Alerts dashboard</span></span>](dlp-alerts-dashboard-learn.md)

<span data-ttu-id="44fda-266">데이터 손실 방지를 사용하여 데이터 개인 정보 보호 규정을 준수하는 방법에 대한 자세한 내용은 [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="44fda-266">To learn how to use data loss prevention to comply with data privacy regulations, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md)  (aka.ms/m365dataprivacy).</span></span>