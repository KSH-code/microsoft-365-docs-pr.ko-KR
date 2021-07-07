---
title: Microsoft Viva 항목 평가판 실행
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: ''
search.appverid: ''
localization_priority: Normal
description: 조직에서 Microsoft Viva 항목에 대한 시험 파일럿 프로그램을 계획하고 실행하는 방법을 학습합니다.
ms.openlocfilehash: 128e82e7664a76baa55d37e983319c9f344624fd
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327144"
---
# <a name="run-a-trial-of-microsoft-viva-topics"></a><span data-ttu-id="d198e-103">Microsoft Viva 항목 평가판 실행</span><span class="sxs-lookup"><span data-stu-id="d198e-103">Run a trial of Microsoft Viva Topics</span></span>

<span data-ttu-id="d198e-104">이 문서에서는 Viva 항목을 조직에 배포하기 위해 시험 파일럿 프로그램을 설정하고 실행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-104">This article describes how to set up and run a trial pilot program to deploy Viva Topics to your organization.</span></span> <span data-ttu-id="d198e-105">또한 이 문서에서는 평가판에 대한 모범 사례를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-105">This article also recommends best practices for the trial.</span></span>

## <a name="sign-up-for-a-trial"></a><span data-ttu-id="d198e-106">평가판 등록</span><span class="sxs-lookup"><span data-stu-id="d198e-106">Sign up for a trial</span></span>

<span data-ttu-id="d198e-107">평가판은 다음 소스 중 하나에서 공개적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-107">Trials are publicly available from one of the following sources.</span></span> <span data-ttu-id="d198e-108">이러한 평가판은 25명이 30일 동안 Viva 항목에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-108">These trials offer 25 users access to Viva Topics for 30 days.</span></span>

