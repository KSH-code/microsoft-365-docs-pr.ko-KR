---
title: 통신 준수 계획
description: 조직의 통신 준수 사용 계획에 대해 설명 합니다.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 214c5376d4c074525253707e181eee69cefff85e
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44045857"
---
# <a name="plan-for-communication-compliance"></a><span data-ttu-id="39253-103">통신 준수 계획</span><span class="sxs-lookup"><span data-stu-id="39253-103">Plan for communication compliance</span></span>

<span data-ttu-id="39253-104">조직의 [통신 준수](communication-compliance.md) 를 시작 하기 전에 정보 기술 및 준수 관리 팀에서 검토 해야 하는 중요 한 계획 작업 및 고려 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39253-104">Before getting started with [communication compliance](communication-compliance.md) in your organization, there are important planning activities and considerations that should be reviewed by your information technology and compliance management teams.</span></span> <span data-ttu-id="39253-105">다음 영역에서 배포를 철저히 이해 하 고 계획 하는 것은 통신 준수 기능의 구현과 사용이 원활 하 게 진행 되 고 솔루션에 대 한 모범 사례와 부합 되도록 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39253-105">Thoroughly understanding and planning for deployment in the following areas will help ensure that your implementation and use of communication compliance features goes smoothly and is aligned with the best practices for the solution.</span></span>

## <a name="work-with-stakeholders-in-your-organization"></a><span data-ttu-id="39253-106">조직의 관련자에 대 한 작업</span><span class="sxs-lookup"><span data-stu-id="39253-106">Work with stakeholders in your organization</span></span>

