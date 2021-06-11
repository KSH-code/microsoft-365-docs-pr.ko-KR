---
title: 데이터 손실 방지 계획
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
description: 데이터 손실 방지 계획 프로세스 개요
ms.openlocfilehash: 84f1dc0426ba88f934c1d67d71f75364adeb4340
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583355"
---
# <a name="plan-for-data-loss-prevention-dlp"></a><span data-ttu-id="dcbb2-103">DLP(데이터 손실 방지) 계획</span><span class="sxs-lookup"><span data-stu-id="dcbb2-103">Plan for data loss prevention (DLP)</span></span>

<span data-ttu-id="dcbb2-104">모든 조직의 비즈니스 요구, 목표, 리소스 및 상황은 각 조직마다 고유하기 때문에 모든 조직은 DLP(데이터 손실 방지)를 다르게 계획하고 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-104">Every organization will plan for and implement data loss prevention (DLP) differently, because every organization's business needs, goals, resources, and situation are unique to them.</span></span> <span data-ttu-id="dcbb2-105">그러나 성공한 모든 DLP 구현에 공통적인 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-105">However, there are elements that are common to all successful DLP implementations.</span></span> <span data-ttu-id="dcbb2-106">이 문서에서는 조직에서 DLP 계획에 사용하는 모범 사례를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-106">This article presents the best practices that are used by organizations in their DLP planning.</span></span>

## <a name="multiple-starting-points"></a><span data-ttu-id="dcbb2-107">여러 시작 지점</span><span class="sxs-lookup"><span data-stu-id="dcbb2-107">Multiple starting points</span></span>

<span data-ttu-id="dcbb2-108">많은 조직에서 다양한 정부 또는 산업 규정을 준수하기 위해 DLP를 구현하기로 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-108">Many organizations choose to implement DLP to comply with various governmental or industry regulations.</span></span> <span data-ttu-id="dcbb2-109">예를 들어 유럽 연합의 GDPR(일반 데이터 보호 규정) 또는 HIPAA(Health Insurance Portability and Accountability Act) 또는 캘리포니아 소비자 개인 정보 보호법(CCPA)을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-109">For example, the European Union's General Data Protection Regulation (GDPR), or the Health Insurance Portability and Accountability Act (HIPAA), or the California Consumer Privacy Act (CCPA).</span></span> <span data-ttu-id="dcbb2-110">또한 데이터 손실 방지를 구현하여 지적 재산을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-110">They also implement data loss prevention to protect their intellectual property.</span></span> <span data-ttu-id="dcbb2-111">그러나 DLP 여정의 시작 장소와 최종 목적지는 다양합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-111">But the starting place and ultimate destination in the DLP journey vary.</span></span> 

<span data-ttu-id="dcbb2-112">조직은 DLP 여정을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-112">Organizations can start their DLP journey:</span></span>

- <span data-ttu-id="dcbb2-113">채팅 및 채널 메시지 또는 Teams 디바이스의 정보를 보호하려는 경우와 같은 플랫폼 Windows 10 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-113">from a platform focus, like wanting to protect information in Teams Chat and Channel messages or on Windows 10 devices</span></span>
- <span data-ttu-id="dcbb2-114">의료 기록과 같이 보호의 우선 순위를 지정하려는 중요한 정보를 알고 있으며 이를 보호하기 위한 정책 정의로 바로 가기</span><span class="sxs-lookup"><span data-stu-id="dcbb2-114">knowing what sensitive information they want to prioritize protecting, like health care records, and going straight to defining policies to protect it</span></span>
- <span data-ttu-id="dcbb2-115">중요한 정보가 무엇인지, 정보의 위치, 누가 검색 및 분류로 시작하고 좀 더 까다로적인 접근 방식을 취하는지 알지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-115">without knowing what their sensitive information is, where it is, and who is doing what with it so they start with discovery and categorization and take a more methodical approach</span></span>
- <span data-ttu-id="dcbb2-116">중요한 정보가 무엇인지, 정보의 위치를 모르거나, 정보로 무엇을 하고 있는지 알지 못하지만 정책 정의로 바로 이동하여 이러한 결과를 시작 위치로 사용하여 정책을 구체화할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-116">without knowing what their sensitive information is, or where it is, or who is doing what with it, but they will move straight to defining policies and use those outcomes as a starting place and then refine their policies from there</span></span>
- <span data-ttu-id="dcbb2-117">정보 보호 스택의 전체 Microsoft 365 구현해야 하다는 것을 알고 있으므로 더 장기적인 방법으로 접근할 예정임</span><span class="sxs-lookup"><span data-stu-id="dcbb2-117">knowing that they need to implement the full Microsoft 365 Information Protection stack and so intend to take a longer term, methodical approach</span></span>

<span data-ttu-id="dcbb2-118">이러한 DLP는 고객이 DLP에 접근할 수 있는 방법의 몇 가지 예에 불과하며, 어디에서 시작해도 상관이 없습니다Microsoft 365 DLP는 시작부터 완전히 실현된 데이터 손실 방지 전략까지 다양한 유형의 정보 보호 여정을 수용할 수 있을 만큼 유연합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-118">These are just some examples of how customers can approach DLP and it doesn't matter where you start from, Microsoft 365 DLP is flexible enough to accommodate various types of information protection journeys from start to a fully realized data loss prevention strategy.</span></span> 

## <a name="overview-of-planning-process"></a><span data-ttu-id="dcbb2-119">계획 프로세스 개요</span><span class="sxs-lookup"><span data-stu-id="dcbb2-119">Overview of planning process</span></span>

