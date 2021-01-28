---
title: '항목 환경 항목 검색 및 큐레이터(미리 보기) '
description: 항목을 검색하는 방법에 대한 개요입니다.
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-topics
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 08860b32b6809f489a9c108dcfaed3f61fb2e306
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029641"
---
# <a name="topic-experiences-discovery-and-curation-preview"></a><span data-ttu-id="4e9be-103">항목 환경 검색 및 큐레이터(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="4e9be-103">Topic Experiences discovery and curation (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="4e9be-104">이 문서의 내용은 Project Cortex Private Preview용입니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="4e9be-105">[Project Cortex](https://aka.ms/projectcortex)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="4e9be-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="4e9be-106">항목 환경은 지식 정보를 Microsoft 365 환경의 지식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-106">Topic Experiences converts knowledge information to knowledge in your Microsoft 365 environment.</span></span> <span data-ttu-id="4e9be-107">익숙하지 않은 용어가 발생하는 문서 및 사이트 페이지를 모두 읽어 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-107">We've all experienced reading through documents and site pages where we encounter terms we are unfamiliar with.</span></span> <span data-ttu-id="4e9be-108">많은 경우 자세한 정보를 검색하는 데 시간을 소비하기 위해 수행하고 있는 작업을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-108">Many times we stop what we are doing to spend precious time searching for more information.</span></span>

<span data-ttu-id="4e9be-109">What Topic Experiences does is use Microsoft Graph and AI to identify **topics** in your organization.</span><span class="sxs-lookup"><span data-stu-id="4e9be-109">What Topic Experiences does is use Microsoft Graph and AI to identify **topics** in your organization.</span></span>  <span data-ttu-id="4e9be-110">주제는 조직에 특정한 의미를 가진 구 또는 용어로, 사용자가 해당 항목에 대한 위키 페이지를 볼 수 있는 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-110">A topic is a phrase or term that has a specific meaning to an organization, where users would benefit by being able to view a wiki page about it.</span></span> <span data-ttu-id="4e9be-111">AI는 항목에 연결된 사용자 및 콘텐츠를 검색하며, 검색된 콘텐츠가 충분히 발견되면 제안된 주제가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-111">AI searches for people and content connected to the topic, and if enough it discovered, it becomes a suggested topic.</span></span>

<span data-ttu-id="4e9be-112">AI 추천 항목 정보는 다음을 포함할 수 있는 항목 페이지에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-112">The AI suggested topic information is added to a **Topic page**, which can contain:</span></span>
- <span data-ttu-id="4e9be-113">항목에 대한 간단한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-113">A short description of the topic.</span></span>
- <span data-ttu-id="4e9be-114">항목의 대체 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-114">Alternate names for the topic.</span></span>
- <span data-ttu-id="4e9be-115">주제에 대해 더 알고 있을 수 있는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-115">People who might know more about the topic.</span></span>
- <span data-ttu-id="4e9be-116">항목과 관련이 있을 수 있는 사이트, 파일 및 페이지</span><span class="sxs-lookup"><span data-stu-id="4e9be-116">Sites, files, and pages that might be related to the topic.</span></span>

<span data-ttu-id="4e9be-117">그런 다음 컨텍스트가 적절한 경우 테넌트의 모든 SharePoint 최신 사이트 페이지에서 이러한 항목을 강조 표시하도록 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-117">Topic experiences then, when the context is appropriate, suggests these topics to be highlighted on all SharePoint modern site pages in your tenant.</span></span> <span data-ttu-id="4e9be-118">사용자가 항목에 대해 자세히 알아보고자 할 때 강조 표시된 항목을 선택하여  간단한 설명을 제공하는 항목 요약 카드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-118">When a user is curious to learn more about a topic, they can select the highlighted topic to view a **Topic summary** card that provides a short description.</span></span> <span data-ttu-id="4e9be-119">또한 자세한 내용을 알아보고자 하는  경우 요약에서 항목 세부 정보 링크를 선택하여 자세한 항목 페이지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-119">And if they want to learn more, they can select a **Topic details** link in the summary to open the detailed topic page.</span></span>

![주요 항목](../media/knowledge-management/saturn.png) </br>

<span data-ttu-id="4e9be-121">또한 사용자는 Microsoft Search를 통해 항목을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-121">Additionally, users will also be able to find topics through Microsoft Search.</span></span>


## <a name="topic-curation"></a><span data-ttu-id="4e9be-122">주제 큐레이터</span><span class="sxs-lookup"><span data-stu-id="4e9be-122">Topic curation</span></span>

<span data-ttu-id="4e9be-123">항목 환경은 주제의 품질을 개선하기 위한 인간적인 기여를 환영합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-123">Topic Experiences welcomes human contribution to improve the quality of your topics.</span></span> <span data-ttu-id="4e9be-124">AI가 처음에 항목을 식별하고 제안하는 동안 참가자의 콘텐츠를 수동으로 편집하고, AI 생성 콘텐츠에 대한 사용자의 확인, 항목의 유용성에 대한 피드백이 모두 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-124">While AI initially identifies and suggests topics, manually made edits to content from contributors, confirmation from users for AI generated content, and feedback on the usefulness of topics are all essential.</span></span>

- <span data-ttu-id="4e9be-125">AI 생성 항목("추천 항목")은 조직의 지식 관리자가 **검토할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-125">AI generated topics ("suggested topics") can be reviewed by **knowledge managers** in your organization.</span></span> <span data-ttu-id="4e9be-126">항목 관리 페이지에서 항목의 유효성을 확인하거나 거부하여 항목을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-126">In the Manage Topics page in the Topic Center, they can choose to confirm them as valid, or reject them to prevent them from being viewed.</span></span>

- <span data-ttu-id="4e9be-127">사용이 *허가된* 사용자에게 항목 만들기 및 편집 권한을 할당하여 기존 항목을 변경하거나 필요한 경우 새 항목을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-127">You can assign *Create and edit topics* permissions to any of your licensed users so that they can make changes to existing topics or create new topics when needed.</span></span> 

- <span data-ttu-id="4e9be-128">항목(항목 보기 권한이 있는 사용자)만이라도 특정 항목의 유용성을 확인하도록 요청됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-128">Even users who only have read access to topic (topic viewers) will be asked to verify the usefulness of specific topics.</span></span> <span data-ttu-id="4e9be-129">또한 제안된 항목을 확인하거나 거부하기 위해 피드백을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-129">Their feedback is also taken to confirm or reject a suggested topic.</span></span>

<span data-ttu-id="4e9be-130">사람의 편집을 조차도 AI는 항목에 대한 자세한 정보를 지속적으로 찾아 인간 확인을 찾아보게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-130">Even with human edits, AI will continually look for more information about topics, and will look for human verification.</span></span> <span data-ttu-id="4e9be-131">예를 들어 AI가 사용자가 주제에 대한 전문가로 나열해야 하는 사람인 경우 이를 확인 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9be-131">For example, if AI thinks you are a person that should be listed as an expert on a topic, it will ask you to confirm this.</span></span> 



## <a name="see-also"></a><span data-ttu-id="4e9be-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e9be-132">See also</span></span>
