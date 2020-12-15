---
title: 보안 및 개인 정보 보호를 경험하는 항목
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365의 항목 환경 보안 및 개인 정보 보호를 계획하는 방법에 대해 자세히 알아보기
ms.openlocfilehash: 7b88e5bbc8158ebd7dea65b2ecbf77085651b439
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668251"
---
# <a name="topic-experiences-security-and-privacy"></a><span data-ttu-id="cf923-103">보안 및 개인 정보 보호를 경험하는 항목</span><span class="sxs-lookup"><span data-stu-id="cf923-103">Topic experiences security and privacy</span></span>

<span data-ttu-id="cf923-104">항목 환경은 기술 네트워크 컨트롤과 함께 Microsoft 365의 기존 콘텐츠 보안 기능을 사용하여 조직의 사용자에게 표시되는 AI 생성 콘텐츠를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-104">Topic experiences uses existing content security features in Microsoft 365, along with knowledge network controls, to control what AI-generated content is shown to users in your organization.</span></span> <span data-ttu-id="cf923-105">Microsoft 365 보안 설정(사이트, 파일 및 폴더에 대한 사용 권한)의 조합으로, 항목에서는 특정 사용자가 항목에 볼 수 있는 항목을 결정하는 관리 설정을 경험합니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-105">It is the combination of Microsoft 365 security settings (permissions to sites, files, and folders) and topic experiences admin settings that determine what a given user can see in topics.</span></span>

<span data-ttu-id="cf923-106">지식 네트워크를 설정하면 조직의 콘텐츠에 대한 기존 액세스 제어가 수정되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-106">Setting up the knowledge network does not modify any existing access controls on content in your organization.</span></span> <span data-ttu-id="cf923-107">사용자는 이미 액세스할 수 있는 것만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-107">Users will only see what they already have access to.</span></span>

<span data-ttu-id="cf923-108">이 문서에서는 보안 관점에서 항목 환경이 작동하는 방식과 지식 관리자와 지식 관리자가 항목 표시를 제어해야 하는 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-108">This article describes how topic experiences works from a security perspective and the options that knowledge administrators and knowledge managers have to control topic visibility.</span></span> <span data-ttu-id="cf923-109">항목 환경 계획의 일부로 이 문서를 [읽어 읽습니다.](plan-topic-experiences.md)</span><span class="sxs-lookup"><span data-stu-id="cf923-109">Read this article as part of your [planning for topic experiences](plan-topic-experiences.md).</span></span>

<span data-ttu-id="cf923-110">이 문서를 읽기 전에 항목 [](topic-center-overview.md) [환경,](knowledge-management-overview.md)항목 [](work-with-topics.md) 센터 및 항목 센터의 항목으로 작업하는 방법을 잘 알고 있을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-110">You should be familiar with [Topic experiences](knowledge-management-overview.md), the [topic center](topic-center-overview.md), and how to [work with topics in the topic center](work-with-topics.md) before you read this article.</span></span>

## <a name="what-users-can-see-in-topics"></a><span data-ttu-id="cf923-111">항목에서 사용자에게 볼 수 있는 항목</span><span class="sxs-lookup"><span data-stu-id="cf923-111">What users can see in topics</span></span>

<span data-ttu-id="cf923-112">항목을 표시하려면 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-112">To see topics, a user must:</span></span>

