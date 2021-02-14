---
title: 검토 집합에서 문서 태그 지정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 검토 집합의 문서에 태그를 지정하면 불필요한 콘텐츠를 제거하고 Advanced eDiscovery 사례에서 관련 콘텐츠를 식별할 수 있습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 83e7a3c9c097968c4d773e6e2092bb3c50154cc3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285284"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="ad5f7-103">Advanced eDiscovery의 검토 집합에서 문서 태그 지정</span><span class="sxs-lookup"><span data-stu-id="ad5f7-103">Tag documents in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="ad5f7-104">검토 집합에서 콘텐츠를 구성하는 것은 eDiscovery 프로세스에서 다양한 워크플로를 완료하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="ad5f7-105">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-105">This includes:</span></span>

- <span data-ttu-id="ad5f7-106">불필요한 콘텐츠 컬링</span><span class="sxs-lookup"><span data-stu-id="ad5f7-106">Culling unnecessary content</span></span>

- <span data-ttu-id="ad5f7-107">관련 콘텐츠 식별</span><span class="sxs-lookup"><span data-stu-id="ad5f7-107">Identifying relevant content</span></span>
 
- <span data-ttu-id="ad5f7-108">전문가 또는 변호사가 검토해야 하는 콘텐츠 식별</span><span class="sxs-lookup"><span data-stu-id="ad5f7-108">Identifying content that must be reviewed by an expert or an attorney</span></span>

<span data-ttu-id="ad5f7-109">전문가, 변호사 또는 기타 사용자가 검토 집합의 콘텐츠를 검토할 때 해당 콘텐츠와 관련된 의견은 태그를 사용하여 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="ad5f7-110">예를 들어 불필요한 콘텐츠를 제거하기 위한 경우 사용자는 "응답하지 않는"와 같은 태그를 사용하여 문서에 태그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="ad5f7-111">콘텐츠를 검토하고 태그를 지정한 후 검토 집합 검색을 만들어 "응답하지 않는"으로 태그가 지정된 모든 콘텐츠를 제외할 수 있습니다. 그러면 eDiscovery 워크플로의 다음 단계에서 이 콘텐츠가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive", which eliminates this content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="ad5f7-112">태그가 의도한 검토 워크플로를 지원할 수 있도록 모든 경우에 대해 태그 패널을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-112">The tag panel can be customized for every case so that the tags can support the intended review workflow.</span></span>

## <a name="tag-types"></a><span data-ttu-id="ad5f7-113">태그 유형</span><span class="sxs-lookup"><span data-stu-id="ad5f7-113">Tag types</span></span>

<span data-ttu-id="ad5f7-114">Advanced eDiscovery는 두 가지 유형의 태그를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-114">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="ad5f7-115">**단일 선택 태그** - 사용자가 그룹 내에서 단일 태그를 선택하도록 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-115">**Single choice tags** - Restricts users to select a single tag within a group.</span></span> <span data-ttu-id="ad5f7-116">이는 사용자가 "응답" 및 "응답하지 않는"과 같은 충돌하는 태그를 선택하지 않도록 하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-116">This can be useful to ensure users don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="ad5f7-117">라디오 단추로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-117">These will appear as radio buttons.</span></span>

- <span data-ttu-id="ad5f7-118">**다중 선택 태그** - 사용자가 그룹 내에서 여러 태그를 선택할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-118">**Multiple choice tags** - Allow users to select multiple tags within a group.</span></span> <span data-ttu-id="ad5f7-119">확인란으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-119">These will appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="ad5f7-120">태그 구조</span><span class="sxs-lookup"><span data-stu-id="ad5f7-120">Tag structure</span></span>

<span data-ttu-id="ad5f7-121">태그 유형 외에도 태그 패널에서 태그를 구성하는 방법의 구조를 사용하여 문서 태그 지정을 보다 직관적으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-121">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="ad5f7-122">태그는 섹션으로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-122">Tags are grouped by sections.</span></span> <span data-ttu-id="ad5f7-123">검토 집합 검색은 태그 및 태그 섹션을 통해 검색하는 기능을 지원하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-123">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="ad5f7-124">즉, 검토 집합 검색을 만들어 섹션의 태그로 태그가 지정된 문서를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-124">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![태그 패널의 태그 섹션](../media/Tagtypes.png)

<span data-ttu-id="ad5f7-126">태그는 섹션 내에 중첩하여 추가로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-126">Tags can be further organized by nesting them within a section.</span></span> <span data-ttu-id="ad5f7-127">예를 들어 권한 있는 콘텐츠를 식별하고 태그를 지정하기 위한 경우 중첩을 사용하여 사용자가 문서에 "Privileged"로 태그를 지정하고 적절한 중첩된 태그를 확인하여 권한 유형을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-127">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a user can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![태그 섹션 내의 중첩된 태그](../media/Nestingtags.png)

## <a name="applying-tags"></a><span data-ttu-id="ad5f7-129">태그 적용</span><span class="sxs-lookup"><span data-stu-id="ad5f7-129">Applying tags</span></span>

<span data-ttu-id="ad5f7-130">콘텐츠에 태그를 적용하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-130">There are several ways to apply a tag to content.</span></span>