<span data-ttu-id="39253-107">조직에서 통신 준수 알림에 대 한 작업을 수행 하기 위해 공동 작업을 수행할 수 있는 적절 한 관련자를 파악 합니다.</span><span class="sxs-lookup"><span data-stu-id="39253-107">Identify the appropriate stakeholders in your organization to collaborate for taking actions on communication compliance alerts.</span></span> <span data-ttu-id="39253-108">초기 계획에 포함 해야 하는 몇 가지 권장 되는 이해 관계자와 종단 간 [통신 규정 준수 워크플로](communication-compliance.md#workflow) 는 다음과 같은 조직 영역의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="39253-108">Some recommended stakeholders to consider including in initial planning and the end-to-end [communication compliance workflow](communication-compliance.md#workflow) are people from the following areas of your organization:</span></span>

- <span data-ttu-id="39253-109">정보 기술</span><span class="sxs-lookup"><span data-stu-id="39253-109">Information technology</span></span>
- <span data-ttu-id="39253-110">규정 준수</span><span class="sxs-lookup"><span data-stu-id="39253-110">Compliance</span></span>
- <span data-ttu-id="39253-111">개인 정보</span><span class="sxs-lookup"><span data-stu-id="39253-111">Privacy</span></span>
- <span data-ttu-id="39253-112">보안</span><span class="sxs-lookup"><span data-stu-id="39253-112">Security</span></span>
- <span data-ttu-id="39253-113">인사부</span><span class="sxs-lookup"><span data-stu-id="39253-113">Human resources</span></span>
- <span data-ttu-id="39253-114">법무</span><span class="sxs-lookup"><span data-stu-id="39253-114">Legal</span></span>

## <a name="plan-for-the-investigation-and-remediation-workflow"></a><span data-ttu-id="39253-115">조사 및 업데이트 관리 워크플로 계획</span><span class="sxs-lookup"><span data-stu-id="39253-115">Plan for the investigation and remediation workflow</span></span>

<span data-ttu-id="39253-116">[Microsoft 365 준수 센터](https://compliance.microsoft.com/)에서 일반 흐름에 대 한 경고를 모니터링 하 고 검토 하려면 전용 검토자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39253-116">Select dedicated reviewers to monitor and review the alerts on a regular cadence in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="39253-117">**관리 검토 관리자**, **사례 관리**, **준수 관리자**및 **검토** 역할을 사용 하 여 검토자에 게 사용 권한을 사용 하도록 설정 하려면 [새 역할 그룹을 만들어야](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) 합니다.</span><span class="sxs-lookup"><span data-stu-id="39253-117">Remember, you’ll need to [create a new role group](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) to enable permissions for reviewers with the **Supervisory Review Administrator**, **Case Management**, **Compliance Administrator**, and **Review** roles to investigate and remediate messages with policy matches.</span></span>

## <a name="plan-for-policies"></a><span data-ttu-id="39253-118">정책 계획</span><span class="sxs-lookup"><span data-stu-id="39253-118">Plan for policies</span></span>

<span data-ttu-id="39253-119">원하지 않는 언어, 중요 한 정보 및 규정 준수를 위해 [미리 정의 된 서식 파일](communication-compliance-feature-reference.md#policy-templates) 을 사용 하 여 쉽고 빠르게 통신 규정 준수 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39253-119">Creating communication compliance policies is quick and easy with the [pre-defined templates](communication-compliance-feature-reference.md#policy-templates) for offensive language, sensitive information, and regulatory compliance.</span></span> <span data-ttu-id="39253-120">사용자 지정 통신 준수 정책을 사용 하면 조직 및 요구 사항과 관련 된 문제를 유연 하 게 검색 하 고 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39253-120">Custom communication compliance policies allow the flexibility for detecting and investigation issues specific to your organization and requirements.</span></span>

<span data-ttu-id="39253-121">통신 준수 정책을 계획할 때는 다음을 고려 하십시오.</span><span class="sxs-lookup"><span data-stu-id="39253-121">When planning for communication compliance policies, consider the following:</span></span>

- <span data-ttu-id="39253-122">조직의 모든 사용자를 통신 준수 정책에 대 한 범위 내로 추가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="39253-122">Consider adding all users in your organization as in-scope for your communication compliance policies.</span></span> <span data-ttu-id="39253-123">개별 정책의 범위 내에서 특정 사용자를 확인 하는 것이 유용한 경우도 있지만 대부분의 조직에는 harassment 또는 판별 검색에 최적화 된 통신 준수 정책의 모든 사용자가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39253-123">Identifying specific users as in-scope for individual policies are useful in some circumstances, however most organizations should include all users in communication compliance policies optimized for harassment or discrimination detection.</span></span>
- <span data-ttu-id="39253-124">설정을 단순화 하려면 통신을 검토 해야 하는 사용자를 위해 그룹을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="39253-124">To simplify your setup, consider creating groups for people who need their communications reviewed.</span></span> <span data-ttu-id="39253-125">그룹을 사용 하는 경우 여러 개 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39253-125">If you're using groups; you might need several.</span></span> <span data-ttu-id="39253-126">예를 들어 서로 다른 두 그룹의 통신을 검색 하려는 경우 또는 감독 되지 않는 그룹을 지정 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="39253-126">For example, if you want to scan communications between two distinct groups of people, or if you want to specify a group that isn't supervised.</span></span>
- <span data-ttu-id="39253-127">검토할 통신 비율을 100%로 구성 하 여 정책에서 조직의 통신에 대 한 모든 문제를 포착 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="39253-127">Configure the percentage of communications to review at 100% to ensure that policies are catching all issues of concern in communications for your organization.</span></span>
- <span data-ttu-id="39253-128">Microsoft 365 조직의 사서함으로 가져온 데이터를 타사 [원본의](communication-compliance-feature-reference.md#supported-communication-types) 통신을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39253-128">You can scan communications from [third-party sources](communication-compliance-feature-reference.md#supported-communication-types) for data imported into mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="39253-129">이러한 플랫폼의 통신 검토를 포함 하려면 통신 정책에 따라 메시지 회의 정책 조건을 모니터링 하기 전에 이러한 서비스에 대 한 커넥터를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39253-129">To include review of communications in these platforms, you’ll need to configure a connector to these services before messages meeting policy conditions are monitored by communication policy.</span></span>
- <span data-ttu-id="39253-130">사용자 지정 통신 준수 정책에서는 정책이 영어가 아닌 다른 모니터링 언어를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39253-130">Policies can support monitoring languages other than English in custom communication compliance policies.</span></span> <span data-ttu-id="39253-131">선택한 언어로 공격적인 단어의 [사용자 지정 키워드 사전을](communication-compliance-feature-reference.md#custom-keyword-dictionaries) 작성 하거나 Microsoft 365에서 [trainable 분류자](classifier-getting-started-with.md) 를 사용 하 여 고유한 컴퓨터 학습 모델을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="39253-131">Build a [custom keyword dictionary](communication-compliance-feature-reference.md#custom-keyword-dictionaries) of offensive words in the language of your choice or build your own machine-learning model using [trainable classifiers](classifier-getting-started-with.md) in Microsoft 365.</span></span>
- <span data-ttu-id="39253-132">모든 조직에는 서로 다른 통신 표준 및 정책 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39253-132">All organizations have different communication standards and policy needs.</span></span> <span data-ttu-id="39253-133">통신 준수 [정책 조건을](communication-compliance-feature-reference.md#conditional-settings) 사용 하 여 특정 키워드를 모니터링 하거나, [사용자 지정 중요 한 정보 유형을](create-a-custom-sensitive-information-type.md)사용 하 여 특정 유형의 정보를 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="39253-133">Monitor for specific keywords using communication compliance [policy conditions](communication-compliance-feature-reference.md#conditional-settings) or monitor for specific types of information with [custom sensitive information types](create-a-custom-sensitive-information-type.md).</span></span>

## <a name="ready-to-get-started"></a><span data-ttu-id="39253-134">시작할 준비가 되셨습니까?</span><span class="sxs-lookup"><span data-stu-id="39253-134">Ready to get started?</span></span>

<span data-ttu-id="39253-135">Microsoft 365 조 직에 대 한 통신 준수를 구성 하려면 microsoft [365에 대 한 통신 준수 구성](communication-compliance-configure.md) 또는 [Contoso의 사례 연구](communication-compliance-case-study.md) 를 확인 하거나 Microsoft 팀, Exchange Online 및 Yammer 통신에서 비속어를 모니터링 하기 위한 통신 준수 정책을 빠르게 구성 하는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="39253-135">To configure communication compliance for your Microsoft 365 organization, see [Configure communication compliance for Microsoft 365](communication-compliance-configure.md) or check out the [case study for Contoso](communication-compliance-case-study.md) and how they quickly configured a communication compliance policy to monitor for offensive language in Microsoft Teams, Exchange Online, and Yammer communications.</span></span>