- <span data-ttu-id="cf923-113">항목 환경 라이선스 사용</span><span class="sxs-lookup"><span data-stu-id="cf923-113">Have a Topic Experiences license</span></span>
- <span data-ttu-id="cf923-114">주제 [뷰어, 참가자](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization)또는 [지식 관리자 1명](topic-experiences-user-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="cf923-114">Be a [topic viewer](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization), [contributor, or knowledge manager](topic-experiences-user-permissions.md)</span></span>

<span data-ttu-id="cf923-115">이러한 두 가지를 통해 사용자는 항목 센터에 대한 액세스 권한을 부여하고 강조 표시 및 항목 카드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-115">These two things give users view access to the topic center and allow them to see highlights and topic cards.</span></span>

<span data-ttu-id="cf923-116">또한 주제 참가자가 항목에 대한 [사용](topic-experiences-user-permissions.md#change-who-has permissions-to-update-topic-details) 권한을 만들고 편집할 수 있으며, 지식 관리자는 항목을 확인하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-116">Topic contributors additionally have [create and edit](topic-experiences-user-permissions.md#change-who-has permissions-to-update-topic-details) permissions for topics, and knowledge managers can confirm or remove topics.</span></span>

<span data-ttu-id="cf923-117">주제가 처음 발견될 때 지식 관리자는 항목 센터에서 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-117">When a topic is first discovered, knowledge managers can see it in the topic center.</span></span> <span data-ttu-id="cf923-118">주제의 완성도 및 관련성에 따라 항목 보기가 항목 카드에 제시된 항목을 보거나 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-118">Depending on the completeness and relevance of the topic, topic viewers may or may not see the topic presented in topic cards.</span></span>

<span data-ttu-id="cf923-119">항목에는 AI에서 생성된 정보와 항목 참가자 또는 지식 관리자가 추가하거나 편집한 정보가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-119">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

- <span data-ttu-id="cf923-120">AI에서 추가한 항목의 정보는 원본 콘텐츠에 액세스할 수 있는 사용자만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-120">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
- <span data-ttu-id="cf923-121">항목 작성자 또는 기술 관리자가 수동으로 추가하거나 편집한 텍스트는 항목을 볼 수 있는 모든 사람이 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-121">Text that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="cf923-122">주제 뷰어 및 참가자는 항목 센터에서 확인 및 게시된 항목 목록을 볼 수 있지만 특정 사용자가 볼 수 있는 항목 세부 정보는 원본 자료에 대한 사용 권한 및 항목을 수동으로 편집한지 여부에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-122">Topic viewers and contributors can see the list of confirmed and published topics in the topic center, but the topic details that a given person can see depends on the permissions that they have to the source material and on whether the topic has been manually edited.</span></span>

<span data-ttu-id="cf923-123">다음 표에서는 사용자(주제 뷰어, 참가자 및 지식 관리자)가 사용 권한에 따라 특정 항목에서 볼 수 있는 항목에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-123">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="cf923-124">항목 항목</span><span class="sxs-lookup"><span data-stu-id="cf923-124">Topic item</span></span>|<span data-ttu-id="cf923-125">사용자에게 표시될 수 있는 것</span><span class="sxs-lookup"><span data-stu-id="cf923-125">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="cf923-126">항목 이름</span><span class="sxs-lookup"><span data-stu-id="cf923-126">Topic name</span></span>|<span data-ttu-id="cf923-127">사용자는 항목 센터에서 모든 항목의 항목 이름을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-127">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="cf923-128">사용자에게 관련성 수준이 낮은 경우 일부 항목은 표시되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-128">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="cf923-129">항목 설명</span><span class="sxs-lookup"><span data-stu-id="cf923-129">Topic description</span></span>|<span data-ttu-id="cf923-130">AI 생성 설명은 원본 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-130">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="cf923-131">수동으로 입력하거나 편집한 설명은 모든 사용자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-131">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="cf923-132">사람</span><span class="sxs-lookup"><span data-stu-id="cf923-132">People</span></span>|<span data-ttu-id="cf923-133">고정된 사용자는 모든 사용자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-133">Pinned people are visible to all users.</span></span> <span data-ttu-id="cf923-134">제안된 사용자는 원본 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-134">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="cf923-135">파일</span><span class="sxs-lookup"><span data-stu-id="cf923-135">Files</span></span>|<span data-ttu-id="cf923-136">파일은 원본 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-136">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="cf923-137">페이지</span><span class="sxs-lookup"><span data-stu-id="cf923-137">Pages</span></span>|<span data-ttu-id="cf923-138">페이지는 원본 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-138">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="cf923-139">사이트</span><span class="sxs-lookup"><span data-stu-id="cf923-139">Sites</span></span>|<span data-ttu-id="cf923-140">사이트는 원본 콘텐츠에 대한 사용 권한이 있는 사용자에게만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-140">Sites are only visible to users who have permissions to the source content.</span></span>|

## <a name="best-practices"></a><span data-ttu-id="cf923-141">모범 사례</span><span class="sxs-lookup"><span data-stu-id="cf923-141">Best practices</span></span>

<span data-ttu-id="cf923-142">항목 환경은 콘텐츠에 대한 기존 사용 권한에 따라 사용자에게 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-142">Topic experiences presents information to users based on their existing permissions to content.</span></span> <span data-ttu-id="cf923-143">Microsoft 365는 중요한 콘텐츠가 적절한 사용자로 제한되도록 다양한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-143">Microsoft 365 provides a variety of ways to ensure that sensitive content is restricted to appropriate users.</span></span> <span data-ttu-id="cf923-144">표준 팀 또는 사이트 권한 이외에 민감도 레이블 [](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) 또는 데이터 손실 방지를 [](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) 사용하여 콘텐츠에 대한 액세스를 제한하고 검토에 액세스하여 중요한 정보에 대한 사용자 액세스를 주기적으로 검토할 수 있습니다. [](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)</span><span class="sxs-lookup"><span data-stu-id="cf923-144">Beyond standard team or site permissions, you can use [sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) or [data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) to restrict access to content and [access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) to periodically review user access to sensitive information.</span></span>

<span data-ttu-id="cf923-145">이러한 도구를 사용하여 조직 내에서 콘텐츠 사용 권한을 적절하게 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-145">We recommend that you use these tools to ensure that your content permissions are set appropriately inside your organization.</span></span> <span data-ttu-id="cf923-146">그러면 항목 환경이 사용자에게 유용하고 적절한 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-146">Topic experiences can then provide useful and appropriate information to your users.</span></span>

<span data-ttu-id="cf923-147">항목 환경에서 완전히 제외하려는 주제가 있는 경우 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-147">If there are topics that you want to exclude entirely from topic experiences, you can also:</span></span>

- <span data-ttu-id="cf923-148">[항목 검색에서 중요한 SharePoint 사이트를 제외합니다.](topic-experiences-discovery.md#select-sharepoint-topic-sources)</span><span class="sxs-lookup"><span data-stu-id="cf923-148">[Exclude sensitive SharePoint sites from topic discovery](topic-experiences-discovery.md#select-sharepoint-topic-sources).</span></span> <span data-ttu-id="cf923-149">이러한 사이트의 콘텐츠는 항목 환경으로 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-149">Content in these sites will not appear in topic experiences.</span></span>

- <span data-ttu-id="cf923-150">[이름으로 항목을 제외합니다.](topic-experiences-discovery.md#exclude-topics-by-name)</span><span class="sxs-lookup"><span data-stu-id="cf923-150">[Exclude topics by name](topic-experiences-discovery.md#exclude-topics-by-name).</span></span> <span data-ttu-id="cf923-151">명시적으로 제외된 항목은 항목 경험에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-151">Topics explicitly excluded will not appear in topic experiences.</span></span>

- <span data-ttu-id="cf923-152">지식 관리자가 항목 센터에서 항목을 제거하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-152">Have knowledge managers remove topics in the topic center.</span></span>

<span data-ttu-id="cf923-153">또한 다음 모범 사례를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-153">Additionally, we recommend these best practices:</span></span>

- <span data-ttu-id="cf923-154">조직의 여러 영역에서 지식 관리자를 모집합니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-154">Recruit knowledge managers from different areas of your organization.</span></span> <span data-ttu-id="cf923-155">다양한 전문 지식이 있는 지식 관리자와 AI에서 사용하는 기반 콘텐츠에 대한 액세스 권한을 부여하면 사용자에게 가장 유용한 지식을 큐링하고 중요한 정보가 발견된 경우 이를 제거하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-155">Having knowledge managers with a variety of expertise - and access to the underlying content used by AI - can help you curate the most useful knowledge for your users and remove sensitive information if found.</span></span>

- <span data-ttu-id="cf923-156">변경 내용을 요청하는 워크플로를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-156">Set up a workflow for requesting changes.</span></span> <span data-ttu-id="cf923-157">기술 관리자 또는 팀 또는 사이트 소유자는 조직 내에서 새 프로젝트가 시작되거나 부적절한 사용 권한 설정이 있는 콘텐츠를 찾을 때 항목 또는 사이트 제외를 요청할 수 있는 프로세스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-157">Knowledge managers or team or site owners should have a process by which they can request exclusion of topics or sites as new projects are started within your organization or if they find content with inappropriate permissions settings.</span></span>

- <span data-ttu-id="cf923-158">항목 설명을 만들 때 대상 사용자와 정보의 민감도를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-158">Be aware of the audience and the sensitivity of information when creating topic descriptions.</span></span> <span data-ttu-id="cf923-159">이러한 설명은 항목의 원본 콘텐츠에 대한 사용 권한이 없는 사용자에게 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-159">These descriptions may be visible to users who don't have permissions to the source content for the topic.</span></span>

<span data-ttu-id="cf923-160">개별 항목 페이지에 대한 사용 권한을 변경하여 특정 사용자 그룹에 대한 액세스 범위를 좁힐 수 있습니다. 그러나 많은 관리 노력이 필요하기 때문에 이 방법은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf923-160">While you can change the permissions on individual topic pages to narrow access to a specific group of users, we don't recommend this approach because of the high degree of administrative effort required.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf923-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf923-161">See also</span></span>

[<span data-ttu-id="cf923-162">세 가지 보호 계층으로 Teams 구성</span><span class="sxs-lookup"><span data-stu-id="cf923-162">Configure Teams with three tiers of protection</span></span>](../solutions/configure-teams-three-tiers-protection.md)

[<span data-ttu-id="cf923-163">항목 환경 계획</span><span class="sxs-lookup"><span data-stu-id="cf923-163">Plan topic experiences</span></span>](plan-topic-experiences.md)

[<span data-ttu-id="cf923-164">항목 환경 설정</span><span class="sxs-lookup"><span data-stu-id="cf923-164">Set up topic experiences</span></span>](set-up-topic-experiences.md)