### <a name="tagging-a-single-document"></a><span data-ttu-id="ad5f7-131">단일 문서에 태그 지정</span><span class="sxs-lookup"><span data-stu-id="ad5f7-131">Tagging a single document</span></span>

<span data-ttu-id="ad5f7-132">검토 집합에서 문서를 볼 때 태그 지정 패널을 클릭하여 검토에서 사용할 수 있는 태그를 표시할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="ad5f7-132">When viewing a document in a review set, you can display the tags that a review can use by clicking **Tagging panel**.</span></span>

![태그 패널을 클릭하여 태그 패널 표시](../media/Singledoctag.png)

<span data-ttu-id="ad5f7-134">이렇게 하면 보기에 표시된 문서에 태그를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-134">This will enable you to apply tags to the document displayed in the viewer.</span></span>

### <a name="bulk-tagging"></a><span data-ttu-id="ad5f7-135">대량 태그 지정</span><span class="sxs-lookup"><span data-stu-id="ad5f7-135">Bulk tagging</span></span>

<span data-ttu-id="ad5f7-136">결과 표에서 여러 파일을 선택한 다음 단일 문서에 태그 지정과  유사한 태그 지정 패널의 태그를 사용하여 대량 태그 지정을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-136">Bulk tagging can be done by selecting multiple files in the results grid and then using the tags in the **Tagging panel** similar to tagging single documents.</span></span> <span data-ttu-id="ad5f7-137">태그를 두 번 선택하여 대량 태그 지정을 할 수 있습니다. 첫 번째 클릭은 태그를 적용하고 두 번째 선택은 선택한 모든 파일에 대해 태그가 지워지기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-137">Bulk un-tagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files.</span></span>

![자동으로 생성된 휴대폰 설명의 스크린샷](../media/Bulktag.png)

> [!NOTE]
> <span data-ttu-id="ad5f7-139">대량 태그 지정 시 태그 지정 패널에는 패널의 각 태그에 대해 태그가 지정되는 파일 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-139">When bulk tagging, the tagging panel will display a count of files that are tagged for each tag in the panel.</span></span>

### <a name="tagging-in-other-review-panels"></a><span data-ttu-id="ad5f7-140">다른 검토 패널에서 태그 지정</span><span class="sxs-lookup"><span data-stu-id="ad5f7-140">Tagging in other review panels</span></span>

<span data-ttu-id="ad5f7-141">문서를 검토할 때 다른 검토 패널을 사용하여 결과 표에서 문서의 다른 특성을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-141">When reviewing documents, you can use the other review panels to review other characteristics of documents in the results grid.</span></span> <span data-ttu-id="ad5f7-142">여기에는 다른 관련 문서, 전자 메일 스레드, 거의 중복된 항목 및 해시 중복을 검토하는 것이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-142">This includes reviewing other related documents, email threads, near duplicates, and hash duplicates.</span></span> <span data-ttu-id="ad5f7-143">예를 들어 문서 패밀리 검토 패널을 사용하여 관련  문서를 검토하는 경우 관련 문서에 대량 태그를 지정하여 검토 시간을 크게 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-143">For example, when you're reviewing related documents (by using the **Document family** review panel), you can significantly reduce review time by bulk tagging related documents.</span></span> <span data-ttu-id="ad5f7-144">예를 들어 전자 메일 메시지에 여러 첨부 파일이 있고 전체 패밀리에 일관되게 태그가 지정되도록 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="ad5f7-144">For example, if an email message has several attachments and you want to ensure that the entire family is tagged consistently.</span></span>

<span data-ttu-id="ad5f7-145">예를 들어 다음은 문서 패밀리  검토 패널을 사용할 때 태그 지정 패널을 **표시하는** 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-145">For example, here's how to display the **Tagging panel** when using the **Document family** review panel:</span></span>

1. <span data-ttu-id="ad5f7-146">선택한 문서에 대한 검토 패널이 열리면(예: 문서 패밀리  검토 패널에  관련 콘텐츠 목록 표시) 문서 패밀리 검토 패널에서 문서 태그를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-146">With the review panel open for a selected document (for example, displaying the list of related content in the **Document family** review panel, click **Tag documents** under the document family review panel.</span></span>

   <span data-ttu-id="ad5f7-147">태그 지정 패널이 팝업 창으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-147">The tagging panel is displayed as a pop-up window.</span></span>

2. <span data-ttu-id="ad5f7-148">선택한 문서를 적용하기 위해 하나 이상의 태그를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-148">Choose one or more tags to apply the selected document.</span></span> 

3. <span data-ttu-id="ad5f7-149">모든 문서에 태그를 지정하려면 문서  패밀리 패널에서 모든 문서를 선택하고 문서 태그를 클릭한 다음 전체 문서 패밀리에 적용할 태그를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5f7-149">To tag all documents, select all documents in the **Document family** panel, click **Tag documents**, and then choose the tags to apply to the entire family of documents.</span></span>

![소셜 미디어 게시물 설명이 자동으로 생성되는 스크린샷](../media/Relatedtag.png)
