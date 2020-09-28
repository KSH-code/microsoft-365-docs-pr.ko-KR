---
title: SharePoint 분류에 대 한 오디오 os 형식 참조
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
description: SharePoint 분류에 대 한 오디오 os 형식 참조
ms.openlocfilehash: eb228394b06b6e6027937ab105df7c0079875226
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296082"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="94e05-103">SharePoint 분류에 대 한 오디오 os 형식 참조</span><span class="sxs-lookup"><span data-stu-id="94e05-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="94e05-104">이 [문서에는](https://www.w3.org/TR/skos-primer/) [SharePoint 분류법](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) 을 나타내는 데 사용 되는 RDF 어휘가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="94e05-105">이 RDF 구문을 직렬화 하려면 RDF [거북](https://www.w3.org/TR/turtle/)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="94e05-106">다음 표에는 [SharePoint 분류](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) 어휘의과 동등한 [os](https://www.w3.org/TR/skos-primer/) 가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="94e05-107">SharePoint에서는 SharePoint 분류가 일치 하지 않는 기능 [운영 체제](https://www.w3.org/TR/skos-primer/) 값을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="94e05-108">SharePoint 분류</span><span class="sxs-lookup"><span data-stu-id="94e05-108">SharePoint taxonomy</span></span>|<span data-ttu-id="94e05-109">에 해당 하는 운영 체제</span><span class="sxs-lookup"><span data-stu-id="94e05-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="94e05-110">sharepoint-분류법: Term</span><span class="sxs-lookup"><span data-stu-id="94e05-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="94e05-111">오디오 os: 개념</span><span class="sxs-lookup"><span data-stu-id="94e05-111">skos:Concept</span></span>|
|<span data-ttu-id="94e05-112">sharepoint-분류법: TermSet</span><span class="sxs-lookup"><span data-stu-id="94e05-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="94e05-113">(고) os: ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="94e05-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="94e05-114">sharepoint-분류법: inTermSet</span><span class="sxs-lookup"><span data-stu-id="94e05-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="94e05-115">(고) os: inScheme</span><span class="sxs-lookup"><span data-stu-id="94e05-115">skos:inScheme</span></span>|
|<span data-ttu-id="94e05-116">sharepoint-분류법: hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="94e05-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="94e05-117">(고) os: hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="94e05-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="94e05-118">sharepoint-분류법: topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="94e05-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="94e05-119">(고) os: topConceptOf</span><span class="sxs-lookup"><span data-stu-id="94e05-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="94e05-120">sharepoint-분류법: defaultLabel</span><span class="sxs-lookup"><span data-stu-id="94e05-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="94e05-121">(고) os: prefLabel</span><span class="sxs-lookup"><span data-stu-id="94e05-121">skos:prefLabel</span></span>|
|<span data-ttu-id="94e05-122">sharepoint-분류법: termSetName</span><span class="sxs-lookup"><span data-stu-id="94e05-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="94e05-123">(고) os: prefLabel</span><span class="sxs-lookup"><span data-stu-id="94e05-123">skos:prefLabel</span></span>|
|<span data-ttu-id="94e05-124">sharepoint-분류법: propertyName</span><span class="sxs-lookup"><span data-stu-id="94e05-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="94e05-125">(고) os: prefLabel</span><span class="sxs-lookup"><span data-stu-id="94e05-125">skos:prefLabel</span></span>|
|<span data-ttu-id="94e05-126">sharepoint-분류법: otherLabel</span><span class="sxs-lookup"><span data-stu-id="94e05-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="94e05-127">(고) os: altLabel</span><span class="sxs-lookup"><span data-stu-id="94e05-127">skos:altLabel</span></span>|
|<span data-ttu-id="94e05-128">sharepoint-분류: 설명</span><span class="sxs-lookup"><span data-stu-id="94e05-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="94e05-129">(고) os: 정의</span><span class="sxs-lookup"><span data-stu-id="94e05-129">skos:definition</span></span>|
|<span data-ttu-id="94e05-130">sharepoint-분류법: 상위</span><span class="sxs-lookup"><span data-stu-id="94e05-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="94e05-131">오디오 os: 더 넓게</span><span class="sxs-lookup"><span data-stu-id="94e05-131">skos:broader</span></span>|
|<span data-ttu-id="94e05-132">sharepoint-분류법: child</span><span class="sxs-lookup"><span data-stu-id="94e05-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="94e05-133">(고) os: 좁게</span><span class="sxs-lookup"><span data-stu-id="94e05-133">skos:narrower</span></span>|

<span data-ttu-id="94e05-134">다음 표에는 [OWL](https://www.w3.org/TR/owl2-primer/)에서 파생 된 SharePoint 분류법 어휘의 엔터티가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="94e05-135">SharePoint 분류 용어 모음</span><span class="sxs-lookup"><span data-stu-id="94e05-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="94e05-136">OWL에서 파생</span><span class="sxs-lookup"><span data-stu-id="94e05-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="94e05-137">sharepoint-분류법: Is사용 가능 For태깅</span><span class="sxs-lookup"><span data-stu-id="94e05-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="94e05-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="94e05-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="94e05-139">sharepoint-분류법: SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="94e05-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="94e05-140">owl: ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="94e05-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="94e05-141">sharepoint-분류법: LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="94e05-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="94e05-142">owl: ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="94e05-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="94e05-143">sharepoint-분류법: CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="94e05-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="94e05-144">owl: ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="94e05-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="94e05-145">SharePoint 분류 용어 모음</span><span class="sxs-lookup"><span data-stu-id="94e05-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="94e05-146">분류는 공식적인 분류 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="94e05-147">분류는 항목을 설명 하는 단어, 레이블 및 용어를 그룹화 한 다음 그룹을 계층 구조로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="94e05-148">**sharepoint-분류법: Term**</span><span class="sxs-lookup"><span data-stu-id="94e05-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="94e05-149">관리 되는 메타 데이터 계층 구조의 용어나 키워드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="94e05-150">[용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 는 SharePoint [시](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)의 원자성 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-150">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="94e05-151">각 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 는 [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)에 속하는 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-151">Each [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="94e05-152">[용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 를 정의 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-152">The syntax to define a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="94e05-153">Compulsorily [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 는 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)내에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-153">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="94e05-154">DefaultLabel은 시각적 표현에 표시 되는 [용어의](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-154">DefaultLabel is the name of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="94e05-155">[용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 를 정의 하는 데 필요한 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-155">The required fields for defining a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="94e05-156">sharepoint-분류법: defaultLabel</span><span class="sxs-lookup"><span data-stu-id="94e05-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="94e05-157">sharepoint-분류법: inTermSet</span><span class="sxs-lookup"><span data-stu-id="94e05-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="94e05-158">다음과 같은 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-158">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="94e05-159">두 [용어가](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 모두 같은 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 제공 되는 다른 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 와 계층적으로 관련 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-159">Be hierarchically related to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="94e05-160">하위 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)는 여러 개 있지만 상위 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)는 하나만 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-160">Have multiple child [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="94e05-161">상위 [용어가](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 정의 되어 있지 않은 경우 TopLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)입니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-161">Not have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="94e05-162">[시](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 작업 언어 당 하나의 defaultlabel을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-162">Have one defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="94e05-163">상위 [용어가](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)포함 되지 않고 TopLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)도 없는 경우에는 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-163">Not exist if it neither contains a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="94e05-164">같은 계층 구조 수준에 고유한 defaultLabel 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="94e05-165">**sharepoint-분류법: TermSet**</span><span class="sxs-lookup"><span data-stu-id="94e05-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="94e05-166">"TermSet"로 알려진 용어 개체의 계층적 또는 단순 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="94e05-167">이름에서 알 수 있듯이 TermSet은 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)집합입니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-167">As the name suggests, TermSet is a set of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="94e05-168">[시](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 의 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 는 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-168">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="94e05-169">[용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 는 독립적으로 존재할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-169">No [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="94e05-170">[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 를 정의 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-170">The syntax to define a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="94e05-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 는 [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)에서 논리적으로 함께 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="94e05-172">[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 을 정의 하는 데 필요한 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-172">The required field for defining a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="94e05-173">sharepoint-분류법: termSetName</span><span class="sxs-lookup"><span data-stu-id="94e05-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="94e05-174">제공 된 termSetName가 [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)내에서 고유 하지 않은 경우 sharepoint는 이름 끝에 번호를 추가 하 여 termSetName의 고유성을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-174">In the case of the termSetName provided is not unique within the [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharPoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="94e05-175">**sharepoint-분류법: hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="94e05-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="94e05-176">SharePoint는이 속성을 사용 하 여 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에서 가장 위쪽에 있는 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) ( [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)의 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 계층 구조를 가리키는 진입점)를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-176">SharePoint uses this property to map the top most [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="94e05-177">이는 sharepoint 분류법: topLevelTermOf에 대 한 역 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="94e05-178">이를 정의 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="94e05-179">상위 [용어의](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)최상위 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 는 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-179">You cannot define the top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="94e05-180">**sharepoint-분류법: topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="94e05-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="94e05-181">Sharepoint-분류법: topLevelTermOf는 sharepoint 분류법: hasTopLevelTerm의 역함수입니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="94e05-182">이를 정의 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="94e05-183">**sharepoint-분류법: inTermSet**</span><span class="sxs-lookup"><span data-stu-id="94e05-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="94e05-184">이를 사용 하 여 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 를 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-184">Use this to map a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="94e05-185">[용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 는 단일 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에만 존재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-185">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="94e05-186">[용어를 정의 하는](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term)경우 SharePoint에서이 속성을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="94e05-187">필수 레이블</span><span class="sxs-lookup"><span data-stu-id="94e05-187">Required labels</span></span>

<span data-ttu-id="94e05-188">관리 되는 메타 데이터 사용을 시작 하기 전에 조직에서 신중한 계획을 수립할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="94e05-189">수행 해야 하는 계획의 양은 분류의 공식적인 정도에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="94e05-190">또한 메타 데이터에 대해 적용 하려는 제어 정도에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="94e05-191">계층 구조의 각 수준에서 용어 또는 TermSet에 대해 필수 lables를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-191">At each level of the hierarchy, you need to configure required lables for a Term or TermSet.</span></span>

<span data-ttu-id="94e05-192">용어에는 기본 언어로 레이블이 하나 이상 있을 수 있으며 기본이 아닌 언어로는 0 개 이상의 레이블이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="94e05-193">용어에 언어 레이블이 있는 경우 레이블 중 하나가 기본 레이블 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="94e05-194">**sharepoint-분류법: defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="94e05-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="94e05-195">[용어의](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)필수 매개 변수인 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 에는이 기본 어휘 레이블을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-195">Use this default lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="94e05-196">[용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)를 시각적으로 표시 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-196">Use to visually representing the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="94e05-197">DefaultLabel을 정의 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="94e05-198">DefaultLabel에는 문자열 및 언어 태그와 같은 두 부분으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="94e05-199">언어는 [시](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 작업 언어 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-199">The language must be one of the [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="94e05-200">DefaultLabel은 동일한 계층 구조 수준에서 같은 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)의 모든 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 에 대해 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-200">The defaultLabel must be unique for all [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="94e05-201">**sharepoint-분류법: termSetName**</span><span class="sxs-lookup"><span data-stu-id="94e05-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="94e05-202">현재 TermSet 개체의 이름을 가져오고 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="94e05-203">[시](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 작업 언어로 된 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)의 어휘 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-203">This the lexical label for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="94e05-204">[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 대 한 필수 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-204">This is a required parameter for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="94e05-205">[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)을 시각적으로 나타내는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-205">Use to visually representing a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="94e05-206">TermSetName를 정의 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="94e05-207">**sharepoint-분류법: propertyName**</span><span class="sxs-lookup"><span data-stu-id="94e05-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="94e05-208">현재 TermSet 개체의 속성 이름을 가져오고 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="94e05-209">Sharepoint 분류법: SharedCustomPropertyForTerm, sharepoint-분류법: LocalCustomPropertyForTerm 및 sharepoint-분류법: CustomPropertyForTermSet ( [시](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 작업 언어)에 대 한 어휘 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="94e05-210">Sharepoint-분류: propertyName은 CustomProperty의 키로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="94e05-211">PropetyName를 정의 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="94e05-212">선택적 레이블</span><span class="sxs-lookup"><span data-stu-id="94e05-212">Optional labels</span></span>

<span data-ttu-id="94e05-213">또한 분류에 선택적 레이블을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="94e05-214">**sharepoint-분류법: otherLabel**</span><span class="sxs-lookup"><span data-stu-id="94e05-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="94e05-215">[용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)에 대 한 대체 어휘 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-215">This is the alternate lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="94e05-216">OtherLabel을 정의 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="94e05-217">의미 관계</span><span class="sxs-lookup"><span data-stu-id="94e05-217">Semantic relationships</span></span>

<span data-ttu-id="94e05-218">분류에는 계층적이 고 간단한 "관련 용어" 연관 관계가 있지만 일부는 "의미 관계" 또는 사용자 지정 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="94e05-219">**sharepoint-분류법: 상위**</span><span class="sxs-lookup"><span data-stu-id="94e05-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="94e05-220">[용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 를 계층적으로 다른 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-220">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="94e05-221">[용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 는 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)의 최상위 [용어만](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 될 수 있지만 상위 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)를 포함 하지 않아야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-221">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="94e05-222">부모를 정의 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="94e05-223">즉, TermA1에 부모 TermA가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-223">This means that TermA1 has parent TermA.</span></span> <span data-ttu-id="94e05-224">이와 반비례 또한 TermA1은 TermA의 자식입니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-224">Inversely it also means that TermA1 is the child of TermA.</span></span> <span data-ttu-id="94e05-225">부모-자식 관계가 inversible 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-225">Parent-child relationship is an inversible relationship.</span></span>

<span data-ttu-id="94e05-226">**sharepoint-분류법: child**</span><span class="sxs-lookup"><span data-stu-id="94e05-226">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="94e05-227">이 개체는 자식 TermSet 인스턴스를 하나 이상 포함 하며 TermSets 속성을 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-227">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="94e05-228">또한이 클래스는 새 자식 TermSet 개체를 만들기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-228">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="94e05-229">하위 용어 및 TermSet 인스턴스 편집에 대 한 권한이 그룹에 지정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-229">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="94e05-230">[용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 를 계층적으로 다른 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-230">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="94e05-231">자식을 정의 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-231">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="94e05-232">즉, TermA에 자식 TermA1가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-232">This means that TermA has child TermA1.</span></span> <span data-ttu-id="94e05-233">이와 반비례 또한 TermA는 TermA1 부모-자식 관계 중 inversible 관계에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-233">Inversely it also means that TermA is the parent of TermA1 parent-child relationship is an inversible relationship.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="94e05-234">문서 참고 사항</span><span class="sxs-lookup"><span data-stu-id="94e05-234">Documentation notes</span></span>

<span data-ttu-id="94e05-235">이 섹션에서는 Microsoft. 분류법 네임 스페이스에 자세히 설명 되어 있는 분류에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-235">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="94e05-236">**sharepoint-분류: 설명**</span><span class="sxs-lookup"><span data-stu-id="94e05-236">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="94e05-237">[SharePoint 분류](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) 어휘 엔터티에 대 한 자세한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-237">This is a detailed explanation of any [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="94e05-238">설명을 추가 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-238">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="94e05-239">사용자 지정 속성</span><span class="sxs-lookup"><span data-stu-id="94e05-239">Custom properties</span></span>

<span data-ttu-id="94e05-240">현재 용어 개체에 대 한 사용자 지정 속성 개체의 컬렉션을 읽기 전용 사전에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-240">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="94e05-241">사용자 지정 속성 [은 용어나](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 대해 정의할 수 있는 키-값 쌍으로, [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 또는 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 대 한 설명을 추가로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-241">Custom Properties are key-values pairs that can be defined for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="94e05-242">SharePoint는 propertyName에 대 한 도움말을 사용 하 여 사용자 지정 속성의 키를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-242">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="94e05-243">**sharepoint-분류법: CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="94e05-243">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="94e05-244">이를 정의 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-244">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="94e05-245">**sharepoint-분류법: SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="94e05-245">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="94e05-246">용어에 대 한 사용자 지정 속성을 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)와 함께 [전달 해야 하](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 는 경우에는 다른 곳에서 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 를 다시 사용할 때 sharedcustompropertyforterm에서 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-246">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="94e05-247">이를 정의 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-247">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="94e05-248">**sharepoint-분류법: LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="94e05-248">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="94e05-249">용어에 대 한 사용자 지정 속성을 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)와 함께 사용할 필요가 없는 경우 다른 곳에서 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 를 다시 사용 하는 경우 [에는](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) localcustompropertyforterm에서 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-249">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="94e05-250">이를 정의 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-250">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="94e05-251">데이터 속성</span><span class="sxs-lookup"><span data-stu-id="94e05-251">Data properties</span></span>

<span data-ttu-id="94e05-252">계층 구조의 각 수준에서 용어 또는 TermSet에 대 한 특정 데이터 속성을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-252">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="94e05-253">**sharepoint-분류법: Is사용 가능 For태깅**</span><span class="sxs-lookup"><span data-stu-id="94e05-253">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="94e05-254">이 방법을 사용 하 여 SharePoint 목록 및 라이브러리에서 [용어](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 또는 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 를 사용할 수 있는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-254">Use this to specify if a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="94e05-255">이에 대 한 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-255">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="94e05-256">도메인 및 범위</span><span class="sxs-lookup"><span data-stu-id="94e05-256">Domain and range</span></span>

<span data-ttu-id="94e05-257">아래 표에는 SharePoint 분류 어휘의 도메인 및 범위에 대 한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-257">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="94e05-258">조건자/동사</span><span class="sxs-lookup"><span data-stu-id="94e05-258">Predicates/verb</span></span>|<span data-ttu-id="94e05-259">의미</span><span class="sxs-lookup"><span data-stu-id="94e05-259">Meaning</span></span>|<span data-ttu-id="94e05-260">도메인</span><span class="sxs-lookup"><span data-stu-id="94e05-260">Domain</span></span>|<span data-ttu-id="94e05-261">Range</span><span class="sxs-lookup"><span data-stu-id="94e05-261">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="94e05-262">inTermSet</span><span class="sxs-lookup"><span data-stu-id="94e05-262">inTermSet</span></span>|<span data-ttu-id="94e05-263">용어 집합</span><span class="sxs-lookup"><span data-stu-id="94e05-263">In term set</span></span>|<span data-ttu-id="94e05-264">용어</span><span class="sxs-lookup"><span data-stu-id="94e05-264">Term</span></span>|<span data-ttu-id="94e05-265">용어 집합</span><span class="sxs-lookup"><span data-stu-id="94e05-265">Term Set</span></span>|
<span data-ttu-id="94e05-266">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="94e05-266">inTermGroup</span></span>|<span data-ttu-id="94e05-267">용어 그룹</span><span class="sxs-lookup"><span data-stu-id="94e05-267">In term group</span></span>|<span data-ttu-id="94e05-268">TermSet</span><span class="sxs-lookup"><span data-stu-id="94e05-268">TermSet</span></span>|<span data-ttu-id="94e05-269">TermGroup</span><span class="sxs-lookup"><span data-stu-id="94e05-269">TermGroup</span></span>|
<span data-ttu-id="94e05-270">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="94e05-270">topLevelTermOf</span></span>|<span data-ttu-id="94e05-271">가 최상위 수준인 경우</span><span class="sxs-lookup"><span data-stu-id="94e05-271">Is Top Level Term Of</span></span>|<span data-ttu-id="94e05-272">용어</span><span class="sxs-lookup"><span data-stu-id="94e05-272">Term</span></span>|<span data-ttu-id="94e05-273">TermSet</span><span class="sxs-lookup"><span data-stu-id="94e05-273">TermSet</span></span>|
<span data-ttu-id="94e05-274">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="94e05-274">hasTopLevelTerm</span></span>|<span data-ttu-id="94e05-275">최상위 용어 포함</span><span class="sxs-lookup"><span data-stu-id="94e05-275">Has top level term</span></span>|<span data-ttu-id="94e05-276">용어 집합</span><span class="sxs-lookup"><span data-stu-id="94e05-276">Term Set</span></span>|<span data-ttu-id="94e05-277">용어</span><span class="sxs-lookup"><span data-stu-id="94e05-277">Term</span></span>|
<span data-ttu-id="94e05-278">termSetName</span><span class="sxs-lookup"><span data-stu-id="94e05-278">termSetName</span></span>|<span data-ttu-id="94e05-279">용어 집합 이름</span><span class="sxs-lookup"><span data-stu-id="94e05-279">Term set has Name</span></span>|<span data-ttu-id="94e05-280">용어</span><span class="sxs-lookup"><span data-stu-id="94e05-280">Term</span></span>|<span data-ttu-id="94e05-281">일반 리터럴</span><span class="sxs-lookup"><span data-stu-id="94e05-281">Plain literal</span></span>|
<span data-ttu-id="94e05-282">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="94e05-282">defaultLabel</span></span>|<span data-ttu-id="94e05-283">용어에 기본 레이블이 있음</span><span class="sxs-lookup"><span data-stu-id="94e05-283">Term has default label</span></span>|<span data-ttu-id="94e05-284">용어</span><span class="sxs-lookup"><span data-stu-id="94e05-284">Term</span></span>|<span data-ttu-id="94e05-285">일반 리터럴</span><span class="sxs-lookup"><span data-stu-id="94e05-285">Plain literal</span></span>|
<span data-ttu-id="94e05-286">otherLabel</span><span class="sxs-lookup"><span data-stu-id="94e05-286">otherLabel</span></span>|<span data-ttu-id="94e05-287">용어에 다른 레이블이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-287">Term has other label</span></span>|<span data-ttu-id="94e05-288">용어</span><span class="sxs-lookup"><span data-stu-id="94e05-288">Term</span></span>|<span data-ttu-id="94e05-289">일반 리터럴</span><span class="sxs-lookup"><span data-stu-id="94e05-289">Plain literal</span></span>|
<span data-ttu-id="94e05-290">propertyName</span><span class="sxs-lookup"><span data-stu-id="94e05-290">propertyName</span></span>|<span data-ttu-id="94e05-291">속성 레이블 있음</span><span class="sxs-lookup"><span data-stu-id="94e05-291">Has Property Label</span></span>|<span data-ttu-id="94e05-292">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="94e05-292">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="94e05-293">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="94e05-293">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="94e05-294">설명</span><span class="sxs-lookup"><span data-stu-id="94e05-294">description</span></span>|<span data-ttu-id="94e05-295">설명 있음</span><span class="sxs-lookup"><span data-stu-id="94e05-295">Has Description</span></span>|<span data-ttu-id="94e05-296">전체</span><span class="sxs-lookup"><span data-stu-id="94e05-296">All</span></span>|<span data-ttu-id="94e05-297">일반 리터럴</span><span class="sxs-lookup"><span data-stu-id="94e05-297">Plain literal</span></span>|
|<span data-ttu-id="94e05-298">상위</span><span class="sxs-lookup"><span data-stu-id="94e05-298">parent</span></span>|<span data-ttu-id="94e05-299">부모 있음</span><span class="sxs-lookup"><span data-stu-id="94e05-299">Has parent</span></span>|<span data-ttu-id="94e05-300">용어</span><span class="sxs-lookup"><span data-stu-id="94e05-300">Term</span></span>|<span data-ttu-id="94e05-301">용어</span><span class="sxs-lookup"><span data-stu-id="94e05-301">Term</span></span>|
|<span data-ttu-id="94e05-302">하위</span><span class="sxs-lookup"><span data-stu-id="94e05-302">child</span></span>|<span data-ttu-id="94e05-303">하위 있음</span><span class="sxs-lookup"><span data-stu-id="94e05-303">Has Child</span></span>|<span data-ttu-id="94e05-304">용어</span><span class="sxs-lookup"><span data-stu-id="94e05-304">Term</span></span>|<span data-ttu-id="94e05-305">용어</span><span class="sxs-lookup"><span data-stu-id="94e05-305">Term</span></span>|
|<span data-ttu-id="94e05-306">Isto For태깅</span><span class="sxs-lookup"><span data-stu-id="94e05-306">isAvailableForTagging</span></span>|<span data-ttu-id="94e05-307">태그 지정 가능</span><span class="sxs-lookup"><span data-stu-id="94e05-307">Is available for tagging</span></span>|<span data-ttu-id="94e05-308">용어, 용어 집합</span><span class="sxs-lookup"><span data-stu-id="94e05-308">Term, Term Set</span></span>|<span data-ttu-id="94e05-309">부울</span><span class="sxs-lookup"><span data-stu-id="94e05-309">Boolean</span></span>|
|<span data-ttu-id="94e05-310">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="94e05-310">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="94e05-311">공유 사용자 지정 속성 있음</span><span class="sxs-lookup"><span data-stu-id="94e05-311">Has shared custom property</span></span>|<span data-ttu-id="94e05-312">용어</span><span class="sxs-lookup"><span data-stu-id="94e05-312">Term</span></span>|<span data-ttu-id="94e05-313">Boolean, string, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="94e05-313">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="94e05-314">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="94e05-314">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="94e05-315">로컬 사용자 지정 속성 있음</span><span class="sxs-lookup"><span data-stu-id="94e05-315">Has local custom property</span></span>|<span data-ttu-id="94e05-316">용어</span><span class="sxs-lookup"><span data-stu-id="94e05-316">Term</span></span>|<span data-ttu-id="94e05-317">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="94e05-317">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="94e05-318">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="94e05-318">CustomPropertyForTermSet</span></span>|<span data-ttu-id="94e05-319">사용자 지정 속성 포함</span><span class="sxs-lookup"><span data-stu-id="94e05-319">Has Custom Property</span></span>|<span data-ttu-id="94e05-320">TermSet</span><span class="sxs-lookup"><span data-stu-id="94e05-320">TermSet</span></span>|<span data-ttu-id="94e05-321">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="94e05-321">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="94e05-322">| [SharePoint 분류](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) 에서 허용 하지 않는 [os](https://www.w3.org/TR/skos-primer/) 의 유효한 시나리오:</span><span class="sxs-lookup"><span data-stu-id="94e05-322">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="94e05-323">계층 구조 중복성-나머지 여러 개념에 동시에 연결할 수 있지만 sharepoint 분류법: 용어 [에는 하나의](https://www.w3.org/TR/skos-primer/) sharepoint 분류법만 있을 수 있으며, 따라서 순환 종속성도 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-323">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="94e05-324">고아 용어는 SharePoint 분류에서 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-324">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="94e05-325">모든 sharepoint-분류: 용어에는 sharepoint 분류법: parent가 있거나 sharepoint-분류법: topLevelTermOf a TermSet 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-325">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="94e05-326">SharePoint 분류법은 결합형 관계를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-326">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="94e05-327">SharePoint 분류법은 두 가지 유형의 계층 구조, 즉 sharepoint-분류법: parent 및 sharepoint-분류법: 하위만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-327">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="94e05-328">과 [(와) 달리,](https://www.w3.org/TR/skos-primer/) SharePoint 분류 어휘의 계층적 관계는 동일한 TermSet 내 에서만 용어를 사용 하 여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94e05-328">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="94e05-329">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94e05-329">See also</span></span>

[<span data-ttu-id="94e05-330">운영 체제 기반 형식으로 된 용어 집합 가져오기</span><span class="sxs-lookup"><span data-stu-id="94e05-330">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)