<span data-ttu-id="dcbb2-120">데이터 [손실 방지에 대한 자세한](dlp-learn-about-dlp.md#learn-about-data-loss-prevention) 정보에서는 DLP 계획 프로세스의 세 가지 [측면을 소개합니다.](dlp-learn-about-dlp.md#plan-for-dlp)</span><span class="sxs-lookup"><span data-stu-id="dcbb2-120">The [Learn about data loss prevention](dlp-learn-about-dlp.md#learn-about-data-loss-prevention) introduces the three different aspects of the [DLP planning process](dlp-learn-about-dlp.md#plan-for-dlp).</span></span> <span data-ttu-id="dcbb2-121">여기서는 모든 DLP 계획에 공통되는 요소에 대해 자세히 설명할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-121">We'll go into more detail here on the elements that are common to all DLP plans.</span></span>

### <a name="identify-stakeholders"></a><span data-ttu-id="dcbb2-122">관련자 파악</span><span class="sxs-lookup"><span data-stu-id="dcbb2-122">Identify stakeholders</span></span>

<span data-ttu-id="dcbb2-123">DLP 정책을 구현하면 조직의 많은 부분에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-123">When implemented, DLP policies can be applied across large portions of your organization.</span></span> <span data-ttu-id="dcbb2-124">IT는 부정적인 결과 없이는 자체적으로 광범위한 계획을 개발할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-124">IT can't develop a broad ranging plan on their own without negative consequences.</span></span> <span data-ttu-id="dcbb2-125">다음을 할 수 있는 관련자를 식별해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-125">You need to identify the stakeholders who can:</span></span>

- <span data-ttu-id="dcbb2-126">조직이 적용하는 규정, 법률 및 산업 표준 설명</span><span class="sxs-lookup"><span data-stu-id="dcbb2-126">describe the regulations, laws, and industry standards your organization is subject to</span></span>
- <span data-ttu-id="dcbb2-127">보호할 중요한 항목의 범주</span><span class="sxs-lookup"><span data-stu-id="dcbb2-127">the categories of sensitive items to be protected</span></span>
- <span data-ttu-id="dcbb2-128">사용되는 비즈니스 프로세스</span><span class="sxs-lookup"><span data-stu-id="dcbb2-128">the business processes they are used in</span></span>
- <span data-ttu-id="dcbb2-129">제한해야 하는 위험한 동작</span><span class="sxs-lookup"><span data-stu-id="dcbb2-129">the risky behavior that should be limited</span></span>
- <span data-ttu-id="dcbb2-130">관련 항목 및 위험의 민감도에 따라 먼저 보호해야 하는 데이터의 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="dcbb2-130">prioritize which data should be protected first based on the sensitivity of the items and risk involved</span></span>
- <span data-ttu-id="dcbb2-131">DLP 정책 일치 이벤트 검토 및 수정 프로세스 개요</span><span class="sxs-lookup"><span data-stu-id="dcbb2-131">outline the DLP policy match event review and remediation process</span></span> 
 
<span data-ttu-id="dcbb2-132">일반적으로 이러한 요구는 85%의 규제 및 규정 준수 보호와 15%의 지적 재산 보호입니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-132">In general these needs tend to be 85% regulatory and compliance protection, and 15% intellectual property protection.</span></span> <span data-ttu-id="dcbb2-133">다음은 계획 프로세스에 포함할 역할에 대한 몇 가지 제안 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-133">Here are some suggestions on roles to include in your planning process:</span></span>

- <span data-ttu-id="dcbb2-134">규정 및 규정 준수 책임자</span><span class="sxs-lookup"><span data-stu-id="dcbb2-134">Regulatory and compliance officers</span></span>
- <span data-ttu-id="dcbb2-135">최고 위험 책임자</span><span class="sxs-lookup"><span data-stu-id="dcbb2-135">Chief risk officer</span></span>
- <span data-ttu-id="dcbb2-136">법률 담당자</span><span class="sxs-lookup"><span data-stu-id="dcbb2-136">Legal officers</span></span>
- <span data-ttu-id="dcbb2-137">보안 및 규정 준수 담당자</span><span class="sxs-lookup"><span data-stu-id="dcbb2-137">Security and compliance officers</span></span>
- <span data-ttu-id="dcbb2-138">데이터 항목에 대한 비즈니스 소유자</span><span class="sxs-lookup"><span data-stu-id="dcbb2-138">Business owners for the data items</span></span>
- <span data-ttu-id="dcbb2-139">비즈니스 사용자</span><span class="sxs-lookup"><span data-stu-id="dcbb2-139">Business users</span></span>
- <span data-ttu-id="dcbb2-140">IT</span><span class="sxs-lookup"><span data-stu-id="dcbb2-140">IT</span></span>

### <a name="describe-the-categories-of-sensitive-information-to-protect"></a><span data-ttu-id="dcbb2-141">보호할 중요한 정보의 범주 설명</span><span class="sxs-lookup"><span data-stu-id="dcbb2-141">Describe the categories of sensitive information to protect</span></span>

<span data-ttu-id="dcbb2-142">그러면 이해 관계자는 보호할 중요한 정보의 범주와 사용되는 비즈니스 프로세스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-142">The stakeholders then describe the categories of sensitive information to be protected and the business process that they're used in.</span></span> <span data-ttu-id="dcbb2-143">예를 들어 Microsoft 365 DLP는 다음 범주를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-143">For example, Microsoft 365 DLP defines these categories:</span></span>

- <span data-ttu-id="dcbb2-144">금융</span><span class="sxs-lookup"><span data-stu-id="dcbb2-144">Financial</span></span> 
- <span data-ttu-id="dcbb2-145">의료 및 의료 정보</span><span class="sxs-lookup"><span data-stu-id="dcbb2-145">Medical and health information</span></span>
- <span data-ttu-id="dcbb2-146">개인 정보</span><span class="sxs-lookup"><span data-stu-id="dcbb2-146">Privacy</span></span>
- <span data-ttu-id="dcbb2-147">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="dcbb2-147">Custom</span></span>

<span data-ttu-id="dcbb2-148">관련자는 중요한 정보를 "데이터 프로세서이기 때문에 데이터 주체 정보 및 재무 정보에 대한 개인 정보 보호를 구현해야 합니다."로 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-148">The stakeholders might identify the sensitive information as "We are a data processor, so we have to implement privacy protections on data subject information and financial information".</span></span>

 
  <!-- The business process is important as it informs the ‘data at rest’, ‘data in transit’, ‘data in use’ aspect of DLP planning and who should be sharing the items and who should not.-->

### <a name="set-goals-and-strategy"></a><span data-ttu-id="dcbb2-149">목표 및 전략 설정</span><span class="sxs-lookup"><span data-stu-id="dcbb2-149">Set goals and strategy</span></span>

<span data-ttu-id="dcbb2-150">이해 관계자를 식별하고 보호가 필요한 중요한 정보 및 사용 위치를 파악한 후 이해 관계자는 보호 목표를 설정할 수 있으며 IT는 구현 계획을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-150">Once you have identified your stakeholders and you know which sensitive information needs protection and where it's used, the stakeholders can set their protection goals and IT can develop an implementation plan.</span></span> 


 <!--
### Discovery
 for the locations (DLP workloads) of these types of items.  (mapping DLP locations and data at rest, data in transit, data in use)

### IT can start coding test policies
start small and always in test mode. Note that DLP policies can feed into insider risk.

### Business process owners help with tuning
 false positive/false negative results and fitting DLP into their business processes.

-->

### <a name="set-implementation-plan"></a><span data-ttu-id="dcbb2-151">구현 계획 설정</span><span class="sxs-lookup"><span data-stu-id="dcbb2-151">Set implementation plan</span></span>

<span data-ttu-id="dcbb2-152">구현 계획에는 다음이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-152">Your implementation plan should include:</span></span>

- <span data-ttu-id="dcbb2-153">시작 상태 및 원하는 종료 상태와 단계 중 하나에서 다른 상태로의 단계 매핑</span><span class="sxs-lookup"><span data-stu-id="dcbb2-153">Mapping out your starting state and desired end state and the steps to get from one to the other</span></span>
- <span data-ttu-id="dcbb2-154">중요한 항목 검색을 해결할 방법</span><span class="sxs-lookup"><span data-stu-id="dcbb2-154">how you will address discovery of sensitive items</span></span>
- <span data-ttu-id="dcbb2-155">정책 계획 및 정책 계획이 구현될 순서</span><span class="sxs-lookup"><span data-stu-id="dcbb2-155">policy planning and the order that they will be implemented</span></span>
- <span data-ttu-id="dcbb2-156">모든 선행 요구 문제를 해결할 방법</span><span class="sxs-lookup"><span data-stu-id="dcbb2-156">how you will address any prerequisites</span></span>
- <span data-ttu-id="dcbb2-157">적용으로 이동하기 전에 정책을 먼저 테스트하는 방법 계획</span><span class="sxs-lookup"><span data-stu-id="dcbb2-157">planning on how policies will first be tested before moving to enforcement</span></span>
- <span data-ttu-id="dcbb2-158">최종 사용자를 교육하는 방법</span><span class="sxs-lookup"><span data-stu-id="dcbb2-158">how you will train your end users</span></span>
- <span data-ttu-id="dcbb2-159">정책을 테스트하고 조정하는 방법</span><span class="sxs-lookup"><span data-stu-id="dcbb2-159">how you will test and tune your policies</span></span>
- <span data-ttu-id="dcbb2-160">변화하는 규제, 법률, 산업 표준 또는 지적 재산 보호 및 비즈니스 요구에 따라 데이터 손실 방지 전략을 검토하고 업데이트하는 방법</span><span class="sxs-lookup"><span data-stu-id="dcbb2-160">how you will review and update your data loss prevention strategy based on changing regulatory, legal, industry standard or intellectual property protection and business needs</span></span>

#### <a name="map-out-path-from-start-to-desired-end-state"></a><span data-ttu-id="dcbb2-161">시작에서 원하는 종료 상태로 경로 매핑</span><span class="sxs-lookup"><span data-stu-id="dcbb2-161">Map out path from start to desired end state</span></span>

<span data-ttu-id="dcbb2-162">조직이 시작 상태부터 원하는 종료 상태로 어떻게 진행할지 문서화하는 것은 관련자와 의사소통하고 프로젝트 범위를 설정하는 데 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-162">Documenting how your organization is going to get from its starting state to the desired end state is essential to communicating with your stakeholders and setting the project scope.</span></span> <span data-ttu-id="dcbb2-163">다음은 DLP를 배포하는 데 일반적으로 사용되는 단계 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-163">Here is a set of steps that are commonly used to deploy DLP.</span></span> <span data-ttu-id="dcbb2-164">이보다 더 자세한 내용을 원하지만 이를 사용하여 DLP 채택 경로를 틀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-164">You'll want more detail than this, but you can use this to frame your DLP adoption path.</span></span>

![DLP 배포의 일반적인 순서를 보여주는 그래픽](../media/dlp-deployment-planning.png)

#### <a name="sensitive-item-discovery"></a><span data-ttu-id="dcbb2-166">중요한 항목 검색</span><span class="sxs-lookup"><span data-stu-id="dcbb2-166">Sensitive item discovery</span></span>

<span data-ttu-id="dcbb2-167">여러 가지 방법으로 개별 중요한 항목의 위치와 위치를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-167">There are multiple ways to discover what individual sensitive items are and where they are located.</span></span> <span data-ttu-id="dcbb2-168">민감도 레이블이 이미 배포되어 있을 수도 있으며, 항목을 검색하고 감사하는 모든 위치에 광범위한 DLP 정책을 배포하기로 결정한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-168">You may have sensitivity labels already deployed or you may have decided to deploy a broad DLP policy to all locations that only discovers and audits items.</span></span> <span data-ttu-id="dcbb2-169">자세한 내용은 데이터 [알고 를 참조합니다.](information-protection.md#know-your-data)</span><span class="sxs-lookup"><span data-stu-id="dcbb2-169">To learn more, see [Know your data](information-protection.md#know-your-data).</span></span>

#### <a name="policy-planning"></a><span data-ttu-id="dcbb2-170">정책 계획</span><span class="sxs-lookup"><span data-stu-id="dcbb2-170">Policy planning</span></span>

<span data-ttu-id="dcbb2-171">DLP 채택을 시작할 때 이러한 질문을 사용하여 정책 디자인 및 구현 노력에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-171">As you begin your DLP adoption, you can use these questions to focus your policy design and implementation efforts.</span></span>

##### <a name="what-laws-regulations-and-industry-standards-must-your-organization-comply-with"></a><span data-ttu-id="dcbb2-172">조직에서 준수해야 하는 법률, 규정 및 산업 표준은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="dcbb2-172">What laws, regulations and industry standards must your organization comply with?</span></span>

<span data-ttu-id="dcbb2-173">많은 조직이 규정 준수를 위해 DLP를 사용하게 많기 때문에 이 질문에 대한 대답은 DLP 구현을 계획하기 위한 자연스러운 시작 장소입니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-173">Because many organizations come to DLP with the goal of regulatory compliance, answering this question is a natural starting place for planning your DLP implementation.</span></span> <span data-ttu-id="dcbb2-174">그러나 IT 구현자 입장에서는 응답할 위치가 아 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-174">But, as the IT implementer, you're probably not positioned to answer it.</span></span> <span data-ttu-id="dcbb2-175">법률 팀과 비즈니스 임원이 답변해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-175">It needs to be answered by your legal team and business executives.</span></span> 
 
<span data-ttu-id="dcbb2-176">**예제** 조직은 영국의 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-176">**Example** Your organization is subject to U.K.</span></span> <span data-ttu-id="dcbb2-177">재무 규정.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-177">financial regulations.</span></span>


##### <a name="what-sensitive-items-does-your-organization-have-that-must-be-protected-from-leakage"></a><span data-ttu-id="dcbb2-178">조직에서 누출로부터 보호해야 하는 중요한 항목은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="dcbb2-178">What sensitive items does your organization have that must be protected from leakage?</span></span>

<span data-ttu-id="dcbb2-179">조직에서 규정 준수 요구의 관점에서 해당 항목이 어디인지 알고 나면 누출로부터 보호해야 하는 중요한 항목과 이를 보호하기 위해 정책 구현의 우선 순위를 지정하는 방법을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-179">Once your organization knows where it stands in terms of regulatory compliance needs, you'll have some idea of what sensitive items need to be protected from leakage and how you want to prioritize policy implementation to protect them.</span></span> <span data-ttu-id="dcbb2-180">이렇게 하면 가장 적합한 DLP 정책 템플릿을 선택하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-180">This will help you choose the most appropriate DLP policy templates.</span></span> <span data-ttu-id="dcbb2-181">Microsoft 365, 의료 및 건강, 개인 정보 보호를 위해 미리 구성된 DLP 템플릿과 함께 사용할 수 있으며 사용자 지정 템플릿을 사용하여 직접 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-181">Microsoft 365 comes with pre-configured DLP templates for Financial, Medical and health, Privacy, and you can build your own using the Custom template.</span></span> <span data-ttu-id="dcbb2-182">실제 DLP 정책을 디자인하고 만들 때 이 질문에 대한 답변을 알면 올바른 중요한 정보 유형을 선택하는 [데도 도움이 됩니다.](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)</span><span class="sxs-lookup"><span data-stu-id="dcbb2-182">As you design and create your actual DLP policies, knowing the answer to this question will also help you choose the right [sensitive information type](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types).</span></span>

<span data-ttu-id="dcbb2-183">**예제** 빠르게 시작하기 위해 , 및 중요한 정보 유형이 포함된 정책 `U.K. Financial Data` `Credit Card Number` `EU Debit Card Number` `SWIFT Code` 템플릿을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-183">**Example** To get started quickly, you pick the `U.K. Financial Data` policy template, which includes the `Credit Card Number`, `EU Debit Card Number`, and `SWIFT Code` sensitive information types.</span></span> 

##### <a name="where-are-the-sensitive-items-and-what-business-processes-are-they-involved-in"></a><span data-ttu-id="dcbb2-184">중요한 항목은 어디에 있으며 어떤 비즈니스 프로세스가 관련이 있나요?</span><span class="sxs-lookup"><span data-stu-id="dcbb2-184">Where are the sensitive items and what business processes are they involved in?</span></span>

<span data-ttu-id="dcbb2-185">조직에서 중요한 정보를 포함하는 항목은 비즈니스를 하는 과정에서 매일 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-185">The items that contain your organizations sensitive information are used every day in the course of doing business.</span></span> <span data-ttu-id="dcbb2-186">중요한 정보의 인스턴스가 발생할 수 있는 위치와 해당 인스턴스가 사용되는 비즈니스 프로세스를 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-186">You need to know where instances of that sensitive information may occur and what business processes they are used in.</span></span> <span data-ttu-id="dcbb2-187">이렇게 하면 DLP 정책을 적용할 올바른 위치를 선택하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-187">This will help you choose the right locations to apply your DLP policies to.</span></span> <span data-ttu-id="dcbb2-188">Microsoft 365 DLP 정책은 위치에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-188">Microsoft 365 DLP policies are applied to locations:</span></span>

- <span data-ttu-id="dcbb2-189">Exchange 전자 메일</span><span class="sxs-lookup"><span data-stu-id="dcbb2-189">Exchange email</span></span>
- <span data-ttu-id="dcbb2-190">SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="dcbb2-190">SharePoint sites</span></span>
- <span data-ttu-id="dcbb2-191">OneDrive 계정</span><span class="sxs-lookup"><span data-stu-id="dcbb2-191">OneDrive accounts</span></span>
- <span data-ttu-id="dcbb2-192">Teams 채팅 및 채널 메시지</span><span class="sxs-lookup"><span data-stu-id="dcbb2-192">Teams chat and channel messages</span></span>
- <span data-ttu-id="dcbb2-193">Windows 10 장치</span><span class="sxs-lookup"><span data-stu-id="dcbb2-193">Windows 10 Devices</span></span>
- <span data-ttu-id="dcbb2-194">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="dcbb2-194">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="dcbb2-195">사내 리포지토리</span><span class="sxs-lookup"><span data-stu-id="dcbb2-195">On-premises repositories</span></span>

<span data-ttu-id="dcbb2-196">**예제** 조직의 내부 감사자는 신용 카드 번호 집합을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-196">**Example** Your organizations' internal auditors are tracking a set of credit card numbers.</span></span> <span data-ttu-id="dcbb2-197">이러한 스프레드시트는 보안 사이트로 SharePoint 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-197">They keep a spreadsheet of them in a secure SharePoint site.</span></span> <span data-ttu-id="dcbb2-198">일부 직원은 복사본을 만들어 자신의 비즈니스용 OneDrive 저장하며, 이 사이트는 Windows 10 장치와 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-198">Several of the employees make copies and save them to their work OneDrive for Business site, which is synced to their Windows 10 device.</span></span> <span data-ttu-id="dcbb2-199">이 중 한 명은 14명 목록을 전자 메일에 붙여넣고 검토를 위해 외부 감사인에게 보내보는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-199">One of them pastes a list of 14 of them in an email and tries to send it to the outside auditors for review.</span></span> <span data-ttu-id="dcbb2-200">정책을 보안 SharePoint 사이트, 모든 내부 감사자 비즈니스용 OneDrive 계정, Windows 10 장치 및 전자 메일 Exchange 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-200">You'd want to apply the policy to the secure SharePoint site, all the internal auditors OneDrive for Business accounts, their Windows 10 devices, and Exchange email.</span></span>

##### <a name="what-is-your-organizations-tolerance-for-leakage"></a><span data-ttu-id="dcbb2-201">조직에서 누출을 허용할 수 있는 것은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="dcbb2-201">What is your organizations tolerance for leakage?</span></span>

<span data-ttu-id="dcbb2-202">조직의 여러 그룹은 허용되는 중요한 항목 누출 수준과 중요하지 않은 항목에 대해 서로 다른 보기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-202">Different groups in your organization may have different views on what's an acceptable level of sensitive item leakage and what's not.</span></span> <span data-ttu-id="dcbb2-203">누출을 완벽하게 이행하면 비즈니스에 너무 많은 비용이 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-203">Achieving the perfection of zero leakage may come at too high a cost to the business.</span></span>

<span data-ttu-id="dcbb2-204">**예제** 법률 팀과 함께 조직의 보안 그룹은 조직 외부의 모든 사용자와 신용 카드 번호를 공유하지 말아야 한다고 생각하며 누출을 0으로 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-204">**Example** Your organizations' security group, along with the legal team both feel that there should be no sharing of credit card numbers with anyone outside the org and insist on zero leakage.</span></span> <span data-ttu-id="dcbb2-205">그러나 신용 카드 번호 활동에 대한 정기적인 검토의 일부로 내부 감사자는 일부 신용 카드 번호를 타사 감사인과 공유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-205">But, as part of regular review of credit card number activity, the internal auditors must share some credit card numbers with third-party auditors.</span></span> <span data-ttu-id="dcbb2-206">DLP 정책으로는 전화기 외부의 신용 카드 번호 공유를 모두 금지하는 경우 내부 감사관이 추적을 완료하기 위해 업무 프로세스 중단과 비용을 추가하여 중단을 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-206">If your DLP policy prohibits all sharing of credit card numbers outside the org, there will be a significant business process disruption and added cost to mitigate the disruption in order for the internal auditors to complete their tracking.</span></span> <span data-ttu-id="dcbb2-207">이 추가 비용은 임원진에게는 받아들일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-207">This extra cost is unacceptable to the executive leadership.</span></span> <span data-ttu-id="dcbb2-208">이 문제를 해결하기 위해 허용되는 누출 수준을 결정하기 위한 내부 대화가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-208">To resolve this, there needs to be an internal conversation to decide an acceptable level of leakage.</span></span> <span data-ttu-id="dcbb2-209">정책이 결정된 후 특정 개인이 정보를 공유하기 위한 예외를 제공하거나 감사 전용 모드에서 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-209">Once that is decided the policy can provide exceptions for certain individuals to share the information or it can be applied in audit only mode.</span></span>

#### <a name="planning-for-prerequisites"></a><span data-ttu-id="dcbb2-210">선행 준비 계획</span><span class="sxs-lookup"><span data-stu-id="dcbb2-210">Planning for prerequisites</span></span>

<span data-ttu-id="dcbb2-211">일부 DLP 위치를 모니터링하려면 먼저 충족해야 하는 선행 조건이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-211">Before you can monitor some DLP locations, there are prerequisites that must be met.</span></span> <span data-ttu-id="dcbb2-212">다음의 **시작하기 전에** 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-212">See the **Before you begin** sections of:</span></span>

- [<span data-ttu-id="dcbb2-213">데이터 손실 방지 온-프레미스 스캐너로 시작하기(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="dcbb2-213">Get started with the data loss prevention on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-get-started.md#before-you-begin)
- [<span data-ttu-id="dcbb2-214">끝점 데이터 손실 방지 시작</span><span class="sxs-lookup"><span data-stu-id="dcbb2-214">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md#before-you-begin)
- [<span data-ttu-id="dcbb2-215">Microsoft 규정 준수 확장 시작(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="dcbb2-215">Get started with the Microsoft compliance extension (preview)</span></span>](dlp-chrome-get-started.md#before-you-begin)
- [<span data-ttu-id="dcbb2-216">Microsoft가 아닌 클라우드 앱에 데이터 손실 방지 정책 사용(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="dcbb2-216">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>](dlp-use-policies-non-microsoft-cloud-apps.md#before-you-begin)

#### <a name="policy-deployment"></a><span data-ttu-id="dcbb2-217">정책 배포</span><span class="sxs-lookup"><span data-stu-id="dcbb2-217">Policy deployment</span></span>

<span data-ttu-id="dcbb2-218">DLP 정책을 만든 후에는 완전히 적용하기 전에 서서히 롤아웃하면서 영향을 평가하고 효율성을 테스트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-218">When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them.</span></span> <span data-ttu-id="dcbb2-219">예를 들어 새 DLP 정책으로 수천 개의 문서에 대한 액세스를 의도하지 않은 것으로 차단하거나 기존 비즈니스 프로세스를 중단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-219">For example, you don't want a new DLP policy to unintentionally block access to thousands of documents or to break an existing business process.</span></span>
  
<span data-ttu-id="dcbb2-220">영향이 클 수 있는 DLP 정책을 생성하는 경우에는 다음과 같은 순서를 따르는 것이 좋습니다:</span><span class="sxs-lookup"><span data-stu-id="dcbb2-220">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
  
1. <span data-ttu-id="dcbb2-221">**정책 팁이 없는 테스트 모드에서 시작** 하고 DLP 보고서 및 모든 사고 보고서를 사용하여 영향을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-221">**Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact.</span></span> <span data-ttu-id="dcbb2-222">DLP 보고서를 사용하여 정책 일치의 횟수, 위치, 유형 및 심각도를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-222">You can use DLP reports to view the number, location, type, and severity of policy matches.</span></span> <span data-ttu-id="dcbb2-223">결과에 따라 필요한 경우 정책을 미세 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-223">Based on the results, you can fine-tune the policies as needed.</span></span> <span data-ttu-id="dcbb2-224">테스트 모드에서 DLP 정책은 조직에서 작업하는 사용자의 생산성에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-224">In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> <span data-ttu-id="dcbb2-225">또한 이 스테이지를 사용하여 DLP 이벤트 검토 및 문제 해결을 위한 워크플로를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-225">Also, use this stage to test out your workflow for DLP event review and issue remediation.</span></span>
    
2. <span data-ttu-id="dcbb2-226">**알림 및** 정책 정책을 팁 모드로 전환하여 사용자에게 규정 준수 정책을 교육하고 적용될 정책을 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-226">**Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the policies that are going to be applied.</span></span> <span data-ttu-id="dcbb2-227">정책 팁에서 정책에 대한 자세한 정보를 제공하는 조직 정책 페이지에 대한 링크를 제공하는 것이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-227">It's useful to have a link to an organization policy page that provides more details about the policy in the policy tip.</span></span> <span data-ttu-id="dcbb2-228">이 단계에서 정책을 추가로 구체화할 수 있도록 사용자에게 가짓 긍정 보고를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-228">At this stage, you can also ask users to report false positives so that you can further refine the policies.</span></span> <span data-ttu-id="dcbb2-229">정책 응용 프로그램의 결과가 관련자의 생각과 일치할 수 있다는 확신이 있는 경우 이 단계로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-229">Move to this stage once you have confidence that the results of policy application match what they stakeholders had in mind.</span></span> 
    
3. <span data-ttu-id="dcbb2-230">규칙에서 작업이 적용되고 콘텐츠가 보호되도록 **정책에 대한 전체 적용을 시작합니다**.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-230">**Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected.</span></span> <span data-ttu-id="dcbb2-231">DLP 보고서 및 모든 사고 보고서나 알림을 계속 모니터링하여 결과가 의도한 대로 나타나는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-231">Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 

    ![테스트 모드를 사용하고 정책을 설정하기 위한 옵션](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    <span data-ttu-id="dcbb2-233">언제든지 DLP 정책을 종료할 수 있습니다. 이 경우 정책의 모든 규칙들이 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-233">You can turn off a DLP policy at any time, which affects all rules in the policy.</span></span> <span data-ttu-id="dcbb2-234">하지만 규칙 편집기에서 상태를 전환하여 각 규칙을 개별적으로 종료할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-234">However, each rule can also be turned off individually by toggling its status in the rule editor.</span></span>

    ![정책에서 규칙을 종료하기 위한 옵션](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    <span data-ttu-id="dcbb2-236">정책에서 여러 규칙의 우선 순위를 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-236">You can also change the priority of multiple rules in a policy.</span></span> <span data-ttu-id="dcbb2-237">이를 위해 편집할 정책을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-237">To do that, open a policy for editing.</span></span> <span data-ttu-id="dcbb2-238">규칙의 행에서 줄임표(**...**)를 선택하고 **아래로 이동** 또는 **마지막 규칙 가져오기** 와 같은 옵션을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-238">In a row for a rule, choose the ellipses (**...**), and then choose an option, such as **Move down** or **Bring to last**.</span></span>

    ![규칙 우선 순위를 설정하십시오.](../media/dlp-set-rule-priority.png)

#### <a name="end-user-training"></a><span data-ttu-id="dcbb2-240">최종 사용자 교육</span><span class="sxs-lookup"><span data-stu-id="dcbb2-240">End-user training</span></span>

<span data-ttu-id="dcbb2-241">DLP 정책이 트리거되면 전자 메일 알림을 보내도록 정책을 구성하고 관리자 및 최종 사용자에게 [DLP](use-notifications-and-policy-tips.md#send-email-notifications-and-show-policy-tips-for-dlp-policies) 정책에 대한 정책 팁을 표시하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-241">When a DLP policy is triggered, you can configure your policies to [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md#send-email-notifications-and-show-policy-tips-for-dlp-policies) to admins and end users.</span></span> <span data-ttu-id="dcbb2-242">정책이 여전히 테스트 모드에 있는 동안 차단 작업을 적용하기 전에 정책 팁은 중요한 항목에 대한 위험한 동작에 대한 인식을 높이고 사용자에게 향후 이러한 동작을 방지할 수 있도록 교육하는 유용한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-242">While your policies are still in test mode and before they are set to enforce a blocking action, policy tips are useful ways to raise awareness of risky behaviors on sensitive items and train users to avoid those behaviors in the future.</span></span>  

#### <a name="review-dlp-requirements-and-update-strategy"></a><span data-ttu-id="dcbb2-243">DLP 요구 사항 및 업데이트 전략 검토</span><span class="sxs-lookup"><span data-stu-id="dcbb2-243">Review DLP requirements and update strategy</span></span>

<span data-ttu-id="dcbb2-244">조직이 적용하는 규정, 법률 및 산업 표준은 시간이 지날 때 변경될 예정이고 DLP에 대한 비즈니스 목표도 변합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-244">The regulations, laws, and industry standards that your organization is subject to will change over time and your business goals for DLP will too.</span></span> <span data-ttu-id="dcbb2-245">조직이 규정을 준수하고 DLP 구현이 비즈니스 요구를 계속 충족하도록 이러한 모든 영역에 대한 정기적인 검토를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-245">Be sure to include regular reviews of all these areas so that your organization stays in compliance and your DLP implementation continues to meet your business needs.</span></span>

## <a name="approaches-to-deployment"></a><span data-ttu-id="dcbb2-246">배포 방법</span><span class="sxs-lookup"><span data-stu-id="dcbb2-246">Approaches to deployment</span></span>

|<span data-ttu-id="dcbb2-247">고객 비즈니스 요구 설명</span><span class="sxs-lookup"><span data-stu-id="dcbb2-247">Customer business needs description</span></span>  | <span data-ttu-id="dcbb2-248">접근 방식</span><span class="sxs-lookup"><span data-stu-id="dcbb2-248">approach</span></span>  |
|---------|---------|
|<span data-ttu-id="dcbb2-249">**Contoso Bank는** 높은 규제 대상 산업에 있으며 다양한 위치에 다양한 유형의 중요한 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-249">**Contoso Bank** is in a highly regulated industry and has  many different types of sensitive items in many different locations.</span></span> </br> <span data-ttu-id="dcbb2-250">- 우선 순위가 가장 높은 중요한 정보 유형을 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-250">- knows which types of sensitive information are top priority.</span></span> </br> <span data-ttu-id="dcbb2-251">- 정책을 롤아웃할 때 비즈니스 중단을 최소화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-251">- must minimize business disruption as policies are rolled out.</span></span> </br> <span data-ttu-id="dcbb2-252">- IT 리소스가 있으며 계획, 디자인 배포에 도움이 되는 전문가를 고용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-252">-  has IT resources and can hire experts to help plan, design deploy</span></span> </br> <span data-ttu-id="dcbb2-253">- Microsoft와 프리미어 지원 계약을 체결</span><span class="sxs-lookup"><span data-stu-id="dcbb2-253">- has a premier support contract with Microsoft</span></span>| <span data-ttu-id="dcbb2-254">- 시간을 내어 준수해야 하는 규정과 규정 준수 방법을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-254">- Take the time to understand what regulations they must comply with and how they are going to comply.</span></span> </br> <span data-ttu-id="dcbb2-255">-정보 보호 스택의 더 나은 함께 값을 이해하기 Microsoft 365 시간을 내어 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-255">-Take the time to understand the better together value of the Microsoft 365 Information Protection stack</span></span> </br> <span data-ttu-id="dcbb2-256">- 우선 순위가 높은 항목에 대한 민감도 레이블 지정 체계 개발 및 적용</span><span class="sxs-lookup"><span data-stu-id="dcbb2-256">- Develop sensitivity labeling scheme for prioritized items and apply</span></span> </br> <span data-ttu-id="dcbb2-257">- 비즈니스 프로세스 소유자 참여</span><span class="sxs-lookup"><span data-stu-id="dcbb2-257">- Involve business process owners</span></span> </br><span data-ttu-id="dcbb2-258">- 디자인/코드 정책, 테스트 모드로 배포, 사용자 교육</span><span class="sxs-lookup"><span data-stu-id="dcbb2-258">- Design/code policies, deploy in test mode, train users</span></span> </br><span data-ttu-id="dcbb2-259">- 반복</span><span class="sxs-lookup"><span data-stu-id="dcbb2-259">- repeat</span></span>|
|<span data-ttu-id="dcbb2-260">**TailSpin Toys는** 현재 위치나 위치를 모르는 리소스 깊이가 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-260">**TailSpin Toys** doesn’t know what they have or where it is, and have little to no resource depth.</span></span> <span data-ttu-id="dcbb2-261">광범위한 Teams, 비즈니스용 OneDrive Exchange 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-261">They use Teams, OneDrive for Business and Exchange extensively.</span></span>     |<span data-ttu-id="dcbb2-262">- 우선 순위가 지정한 위치에 대한 간단한 정책으로 시작</span><span class="sxs-lookup"><span data-stu-id="dcbb2-262">- Start with simple policies on the prioritized locations.</span></span> </br><span data-ttu-id="dcbb2-263">- 식별된 것을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-263">- Monitor what gets identified</span></span> </br><span data-ttu-id="dcbb2-264">- 그에 따라 민감도 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="dcbb2-264">- Apply sensitivity labels accordingly</span></span> </br><span data-ttu-id="dcbb2-265">- 정책 구체화, 사용자 교육</span><span class="sxs-lookup"><span data-stu-id="dcbb2-265">- Refine policies, train users</span></span>       |
|<span data-ttu-id="dcbb2-266">**Fabrikam은** 소규모 스타트업으로, 지적 재산을 보호하려는 경우 빠르게 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-266">**Fabrikam** is a small startup and wants to protect its intellectual property, and must move quickly.</span></span> <span data-ttu-id="dcbb2-267">일부 자원은 전담하지만 외부 전문가를 고용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-267">They are willing to dedicate some resources, but can't afford to hire outside experts.</span></span> </br><span data-ttu-id="dcbb2-268">- 중요한 항목이 모두 Microsoft 365 비즈니스용 OneDrive/SharePoint</span><span class="sxs-lookup"><span data-stu-id="dcbb2-268">- Sensitive items are all in Microsoft 365 OneDrive for Business/SharePoint</span></span> </br><span data-ttu-id="dcbb2-269">- 사용자 및 비즈니스용 OneDrive SharePoint, 직원/섀도 IT는 DropBox 및 Google drive를 사용하여 항목을 공유/저장합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbb2-269">- Adoption of OneDrive for Business and SharePoint is slow, employees/shadow IT use DropBox and Google drive to share/store items</span></span> </br><span data-ttu-id="dcbb2-270">- 직원의 데이터 보호 분야보다 작업 속도 향상</span><span class="sxs-lookup"><span data-stu-id="dcbb2-270">- Employees value speed of work over data protection discipline</span></span> </br><span data-ttu-id="dcbb2-271">- 고객 지원 및 신규 직원 18명 모두 Windows 10 구입</span><span class="sxs-lookup"><span data-stu-id="dcbb2-271">- Customer splurged and bought all 18 employees new Windows 10 devices</span></span>     |<span data-ttu-id="dcbb2-272">- 기본 DLP 정책을 Teams</span><span class="sxs-lookup"><span data-stu-id="dcbb2-272">- Take advantage of the default DLP policy in Teams</span></span> </br><span data-ttu-id="dcbb2-273">- 항목의 기본 설정으로 SharePoint 사용</span><span class="sxs-lookup"><span data-stu-id="dcbb2-273">- Use restricted by default setting for SharePoint items</span></span> </br><span data-ttu-id="dcbb2-274">- 외부 공유를 방지하는 정책 배포</span><span class="sxs-lookup"><span data-stu-id="dcbb2-274">- Deploy policies that prevent external sharing</span></span> </br><span data-ttu-id="dcbb2-275">- 우선 순위가 지정한 위치에 정책 배포</span><span class="sxs-lookup"><span data-stu-id="dcbb2-275">- Deploy policies to prioritized locations</span></span> </br><span data-ttu-id="dcbb2-276">- 디바이스에 정책 Windows 10 배포</span><span class="sxs-lookup"><span data-stu-id="dcbb2-276">- Deploy policies to Windows 10 devices</span></span> </br><span data-ttu-id="dcbb2-277">- 비보안 클라우드 저장소로의 비즈니스용 OneDrive 차단</span><span class="sxs-lookup"><span data-stu-id="dcbb2-277">- Block uploads to non-OneDrive for Business cloud storage</span></span>      |

<!--

## Planning for workloads

### Exchange

### SharePoint

### OneDrive for Business

### Teams

### Windows 10 Devices

### Microsoft Cloud App Security (MCAS)

### On-premises Scanner
-->

## <a name="see-also"></a><span data-ttu-id="dcbb2-278">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dcbb2-278">See also</span></span>
- [<span data-ttu-id="dcbb2-279">데이터 손실 방지에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="dcbb2-279">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