- <span data-ttu-id="d198e-109">[Viva 항목 제품 페이지](https://www.microsoft.com/microsoft-viva/topics?activetab=pivot:overviewtab)</span><span class="sxs-lookup"><span data-stu-id="d198e-109">The [Viva Topics product page](https://www.microsoft.com/microsoft-viva/topics?activetab=pivot:overviewtab)</span></span>

- <span data-ttu-id="d198e-110">Microsoft 365 관리 센터 [](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="d198e-110">The [Microsoft 365 admin center](https://admin.microsoft.com)</span></span>
    1.  <span data-ttu-id="d198e-111">[Microsoft 365 관리 센터](https://admin.microsoft.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-111">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
    2.  <span data-ttu-id="d198e-112">청구 **구매**  >  **서비스로 이동**</span><span class="sxs-lookup"><span data-stu-id="d198e-112">Go to **Billing** > **Purchase Services**.</span></span>
    3.  <span data-ttu-id="d198e-113">아래로 스크롤하여 **추가 기능** 섹션으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-113">Scroll down to the **Add-Ons** section.</span></span>
    4.  <span data-ttu-id="d198e-114">항목 **환경 타일에서** 세부 **정보를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d198e-114">On the **Topic Experiences** tile, select **Details**.</span></span>
    5.  <span data-ttu-id="d198e-115">**사용 가능한 평가판** 을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="d198e-115">Select **Get free trial**.</span></span>
    6.  <span data-ttu-id="d198e-116">나머지 마법사 단계에 따라 평가판을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-116">Follow the remaining wizard steps to confirm the trial.</span></span>

<span data-ttu-id="d198e-117">평가판을 활성화하려면 Microsoft 365 관리자 또는 대금 청구 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-117">You must be a Microsoft 365 global administrator or billing administrator to activate a trial.</span></span>

> [!NOTE]
> <span data-ttu-id="d198e-118">공개 평가판은 각 테넌트에 대해 한 번만 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-118">Public trials can only be added once for each Microsoft 365 tenant.</span></span>

### <a name="who-should-be-involved-in-a-trial"></a><span data-ttu-id="d198e-119">Who 평가판에 참여해야 하는지</span><span class="sxs-lookup"><span data-stu-id="d198e-119">Who should be involved in a trial</span></span>

|<span data-ttu-id="d198e-120">역할</span><span class="sxs-lookup"><span data-stu-id="d198e-120">Role</span></span>  |<span data-ttu-id="d198e-121">활동</span><span class="sxs-lookup"><span data-stu-id="d198e-121">Activity</span></span>  |
|---------|---------|
|<span data-ttu-id="d198e-122">Microsoft 365 관리자 또는 대금 청구 관리자</span><span class="sxs-lookup"><span data-stu-id="d198e-122">Microsoft 365 global admin or billing admin</span></span>  |   <span data-ttu-id="d198e-123">평가판 활성화 및 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="d198e-123">Activate the trial and assign licenses</span></span>      |
|<span data-ttu-id="d198e-124">Microsoft 365 관리자 또는 SharePoint 관리자</span><span class="sxs-lookup"><span data-stu-id="d198e-124">Microsoft 365 global admin or SharePoint admin</span></span>    |       <span data-ttu-id="d198e-125">Viva 항목 구성 및 항목 센터 만들기</span><span class="sxs-lookup"><span data-stu-id="d198e-125">Configure  Viva Topics and create topic centers</span></span>  |
|<span data-ttu-id="d198e-126">비즈니스 사용자</span><span class="sxs-lookup"><span data-stu-id="d198e-126">Business user</span></span>     |   <span data-ttu-id="d198e-127">기술 관리자, 주제 참가자 및 소비자 역할 주제 수행</span><span class="sxs-lookup"><span data-stu-id="d198e-127">Perform knowledge manager, topic contributor, and topic consumer roles</span></span>      |

### <a name="before-you-activate-a-trial"></a><span data-ttu-id="d198e-128">평가판을 활성화하기 전에</span><span class="sxs-lookup"><span data-stu-id="d198e-128">Before you activate a trial</span></span>

<span data-ttu-id="d198e-129">Viva 항목의 효과적인 평가판을 위해 계획은 반드시 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-129">Planning is essential for an effective trial of Viva Topics.</span></span> <span data-ttu-id="d198e-130">평가 기간은 제한되어 있으며 항목 검색 및 탐색 항목 품질, 관리 및 최종 사용자 환경을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-130">The trial period is limited and must include topic discovery and exploring topic quality, management, and end-user experiences.</span></span>

#### <a name="discovery"></a><span data-ttu-id="d198e-131">검색</span><span class="sxs-lookup"><span data-stu-id="d198e-131">Discovery</span></span>

<span data-ttu-id="d198e-132">평가판 동안 항목 검색을 구성하기 위한 두 가지 고급 전략 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-132">There are two high-level strategy options for configuration of topic discovery during a trial:</span></span>

- <span data-ttu-id="d198e-133">온라인 콘텐츠의 전체 또는 SharePoint 인덱싱합니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-133">Index all or most of your SharePoint Online content.</span></span>
   - <span data-ttu-id="d198e-134">대규모 테넌트는 완전히 인덱싱하는 데 최대 2주가 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-134">Large tenants can take up to two weeks to fully index.</span></span> <span data-ttu-id="d198e-135">이 기간 동안 항목은 증분적으로 생성되는 반면 전체 인덱싱은 평가 기간의 절반까지 소비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-135">While topics will be generated incrementally throughout this period, full indexing could consume up to half the trial period.</span></span>
   - <span data-ttu-id="d198e-136">데이터가 많은 테넌트의 경우 이 옵션은 매우 많은 수의 항목을 만들 수 있습니다(수만 개).</span><span class="sxs-lookup"><span data-stu-id="d198e-136">For tenants with a significant volume of data, this option can produce a very large number of topics, perhaps tens of thousands.</span></span>

- <span data-ttu-id="d198e-137">인덱싱을 위해 SharePoint 사이트의 하위 집합을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-137">Identify a subset of your SharePoint sites for indexing.</span></span>

<span data-ttu-id="d198e-138">이러한 전략의 선택은 다음 두 가지 요인의 균형을 이루는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-138">The choice of these strategies is a balance of the following two factors:</span></span>

- <span data-ttu-id="d198e-139">의미 있는 항목을 생성할 수 있는 충분한 데이터가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="d198e-139">Having enough data to generate meaningful topics.</span></span> <span data-ttu-id="d198e-140">Viva 항목의 AI는 10,000개 이상의 문서가 있는 큰 데이터 집합에서 작동하게 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-140">The AI in Viva Topics is tuned to work on large datasets, ideally ones that have more than 10,000 documents.</span></span>
- <span data-ttu-id="d198e-141">체험 기간 동안 너무 많은 항목을 생성하지 못하여 사용 가능한 기간 동안 항목을 평가하는 것은 압도적입니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-141">Not generating so many topics during the trial period that evaluating them during the available time period is overwhelming.</span></span>

<span data-ttu-id="d198e-142">대부분의 조직에서 두 번째 전략은 최상의 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-142">For most organizations, the second strategy produces the best outcome.</span></span>

> [!NOTE]
> <span data-ttu-id="d198e-143">AI에 필요한 문서 수 때문에 프로덕션 테넌트에서 Viva Topics 평가판을 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-143">Due to the number of documents required by the AI, we recommend that you run Viva Topics trials on a production tenant.</span></span> <span data-ttu-id="d198e-144">이 기간 동안 테넌트의 성능에는 영향을 끼치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-144">There’s no impact on the performance of the tenant during this period.</span></span> <span data-ttu-id="d198e-145">평가판 라이선스가 있는 사용자만 Viva Topics 사용자 경험에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-145">Only users who have a trial license can access Viva Topics user experiences.</span></span>

#### <a name="roles"></a><span data-ttu-id="d198e-146">역할</span><span class="sxs-lookup"><span data-stu-id="d198e-146">Roles</span></span>

<span data-ttu-id="d198e-147">체험 중에 다음 표에 설명된 세 가지 역할이 활성화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-147">During the trial, there are three roles that must be active, which are described in the following table.</span></span>

|<span data-ttu-id="d198e-148">역할</span><span class="sxs-lookup"><span data-stu-id="d198e-148">Role</span></span>  |<span data-ttu-id="d198e-149">활동</span><span class="sxs-lookup"><span data-stu-id="d198e-149">Activity</span></span>  |
|---------|---------|
|<span data-ttu-id="d198e-150">지식 매니저</span><span class="sxs-lookup"><span data-stu-id="d198e-150">Knowledge manager</span></span>     |   <span data-ttu-id="d198e-151">항목의 수명 주기 단계 제어 항목을 확인하고 제거합니다. 주제 참가자를 위한 커뮤니티 관리자로 활동</span><span class="sxs-lookup"><span data-stu-id="d198e-151">Control the lifecycle stages of topics; confirm and remove topics; act as a community manager for topic contributors</span></span>      |
|<span data-ttu-id="d198e-152">주제 기여자</span><span class="sxs-lookup"><span data-stu-id="d198e-152">Topic contributor</span></span>    |      <span data-ttu-id="d198e-153">콘텐츠 주제 전문가, 다음을 할 수 있는 사람</span><span class="sxs-lookup"><span data-stu-id="d198e-153">Content subject matter experts, who can:</span></span><br> <span data-ttu-id="d198e-154">항목을 검토하여 AI 정의 콘텐츠의 품질을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-154">Review topics to evaluate the quality of AI-defined content</span></span><br><span data-ttu-id="d198e-155">추가 콘텐츠로 검색된 항목 큐레이터</span><span class="sxs-lookup"><span data-stu-id="d198e-155">Curate discovered topics with additional content</span></span><br><span data-ttu-id="d198e-156">AI에서 검색되지 않은 추가 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="d198e-156">Create additional topics that weren’t discovered by AI</span></span>   |
|<span data-ttu-id="d198e-157">항목 소비자</span><span class="sxs-lookup"><span data-stu-id="d198e-157">Topic consumer</span></span>    |     <span data-ttu-id="d198e-158">페이지 강조 표시 및 검색을 통해 항목 사용</span><span class="sxs-lookup"><span data-stu-id="d198e-158">Consume topics through page highlights and search</span></span><br><span data-ttu-id="d198e-159">제공된 항목의 값에 대한 피드백 제공</span><span class="sxs-lookup"><span data-stu-id="d198e-159">Provide feedback on the value of the topics presented</span></span>    |

#### <a name="expected-topics"></a><span data-ttu-id="d198e-160">예상 항목</span><span class="sxs-lookup"><span data-stu-id="d198e-160">Expected topics</span></span>

<span data-ttu-id="d198e-161">AI에서 생성될 것으로 예상되는 항목을 문서화하는 것이 유용할 수 있습니다. 가정에만 기반을 두어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-161">It can be useful to document the topics you expect to be generated by the AI, even if this is based only on assumptions.</span></span> <span data-ttu-id="d198e-162">이 작업은 중소기업을 쉽게 식별할 수 있는 SharePoint 사이트의 정의된 하위 집합을 인덱싱할 때 가장 쉽게 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-162">This task is most easily completed when you index a defined subset of your SharePoint sites for which SMEs can be easily identified.</span></span>

<span data-ttu-id="d198e-163">문서화된 목록을 사용하면 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-163">Having a documented list will help you to:</span></span>

- <span data-ttu-id="d198e-164">예상보다 클 수 있는 AI 생성 항목 목록을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-164">Review the list of AI-generated topics, which might be larger than you expect.</span></span>
- <span data-ttu-id="d198e-165">수동으로 만들어야 할 수도 있는 항목이나 큐레이터의 우선 순위인 항목을 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-165">Know the topics you might need to manually create or that are priorities for curation.</span></span>

<span data-ttu-id="d198e-166">Viva 항목의 성공적인 배포 또는 평가판에서 AI가 정의한 항목과 사람이 만든 항목을 혼합해야 하는 경우도 항상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-166">There will always be a need for a mixture of AI-defined and human-created topics in a successful deployment or trial of Viva Topics.</span></span>

## <a name="activate-a-trial"></a><span data-ttu-id="d198e-167">평가판 활성화</span><span class="sxs-lookup"><span data-stu-id="d198e-167">Activate a trial</span></span>

<span data-ttu-id="d198e-168">평가판을 시작할 때 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-168">When you initiate a trial, you need to:</span></span>

- <span data-ttu-id="d198e-169">관련 사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-169">Assign licenses to the relevant users.</span></span>
- <span data-ttu-id="d198e-170">Viva [항목의](set-up-topic-experiences.md) 추가 설정을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="d198e-170">Perform [additional setup](set-up-topic-experiences.md) of Viva Topics.</span></span>

<span data-ttu-id="d198e-171">평가판이 활성화되면 항목 검색 프로세스가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-171">When the trial is activated, the topic discovery process begins.</span></span>

## <a name="during-a-trial"></a><span data-ttu-id="d198e-172">평가판 중</span><span class="sxs-lookup"><span data-stu-id="d198e-172">During a trial</span></span>

<span data-ttu-id="d198e-173">평가 기간을 사용하여 Viva 항목의 다음 구성 요소를 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-173">The trial period should be used to evaluate the following components of Viva Topics:</span></span>

- <span data-ttu-id="d198e-174">AI 추천 항목 및 항목 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="d198e-174">The AI-suggested topics and topic content</span></span>
- <span data-ttu-id="d198e-175">최종 사용자 환경, 최신 웹 페이지 및 SharePoint 주제 카드를 Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="d198e-175">The end-user experiences, surfacing topic cards on modern SharePoint pages and in Microsoft Search</span></span>

<span data-ttu-id="d198e-176">다음 요인들을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-176">Consider these factors:</span></span>

- <span data-ttu-id="d198e-177">Viva Topics에서 최대값을 전달하기 위해 항목의 콘텐츠는 AI 정의 콘텐츠와 인간 큐레이터 콘텐츠의 조합이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-177">For Viva Topics to deliver the maximum value, the content in topics needs to be a combination of AI-defined content and human-curated content.</span></span>
- <span data-ttu-id="d198e-178">모든 사용자 환경은 "사용 권한이 잘림"(항목 관리  페이지의 지식 관리자의 보기 포함)입니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-178">All user experiences are “permission trimmed” (including the knowledge manager’s view on the **Manage topics** page).</span></span> <span data-ttu-id="d198e-179">사용자는 항목을 생성하는 데 사용된 리소스 중 일부를 볼 수 있는 권한이 있는 경우만 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-179">Users will only see a topic if they have permissions to view some of the resources that were used to generate the topic.</span></span> <span data-ttu-id="d198e-180">즉, 여러 사용자가 동일한 항목 페이지에서 서로 다른 콘텐츠를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-180">This means that different users might see different content on the same topic page.</span></span>
- <span data-ttu-id="d198e-181">사용자는 항목 관리 페이지에서 이름이 같은 여러 **항목을 볼 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-181">Users might see multiple topics that have the same name in the **Manage topics** page.</span></span> <span data-ttu-id="d198e-182">이러한 항목은 반드시 중복되는 것은 아니며, 데이터의 여러 컨텍스트에서 사용되는 단일 용어(예: 두 개의 고유한 프로젝트에서 사용되는 프로젝트 코드 이름) 때문에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-182">These topics aren't necessarily duplicates but might be because of a single term that’s used in multiple contexts in the data, such as a project code name that’s used by two distinct projects.</span></span>

## <a name="after-a-trial"></a><span data-ttu-id="d198e-183">평가판 이후</span><span class="sxs-lookup"><span data-stu-id="d198e-183">After a trial</span></span>

<span data-ttu-id="d198e-184">평가판의 결과에 따라 Viva 항목의 프로덕션 사용을 진행할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-184">Based on the outcome of the trial, you can decide whether to proceed to production use of Viva Topics.</span></span>

### <a name="proceed-to-production-use"></a><span data-ttu-id="d198e-185">프로덕션 사용 진행</span><span class="sxs-lookup"><span data-stu-id="d198e-185">Proceed to production use</span></span>

<span data-ttu-id="d198e-186">서비스의 연속성을 보장하려면 필요한 라이선스 수를 구매하고 사용자에게 해당 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-186">To ensure continuity of service, you must purchase the required number of licenses and assign those licenses to users.</span></span> <span data-ttu-id="d198e-187">평가 기간이 끝나면 정식 라이선스가 없는 평가판 사용자는 Viva 항목 경험에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-187">Trial users who don’t have a full license at the end of the trial period won’t be able to access any Viva Topics experiences.</span></span>

### <a name="dont-proceed-to-production-use"></a><span data-ttu-id="d198e-188">프로덕션 사용을 계속 진행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-188">Don’t proceed to production use</span></span>

<span data-ttu-id="d198e-189">평가판 다음에 라이선스를 구매하지 않는 경우:</span><span class="sxs-lookup"><span data-stu-id="d198e-189">If you don’t purchase licenses following the trial:</span></span>

- <span data-ttu-id="d198e-190">항목 검색이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-190">Topic discovery will stop.</span></span>
- <span data-ttu-id="d198e-191">사용자는 더 이상 주요 항목이나 카드를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-191">Users will no longer see topic highlights or cards.</span></span>
- <span data-ttu-id="d198e-192">항목 센터는 삭제되지 않지만 제안된 항목 및 항목 관리 환경을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-192">The topic center won’t be deleted, but the suggested topics and manage topics experiences won’t be available.</span></span>
- <span data-ttu-id="d198e-193">AI로 정의된 항목은 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-193">Any AI-defined topics will be lost.</span></span>
- <span data-ttu-id="d198e-194">항목 참가자가 편집한 항목은 항목 센터 페이지 라이브러리에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-194">Topics that have been edited by a topic contributor will remain in the topic center pages library.</span></span> <span data-ttu-id="d198e-195">수동으로 제공된 콘텐츠만 AI 추천 콘텐츠가 아니라 이러한 페이지에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d198e-195">Only the manually provided content will remain on these pages, not any AI-suggested content.</span></span>

## <a name="see-also"></a><span data-ttu-id="d198e-196">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d198e-196">See also</span></span>

[<span data-ttu-id="d198e-197">Microsoft Viva 항목의 채택 시작</span><span class="sxs-lookup"><span data-stu-id="d198e-197">Get started driving adoption of Microsoft Viva Topics</span></span>](topics-adoption-getstarted.md)

